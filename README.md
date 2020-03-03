# php
php-7.4 new features

# Typed Properties

```php
class Person{
	public int $age;
	public string $first_name;

	function __construct($age, $first_name){
		$this->age = $age;
		$this->first_name = $first_name;
	}
}

$joe = new Person(24,'Joe');
```


# Spread Operator
Spread operator should have a better performance than array_merge. It's because not only that spread operator is a language structure while array_merge is a function call, but also compile time optimization can be performant for constant arrays.

```php
function greys() {
	return ['light grey','dark_grey','grey'];
}

function hex_colors(){
	for($i=0;i<=9;i++){
		yield "00000" . $i;
	}
}


$primary_colors = ['red','green','blue'];
$more_colors = ['purple','orange','yellow',...$primary_colors];
$all_colors = [...$primary_colors,...$more_colors,'white','black',...greys(),...hex_colors()];


print_r($all_colors);
```

# Arrow Function
- They can only have one expression:
a return statement
- Do not use the return keyword
- They support type hinting and the spread operator

```php
$square = function($num){
	return $num*$num;
};

$square = fn($num) => $num * $num;
echo $square(10);

$factor = 10;
$multiply = function($num) use($factor){
	return $num * $factor;
};

$multiply = fn($num) =>  $num * $factor;
echo $multiply(10);


$numbers = [1,2,3];
$squares = array_map(fn($num) => $num*$num,$numbers);
print_r($squares);
