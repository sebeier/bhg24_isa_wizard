---
title: 'BioHackGermany24 report: User-friendly ISA-based metadata annotation of life science experiments with ISA Wizard'
title_short: 'BioHackGermany24 project #8: ISA Wizard'
tags:
  - FAIR
  - ISA
  - MIAPPE
  - svelte
  - Research Data Management
  - ENA
authors:
  - name: Sebastian Beier
    orcid: 0000-0002-2177-8781
    affiliation: 1
  - name: Patrick König
    orcid: 0000-0002-8948-6793
    affiliation: 2
affiliations:
  - name: Institute of Bio- and Geosciences (IBG-4 Bioinformatics), Bioeconomy Science Center (BioSC), CEPLAS, Forschungszentrum Jülich GmbH, 52425 Jülich, Germany
    index: 1
  - name: Leibniz Institute for Plant Genetics and Crop Plant Research (IPK) Gatersleben, Germany
    index: 2
date: 19 December 2024
cito-bibliography: paper.bib
event: BHG24
biohackathon_name: "BioHackathon Germany 2024"
biohackathon_url:   "https://www.denbi.de/de-nbi-events-archive/1678-biohackathon-germany-3/"
biohackathon_location: "Kassel, Germany, 2024"
group: Project 8
# URL to project git repo --- should contain the actual paper.md:
git_url: https://github.com/sebeier/bhg24_isa_wizard
# This is the short authors description that is used at the
# bottom of the generated paper (typically the first two authors):
authors_short: Beier & König
---


# Introduction

As a contribution to BioHackathon Germany 2024, the following report details the work conducted during that event for project 8: User-friendly ISA-based metadata annotation of life science experiments with ISA Wizard.

The Investigation-Study-Assay (ISA) framework [@citesAsAuthority:Rocca_Serra2010] has become an essential tool for managing the increasingly diverse and complex metadata associated with life science, environmental, and biomedical experiments. By structuring metadata around three core components—Investigation (the overarching research context), Study (individual research units), and Assay (analytical measurements)—the ISA framework ensures that experimental data is described in a way that promotes reproducibility and reusability. To this end, the ISA framework provides support for various serialisation formats, including tabular ISA-Tab, ISA-JSON, and RDF.

However, while the ISA framework's flexibility and expressiveness are powerful tools, its inherent complexity poses a significant barrier to non-experts. For researchers and data stewards lacking familiarity with the ISA data model, manual creation of ISA-JSON or ISA-Tab files is both prone to errors and impractical, particularly for large-scale or intricate experiments. This underscores the necessity for user-friendly tools that facilitate metadata ingestion and shield users from the complexity of the data model.

To address these challenges, we introduce the ISA Wizard, a tool designed to simplify the metadata creation process through a questionnaire-based workflow. The ISA Wizard empowers researchers and data stewards to generate accurate and standardised ISA metadata without needing in-depth technical expertise and domain knowledge about the metadata model. By abstracting much of the ISA framework's complexity, the ISA Wizard enhances accessibility while maintaining the richness and precision required for metadata description.

## Abstract

To guarantee that the results data of life science experiments align with the FAIR guidelines, proper metadata annotation of the experimental outcomes is crucial. The widely accepted metadata annotation format for this field is the ISA framework. However, achieving FAIR-compliant annotation of life science experiments is currently hindered by several challenges. The manual generation of ISA-compliant metadata is labor-intensive and prone to errors due to the complexity of ISA itself and the heterogeneous nature of the datasets derived from experiments. Additionally, researchers conducting life science related experiments often lack expertise in utilizing metadata schemas and related ontology concepts. Existing software libraries for the programmatic generation of ISA-compliant metadata are not easily usable by most researchers withoutsignificant programming skills and a deep understanding of ISA and its serialization formats ISA-Tab and ISA-JSON. Existing software with graphical user interfaces for these application areas are difficult to use without domain-specific expert knowledge.

To address these issues, we are developing an intuitive and user-friendly tool called “ISA-Wizard”, a domain-agnostic successor to the MIAPPE-Wizard [@citesAsAuthority:miappewizard]. This web application can assist users in creating ISA-compliant metadata for the resulting datasets of their experiments. The ISA wizard provides a step-by-step questionnaire-based process for data entry with content recommendations and ontology term suggestions. Through comprehensive JSON-based configuration features it will ensure adherence to ISA-compliance and domain-specific minimal information checklists. Users are able to export and save the generated metadata files as ISA-JSON. We will also offer the capability to generate and publish FAIR Digital Objects (FDOs) by leveraging the ARC-concept of the NFDI consortium DataPLANT and their PLANTdataHUB infrastructure [@citesAsAuthority:Weil2023] by using their software libraries and REST APIs.

During BioHackathon Germany we wanted to find collaborators from various life science domains to create domain-specific and experiment-specific configuration files for ISA Wizard instances that could serve as configuration receipts and proof of concept of the generic capabilities of the wizard. By developing a user-friendly web application with interoperability features, we aimed to promote the adoption of FAIR principles and enhance data accessibility and reusability in the life science communities within de.NBI, ELIXIR, NFDIs and beyond.

## Goals and Requirements during the BioHackathon

The BioHackathon project concentrated on the advancement of the ISA Wizard's capabilities through the establishment of specific objectives, namely:

* **Development of a Configuration Manager**: The creation of a graphical user interface (GUI) for the management of ISA Wizard configuration files, thereby facilitating the customisation of metadata ingestion workflows.
* **Expansion of Questionnaire Coverage**: The development of new, domain-specific questionnaires designed to capture experimental metadata across various life science domains.

In order to contribute effectively to these objectives, participants were required to meet the following requirements:

* **Mandatory Knowledge**: Familiarity with minimum information standards and checklists as well as a foundational understanding of the ISA framework and its concepts.
* **Optional Skills**: Experience with JavaScript and HTML development was advantageous but not essential.

# Results

During the BioHackathon, the limited availability of participants (two contributors) necessitated a reassessment and adjustment of the original project goals. 

## Deviation from the defined Goals

* **Configuration Manager for ISA Wizard Configuration Files**:
Initially aimed at creating a GUI-based manager for configuration files, this goal was deemed too complex to implement within the constraints of the BioHackathon. Instead, focus shifted to addressing urgent bug fixes that directly enhanced the functionality of the ISA Wizard.

* **Development of New Questionnaires**:
Two new questionnaires were successfully added to support ENA [@citesAsAuthority:10.1093/nar/gkae975] Sequencing Experiments:
    * A default configuration suitable for a broad range of sequencing experiments corresponding to the `ENA Default Checklist`.
    * A specialized configuration for plant-specific sequencing experiments corresponding for the `ENA Plant Sample Checklist`.
    * New logic was introduced to display Parameter Sets and multiple Protocol Sets, allowing for more nuanced metadata descriptions.

* **Conceptual Design for Template Spreadsheet Integration**:
A conceptual framework for enabling configurable spreadsheet template download and upload was discussed. This feature was not implemented but in the future will be helpful to custom spreadsheets collecting all the necessary metadata information.

* **Bug Fixes and Minor Enhancements**:
Addressing existing bugs and implementing smaller enhancements improved the overall stability and usability of the ISA Wizard.

# Discussion

The development of the ISA Wizard has not yet been fully completed with regard to the minimum features required for a usable software. The integration of ontology terms and the upload of study- and assay-related data like e.g. sample sheets or measurement results is only partially implemented and needs a stronger focus of implementation efforts in future hackathons. 

Regarding the feature domain of ontology annotation of metadata, there is the idea of developing a universal widget for ontology annotation, which offers a search function for ontology terms based on the APIs provided by "Terminology Services for NFDI" (TS4NFDI, https://base4nfdi.de/projects/ts4nfdi).

For the feature domain of uploading metadata in tabular form (e.g. CSV, TSV or Excel files), there is the idea of implementing a template-based mechanism. The user would download a table template containing named column headers, fill it with their own metadata as rows and then upload it into the ISA Wizard. The ISA Wizard would then automatically insert this uploaded metadata within the internal object hierarchy of the ISA data model.

For the future, it would be important to develop further questionnaires for different life science domains and to test the ISA Wizard concept with them regarding usability for the users and correctness of the output.

github repository: https://github.com/IPK-BIT/isa-wizard/

## Acknowledgements

This work was funded by ELIXIR, the research infrastructure for life-science data and by the Federal Government of Germany and the county of North Rhine-Westphalia (de.NBI - the German Network for Bioinformatics Infrastructure).

## References
