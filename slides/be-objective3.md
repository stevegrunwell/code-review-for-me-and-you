**Not so great:**

> Output should be escaped

**Better:** <!-- .element: class="fragment" data-fragment-index="0" -->

> The output of this HTML attribute should be escaped via [`esc_attr()`](https://developer.wordpress.org/reference/functions/esc_attr/).

<!-- .element: class="fragment" data-fragment-index="0" -->

Note:

* If you're referencing a specific function or library, it can be helpful to provide a link to the relevant docs
* Supports your case + gives dev more background
    - Could lead the dev to read more about sanitization and late-escaping in WP
