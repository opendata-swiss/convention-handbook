.. container:: custom-breadcrumbs

   - :fa:`home` :doc:`Conventions-Handbook <../../index>` :fa:`chevron-right`
   - :doc:`Conventions <../conventions>` :fa:`chevron-right`
   - Namespaces

*********************
Namespaces
*********************

Wie definiere ich die Namespaces in meinem Datenkatalog?
==========================================================

.. container:: Intro

   Namespaces sind die Vokabulare, die benutzt werden um den Datenkatalog zu beschreiben.
   Damit der Datenkatalog beim Import richtig verstanden wird, müssen die benutzen
   Datenvokabulare abgesprcohen sein. Die unterstützen Namespaces sind Teil der Definition eines
   :general:term:`Applikationsprofils <DCAT-Applikationsprofil>`,
   sowie des :general:term:`DCAT-AP-CH` oder :general:term:`DCAT-AP`. Der DCAT-AP kennt mehr Vokabulare als
   der DCAT-AP-CH. Wenn der DCAT-AP-CH in Zukunft um zusätzliche Vokabulare erweitert wird, werden
   diese erst Eingang ins Konventionen-Handbuch finden und erst später auch im DCAT-AP-CH beschrieben sein.

Überblick
---------------

- :ref:`Namespaces im DCAT-AP-CH <namespaces-dcat-ap-ch>`

.. _namespaces-dcat-ap-ch:

Aktuelle Namespaces im DCAT-AP-CH
---------------------------------------

.. admonition:: :dcat:term:`Konvention Namespaces DCAT-AP-CH`
   :class: konvention

   Wie definiere ich Namespaces?

   Die benutzen Vokabulare sollen am Anfang des Datenkatalog angebenen werden.
   Im Datenkatalog selbst wird nur das jeweilige Kürzel verwendet, nicht
   aber der Namespace-URI.
   Siehe :ref:`Beispiel <dcatapch-namespaces-beispiel-rdf>`.

   Folgende Namespaces werden zur Zeit im DCAT-AP-CH unterstützt:

   :dcat: http://www.w3.org/ns/dcat#
   :dct: http://purl.org/dc/terms/
   :rdf: http://www.w3.org/1999/02/22-rdf-syntax-ns#
   :rdfs: http://www.w3.org/2000/01/rdf-schema#
   :xsd: http://www.w3.org/2001/XMLSchema#
   :schema: http://schema.org/
   :vcard: http://www.w3.org/2006/vcard/ns#
   :foaf: http://xmlns.com/foaf/0.1/
   :adms: https://www.w3.org/TR/vocab-adms/
   :skos: https://www.w3.org/2009/08/skos-reference/skos.html

Beispiele
^^^^^^^^^^^^^^

.. code-block:: xml
   :caption: Namesspaces des DCAT-AP-CH in rdf/xml

   <?xml version="1.0" encoding="utf-8"?>
   <rdf:RDF
      xmlns:dcat="http://www.w3.org/ns/dcat#"
      xmlns:dct="http://purl.org/dc/terms/"
      xmlns:foaf="http://xmlns.com/foaf/0.1/"
      xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
      xmlns:rdfs="http://www.w3.org/2000/01/rdf-schema#"
      xmlns:schema="http://schema.org/"
      xmlns:vcard="http://www.w3.org/2006/vcard/ns#"
   >
   </rdf:RDF>

.. code-block:: turtle
   :caption: Namespaces in Turtle

   @prefix dcat: <http://www.w3.org/ns/dcat#> .
   @prefix dct: <http://purl.org/dc/terms/> .
   @prefix foaf: <http://xmlns.com/foaf/0.1/> .
   @prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
   @prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
   @prefix schema: <http://schema.org/> .
   @prefix vcard: <http://www.w3.org/2006/vcard/ns#> .

