Home
===============================
.. toctree::
   :hidden:

   quickstart
   hardware/index
   ros_configuration/index
   algorithms/index
   faqs
   license

Heavy WIP
^^^^^^^^^
* This is a bulleted list.
* It has two items, the second
  item uses two lines.

1. This is a numbered list.
2. It has two items too.

#. This is a numbered list.
#. It has two items too.

This is an ordinary paragraph.

>>> print 'this is a Doctest block'
this is a Doctest block

The following is a literal block::

    >>> This is not recognized as a doctest block by
    reStructuredText.  It *will* be recognized by the doctest
    module, though!


+------------------------+------------+----------+----------+
| Header row, column 1   | Header 2   | Header 3 | Header 4 |
| (header rows optional) |            |          |          |
+========================+============+==========+==========+
| body row 1, column 1   | column 2   | column 3 | column 4 |
+------------------------+------------+----------+----------+
| body row 2             | Cells may span columns.          |
+------------------------+------------+---------------------+
| body row 3             | Cells may  | - Table cells       |
+------------------------+ span rows. | - contain           |
| body row 4             |            | - body elements.    |
+------------------------+------------+---------------------+

=====  =====  =======
  A      B    A and B
=====  =====  =======
False  False  False
True   False  False
False  True   False
True   True   True
=====  =====  =======

See the Python_ home page for info.

`Write to me`_ with your questions.

.. _Python: http://www.python.org
.. _Write to me: jdoe@example.com

One more |example| here.

.. |example| image:: _images/example.png



Literal blocks are either indented or line-prefix-quoted blocks,
and indicated with a double-colon ("::") at the end of the
preceding paragraph (right here -->)::

    if literal_block:
        text = 'is left as-is'
        spaces_and_linebreaks = 'are preserved'
        markup_processing = None



Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
