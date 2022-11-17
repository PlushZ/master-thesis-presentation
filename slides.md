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
<img src="img/intro/sars-surveillance-bioinf.png" alt="drawing" width="600"/>
<small>Main steps to be done for bioinformatics step of SARS-CoV-2 surveillance</small>
</span>
<span class="fragment" data-fragment-index="0">

#### Galaxy effort

<img src="img/intro/galaxy-analysis.jpg" alt="drawing" width="600"/>
<small>Source: Maier et al., 2021</small>

<span class="fragment" data-fragment-index="0">

<div style="text-align: left">

#### Galaxy effort

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
<span class="fragment fade-out" data-fragment-index="0">
<img src="img/intro/ww-process.png" alt="drawing" width="800"/>
<small>Clinical surveillance vs Wastewater surveillance</small>
</span>
<span class="fragment" data-fragment-index="0">

#### Galaxy effort

<div style="text-align: left">

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
</div>

</span>
</div>

------
<span class="menu-title" style="display: none">TGS technologies: PacBio</span>

### TGS technologies: PacBio

<img src="img/pacbio.png" alt="drawing" width="750"/>
<small>Average read length between 20 kb and 30 kb. Low error rate (99.9%).</small>

---

<span class="menu-title" style="display: none">Information storage</span>

## Information storage

------

<span class="menu-title" style="display: none">File formats: FASTQ</span>

### Information storage: FASTQ datatype

<img src="img/FASTQ_format.png" alt="drawing"/>

------

<span class="menu-title" style="display: none">File formats: Phred score</span>

### Information storage: Phred quality score

<div class="r-stack">
<span class="fragment fade-out" data-fragment-index="0">

<pre><code data-trim data-noescape >
@ERR4760040.1 MN00415:74:FREIBURG:1
TATAGCTCGCAAATCGTATCAGCAGATGTAATCAGGTAATGAAGTAGTTCTAGTTCTAGTTCTA
+
&%%)'/5516:;-,*&,)+1.-3(+-)%&+623196366-+-')*029==*029==*029==*0
</code></pre>

<div style="text-align: left">

Phred quality score is used to indicate the measure of base quality in DNA/RNA sequencing.<br>

</div>

$$
Q = -10\log_{10}p \rightarrow p = 10^{\frac{-Q}{10}}
$$

<br><small>*p: error probability associated with any given basecall*</small><br>
<small>*Q: quality score, encoded in ASCII characters*</small>

</span>
<span class="fragment current-visible" data-fragment-index="0">

<img src="img/per_base_quality_02.png" alt="drawing"  width="700"/>

</span>
<span class="fragment">

<img src="img/per_base_quality.png" alt="drawing"  width="700"/>

</span>
</div>

------

<span class="menu-title" style="display: none">Information storage: SAM/BAM datatype</span>

### Information storage
#### SAM/BAM datatype

<br>

<img src="img/sam.png" alt="drawing"/>

---

<span class="menu-title" style="display: none">Applications of sequencing technologies</span>

## Applications of sequencing technologies

------

<span class="menu-title" style="display: none">Genome assembly</span>

### Genome assembly

<div class="r-stack">
<span class="fragment fade-out" data-fragment-index="0">
<img src="img/dna_structure.jpg" alt="drawing" width="1000"/>
<p style="font-size:14px;">Source: https://www.genome.gov</p>    
</span>
<span class="fragment" data-fragment-index="0">
<img src="img/genome_assembly.png" alt="drawing" width="1000"/>
</span>
</div>

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