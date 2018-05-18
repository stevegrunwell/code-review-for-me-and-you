### Exercise One

**Context:** WordPress plugin for PHP 5.3+

```php
/**
 * Given a $value in cents, print the value as a string in dollars.
 *
 * @param int    $value The value (in cents).
 * @param string $prefix Optional. A string to prepend to the
 *                       output. Default is "$".
 *
 * @return string The formatted currency string, in dollars.
 */
function print_currency( int $value, string $prefix = '$' ): string
{
    return number_format( $value, 2 ) . $prefix;
}
```

Note:

* Does it work?
    - Value in cents passed to number_format, should be divided by 100
    - Prefix is appended, not prepended
* Does it work well?
    - Type-hints are not permitted for PHP 5
* Does it meet our standards (WordPress coding standards)?
    - Braces
