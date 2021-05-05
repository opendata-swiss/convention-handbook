.. container:: custom-breadcrumbs

   - :fa:`home` :doc:`Conventionen-Handbook <../../index>` :fa:`chevron-right`
   - :doc:`Properties <properties>` :fa:`chevron-right`
   - dct:language

******************************
dct:language
******************************

.. _catalog-language:

dcat:Catalog dct:language
============================================================

.. admonition:: DCAT-AP
   :class: dcatap

   :property: language
   :URI: dct:language
   :Range: dct:LinguisticSystem
   :Cardinality: 0:n
   :compliance: recommended
   :Usage note: This property refers language used in the catalog, dataset or distributions.
                It can be repeated if multiple languages are used

.. admonition:: DCAT-AP-CH
   :class: dcatapch

   :Range: rdfs:Literal (ISO 639-1two-letter code)
   :compliance: optional

.. admonition:: opendata.swiss
   :class: ogdch

   catalog is not used

.. admonition:: geocat
   :class: geocat

   mapping is not implemented

.. _dataset-language:

dcat:Dataset dct:language
============================================================

.. admonition:: DCAT-AP
   :class: dcatap

   :property: language
   :URI: dct:language
   :Range: dct:LinguisticSystem
   :Cardinality: 0:n
   :compliance: optional
   :Usage note: This property refers to a language of the Dataset.
                This property can be repeated if there are multiple languages in the Dataset.

.. admonition:: DCAT-AP-CH
   :class: dcatapch

   :Range: rdfs:Literal (ISO 639-1two-letter code)
   :compliance: conditional
   :Usage note: This property can be left out if the distributions are language independent or
                occur in all the in DCAT_AP_CH supported languages

.. admonition:: opendata.swiss
   :class: ogdch

   .. code-block:: xml
      :caption: dct:language in rdf/xml: pick up all of these statements for dcat:Dataset and dcat:Distribution
      :emphasize-lines: 1

       <dct:language>de</dct:language>

.. admonition:: geocat
   :class: geocat

   .. code-block:: xml
      :caption: XPATH for dct:language on dcat:Dataset: pick up first of

      //gmd:identificationInfo//gmd:language/gmd:LanguageCode/gco:CharacterString
      //che:CHE_MD_Metadata/gmd:language/gco:CharacterString

   .. code-block:: xml
      :caption: Mapping of language codes for dcat:Datasets

      lang_mapping = {
        'ger': 'de',
        'fra': 'fr',
        'eng': 'en',
        'ita': 'it',
      }

   .. code-block:: xml
      :caption: Example of mapping the language code for dcat:Dataset
      :emphasize-lines: 2

      <gmd:language>
        <gmd:LanguageCode codeList="http://www.loc.gov/standards/iso639-2/" codeListValue="ger"/>
      </gmd:language>

.. _distribution-language:

dcat:Distribution dct:language
============================================================

.. admonition:: DCAT-AP
   :class: dcatap

   :property: language
   :URI: dct:language
   :Range: dct:LinguisticSystem
   :Cardinality: 0:n
   :compliance: optional
   :Usage note: This property refers to a language used in the the Distribution.
                This property can be repeated if the metadata is provides in multiple languages.

.. admonition:: DCAT-AP-CH
   :class: dcatapch

   :Range: rdfs:Literal (ISO 639-1two-letter code)
   :compliance: conditional

.. admonition:: opendata.swiss
   :class: ogdch

   .. code-block:: xml
      :caption: dct:language in rdf/xml: pick up all of these statements for dcat:Dataset and dcat:Distribution
      :emphasize-lines: 1

       <dct:language>de</dct:language>

.. admonition:: geocat
   :class: geocat

   .. code-block:: xml
      :caption: XPATH for dct:language on dcat:Distribution: pick up all

      .//gmd:transferOptions//gmd:CI_OnlineResource//che:LocalisedURL

   .. code-block:: xml
      :caption: Example of mapping the language code for dcat:Distribution
      :emphasize-lines: 7

      <gmd:CI_OnlineResource>
        <gmd:linkage xsi:type="che:PT_FreeURL_PropertyType">
          <gmd:URL>...</gmd:URL>
          <che:PT_FreeURL>
            <che:URLGroup>
              <che:LocalisedURL locale="#EN">
                https://www.bafu.admin.ch/bafu/en/home/office/divisions-sections/noise-and-nir-division.html
              </che:LocalisedURL>
            </che:URLGroup>
          </che:PT_FreeURL>
        </gmd:linkage>
        <gmd:protocol>...</gmd:protocol>
      </gmd:CI_OnlineResource>