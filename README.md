# PHP COOKIE
---
PHP library for handling cookies


### Install
See in packagist
````
https://packagist.org/packages/fatkulnurk/cookies
````
with composer
```
composer require fatkulnurk/cookies
```

### Usage

**Custom cookie with options:**

calling all methods is not needed, just use as necessary and end by calling the save () method;

````
(new Cookie('name'))
    
    // string|null the domain that the cookie will be valid for (including subdomains) or `null` for the current host (excluding subdomains)
    ->setDomain('example.com')
    
    //  bool indicates that the cookie should be accessible through the HTTP protocol only and not through scripting languages
    ->setHttpOnly(true)
    
    //int the Unix timestamp indicating the time that the cookie will expire at, i.e. usually `time() + $seconds`
    ->setExpiryTime(time() + 360000) // or ->setMaxAge(36000) without time()
        
    // @var string the path on the server that the cookie will be valid for (including all sub-directories), e.g. an empty string for the current directory or `/` for the root directory */
    ->setPath('/')
    
    // bool indicates that the cookie should be sent back by the client over secure HTTPS connections only
    ->setSecureOnly(false)
    
    // mixed|null the value of the cookie that will be stored on the client's machine
    ->setValue('fatkul nur koirudin')
    
    // save
    ->save();
````

**Add value to a cookie:**
```
Cookie::set('name', 'Fatkul Nur Koirudin');

// same with

Cookie::setCookie('name', 'Fatkul Nur Koirudin');
```

**Return the cookies value by key:**
```
Cookie::get('keyname');
```

**Destroys Cookie:**

by default cookie can't destroy, cookie will be change to empty value.

```
Cookie::destroy('name')

// same with

Cookie::set('name', '');
```