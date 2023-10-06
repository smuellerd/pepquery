Standalone version
=====

.. _installation:

Installation
------------

To use the standalone version of PepQuery2, first install it on your computer:

You must have Java 1.8 or newer installed. To check your java version please open your terminal 
application and run the following command:

.. code-block:: console

   java -version

Next go to download the standalone version of PepQuery here <http://www.pepquery.org/data/pepquery-2.0.2.tar.gz>_. 
After you download it, please uncompress it using the following command line and you will find a jar file in the package folder. 
The whole installation process typically only takes one or two minutes. Depending on where the file is downloaded you might need to adjust the path (see example below)

.. code-block:: console

   tar xvzf pepquery-2.0.2.tar.gz (or tar xvzf Downloads/pepquery-2.0.2.tar.gz) 

If you want to run PepQuery with your own data you need to provide MS/MS data in 
`MGF <http://www.matrixscience.com/help/data_file_help.html#GEN>`_ format, 
a reference protein database in FASTA format and a peptide, protein, DNA sequence or a pair of peptide and spectrum ID.
We will not go into this here, so please refer to the official documantation for more information.  

Identifying novel peptides
----------------

Let's repeat the example from the :doc:`webapplication` section: Can you identify the novel peptide LVVVGADGVGK 
from the KRAS G12D mutation in the LUAD (lung adenocarcinoma), COAD (colon adenocarcinoma) and OV (ovarian cancer) datasets?

With the standalone version you can search all three datasets at the same time by running the following command:

.. code-block:: console

   java -jar pepquery-2.0.2/pepquery-2.0.2.jar -b CPTAC_LUAD_Discovery_Study_Proteome_PDC000153,CPTAC_TCGA_Colon_Cancer_Proteome_PDC000111,CPTAC_Prospective_Ovarian_PNNL_Proteome_Qeplus_PDC000118 -db gencode:human -o pepquery_kras_g12d/ -i LVVVGADGVGK

So let's take a closer look at the command line:

- **java -jar pepquery-2.0.2/pepquery-2.0.2.jar**: Link to your PepQuery installment
- **-b CPTAC_LUAD_Discovery_Study_Proteome_PDC000153, CPTAC_TCGA_Colon_Cancer_Proteome_PDC000111, CPTAC_Prospective_Ovarian_PNNL_Proteome_Qeplus_PDC000118**: This specifies the datasets you want to search in. Multiple datasets are seperated with a comma. A full list of datasets in the PepQueryDB is available with "java -jar pepquery-2.0.2/pepquery-2.0.2.jar -b show".
- **-db gencode:human**: Specifies the reference database.
- **-o pepquery_kras_g12d/**: Output folder where the results are saved.
- **-i LVVVGADGVGK**: Input peptides. Multiple peptides would be seperated with a comma.

There are a lot more parameters that can be set in the standalone version which 
are listed `here <http://pepquery.org/document.html#saparameter>`_.

**Results**

The results will appear in your specified output folder. The main result file of PepQuery is the ptm_rank.txt file. 
This file includes the detailed identification results for the input target peptide. 
You can open the psm_rank.txt file in excel and check how many PSMs 
passed the quality checks (confident = 'Yes'). 

For Result visualisation please refer to the official `PepQuery
visualisation <http://pepquery.org/document.html#savis>`_.


.. note::

   There are many other examples in the official `PepQuery Demo <http://pepquery.org/document.html#saexample>`_.

