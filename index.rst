.. Learning Read the Docs documentation master file, created by
   sphinx-quickstart on Fri Jun 22 11:04:56 2018.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to Learning Read the Docs's documentation!
==================================================
This tutorial is for learning basic sytanx Commands for read the docs.

*Italic content* with Single ``astric``.

**Bold content** with double ``astric``.

``decorated box`` with double ``back ticks``.

**List items** should be with ``astric``.

* Item1
* Item2
* Item3

**Numbered List** with ``hash`` followed by ``dot``

#. Item1
#. Item2
#. Item3

Adding Image example:

.. image:: /images/chrome_2018-06-22_10-42-31.png

Code that we wanted to add:

.. code-block:: csharp

    private static string GetMessageFromException(Exception ex)
    {
        if (ex ==null) return "";
        if (ex.InnerException != null)
        {
            return GetMessageFromException(ex.InnerException);
        }
            return ex.message; 
    }

If code is single language for the documentation we can add it on ``conf.py``
file under ``pygments`` section add below line.

highlight_language = csharp


Testing Continuous Integration

Testing using *Shiny* branch



.. toctree::
   :maxdepth: 2
   :hidden:
   :caption: Contents:

   Options/table
   Options/admonition
