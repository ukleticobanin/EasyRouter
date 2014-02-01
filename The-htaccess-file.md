# The .htaccess file

You must copy the [.htaccess](https://github.com/Teddy95/EasyRouter/blob/master/src/.htaccess) file into the root directory of your website! **Otherwise, EasyRouter won't work or will work faulty!**

### Content of .htaccess

```
Options +FollowSymLinks
RewriteEngine on

RewriteRule (.*)\ /index.php [L]

RewriteCond %{REQUEST_FILENAME} -f [OR]
RewriteCond %{REQUEST_FILENAME} -d
RewriteRule .+ - [L]
RewriteRule .* index.php [L]
```
