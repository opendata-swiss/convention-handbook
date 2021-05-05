.. container:: custom-breadcrumbs

   - :fa:`home` :doc:`Conventionen-Handbook <../../index>` :fa:`chevron-right`
   - :doc:`Conventions <../conventions>` :fa:`chevron-right`
   - Distributions

********************
dcat:Distributions
********************

.. list-table:: Properties of dcat_Distribtuion
    :widths: 10 5 10 50 10
    :header-rows: 1
    :stub-columns: 1

    * - dcat:Distribtion
      - DCAT-AP
      - DCAT-AP-CH
      - opendata.swiss
      - Geocat
    * - URI
      - :ref:`1..1 <uri-dcat-ap>`
      - x
      - x
      - x
    * - dct:title
      - optional 0..n
      - conditional 0..n
      -
      -
    * - dct:description
      - recommended 0..n
      - conditional 0..n
      -
      -
    * - :ref:`dct:language <distribution-language>`
      - optional
      - conditional
      - conforms
      - conforms
    * - dct:issued
      - optional 0..1
      - mandatory 1..1
      -
      -
    * - dct:modified
      - optional 0..1
      - conditional 0..1
      -
      -
    * - dcat:accessURL
      - mandatory 1..n
      - mandatory 1..n
      - 1..1
      - 1..1
    * - dct:rights
      - optional 0..1
      - mandatory 1..1
      -
      -
    * - dct:license
      - recommended 0..1
      - optional 0..1
      -
      -
    * - dct:identifier
      - x
      - optional 0..1
      -
      -
    * - dcat:downloadURL
      - optional 0..n
      - optional 0..n
      - 0..1
      - 0..1
    * - dcat:byteSize
      - optional 0..1
      - conditional 0..1
      -
      -
    * - dcat:mediaType
      - optional 0..1
      - conditional 0..1
      -
      -
    * - dct:format
      - recommended 0..1
      - conditional 0..1
      -
      -
    * - :ref:`dct:coverage <distribution-coverage>`
      - x
      - optional 0..n
      - optional 0..1
      - x
    * - schema:image
      - x
      - optional 0..3
      - x
      - x
