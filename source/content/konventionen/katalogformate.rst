.. container:: custom-breadcrumbs

   - :fa:`home` :doc:`Handbuch <../../index>` :fa:`chevron-right`
   - :doc:`Konventionen <../konventionen>` :fa:`chevron-right`
   - Datenkatalog-Formate

*********************
Datenkatalog Formate
*********************

In welchem Format definiere ich meinen Datenkatalog?
==========================================================

.. container:: Intro

   Datenkatalog dienen zum Weiterreichen der Metadaten über vorhandene physische Ressourcen. Damit diese Weitergabe
   klappt muss vereinbart werden in welchen Formaten diese Datenkataloge erwartet und interpretiert
   werden können. Dies ist unabhängig vom Datenstandard (:term:`DCAT-AP-CH`). Vielmehr hängt es vom Datenportal
   ab, welche Daten dort importiert werden kömnen. Das ist in diesem Falls :term:`opendata.swiss`.
   Derzeit können nur DCAT-Datenkatalog im Format :term:`rdf/xml` und Geodatenkatalog im Format :term:`csw`
   importiert werden. Es ist möglich, dass sich die Anzahl der verstandenen Datenformate in Zukunft erweitert.

Überblick
-------------------------------------------

- :ref:`Konvention DCAT Datenkatalog Format <katalogformate-dcat>`
- :ref:`Konvention Geodatenkatalog Format <katalogformate-geodaten>`
- :ref:`Konvertierung von Meta-Datenformaten <datenformate-konvertierung>`

.. _katalogformate-dcat:

Datenkatalog Formate DCAT
-------------------------------

.. admonition:: :dcat:term:`Konvention DCAT Datenkatalog Format`
   :class: konvention

   In welchem RDF-Format muss mein Datenkatalog vorliegen?

   Zur Zeit können nur Datenkatalog im Format ``rdf/xml`` auf :term:`opendata.swiss` geharvested werden.
   Eine Ausnahme bilden :ref:`Geodaten  <dcatapch-002-katalogformate-geodaten>`
   Im Datenkatalog selbst wird nur das jeweilige Kürzel verwendet, nicht aber der Namespace-URI.

.. _katalogformate-geodaten:

Datenkatalog Formate Geodaten
-------------------------------

.. admonition:: :geo:term:`Konvention Geodaten Datenkatalog Format`
   :class: konvention

   In welchem Format muss mein Geodatenkatalog vorliegen?

   Geodaten werden im Format csw erwartet und im Datenstandard ISO-19139_che.
   Für diesen Datenstandard ist ein Mapping auf den DCAT-AP-CH definiert.

.. _datenformate-konvertierung:

Konvertierung von Datenkatalogen in anderen Formaten
-------------------------------------------------------

Es ist möglich, dass in der Zukunft auch weitere Datenformate auf opendata.swiss unterstützt werden wie ``turtle`` und ``json_ld``.
Solange das noch nicht der Fall ist kann man dennoch den Datenkatalog in einem anderen Format erstellen und
anschliessend nach ``rdf/xml`` konvertieren. Der besseren Lesbarkeit wegen sind bei den Besipielen auch Beispiele
in ``turtle`` vorhanden.

.. admonition:: Datenkataloge konvertieren
   :class: general

   RDF-Datenkatalog in anderen Datenformaten, können mit einem Online verfügbaren Werkzeug
   nach rdf/xml konvertierte werden: https://www.easyrdf.org/converter
