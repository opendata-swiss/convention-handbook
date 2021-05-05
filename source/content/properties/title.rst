.. container:: custom-breadcrumbs

   - :fa:`home` :doc:`Conventionen-Handbook <../../index>` :fa:`chevron-right`
   - :doc:`Properties <properties>` :fa:`chevron-right`
   - dct:title

******************************
dct:title
******************************
.. _catalog-title:

dcat:Catalog dct:title
============================================================

.. admonition:: DCAT-AP
   :class: dcatap

   :property: title
   :URI: dct:title
   :Range: rdfs:Literal
   :Cardinality: 1:n
   :compliance: mandatory
   :Usage note: This property contains a name given to the Catalogue.
                It can be repeated in multiple languages.

.. admonition:: DCAT-AP-CH
   :class: dcatapch

   :Usage note: Title is expected in at least one of the languages: de, fr, it, en

.. admonition:: opendata.swiss
   :class: ogdch

   not implemented

.. admonition:: geocat
   :class: geocat

   not implemented

.. _dataset-title:

dcat:Dataset dct:title
============================================================

.. admonition:: DCAT-AP
   :class: dcatap

   :property: title
   :URI: dct:title
   :Range: rdfs:Literal
   :Cardinality: 1:n
   :compliance: mandatory
   :Usage note: This property contains a name given to the Dataset.
                It can be repeated in multiple languages.

.. admonition:: DCAT-AP-CH
   :class: dcatapch

   :Usage note: Title is expected in at least one of the languages: de, fr, it, en

.. admonition:: opendata.swiss
   :class: ogdch

   .. code-block:: xml
      :caption: dct:title in rdf/xml for dcat:Dataset
      :emphasize-lines: 1

      <dct:title xml:lang="de">Eisenbahnlärm Nacht</dct:title>

.. admonition:: geocat
   :class: geocat

   .. code-block:: xml
      :caption: XPATH for dct:title on dcat:Dataset

      //gmd:identificationInfo//gmd:citation//gmd:title//gmd:textGroup/gmd:LocalisedCharacterString

   .. code-block:: xml
      :caption: Example of getting dct:title: only 4 languages are taken: DE, EN, FR, IT
      :emphasize-lines: 6, 11, 16, 21

      <gmd:title xsi:type="gmd:PT_FreeText_PropertyType">
        <gco:CharacterString>Lärmbelastung durch Eisenbahnverkehr (Lr_Nacht)</gco:CharacterString>
          <gmd:PT_FreeText>
            <gmd:textGroup>
              <gmd:LocalisedCharacterString locale="#FR">
                Exposition au bruit du trafic ferroviaire (Lr_nuit)
              </gmd:LocalisedCharacterString>
            </gmd:textGroup>
            <gmd:textGroup>
              <gmd:LocalisedCharacterString locale="#DE">
                Lärmbelastung durch Eisenbahnverkehr (Lr_Nacht)
              </gmd:LocalisedCharacterString>
            </gmd:textGroup>
            <gmd:textGroup>
              <gmd:LocalisedCharacterString locale="#EN">
                Nighttime railway noise exposure
              </gmd:LocalisedCharacterString>
            </gmd:textGroup>
            <gmd:textGroup>
              <gmd:LocalisedCharacterString locale="#IT">
                Esposizione al rumore del traffico ferroviario (Lr_notte)
              </gmd:LocalisedCharacterString>
            </gmd:textGroup>
            <gmd:textGroup>
              <gmd:LocalisedCharacterString locale="#RM">
                Grevezza da canera tras il traffic da viafier durant la notg
              </gmd:LocalisedCharacterString>
            </gmd:textGroup>
          </gmd:PT_FreeText>
        </gmd:title>

.. _distribution-title:

dcat:Distribution dct:title
============================================================

.. admonition:: DCAT-AP
   :class: dcatap

   :property: title
   :URI: dct:title
   :Range: rdfs:Literal
   :Cardinality: 1:n
   :compliance: optional
   :Usage note: This property contains a name given to the Distribution.
                It can be repeated in multiple languages.

.. admonition:: DCAT-AP-CH
   :class: dcatapch

   conforms

.. admonition:: opendata.swiss
   :class: ogdch

   .. code-block:: xml
      :caption: dct:title for dcat:Dataset
      :emphasize-lines: 1

      <dct:title xml:lang="de">Eisenbahnlärm Nacht</dct:title>

.. admonition:: geocat
   :class: geocat

   depends on the protocol: ``//gmd:transferOptions//gmd:CI_OnlineResource//gmd:protocol/gco:CharacterString``

   .. code-block:: xml
      :caption: XPATH for dct:title for geoservices

      .//srv:operationName/gco:CharacterString

   .. code-block:: xml
      :caption: XPATH for dct:title for other protocols

      .//gmd:distributionInfo//gmd:transferOptions/gmd:name
