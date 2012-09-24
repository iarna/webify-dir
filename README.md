webify-dir
==========

This is just a little hack of mine to make it trivial for me to reflect any
directory on my server as a website, either with a name I specify or a hash. 
Handy for all sorts of things, I initially created it to give myself an easy
way to view remote coverage reports that generated to HTML.  It's also a
nice way to view HTML docs bundled with a package, or any other random HTML
you come across.  More generally, I basically use this as a public_html
replacement.

How it works
------------

We create a file based apache rewrite map that rewrites [slugs][] off of our
domain based on rules from a text file.  These text files are super simple,
just the slug followed by a space and then what to rewrite to.

  [slugs]: http://en.wikipedia.org/wiki/Slug_%28web_publishing%29

The shell script uses Perl to figure out the absolute path from your
relative one and openssl generate a hash from that.  It uses the hash as the
slug if you don't specify one.

Finally, it tells you what your shiny new URL is.  This here isn't generic,
obviously, it's filled in with my own domain, but it can be easily adapted.
