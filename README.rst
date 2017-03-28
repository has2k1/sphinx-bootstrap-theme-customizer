#################################
Sphinx Bootstrap Theme Customizer
#################################

`Sphinx Bootstrap Theme`_ brings to `Sphinx`_ documentation generator
the variety of `Bootswatch`_ CSS themes. Though well organized, the
process from customization to usable Sphinx theme is elaborate. This
customizer automates that process.

As the Bootswatch themes were not specifically designed for styling
code documentation, the CSS is also modified (see: `sphinx.less` and
`code_pygments.css` files) to improve code layout and highlighting
as required by sphinx. These modifications borrow from `sphinx_rtd_theme`_.


How does it work?
=================

The Bootswatch themes are designed in a dynamic form with a
*brand_color* variable that governs most of color scheme. A bunch
of other colors are generated from that one color alone. This
customizer changes the *@brand_color* `less`_ variable of your
preferred Bootswatch theme, and then builds a Sphinx theme.

Usage
=====

To change the *brand_color* of for `sandstone theme`_ sandstone, `cd`
into this projects directory, issue one command and a new theme will
be generated.

.. code-block:: bash

   $ build '#AACCDD' sandstone

The created theme is stored in the ``theme`` directory. You can then
copy that theme to the Sphinx directory and with these settings in
``conf.py`` it will be the theme that sphinx uses.

.. code-block:: python

   html_theme = 'theme'
   html_theme_path = ['.']

See the `Sphinx documentation on theming`_.


Requirements
============

The build tools used by Bootswatch themes require nodejs_ infrastructure.
Assuming you use Linuxbrew or Homebrew, these commands will install the
required packages as a user.

1. Clone repository::

    $ git clone https://github.com/has2k1/sphinx-bootstrap-theme-customizer

2. Install nodejs and npm::

    $ brew install nodejs
    $ brew install npm
    # fix npm path ...

These `npm instructions`_ may be useful.

3. Install *less* compile and css minifier::

    $ npm install -g less
    $ npm install -g clean-css
    $ npm install -g clean-css-cli

4. You can now do some customization, see usage information above.


.. _`Sphinx Bootstrap Theme`: https://github.com/ryan-roemer/sphinx-bootstrap-theme
.. _`Bootswatch`: http://bootswatch.com/
.. _`Sphinx`: http://sphinx-doc.org/
.. _`less`: http://lesscss.org/
.. _`sandstone theme`: https://bootswatch.com/sandstone/
.. _`Sphinx documentation on theming`: http://www.sphinx-doc.org/en/stable/theming.html#using-a-theme, 
.. _nodejs: https://nodejs.org/en/
.. _`npm instructions`: http://stackoverflow.com/questions/10081293/install-npm-into-home-directory-with-distribution-nodejs-package-ubuntu/13021677#13021677
.. _`sphinx_rtd_theme`: https://github.com/rtfd/sphinx_rtd_theme
