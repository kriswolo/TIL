# Delete cookies using jQuery

Normally, to delete a cookie, you use:
```
$.cookie(COOKIE_NAME, null, {path: '/'}
```
However if Chrome's `keep where you left off` feature is turned on, cookies will not be deleted, but have a value of null instead