---
layout: post # page | post
title: 40 Bibliografia
date: 2017-06-17 
description:     # Argument
keywords:        # Paraules clau
coments: true    # Comentaris activats
---

Documento de trabajo, iremos puliéndolo para explicar cómo insertar referenias bibliográficas.


Bibtex

Citas bibliográficas automáticas

1. Instalamos paquete en Emacs mediante MELPA (Milkypostman’s Emacs Lisp Package Archive) es un repositorio de programas de Emacs.

Elegimos el paquete basado en [![MELPA](http://melpa.org/packages/helm-bibtex-badge.svg)](http://melpa.org/#/helm-bibtex)

Iniciamos Emacs y escribimos:

`M-x package-install <RET>` RET significa que pulsemos la tecla de retorno.

Escribimos `helm-bibtex <RET>`

Así ya tendremos instalado el paquete.

2. Configuramos **org-ref**

(setq org-ref-notes-directory "$SOME"
      org-ref-bibliography-notes "$SOME/index.org"
      org-ref-default-bibliography '("$SOME/index.bib")
      org-ref-pdf-directory "$SOME/lib/")
      
3. Configuramos **helm-bibtex**

(setq helm-bibtex-bibliography "$SOME/index.bib" ;; where your references are stored
      helm-bibtex-library-path "$SOME/lib/" ;; where your pdfs etc are stored
      helm-bibtex-notes-path "$SOME/index.org" ;; where your notes are stored
      bibtex-completion-bibliography "$SOME/index.bib" ;; writing completion
      bibtex-completion-notes-path "$SOME/index.org"
)

4. Intercalamos dentro de un documento **orgmode**

:INTERLEAVE_PDF:

5. Referencias

- [Codearsonist](https://codearsonist.com/reading-for-programmers)
- [Org-Ref Manual](https://github.com/jkitchin/org-ref/blob/master/org-ref.org)
