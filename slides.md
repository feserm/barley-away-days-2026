---
theme: ./themes/slidev-theme-nfdi4plants
title: FAIR and Square
info: |
  Slide deck for the Barley Away Days 2026
transition: fade-out
duration: 15min
license: cc-by
hideInToc: true
addons:
  - rabbit
---

# FAIR and Square
## Letting Research Data Tell the Story of Your Research

---

# Why FAIR by Design

<div class="flex flex-col justify-center items-center">
  <img class="w-1/5" src="/assets/scarytale-undocumented.png"/>
  <span class="text-[#3B8382] font-semibold">The data existed, but could not be re-used despite their best efforts.</span>
  <v-clicks>
   
  - PhD student told to work on unpublished data collected 3 years prior
  - Lots of unclear datasheets, columns, scripts, equipments, settings, etc.
  - Manufacturers of the equipment or data authors did not remember details
  - Data could not be reused
  
  </v-clicks>
</div>

<span class="absolute bottom-8 right-2 italic font-mono text-xs">https://doi.org/10.5281/zenodo.4066679</span>

<!-- 
- Introduction: When a young researcher started on his PhD, he was told to work on unpublished data that had been collected 3 years prior. He received various folders that were full of data. After going through them, he found that there were several datasheets with duplicate names but different contents, scripts that nobody knew what they did or why and column names that where unclear and ambiguous. Moreover, the exact equipment and/or settings used for the experiments where unknown in some cases. Since it had been several years, not even extensive talks with the manufacturers of the used equipment or the data authors could make the data usable. In the end, the data were not able to be re-used.

- Key message: If we adhere to FAIR principles when collecting and organizing data, we save a tremendous amount of time later on and lay the foundation for automation and AI-supported analyses.

- Transition to FAIR principles: But what exactly does FAIR mean in everyday research? Let's take a quick look at the four principles.
-->

---

# FAIR Principles

<div class="flex justify-center"> 
  <img class="w-1/2" src="/assets/FAIR_data_principles.png"/>
</div>

- Provide proper metadata so machines and humans can understand what the data describes and how it may be used
- Metadata, Formats differ between domains (genotyping vs. phenotyping)
- For Plant Phenomics: 
  - [MIAPPE](https://github.com/MIAPPE/MIAPPE) (Minimal Information About a Plant Phenotyping Experiment)
  - [ISA](https://isa-tools.org/) (Investigation / Study / Assay)

<span class="absolute bottom-8 right-2 italic font-mono text-xs">https://doi.org/10.1038/sdata.2016.18</span>

<!-- 
- Short definition: FAIR stands for Findable, Accessible, Interoperable, and Reusable.

- Example: When metadata is properly maintained, machines and humans can understand what the data describes and how it may be used.

- Transition: To ensure that FAIR does not remain merely a theory, we need structures that implement FAIRness technically. One of these is what are known as FAIR Digital Objects – in our case in the form of ARCs.
-->

---

# ARCs as FAIR Digital Objects

<div class="flex space-x-4">
  <img class="w-1/2" src="/assets/orga-principle-folder2process.png"/>
  <div class="flex flex-col justify-between w-1/2">
    <img class="w-7/8 h-fit" src="/assets/ci-cd-cqc.png"/>
    <ul>
      <li>Process graph describing research steps</li>
      <li>Automated validation through CI/CD</li>
      <li>Packaging of research object as RO Crate</li>
      <li>Tool ecosystem to facilitate management of ARCs</li>
    </ul>
  </div>
</div>

<!-- 
- Introduction: An ARC, or Annotated Research Context, is essentially a container that encapsulates data, metadata, and provenance information together in a way that is both machine- and human-readable.

- Example: Every ARC is a FAIR Digital Object and can be automatically checked using CI/CD pipelines – this makes FAIRness verifiable and reproducible.

- Transition to ISA Wizard: One of such tools is the ISA Wizard, which helps to correctly describe the dataset at the time of creation.
-->

--- 
layout: two-cols-header
layoutClass: gap-4
---

# FAIR from the get-go

::left::

<v-switch>
<template #0><img class="w-full border border-black rounded" src="/assets/isa-wizard-protocol.png"/></template>
<template #1><img class="w-full border border-black rounded" src="/assets/isa-wizard-upload.png"/></template>
<template #2><img class="w-full border border-black rounded" src="/assets/isa-wizard-gui.png"/></template>
</v-switch>

::right::
<div class="w-full pb-4 flex justify-between items-center">
  <span class="font-bold text-2xl">ISA Wizard</span>
  <img class="w-24" src="/assets/isa-wizard-logo.png"/>
</div>

- Configurable questionnaire 
- Extendable to domain-specific standards like [MIAPPE](https://github.com/MIAPPE/MIAPPE)
- Description of research experiments
- Linked to PID and Ontlogy Lookup Services
- Automated creation of sample process graph
- Authenticated export to PLANTdataHUB

<!-- 
- Introduction: The ISA Wizard supports researchers in the structured collection of metadata without them having to know the complex ISA structures in detail.

- Example: In phenotyping, it can be configured to automatically query MIAPPE-compliant metadata – exactly what is needed later for FAIRness.

- Transition: Once the data has been collected, it needs to be integrated into a larger FAIR ecosystem – and that's exactly what BrAPI2ARC does.
-->

--- 
layout: two-cols-header
layoutClass: gap-4
---

# How to integrate GridScore

::left::

- Import ARC into MIRA Dashboard
- Import Observation Variables e.g. from Cropontology
- Import trial in GridScore using Breeding API
- Use GridScore as usual
- Export trial to MIRA using Breeding API
- Automatic creation of new version in PLANTdataHUB

::right::

<v-switch>
<template #0><img class="w-full border border-black rounded" src="/assets/brapi2arc-arc-import.png"/></template>
<template #1><img class="w-full border border-black rounded" src="/assets/brapi2arc-co-import.png"/></template>
<template #2><img class="w-full border border-black rounded" src="/assets/brapi2arc-gridscore-import.png"/></template>
<template #3><img class="w-full border border-black rounded" src="/assets/brapi2arc-gridscore-scoring.png"/></template>
<template #4><img class="w-full border border-black rounded" src="/assets/brapi2arc-gridscore-detail.png"/></template>
<template #5><img class="w-full border border-black rounded" src="/assets/brapi2arc-gridscore-export.png"/></template>
<template #6><img class="w-full border border-black rounded" src="/assets/brapi2arc-datahub-view.png"/></template>
<template #7><img class="w-full border border-black rounded" src="/assets/brapi2arc-datahub-df.png"/></template>
</v-switch>

<!-- 
- Introduction: BrAPI2ARC connects ARC structures with BrAPI-based tools such as GridScore to transfer data directly from the survey into the FAIR context.

- Example: At the same time, external sources such as CropOntology can be integrated for trait definition – this saves manual work and ensures consistency.

- Completion of the workflow: Once the data is complete, the ARC can be exported or versioned directly into PLANTdataHUB. This ensures that the entire process remains FAIR and traceable.

- Transition: This closes the loop – from data collection to FAIR validation. And that is precisely the basis for automation and AI readiness.
 -->

--- 
layout: two-cols-header
layoutClass: gap-4
---

# Plant Data Commons

::left:: 

- Network of interoperable services allows the creation of datasets that are FAIR by design
  - **ISA Wizard** collects and structures metadata
  - **MIRA** integrates BrAPI-enabled tools like **GridScore**
  - **CI/CD** performs automatic validation
- Creation of FDOs can be as simply as using the right tools
- Evolving your dataset through versions helps others to understand what you did and why

::right::

<img class="w-full ml-auto" src="/assets/datamesh-plantphenomics.drawio.png"/>

<!-- 
- Consolidation: All of the tools presented are interconnected: ISA Wizard collects structured information, BrAPI2ARC integrates it into an ARC, and CI/CD performs automatic FAIR checks.

- Motivational anchor: This creates data that can be actively reused—not just stored—by people, machines, and AI systems.

- Transition to conclusion: Let's summarize the key ideas once again to conclude.
 -->

---

# Take Home Messages


1. FAIR RDM doesn't start in the repository, but in the lab
1. Automation and AI readiness aren't just a vision for the future but come from consistently structured data
1. **Immutable yet evolving**: ARCs can help you tell the story of your research data

<div class="flex justify-between mt-8">

<div>

- Links and Repositories:
  - [ISA Wizard](https://github.com/ipk-bit/isa-wizard)
  - [GridScore Integration](https://doi.org/10.5281/zenodo.13740519)
  - [ARC](https://arc-rdm.org)
  - [Plant Data Commons](https://plant-commons.ipk-gatersleben.de)

</div>

<img class="w-1/2" src="/assets/git-fairification.png"/>
</div>

<!-- 
- Key messages: FAIR data management doesn't start in the archive, but in the lab. Automation and AI readiness aren't just a vision for the future—they come from consistently structured data.

- Conclusion: If you'd like to learn more about the tools or try out ARCs for yourself, I'd be happy to chat after the presentation.
-->

---

# Thank you

<div class="grid grid-cols-3">

<div>

- Uwe Scholz
- Daniel Arend
- Patrick König
- Dennis Psaroudakis

</div>
<div>

- Timo Mühlhaus
- Heinrich Lukas Weil
- Jonathan Bauer
- Kevin Schneider

</div>
<div>

- Paul Shaw
- Sebastian Raubach
- and many more

</div>
</div>

<div class="mt-8 grid grid-cols-2 items-center">
  <img class="w-1/2" src="/assets/dfg-funded.png">
  <img class="w-1/2" src="/assets/nfdi_rgb_Wortmarke_Zusatz_quer.png" />
  <img class="w-1/2" src="/assets/NFDI_4_Biodiversity___Logo_Positiv_Kopie.png"/>
  <img class="w-1/2" src="/assets/dataplant.png"/>
</div>
