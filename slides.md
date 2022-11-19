<small>Albert-Ludwigs University Freiburg</small>

<small>Department of Computer Science</small>

<small>Bioinformatics Group</small>

<small>Master Thesis</small>

##### **Development and evaluation of Galaxy pipelines for detection of SARS-CoV-2 variants by genomic analysis of wastewater samples**

<small>Author: Polina Polunina</small>

<small>Examiner: Prof. Dr. Rolf Backofen</small>

<small>Second Examiner: Prof. Dr. Wolfgang R. Hess</small>

<small>Advisors: Dr. Berenice Batut, Dr. Wolfgang Maier</small>

---

<span class="menu-title" style="display: none">Table of contents</span>

<div style="text-align: left">

### Table of contents
CHANGE
- <span style="font-size:30px">**Introduction**</span>
    - <span style="font-size:20px">SARS-CoV-2 surveillance</span>
    - <span style="font-size:20px">Galaxy?</span>
    - <span style="font-size:20px">Wastewater surveillance</span>
    - <span style="font-size:20px">State-of-the-art</span>
- <span style="font-size:30px">**Methods**</span>
- <span style="font-size:30px">**Results**</span>
    - <span style="font-size:20px">Mock dataset</span>
    - <span style="font-size:20px">Real-world dataset</span>
- <span style="font-size:30px">**Discussion**</span>
    - <span style="font-size:20px">Limitations</span>
    - <span style="font-size:20px">Next steps</span>
- <span style="font-size:30px">**Summary**</span>

</div>

---

<span class="menu-title" style="display: none">Introduction</span>

## Introduction

<img src="img/intro/nextstrain_phylo.png" alt="nextstrain"/>
<small style="position: absolute; right: 0%; font-size: 0.2em; bottom: -1%;">Source: nextstrain.org</small>

------

<span class="menu-title" style="display: none">SARS-CoV-2 surveillance</span>

### SARS-CoV-2 surveillance

<div class="r-stack">
<span class="fragment fade-out" data-fragment-index="0">
<img src="img/intro/sars-surveillance-bioinf.png" alt="drawing" width="800"/>
</span>
<span class="fragment current-visible" data-fragment-index="0">
<img src="img/intro/sars-surveillance-bioinf-highlight.png" alt="drawing" width="800"/>
</span>
</span>
<span class="fragment">
<img src="img/intro/sars-surveillance-bioinf-last.png" alt="Process diagram with bioinf steps for sars surveillance" width="800"/>
<small>Main steps to be done for bioinformatics of SARS-CoV-2 surveillance</small>
</span>

</div>

------

<span class="menu-title" style="display: none">Galaxy effort</span>

#### Galaxy effort for clinical surveillance

<div class="r-stack">
<span class="fragment fade-out" data-fragment-index="0">
<img src="img/intro/galaxy-analysis.jpg" alt="drawing" width="600"/>
<small style="position: absolute; right: 0%; font-size: 0.2em; bottom: -1%;">Source: Maier et al., 2021</small>
</span>
<span class="fragment current-visible" data-fragment-index="0">
<div style="text-align: left">

- transparency, accessibility, reproducibility
- 4 workflows for **clinical** SARS-CoV-2 data surveillance can be repurposed
- automated bots for regular data analysis

</div>

</span>
</div>

------

<span class="menu-title" style="display: none">Wastewater surveillance</span>

### Wastewater surveillance

<div class="r-stack">
<img class="fragment fade-out" data-fragment-index="0" src="img/intro/ww-process.png" alt="drawing" width="1000"/>
<span class="fragment current-visible" data-fragment-index="0">
<div style="text-align: left">
<small>

**Pros**
- variant detection 2 weeks sooner vs clinical
- detection in sewage even when SARS-CoV-2 prevalence is low
- more economical
- can cover 'seqiencing deserts'

**Cons**
- less accurate detection vs clinical testing
- data are anonymized
- difficult to quantify the number of infected people
- cannot show completely unbiased picture because of population mobility

</small>
</div>

</span>
</div>

------

<span class="menu-title" style="display: none">State-of-the-art</span>

### State-of-the-art

<div class="r-stack">
<img class="fragment fade-out" data-fragment-index="0" src="img/intro/prior-tools.png" alt="Simplified table with state of the art individual tools" width="1000"/>
<img class="fragment current-visible" data-fragment-index="0" src="img/intro/prior-pipelines.png" alt="Simplified table with state of the art standalone pipelines" width="1000"/>
</div>

------

<span class="menu-title" style="display: none">Aim of the thesis</span>

### Aim of the thesis

<div class="r-stack">
<span class="fragment fade-out" data-fragment-index="0">
<div style="text-align: left">

Develop pipelines for SARS-CoV-2 wastewater data analysis that is:
- complete
- accessible
- reproducible
- transparent
- regular

</div>
</span>

<img class="fragment current-visible" data-fragment-index="0" src="img/intro/tasks.png" alt="drawing" width="600"/>


---

<span class="menu-title" style="display: none">Methods</span>

### Methods

<div class="r-stack">
<span class="fragment fade-out" data-fragment-index="0">
<div style="text-align: left">

2 workflows:
- metatranscriptomic-illumina
- ampliconic-illumina

2 branches:
- Freyja-based
- COJAC-based

Extra steps:
- decontamination step
- taxonomic analysis
</div>
</span>
<span class="fragment current-visible" data-fragment-index="0">
<img src="img/methods/methods-ampliconic.png" alt="drawing" width="1000"/>
</span>
</span>
<span class="fragment">
<img src="img/methods/methods-metatranscriptomic.png" alt="drawing" width="1000"/>
</span>

</div>

Note:
- Galaxy wfs showed decent results for clinical SARS=CoV-2 data surveillance and was based on Galaxy that can assure transparency, reproducibility and availability as well as regular analysis tools (bots) -> repurposing existing galaxy wfs
- First: evaluation of needs showed that the most of  available real-world data are extracted with ampliconic and metatranscriptomic approaches with Illumina sequencing methods ->
- focus on 2 wfs: illumina-ampliconic + illumina-metatranscriptomic
- Freyja and COJAC tools were chosen to be implemented into Galaxy wfs -> there were 2 wrappers created with Planemo
- 2 branches were created: freyja-based and cojac-based that can be run simultaneously to get both results

------

<span class="menu-title" style="display: none">Datasets</span>

### Datasets

<div style="text-align: left">

Workflows were tested on:
- mock dataset
- real-world dataset
</div>

------

<span class="menu-title" style="display: none">Mock dataset</span>

### Mock dataset

<img src="img/methods/table-rmock-data.png" alt="table" width="600"/>

Note:
- Generation of mock dataset: Delta, BA.1, BA.2, asa well as synthetic lineage; Single lineage vs Two lineages
- Comparison Freyja, COJAC, and Lineagespot results with expected results

------

<span class="menu-title" style="display: none">Real-world dataset</span>

### Real-world dataset

<img src="img/methods/table-real-data.png" alt="table" width="800"/>

Note:
- In order to provide a fairly comprehensive analysis, real-world datasets for experiments in this thesis were selected in such a way that they cover a variety of locations in the world and different time points of collecting samples. 
- That is why the choice of my thesis fell on the four datasets: 
- i) one dataset from California where the samples were collected in 2020 at a wastewater interceptor; 
- ii) a dataset from the UK, with data collected in sewage across six major urban centers in the UK (with a total population equivalent of 3 million) around the same time period (late spring - early summer of 2020) as the previous dataset in order to show different proportions of different variants of the virus
- iii) a dataset from wastewater treatment facilities across Ontario, Canada collected by Canadian Research Institute for Food Safety, which is interesting to analyze because it contains one of the most recent datasets, the last sample was published in June of 2022;
- iv) a dataset from the US collected by the FDA Center for Food Safety and Applied Nutrition, one of the most extensive dataset with more than 340 samples already and regularly new samples are being added (last samples being from October of 2022). This dataset would be interesting to connect to Galaxy bots for regilar analysis

---

<span class="menu-title" style="display: none">Results</span>

## Results

------

<span class="menu-title" style="display: none">Results on mock dataset</span>

### Results on mock dataset
#### Single lineage expected

<div class="r-stack">
<span class="fragment fade-out" data-fragment-index="0">
<img src="img/results/singlin-num-bars.png" alt="drawing" width="600"/>
</span>
<span class="fragment current-visible" data-fragment-index="0">
<img src="img/results/venn-singlin.png" alt="drawing" width="600"/>
</span>
</span>
<span class="fragment">
<img src="img/results/dist-singlin-fr-co.png" alt="drawing" width="600"/>
</span>
</div>

Note:
- Distplot: distribution of the proportion of lineage detected by Freyja and COJAC among samples in the Single lineage group was plotted. Looking at fig of distribution, I conclude that for single lineage detection, the results of lineage proportion from COJAC and Freyja are from 0.9 to 1.
- However, some differences between Freyja and COJAC results are observed. Freyja showed a lower proportion of expected lineage, while for COJAC the proportion tends to 1 which is expected. Thus, we can guess that COJAC results for the single lineage group are closer to what was expected.

------

### Genome assembly
#### VGP *de novo* assembly workflow

<div class="r-stack">
<span class="fragment fade-out" data-fragment-index="0">

<img src="img/VGP_workflow.png" alt="drawing"/>

</span>
<span class="fragment current-visible" data-fragment-index="0">

<div style="text-align:left; font-size:28px">

- The VGP-Galaxy project has assembled 26 genomes in the last 6 months
- Largest: 4Gbp *Gastrophryne carolinensis*

</div>

<img src="img/gastrophryne.png" alt="drawing" width="800"/>

</span>
</div>

------

### Genome assembly
#### Within-species variation: resequencing

<div class="r-stack">
<span class="fragment fade-out" data-fragment-index="0">

<img src="img/within_specie_variation.png" alt="drawing" width="1200"/>

<small>The butterfly genus *Heliconius* contains species that are extremely difficult to tell apart.</small>

</span>
<span class="fragment current-visible" data-fragment-index="0">

<img src="img/resequencing.jpg" alt="drawing" width="700"/>

<small><small>Source: nature.com</small></small>

</span>
</div>

------

<span class="menu-title" style="display: none">Transcriptomics: expression analysis</span>

### Transcriptomics: RNA-seq

<div class="r-stack">
<span class="fragment fade-out" data-fragment-index="0">

<img src="img/transcription.jpg" alt="drawing" width="800"/>

<small><small>Source: metrics-lab.github.io</small></small>

</span>
<span class="fragment current-visible" data-fragment-index="0">

<img src="img/comparison_transcription.jpg" alt="drawing" width="800"/>

</span>
</div>

------

### Transcriptomics: RNA-seq
#### Differential expression analysis pipeline

<div class="r-stack">
<span class="fragment fade-out" data-fragment-index="0">

<img src="img/differential_expression.png" alt="drawing" width="500"/>

</span>
<span class="fragment current-visible" data-fragment-index="0">

<img src="img/DE_plots.png" alt="drawing" width="1000"/>

<small><small>Source: nature.com</small></small>

</span>
</div>

------

### Transcriptomics: RNA-seq
#### Cancer prognosis by gene expression analysis

<img src="img/transcriptome_cancer.jpg" alt="drawing" width="1000"/>

------

### Epigenetics

<a href="https://imgflip.com/i/6zn61x" ><img src="https://i.imgflip.com/6zn61x.jpg"  width="600"/></a>

------

<span class="menu-title" style="display: none">Epigenetics</span>
    
### Epigenetics

<div class="r-stack">
<span class="fragment fade-out" data-fragment-index="0">

Epigenetics is the study of **stable and inheritable phenotypic changes** that do not involve alterations in the DNA sequence.

<div style="text-align: left">
<br>

It involves multiple mechanisms:
    
- Covalent modifications (e.g. DNA/RNA methylation)
- Histone positioning
- Histone variants
- Many more!

</div>
</span>
<span class="fragment current-visible" data-fragment-index="0" style="font-size:40px">
<div style="text-align: left">

Detection requires usually  a three-phase strategy:

<br>

- Conversion of epigenetic into genetic information
    - Usually by biochemical methods
- High-throughput sequencing
- Computational and statisticall analysis

</div>

</span>
</div>

------

<span class="menu-title" style="display: none">DNA/RNA methylation</span>

### Epigenetics
#### Covalent modifications: DNA/RNA methylation

<div class="r-stack">
<span class="fragment fade-out" data-fragment-index="0">

<img src="img/methylation.jpg" alt="drawing" width="1000"/>

<small>DNA/RNA methylation **regulates gene expression** by recruiting proteins involved in gene repression or by inhibiting the binding of transcription factor(s) to DNA.</small>

</span>
<span class="fragment current-visible" data-fragment-index="0">
<img src="img/bisulfite_sequencing.jpg" alt="drawing" width="800"/>
<small>Bisulfite sequencing involves the deamination of unmodified cytosines to uracil.</small>
</span>
</span>
<span class="fragment">
<img src="img/paper_methylation.png" alt="drawing"/>
</span>
</div>

------

<span class="menu-title" style="display: none">Cancer molecular markers</span>

### Epigenetics
#### Identification of cancer molecular markers

<div class="r-stack">
<span class="fragment fade-out" data-fragment-index="0">

<img src="img/cancer_methylation.png" alt="drawing" width="700"/>

</span>
<span class="fragment current-visible" data-fragment-index="0">

<img src="img/cancer_genes.png" alt="drawing" width="900"/>

<small><small>Source: nature.com</small></small>

</span>
</div>

------

<span class="menu-title" style="display: none">Plant resistance to extreme conditions</span>

### Epigenetics
#### Evaluation of plant resistance to extreme conditions

<div class="r-stack">
<span class="fragment fade-out" data-fragment-index="0">

<img src="img/plants_methylation.png" alt="drawing" width="700"/>

<small><small>Plant stress memory and their capacity to influence plant tolerance to a changing environment and crop productivity is considered to play an important role in the adaptation and evolution of plants.</small></small>
    
</span>
<span class="fragment current-visible" data-fragment-index="0">

<img src="img/lysenko.png" alt="drawing" width="1000"/>

<small>"Hereditary changes can be induced by changing environmental conditions." <br><small>Trofim Denisovich Lysenko (1898-1976)</small></small>

</span>
</div>

------

<span class="menu-title" style="display: none">Neurodegenerative disorders</span>

### Epigenetics
#### Neuroepigenetics: study of psyquiatric disorders

<span style="font-size:28px">

<div style="text-align: left">

<br>
Psichyatric disorders influenced/associated by epigenetic modifications:
<br><br>

- Schizophrenia
- Rubinstein-Taybi syndrome
- Huntington's disease
- Fragile X syndrome

</div>
</span>

------

### Epigenetics
#### Neuroepigenetics: substance abuse disorders

<img src="img/opioid_overdose.png" alt="drawing" width="600"/>

<small><small>Five genes over-burdened by epigenetic modifications: ASTN2, KCNMA1, DUSP4, GABBR2, ENOX1.</small></small>

</span>
</div>

------

### Epigenetics
#### Neuroepigenetics: intergenerational transmission of fear

<span style="font-size:24px">

<div style="text-align: left">

<br>
Animal studies in rats have shown that:
<br><br>

- Persistent fear-related memory behaviour is dependent on *de novo* DNA methylation [1].
    - DNA-methyltransferases (DMT) inhibitors block the formation of traumatic memories.
- Genetic imprint from traumatic experiences carries through at least two generations [2].

</span>

<small><br>
[1] Bali P, Im HI, Kenny PJ. Methylation, memory and addiction. Epigenetics (2011). https://doi.org/10.4161/epi.6.6.15905<br><br>[2] Callaway, E. Fearful memories haunt mouse descendants. Nature (2013). https://doi.org/10.1038/nature.2013.14272
</small>

</div>

---

Thanks for you attention!