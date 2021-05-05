.. container:: custom-breadcrumbs

   - :fa:`home` :doc:`Conventionen-Handbook <../../index>` :fa:`chevron-right`
   - :doc:`Conventions <../conventions>` :fa:`chevron-right`
   - Catalog

***************
dcat:Catalog
***************

.. list-table:: Properties of dcat:Catalog
    :widths: 10 5 10 50 10
    :header-rows: 1
    :stub-columns: 1

    * - dcat:Catalog
      - DCAT-AP
      - DCAT-AP-CH
      - opendata.swiss
      - Geocat
    * - URI
      - :ref:`1..1 <uri-dcat-ap>`
      - x
      - x
      - x
    * - :doc:`dct:title <../properties/title>`
      - mandatory 1..n
      - conforms
      - x
      - x
    * - dct:description
      - mandatory 1..n
      - conforms
      - x
      - x
    * - dct:issued
      - recommended 0..1
      - mandatory 1..1
      - x
      - x
    * - dct:modified
      - recommended 0..1
      - conditional 0:1
      - x
      - x
    * - foaf:homepage
      - recommended 0..1
      - mandatory 1..1
      - x
      - x
    * - dct:publisher
      - mandatory 1..1
      - conforms
      - x
      - x
    * - dcat:themeTaxonomy
      - recommended 0..n
      - optional 0..n
      - x
      - x
    * - dcat:dataset
      - mandatory 1..n
      - conforms
      - conforms
      - conforms
    * - dct:rights
      - optional 0..1
      - conforms
      - x
      - x
    * - dct:license
      - recommended 0..1
      - optional 0..1
      - x
      - x
    * - :ref:`dct:language <catalog-language>`
      - recommended 0..n`
      - optional 0..n`
      - x
      - x
