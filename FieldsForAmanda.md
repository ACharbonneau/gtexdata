---
pdf_options:
  format: Letter
---

# Things & Fields Rick Needs Help With

Here's a list of the things that I know I don't know. There's
certainly more that I don't, but I'm willing to take a crack it to
find out.

This is based on the description document I wrote so you should be
able to check that for more context. Actually, you should read that first.


## Things (Proper Nouns)

The Level 1 C2M2 includes tables to describe the following things (entities), and the relationships between them.

 * Namespaces
 * Project
 * File
 * Subject
 * Biosample
 * Collection

### Project

Should there be a single GTEx project, or do we treat studies or other
things as subprojects?

### File

 * **file_format** An EDAM CV term ID identifying the digital format of this file (e.g. TSV or FASTQ)
 * **data_type** An EDAM CV term ID identifying the type of information stored in this file (e.g. RNA sequence reads)

### Subject

 * **granularity** A CFDE CV term categorizing this subject by multiplicity (see Subject Granularity under Controlled Vocabularies). One of
  - single organism
  - symbiont system
  - host-pathogen system
  - microbiome
  - cell line
  - synthetic

### Biosample

There was a conversation with Daniel about LINCS because it wasn't
clear how to represent a biosample. We can say a file describes a
subject, but the only way to have an assay type or anatomy reference
is through biosample. So if don't have a real biosample to catalog, we
might need to use a virtual one.

 * **assay_type** An OBI CV term ID describing the type of material represented by this biosample
 * **anatomy** An UBERON CV term ID used to locate the origin of this biosample within the physiology of its source or host organism

### Collection

This is where we put datasets or cohorts. I'll need a suggestion on
how to define those groups.

## Relationships

### Subject Role and Taxonomy

I'm not sure what this is all about.

A table linking a subject, a subject_role (a named organism-level constituent component of a subject, like 'host', 'pathogen', 'endosymbiont', 'taxon detected inside a microbiome subject', etc.) and a taxonomic label (which is hereby assigned to this particular subject_role within this particular subject)".

#### Attributes

 * **subject**
   - **namespace** The namespaec of the subject
   - **id** The ID of this subject
 * **role** The role assigned to this organism-level constituent component of this subject (see Subject Role under Controlled Vocabularies). One of
   - single organism
   - host
   - symbiont
   - pathogen
   - microbiome taxon
   - cell line ancestor
   - synthetic
 * **taxonomy_id** An NCBI Taxonomy Database ID identifying this taxon
