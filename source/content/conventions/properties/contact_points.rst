.. container:: custom-breadcrumbs

   - :fa:`home` :doc:`Conventionen-Handbook <../../index>` :fa:`chevron-right`
   - :doc:`Conventions <../conventions>` :fa:`chevron-right`
   - Contact Points

*************************
Contact Points
*************************

How do I add contact points for my dataset?
==========================================================

.. admonition:: :dcatap:`DCAT-AP`
   :class: dcat-ap

   The :term:`DCAT-AP` versteht unter dem ``dcat:contactPoint`` eine Kontaktstelle
   für eine Dataset. Das Attribut ist im DCAT-AP empfohlen. Es ist pro Dataset
   defniert. Hinsichtlich der Anzahl der Kontaktstellen gibt es im DCAT-AP keine Einschränkung.
   Im DCAT-AP-CH ist das Feld ein Pflichtfeld, das ebenfalls auf der Ebene des Datasets erwartet wird.
   Es kann pro Dataset mehrere Kontakstellen geben.

.. container:: DCAT-AP-CH

   The :term:`DCAT-AP` versteht unter dem ``dcat:contactPoint`` eine Kontaktstelle
   für eine Dataset. Das Attribut ist im DCAT-AP empfohlen. Es ist pro Dataset
   defniert. Hinsichtlich der Anzahl der Kontaktstellen gibt es im DCAT-AP keine Einschränkung.
   Im DCAT-AP-CH ist das Feld ein Pflichtfeld, das ebenfalls auf der Ebene des Datasets erwartet wird.
   Es kann pro Dataset mehrere Kontakstellen geben.

.. admonition:: Beziehung zwischen Kontaktstelle und Publisher
   :class: general

   Die Unterscheidung zwischen Publisher und Kontaktstellen kommt von DCAT-AP: der Publisher ist eine
   Organisation, während es sich bei den Kontaktstellen um Person,
   eben einen Ansprechpartner für ein Datasets handelt handelt. Es ist nicht zwingend, dass Kontakstellen
   ``dcat:contactPoint`` bei der herausgebenden Organisation ``dct:publisher`` angesiedelt sind.

Überblick
-------------------------------------------

- :ref:`Kontakstellen bei DCAT-Datenkatalogen <kontaktstellen-dcat>`
- :ref:`Kontaktstellen bei Geodaten Datenkatalogen <kontaktstellen-geodaten>`

.. _kontaktstellen-dcat:

Kontaktstellen bei DCAT-Datenkatalogen
-----------------------------------------------

.. admonition:: :konventionen:term:`Konvention Kontakstellen DCAT`
   :class: konvention

   Der ``dct:publisher`` wird als ``rdf:Description`` definiert. Er hat die Pflichtattribute
   ``rdfs:label`` (Name der herausgebenden Organisation) und ein optionales Attribut
   ``rdf:about`` (URI der Organisation). Es kann ein oder mehrere Publisher pro Dataset geben.
   Publishers werden auf Dataset-Ebene angegeben.

.. container:: attribute

    **dcat:contactPoint** 1..n

    :Elements: ``vcard:Organization``
    :Parent: ``dcat:Dataset``
    :Type: ``vcard:Kind``
    :Mandatory: yes
    :Cardinality: 1..n
    :Description: One or more contact email addresses for this dataset
                  ``vcard:fn``. Description of the point of contact
                  ``vcard:hasEmail`` has an attribute ``rdf:resource`` which
                  contains the email of the point of contact (including mailto:)

    .. code-block:: xml
       :caption: dcat:contactPoint
       :emphasize-lines: 2,3,4,5,9,10,11,12

       <dcat:contactPoint>
           <vcard:Organization>
               <vcard:fn>Abteilung Lärm BAFU</vcard:fn>
               <vcard:hasEmail rdf:resource="mailto:noise@bafu.admin.ch"/>
           </vcard:Organization>
       </dcat:contactPoint>

       <dcat:contactPoint>
           <vcard:Individual>
               <vcard:fn>Sekretariat BAFU</vcard:fn>
               <vcard:hasEmail rdf:resource="mailto:sekretariat@bafu.admin.ch"/>
           </vcard:Individual>
       </dcat:contactPoint>

.. _kontaktstellen-geodaten:

Kontaktstellen bei Geodaten Datenkatalogen
-----------------------------------------------

.. admonition:: :dcat:term:`Konvention Kontaktstellen Geodaten`
   :class: konvention

   Bei geodaten wird der Publisher wie unten beschrieben gesucht:

.. container:: attribute

    **dcat:contactPoint**

    :Display name on opendata.swiss: Contact points
    :ISO-19139_che XPath:

    .. code-block:: xml
        :caption: The first one is taken in the following order:

        XPathValue('//gmd:identificationInfo//gmd:pointOfContact[.//gmd:CI_RoleCode/@codeListValue = "publisher"]//gmd:address//gmd:electronicMailAddress/gco:CharacterString/text()'),  # noqa
        XPathValue('//gmd:identificationInfo//gmd:pointOfContact[.//gmd:CI_RoleCode/@codeListValue = "owner"]//gmd:address//gmd:electronicMailAddress/gco:CharacterString/text()'),  # noqa
        XPathValue('//gmd:identificationInfo//gmd:pointOfContact[.//gmd:CI_RoleCode/@codeListValue = "pointOfContact"]//gmd:address//gmd:electronicMailAddress/gco:CharacterString/text()'),  # noqa
        XPathValue('//gmd:identificationInfo//gmd:pointOfContact[.//gmd:CI_RoleCode/@codeListValue = "distributor"]//gmd:address//gmd:electronicMailAddress/gco:CharacterString/text()'),  # noqa
        XPathValue('//gmd:identificationInfo//gmd:pointOfContact[.//gmd:CI_RoleCode/@codeListValue = "custodian"]//gmd:address//gmd:electronicMailAddress/gco:CharacterString/text()'),  # noqa
        XPathValue('//gmd:contact//che:CHE_CI_ResponsibleParty//gmd:address//gmd:electronicMailAddress/gco:CharacterString/text()'),  # noqa

    .. code-block:: xml
       :caption: Example of getting dcat:contactPoint: codeListValue="pointOfContact" was found
       :emphasize-lines: 1,2,6,8,9,10,16,17

       <gmd:identificationInfo>
           <gmd:pointOfContact>
              <gmd:CI_ResponsibleParty>
                 <gmd:contactInfo>
                    <gmd:CI_Contact>
                       <gmd:address>
                          <gmd:CI_Address>
                             <gmd:electronicMailAddress>
                                <gco:CharacterString>gerhard.schuwerk@astra.admin.ch</gco:CharacterString>
                             </gmd:electronicMailAddress>
                          </gmd:CI_Address>
                       </gmd:address>
                    </gmd:CI_Contact>
                 </gmd:contactInfo>
                 <gmd:role>
                    <gmd:CI_RoleCode codeList="http://www.isotc211.org/2005/resources/codeList.xml#CI_RoleCode"
                                     codeListValue="pointOfContact"/>
                 </gmd:role>
             </gmd:CI_ResponsibleParty>
          <gmd:pointOfContact>
       </gmd:identificationInfo>

.. container:: materialien

   Mehr zum Thema

- `Zur Unterscheidung zwischen Publishern und Kontaktstellen im DCAT-AP <https://joinup.ec.europa.eu/release/how-are-publisher-and-contact-point-modelled>`__ –
   Artikel zur Unterscheidung zwischen ``dct:publisher``und ``dct:ContactPoint``


