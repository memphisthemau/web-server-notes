# WSGI and `nginx`

* Two distinct components that makes up the _web server_: uWSGI and `nginx`.
  * uWSGI acts as and _application server_.
  * `nginx` handles and forwards the HTTP requests.
* Ease of _partinioning_ between development and production environment.
  * Code development and testing is done using _virtual environments_ using high TCP ports.
  * Production code is run via _application servers_ wtih `nginx` handling and serving the client HTTP requests.
* Perl and PHP language support is done via uWSGI plugin implementations.
 * https://uwsgi-docs.readthedocs.io/en/latest/Perl.html
 * https://uwsgi-docs.readthedocs.io/en/latest/PHP.html
