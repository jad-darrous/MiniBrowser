# MiniBrowser
A simple parser and renderer for HTML and Javascript.


The project is done as a mini project for the compiler course during my bachelor.

# Intro
This project is a simple parser and viewer for HTML and Javascript. It is written in Java using the **JavaCC** library for parsing.


# Features

For HTML, the following tags are supported:
```
<a>
<b> <u> <i>
<font>
<br />
<p>
<h1> .. <h6>
<ul> <ol> <li>
<table> <tr> <td>
<img>
<input>
<select>
<script>
<title>
```

The HTML part is actually XHTML which mean a more restrictive form of HTML; like all opened tags should be closed and tags are case sensitive. More examples about the difference between HTML and XHTML can be found here https://en.wikipedia.org/wiki/XHTML#Common_errors

For JavaScript part, the following concepts are supported:
* Function (definition and call)
* Loops (for, while, do while, foreach)
* Variables (assignment – definition – usage)
* Conditions (if , switch)
* DOM access (to change input tag parameters only)
* Document.write – alert
* Document.getElementById

Only inlined JS script are supported.


# Run

First, download the JavaCC library, extract the files and update the PATH variable

```
wget https://java.net/projects/javacc/downloads/download/javacc-5.0.tar.gz
tar -xf javacc-5.0.tar.gz
export PATH="$HOME/javacc-5.0/bin/:$PATH"
```

Create a `src` folder to put the generated `.java` files, and compile the `.jj` file.
```
mkdir src
(cd src && exec javacc ../xhtml_js.jj)
```

Create the `classes` folder to put the generate binary files, and compile the java source code.
```
mkdir classes
javac -d classes src/*.java
```

Now run the mini browser with the desired web page.
```
java -cp classes MiniBrowser < data/full.html
```

There are 3 test web pages:
* full.html: has almost all the Features
* errors.html: has almost all types of errors that can be handled.
* headers.html: a simple example.


Feel free to edit and run the examples :)
