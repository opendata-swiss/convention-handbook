.. container:: custom-breadcrumbs

   - :fa:`home` :doc:`Conventionen-Handbook <../../index>` :fa:`chevron-right`
   - :doc:`Conventions <../conventions>` :fa:`chevron-right`
   - Publisher

******************************
Publisher
******************************

.. admonition:: dct:publisher and dct:contact point in DCAT-AP
   :class: dcatap

   The :term:`DCAT-AP` expects for ``dct:publisher``:

   - ``dct:publisher`` as a mandatory property of ``dcat:Catalog``
   - ``dct:publisher`` is supposed to be a class of type ``foaf:Agent``
   - This class can be overwritten on each ``dcat:Dataset``
   - The class ``foaf:Agent` is supposed to have a URI and a name.
   - The publisher in DCAT-AP is the organisation that makes the decsion to publish the data.
   - There should be only one publisher per dataset or catalog

   More on the difference between publisher and contact point
   see here: `How are publisher and contact point modelled?  <https://joinup.ec.europa.eu/release/how-are-publisher-and-contact-point-modelled>`__

.. admonition:: dct:publisher and dct:contact point in DCAT-AP-CH
   :class: dcatapch

    - The DCAT-AP-CH is mostly conformant with DCAT-AP except for the fact that the ``foaf:Agent`` should be
      implemented as a mandatory class and that there should be exactly one publisher per ``dcat:Catalog`` and
      at most one ``dcat:Dataset``
    - The implementaion of ``dct:publisher`` is not conformat to the :term:`DCAT-AP-CH`
    - ``dcat:contactPoint`` is conformant with the DCAT-AP-CH and its implementaion on opendata.swiss is also
      conformant


Overview
-------------------------------------------

- :ref:`Publisher for DCAT-Catalogs <publisher-dcat>`
- :ref:`Publisher for Geocat Catalogs <publisher-geocat>`

.. _publisher-dcat:

Publisher for DCAT-Catalogs
-----------------------------------

.. admonition:: :dcat:term:`Convention dct:publisher NEW`
   :class: convention

   The convention demands the dct:publisher exactly as in the DCAT-AP above:

.. container:: attribute

    **dct:publisher** 1..1

    :Type: ``foaf:Organization``
    :Parent: ``dcat:Catalog``
    :Mandatory: yes
    :Cardinality: 1..1
    :Description: The publishers of the catalog.
    :Attributes: - name: ``foaf:name`` mandatory
                 - uri: ``rdf:about`` mandatory

    **dct:publisher** 0..1

    :Type: ``foaf:Organization``
    :Parent: ``dcat:Dataset``
    :Mandatory: no
    :Cardinality: 0..1
    :Description: The publishers of the dataset.
    :Attributes: - name: ``foaf:name`` mandatory
                 - uri: ``rdf:about`` mandatory


    .. code-block:: xml
       :caption: dct:publisher
       :emphasize-lines: 2,3,4

         <dct:publisher>
            <foaf:Organization rdf:about="https://uri-to-the-publisher">
               <foaf:name>Bundesamt für Landestopografie swisstopo</foaf:name>
            </foaf:Organization>
         </dct:publisher>

See here for a :doc:`complete example in rdf/xml and turtle publisher <../../examples/publisher>`.

.. admonition:: :dcat:term:`Convention dct:publisher DEPRECIATED`
   :class: convention

   - in the current implementation on opendata.swiss
   - the ``dct:publisher`` is defined as ``rdf:Description``
   - it comes with two properties: ``rdfs:label`` (Name of the publisher) und an optional property
     ``rdf:about`` (the URI of the organisation)
   - it is defined on ``dcat:Dataset``
   - there can be more then one publisher per dataset

.. container:: attribute

    **dct:publisher** 1..n

    :Elements: ``rdf:Description``
    :Parent: ``dcat:Dataset``
    :Type: Nested element
    :Mandatory: yes
    :Cardinality: 1..n
    :Description: The publishers of the dataset.
                  ``rdf:about`` is an optional attribute.

    .. code-block:: xml
       :caption: dct:publisher
       :emphasize-lines: 2,3,4

       <dct:publisher rdf="publisher-uri">
           <foaf:Description rdf:about="https://www.bafu.admin.ch/">
               <rdfs:label>Bundesamt für Landestopografie swisstopo</rdfs:label>
           </rdf:Description>
       </dct:publisher>

.. _publisher-geocat:

Publisher for Geocat-Catalogs
-----------------------------------

.. admonition:: :neu:term:`Convention Publisher for Geocat NEW`
   :class: convention

   The mapping has to be defined. The URI for the publisher is missing in the current mapping
   but needed for the DCAT-AP a conformant publisher class.

.. admonition:: :geo:term:`Konvention Publisher Geodaten DEPRECIATED`
   :class: convention

   Currently the publisher is mapped as described below: Only one publisher is taken and only the
   non localized name of the publisher is taken. There is a certain order in which roles are
   considered and taken as a publisher.

.. container:: attribute

    **dct:publisher**

    :Display name on opendata.swiss: Publishers
    :ISO-19139_che XPath:

    .. code-block:: xml
        :caption: The first one is taken in the following order:

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
