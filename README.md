```
source: clear
features:
  - php latest
  - mysql
root: public_html/public
nginx:
  fastcgi: "on"
  locations:
    - match: /
      try_files: $uri $uri/ /index.php$is_args$args
    - match: ~ \.[^\/]+(?<!\.php)$
      try_files: $uri =404
```