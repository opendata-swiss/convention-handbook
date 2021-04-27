.. container:: custom-breadcrumbs

   - :fa:`home` :doc:`Conventionen-Handbook <../../index>` :fa:`chevron-right`
   - :doc:`Examples <../examples>` :fa:`chevron-right`
   - Example DCAT Publisher DCAT-AP conformant

**********************************************
Example DCAT Publisher DCAT-AP conformant
**********************************************

.. code-block:: xml
   :caption: Publisher im Datenkatalog
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
   :caption: Publisher im Datenkatalog in Turtle
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