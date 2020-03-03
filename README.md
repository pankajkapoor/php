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
