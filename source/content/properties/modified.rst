.. container:: custom-breadcrumbs

   - :fa:`home` :doc:`Conventionen-Handbook <../../index>` :fa:`chevron-right`
   - :doc:`properties <../properties>` :fa:`chevron-right`
   - dct:modified

******************************
dct:modified
******************************

.. _accrual-periodicity-dcat-ap:

.. admonition:: DCAT-AP
   :class: dcatap

   :property: frequency
   :URI: dct:accrualPeriodicity
   :Class: dcat:Dataset
   :Range: `dct:Frequency <http://dublincore.org/groups/collections/frequency/>`__
   :Cardinality: 0:1
   :Usage note: This property refers to the frequency
                at which the Dataset is updated.

.. _accrual-periodicity-dcat-ap-ch:

.. admonition:: DCAT-AP-CH
   :class: dcatapch

   conforms

.. _accrual-periodicity-opendata-swiss:

.. admonition:: opendata.swiss
   :class: ogdch

   .. code-block:: xml
      :caption: dct:accrualPeriodicity in rdf/xml
      :emphasize-lines: 1

      <dct:accrualPeriodicity rdf:resource="http://purl.org/cld/freq/daily"/>

.. _accrual-periodicity-geocat:

.. admonition:: geocat
   :class: geocat

   .. code-block:: xml
      :caption: XPATH for dct:accrualPeriodicity
      :emphasize-lines: 1

      //gmd:identificationInfo//che:CHE_MD_MaintenanceInformation/gmd:maintenanceAndUpdateFrequency/gmd:MD_MaintenanceFrequencyCode/@codeListValue

   .. code-block:: xml
      :caption: mapping of values
      :emphasize-lines: 1

      frequency_mapping= {
        'continual': 'http://purl.org/cld/freq/continuous',
        'daily': 'http://purl.org/cld/freq/daily',
        'weekly': 'http://purl.org/cld/freq/weekly',
        'fortnightly': 'http://purl.org/cld/freq/biweekly',
        'monthly': 'http://purl.org/cld/freq/monthly',
        'quarterly': 'http://purl.org/cld/freq/quarterly',
        'biannually': 'http://purl.org/cld/freq/semiannual',
        'annually': 'http://purl.org/cld/freq/annual',
        'asNeeded': 'http://purl.org/cld/freq/completelyIrregular',
        'irregular': 'http://purl.org/cld/freq/completelyIrregular',
      }
