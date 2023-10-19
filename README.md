<IfModule mod_rewrite.c>
    <IfModule mod_negotiation.c>
        Options -MultiViews
    </IfModule>

    RewriteEngine On

    # Redirect to public/index.php
    RewriteCond %{REQUEST_URI} !^/public/
    RewriteRule ^(.*)$ /public/$1 [L]

    # Handle public/index.php
    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteRule ^ /public/index.php [L]
</IfModule>

<IfModule mod_headers.c>
    <FilesMatch "\.(eot|otf|ttf|woff|woff2|ico)$">
        Header set Access-Control-Allow-Origin "https://"
    </FilesMatch>
</IfModule>

