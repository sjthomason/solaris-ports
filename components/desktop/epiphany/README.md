## GNOME Web (epiphany)

This is the GNOME Web browser, formerly known as 'epiphany'.

To build and run, you need the [webkitgtk4](../webkitgtk4/) package
from this repo, in place of webkitgtk4 from the Solaris userland gate.
In addition, you will need `libdazzle`, also found in this repo.

By default, this package depends on the icu from the userland gate.
If you are running under 11.3 and have dependencies on the existing
icu, then build the [icu-gcc](../../icu-gcc) in this repo and uncomment
the relevant lines in the Makefile to use it.

Performance is decent relative to Firefox.  Compare the results of the
JetStream test:

### GNOME Web 3.30.2 powered by WebKitGTK+ 2.22.3 (64-bits)
![screenshot](https://raw.githubusercontent.com/RocketMan/solaris-ports/master/components/desktop/epiphany/screenshot-epiphany.png "Epiphany/WebKitGTK+")
(Shown using the [nimbus-gtk3](../../look-and-feel/nimbus-gtk3/)
theme, available in this repo.)

### Firefox 52.9.0 ESR (32-bits)
![screenshot](https://raw.githubusercontent.com/RocketMan/solaris-ports/master/components/desktop/epiphany/screenshot-firefox.png "Firefox 52.9.0esr")

### Firefox 60.3.0 ESR (64-bits)
![screenshot](https://raw.githubusercontent.com/RocketMan/solaris-ports/master/components/desktop/epiphany/screenshot-firefox-60.3.0.png "Firefox 60.3.0esr")

