# Base64 UID

Generate UID like YouTube.

## Introduction

The library generates a unique identifier consisting of 64 characters and a length of 10 characters *(you can change
the length of the identifier).* This gives us a lot of combinations.

```
64^10 = 2^60 = 1 152 921 504 606 846 976 (combinations)
```

To represent this number, imagine that in order to get all possible values of identifiers with a length of **10**
characters and generating an ID every microsecond, it takes **36 559** years.

[UUID](https://en.wikipedia.org/wiki/Universally_unique_identifier) works on the same principle, but its main drawback
is that it's too long. It is not convenient to use it as a public identifier, for example in the URL.

Due to the fact that **Base64 UID** uses 64 chars instead of 36, the identifier turns out to be noticeably shorter.
Also you have the opportunity to manage the long identifier and the number of possible values. This will optimize the length of the identifier for your business requirements.

## Installation

Pretty simple with [Composer](http://packagist.org), run:

```sh
composer require ofilin/base64uid
```

## Usage

```php
use ofilin\base64uid\Base64UID;

$uid = Base64UID::generate(); // iKtwBpOH2E
```

With length 6 chars

```php
// 64^6 = 68 719 476 736 (combinations)
$uid = Base64UID::generate(6); // nWzfgA
```

The floating-length identifier will give more unique identifiers.

```php
// 64^10 + 64^9 + 64^8 = 1 171 217 378 093 039 616 (combinations)
$uid = Base64UID::generate(random_int(8, 10));
```


## License

This bundle is under the [MIT license](http://opensource.org/licenses/MIT). See the complete license in the file: LICENSE
