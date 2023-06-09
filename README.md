
# Table of Contents

1.  [Project structure and layout](#org3c3b74c)
    1.  [Tags legend](#org641090b)
2.  [Installation](#org843699a)
    1.  [Use as channel](#org67d30fd)
    2.  [Use as build/install source](#org84b835a)
3.  [References](#org9259bb9)
    1.  [Guix channels](#org31030ae)
    2.  [etc](#org81bc0dd)

*FFAB :: Flock Full of Aleatory Burden*

[![builds.sr.ht status](https://builds.sr.ht/~hellseher/ffab.svg)](https://builds.sr.ht/~hellseher/ffab?)

This repository contains packaging process and patches contributed to <guix-patches@gnu.org>. It
also can be used as stand alone Guix channel.

The main target is to collect packages related to Astronomy, Astrophysics and group of languages
such as **Common Lisp**, **Golan** and **Python**.

`master` branch contains packages passed lint and build procedures and is intended to be save to
use all the time, `wip-` branches might be broken on some stage.


<a id="org3c3b74c"></a>

# Project structure and layout

Layout follows Guix upstream.

    ../
    ├── etc
    ├── ffab
    │   ├── guix
    │   │   ├── build-system
    │   │   └── import
    │   └── packages
    │       └── patches
    ├── org
    ├── patches
    ├── scripts
    └── tmp
    
    12 directories

-   **./issues.org:** Tracks all sent patches to <guix-patches@gnu.org>
-   **./TODO.md:** Generated report from packaging process in `org/` directory.
-   **./Makefile:** Contains CI aware lint and build targets with convenient tooling for local build.

    :guix-commit 44bbfc24e4bcc48d0e3343cd3d83452721af8c36
    :accepted 174
    :pending 159
    
    :astronomy 24
    :golang 70
    :lisp 6
    :python 12
    :misc 20
    
    :date Fri 9 Jun 22:49:37 BST 2023

Any packages with suffix **-ffab** are meant to be accepted in Guix upstream but have kind of
modifications e.g. newer version, enabled tests etc.


<a id="org641090b"></a>

## Tags legend

There is an essential priority tag set is applied to manager the order of packaging for large
project and ease the pace of patch preparation. They are not strict and just intended to visualize
the current effort

-   **p1:** In the head of the packaging queue, tried to packed, resolving issues with dependencies and
    eventually packed.
-   **p2:** The patch is prepared from `guix` checkout.
-   **p3:** The patch set is sent for review.
-   **p4:** Initial estimation is made for the future packaging steps and resolving dependencies issues.
-   **p5:** Dormant or not so interested right now.


<a id="org843699a"></a>

# Installation

All examples are based on assumptions that `guix` is the main system or available as package
manager.


<a id="org67d30fd"></a>

## Use as channel

`/.config/guix/channels.scm`

    (cons* (channel
            (name 'ffab)
            ;; Mirror https://github.com/Hellseher/guix-channel
            (url "https://git.sr.ht/~hellseher/ffab"))
           %default-channels)


<a id="org84b835a"></a>

## Use as build/install source

    ~$ git clone https://git.sr.ht/~hellseher/ffab
    ~$ cd ffab
    ~$ guix build -L . python-sunpy


<a id="org9259bb9"></a>

# References

Main official resources:

-   **VCS:** <https://git.savannah.gnu.org/cgit/guix.git> Read only git repository hosted at Savanha.
-   **CI and Substitutes:** -   <https://ci.guix.gnu.org> Main CI and substitute and server
    -   <https://bordeaux.guix.gnu.org/> Secondary substitute server
-   **HPC:** <http://hpc.guix.info/> Reproducible software deployment for high-performance computing.
-   **Data Service:** <https://data.guix.gnu.org/>
-   **QA Service:** <https://qa.guix.gnu.org/>
-   **Issues:** <https://issues.guix.gnu.org/>


<a id="org31030ae"></a>

## Guix channels

-   <https://github.com/flatwhatson/guix-channel>
-   **nonguix:** Guix channel for packages that can&rsquo;t be included upstream. Please do NOT promote or
    refer to this repository on any official Guix communication channels.
    <https://gitlab.com/nonguix/nonguix>
-   **guixrus:** Curated collection of packages with goal to promote them to upstream
    <https://sr.ht/~whereiseveryone/guixrus/>
-   **Guix Gaming Channels:** A collection of gaming-oriented channels for Guix
    <https://gitlab.com/guix-gaming-channels>
-   **Guix Science:** Free scientific packages for GNU Guix <https://github.com/guix-science/guix-science>
    and non-free scientific packages for GNU Guix <https://github.com/guix-science/guix-science-nonfree>
-   **Emacs channel:** Guix channel for automatically generated emacs packages
    <https://github.com/babariviere/guix-emacs>


<a id="org81bc0dd"></a>

## etc

-   <https://github.com/ryanprior/guix-packages>
-   <https://github.com/BIMSBbioinfo/guix-bimsb>
-   <https://github.com/techenthusiastsorg/awesome-guix>

