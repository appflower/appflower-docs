# REST API
It is possible to access the AppFlower widgets by a Representational State Transfer (REST) interface.

## Authentication via API Key

Each user has an API key to access the web application, which means cookies are not needed when the API key is used. The API key has to be provided as an additional GET parameter, 'af_apikey'.

The access to the API key is not enabled by default. To enable it, put the 'afApikeySecurityFilter' before the security filter in your filters.yml file:

<pre>
apikey_security:
    class: afApikeySecurityFilter
security: ~
</pre>

The API key value is returned by 'afApikeySecurityFilter::getApikey($sfGuardUser)'. Usually, the API key value is displayed on the user's profile page.

Users can change their API key value by changing their passwords. The old API key becomes invalid once the password is changed.

The API key value is protected by a site secret. You can configure your 'app_appFlower_siteSecre' in the app.yml file, to a random value. This will prevent others from guessing the user password via API key values.

## List Views
Every List View action can be accessed via the REST interface. Here's an example:

<pre>
/customer/listCustomer?af_format=json&af_apikey=...
</pre>

The requested output format is defined by the "af_format" GET parameter. Supported values are "af_format=json" and "af_format=csv".

## A Form Submit

It is also possible to read and submit a form via the REST interface.

Fetching a form by PHP:

<pre>
$formUrl = 'https://localhost/customer/editCustomer?id=1';
$apikey = '...~user@example.com';

$url = $formUrl.'&af_format=json&af_apikey='.urlencode($apikey);
$response = file_get_contents($url);
if ($response === false) {
    throw new Exception('Unable to fetch the URL: '.$url);
}

echo "JSON response: $response\n";

$json = json_decode($response, true);
if ($json === null) {
    throw new Exception('Unable to decode the JSON response: '.$response);
}

if (!isset($json['success']) || $json['success'] !== true) {
    throw new Exception('A form display error: '.$response);
}
</pre>

The fetched JSON will contain the form field values. The hidden fields are also included. They have to be preserved when submitting the form.

Submitting the form:

<pre>
$submitUrl = $json['af_submitUrl'].'?af_apikey='.urlencode($apikey);
$data = $json;
$data['edit[name]'] = 'Changed name';

$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, $submitUrl);
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_POSTFIELDS, $data);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HEADER, false);
curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, false);
curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, false);

$result = curl_exec($ch);
if ($result === false) {
    throw new Exception('Unable to post data: '.curl_error($ch));
}

curl_close($ch);

echo "JSON result: $result\n";

$json = json_decode($result, true);
if ($json === null) {
    throw new Exception('Unable to decode the JSON result: '.$result);
}

if (!isset($json['success']) || $json['success'] !== true) {
    throw new Exception('A form validation error: '.$result);
}
</pre>

The example changes the value of the 'edit[name]' form field, by corresponding to the 'name' field defined in the form's XML configuration.