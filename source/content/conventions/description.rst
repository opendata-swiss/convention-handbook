.. container:: custom-breadcrumbs

   - :fa:`home` :doc:`Conventions-Handbook <../../index>` :fa:`chevron-right`
   - :doc:`Conventions <../conventions>` :fa:`chevron-right`
   - Title and Description

************************************************************************************
Title and Description
************************************************************************************

:Properties:  ``dct:title``, ``dct:decription``
:Classes:     ``dcat:Catalog``, ``dcat:Dataset``, ``dcat:Distribution``

.. admonition:: DCAT-AP
   :class: dcatap

   :dcat:Dataset 1:n: ``dcat:title`` and ``dct: description`` are mandatory
   :dcat:Catalog 1:n:  ``dcat:title`` and ``dct: description`` are mandatory
   :dcat:Distribution 0:n: ``dcat:title`` and ``dct: description`` are optional

   There can be more than one title and description: one for each supported language

.. admonition:: DCAT-AP-CH
   :class: dcatapch

   :DCAT-AP: conformant
   :opendata.swiss: dcat:Catalog title and description are currrently not used

   - one of the languages de, fr, it or en is expected
   - consider to require en as a language, so that the dataset shows a title and description on the
     European Dataportal

Überblick
-------------------------------------------

- :ref:`Title and Description for DCAT-catalogs <title-description-dcat>`
- :ref:`Title and Description for GEOCAT-catalogs <titel-description-geocat>`

.. _title-description-dcat:

Title and Description DCAT
----------------------------------------------------

.. admonition:: :dcat:term:`dct:title dct:description`
   :class: convention

   Title and description are manatory on ``dcat:Dataset``.
   and optional for ``dcat:Distribution``. There should be at least one
   national language set: German (``de``), French (``fr``) or Italian (``it``).
   English (``en``) should also be set, since it is the language which is taken by the European
   Dataportal to represent the dataset.

.. container:: attribute

    **dct:title** 1..n

    :Type: ``rdfs:Literal`` http://www.w3.org/TR/rdf-schema/#ch_literal
    :Parent: ``dcat:Catalog``, ``dcat:Dataset``, ``dcat:Distribution``
    :Cardinality: 1..n (one for each language) for ``dcat:Catalog``, ``dcat:Dataset``
                  0..n for ``dcat:Distribution``
    :Attributes: - Name: ``xml:lang``
                 - Content: ``en``, ``de``, ``fr``, ``it``
                 - Description: Language of the element
                 - Mandatory : yes
    :Description: Title of the dataset in the language defined by the
                  ``xml:lang`` attribute

    .. code-block:: xml
       :caption: dct:title
       :emphasize-lines: 1

        <dct:title xml:lang="de">Eisenbahnlärm Nacht</dct:title>

.. container:: attribute

    **dct:description** 1..n

    :Type: ``rdfs:Literal`` http://www.w3.org/TR/rdf-schema/#ch_literal
    :Cardinality: 1..n (one for each language) for ``dcat:Catalog``, ``dcat:Dataset``
                  0..n for ``dcat:Distribution``
    :Attributes: - Name: ``xml:lang``
                 - Content: ``en``, ``de``, ``fr``, ``it``
                 - Description: Language of the element
                 - Mandatory : yes
    :Description: Description of the dataset in the the language defined by the
                  ``xml:lang`` attribute

    .. code-block:: xml
       :caption: dct:description
       :emphasize-lines: 1,2,3,4

       <dct:description xml:lang="de">
           Die Karte zeigt, welcher Lärmbelastung die Bevölkerung
           durch den Schienenverkehr ausgesetzt ist.
       </dct:description>

.. _title-description-gm03:

Title and Description GM03
----------------------------------------------------

.. admonition:: :geo:term:`GM03 dcat:Catalog dct:title and dct:description`
   :class: convention

    The dataset title and description are currently not mapped for the Catalog

.. admonition:: :geo:term:`GM03 dcat:Dataset dct:title and dct:description`
   :class: convention

    The dataset title and description are mapped as localized Character Strimgs

.. container:: attribute

    **dct:title**

    .. code-block:: xml
       :caption: ISO-19139_che XPath for dct:title of dcat:Dataset

       //gmd:identificationInfo//gmd:citation//gmd:title//gmd:textGroup/gmd:LocalisedCharacterString

.. container:: attribute

    **dct:description**

    .. code-block:: xml
       :caption: ISO-19139_che XPath for dct:description of dcat:Dataset

       //gmd:transferOptions//gmd:CI_OnlineResource//gmd:description//gmd:LocalisedCharacterString

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

    .. code-block:: xml
       :caption: Example of getting dct:description: only 4 languages are taken: DE, EN, FR, IT
       :emphasize-lines: 5, 8, 11, 14

       <gmd:abstract xsi:type="gmd:PT_FreeText_PropertyType">
          <gco:CharacterString>swissTLM3D Wanderwege enthält die signalisierten Wanderrouten der Schweiz und des Fürstentums Liechtenstein. Der Datensatz wird in Zusammenarbeit mit dem Bundesamt für Strassen ASTRA, SchweizMobil, Schweizer Wanderwege und den Kantonen publiziert. swissTLM3D Wanderwege bildet einen Teil des Datensatzes swissTLM3D.</gco:CharacterString>
          <gmd:PT_FreeText>
             <gmd:textGroup>
                <gmd:LocalisedCharacterString locale="#FR">swissTLM3D chemins de randonnée pédestre comprend les chemins de randonnée officiels de la Suisse et de la Principauté de Liechtenstein. Le jeu de données est publié en collaboration avec l'Office fédéral des routes OFROU, SuisseMobile, Suisse Rando et les cantons. swissTLM3D chemins de randonnée pédestre fait partie du jeu de données swissTLM3D.</gmd:LocalisedCharacterString>
             </gmd:textGroup>
             <gmd:textGroup>
                <gmd:LocalisedCharacterString locale="#DE">swissTLM3D Wanderwege enthält die signalisierten Wanderrouten der Schweiz und des Fürstentums Liechtenstein. Der Datensatz wird in Zusammenarbeit mit dem Bundesamt für Strassen ASTRA, SchweizMobil, Schweizer Wanderwege und den Kantonen publiziert. swissTLM3D Wanderwege bildet einen Teil des Datensatzes swissTLM3D.</gmd:LocalisedCharacterString>
             </gmd:textGroup>
             <gmd:textGroup>
                <gmd:LocalisedCharacterString locale="#EN">swissTLM3D hiking trails contains the hiking trails of Switzerland and the Principality of Liechtenstein. This dataset is published in collaboration with the Federal roads office FEDRO, SwitzerlandMobility, Suisse Rando and the cantons. swissTLM3D hiking trails forms a part of the dataset swissTLM3D.</gmd:LocalisedCharacterString>
             </gmd:textGroup>
             <gmd:textGroup>
                <gmd:LocalisedCharacterString locale="#IT">swissTLM3D sentieri pedestri comprende i sentieri pedestri ufficiali della Svizzera e del Principato del Liechtenstein. Il set di dati viene pubblicato in collaborazione con l'Ufficio federale delle strade USTRA, SvizzeraMobile, Sentieri Svizzeri e i cantoni. swissTLM3D sentieri pedestri fa parte del set di dati swissTLM3D.</gmd:LocalisedCharacterString>
             </gmd:textGroup>
             <gmd:textGroup>
                <gmd:LocalisedCharacterString locale="#RM">swissTLM3D Sendas da viandar cuntegna las sendas da viandar uffizialas da la Svizra e dal Principadi da Liechtenstein. L'unitad da datas vegn publitgada en collavuraziun cun l'Uffizi federal da vias UVias, cun SvizraMobila, cun Sendas svizras e cun ils chantuns. swissTLM3D Sendas da viandar è ina part da l'unitad da datas swissTLM3D.</gmd:LocalisedCharacterString>
             </gmd:textGroup>
          </gmd:PT_FreeText>
       </gmd:abstract>

.. admonition:: :geo:term:`GM03 distribution title and description`
   :class: convention

   The mapping depends on the distribution protocol:
   ``//gmd:transferOptions//gmd:CI_OnlineResource//gmd:protocol/gco:CharacterString``

   see :doc:`geocat-distributions <../classes/geocat-distribution>`

