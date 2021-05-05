.. container:: custom-breadcrumbs

   - :fa:`home` :doc:`Conventionen-Handbook <../../index>` :fa:`chevron-right`
   - :doc:`Properties <properties>` :fa:`chevron-right`
   - dct:coverage

******************************
dct:coverage
******************************

.. _dataset-coverage:

dcat:Dataset dct:coverage
============================

.. admonition:: DCAT-AP-CH
   :class: dcatapch

   :property: coverage
   :URI: dct:coverage
   :Range: `dct:LocationPeriodOrJurisdiction <https://www.dublincore.org/specifications/dublin-core/dcmi-terms/terms/LocationPeriodOrJurisdiction/>`__
   :Cardinality: 0..n
   :Compliance: optional
   :Usage note: spatial (and temporal) characteristics of the object or resource. This is the key element for
                supporting spatial or temporal range
                searching on document-like objects that are spatially referenced or time-referenced

.. admonition:: opendata.swiss
   :class: ogdch

   :Cardinality: 0..1 only

   .. code-block:: xml
     :caption: dct:coverage in rdf/xml

     <dct:coverage/>2020-04-09</dct:coverage>

.. admonition:: geocat
   :class: geocat

   mapping not implemented

.. _distribution-coverage:

dcat:Distribution dct:coverage
======================================

.. admonition:: DCAT-AP-CH
   :class: dcatapch

   :property: coverage
   :URI: dct:coverage
   :Range: `dct:LocationPeriodOrJurisdiction <https://www.dublincore.org/specifications/dublin-core/dcmi-terms/terms/LocationPeriodOrJurisdiction/>`__
   :Cardinality: 0..n
   :Compliance: optional
   :Usage note: spatial (and temporal) characteristics of the object or resource. This is the key element for
                supporting spatial or temporal range
                searching on document-like objects that are spatially referenced or time-referenced

.. admonition:: opendata.swiss
   :class: ogdch

   :property: coverage
   :URI: dct:coverage
   :Class: dcat:Distribution only
   :Range: conforms
   :Cardinality: 0..1 only
   :Mandatory: no

   .. code-block:: xml
     :caption: dct:coverage in rdf/xml

     <dct:coverage/>2020-04-09</dct:coverage>

.. admonition:: geocat
   :class: geocat

   mapping not implemented
