# Solstice Theme

The **Solstice** Theme is for [Grav CMS](http://github.com/getgrav/grav). It's a modified port of [solstice](https://templated.co/solstice) by Templated under its [CCA 3.0 license](https://templated.co/license). For additional modifications see CHANGELOG.md included in this release.

The Grav port includes an additional [Elements page](_demo/pages/90.elements/default.md) as per many Templated themes, to allow you to identify gaps in the theme's styling. There are a few.

![Solstice](screenshot.jpg)

## Quickstart Guide: Gulp usage

in /user/theme/solstice/

* Run `npm install` once to install packages

* Run `gulp` or `gulp serve` or `npm run serve` for development 
* Run `gulp fix` to automatically --fix code where possible

* Run `npm run build` for production build

(Developers) How-to [update](https://stackoverflow.com/a/69537863)


Gulp is configured to run the following functions:

* Autoreload on CSS/JS or content change
* Lint SCSS files via stylelint
* Concatenate and compile SCSS files to CSS
* Autoprefix and minify CSS file
* Minify JS files
* Move final CSS and JS files to the `/dist` folder

# Installation

Installing the solstice theme can be done in one of two ways. Our GPM (Grav Package Manager) installation method enables you to quickly and easily install the theme with a simple terminal command, while the manual method enables you to do so via a zip file.

## GPM Installation (Preferred)

The simplest way to install this theme is via the [Grav Package Manager (GPM)](http://learn.getgrav.org/advanced/grav-gpm) through your system's Terminal (also called the command line).  From the root of your Grav install type:

    bin/gpm install solstice

This will install the solstice theme into your `/user/themes` directory within Grav. Its files can be found under `/your/site/grav/user/themes/solstice`.

>> This method will copy the sample pages provided in the `_demo/pages` folder to your `user/pages` folder so that the theme will work out of the box with placeholder content. The content is the same _Ipsum lorem_ content provided in the original [Templated theme](https://templated.co/solstice).

## Manual Installation

To install this theme, just download the zip version of this repository and unzip it under `/your/site/grav/user/themes`. Then, rename the folder to `solstice`. You can find these files either on [GitHub](https://github.com/hughbris/grav-theme-solstice) or via [GetGrav.org](http://getgrav.org/downloads/themes).

You should now have all the theme files under

    /your/site/grav/user/themes/solstice

>> NOTE: If you want to use and adapt the default _Ipsum lorem_ content provided with the original theme, move the contents of `_demo/pages` into your grav installations's `user/pages` directory. This will ensure that the theme templates work out of the box.

# Updating

As development for the solstice theme continues, new versions may become available that add additional features and functionality, improve compatibility with newer Grav releases, and generally provide a better user experience. Updating solstice is easy, and can be done through Grav's GPM system, as well as manually.

## GPM Update (Preferred)

The simplest way to update this theme is via the [Grav Package Manager (GPM)](http://learn.getgrav.org/advanced/grav-gpm). You can do this with this by navigating to the root directory of your Grav install using your system's Terminal (also called command line) and typing the following:

    bin/gpm update solstice

This command will check your Grav install to see if your solstice theme is due for an update. If a newer release is found, you will be asked whether or not you wish to update. To continue, type `y` and hit enter. The theme will automatically update and clear Grav's cache.

## Manual Update

Manually updating solstice is pretty simple. Here is what you will need to do to get this done:

* Delete the `your/site/user/themes/solstice` directory.
* Download the new version of the solstice theme from either [GitHub](https://github.com/hughbris/grav-plugin-solstice) or [GetGrav.org](http://getgrav.org/downloads/themes#extras).
* Unzip the zip file in `your/site/user/themes` and rename the resulting folder to `solstice`.
* Clear the Grav cache. The simplest way to do this is by going to the root Grav directory in terminal and typing `bin/grav clear-cache`.

> Note: Any changes you have made to any of the files listed under this directory will also be removed and replaced by the new set. Any files located elsewhere (for example a YAML settings file placed in `user/config/themes`) will remain intact.

### Supported Page Templates

* [Sample homepage view template](templates/home.html.twig)
* [Left sidebar two-column template](templates/left-sidebar.html.twig)
* [Right sidebar two-column template](templates/right-sidebar.html.twig)
* [Single column template](templates/default.html.twig)

## Deferred assets block support

As [explained in the Grav blog](https://getgrav.org/blog/important-theme-updates), since Grav 1.5.10 deferred blocks are supported and these are implemented in this theme.

In a template that extends `partials/base.html.twig`, simply add a deferred block called `assets`. For example:

```twig
{% extends 'partials/base.html.twig' %}

{# for example, add a custom javascript file #}
{% block javascripts %}
  {% do assets.addJs('theme://js/site.js') }}
  {{ parent() }}
{% endblock %}

{# then override the default non-deferred assets block with a deferred block, and optionally alter it #}
{% block assets deferred %}
  {{ parent() }}
{% endblock %}
```

If several of your templates require a deferred asset block, either:

* create a common shared partial template, say `partials/extended-base.html.twig` with similar contents to the example above, and change your template files so that they extend this rather than `partials/base.html.twig`; _or_
* modify a copy of `partials/base.html.twig`.

# Setup

If you want to set solstice as the default theme, you can do so by following these steps:

* Navigate to `/your/site/grav/user/config`.
* Open the **system.yaml** file.
* Change the `theme:` setting to `theme: solstice`.
* Save your changes.
* Clear the Grav cache. The simplest way to do this is by going to the root Grav directory in Terminal and typing `bin/grav clear-cache`.

Once this is done, you should be able to see the new theme on the frontend. Keep in mind any customizations made to the previous theme will not be reflected as all of the theme and templating information is now being pulled from the **solstice** folder.

# Examples in the wild

* [Official demo](https://behold.metamotive.co.nz/solstice)

There's only one contrived one now :(

Please let me know if you want yours included (hey, it's free publicity).