### Exercise Three

**Context:** WordPress Plugin

```php
/**
 * Retrieve an API response and return the body as an array.
 *
 * @param string $url The API URL.
 *
 * @return array The decoded JSON response.
 */
function get_api_response( $url ) {
    $json = file_get_contents( $url );

    return json_decode( $json, false );
}
```

Note:

* Does it work?
* Does it work well?
    - Uses file_get_contents() instead of the WP HTTP API
    - No caching
    - No error handling
* Does it meet our standards (WordPress coding standards)?
    - Returns object, DocBlock claims array
