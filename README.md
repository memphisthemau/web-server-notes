# Django, WSGI and `nginx` stack

* Two distinct components that makes up the _web server_, so it decouples the application from the web server: uWSGI and `nginx`.
  * Because web servers cannot talk directly to Django. Instead requires a WSGI interface.
  * uWSGI acts as and _application server_.
  * `nginx` handles and forwards the HTTP requests.
* Ease of _partinioning_ between development and production environment.
  * Code development and testing is done using _virtual environments_ using high TCP ports.
  * Production code is run via _application servers_ wtih `nginx` handling and serving the client HTTP requests.
* Perl and PHP language support is done via uWSGI plugin implementations.
  * https://uwsgi-docs.readthedocs.io/en/latest/Perl.html
  * https://uwsgi-docs.readthedocs.io/en/latest/PHP.html
* Concept
```shell
web client <-> web server <-> tcp socket <-> uwsgi <-> Django
```
* Running the code in the development environment.
  * Multiple developers will have access to a pool of high-numbered TCP ports.
  * The pool of high-numbered ports are assigned to the developers.
  * Developers run and test their application in `virtualenv` sandboxes. `pip` is used to install required libraries into the sandboxed virtual environments without poluting the libraries on the host box.
* Running the code in the production environment.
  * Only ports 80 and 443 are available.
