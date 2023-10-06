Web Application
=====

Preparation
------------
You can use PepQuery through `PepQuery Web <http://pepquery2.pepquery.org/>`. 
To use PepQuery Web, you don't need to prepare the MS/MS data and protein reference database
or install the PepQuery software. All you need to do is provide the target peptide/protein/DNA sequence
which you want to identify. 

Identifying novel peptides
----------------

Let's start with an example from the PepQuery2 manuscript: Can you identify the novel peptide **LVVVGADGVGK**
from the KRAS G12D mutation?

- How many PSMs can you identify in the LUAD (lung adenocarcinoma), COAD (colon adenocarcinoma) and OV (ovarian cancer) datasets?

.. note::

   You can also just play around with the Web Application and query different known or novel peptides/proteins in any of the datasets. 


**Parameters to set**

Here is a list of parameters you can send in the Web Application. In `italic` you can find one of the inputs for the example above.

- MS/MS dataset: select one MS/MS dataset which you want to search. `CPTAC_TCGA_Colon_cancer_Proteome_PDC000111`
- Task type: novel or known peptide/protein identification. `Novel peptide/protein`
- Target event: select the sequence class you provide (Peptide, protein and DNA sequences). `Peptide sequence`
- Input peptide/protein/DNA sequence or a protein ID. For one search, only one sequence is accepted. `LVVVGADGVGK`
- Reference database: a protein reference database. `gencode_v34_human`
- Scoring algorithm: peptide spectrum scoring algorithm: Hyperscore and MVH are available and Hyperscore is recommended. `Hyperscore`
- Fast searching mode: choose to use the fast mode for searching or not. In fast mode, only one better match from reference peptide-based competitive filtering steps will be returned. `Yes`


**Results**

After running your query you get the following results:

1. **Identification overview**: A list of the major parameters used in PepQuery including the command line to run it on the standalone version.

2. **Identification results**: Overview of the PSMs with confident matches highlighted in green. An overview of the columns can be found `here <http://pepquery.org/document.html#saoutput>_`.

3. **Spectrum annotation**: When you click on a PSM in the identification result you can see the corresponding spectrum. Additionally, you can look at the spectra from the best PSM in the reference database and the unrestricted modification-based search. 

4. **Sample information**: In theory you can find the sample information for the selected row here. However this has never worked for me so far. 

