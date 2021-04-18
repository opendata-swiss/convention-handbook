.. container:: custom-breadcrumbs

   - :fa:`home` :doc:`Konventionen-Handbuch <../../index>` :fa:`chevron-right`
   - :doc:`Konventionen <../konventionen>` :fa:`chevron-right`
   - Publisher

*************************
Publisher
*************************

Wie gebe ich Kontaktstellen für meine Daten an?
==========================================================

.. container:: Intro

   Der :term:`DCAT-AP` versteht unter dem ``dct:publisher`` den Herausgeber des Datenkatalog und
   erwartet eine Klasse vom Typ ``foaf:Agent``.
   Der Publisher ist die Organisation, die
   die Entscheidung darüber fällt, die Daten zu veröffentlichen und dazu auch rechtlich befugt ist.

.. admonition:: Unterscheidung Publisher Kontaktstelle
   :class: general

   Die Unterscheidung zwischen Publisher und Kontaktstellen kommt von DCAT-AP: der Publisher ist eine
   Organisation, während es sich bei den Kontaktstellen um Person, eben Ansprechpartner handelt.

Überblick
-------------------------------------------

- :ref:`Kontakstellen bei DCAT-Datenkatalogen <publisher-dcat>`
- :ref:`Kontaktstellen bei Geodaten Datenkatalogen <publisher-geodaten>`

.. _kontaktstellen-dcat:

Kontaktstellen bei DCAT-Datenkatalogen
-----------------------------------------------

.. admonition:: :konventionen:term:`Konvention-Publisher-DCAT-neu`
   :class: konvention

   Der ``dct:publisher`` wird als ``foaf:Organization`` definiert. Er hat die Pflichtattribute
   ``foaf:name`` (Name der herausgebenden Organisation) und ``rdf:about`` (URI der Organisation)
   Es geht dabei um die Organisation, die die Entscheidung zur Veröffentlichung des Datenkatalog
   getroffen hat. Das sollte genau eine Organisation sein. Für andere Rollen stehen andere
   Attribute zur Verfügung, etwa die :doc:`Kontaktstellen <kontaktstellen>`.
   Der Publisher wird auf Ebene des
   Datenkatalogs oder des Datasets definiert. Der Publisher im Datenkatalog ist ein Pflichtattribut.
   Optional kann der Publisher auf der Ebene des Datasets überschrieben werden.

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

         <dct:publisher>
            <foaf:Organization rdf:about="https://uri-to-the-publisher">
               <foaf:name>Bundesamt für Landestopografie swisstopo</foaf:name>
            </foaf:Organization>
         </dct:publisher>

.. code-block:: xml
   :caption: Publisher im Datenkatalog

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
         <dct:publisher>
            <foaf:Organization rdf:about="https://www.swisstopo.admin.ch/some-suborganisation">
               <foaf:name>Some suborganization</foaf:name>
            </foaf:Organization>
         </dct:publisher>
         <dcat:dataset>
            <dcat:Dataset rdf:about="https://uri-to-the-dataset-1">
               <dct:publisher rdf:resource="https://www.swisstopo.admin.ch/some-suborganisation"></dct:publisher>
            </dcat:Dataset>
         </dcat:dataset>
      </dcat:Catalog>
   </rdf:RDF>

.. code-block:: turtle
   :caption: Publisher im Datenkatalog in Turtle

    @prefix dcat: <http://www.w3.org/ns/dcat#> .
    @prefix dc: <http://purl.org/dc/terms/> .
    @prefix foaf: <http://xmlns.com/foaf/0.1/> .

    <https://uri-to-the-catalog>
      a dcat:Catalog ;
      dc:publisher <https://www.swisstopo.admin.ch>, <https://www.swisstopo.admin.ch/some-suborganisation> ;
      dcat:dataset <https://uri-to-the-dataset-1> .

    <https://www.swisstopo.admin.ch>
      a foaf:Organization ;
      foaf:name "Bundesamt für Landestopografie swisstopo" .

    <https://www.swisstopo.admin.ch/some-suborganisation>
      a foaf:Organization ;
      foaf:name "Some suborganization" .

    <https://uri-to-the-dataset-1>
      a dcat:Dataset ;
      dc:publisher <https://www.swisstopo.admin.ch/some-suborganisation> .

.. admonition:: :konventionen:term:`Konvention Publisher DCAT`
   :class: konvention

   Der ``dct:publisher`` wird als ``rdf:Description`` definiert. Er hat die Pflichtattribute
   ``rdfs:label`` (Name der herausgebenden Organisation) und ein optionales Attribut
   ``rdf:about`` (URI der Organisation). Es kann ein oder mehrere Publisher pro Dataset geben.
   Publishers werden auf Dataset-Ebene angegeben.

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

       <dct:publisher rdf="publisher-uri">
           <foaf:Description rdf:about="https://www.bafu.admin.ch/">
               <rdfs:label>Bundesamt für Landestopografie swisstopo</rdfs:label>
           </rdf:Description>
       </dct:publisher>

.. _kontaktstellen-geodaten:

Kontaktstellen bei  Geodaten Datenkatalogen
-----------------------------------------------

.. admonition:: :konventionen:term:`Konvention-Publisher-Geodaten-neu`
   :class: konvention

   Bei geodaten wird der Publisher wie unten beschrieben gesucht:

.. container:: attribute

    **dct:publisher**

    :Display name on opendata.swiss: Publishers
    :ISO-19139_che XPath:

    .. code-block:: xml
        :caption: Es wird erwartet, dass gmd:LocalisedCharacterString oder ein gmd:LocalisedCharacterString gesetzt ist

        //gmd:contact//gmd:pointOfContact//gmd:CI_ResponsibleParty//gmd:organisationName/


    .. code-block:: xml
       :caption: Example of getting dct:publisher: codeListValue="pointOfContact" is detected,

       <gmd:contact xmlns:che="http://www.geocat.ch/2008/che" xmlns:gco="http://www.isotc211.org/2005/gco" xmlns:gmx="http://www.isotc211.org/2005/gmx" xmlns:gts="http://www.isotc211.org/2005/gts" xmlns:srv="http://www.isotc211.org/2005/srv" xmlns:gml="http://www.opengis.net/gml" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:geonet="http://www.fao.org/geonetwork">
          <gmd:CI_ResponsibleParty>
             <gmd:organisationName xsi:type="gmd:PT_FreeText_PropertyType">
                <gco:CharacterString>Amt für Landschaft und Natur - Fachstelle Bodenschutz</gco:CharacterString>
                   <gmd:PT_FreeText>
                      <gmd:textGroup>
                         <gmd:LocalisedCharacterString locale="#DE">Amt für Landschaft und Natur - Fachstelle Bodenschutz</gmd:LocalisedCharacterString>
                      </gmd:textGroup>
                   </gmd:PT_FreeText>
             </gmd:organisationName>
          </gmd:CI_ResponsibleParty>
       </gmd:contact>

.. admonition:: :konventionen:term:`Konvention-Publisher-Geodaten`
   :class: konvention

   Bei geodaten wird der Publisher wie unten beschrieben gesucht:

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
       :caption: Example of getting dct:publisher: codeListValue="pointOfContact" is detected,

        <gmd:pointOfContact xlink:show="embed">
           <che:CHE_CI_ResponsibleParty xmlns:geonet="http://www.fao.org/geonetwork" gco:isoType="gmd:CI_ResponsibleParty">
              <gmd:organisationName xsi:type="gmd:PT_FreeText_PropertyType">...</gmd:organisationName>
              <gmd:positionName xsi:type="gmd:PT_FreeText_PropertyType">...</gmd:positionName>
              <gmd:contactInfo>
                 <gmd:CI_Contact>
                    <gmd:phone>...</gmd:phone>
                    <gmd:address>...</gmd:address>
                    <gmd:onlineResource>...</gmd:onlineResource>
                 </gmd:CI_Contact>
              </gmd:contactInfo>
              <gmd:role>
                 <gmd:CI_RoleCode codeList="http://www.isotc211.org/2005/resources/codeList.xml#CI_RoleCode" codeListValue="pointOfContact"/>
              </gmd:role>
              <che:individualLastName>...</che:individualLastName>
              <che:organisationAcronym xsi:type="gmd:PT_FreeText_PropertyType">...</che:organisationAcronym>
           </che:CHE_CI_ResponsibleParty>
        </gmd:pointOfContact>

.. container:: materialien

   Mehr zum Thema

- `Zur Unterscheidung zwischen Publishern und Kontaktstellen im DCAT-AP <https://joinup.ec.europa.eu/release/how-are-publisher-and-contact-point-modelled>`__ –
   Artikel zur Unterscheidung zwischen ``dct:publisher``und ``dct:ContactPoint``


