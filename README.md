# Docx Search & Replace Java Project (SimpleDocxReplaceTool)

This project builds on the java gradle project template provided by **BRYTER.io**

## Description of this Library

This simple library was written with the help of Apache POI and uses its XWPFDocument class to create an abstraction for reading, searching and replacing strings, and writing back the modifications to a **DOCX** file.

## Instructions of Use

Unzip the file SimpleDocxReplaceTool.zip, open the contained gradle project on an IDE, gradle's wrapper should automatically install the dependencies. Modified project files:

* `README.md` : This readme file with the SimpleDocxReplaceTool overview and documentation
* `SimpleDocxReplaceTool.java` : the java code for the library, with comments and documentation
* `LibraryTest.java` : execute this test to evaluate the library. Please set the static parameters in this test file appropriately before executing.

Please refer to documentation of the library methods below (same as in the source code). All the described library methods are tested in the testcase `LibraryTest.java`. Only basic error handling is built in.

## SimpleDocxReplaceTool Documentation 

#### `public int isDocxLoaded()`

Tests if a Docx is loaded in the tool

 * **Returns:** will return 0 in case a Docx was loaded

     successfully before with openDocx!

#### `public int closeDocx()`

Closes the Docx releasing resources and allows for subsequent opening of other Docx documents with the openDocx method!

 * **Returns:** -1 is returned in case of error, 0 otherwise

#### `public int openDocx(String filename)`

The method openDocx opens the specified .docx file and loads it in an internal XWPFDocument representation.

 * **Parameters:** `filename` — specification of filename and path
 * **Returns:** -1 is returned in case of error, 0 otherwise

#### `public int writeDocx(String filename)`

This method writes the current state of the internal document representation to the specified file.

 * **Parameters:** `filename` — specification of filename and path
 * **Returns:** -1 is returned in case of error, 0 otherwise

#### `public int analyseDocx(PrintStream output)`

This method outputs some Document details to a specified PrintStream.

 * **Parameters:** `output` — specifies the PrintStream for outputting the file details
 * **Returns:** -1 is returned in case of error, 0 otherwise

#### `public int textFind(String findtext)`

This is just a simple finder, to test if a string occurs inside the loaded document. If the string is found inside the document, an integer greater than 0 is returned (representing the number of text runs in the XWPFDocument where the string occurs)

 * **Parameters:** `findtext` — specifies the string to be found
 * **Returns:** -1 is returned in case of error, 0 if nothing is found,

     1 or higher if the string is found

#### `public int textReplaceAll(String findtext, String replacetext)`

Will replace all occurrences of 'findtext' with 'replacetext' inside the internally loaded XWPFDocument

 * **Parameters:**
   * `findtext` — specifies the string to be found
   * `replacetext` — specifies the replacing string
 * **Returns:** -1 is returned in case of error, 0 if nothing is replaced,

     1 or higher if the string is found and replaced (num. of text runs)

