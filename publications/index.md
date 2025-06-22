---
layout: single
classes: wide
author_profile: true
title: "Publications"
---
A full list of my publications is available on my [Google Scholar](https://scholar.google.com/citations?user=dKmUzp4AAAAJ&hl=zh-CN) profile.

<input type="text" id="searchBox" placeholder="Search by year or title..." onkeyup="searchPublications()" style="width:100%;padding:10px;margin-bottom:20px;font-size:16px;">

<div id="publicationContent" markdown="1">

## 2025

<img src="https://raw.githubusercontent.com/qiaw99/qiaw99.github.io/main/figures/quantization.png?raw=true" width="80px" align="right">

### 🔍Through a Compressed Lens: Investigating the Impact of Quantization on LLM Explainability and Interpretability
**Qianli Wang**, Mingyang Wang, Nils Feldhus, Simon Ostermann, Yuan Cao, Hinrich Schütze, Sebastian Möller, Vera Schmitt <br>
_In submission_<br>
[arXiv](https://arxiv.org/abs/2505.13963) | _(Code will be publicly available once the paper is published)_

### Truth or Twist? Optimal Model Selection for Reliable Label Flipping Evaluation in LLM-based Counterfactuals
**Qianli Wang**, Van Bach Nguyen, Nils Feldhus, Luis Felipe Villa-Arenas, Christin Seifert, Sebastian Möller, Vera Schmitt <br>
_In submission_<br>
[arXiv](https://arxiv.org/abs/2505.13972) | _(Code will be publicly available once the paper is published)_

<img src="https://raw.githubusercontent.com/qiaw99/qiaw99.github.io/main/figures/compass.png?raw=true" width="60px" align="right">

### Multilingual Datasets for Custom Input Extraction and Explanation Requests Parsing in Conversational XAI Systems
**Qianli Wang**, Tatiana Anikina, Nils Feldhus, Simon Ostermann, Fedor Splitt, Jiaao Li, Yoana Tsoneva, Sebastian Möller, Vera Schmitt <br>
_In submission_<br>
_(Code will be publicly available once the paper is published)_

<img src="https://raw.githubusercontent.com/qiaw99/qiaw99.github.io/main/figures/fitcf_logo.png?raw=true" width="125px" align="right">

### FitCF: A Framework for Automatic Feature Importance-guided Counterfactual Example Generation
**Qianli Wang**, Nils Feldhus, Simon Ostermann, Luis Felipe Villa-Arenas, Sebastian Möller, Vera Schmitt <br>
_ACL 2025 Findings_<br>
ACL Anthology will be available in July | [arXiv](https://arxiv.org/abs/2501.00777) | [GitHub](https://github.com/qiaw99/FitCF)

### Cross-Refine: Improving Natural Language Explanation Generation by Learning in Tandem
**Qianli Wang**, Tatiana Anikina, Nils Feldhus, Simon Ostermann, Sebastian Möller, and Vera Schmitt<br>
*COLING 2025*<br>
[ACL Anthology](https://aclanthology.org/2025.coling-main.77/) | [arXiv](https://arxiv.org/abs/2409.07123) | [GitHub](https://github.com/qiaw99/Cross-Refine)

## 2024
### AnchorAlign: Self-Explanations Enhancement via Anchored Alignment
Luis Felipe Villa-Arenas, Ata Nizamoglu, **Qianli Wang**, Sebastian Möller, and Vera Schmitt<br>
*In submission*<br>
[arXiv](https://arxiv.org/abs/2410.13216) | [GitHub](https://github.com/felipevillaarenas/anchored-alignment)

### CoXQL: A Dataset for Explanation Request Parsing in Conversational XAI Systems
**Qianli Wang**, Tatiana Anikina, Nils Feldhus, Simon Ostermann, and Sebastian Möller <br>
*EMNLP 2024 Findings*  <br>
[ACL Anthology](https://aclanthology.org/2024.findings-emnlp.76/) | [arXiv](https://arxiv.org/abs/2406.08101) | [GitHub](https://github.com/DFKI-NLP/CoXQL)  

<img src="https://raw.githubusercontent.com/qiaw99/qiaw99.github.io/main/figures/InstruX_Logo.png?raw=true" width="125px" align="right"> 

### Towards Modeling and Evaluating Instructional Explanations in Teacher-Student Dialogues
Nils Feldhus, Aliki Anagnostopoulou, **Qianli Wang**, Milad Alshomary, Henning Wachsmuth, Daniel Sonntag, and Sebastian Möller  
*ACM GoodIT 2024 (Work in Progress track)*  
[ACM Digital Library](https://dl.acm.org/doi/10.1145/3677525.3678665) | [OpenReview (previous version submitted to ARR)](https://openreview.net/forum?id=mHgNzfiApQ)


<img src="https://raw.githubusercontent.com/qiaw99/qiaw99.github.io/main/figures/LLMCheckup_Logo.png?raw=true" width="125px" align="right"> 

### LLMCheckup: Conversational Examination of Large Language Models via Interpretability Tools and Self-Explanations
**Qianli Wang**, Tatiana Anikina, Nils Feldhus, Josef van Genabith, Leonhard Hennig, and Sebastian Möller  
*NAACL 2024 Workshop on Bridging Human-Computer Interaction and Natural Language Processing (HCI+NLP)*  
[ACL Anthology](https://aclanthology.org/2024.hcinlp-1.9) | [arXiv](https://arxiv.org/abs/2401.12576) | [GitHub](https://github.com/DFKI-NLP/LLMCheckup)  



## 2023

<a href="https://aclanthology.org/2023.findings-emnlp.359/"><img src="https://raw.githubusercontent.com/nfelnlp/nfelnlp.github.io/main/figures/InterroLang_Logo.png?raw=true" width="150px" align="right"></a>  
### InterroLang: Exploring NLP Models and Datasets through Dialogue-based Explanations
Nils Feldhus, **Qianli Wang**, Tatiana Anikina, Sahil Chopra, Cennet Oguz, and Sebastian Möller  
*EMNLP 2023 Findings* & *[BlackboxNLP](https://blackboxnlp.github.io/) Workshop*  
[ACL Anthology](https://aclanthology.org/2023.findings-emnlp.359/) | [arXiv](https://arxiv.org/abs/2310.05592) | [GitHub](https://github.com/DFKI-NLP/InterroLang)  

</div>

function searchPublications() {
  const term = document.getElementById("searchBox").value.toLowerCase();
  const items = document.querySelectorAll("#publicationContent .publication-item");
  items.forEach(item => {
    const text = item.textContent.toLowerCase();
    item.style.display = text.includes(term) ? "" : "none";
  });
}