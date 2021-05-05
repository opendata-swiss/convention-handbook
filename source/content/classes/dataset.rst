.. container:: custom-breadcrumbs

   - :fa:`home` :doc:`Conventionen-Handbook <../../index>` :fa:`chevron-right`
   - :doc:`Classes <classes>` :fa:`chevron-right`
   - Dataset

***************
dcat:Dataset
***************

.. list-table:: Properties of dcat_Distribtuion
    :widths: 10 5 10 50 10
    :header-rows: 1
    :stub-columns: 1

    * - dcat:Dataset
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
      - mandatory 1..n
      - conforms
      - conforms
      - conforms
    * - dct:description
      - mandatory 1..n
      - conforms
      - conforms
      - conforms
    * - dct:issued
      - optional 0..1
      - conditional 0..1
      - not validated
      - not validated
    * - dct:modified
      - optional 0..1
      - conditional 0..1
      - not validated
      - not validated
    * - dct:publisher
      - recommended 0..1
      - mandatory 1..n
      - conforms
      - conforms
    * - dcat:contactPoint
      - recommended 0..n
      - mandatory 1..n
      - conforms
      - 1..1
    * - :ref:`dct:language <dataset-language>`
      - optional 0:n
      - conditional 0..n
      - conforms
      - 0..1
    * - dcat:distribtution
      - recommended 0..n
      - conditional 0..n
      - 1..n
      - 1..n
    * - dcat:keyword
      - recommended 0..n
      - optional 0..n
      - conforms
      - conforms
    * - dcat:landingPage
      - optional 0:n
      - conditional 0..1
      - ?
      - ?
    * - dct:spatial
      - recommended 0..n
      - conforms
      - x
      - x
    * - :ref:`dct:coverage <dataset-coverage>`
      - x
      - :ref:`optional 0..n <coverage-dcat-ap-ch>`
      - x
      - x
    * - dct:temporal
      - recommended 0..n
      - optional 0..n
      - conforms
      - conforms
    * - :doc:`dct:accrualPeriodicity <../properties/accrual-periodicity>`
      - :ref:`optional 0..1 <accrual-periodicity-dcat-ap>`
      - :ref:`conforms <accrual-periodicity-dcat-ap-ch>`
      - :ref:`conforms <accrual-periodicity-opendata-swiss>`
      - :ref:`conforms <accrual-periodicity-geocat>`
    * - dct:identifier
      - optional 0..n
      - mandatory 1..1
      - conforms
      - conforms
    * - dct:relation
      - recommended 0..n
      - conforms
      - conforms
      - conforms
    * - rdfs:seeAlso
      - x
      - optional 0:n
      - conforms
      - conforms
    * - schema:image
      - x
      - optional 0:3
      - x
      - x
