ontolex2tei
===========

A Python script for converting OntoLex RDF (Turtle serialization) into TEI Lex-0 XML,
with input constraints and/or assumptions roughly as defined by [ELEXIS D2.1 § 3].

[ELEXIS D2.1 § 3]: https://elex.is/wp-content/uploads/2019/02/ELEXIS_D2_1_Interface_for_Interoperable_Resources.pdf 

Installation
------------
```
pip install lxml rdflib
```

Usage
-----
```
python ontolex2tei.py example.ttl
```
Example output:
```
<?xml version="1.0" encoding="UTF-8"?>
<?xml-model href="http://www.tei-c.org/release/xml/tei/custom/schema/relaxng/tei_all.rng"
            schematypens="http://relaxng.org/ns/structure/1.0" type="application/xml"?>
<!-- Should validate with `xmllint -relaxng $model-href $file` -->
<TEI xmlns="http://www.tei-c.org/ns/1.0">
    <teiHeader>
        <fileDesc>
            <titleStmt>
                <title>Ontolex Turtle Example Dictionary</title>
                <author></author>
            </titleStmt>
            <publicationStmt>
                <availability>
                    <licence target="http://www.example.com/license">http://www.example.com/license</license>
                </availability>
                <publisher>Example Publisher</publisher>
            </publicationStmt>
        </fileDesc>
    </teiHeader>
    <text>
        <body>

<entry xml:id="cat-n">
<form type="lemma"><orth xml:lang="en">cat</orth><orth xml:lang="sl">mačka</orth></form>
<gramGrp><pos norm="NOUN">NOUN</pos></gramGrp>
<sense n="1" xml:id="cat-n-1"><def xml:lang="en">a type of animal</def><def xml:lang="sl">vrsta živali</def></sense>
<sense n="2" xml:id="cat-n-2"><def xml:lang="en">an attractive woman</def><def xml:lang="sl">privlačna ženska</def></sense>
</entry>

<entry xml:id="cat-v">
<form type="lemma"><orth xml:lang="en">cat</orth></form>
<gramGrp><pos norm="VERB">VERB</pos></gramGrp>
<sense n="1" xml:id="cat-v-1"><def xml:lang="en">print contents of a computer file</def></sense>
<sense n="2" xml:id="cat-v-2"><def xml:lang="en">raise (an anchor) from the surface of the water to the cathead</def></sense>
</entry>

        </body>
    </text>
</TEI>

```
