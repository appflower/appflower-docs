# Coding Style

# IDE preferences
Tabs - should be replaced by 4 spaces(soft tabs)

# Definitions
Variable definitions - preferred naming variables in lower case, and preferred small 1 word name (error, location etc.), but if needs to use 2 or more word in variable name definition use camel style (className, parentScope etc.)

# Operators definition
‘if’, ‘foreach’ etc - first bracket should be on same line with block definition, example:

<pre class="brush: php;">
if (null !== $this->compiled) {
    return $this->compiled;
} else {
    return false;
}
</pre>

Spaces in block definition - Every part in block definition should be separated by 1 space, example:

<pre>
if (null !== $this->compiled && true === $this->validate) {
</pre>

Parts of ternary operator also should be separated by space, example:
<pre>
isset($this->defaults[$name]) ? $this->defaults[$name] : null;

	// not 

isset($this->defaults[$name])?$this->defaults[$name]:null;
</pre>

Spaces in calling functions, object methods, example:
<pre>
preg_replace_callback('/pattern/', $replacer, $string)
</pre>

Concatenation with spaces, example:
<pre>
$path . DIRECTORY_SEPARATOR . $file_name;
</pre>

Spaces in arithmetic operators, example:
<pre>
$a * $b
($a + $b) * $c
</pre>

Spaces in assognment operator definition, example:
<pre>
$a = 5;
  // not 
$a=5;
</pre>

# PHP files definition
php files should be written only with open php tag, without close tag, example:
<pre>
&lt;?php
    // definition … 
?&gt;
</pre>

# Class and Methods declarations
for class and method first bracket should be placed in new line, example:
<pre>
class Route
{

public function getPattern()
</pre>
    		{
for methods even if method is public should be defined ‘public’, example:
<pre>
public function getPattern()

  // not as PHP 4 style!

function getPattern()
</pre>

Static word should be first, example:
<pre>
static public function getPattern()

  // not 

public static function getPattern()
</pre>

Ordering methods in class - methods, properties should be ordered by they access type, example:

<pre>
// constants
		
public properties
protected properties
private properties
		
public methods
protected methods
private methods
</pre>

before return should be 1 empty line, example:
<pre>
public function setDefault($name, $default)
    {
        $this->defaults[$name] = $default;
		                                      
        return $this;
    }
</pre>

All classes and methods should be documented, all parameters in methods should be described, author parameter also required. Spaces between params in declaration method, example:
<pre>
public function renderFile($file, $parameters)
</pre>

Defining expected parameter type - where it possible, example:
<pre>
public function renderFile($file, array $parameters)
public function executeIndex(sfWebRequest $request)
</pre>

Separating large unreadable methods(that may contains more than 80 lines) to few help methods constructor should contains only process initialization needed parts, and not to execute main part of class. Formatting call class. For more readable will be better to formatting call long methods using new line and shift, example:

<pre>
$type = new TypeGuess(
    'entity',
    array(
        'em' => $this->em,
        'class' => $mapping['targetEntity'],
        'multiple' => $multiple,
    ),
    Guess::HIGH_CONFIDENCE
);
</pre>

Same with defining arrays as defined in example above

<pre>			
array(
    'em' => $this->em,
    'class' => $mapping['targetEntity'],
    'multiple' => $multiple,
)
</pre>