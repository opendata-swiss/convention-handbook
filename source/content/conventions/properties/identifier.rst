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