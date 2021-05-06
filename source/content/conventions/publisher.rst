.. container:: custom-breadcrumbs

   - :fa:`home` :doc:`Conventionen-Handbook <../../index>` :fa:`chevron-right`
   - :doc:`Properties <properties>` :fa:`chevron-right`
   - dct:publisher

******************************
dct:publisher
******************************

Convention #1 make dct:publisher DCAT-AP comformant:
========================================================

:Status: draft

:Goals: - make publisher mandatory on dcat:Catalog
        - dcat:Dataset may overwrite the publisher on dcat:Catalog
        - only one publisher per Catalog or dataset is allowed
        - the publisher is expected as a class of foaf:Agent
        - DCAT-AP-CH: define this class in the next DCAT-AP-CH
        - Implementation on opendata.swiss: get publisher form the catalog and take as a default
        - Geocat Mapping to be discussed

.. _catalog-publisher#1:

dcat:Catalog dct:publisher
============================================================

.. admonition:: DCAT-AP
   :class: dcatap

   :property: publisher
   :URI: dct:publisher
   :Range: foaf:Agent
   :Cardinality: 1:1
   :compliance: mandatory
   :Usage note: This property refers to an entity (organisation) responsible for making the Catalogue available.

.. admonition:: DCAT-AP-CH
   :class: dcatapch

   conforms

.. admonition:: opendata.swiss
   :class: ogdch

   .. code-block:: xml
      :caption: dct:publisher
      :emphasize-lines: 2,3,4

      <dct:publisher>
        <foaf:Description rdf:about="https://www.bafu.admin.ch/">
          <rdfs:label>Bundesamt für Landestopografie swisstopo</rdfs:label>
        </rdf:Description>
      </dct:publisher>

.. admonition:: geocat
   :class: geocat

   to be discussed with swisstopo

.. _dataset-publisher#1:

dcat:Dataset dct:publisher
============================================================

.. admonition:: DCAT-AP
   :class: dcatap

   :property: publisher
   :URI: dct:publisher
   :Range: foaf:Agent
   :Cardinality: 0:1
   :compliance: recommended
   :Usage note: This property refers to an entity (organisation) responsible for making the Dataset available.

.. admonition:: DCAT-AP-CH
   :class: dcatapch

   conforms

.. admonition:: opendata.swiss
   :class: ogdch

   publisher can also be defined for a dataset

.. code-block:: xml
   :caption: Example Catalog with publisher in rdf/xml
   :emphasize-lines: 10,11,12,16,22,23,24

   <?xml version="1.0" encoding="utf-8"?>
   <rdf:RDF
     xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
     xmlns:dcat="http://www.w3.org/ns/dcat#"
     xmlns:dct="http://purl.org/dc/terms/"
     xmlns:foaf="http://xmlns.com/foaf/0.1/"
   >
      <dcat:Catalog rdf:about="https://uri-to-the-catalog">
         <dct:publisher>
            <foaf:Organization rdf:about="https://www.swisstopo.admin.ch">
               <foaf:name>Bundesamt für Landestopografie swisstopo</foaf:name>
            </foaf:Organization>
         </dct:publisher>
         <dcat:dataset>
            <dcat:Dataset rdf:about="https://uri-to-the-dataset-1">
               <dct:publisher rdf:resource="https://www.swisstopo.admin.ch"></dct:publisher>
            </dcat:Dataset>
         </dcat:dataset>
         <dcat:dataset>
            <dcat:Dataset rdf:about="https://uri-to-the-dataset-2">
               <dct:publisher>
                  <foaf:Organization rdf:about="https://www.swisstopo.admin.ch/some-suborganisation">
                     <foaf:name>Some suborganization</foaf:name>
                  </foaf:Organization>
               </dct:publisher>
            </dcat:Dataset>
         </dcat:dataset>
      </dcat:Catalog>
   </rdf:RDF>

.. code-block:: turtle
   :caption: Example Catalog with publisher in Turtle
   :emphasize-lines: 7,10,16,20,22

    @prefix dcat: <http://www.w3.org/ns/dcat#> .
    @prefix dct: <http://purl.org/dc/terms/> .
    @prefix foaf: <http://xmlns.com/foaf/0.1/> .

    <https://uri-to-the-catalog>
      a dcat:Catalog ;
      dct:publisher <https://www.swisstopo.admin.ch> ;
      dcat:dataset <https://uri-to-the-dataset-1>, <https://uri-to-the-dataset-2> .

    <https://www.swisstopo.admin.ch>
      a foaf:Organization ;
      foaf:name "Bundesamt für Landestopografie swisstopo" .

    <https://uri-to-the-dataset-1>
      a dcat:Dataset ;
      dct:publisher <https://www.swisstopo.admin.ch> .

    <https://uri-to-the-dataset-2>
      a dcat:Dataset ;
      dct:publisher <https://www.swisstopo.admin.ch/some-suborganisation> .

    <https://www.swisstopo.admin.ch/some-suborganisation>
      a foaf:Organization ;
      foaf:name "Some suborganization" .

.. admonition:: geocat
   :class: geocat

   To be discussed with swisstopo
