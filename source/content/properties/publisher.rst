.. container:: custom-breadcrumbs

   - :fa:`home` :doc:`Conventionen-Handbook <../../index>` :fa:`chevron-right`
   - :doc:`Properties <properties>` :fa:`chevron-right`
   - dct:publisher

******************************
dct:publisher
******************************

.. _catalog-publisher:

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

   not implemented

.. admonition:: geocat
   :class: geocat

   not implemented

.. _dataset-publisher:

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

   :Cardinality: 1:1
   :compliance: mandatory

.. admonition:: opendata.swiss
   :class: ogdch

   implementation does not conform
   - uses ``rdfs:label`` instead of ``foaf:name``
   - does not use a class ``foaf:Agent``

    .. code-block:: xml
       :caption: dct:publisher
       :emphasize-lines: 2,3,4

       <dct:publisher rdf="publisher-uri">
           <foaf:Description rdf:about="https://www.bafu.admin.ch/">
               <rdfs:label>Bundesamt für Landestopografie swisstopo</rdfs:label>
           </rdf:Description>
       </dct:publisher>

.. admonition:: geocat
   :class: geocat

    .. code-block:: xml
        :caption: XPATH for dct:publisher: the first one is taken in the following order:

        //gmd:identificationInfo//gmd:pointOfContact[.//gmd:CI_RoleCode/@codeListValue = "publisher"]//gmd:organisationName/gco:CharacterString
        //gmd:identificationInfo//gmd:pointOfContact[.//gmd:CI_RoleCode/@codeListValue = "owner"]//gmd:organisationName/gco:CharacterString
        //gmd:identificationInfo//gmd:pointOfContact[.//gmd:CI_RoleCode/@codeListValue = "pointOfContact"]//gmd:organisationName/gco:CharacterString
        //gmd:identificationInfo//gmd:pointOfContact[.//gmd:CI_RoleCode/@codeListValue = "distributor"]//gmd:organisationName/gco:CharacterString
        //gmd:identificationInfo//gmd:pointOfContact[.//gmd:CI_RoleCode/@codeListValue = "custodian"]//gmd:organisationName/gco:CharacterString
        //gmd:contact//che:CHE_CI_ResponsibleParty//gmd:organisationName/gco:CharacterString

    .. code-block:: xml
       :caption: Example of getting dct:publisher: codeListValue="pointOfContact" is detected
       :emphasize-lines: 1,2,3,4,5,8,9

       <gmd:identificationInfo>
          <gmd:pointOfContact>
             <gmd:CI_ResponsibleParty>
                <gmd:organisationName xsi:type="gmd:PT_FreeText_PropertyType">
                   <gco:CharacterString>Bundesamt für Strassen</gco:CharacterString>
                </gmd:organisationName>
                <gmd:role>
                   <gmd:CI_RoleCode codeList="http://www.isotc211.org/2005/resources/codeList.xml#CI_RoleCode"
                                    codeListValue="pointOfContact"/>
                </gmd:role>
             </gmd:CI_ResponsibleParty>
          </gmd:pointOfContact>
       </gmd:identificationInfo>
