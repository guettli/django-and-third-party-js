# Django and Third Party JS

If you want to use a third party JS or CSS library in your Django application,
you have far too many options.

.... [Analysis paralysis](https://en.wikipedia.org/wiki/Analysis_paralysis)

For example you want to use [Boostrap](//getbootstrap.com/) or [htmx](//htmx.org).

Here I list the options you have, so that you have an overview to find
your solution.

Please give me feedback! Is there a feasible option missing in this list? Please share your solution.

# Public CDN

If the package is available via a public CDN, then you can use these files.

Example from [Bootstrap docs](https://getbootstrap.com/docs/5.1/getting-started/download/#cdn-via-jsdelivr)

```
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-ka7Sk0Gln4gmtz2MlQnikT1wXgYsOg+OMhuP+IlRH9sENBO0LRn5q+8nbTov4+1p" crossorigin="anonymous"></script>
```

Pro:

* super easy to set up. You don't need to download anything.

Con:

* If are offline, for example you are traveling, then you can't reach the public CDN.

# Vendor

To "vendor" a library means to copy the code of a third-party library into the own code base.

This is a common work-around for having no useable dependency management.

You could just take the `bootstrap.min.css` and `bootstrap.bundle.min.js` and copy these
files into your code.

Please use a directory called "vendor" to signal all participants, that this is code which was copied.

Pro:

* You don't need internet connection for development, since the files get served from your server.

Con:

* You have strange binary-like file in your git repo.
* If it is only one file, then it is not much work. But in the long run you might have many and maintaining them needs time.

# Python Webpack Boilerplate

You can use [Python Webpack Boilerplate](https://github.com/AccordBox/python-webpack-boilerplate).

I looks like a promising helper, but I have not used it up to now.



# xstatic

[python-xstatic](//xstatic.readthedocs.io/en/latest/) creates python packages for static files.
 
For example for Bootstrap you could install https://pypi.org/project/XStatic-Bootstrap/ via pip.

Pro:

* You can manage your dependencies with Python tools

Con:

* It is likely that you package you need was not uploaded yet.


# Related

[Thomas Working-out-Loud](//github.com/guettli/wol)

