# Benchmarking AppFlower Projects
The afBenchmark plugin provides benchmarking info about AF applications. You can use it to benchmark a single widget or layout, all widgets in a module or the entire application. It measures and prints various execution times, counts DB queries, shows download speeds and response sizes as well as other useful details like averages and totals. With afBenchmark, it is easy to see how fast your AF application is. You can find and fix bottlenecks (if any) and detect execution errors.

# How to Install and setup
Installing the plugin is piece of cake, it can be done in two easy steps:
 - Checkout the source code from GitHub: 
<pre>
 git clone git@github.com:appflower/afBenchmarkPlugin.git %SF_ROOT_DIR%/plugins/afBenchmarkPlugin
</pre>
 - Open up %SF_ROOT_DIR%/plugins/afBenchmarkPlugin/config/app.yml and check:
Does the url key point to your AF application? Do username and password have correct values? These are only needed if your application uses authentication. Is your AF application running on port 80? If it isn't, you should set port too. The rest of the values should be fine for now. If you wanna tweak them, please check out [Configuration and Command-line options]. That's it. Now you should be able to run afBenchmark!

NOTICE: Please note that only afGuard authentication is supported at the moment, sfGuard or other custom mechanism won't work! 


# How to use the afBenchmarkPlugin
<pre>
 cd %SF_ROOT_DIR%
 ./symfony appflower:benchmark yourmodule/yourwidget
</pre>

The above command will print basic benchmarking results for yourmodule/yourwidget.
The following commands can provide different results, depending on what do you want to benchmark.

To benchmark a **single layout**, run:
<pre>
 ./symfony appflower:benchmark pages/yourlayout
</pre>

To benchmark **all widgets in a module**, run:
<pre>
 ./symfony appflower:benchmark yourmodule/*
</pre>

To benchmark **the entire app** (all layouts and widgets), run:
<pre>
 ./symfony appflower:benchmark
</pre>

To benchmark **all widgets** (no layouts), run:
<pre>
 ./symfony appflower:benchmark --layouts=0
</pre>

These are the most commonly used calls, but you can fine-tune output by adjusting various config options. To learn more about this, please refer to [Configuration and Command-line options]. Also keep in mind that the benchmarker comes with command-line help. When you need info, just run:

<pre>
 ./symfony help appflower:benchmark
</pre>
 
# Understanding the benchmark report
The benchmarker is able to produce either basic or verbose output. The former contains only basic information, whilst the latter has all the details. If you have **afProfiler Plugin** installed, profiling results will be also added to verbose output, making it even more detailed. 

This is how **basic** output looks like:
<pre>
 Widget                                      Status    Valid    totalTime        Data 
 ------------------------------------------------------------------------------------ 
   
 Processing widgets.. 
   
 ticket/list                                    200     true     1792ms       29,84KB 
</pre>

This is how **verbose** output looks like:
<pre>
 Widget                                      Status    Valid    connectTime    serverTime    transferTime    totalTime    averageSpeed        Data 
 -------------------------------------------------------------------------------------------------------------------------------------------------- 
   
 Processing widgets.. 
   
 ticket/list                                    200     true            0ms         820ms           272ms       1092ms        1,13KB/s       29,84KB 
</pre>

This is how **verbose profiler** output looks like:
<pre>
 Widget                                      Status    Valid    connectTime    actionTime    readTime    renderTime    serverTime    transferTime    totalTime    queriesCount    averageSpeed        Data 
 --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 
   
 Processing widgets.. 
   
 ticket/list                                    200     true            0ms           0ms         0ms          30ms         820ms           272ms       1092ms        12 (9ms)        1,13KB/s       29,84KB 
</pre>

The benchmarker prints **basic** output by default. If you want to make it verbose, add the **--verbose=1** switch to any of the calls listed above.  For instance, to obtain detailed results for widget "list" in module "ticket", you can call:

<pre>
 ./symfony appflower:benchmark ticket/list --verbose=1
</pre>

# What the benchmark details mean
In general, the afBenchmark Plugin behaves like your browser would, since it simulates a browser session. It calculates several values for each item it processed and prints results as a table. The values in the columns show you how long it took to fully render the given widget or layout, how much data was returned and other details. Results from various phases of processing are shown.

Here is a list of all the columns of the output table, with some sort description of each.

***Times and Sizes***
connectTime This much time was required to resolve the domain name and establish the HTTP connection.

actionTime The amount of time it took to perform the associated Symfony Action.

readTime The amount of time it took to read the item's XML config file.

renderTime XML reading, parsing and output (JS) generation time.

serverTime The total server-side processing time. At this point, response is ready to be sent back to the client.

transferTime The response download time. It always equals to totalTime - serverTime

totalTime The total processing time of this item. It includes all other times.

queriesCount The total number of DB queries and their total execution time.

averageSpeed Average download speed. This is either the download speed of the given layout, or - in case of widgets - the speed of the last request.

Data The total amount of data returned in response.

***Result validation***
There are 2 more columns in the output table, namely "Status" and "Valid". These indicate if processing of the given item was successful. The AF engine generates multiple requests to completely render a widget or a layout. These columns show you the end result of those requests. They might be helpful when you need to identify problematic widgets or detect missing parameters.

Status The "aggregated" HTTP Status code. If all requests were successful, its value is 200. Otherwise the item will be marked as failed (printed with red background).

Valid An item is considered valid only if all associated requests returned 200 and the response body contained valid data (HTML for layouts, JSON for widgets). In every other case the item will be marked as failed.
 
***Stats & Totals***
The benchmarker also prints various totals and stats once it finished its job.:

Totals
 * Total number of items processed and total execution time.
 * Number of failed items
 * Number of slow widgets (those that took more than 1000ms to run)

<pre>
 Finished at: 2011-05-28 22:24:08 
 Executed 32 item(s) in 34.866ms 
 Loading 2 items(s) failed due to errors! 
 20 widget(s) took more than 1000ms to run. 
</pre>

Stats HTTP response stats with counts, status codes and messages

<pre>
 HTTP Response stats:
 
 200 - OK ........................30 
 404 - Not Found .................2 
</pre>

Averages for all the columns mentioned above, calculated separately for widgets and layouts.

<pre>
 Connecting host: 0ms 
 Performing SF action: 17,19ms 
 Reading XML data: 8,75ms 
 Generation of content: 53,75ms 
 Server processing total: 916,13ms 
 Transfer time: 173,44ms 
 Total execution time: 1.089,56ms 
</pre>

# Configuration and Command-line Options
The plugin's configuration file is located in **%SF_ROOT_DIR%/plugins/afBenchmarkPlugin/config/app.yml**. 

Each configuration option has a command-line counterpart which takes precedence over the YML value. This allows you to set your default values in YML, and override them later if necessary. So for instance, to override the **username** and *password* settings, call the benchmarker like this:

<pre>
 ./symfony appflower:benchmark pages/dashboard --username=foo --password=bar
</pre>

Below is a list of all config values.:

size_unit The unit to use when calculating sizes. Valid values are **B** (Bytes) and **KB** (Kilobytes).

time_unit The unit to use when measuring times. Valid values are **s** (seconds) and **ms** (microseconds).
 
use_cache This is a boolean value. If true, the SF cache will be cleared before benchmarking.

url The app to be benchmarked. This should point to your AF application. 

NOTICE: Please note that benchmarking of remote applications is NOT supported (yet!) 

username and password These should be set correctly if the application requires authentication.

NOTICE: Please note that only **afGuard authentication** is supported at the moment, sfGuard or other custom mechanism won't work!

application The name of the Symfony application. Normally you don't need to change this.

env The Symfony environment to use. Ditto.

csrf This is another boolean. It should be true if your application uses CSRF protection.

layouts If you set this one to false, only widgets will be processed when running in bulk mode (appflower:benchmark without arguments)

params The value should be a query string. This allows you to supply request parameters to be passed to your widget / layout. However, currently this works only with one item at a time.

<pre>
 ./symfony appflower:benchmark module/widget --params=foo=bar&bar=1
</pre>

verbose You should set this one to true if you want verbose output to be generated. 