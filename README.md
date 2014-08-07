# xss-cleaner
===========

A simple yet effictive PHP class to clean your users' inputs and avoid XSS injections.

## Usage
### basic usage
```
$xss = new xss;
$xss->clean(
  array(
    'first_name' => 'str', 
    'last_name'  => 'str',
    'email'      => 'email',
    'website'    => 'url',
    'rating'     => 'float',
    'usr_id'     => 'int'
  ));
$input = $xss->get();
echo $input['first_name'];
echo $input['rating'];
// ...
```

### object notation
If you like to use the object notation, you only need to set the second argument of `clean()` method to true. 
Let's take the same example as before:

```
$xss = new xss;
$xss->clean(
  array(
    'first_name' => 'str', 
    'last_name'  => 'str',
    'email'      => 'email',
    'website'    => 'url',
    'rating'     => 'float',
    'usr_id'     => 'int'
  ), TRUE);
$input = $xss->get();
echo $input->first_name;
echo $input->rating;
// ...
```

## Available filters
`str` => string

`int` => integer

`email`

`boolean`

`float` 

`url` 

`ip`


### getting errored fileds
You can get the errored fileds as followed:
```
echo 'Errors: '.$this->_errors; // errors number
foreach($xss->_erroredFields as $error)
{
  echo $error
}
```
