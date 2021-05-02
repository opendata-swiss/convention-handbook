.. container:: custom-breadcrumbs

   - :fa:`home` :doc:`Conventionen-Handbook <../../index>` :fa:`chevron-right`
   - :doc:`Conventions <../conventions>` :fa:`chevron-right`
   - Accrual Periodicity

******************************
Coverage
******************************

.. admonition:: DCAT-AP
   :class: dcatap

   This property is not on the DCAT-AP
   There are ``dct:spatial`` and ``dct:temporal``  for the Dataset as recommended
   properties and ``dcat:temporalResolution``
   and ``dcat:spatialResolutionInMeters`` for the Distribtion as optional poperties

.. admonition:: DCAT-AP-CH
   :class: dcatapch

   :property: coverage
   :URI: dct:coverage
   :Class: dcat:Dataset and dcat:Distribution
   :Range: `dct:LocationPeriodOrJurisdiction <https://www.dublincore.org/specifications/dublin-core/dcmi-terms/terms/LocationPeriodOrJurisdiction/>`__
   :Cardinality: 0:n
   :Mandatory: no
   :Usage note: On Distribution this property is used to map the Distributions
                to the time or area that they cover. On Datasets the usage seems to
                be more unclear

.. admonition:: opendata.swiss
   :class: convention

   Implementation in rdf/xml

.. code-block:: xml
  :caption: dct:coverage

  <dct:coverage/>2020-04-09</dct:coverage>

.. admonition:: geocat
   :class: geocat

    No mapping is currently implemented: the field is not set for geodata.
