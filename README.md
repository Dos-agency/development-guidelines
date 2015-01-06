# Dos Development Guidelines


## .htaccess

### www. redirection

The same content should never be available under two different URLs, especially not with and without `www.` at the beginning. This can cause SEO problems (duplicate content), and therefore, you should choose one of the alternatives  and redirect the other one.

Add the following in your .htaccess to always redirect to the url without www. at the front. 

````
<IfModule mod_rewrite.c>
    RewriteEngine On
    RewriteCond %{HTTPS} !=on
    RewriteCond %{HTTP_HOST} ^www\.(.+)$ [NC]
    RewriteRule ^ http://%1%{REQUEST_URI} [R=301,L]
</IfModule>
```
