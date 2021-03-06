======================================================
DreamCompute and DreamObjects documentation styleguide
======================================================

Basic Formatting
~~~~~~~~~~~~~~~~

Lines should be wrapped at 80 characters for readability. Trailing whitespaces
should also be watched out for and prevented. If your article describes how to
write code of some sort, ie. python, ansible, etc. add a file that contains
just the program and put it in examples/filename (relative to the article)
and include it at the end of your article. Article titles should be in the
"down style", only capitalize the first word in article titles and section
headings, except when a proper noun exists which is always capitalized. Use 4
spaces instead of one hard tab for indentation.

Headers
~~~~~~~

RST does not have strict requirements on header hierarchy, but keeping a
consistent hierarchy makes thing easier to read. In our docs, our
titles and H1 are surrounded by =, H2 underlined by ~, H3 underlined by -, H4
underlined by ^, H5 underlined by \*, and H6 underlined by " example:

.. code::

    =================
    Title or Header 1
    =================

    Header 2
    ~~~~~~~~

    Header 3
    --------

    Header 4
    ^^^^^^^^

    Header 5
    ********

    Header 6
    """"""""

which looks like

=================
Title or Header 1
=================

Header 2
~~~~~~~~

Header 3
--------

Header 4
^^^^^^^^

Header 5
********

Header 6
""""""""

Tables
~~~~~~

RST allows for several different ways of creating tables, the easiest way is
the following although it is not extremely flexible.

.. code::

    ======== ========
    Column 1 Column 2
    ======== ========
     Data 1   Data 2
     Data 3   Data 4
    ======== ========

which looks like:

======== ========
Column 1 Column 2
======== ========
 Data 1   Data 2
 Data 3   Data 4
======== ========

The second way is harder to manage, but more flexible

.. code::

    +----------+----------+----------+
    | Column 1 | Column 2 | Column 3 |
    +==========+==========+==========+
    | Data 1   | Data 2   | Data 3   |
    +----------+----------+----------+
    | Data 4   |       Data 5        |
    +----------+---------------------+


Which ends up looking like

+----------+----------+----------+
| Column 1 | Column 2 | Column 3 |
+==========+==========+==========+
| Data 1   | Data 2   | Data 3   |
+----------+----------+----------+
| Data 4   |       Data 5        |
+----------+---------------------+

The final way is easiest to manage but hardest to visualize before built to
html.

.. code::

    .. csv-table:: Table Title
       :header: "Column 1", "Column 2"
       :widths: 20, 40

       "Data 1", "Data 2"
       "Data 3", "Data 4"

Which looks like:

.. csv-table:: Table Title
   :header: "Column 1", "Column 2"
   :widths: 20, 40

   "Data 1", "Data 2"
   "Data 3", "Data 4"

Code Blocks
~~~~~~~~~~~

It is common to need to include code in tutorials. Our docs are built with
sphinx, which allows you to include code by using the following:

.. code::

    .. code::

        code goes here

Which looks like:

.. code::

    code goes here

Lists
~~~~~

Ordered lists should be done like the following:

.. code::

    #. Item 1

        #. Item 1a

    #. Item 2

        #. Item 2a

    #. Item 3

        #. Item 3a

and unordered lists should be done with "*", such as:

.. code::

    * List Item

    * List Item

    * List Item

Images
~~~~~~

Images are useful, but not required in our documentation. If you want to have
an image in an article, put the image in the ./images directory relative to the
article and reference it from there, using the following:

.. code::

    .. figure:: images/image.png

Bold and Italicized Text
~~~~~~~~~~~~~~~~~~~~~~~~

Bold and italicized text are allowed in our documentation to emphasize key
words or points, they can be done by surrounding a word with * or **.

Using domain names in documentation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

When using an example domain name in an article, use "example.com".

Links
~~~~~

In most cases you will use links that look like:

.. code::

    `text to be clickable <https://example.com>`__

note that there are two underscores, that tells the RST
compiler to throw away the reference when it is done, so you can later have the
same text be a link to a different target. If you have one underscore it will
create a link and save the text as a reference, so the next time you use it you
dont have to add the target, just the text, like:

.. code::

    `text to be clickable`_

http://docutils.sourceforge.net/docs/user/rst/quickref.html#hyperlink-targets
for more info on links.

Standard phrasing for introducing paragraphs
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

When introducing a new paragraph about installing or configuring something,
phrase it like "The following describes how to configure/install X...", if you
have bulleted points describing how to install or configure something, phrase
it as "Configure/Install X...".
