.. container:: custom-breadcrumbs

   - :fa:`home` :doc:`Conventionen-Handbook <../../index>` :fa:`chevron-right`
   - :doc:`Conventions <../conventions>` :fa:`chevron-right`
   - Contact Points

******************************
Contact Points
******************************

.. admonition:: dct:publisher and dct:contact point in DCAT-AP
   :class: dcatap

   The :term:`DCAT-AP` recommends ``dcat:contactPoint``:

   - as a contact person to define for each dataset
   - ``dcat:contactPoint`` is supposed to be of ``vcard:kind``
   - It does not have to be a person in the same organization as the dct:publisher.

.. admonition:: dct:publisher and dct:contact point in DCAT-AP-CH
   :class: dcatapch

    - ``dcat:contactPoint`` is conformant with the DCAT-AP-CH and its implementaion on opendata.swiss is also
      conformant


Overview
-------------------------------------------

- :ref:`Contact Point for DCAT-Catalogs <contact-points-dcat>`
- :ref:`Contact Point for Geocat Catalogs <contact-points-geocat>`

.. _publisher-dcat:

Contact Points for DCAT-Catalogs
-----------------------------------------------

.. admonition:: :konventionen:term:`Konvention Kontakstellen DCAT`
   :class: convention

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

.. _contact-points-geocat:

Contact Points for Geocat Catalogs
-----------------------------------------------

.. admonition:: :dcat:term:`Konvention Kontaktstellen Geodaten`
   :class: convention

   Bei geodaten wird der Publisher wie unten beschrieben gesucht:

.. container:: attribute

    **dcat:contactPoint**

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


