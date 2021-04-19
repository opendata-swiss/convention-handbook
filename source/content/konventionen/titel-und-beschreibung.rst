.. container:: custom-breadcrumbs

   - :fa:`home` :doc:`Konventionen-Handbuch <../../index>` :fa:`chevron-right`
   - :doc:`Konventionen <../konventionen>` :fa:`chevron-right`
   - Titel und Beschreibung

************************************************************************************
Titel und Beschreibung
************************************************************************************

Wie benenne und beschreibe ich ein Dataset, den Datenkatalog, die Distributionen?
===================================================================================

.. container:: Intro

   Der :term:`DCAT-AP` sind ``dcat:title`` und ``dct: description`` Pflichtfelder
   für das ``dcat:Dataset``  und den ``dcat:Catalog``. Bei ``dcat:Distribution`` sind diese
   Felder optional.
   Im DCAT-AP kann es mehrere Titel und Beschreibungen geben: dabei ist an Titel und Beschreibungen
   in verschiedenen Sprachen gedacht.
   Der DCAT-AP-CH ist in diesen Attributen kompatibel mit dem DCAT-AP und hat genau dieselben
   Regeln für diese Attribute.

Überblick
-------------------------------------------

- :ref:`Titel und Beschreibung bei DCAT-Datenkatalogen <titel-beschreibung-dcat>`
- :ref:`Titel und Beschreibung bei Geodaten Datenkatalogen <titel-beschreibung-geodaten>`

.. _titel-beschreibung-dcat:

Titel und Beschreibung bei DCAT-Datenkatalogen
----------------------------------------------------

.. admonition:: :dcat:term:`Konvention Titel und Beschreibung bei  Geodaten Datenkatalogen`
   :class: konvention

   Titel und Beschreibung sind Pflichtattribute für ``dcat:Catalog`` und ``dcat:Dataset``.
   Sie sind optional für ``dcat:Distribution``.
   Es sollten jeweils mindestens eine Landesprache und Englisch besetzt sein.
   Englisch ist die Sprache, die auf das europäische Datenportal übernommen wird.

.. container:: attribute

    **dct:title** 1..n

    :Type: ``rdfs:Literal`` http://www.w3.org/TR/rdf-schema/#ch_literal
    :Parent: ``dcat:Catalog``, ``dcat:Dataset``, ``dcat:Distribution``
    :Mandatory: yes
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

        <dct:title xml:lang="de">Eisenbahnlärm Nacht</dct:title>

.. container:: attribute

    **dct:description** 1..n

    :Type: ``rdfs:Literal`` http://www.w3.org/TR/rdf-schema/#ch_literal
    :Mandatory: yes
    :Cardinality: 1..n (one for each language)
    :Attributes: - Name: ``xml:lang``
                 - Content: ``en``, ``de``, ``fr``, ``it``
                 - Description: Language of the element
                 - Mandatory : yes
    :Description: Description of the dataset in the the language defined by the
                  ``xml:lang`` attribute

    .. code-block:: xml
       :caption: dct:description

       <dct:description xml:lang="de">
           Die Karte zeigt, welcher Lärmbelastung die Bevölkerung
           durch den Schienenverkehr ausgesetzt ist.
       </dct:description>

.. _titel-beschreibung-geodaten:

Titel und Beschreibung bei Geodaten Datenkatalogen
----------------------------------------------------

.. admonition:: :geo:term:`Konvention Titel und Beschreibung bei Geodaten-Datenkatalogen`
   :class: konvention

    Bei Geodaten werden Titel und Beschreibung wie folgt gemapped:

.. container:: attribute

    **dct:title**

    :Display name on opendata.swiss: Pagetitle
    :ISO-19139_che XPath:

    .. code:: xml

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

.. container:: attribute

    **dct:description**

    :Display name on opendata.swiss: Description
    :ISO-19139_che XPath:

    .. code:: xml

        //gmd:identificationInfo//gmd:abstract//gmd:textGroup/gmd:LocalisedCharacterString

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


