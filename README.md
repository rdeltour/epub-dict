This repository is used to develop schema(s) for the [EPUB DICT](http://www.idpf.org/epub/dict/) specification. It also includes schema tests.

## Schema(s)

This repository contain the following schemas:

 * `epub-dict-10.sch`: a [Schematron](http://schematron.com/)-based schema for EPUB XHTML Content Documents including dictionary content as defined in the [EPUB DICT](http://www.idpf.org/epub/dict/) specification.
 * `epub-glossary-10.sch`: a [Schematron](http://schematron.com/)-based schema for EPUB XHTML Content Documents including glossary content as defined in the [EPUB DICT](http://www.idpf.org/epub/dict/) specification.
 * `search-key-map-10.sch`: a [RelaxNG](http://relaxng.org/) schema (in compact syntax) for EPUB Search Key Map Documents as defined in the [EPUB DICT](http://www.idpf.org/epub/dict/) specification.

## How to run tests

```
mvn clean test
```

This will:

 * expand Schematron abstract patterns and generate the output schema in `target/schema/schema-expanded.xsl`
 * compile the expanded Schematron schema in `target/schema/schema-compiled.xsl`
 * convert the single test file to multiple test sources + [XSpec](https://code.google.com/p/xspec/) tests in `target/tests/`
 * run the generated tests

Tests are only available for Schematron schemas.

## How to write tests

Tests are defined in `src/tests/test-dict.xhtml` and `src/tests/test-glossary.xhtml`.
Create a child element of  the HTML `body` element with the following attributes:

 * `title` contains the label of the test (the description of the tested markup)
 * `class` must be one of `valid` or `invalid`
