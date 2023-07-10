---
title: 'BioHackCloud: hogehoge'
title_short: 'BioHackCloud 2023'
tags:
  - Cloud computing
  - FAIR cloud
  - Common Workflow Language
authors:
  - name: Tazro Ohta
    orcid: 0000-0003-3777-5945
    affiliation: 1
  - name: Michael R. Crusoe
    orcid: 0000-0002-2961-9670
    affiliation: 2
  - name: Tomoya Tanjo
    orcid: 0000-0002-4421-9659
    affiliation: 3
  - name: Yui Asano
    orcid: 
    affiliation: 4
  - name: Anton Zhuravlev
    orcid: 
    affiliation: 5
  - name: Teemu Kataja
    orcid: 0009-0001-1434-0415
    affiliation: 6
  - name: Hirotaka Suetake
    orcid: 0000-0003-2765-0049
    affiliation: 7
  - name: Manabu Ishii
    orcid: 0000-0002-5843-4712
    affiliation: 8
  - name: Alex Kanitz
    orcid: 0000-0002-3468-0652
    affiliation: [9, 10]
  - name: 
    orcid:
    affiliation: 
  - name: 
    orcid:
    affiliation: 
    
affiliations:
  - name: Institute for Advanced Academic Research, Chiba University
    index: 1
  - name: ELIXIR-Germany (via FZ Jülich); VU Amsterdam
    index: 2
  - name: Bioinformation and DDBJ Center
    index: 3
  - name: Swallow Design Studio
    index: 4
  - name: PENQE Inc.
    index: 5
  - name: CSC - IT Center for Science Ltd.; ELIXIR-FI
    index: 6
  - name: Sator, Inc.
    index: 7
  - name: Genome Analytics Japan, Inc.
    index: 8
  - name: Biozentrum, University of Basel, Switzerland
    index: 9
  - name: Swiss Institute of Bioinformatics, Lausanne, Switzerland
    index: 10
date: 30 June 2023
cito-bibliography: paper.bib
event: BH23JP
biohackathon_name: "BioHackathon Japan 2023"
biohackathon_url:   "https://2023.biohackathon.org/"
biohackathon_location: "Kagawa, Japan, 2023"
group: R4
# URL to project git repo --- should contain the actual paper.md:
git_url: https://github.com/biohackathon-japan/bh23-biohackcloud
# This is the short authors description that is used at the
# bottom of the generated paper (typically the first two authors):
authors_short: First Author \emph{et al.}
---

# Background

The highly collaborative, spontaenous and international nature of BioHackathon events can make it difficult to effectively work together on problems that require computing or storage resources that exceed those of most laptops. As BioHackathon organizers typically procure remote venues to foster more intensive collaboration and minimize distractions, central compute facilities for participants are generally not available. And while many participants have access to high performance/throughput computing (HPC/HTC) clusters or cloud environments, rarely can these be accessed by multiple contributors to a project.

At the same time, multiple efforts focusing on the provisioning of bespoke cloud infrastructures for bioinformaticians and the development of high-quality tools and workflows that can be run in the cloud, are typically featured at every BioHackathon event (e.g., see [ADD REFS: https://doi.org/10.37044/osf.io/gbt8p, https://doi.org/10.37044/osf.io/2z6nu, https://doi.org/10.37044/osf.io/k8znb]). The authors therefore envisioned that gap in available compute resources could be filled by a dedicated "BioHackCloud" environment that serves as an entry point for the access of various cloud infrastructures made available to BioHackathon participants at future events, as well as the provisioning of expert support in preparing tools, workflows and data to make it ready for analysis in the cloud and the rich annotation of results according to FAIR [ADD REF] principles.

Importantly, many such cloud infrastructures, such as Sapporo [ADD REF], Galaxy [ADD REF] and the ELIXIR Cloud [ADD REF], which frequently feature in BioHackathon events, make heavy use of a set of community standards developed by the non-profit standard setting organization Global Alliance for Genomics and Health (GA4GH) [ADD REF]. This offers the potential for a future integration of these instructures, and we believe that a BioHackCloud could be an important driver for this process.

Here, we report on the first efforts to kick off the BioHackCloud. In particular, we have prepared a survey to learn more about potential use cases for the cloud, as well as a landing page [ADD REF; https://biohack.cloud]. We have also worked on improving ELIXIR Cloud documentation [ADD REF; https://elixir-cloud-aai.github.io/], the development of a frontend component for the execution of workflows via the GA4GH Workflow Execution Service (WES) [ADD REF] standard, and 
- we helped people who has an issue with workflows (Michael)

# Outcomes

## BioHackCloud Design

In the long term, we envision the BioHackCloud to provide BioHackathon participants with seamless access to a multicloud computing environment that integrates individual national, regional or global clouds, such as those provided by DBCLS (Sapporo; [ADD REF]), ELIXIR Germany (de.NBI; [ADD REF]), the ELIXIR Cloud [ADD REF], or Galaxy [ADD REF] [FIG 1]. This integration will be facilitated by a set of community standards that all of the individual clouds are increasingly adopting, such as the "GA4GH Cloud APIs" for workflow exectution (Workflow Execution Service API; WES [ADD REF]), task execution (Task Execution Service API; TES [ADD REF]), the data access (Data Repository Service API; DRS [ADD REF]) and workflow and tool access (Tool Registry Service API; TRS [ADD REF]), as well as RO-Crates [ADD REF] for the packaging and semantic annotation of research artifacts, along with relevant profiles for tracing task and workflow execution [ADD REF for Workflow Run RO-Crates].

[FIG 1]

Figure 1: Long-term vision for BioHackCloud. Various national, regional and global clouds will be integrated through a layer of common community standards, thus providing a seamless user experience for BioHackathon participants.

However, as the individual cloud environments are still in different states of maturity and common access control policies are largely lacking, especially with regard to the use of sensitive data, provisioning a fully integrated multicloud experience (i.e., a single-sign on web application that supports through the same interface) is currently out of reach. So while we will be steadily working towards this goal during and in between BioHackathon events, for the time being we will the BioHackCloud will serve as a portal that lists specific use cases together with the documentation, tutorials and examples to realize these use cases through the different individual clouds. If multiple clouds support a given use case, users can then choose the one that works best for them (or which they have access to). 

The required compute and storage resources for BioHackathon projects will be provided by institutional sponsors, for example compute centers at the DBCLS or at different ELIXIR Nodes, as well as industry partners. However, as resources will be limited, a fair use policy will be enacted to ensure that all participants have a chance to make use of the available resources.

Only free and open source software [ADD REF] will be integrated into the BioHackCloud. Also, any code and documentation specifically written for the BioHackCloud, will be made publicly available under permissive licenses. In the spirit of a "FAIR [ADD REF] infrastrucutre", all integrated service instances will be recorded in a richly annotated service registry, thus facilitating their disoverability and accessibility.

An initial version of the BioHackCloud portal was implemented [ADD REF to GitHub] by YA, AZ, TO and AK as a static web site and deployed at [https://biohack.cloud/; ADD REF] [FIG 2].

[FIG. 2: ADD SCREENSHOT]

Figure 2: The BioHackCloud portal. Screenshot of the landing page.

Next to finding background information on the BioHackCloud ("About"), visitors can submit use cases ("Submit use case"), join the BioHackCloud team ("Contribute"). In the future, they will be able to find out how to realize different use cases ("Docs") and find out about the institutions sponsoring the BioHackCloud ("Sponsors").

During the BioHackathon, AK also added initial drafts for user and administrator guides [ADD REFS TO PRS] for the ELIXIR Cloud Documentation Hub [ADD REF]. 

### Potential use cases

Apart from being able to handle the execution indivdual tasks with large data volumes and high compute performance needs, cloud environments are, also particularly well suited for the more complex use cases that bioinformaticians typically face, such as the execution of computational analysis workflows, interactive exploratory analyses and the sharing and processing of sensitive data. In addition, cloud environments enable certain and increasingly relevant use cases that are hard or even impossible to realize in their absence, such as federated analytics and federated learning.

To better understand the specific use cases of the BioHackathon community, AK has created a survey [ADD REF] through which BioHackathon participants can select one or more compute and data use cases from a list of predefined entries or add their own use case. In addition, participants to describe how current and past projects could benefit or might have benefited from a cloud infrastructure being available during BioHackathon events. At the time of writing, the number of responses is still too low to draw strong conclusions. However, seven out of eight respondents expressed a need for better data sharing options.

### BHCloud app: Neko-punch

(Taz and Hiro will write this)

[sapporo\-wes/neko\-punch: An execution interface, designed as a web component, for the effortless execution of workflows via GA4GH WES API](https://github.com/sapporo-wes/neko-punch)


## Supporting activities

### CWL updates (MRC, TT, MI, TK)

<!-- We've been asked to keep this to one paragraph. -->
MRC launched a new project to translate the CWL User Guide into Japanese, using the free localization platform «[Weblate](https://weblate.org/en/)» ([Preview](https://common-workflow-languageuser-guide.readthedocs.io/ja/latest/)) ([Contribute](https://hosted.weblate.org/projects/commonwl/user-guide/ja/)). TK & MRC wrote [new documentation](https://github.com/CSCfi/csc-user-guide/pull/1711) for running `toil-cwl-runner` working on the CSC (Finland) "Puhti" cluster. Related to [R2: microbiome](https://docs.google.com/presentation/d/15qg1ZS2UiV4G3VZvOm1OnCotdZnkTH8Q9_AQ2pSQYhY/edit#slide=id.g25614fffa52_0_263), MI wrote [new documentation](https://github.com/nigyta/bact_genome/pull/4) for running DFAST and DFASTQC with `toil-cwl-runner` at HPC (mainly NIG). MRC reviewed & merged contributions to the CWL user guide ([1](https://github.com/common-workflow-language/user_guide/pull/404), [2](https://github.com/common-workflow-language/user_guide/pull/402), [3](https://github.com/common-workflow-language/user_guide/pull/401), [4](https://github.com/common-workflow-language/user_guide/pull/408), [5](https://github.com/common-workflow-language/user_guide/pull/405)). TT & MRC worked on the proposed changes to versions 1.2.1 and 1.3 of the CWL standards ([1](https://github.com/common-workflow-language/schema_salad/pull/711), [2](https://github.com/common-workflow-language/cwltool/pull/1868)). MI provides the idea of these changes for his workflows for [R2: microbiome](https://docs.google.com/presentation/d/15qg1ZS2UiV4G3VZvOm1OnCotdZnkTH8Q9_AQ2pSQYhY/edit#slide=id.g25614fffa52_0_263). MRC released new version of the CWL reference runner to [PyPI](https://pypi.org/project/cwltool/3.1.20230624081518/) & [Conda](https://github.com/conda-forge/cwltool-feedstock/pull/143). MRC and MI delivered a CWL lecture and interactive live coding session ([slides](https://tinyurl.com/BioHackJP23-CWL)).

### Snakemake Ecosystem updates
- MI described to [R2: Microbial strains](https://docs.google.com/presentation/d/15qg1ZS2UiV4G3VZvOm1OnCotdZnkTH8Q9_AQ2pSQYhY/edit#slide=id.g25614fffa52_0_191), how to read snakemake file and execution tips.

# Future work

- BioHackCloud future (Alex)
- WES App (Taz)
- CWL 1.3 will have workflow-step loops; lets see how this helps ML/AI workflows (Michael)


## Acknowledgements



## References
