.. container:: custom-breadcrumbs

   - :fa:`home` :doc:`Conventionen-Handbook <../../index>` :fa:`chevron-right`
   - :Properties


*********************
Auf einen Blick
*********************

Properties
=================

.. list-table:: Properties implemented by DCAT-AP-CH
    :widths: 10 5 10 50 10
    :header-rows: 1
    :stub-columns: 1

    * - Properties
      - dcat:Catalog
      - dcat:Dataset
      - dcat:Distribution
      - foaf:Agent
    * - :doc:`dct:title <title>`
      - mandatory
      - mandatory
      - optional
      - x
    * - :doc:`dct:description <description>`
      - mandatory
      - mandatory
      - x
      - x
    * - :doc:`dct:issued <issued>`
      - mandatory
      - mandatory
      - optional
      - x
    * - :doc:`dct:modified <modified>`
      - conditional
      - conditional
      - conditional
      - x
    * - :doc:`foaf:homepage <homepage>`
      - mandatory
      - x
      - x
      - x
    * - :doc:`dct:publisher <publisher>`
      - mandatory
      - mandatory
      - x
      - x
    * - :doc:`dcat:themeTaxonomy <theme-taxonomy>`
      - optional
      - optional
      - x
      - x
    * - :doc:`dct:rights <rights>`
      - optional
      - conditional
      - conditional
      - x
    * - :doc:`dct:license <license>`
      - optional
      - conditional
      - conditional
      - x
    * - :doc:`dct:language <language>`
      - :ref:`optional <catalog-language>`
      - :ref:`conditional <dataset-language>`
      - :ref:`conditional <distribution-language>`
      - x
    * - :doc:`foaf:name <name>`
      - x
      - x
      - x
      - mandatory

