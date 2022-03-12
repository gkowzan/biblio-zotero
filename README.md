Retrieve and insert BibTeX records from various sources by using [Zotero translation server](https://github.com/zotero/translation-server). Calling `biblio-zotero-insert-bibtex` will forward the provided URL to the server and insert a formatted BibTeX entry in the current buffer.

# Install

## straight.el

Users of [straight.el](https://github.com/raxod502/straight.el) can use the following recipe:

``` emacs-lisp
(straight-use-package '(:type :git :host github :repo "gkowzan/biblio-zotero"))
```

or with [use-package](https://github.com/jwiegley/use-package) integration:

``` emacs-lisp
(use-package biblio-zotero
  :straight (biblio-zotero type git :host github :repo "gkowzan/biblio-zotero")
  :commands (biblio-zotero-insert-bibtex))
```

## Directly

The repository can also be cloned to `some-path` and loaded directly:

``` emacs-lisp
(add-to-list 'load-path some-path)
(require 'biblio-zotero)
```

provided [biblio-core](https://github.com/cpitclaudel/biblio.el) is already installed.

# Configure

`biblio-zotero-translation-server` variable needs to contain the address of a running Zotero server instance. The default value points to localhost. The easiest way to run your local instance is to set up [Docker](https://www.docker.com) and run the server with:

```sh
docker pull zotero/translation-server
docker run -d -p 1969:1969 --restart-always --rm --name translation-server zotero/translation-server
```

The `--restart-always` flag ensures that the server will start with docker.

# See also

[ebib-zotero](https://github.com/gkowzan/ebib-zotero) uses this package to add new entries directly to your ebib database.
