=================
Executive Summary
=================

RoboFab is the result of over 6 man-years of concentrated coding. The package combines a solid Pythonic API with over 40 standardized classes of objects for font and glyph related data. With RoboFab installed, the scripter will find it easier to produce scripts, API standardization means fewer things to remember or look up -- eventhough RoboFab comes with extensive documentation and example code.

The Font/Glyph/Contour/Point model can be tailored to the needs of the scripter, manipulating data from glyph to glyph or font to font and addressing the outline data point by point, as offcurve/oncurve segments or as conventional knots with incoming / oncurve / outgoing attributes. RoboFab's Kerning object delivers the kerning data as a standard Python dictionary object. The Lib objects will soon take advantage of FontLab's new PythonDict field for storing Python data inside FontLab .vfb sources.

RoboFab's pen objects (an implementation of fontTools' pen classes) provide a powerful method to interface with glyph data, either for actual drawing (for instance on screen, or some sort of vector based file format), complex comparisons, transformations and filtering.

RoboFab offers a large selection of standardised UI dialogs, ranging from plain messaging to very powerful font and glyph retrieval functionality.

RoboFab also brings extensive support for import and export of glyph and font data to UFO, an open industry standard based on XML. UFO makes it possible to, for instance, store text versions of glyphs and fonts in large SQL databases and apply standard text source management tools (such as cvs, diff) to glyphsets.
