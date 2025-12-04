# 🧬 Differential DNA Methylation Analysis in T2D Myotubes (GSE166787)

![R](https://img.shields.io/badge/R-4.3.3-blue)
![Bioconductor](https://img.shields.io/badge/Bioconductor-3.17-blueviolet)
![Platform](https://img.shields.io/badge/Platform-Illumina%20450K-orange)
![Dataset](https://img.shields.io/badge/GEO-GSE166787-teal)
![Status](https://img.shields.io/badge/Analysis-Complete-brightgreen)

This repository hosts a complete analysis pipeline for differential DNA methylation between **Type 2 Diabetes (T2D)** and **Normal Glucose Tolerance (NGT)** **human myotube** samples using the **Illumina 450K array**.  
The project focuses on **20 myotube samples** (10 T2D vs 10 NGT) and includes QC, normalization, probe filtering, differential methylation testing, region-level analysis, and functional enrichment.

---

## 📊 Workflow Diagram

<img width="500" height="800" alt="image" src="https://github.com/user-attachments/assets/10e24b5a-8f05-4395-b772-258e96f1de68" />



---

## 🔍 Dataset Summary

- **Platform:** Illumina HumanMethylation450K  
- **Source:** GEO (GSE166787)  
- **Selected for analysis:**  
  - 10 NGT myotubes  
  - 10 T2D myotubes  
- **Focus:** DNA methylation differences in mature muscle cells

---

## 🧪 Analysis Modules

### **1. Raw Data Handling**
- Automatic `SampleSheet.csv` creation  
- IDAT loading via `minfi`  
- Detection P-value QC (samples + probes)

### **2. Preprocessing**
- NOOB normalization  
- SNP filtering  
- Sex chromosome filtering  
- Genome mapping (hg19)

### **3. Exploratory Analysis**
- PCA  
- Beta/M-value distribution plots  

### **4. Differential Methylation (CpGs)**
- Linear modeling with **limma**  
- Moderated statistics  
- ΔBeta calculation  
- Top hyper/hypo CpGs export

### **5. Differentially Methylated Regions (DMRs)**
- Identified via **DMRcate**  
- 34 DMRs detected  
- Region-level ΔBeta  
- Gene annotation

### **6. Functional Enrichment**
- **GREAT** analysis (BP, MF, CC)  
- Bubble plots & top enriched terms exported

---

## 📁 Repository Contents (Detailed)


```
Differential DNA Methylation Analysis in T2D Myotubes (GSE166787)
    |   
    ├── GSE166787_RAW/
    │ ├── *.idat # Raw Illumina 450K IDAT files
    │ ├── SampleSheet.csv # Auto-generated metadata
    │
    ├── GREAT_results/
    │ ├── GREAT_GO_BP.csv # Biological Process enrichments
    │ ├── GREAT_GO_MF.csv # Molecular Function enrichments
    │ ├── GREAT_GO_CC.csv # Cellular Component enrichments
    │
    ├── DMP_all_CpGs.csv # CpG-level limma results
    ├── Top10_hyper_CpGs.csv # Highest ΔBeta (T2D > NGT)
    ├── Top10_hypo_CpGs.csv # Lowest ΔBeta (T2D < NGT)
    │
    ├── DMRs_annotated.csv # Gene-annotated regions
    ├── DMRs_with_mean_deltaBeta.csv # Region-level ΔBeta summaries
    ├── DMRs_final_manual_extraction.csv# Cleaned DMR list
    │
    ├── Volcano_T2D_vs_NGT.png # Volcano plot (CpG-level)
    ├── GO_BP_bubble.png # Biological Process Bubble Plot
    ├── workflow_diagram.png # Analysis workflow diagram
    │
    ├── Methylation_Data_T2D_Script.Rmd # Full analysis pipeline source
    ├── Methylation_Data_T2D_Script.pdf # Pipeline with plots + explanations
    └── README.md
```

---

## ▶ Running the Analysis

You can execute the full analysis using:

- `Methylation_Data_T2D_Script.Rmd`  
or  
- `Methylation_Data_T2D_Script.pdf` (for a documented workflow)

---

## 📬 Contact

For questions or collaboration:  
**Gayatri Samant**<br>
Bioinformatics intern <br>
Vizzhy, Banglore<br>
mail : gayatrisamant05@gmail.com

---
