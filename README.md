
# Postcodes


A Laravel 6 facade/service provider for the API methods at ```postcodes.io``` - useful for UK postcode validation and reverse geocoding: that is, determining postcode from lat, long coordinates.
**No fiddling around with api keys, authentication, necessary...**

With thanks to https://postcodes.io


## Installation

```
composer require codescheme/postcodes
```

## Basic Example Laravel Usage

Return data for a given postcode

```php
Route::get('/postcode', function(){
    $data = Postcode::postcodeLookup('SE21 8JL');
    print_r($data);
    return null;      
});	
```

## Methods

```
Postcode::validate('SE31 9AX'); //returns boolean
Postcode::postcodeLookup('SE21 8JL');
Postcode::nearest('SE21 8JL');
Postcode::reverseGeocode(-0.397913, 51.44015); // long,lat
Postcode::autocomplete('RG1 3');
Postcode::outcodeLookup('SE21');

$postcodes = ['OX49 5NU', 'M32 0JG', 'NE30 1DP'];
Postcode::postcodeLookupBulk($postcodes);
	
$coordinates = [
    ['longitude' =>  0.629834723775309, 'latitude' => 51.7923246977375],
    ['longitude' => -2.49690382054704, 	'latitude' => 53.5351312861402]
    ];
Postcode::reverseGeocodeBulk($coordinates);
```

## Testing

``` bash
$ composer test
```

