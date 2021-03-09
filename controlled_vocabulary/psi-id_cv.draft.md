<!-- TO DO:
# do we keep synonyms from PSI-MI CV
# do we keep types of synonyms from PSI-MI CV (alternate, short,...)
# do we define subsets similar to PSI-MI CV
# do we copy whole branches or select only terms useful to us from different branches
# header
# copyright statements
# namespace
# complete missing PMIDs
# change all 14755292 to 31824649, and later to PSI-ID pmid
# define PSI-ID specific term ID's
# check definitions
-->

We need to define a PSI-ID controlled vocabulary, specifically describing aspects of intrinsically disordered proteins and 
IDP experiments. This CV will be used to annotate data captured in the PSI-ID XML schema and elements of the schema. Many 
terms can be taken from the PSI-MI CV, but as these terms are specific for molecular interactions some of them might need 
to be redefined. Also, as the terms of the PSI-MI CV are part of the root term 'molecular interaction', branches of this 
CV need to be copied to the PSI-ID CV to make them IDP specific, using an IDP specific root term and namespace.

Branches from the PSI-MI CV we can use:
- alias type (to describe the type of nomenclature used to describe an object or entity in the PSI-ID XML format)
- attribute name (to describe free text stored as attribute value in the PSI-ID XML format)
- cross-reference type (to describe the type of information a cross-reference in the PSI-ID XML format is pointing to)
- database citation (to name databases used to cross-reference IDP-related data in the PSI-ID XML format)
- experimental preparation (to describe experimental treatment and status of experimental constructs analysed in IDP experiments in the PSI-ID XML format)
- feature detection method (will we use this in the schema?) (to describe the method used to determine the features of experimental constructs analysed in IDP experiments in the PSI-ID XML format)
# many methods used for feature detection are present in ECO; we can use these?
- feature range status (to describe the resolution of sequence positions of an experimental construct feature in the PSI-ID XML format)
- feature type (to describe the type of feature of an experimental constructs analysed in IDP experiments in the PSI-ID XML format)
- [interaction] confidence (to describe a measure of confidence in a specific structure state or IDP experiment in the PSI-ID XML format)
- [interactor] type (probably only in a later version of the schema, in which more experimental details might be captured, involving molecules other than proteins) (to describe the type of molecule involved in the experiment)
- parameter type (to describe the type of an experimental variable used in the experiment)
- parameter unit (to describe the unit of an experimental variable used in the experiment)
- [participant] identification method (to describe the method used to determine the molecules/experimental constructs used in the experiment)
# many methods used for molecule identification are present in ECO; we can use these?

Branches from the PSI-MI CV we will probably not use (at least not in a first version of the schema):
- biological role
- causal interaction
- cooperative interaction
- curation content
- curation quality
- experimental role
- interaction detection method (we will need to use methods to determine the structure of a protein or protein region, taken from the ECO CV)
- interaction type (we will need to use terms to describe the structure state of a protein or protein region, taken from the IDPO CV)



format-version: 
date: 
saved-by: 
auto-generated-by:
subsetdef: PSI-ID_slim "Subset of PSI-ID"
synonymtypedef: PSI-ID-alternate "Alternate label curated by PSI-ID" EXACT
synonymtypedef: PSI-ID-short "Unique short label curated by PSI-ID" EXACT
default-namespace: PSI-ID
remark: Notes:
remark: Each of the top level terms in this file is the root term of an independent controlled vocabulary
remark: mapping an element of the PSI Intrinsic Disorder XML schema.
remark: coverage: This file collects controlled vocabularies describing different aspects of intrinsically disordered proteins.
remark: publisher: This file is published by the PSI-ID working group, see http://psidev.info/ID
remark: CVversion: 1.0.0
ontology: id or idp or idpo


<!-- ROOT TERM -->

[Term]
id: ID:0000 or IDP:0000 or IDPO:0000 ?
name: intrinsic disorder or intrinsically disordered protein(s) or something with ontology ?
def: "Controlled vocabularies created for intrinsically disordered proteins." [PMID:31824649]
subset: PSI-ID_slim ?
synonym: "id" or "idp" EXACT PSI-ID-short [] ?
created_by: ?
creation_date: ?



<!-- ALIAS TYPE - ROOT TERM FOR NAME ELEMENT ANNOTATION - type and typeAc attributes of idf:alias elements to annotate free text stored as value of these elements -->

[Term]
id: 
name: alias type
def: "Descriptor of the type of nomenclature used to describe an object or an entity." [PMID:31824649]
relationship: part_of ID:0000 ! intrinsically disordered protein

[Term]
id: 
name: synonym
def: "Alternative name or descriptor for an object or an entity." [PMID:31824649]
is_a: ??:xxxx ! alias type

[Term]
id: 
name: author assigned name
def: "Name assigned to an object or entity by the authors within a paper that may differ from the name used in a reference database." [PMID:31824649]
is_a: ??:xxxx ! synonym

[Term]
id: 
name: gene name
def: "The name of a gene." [PMID:31824649]
synonym: "gene" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! synonym

[Term]
id: 
name: gene name synonym
def: "Synonymous name for a gene." [PMID:31824649]
is_a: ??:xxxx ! synonym

[Term]
id: 
name: gene ontology synonym
def: "Synonym as used in Gene Ontology." [PMID:31824649]
synonym: "go synonym" EXACT PSI-ID-short []
is_a: ??:xxxx ! synonym

[Term]
id: 
name: isoform synonym
def: "Synonymous name for an isoform." [PMID:31824649]
is_a: ??:xxxx ! synonym



<!-- ATTRIBUTE NAME - ROOT TERM FOR ATTRIBUTE ELEMENT ANNOTATION - name and nameAc attributes of idf:attribute elements to annotate free text stored as value of idf:attribute elements -->
<!-- in PSI-MI CV there is an additional level of terms between 'attribute name' and the terms actually used as descriptor, to specify to which element an attribute can be associated, e.g. feature attribute name, experiment attribute name, ... -->
<!-- these intermediate level terms are currently not present (except for bibliographic attribute name) in the CV version adopted for IDP, but can be easily inserted if necessary or desired--> 

[Term]
id: 
name: attribute name
def: "Collection of topics describing the free text stored as an attribute value." [PMID:31824649]
relationship: part_of ID:0000 ! intrinsically disordered protein

[Term]
id: 
name: comment
def: "Comment for public view." [PMID:31824649]
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: url
def: "URL/Web address describing an object or entity." [PMID:31824649]
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: caution
def: "Warning about errors or grounds for confusion." [PMID:31824649]
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: experiment description
def: "The experimental text description may include information about host organisms, experimental methods and experimental conditions." [PMID:31824649]
synonym: "exp-description" EXACT PSI-ID-short []
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: experiment modification
def: "Modifications of the standard experimental method described in the CV." [PMID:31824649]
synonym: "exp-modification" EXACT PSI-ID-short []
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: experimental form description
def: "Free text description of all the modifications undergone by a molecule in the context of an an experiment." [PMID:31824649]
synonym: "experimental form" EXACT PSI-ID-short []
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: data-processing
def: "Comments on how the data was processed." [PMID:31824649]
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: isoform-comment
def: "Comments on the isoform of a molecule." [PMID:31824649]
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: antibodies
def: "This annotation topic should contain information about antibodies when specific antibodies (monoclonal or polyclonal raised against specific regions of the proteins or purified in a specific manner) have been used." [PMID:31824649]
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: library-used
def: "This annotation topic will be used to store information about the cDNA library. If a name is available this should be reported along with a short description of the library." [PMID:31824649]
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: feature description
def: "The feature text description may include information about the feature detection method." [PMID:31824649]
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: figure legend
def: "Text pointing to a specific paper figure legend where the experimental evidence for a structure state are to be found." [PMID:31824649]
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: function
def: "Biological function of a molecule or of a molecule region." [PMID:31824649]
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: search-url
def: "Search engine URL associated to CV database terms." [PMID:31824649]
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: disease
def: "A known or demonstrated disease association of a molecule or of a molecule region." [PMID:31824649]
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: pathway
def: "A metabolic or signalling pathway in which a molecule or a molecule region is involved." [PMID:31824649]
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: 3d-structure
def: "Comments on the 3D structure." [PMID:31824649]
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: 3d-work-r-factor
def: "Working R-Factor for the quality of the crystallographic model." [PMID:31824649]
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: 3d-free-r-factor
def: "Free R-Factor for the quality of the crystallographic model." [PMID:31824649]
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: 3d-resolution
def: "Resolution of the 3D structure." [PMID:31824649]
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: checksum
def: "A fixed-size datum calculated (by using a hash function) for a molecular sequence or structure, typically for purposes of error detection or indexing." [PMID:31824649]
synonym: "hashsum" RELATED []
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: resulting sequence
def: "Used to specify the identity of the residue (or residues) introduced by mutation or variant (of child terms). The attribute would be used concurrently with the description provided in the feature name." [PMID:31824649]
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: genomic coordinates
def: "Coordinates of a reference DNA sequence in the genome, providing information about the chromosome name, start and end of the sequence, optionally including the strand as well if it applies." [PMID:31824649]
synonym: "genomic coord" EXACT PSI-ID-short []
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: author-confidence
def: "Confidence classification assigned by the author of the publication to a specific structure state." [PMID:31824649]
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: confidence-mapping
def: "Description of confidence assessment for an experiment or structure state." [PMID:31824649]
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: validation regular expression
def: "Regular Expression used to check the validity of a cross-reference's identifier, generally associated to terms in CV Database." [PMID:31824649]
synonym: "id-validation-regexp" EXACT PSI-ID-short []
is_a: ??:xxxx ! attribute name

[Term]
id: 
name: author submitted
def: "Data directly submitted by the authors to a database prior to publication." [PMID:31824649]
is_a: ??:xxxx ! attribute name

# bibliographic attribute names - to annotate attribute values related to a publication -->

[Term]
id: 
name: bibliographic attribute name
def: "Attributes to specifically annotate a publication." [PMID:31824649]
synonym: "bib attribute" EXACT PSI-ID-short []
synonym: "publication attribute" EXACT []
is_a: ??:xxxx ! attribute name
	 

[Term]
id: 
name: contact-email
def: "E-mail address to contact the author or organisation which has produced the data." [PMID:31824649]
is_a: ??:xxxx ! bibliographic attribute name

[Term]
id: 
name: contact-comment
def: "Free text notes on how to contact the author or organisation which has produced the data." [PMID:31824649]
is_a: ??:xxxx ! bibliographic attribute name

[Term]
id: 
name: author-list
def: "List of authors associated to a publication." [PMID:31824649]
is_a: ??:xxxx ! bibliographic attribute name

[Term]
id: 
name: curation request
def: "Annotation of a published paper which has been externally requested." [PMID:31824649]
is_a: ??:xxxx ! bibliographic attribute name

[Term]
id: 
name: dataset
def: "Targeted curation dataset grouping experiments by topic or dataset origin." [PMID:31824649]
is_a: ??:xxxx ! bibliographic attribute name

[Term]
id: 
name: journal
def: "Name and details of a journal from which a paper has been taken." [PMID:31824649]
is_a: ??:xxxx ! bibliographic attribute name

[Term]
id: 
name: publication year
def: "Year of publication of a paper." [PMID:31824649]
is_a: ??:xxxx ! bibliographic attribute name

[Term]
id: 
name: publication title
def: "Title of the publication." [PMID:31824649]
synonym: "title" EXACT PSI-ID-short []
is_a: ??:xxxx ! bibliographic attribute name



<!-- BIOLOGICAL ROLE - Physiological role of an interactor in a cell or in vivo environment, which is reproduced in the current experiment. -->
<!-- currently we don't use/need this branch -->



<!-- CAUSAL INTERACTION - Binary causative relationships between biological entities. CV terms belonging to this term allow the description of causal interactions using the current PSI-MI schema. -->
<!-- currently we don't use/need this branch -->



<!-- COOPERATIVE INTERACTION - A set of molecular binding events that influence each other either positively or negatively through allostery or pre-assembly. In this context, covalent post-translational modifications are considered as binding events. CV terms that are part of this term allow the description of cooperative interactions using the current PSI-MI schema. -->
<!-- currently we don't use/need this branch -->



<!-- CROSS-REFERENCE TYPE - ROOT TERM FOR XREF ELEMENT ANNOTATION - refType and refTypeAc attributes of idf:dbReference elements to describe the type of information a cross-reference is pointing to -->

[Term]
id: 
name: cross-reference type
def: "Qualifier to describe the type of information a cross-reference is pointing to." [PMID:31824649]
synonym: "refType" EXACT PSI-ID-alternate []
synonym: "xref type" EXACT PSI-ID-short []
relationship: part_of ID:0000 ! intrinsically disordered protein

[Term]
id: 
name: gene product
def: "Reference of a protein object pointing to its genomic or nucleic acid sequence." [PMID:31824649]
is_a: ??:xxxx ! cross-reference type

[Term]
id: 
name: isoform parent sequence reference
def: "Reference to the master sequence from which an isoform has been derived." [PMID:31824649]
synonym: "isoform-parent" EXACT PSI-ID-short []
is_a: ??:xxxx ! cross-reference type

[Term]
id: 
name: cellular component
def: "Cross-reference pointing to a Gene Ontology - 'cellular component' term." [PMID:14681407]
synonym: "component" EXACT PSI-ID-short []
synonym: "go component term" EXACT PSI-ID-alternate []
xref: search-url: "https://www.ebi.ac.uk/QuickGO/term/${ac}"
is_a: ??:xxxx ! cross-reference type

[Term]
id: 
name: molecular function
def: "Cross-reference pointing to a Gene Ontology - 'molecular function' term." [PMID:14681407]
synonym: "function" EXACT PSI-ID-short []
synonym: "go function term" EXACT PSI-ID-alternate []
xref: search-url: "https://www.ebi.ac.uk/QuickGO/term/${ac}"
is_a: ??:xxxx ! cross-reference type

[Term]
id: 
name: biological process
def: "Cross reference pointing to a Gene Ontology - 'cellular process' term." [PMID:14681407]
synonym: "go process term" EXACT PSI-ID-alternate []
synonym: "process" EXACT PSI-ID-short []
xref: search-url: "https://www.ebi.ac.uk/QuickGO/term/${ac}"
is_a: ??:xxxx ! cross-reference type

[Term]
id: 
name: identical object in an external resource
def: "Reference to the corresponding object in another database. Correspondence may be complete or partial." [PMID:31824649]
comment: For instance this qualifier, in an IDP structure state entry, can be associated to a cross reference to an experimentally determined structure of the same IDP region in another database.
synonym: "identity" EXACT PSI-ID-short []
is_a: ??:xxxx ! cross-reference type

[Term]
id: 
name: partial identity match
def: "Reference to the corresponding object in another database. Correspondence is partial, so the objects are similar but explicitly not identical." [PMID:31824649]
synonym: "partial match" EXACT PSI-ID-short []
synonym: "similar object in an external resource" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! cross-reference type

[Term]
id: 
name: primary-reference
def: "Used to indicate the PMID from which the experimental data is extracted." [PMID:31824649]
is_a: ??:xxxx ! cross-reference type

[Term]
id: 
name: secondary accession number
def: "Reference to the corresponding object in another database, but the identifier used in the external database is a secondary identifier or former accession number." [PMID:31824649]
synonym: "secondary-ac" EXACT PSI-ID-short []
is_a: ??:xxxx ! cross-reference type

[Term]
id: 
name: multiple parent reference
def: "Qualifier used for hybrid or composite molecules with more than one cross-reference to parent molecules." [PMID:31824649]
subset: PSI-MI_slim
synonym: "multiple parent" EXACT PSI-MI-short []
is_a: ??:xxxx ! cross-reference type

[Term]
id: 
name: inferred-from
def: "Refers to the original experimentally verified object from which the described object has been derived." [PMID:25313161]
is_a: ??:xxxx ! cross-reference type

[Term]
id: 
name: subset
def: "Reference to the corresponding object in another database, implying the object is part of a cross-referenced entity (usually a complex)." [PMID:31824649]
synonym: "part of" EXACT PSI-ID-alternate []
synonym: "subset" EXACT PSI-ID-short []
is_a: ??:xxxx ! cross-reference type

[Term]
id: 
name: method reference
def: "Reference to a related paper which more fully describes either the experimental method or one or more of the molecules used within the experiment." [PMID:31824649]
is_a: ??:xxxx ! cross-reference type

[Term]
id: 
name: additional information
def: "Related object within the same database or pointing to an external database." [PMID:31824649]
synonym: "see-also" EXACT PSI-ID-short []
is_a: ??:xxxx ! cross-reference type



<!-- CURATION CONTENT - Indicates source, depth and standards by which an entry has been added to a database. -->
<!-- currently we don't use/need this branch -->



<!-- CURATION QUALITY - An assessment of the depth and extent to which a paper has been curated -->
<!-- currently we don't use/need this branch -->



<!-- DATABASE CITATION - ROOT TERM FOR DATABASE REFERENCING (XREF ELEMENT) - db and dbAc attributes of idf:dbReference elements to define external resources -->

[Term]
id: 
name: database citation
def: "Database citation lists names of databases commonly used to cross reference IDP data." [PMID:31824649]
relationship: part_of ID:0000 ! intrinsically disordered protein

[Term]
id: 
name: psi-mi
def: "PSI-MI." [PMID:14755292]
synonym: "PSI-MI" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "MI:[0-9]{4}"
xref: search-url: "http://www.ebi.ac.uk/ols/ontologies/mi/terms?obo_id=${ac}"
is_a: ??:xxxx ! database citation

# NEW TERM
[Term]
id: 
name: psi-id
def: "PSI-ID." [PMID:31824649]
synonym: "PSI-ID" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "ID:[0-9]{4}"
xref: search-url: "http://www.ebi.ac.uk/ols/ontologies/id/terms?obo_id=${ac}"
is_a: ??:xxxx ! database citation

# NEW TERM
[Term]
id: 
name: idpo
def: "The IDPontology is organized in five different branches/aspects ("namespace" in the DisProt and OBO formats) and is maintained by DisProt consortium." [PMID:27899601]
synonym: "IDPO" EXACT PSI-ID-alternate []
xref: search-url: "https://www.disprot.org/about"
is_a: ??:xxxx ! database citation

# experiment database

[Term]
id: 
name: experiment database
def: "Database that contains information used to add additional information to experiments (meta-data)." [PMID:31824649]
synonym: "experiment xref" EXACT PSI-ID-short []
is_a: ??:xxxx ! database citation

[Term]
id: 
name: evidence and conclusion ontology
def: "The Evidence & Conclusion Ontology (ECO) describes types of scientific evidence within the realm of biological research that can arise from laboratory experiments, computational methods, manual literature curation, and other means." [PMID:30407590]
synonym: "ECO" EXACT PSI-ID-short []
xref: id-validation-regexp: "ECO:\\d{7}$"
xref: search-url: "http://www.ebi.ac.uk/ols/ontologies/ECO/terms?obo_id=${ac}"
is_a: ??:xxxx ! experiment database

[Term]
id: 
name: experimental factor ontology
def: "The Experimental Factor Ontology (EFO) provides a systematic description of many experimental variables, combining parts of several biological ontologies to additional new terms." [pmid:20200009]
synonym: "EFO" EXACT PSI-ID-short []
xref: id-validation-regexp: "\\d{7}$"
xref: search-url: "http://www.ebi.ac.uk/ols/ontologies/efo/terms?obo_id=${ac}"
is_a: ??:xxxx ! experiment database

[Term]
id: 
name: edam
def: "EDAM (EMBRACE Data And Methods) is an ontology of bioinformatics operations (tool, application, or workflow functions), types of data, topics (application domains), and data formats.\nhttp://edamontology.org/" [PMID:23479348]
synonym: "EDAM" EXACT PSI-ID-alternate []
synonym: "EMBRACE Data And Methods" EXACT PSI-ID-alternate []
xref: url:http\://edamontology.org/
is_a: ??:xxxx ! experiment database

# feature database

[Term]
id: 
name: feature database
def: "A database describing a feature on a molecule." [PMID:31824649]
synonym: "feature xref" EXACT PSI-ID-short []
is_a: ??:xxxx ! database citation

[Term]
id: 
name: gene ontology
def: "The objective of Gene Ontology (GO) is to provide controlled vocabularies for the description of the molecular function, biological process and cellular component of gene products.\nhttp://www.ebi.ac.uk/GO" [PMID:30395331]
synonym: "go" EXACT PSI-ID-short []
xref: id-validation-regexp: "GO:[0-9]{7}"
xref: search-url: "https://www.ebi.ac.uk/QuickGO/term/${ac}"
is_a: ??:xxxx ! feature database
is_a: ??:xxxx ! interaction database

[Term]
id: 
name: go_central
def: "The GO Consortium coordinated an effort to maximize and optimize GO annotations for a large and representative set of key genomes, known as 'reference genomes'. The Reference Genome Annotation Project aimed to completely annotate twelve reference genomes, producing a resource that may effectively seed automatic annotation efforts of other genomes. This resource represents manual annotation from PAINT curators into the UniProt Protein2GO curation tool.\nhttp://www.geneontology.org/GO.refgenome.shtml" [PMID:19578431]
synonym: "GO central" EXACT PSI-ID-alternate []
synonym: "go_central" EXACT PSI-ID-short []
synonym: "GO_central" EXACT PSI-ID-alternate []
synonym: "The Reference Genome Annotation Project" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! gene ontology

[Term]
id: 
name: cdd
def: "The Conserved Domain Database may be used to identify the conserved domains present in a protein sequence.\nhttp://www.ncbi.nlm.nih.gov/Structure/cdd/cdd.shtml" [PMID:14755292]
synonym: "CDD" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "[0-9]+"
is_a: ??:xxxx ! feature database

[Term]
id: 
name: interpro
def: "InterPro combines a number of databases (referred to as member databases) that use different methodologies and a varying degree of biological information on well-characterised proteins to derive protein signatures that predict family membership and domain composition of naive protein sequences.\nhttps://www.ebi.ac.uk/interpro/" [PMID:30398656]
synonym: "InterPro" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "IPR[0-9]{6}"
xref: search-url: "https://www.ebi.ac.uk/interpro/entry/InterPro/${ac}"
is_a: ??:xxxx ! feature database

[Term]
id: 
name: gene3d
def: "The Gene3D database provides a combined structural, functional and evolutionary view of the protein world. It is focused on providing structural annotation for protein sequences without structural representatives--including the complete proteome sets of over 240 different species.\nhttp://cathwww.biochem.ucl.ac.uk:8080/Gene3D/" [PMID:29112716]
synonym: "Gene3D" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! interpro

[Term]
id: 
name: pirsf
def: "PIRSF is a classification system based on evolutionary relationship of whole proteins.\nhttp://pir.georgetown.edu/pirwww/dbinfo/pirsf.shtml" [PMID:14681371]
synonym: "PIRSF" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "PIRSF[0-9]{5}"
is_a: ??:xxxx ! interpro

[Term]
id: 
name: prints
def: "PRINTS is a compendium of protein fingerprints. A fingerprint is a group of conserved motifs used to characterise a protein family.\nhttp://umber.sbs.man.ac.uk/dbbrowser/PRINTS/" [PMID:7971946]
synonym: "PRINTS" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "PR[0-9]{6}"
is_a: ??:xxxx ! interpro

[Term]
id: 
name: prodom
def: "The ProDom protein domain database consists of an automatic compilation of homologous domains.\nhttp://protein.toulouse.inra.fr/prodom.html" [PMID:9399865]
synonym: "ProDom" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "PD[0-9]{6}"
is_a: ??:xxxx ! interpro

[Term]
id: 
name: tigrfams
def: "TIGRFAMs is a collection of protein families, featuring curated multiple sequence alignments, Hidden Markov Models (HMMs) and annotation.\nhttp://www.tigr.org/TIGRFAMs" [PMID:23197656]
synonym: "TIGRFAMs" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "TIGR[0-9]+"
is_a: ??:xxxx ! interpro

[Term]
id: 
name: panther
def: "The PANTHER (Protein ANalysis THrough Evolutionary Relationships) Classification System is a unique resource that classifies genes by their functions using published scientific experimental evidence and evolutionary relationships to predict function even in the absence of direct experimental evidence.\nwww.pantherdb.org/" [PMID:30407594]
synonym: "PANTHER" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! interpro

[Term]
id: 
name: pfam
def: "Pfam is a large collection of multiple sequence alignments and hidden Markov models covering many common protein domains.\nhttp://www.sanger.ac.uk/Software/Pfam" [PMID:30357350 ]
synonym: "Pfam" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "PF[0-9]{5}"
is_a: ??:xxxx ! interpro

[Term]
id: 
name: prosite
def: "PROSITE is a database of protein families and domains. It consists of biologically significant sites, patterns and profiles.\nhttp://us.expasy.org/prosite/" [PMID:16381852]
synonym: "Prosite" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "PS[0-9]{5}"
is_a: ??:xxxx ! interpro

[Term]
id: 
name: scop superfamily
def: "SUPERFAMILY is a library of profile hidden Markov models that represent all proteins of known structure. The library is based on the SCOP classification of proteins: each model corresponds to a SCOP domain.\nhttp://supfam.mrc-lmb.cam.ac.uk/SUPERFAMILY/" [PMID:31724711]
synonym: "SCOP superfamily" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "[0-9]+"
is_a: ??:xxxx ! interpro

[Term]
id: 
name: smart
def: "SMART (a Simple Modular Architecture Research Tool) allows the identification and annotation of genetically mobile domains and the analysis of domain architectures.\nhttp://smart.embl-heidelberg.de/" [PMID:9600884]
synonym: "SMART" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "SM[0-9]{5}"
is_a: ??:xxxx ! interpro

[Term]
id: 
name: eukaryotic linear motif resource
def: "The ELM resource provides a database of curated short linear motif classes and instances, as well as a sequence analysis tool to detect putative short linear motif instances in query sequences. http://elm.eu.org/" [PMID:22110040]
synonym: "elm" EXACT PSI-ID-short []
xref: id-validation-regexp: "[A-Za-z_0-9]+$"
xref: search-url: "http://elm.eu.org/elms/elmPages/${ac}.html"
is_a: ??:xxxx ! feature database

[Term]
id: 
name: ipfam
def: "Web resource that allows the investigation of protein interactions in the Protein Data Bank structures at the level of Pfam domains and amino acid residues. iPfam is available on the Web for browsing at.\nhttp://www.sanger.ac.uk/Software/Pfam/iPfam/" [PMID:15353450]
is_a: ??:xxxx ! feature database

[Term]
id: 
name: cog
def: "Clusters of Orthologous Groups of proteins (COGs) were delineated by comparing protein sequences encoded in complete genomes, representing major phylogenetic lineages. Each COG consists of individual proteins or groups of paralogs from at least 3 lineages and thus corresponds to an ancient conserved domain." [PMID:11125040]
synonym: "Clusters of Orthologous Groups" EXACT []
synonym: "cogg" EXACT PSI-ID-short []
is_a: ??:xxxx ! feature database

[Term]
id: 
name: wwpdb
def: "The Worldwide Protein Data Bank (wwPDB) consists of organizations that act as deposition, data processing and distribution centers for PDB data. The founding members are RCSB PDB (USA), MSD-EBI (Europe) and PDBj (Japan). The BMRB (USA) group joined the wwPDB in 2006. The mission of the wwPDB is to maintain a single Protein Data Bank Archive of macromolecular structural data that is freely and publicly available to the global community.\nhttp://www.wwpdb.org/" [PMID:14634627]
synonym: "wwPDB" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "[0-9][a-zA-Z0-9]{3}"
xref: search-url: "http://www.pdbe.org/${ac}"
is_a: ??:xxxx ! feature database
is_a: ??:xxxx ! interaction database
is_a: ??:xxxx ! source database

[Term]
id: 
name: pdbe
def: "The Protein Data Bank in Europe - the European project for the collection, management and distribution of data about macromolecular structures, derived in part from the Protein Data Bank (PDB).\nhttp://www.ebi.ac.uk/pdbe/" [PMID:16381867]
synonym: "e-MSD" EXACT []
synonym: "MSD" RELATED []
synonym: "PQS" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "[0-9][a-zA-Z0-9]{3}"
xref: search-url: "http://www.ebi.ac.uk/pdbe/entry/pdb/${ac}"
is_a: ??:xxxx ! wwpdb

[Term]
id: 
name: emdb
def: "The Electron Microscopy Data Bank (EMDB) contains experimentally determined three-dimensional maps and associated experimental data and files." [PMID:14643225]
synonym: "Electron Microscopy Data Bank" EXACT PSI-ID-alternate []
synonym: "eMDB" EXACT PSI-ID-short []
xref: search-url: "https://www.ebi.ac.uk/pdbe/entry/emdb/${ac}"
is_a: ??:xxxx ! pdbe

[Term]
id: 
name: empiar
def: "EMPIAR, the Electron Microscopy Public Image Archive, is a public resource for raw, 2D electron microscopy images. The purpose of EMPIAR is to provide easy access to state-of-the-art raw data to facilitate methods development and validation, which will lead to better 3D structures. It complements the Electron Microscopy Data Bank (EMDB), where 3D volumes are stored, and uses the fault-tolerant Aspera platform for data transfers.\n\nhttps://www.ebi.ac.uk/pdbe/emdb/empiar/" [PMID:27067018]
synonym: "Electron Microscopy Public Image Archive" EXACT PSI-ID-alternate []
synonym: "EMPIAR" EXACT PSI-ID-alternate []
synonym: "empiar" EXACT PSI-ID-short []
xref: id-validation-regex: "EMPIAR-[0-9]{5}"
xref: search-url: "https://dx.doi.org/10.6019/${ac}"
is_a: ??:xxxx ! emdb

[Term]
id: 
name: pdbj
def: "PDBj (Protein Data Bank Japan) maintains the database for the protein structures with financial assistance from the Institute for Bioinformatics Research and Development of Japan Science and Technology Corporation(BIRD-JST), collaborating with the Research Collaboration for Structural Bioinformatics(RCSB) and the MSD in the European Bioinformatics Institute(MSD-EBI) in EU. All three organizations serve as deposition, data processing and distribution sites.\nhttp://www.pdbj.org/" [PMID:12099029]
synonym: "PDBj" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "[0-9][a-zA-Z0-9]{3}"
xref: search-url: "http://pdbjs3.protein.osaka-u.ac.jp/xPSSS/DetailServlet?PDBID=${ac}&PAGEID=Summary"
is_a: ??:xxxx ! wwpdb

[Term]
id: 
name: rcsb pdb
def: "The RCSB PDB provides a variety of tools and resources for studying the structures of biological macromolecules and their relationships to sequence, function, and disease. \nhttp://www.pdb.org/" [PMID:14634627]
synonym: "PDB" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "[0-9][a-zA-Z0-9]{3}"
xref: search-url: "http://www.pdb.org/pdb/explore/explore.do?structureId=${ac}"
is_a: ??:xxxx ! wwpdb

[Term]
id: 
name: heterogen
def: "The HET records are used to describe non-standard residues, such as prosthetic groups, inhibitors, solvent molecules, and ions for\nwhich coordinates are supplied. Groups are considered HET if they are: \n- not one of the standard amino acids, and \n- not one of the nucleic acids (C, G, A, T, U, and I), and \n- not one of the modified versions of nucleic acids (+C, +G, +A,\n+T, +U, and +I), and \n- not an unknown amino acid or nucleic acid where UNK is used to\nindicate the unknown residue name. \nHet records also describe heterogens for which the chemical identity is unknown, in which case the group is assigned the hetID UNK." [PMID:31824649]
synonym: "het" EXACT PSI-ID-short []
is_a: ??:xxxx ! rcsb pdb
is_a: ??:xxxx ! pdbe
is_a: ??:xxxx ! pdbj

## feature db, PTM

[Term]
id: 
name: protein modification ontology
def: "Catalogue of covalent modification of, or a change resulting in an alteration of the measured molecular mass of, a peptide or protein amino acid residue." [PMID:18688235]
synonym: "psi-mod" EXACT PSI-ID-short []
xref: id-validation-regexp: "MOD:[0-9]{5}"
is_a: ??:xxxx ! feature database

[Term]
id: 
name: resid
def: "The RESID Database of Protein Modifications is a comprehensive collection of annotations and structures for protein modifications including amino-terminal, carboxyl-terminal and peptide chain cross-link post-translational modifications.\nhttp://www.ebi.ac.uk/RESID/index.html" [PMID:15174122]
xref: id-validation-regexp: "AA[0-9]{4}"
xref: search-url: "http://srs.ebi.ac.uk/cgi-bin/wgetz?[resid-id:${ac}]+-e"
is_a: ??:xxxx ! feature database

[Term]
id: 
name: deltamass
def: "A database of protein post translational modifications. www.abrf.org/index.cfm/dm.home" [PMID:8322616]
is_a: ??:xxxx ! feature database

[Term]
id: 
name: unimod
def: "A database of protein modifications for mass spectrometry. www.unimod.org" [PMID:15174123]
is_a: ??:xxxx ! feature database

## feature db, variants

[Term]
id: 
name: dbsnp
def: "dbSNP contains human single nucleotide variations, microsatellites, and small-scale insertions and deletions along with publication, population frequency, molecular consequence, and genomic and RefSeq mapping information for both common variations and clinical mutations." [PMID:11125122]
synonym: "dbSNP" EXACT PSI-ID-alternate []
synonym: "dbsnp" EXACT PSI-ID-short []
xref: search-url: "https://www.ncbi.nlm.nih.gov/snp/${ac}"
is_a: ??:xxxx ! feature database

[Term]
id: 
name: clinvar
def: "ClinVar is a freely accessible, public archive of reports of the relationships among human variations and phenotypes, with supporting evidence. \nhttps://www.ncbi.nlm.nih.gov/clinvar" [PMID:29165669]
synonym: "ClinVAR" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "[0-9]+"
xref: search-url: "https://www.ncbi.nlm.nih.gov/clinvar/variation/${ac}"
is_a: ??:xxxx ! feature database

# new terms for database citation related to IDP (feature or source db's ?)

# NEW TERM
[Term]
id: 
name: idpcentral / disprotcentral ?
def: "An umbrella consortium for central management of protein disorder related tools and databases." [PMID:22453911]
subset: PSI-MI_slim
synonym: "IDPcentral" EXACT PSI-ID-alternate []
xref: search-url: "http://www.ebi.ac.uk/intact/imex/main.xhtml?query=${ac}"
is_a: ??:xxxx ! feature database ? or source database ?
? add as parent term to db's integrated in disprot central ?

# NEW TERM
[Term]
id: 
name: disprot
def: "DisProt is a database of manually curated annotations of experimental disorder, collected from the literature.\nhttps://www.disprot.org/" [PMID:27899601]
synonym: "DisProt" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! feature database ? maybe also source database?

# NEW TERM
[Term]
id: 
name: bmrb
def: "The Biological Magnetic Resonance Data Bank (BMRB) is a repository for data from NMR spectroscopy on proteins, peptides, nucleic acids, and other biomolecules.\nhttps://bmrb.io/" [PMID:32006287]
synonym: "BMRB" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! feature database or is_a: ??:xxxx ! wwpdb ? maybe also source database?

# a term for BMRB already exists in PSI-MI CV, however, defined as an interaction database
[Term]
id: 
name: bmrb
def: "Database for NMR spectroscopy information on biomolecules hosted at the University of Wisconsin, Madison, US." [PMID:18288446]
synonym: "Biological Magnetic Resonance Data Bank" RELATED []
synonym: "BioMagResBank" RELATED []
is_a: ??:xxxx ! interaction database

# NEW TERM
[Term]
id: 
name: sasbdb
def: "The Small Angle Scattering Biological Data Bank (SASBDB) is a fully searchable curated repository of freely accessible and downloadable experimental data, which are deposited together with the relevant experimental conditions, sample details, derived models and their fits to the data.\nhttps://www.sasbdb.org/" [PMID:31576635]
synonym: "SASBDB" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! feature database ? maybe also source database?

# NEW TERM
[Term]
id: 
name: pcddb
def: "The Protein Circular Dichroism Data Bank (PCDDB) is a public repository that archives and freely distributes circular dichroism (CD) and synchrotron radiation CD (SRCD) spectral data and their associated experimental metadata.\nhttps://pcddb.cryst.bbk.ac.uk/" [PMID:21071417]
synonym: "PCDDB" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! feature database ? maybe also source database?

# NEW TERM
[Term]
id: 
name: dibs
def: "Disordered Binding Site (DIBS) database is a repository for protein complexes that are formed between Intrinsically Disordered Proteins (IDPs) and globular/ordered partner proteins.\nhttp://dibs.enzim.ttk.mta.hu/" [PMID:29385418]
synonym: "DIBS" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! feature database ? maybe also source database?
is_a: ??:xxxx ! interaction database

# NEW TERM
[Term]
id: 
name: mobidb
def: "MobiDB provides information about intrinsically disordered regions (IDRs) and related features from various sources and prediction tools. Different levels of reliability and different features are reported as different and independent annotations.\nhttps://mobidb.bio.unipd.it/" [PMID:33237329]
synonym: "MobiDB" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! feature database ? maybe also source database?

# NEW TERM
[Term]
id: 
name: mfib
def: "Mutual Folding Induced by Binding (MFIB) database is a repository for protein complexes that are formed exclusively by intrinsically unstructured proteins (IUPs).\nhttp://mfib.enzim.ttk.mta.hu/" [PMID:29036655]
synonym: "MFIB" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! feature database ? maybe also source database?
is_a: ??:xxxx ! interaction database

# NEW TERM
[Term]
id: 
name: ideal
def: "Intrinsically Disordered proteins with Extensive Annotations and Literature (IDEAL) provides a collection of knowledge on experimentally verified intrinsically disordered proteins (IDPs) or intrinsically disordered regions (IDRs). IDEAL contains manually curated annotations on IDPs in locations, structures, and functional sites such as protein binding regions and posttranslational modification sites together with references and structural domain assignments.\nhttps://www.ideal-db.org/" [PMID:22067451]
synonym: "IDEAL" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! feature database ? maybe also source database?

# NEW TERM
[Term]
id: 
name: ped
def: "The Protein Ensemble Database (PED) is an open access database for the deposition of structural ensembles, mainly intrinsically disordered proteins (IDPs), measured with nuclear magnetic resonance spectroscopy, small-angle X-ray scattering, and fluorescence resonance energy transfer.\nhttps://proteinensemble.org/" [PMID:33305318]
synonym: "PED" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! feature database ? maybe also source database?

# interaction (& pathway) database: can we use MI terms/id's for this, as they are defined there?

# literature database

[Term]
id: 
name: literature database
def: "Database acting as a source of literature information." [PMID:31824649]
synonym: "literature xref" EXACT PSI-ID-short []
synonym: "publication xref" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! database citation

[Term]
id: 
name: pubmed
def: "PubMed is designed to provide access to citations from biomedical literature. The data can be found at both NCBI PubMed and Europe PubMed Central. \nhttp://www.ncbi.nlm.nih.gov/pubmed\nhttp://europepmc.org" [PMID:31824649]
xref: id-validation-regexp: "[0-9]+"
xref: search-url: "http://europepmc.org/abstract/MED/${ac}"
is_a: ??:xxxx ! literature database

[Term]
id: 
name: pubmed central
def: "PubMed Central is the US National Institute of Health free digital archive of biomedical and life science journals." [PMID:12519941]
synonym: "pmc" EXACT PSI-ID-short []
is_a: ??:xxxx ! literature database

[Term]
id: 
name: digital object identifier
def: "Identifier of a publication prior to pubmed indexing." [PMID:31824649]
synonym: "doi" EXACT PSI-ID-short []
xref: id-validation-regexp: "\\d+.\\d+/[a-zA-Z0-9\\.\\:]+"
xref: search-url: "http://dx.doi.org/${ac}"
is_a: ??:xxxx ! literature database

[Term]
id: 
name: biorxiv
def: "bioRxiv is a free online archive and distribution service for unpublished preprints in the life sciences, operated by Cold Spring Harbor Laboratory. Articles are not peer-reviewed, edited, or typeset before being posted online.\nhttp://biorxiv.org/" [PMID:]
synonym: "bioRxiv" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "\\d+.\\d+/[a-zA-Z0-9\\.\\:]+"
xref: search-url: "https://www.biorxiv.org/content/${ac}"
is_a: ??:xxxx ! literature database

# participant database --> this needs to be adopted to IDP standard, region database, or molecule database, or experimental construct database ?

[Term]
id: 
name: region database or molecule database or experimental construct database ?
def: "Database for cross-referencing molecules or regions thereof analysed in experiments." [PMID:31824649]
synonym: "region xref" or "molecule xref" or "experimental construct xref" EXACT PSI-ID-short [] ?
is_a: ??:xxxx ! database citation


## participant/sequence db

[Term]
id: 
name: sequence database
def: "Database collecting nucleic or amino acid sequences mainly derived from genomic or mRNA sequencing." [PMID:31824649]
is_a: ??:xxxx ! region database or molecule database or experimental construct database ?

[Term]
id: 
name: sequence ontology
def: "The Sequence Ontology (SO) is a structured controlled vocabulary for the parts of a genomic annotation. SO provides a common set of terms and definitions that will facilitate the exchange, analysis and management of genomic data." [PMID:15892872]
synonym: "so" EXACT PSI-ID-short []
xref: id-validation-regexp: "SO:[0-9]{7}"
is_a: ??:xxxx ! feature database
is_a: ??:xxxx ! participant database

## participant/sequence db, peptide

[Term]
id: 
name: peptide sequence database
def: "database storing sequences detected by peptide identification methods." [PMID:31824649]
synonym: "pep seq db" EXACT PSI-ID-short []
is_a: ??:xxxx ! sequence database

[Term]
id: 
name: pride
def: "PRIDE is a public repository of protein and peptide identifications for the proteomics community.\nhttp://www.ebi.ac.uk/pride/" [PMID:16381953]
xref: search-url: "http://www.ebi.ac.uk/pride/archive/projects/${ac}"
is_a: ??:xxxx ! peptide sequence database

[Term]
id: 
name: peptide atlas
def: "PeptideAtlas addresses these needs by identifying peptides by tandem mass spectrometry (MS/MS), statistically validating those identifications and then mapping identified sequences to the genomes of eukaryotic organisms.\nhttp://www.peptideatlas.org/" [PMID:16381952]
synonym: "PeptideAtlas" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! peptide sequence database

[Term]
id: 
name: gpm
def: "Global Proteome Machine aim to improve the quality of analysis, make the results portable and to provide a common platform for testing and validating proteomics results.\nhttp://www.thegpm.org" [PMID:15595733]
synonym: "Global Proteome Machine" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! peptide sequence database

[Term]
id: 
name: proteomexchange
def: "The ProteomeXchange consortium was set up to provide a single point of submission of MS proteomics data to the main existing proteomics repositories, and to encourage the data exchange between them for optimal data dissemination. The data is actually hosted by consortium member databases like PeptideAtlas or PRIDE. \n\nhttp://www.proteomexchange.org" [PMID:25047258]
synonym: "proteomexchange" EXACT PSI-ID-short []
synonym: "ProteomExchange" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! peptide sequence database

## participant/sequence db, protein

[Term]
id: 
name: protein sequence database
def: "Database dedicated to the collection and annotation of protein sequences." [PMID:21447597]
synonym: "protein seq db" EXACT PSI-ID-short []
is_a: ??:xxxx ! sequence database

[Term]
id: 
name: uniprot
def: "UniProt is a centralized repository of protein sequences with comprehensive coverage and a systematic approach to protein annotation, incorporating, interpreting, integrating and standardizing data from numerous sources and is the most comprehensive catalog of protein sequences and functional annotation." [PMID:21051339]
synonym: "uniprot" EXACT PSI-ID-short []
is_a: ??:xxxx ! protein sequence database

[Term]
id: 
name: uniparc
def: "UniProt Archive (UniParc) is part of UniProt project. It is a non-redundant archive of protein sequences derived from many sources.\nhttp://www.ebi.ac.uk/uniparc/" [PMID:14681372]
synonym: "UniParc" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "UPI[A-F0-9]{10}"
xref: search-url: "http://www.ebi.uniprot.org/entry/${ac}"
is_a: ??:xxxx ! uniprot

[Term]
id: 
name: uniprot knowledge base
def: "UniProt (Universal Protein Resource) is the world's most comprehensive catalogue of information on proteins. It is a central repository of protein sequence and function created by joining the information contained in Swiss-Prot, TrEMBL, and PIR.\nhttp://www.uniprot.org" [PMID:14681372]
synonym: "uniprotkb" EXACT PSI-ID-short []
synonym: "UniProtKB" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "[OPQ][0-9][A-Z0-9]{3}[0-9]|[A-NR-Z][0-9]([A-Z][A-Z0-9]{2}[0-9]){1,2}-PRO_[0-9]{10}"
xref: search-url: "http://www.uniprot.org/uniprot/${ac}"
is_a: ??:xxxx ! interaction database
is_a: ??:xxxx ! uniprot

[Term]
id: 
name: uniprot/swiss-prot
def: "UniProt (Universal Protein Resource) is the world's most comprehensive catalogue of information on proteins. It is a central repository of protein sequence and function created by joining the information contained in Swiss-Prot, TrEMBL, and PIR. UniProtKB/Swiss-Prot is manually curated which means that the information in each entry is annotated and reviewed by a curator. \nhttp://www.uniprot.org" [PMID:14681372, PMID:21447597]
synonym: "swiss-prot" EXACT PSI-ID-short []
synonym: "UniProt" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "[OPQ][0-9][A-Z0-9]{3}[0-9]|[A-NR-Z][0-9]([A-Z][A-Z0-9]{2}[0-9]){1,2}-PRO_[0-9]{10}"
xref: search-url: "http://www.uniprot.org/uniprot/${ac}"
is_a: ??:xxxx ! uniprot knowledge base

[Term]
id: 
name: uniprot/trembl
def: "UniProt (Universal Protein Resource) is the world's most comprehensive catalogue of information on proteins. It is a central repository of protein sequence and function created by joining the information contained in Swiss-Prot, TrEMBL, and PIR. The records in UniProtKB/TrEMBL are automatically generated and are enriched with automatic annotation and classification.\nhttp://www.uniprot.org" [PMID:14681372, PMID:21447597]
synonym: "trembl" EXACT PSI-ID-short []
synonym: "UniProt" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "[OPQ][0-9][A-Z0-9]{3}[0-9]|[A-NR-Z][0-9]([A-Z][A-Z0-9]{2}[0-9]){1,2}-PRO_[0-9]{10}"
xref: search-url: "http://www.uniprot.org/uniprot/${ac}"
is_a: ??:xxxx ! uniprot knowledge base

[Term]
id: 
name: refseq
def: "The Reference Sequence (RefSeq) collection aims to provide a comprehensive, integrated, non-redundant set of sequences, including genomic DNA, transcript (RNA), and protein products, for a number of organisms.\nhttp://www.ncbi.nlm.nih.gov/RefSeq/" [PMID:26553804]
synonym: "Refseq" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "[XNZ][A-Z]_[0-9]+|[0-9]+|[XNZ][A-Z]_[0-9]+\\.[0-9]+"
is_a: ??:xxxx ! protein sequence database

[Term]
id: 
name: human orfeome collection
def: "A central resource of single-colony, fully-sequenced cloned human ORFs which can be readily transferred to Gateway compatible destination vectors for various functional proteomics studies. This set of ORFs ranges in size from 75 to more than 10,000 base pairs, and contains over 1,000 ORFs from genes with multiple splice variants." [PMID:15489335]
xref: search-url: "http://horfdb.dfci.harvard.edu/"
is_a: ??:xxxx ! protein sequence database

[Term]
id: 
name: pir
def: "The PIR-International Protein Sequence Database (PIR-PSD) was the world's first database of classified and functionally annotated protein sequences that grew out of the Atlas of Protein Sequence and Structure (1965-1978) edited by Margaret Dayhoff. Produced and distributed by the Protein Information Resource in collaboration with MIPS (Munich Information Center for Protein Sequences) and JIPID (Japan International Protein Information Database), PIR-PSD has been the most comprehensive and expertly-curated protein sequence database in the public domain for over 20 years. In 2002, PIR joined EBI (European Bioinformatics Institute) and SIB (Swiss Institute of Bioinformatics) to form the UniProt consortium. PIR-PSD sequences and annotations have been integrated into UniProt Knowledgebase. Bi-directional cross-references between UniProt (UniProt Knowledgebase and/or UniParc) and PIR-PSD are established to allow easy tracking of former PIR-PSD entries. PIR-PSD unique sequences, reference citations, and experimentally-verified data can now be found in the relevant UniProt records. \n\nLegacy data can be found at \nhttp://pir.georgetown.edu/pirwww/dbinfo/pir_psd.shtml" [PMID:10592177]
synonym: "PIR" EXACT PSI-ID-alternate []
synonym: "Protein Information Resource" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! protein sequence database

[Term]
id: 
name: international protein index
def: "IPI provides a top level guide to the main databases that describe the proteomes of higher eukaryotic organisms. IPI effectively maintains a database of cross references between the primary data sources, provides minimally redundant yet maximally complete sets of proteins for featured species (one sequence per transcript) and maintains stable identifiers (with incremental versioning) to allow the tracking of sequences in IPI between IPI releases. IPI is updated monthly in accordance with the latest data released by the primary data sources." [PMID:15221759]
synonym: "ipi" EXACT PSI-ID-short []
xref: id-validation-regexp: "IPI[0-9]+.[0-9]+|IPI[0-9]+"
is_a: ??:xxxx ! protein sequence database

## participant/sequence db, rna

[Term]
id: 
name: rfam
def: "Rfam is a large collection of multiple sequence alignments and covariance models covering many common non-coding RNA families.\nhttp://www.sanger.ac.uk/Software/Rfam/" [PMID:29112718]
synonym: "rfam" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "RF[0-9]{5}"
is_a: ??:xxxx ! sequence database

[Term]
id: 
name: RNAcentral
def: "Provides unified access to the ncRNA sequence data supplied by the expert databases." [PMID:25352543]
xref: id-validation-regexp: "/URS[0-9A-F]{10}/i"
xref: search-url: "http://rnacentral.org/rna/${ac}"
is_a: ??:xxxx ! sequence database

## participant/sequence db, genome

[Term]
id: 
name: genome database
def: "Database responsible for the maintenance and subsequent annotation of one or more genomic sequences." [PMID:31824649]
synonym: "genome db" EXACT PSI-ID-short []
is_a: ??:xxxx ! sequence database

[Term]
id: 
name: cygd
def: "The MIPS Comprehensive Yeast Genome Database (CYGD) aims to present information on the molecular structure and functional network of the entirely sequenced, well-studied model eukaryote, the budding yeast Saccharomyces cerevisiae. In addition the data of various projects on related yeasts are used for comparative analysis.\nhttp://mips.gsf.de/proj/yeast/CYGD.\nhttp://mips.gsf.de/genre/proj/mpact" [PMID:]
synonym: "CYGD" EXACT PSI-ID-alternate []
synonym: "CYGD (MIPS)" EXACT PSI-ID-alternate []
synonym: "MIPS" EXACT PSI-ID-alternate []
synonym: "MPact" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "[0-9]+|[A-Z]{3}[0-9]{3}[A-Za-z](-[A-Za-z])?|[A-Z0-9]+\\.[0-9]+|YM[A-Z][0-9]{3}[a-z][0-9]"
is_a: ??:xxxx ! source database
is_a: ??:xxxx ! genome database
is_a: ??:xxxx ! pathways database

[Term]
id: 
name: flybase
def: "FlyBase is a comprehensive database for information on the genetics and molecular biology of Drosophila.\nhttp://flybase.org" [PMID:]
synonym: "FlyBase" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "FB[a-z]{2}[0-9]{7}"
xref: search-url: "http://flybase.org/reports/${ac}"
is_a: ??:xxxx ! genome database

[Term]
id: 
name: mgd/mgi
def: "Mouse Genome Informatics (MGI) provides integrated access to data on the genetics, genomics, and biology of the laboratory mouse.\nhttp://www.informatics.jax.org/" [PMID:]
synonym: "MGD/MGI" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "MGI:[0-9]+"
is_a: ??:xxxx ! genome database

[Term]
id: 
name: ensembl
def: "Ensembl is a joint project between the EMBL-EBI and the Wellcome Trust Sanger Institute that aims at developing a system that maintains automatic annotation of large eukaryotic genomes.\nhttp://www.ensembl.org" [PMID:15078858]
synonym: "Ensembl" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "ENS[A-Z]+[0-9]{11}|[A-Z]{3}[0-9]{3}[A-Za-z](-[A-Za-z])?|CG[0-9]+|[A-Z0-9]+\\.[0-9]+|YM[A-Z][0-9]{3}[a-z][0-9]"
xref: search-url: "http://www.ensembl.org/Multi/Search/Results?q=${ac}"
is_a: ??:xxxx ! genome database

[Term]
id: 
name: rgd
def: "The Rat Genome Database (RGD) curates and integrates rat genetic and genomic data.\nhttp://rgd.mcw.edu/" [PMID:]
synonym: "RGD" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "[0-9]+"
is_a: ??:xxxx ! genome database

[Term]
id: 
name: sgd
def: "SGD is a scientific database of the molecular biology and genetics of the yeast Saccharomyces cerevisiae.\nhttp://www.yeastgenome.org/" [PMID:]
synonym: "Saccharomyces Genome Database" EXACT PSI-ID-alternate []
synonym: "SGD" EXACT PSI-ID-short []
xref: id-validation-regexp: "S[0-9]{9}"
xref: search-url: "http://www.yeastgenome.org/locus/${ac}/overview"
is_a: ??:xxxx ! genome database

[Term]
id: 
name: wormbase
def: "WormBase is the central worm database that houses the gene reports, locus reports, translation reports, expression pattern data and genome browser.\nhttp://www.wormbase.org/" [PMID:]
subset: PSI-MI_slim
synonym: "WormBase" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "WBGene[0-9]{8}"
is_a: ??:xxxx ! genome database

[Term]
id: 
name: encode
def: "ENCODE (the Encyclopedia Of DNA Elements) seeks to identify all protein-coding genes. The current ENCODE data set is derived from 1% of the human genome and has been selected for analysis in the pilot phase of the project.\nhttp://www.genome.gov/10005107" [PMID:17372197]
synonym: "ENCODE" EXACT PSI-ID-alternate []
synonym: "Encyclopedia Of DNA Elements" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! genome database

[Term]
id: 
name: camjedb
def: "Camjedb is a comprehensive database for information on the genome of Campylobacter jejuni.\nhttp://www.sanger.ac.uk/Projects/C_jejuni/" [PMID:106882042]
is_a: ??:xxxx ! genome database

[Term]
id: 
name: ensemblgenomes
def: "Genome browser complementary to Ensembl which extends the search space across a broader taxonomic range.\nhttp://www.ensemblgenomes.org" [PMID:19884133]
xref: search-url: "http://ensemblgenomes.org/search/eg/${ac}"
is_a: ??:xxxx ! genome database

[Term]
id: 
name: dictybase
def: "dictyBase (http://dictybase.org) is the model organism database for Dictyostelium discoideum. It houses the complete genome sequence, ESTs and the entire body of literature relevant to Dictyostelium. This information is curated to provide accurate gene models and functional annotations, with the goal of fully annotating the genome." []
xref: id-validation-regexp: "DDB_G(0-9){7}"
is_a: ??:xxxx ! genome database

[Term]
id: 
name: rice genome annotation project
def: "NSF funded annotation project." [PMID:17145706]
synonym: "RGAP" RELATED []
is_a: ??:xxxx ! genome database

[Term]
id: 
name: plantgdb
def: "PlantGDB  develops plant species-specific EST and GSS databases, to provide web-accessible tools and inter-species query capabilities, and to provide genome browsing and annotation capabilities." [PMID:18063570]
synonym: "plantgdb" EXACT PSI-ID-short []
is_a: ??:xxxx ! genome database

[Term]
id: 
name: ratmap
def: "The rat genome database RatMap (http://ratmap.org or http://ratmap.gen.gu.se) has been one of the main resources for rat genome information since 1994. The database is maintained by CMB Genetics at Gothenburg University in Sweden and provides information on rat genes, polymorphic rat DNA-markers and rat quantitative trait loci (QTLs), all curated at RatMap." [PMID:15608244]
synonym: "ratmap" EXACT PSI-ID-short []
is_a: ??:xxxx ! genome database

[Term]
id: 
name: tair
def: "The Arabidopsis Information Resource (TAIR) maintains a database of genetic and molecular biology data for the model higher plant Arabidopsis thaliana . Data available from TAIR includes the complete genome sequence along with gene structure, gene product information, metabolism, gene expression, DNA and seed stocks, genome maps, genetic and physical markers, publications, and information about the Arabidopsis research community." [PMID:20521243]
synonym: "tair" EXACT PSI-ID-short []
synonym: "The Arabidopsis Information Resource" EXACT []
is_a: ??:xxxx ! genome database

[Term]
id: 
name: tigr/jcvi
def: "The J. Craig Venter Institute was formed in October 2006 through the merger of several affiliated and legacy organizations including The Institute for Genomic Research (TIGR)." [PMID:18287690]
synonym: "J. Craig Venter Institute" EXACT []
synonym: "The Institute for Genomic Research" EXACT PSI-ID-short []
synonym: "tigr/jcvi" EXACT PSI-ID-short []
is_a: ??:xxxx ! genome database

[Term]
id: 
name: zfin
def: "Extensive information on Danio rerio, including genomics databases, developmental stages, publications and molecular tools." [PMID:21036866]
synonym: "The Zebrafish Model Organism Database " EXACT []
synonym: "zfin" EXACT PSI-ID-short []
is_a: ??:xxxx ! genome database

## participant db, gene

[Term]
id: 
name: gene database
def: "Primarily nomenclature/cross-reference database, used by curators to establish a link between a gene and protein ID. In some cases, database records do not contain actual sequence but point to loci on specific reference genomes." [PMID:31824649]
synonym: "gene db" EXACT PSI-ID-short []
is_a: ??:xxxx ! region database or molecule database or experimental construct database ?

[Term]
id: 
name: hgnc
def: "HGNC is the nomenclature committee responsible for the naming of human genes." [PMID:20929869]
synonym: "hgnc" EXACT PSI-MI-short []
synonym: "Human Genome Nomenclature Committee" EXACT PSI-ID-short []
is_a: ??:xxxx ! gene database

[Term]
id: 
name: entrez gene/locuslink
def: "LocusLink provides a single query interface to curated sequence and descriptive information about genetic loci.\nhttp://www.ncbi.nlm.nih.gov/LocusLink/" [PMID:]
synonym: "Entrez gene/locuslink" EXACT PSI-ID-alternate []
synonym: "entrezgene/locuslink" EXACT PSI-ID-short []
xref: id-validation-regexp: "[0-9]+|[A-Z]{1,2}_[0-9]+|[A-Z]{1,2}_[A-Z]{1,4}[0-9]+"
is_a: ??:xxxx ! gene database

## participant/sequence db, genbank

[Term]
id: 
name: ddbj/embl/genbank
def: "DDBJ EMBL GenBank Nucleotide Sequence Database Collaboration exchange new and updated data on a daily basis to achieve optimal synchronisation.\nhttp://www.ebi.ac.uk/embl/Contact/collaboration" [PMID:29190397]
synonym: "DDBJ" EXACT PSI-ID-alternate []
synonym: "DDBJ/EMBL/GenBank" EXACT PSI-ID-alternate []
synonym: "EMBL" EXACT PSI-ID-alternate []
synonym: "GenBank" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "[A-Z][0-9]{5}|[A-Z][0-9]{5}\\.[0-9]+|[A-Z]{2}[0-9]{6}|[A-Z]{2}[0-9]{6}\\.[0-9]+|[A-Z]{4}[0-9]{8}|[A-Z]{4}[0-9]{8}\\.[0-9]+"
xref: search-url: "http://www.ebi.ac.uk/cgi-bin/dbfetch?db=EMBLSVA&id=${ac}"
is_a: ??:xxxx ! sequence database

[Term]
id: 
name: genbank identifier
def: "GenBank Identifier or GI numbers for nucleotides or proteins" [PMID:15078858]
xref: id-validation-regexp: "ENS[A-Z]+[0-9]{11}"
is_a: ??:xxxx ! sequence database

[Term]
id: 
name: protein genbank identifier
def: "GenBank Identifier or GI numbers for proteins." [PMID:17170002]
synonym: "GenBank Protein GI" EXACT PSI-ID-alternate []
synonym: "genbank protein gi" EXACT PSI-ID-alternate []
synonym: "genbank_protein_gi" EXACT PSI-ID-short []
synonym: "genpept id" EXACT []
xref: id-validation-regexp: "[0-9]+"
xref: search-url: "http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?db=protein&cmd=Retrieve&dopt=Graphics&list_uids=${ac}"
is_a: ??:xxxx ! genbank identifier

[Term]
id: 
name: nucleotide genbank identifier
def: "GenBank Identifier or GI numbers for nucleotide." [PMID:17170002]
synonym: "genbank nucleotide" EXACT PSI-ID-alternate []
synonym: "GenBank Nucleotide" EXACT PSI-ID-alternate []
synonym: "genbank_nucl_gi" EXACT PSI-ID-short []
xref: id-validation-regexp: "[0-9]+"
xref: search-url: "http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?db=nucleotide&cmd=Retrieve&dopt=Graphics&list_uids=$"
is_a: ??:xxxx ! genbank identifier

## participant/sequence db, other

[Term]
id: 
name: chembl target
def: "ChEMBL focuses on mapping the interactions of small molecules binding to their macromolecular targets." []
xref: regexp: "CHEMBL:[0-9]+"
xref: search-url: "http://www.ebi.ac.uk/chembldb/index.php/target/inspect/${ac}"
is_a: ??:xxxx ! sequence database
relationship: part_of ??:xxxx ! chembl

[Term]
id: 
name: flannotator
def: "A repository for collecting, storing and and searching the annotation of gene or protein expression patterns in Drosophila melongaster. CPTI (Cambridge Protein Trap Identifier)" [PMID:19126575]
xref: id-validation-regexp: "CPTO-[0-9]{6}"
is_a: ??:xxxx ! sequence database

[Term]
id: 
name: huge
def: "A Database of Human Unidentified Gene-Encoded Large Proteins Analyzed by Kazusa Human cDNA Project.\nhttp://www.kazusa.or.jp/huge/" [PMID:]
xref: id-validation-regexp: "KIAA[0-9]{4}[A-Z]{0,1}"
xref: search-url: "http://www.kazusa.or.jp/huge/gfpage/${ac}"
is_a: ??:xxxx ! sequence database

[Term]
id: 
name: omim
def: "Online Mendelian Inheritance in Man (OMIM) is a catalogue of human genes and genetic disorders, with links to literature references, sequence records, maps, and related databases.\nhttp://www.ncbi.nlm.nih.gov/entrez/query.fcgi?db=OMIM" [PMID:]
synonym: "OMIM" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "[0-9]+"
xref: search-url: "http://www.omim.org/entry/${ac}"
is_a: ??:xxxx ! sequence database


## participant db, source organism

[Term]
id: 
name: uniprot taxonomy
def: "Based on NCBO Taxonomy but adapted for UniProt\nhttp://www.uniprot.org/taxonomy/" [PMID:18836194]
synonym: "uniprot taxon" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "[0-9]+"
xref: search-url: "http://www.uniprot.org/taxonomy/${ac}"
is_a: ??:xxxx ! region database or molecule database or experimental construct database ?

[Term]
id: 
name: ncbi taxonomy
def: "The NCBI taxonomy database indexes over 55.000 organisms that are represented in the sequence databases with at least one nucleotide or protein sequence. The Taxonomy Browser can be used to view the taxonomic position or retrieve sequence and structural data for a particular organism or group of organisms. Searches of the NCBI taxonomy may be made on the basis of whole or partial organism names, and direct links to organisms commonly used in biological research are also provided. The Taxonomy Browser can also be used to display the number of nucleic acid sequences, protein sequences, and protein structures available for organisms included in the branch. From the data display for a particular organism, one can retrieve and download the sequence data for that organism, or protein 3D structure data if available.\nhttp://www.ncbi.nlm.nih.gov/Taxonomy/" [PMID:10592169]
xref: id-validation-regexp: "[0-9]+"
xref: search-url: "http://www.ncbi.nlm.nih.gov/Taxonomy/Browser/wwwtax.cgi?mode=Info&id=${ac}&lvl=3&lin=f&keep=1&srchmode=1&unlock"
is_a: ??:xxxx ! region database or molecule database or experimental construct database ?

[Term]
id: 
name: brenda
def: "A structured controlled vocabulary for the source of an enzyme. It comprises terms for tissues, cell lines, cell types and cell cultures from uni- and multicellular organisms.\nhttp://www.brenda-enzymes.info" [PMID:21030441]
is_a: ??:xxxx ! region database or molecule database or experimental construct database ?

[Term]
id: 
name: cabri
def: "CABRI cell lines catalogue available at.\nhttp://www.cabri.org/" [PMID:31824649]
xref: id-validation-regexp: "[0-9]+|ACC\\s[A-Z0-9]+|ECACC\\s[A-Z0-9]+|LMBP\\s[A-Z0-9]+|ICLC\\s[A-Z0-9]+|CIP-[0-9]+|DSMZ_MUTZ\\:ACC\\s[0-9]+"
xref: search-url: "http://www.cabri.org/CABRI/srs-bin/wgetz?-e+-page+EntryPage+[$id]"
is_a: ??:xxxx ! region database or molecule database or experimental construct database ?

[Term]
id: 
name: cell ontology
def: "Ontology of cell types.\nhttp://obo.sourceforge.net/cgi-bin/detail.cgi?cell" [PMID:29322914]
is_a: ??:xxxx ! region database or molecule database or experimental construct database ?

[Term]
id: 
name: tissue list
def: "List of tissue used as topic in UniProt RC line.\nhttp://www.expasy.org/cgi-bin/lists?tisslist.txt" [PMID:]
is_a: ??:xxxx ! region database or molecule database or experimental construct database ?


## participant db, bioactive entity reference

[Term]
id: 
name: bioactive entity reference
def: "General on-line reference to other details about a drug or other bioactive entity." [PMID:]
synonym: "bioactive entity ref" EXACT PSI-ID-short []
is_a: ??:xxxx ! region database or molecule database or experimental construct database ?

[Term]
id: 
name: chebi
def: "A definitive, freely available database of Chemical compounds of Biological Interest (ChEBI).\nhttp://www.ebi.ac.uk/chebi/" [PMID:]
synonym: "ChEBI" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "CHEBI:[0-9]+"
xref: search-url: "http://www.ebi.ac.uk/chebi/searchId.do?chebiId=${ac}"
is_a: ??:xxxx ! bioactive entity reference

[Term]
id: 
name: pubchem
def: "PubChem provides information on the biological activities of small molecules.\nhttp://pubchem.ncbi.nlm.nih.gov/" [PMID:16381840]
synonym: "PubChem" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! bioactive entity reference

[Term]
id: 
name: chembl compound
def: "ChEMBL focuses on mapping the interactions of small molecules binding to their macromolecular targets." [PMID:19194660, PMID:24214965]
synonym: "chembl" EXACT []
xref: id-validation-regexp: "[0-9]+"
xref: search-url: "http://www.ebi.ac.uk/chembldb/index.php/compound/inspect/${ac}"
is_a: ??:xxxx ! bioactive entity reference
relationship: part_of ??:xxxx ! chembl

[Term]
id: 
name: beilstein
def: "The Beilstein database is in the field of organic chemistry, in which compounds are uniquely identified by their Beilstein Registry Number." [PMID:ID\:11604014]
synonym: "beilstein" EXACT PSI-ID-short []
is_a: ??:xxxx ! bioactive entity reference

[Term]
id: 
name: einecs
def: "The EINECS database provides general information such as CAS number, EINECS number, Substance Name and Chemical Formula for 100,204 chemical substances. Where available each compound entry is linked to risk and safety phrases and IUCLID and OECD chemical data sheets." [PMID:17125194]
synonym: "einecs" EXACT PSI-ID-short []
synonym: "European Inventory of Existing Commercial Chemical Substances " EXACT []
is_a: ??:xxxx ! bioactive entity reference

[Term]
id: 
name: merck index
def: "Comprehensive information on chemicals, drugs, and biologicals." [PMID:17832605]
synonym: "merck index" EXACT PSI-ID-short []
is_a: ??:xxxx ! bioactive entity reference

[Term]
id: 
name: drugbank
def: "DrugBank Accession number consisting of the 4 letter prefix and a 5 number suffix. Each Accession number is unique to the drug's generic name. The 4 letter suffix (APRD, EXPT, BIOD, NUTR) indicates the type of drug (APRD=approved small molecule drug, EXPT=experimental drug, BIOD=biotech drug, NUTR=nutraceutical or natural product). Biotech drugs consist of FDA approved peptide, protein or nucleic acid drugs, approved small molecule drugs are FDA approved non-biotech drugs, nutraceuticals are natural products (amino acids, vitamins, other metabolites) and experimental drugs include drugs under trial, pre-clinical drugs, unapproved drugs, well known inhibitors and possible toxins." [PMID:]
is_a: ??:xxxx ! bioactive entity reference

[Term]
id: 
name: cas registry number
def: "Chemical Abstract Service identification number" [PMID:]
is_a: ??:xxxx ! bioactive entity reference

[Term]
id: 
name: pharmgkb
def: "Pharmacogenomics Knowledge Base identification number (if molecule is in PharmGKB)" [PMID:]
is_a: ??:xxxx ! bioactive entity reference

[Term]
id: 
name: bind smid
def: "BIND database Small Molecule Identification number (if molecule is in BIND)" [PMID:]
comment: May not be publicly available any more since now owned by Thompson Scientific.
is_a: ??:xxxx ! bioactive entity reference

[Term]
id: 
name: canadian drug identification number
def: "Drug Identification Number (Canadian Drug ID system)" [PMID:]
synonym: "din" EXACT PSI-ID-short []
is_a: ??:xxxx ! bioactive entity reference

[Term]
id: 
name: rxlist link
def: "Hyperlink to RxList entry for the given drug (if it exists)" [PMID:]
is_a: ??:xxxx ! bioactive entity reference

[Term]
id: 
name: pdr health
def: "Hyperlink to PDRhealth entry for the given drug (if it exists)" [PMID:]
synonym: "PDRhealth" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! bioactive entity reference

[Term]
id: 
name: wikipedia
def: "Hyperlink to wikipedia entry for the given drug (if it exists)" [PMID:]
is_a: ??:xxxx ! bioactive entity reference


## participant db, other

[Term]
id: 
name: kegg
def: "KEGG (Kyoto Encyclopedia of Genes and Genomes) is a knowledge base for systematic analysis of gene functions, linking genomic information with higher order functional information and also supplies information about chemical compounds, enzyme molecules and enzymatic reactions.\nhttp://www.genome.ad.jp/kegg/" [PMID:10592173]
synonym: "KEGG" EXACT PSI-ID-alternate []
xref: id-validation-regexp: "[a-zA-Z]+:[a-zA-Z]+[0-9]+"
is_a: ??:xxxx ! region database or molecule database or experimental construct database ?
is_a: ??:xxxx ! pathways database

[Term]
id: 
name: kegg compound
def: "Kyoto Encyclopedia of Genes and Genomes compound identification number (if molecule is in KEGG)" [PMID:]
synonym: "KEGG Compound ID" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! kegg

[Term]
id: 
name: dflat
def: "Database dedicated to annotating gene function related to human fetal development using the Gene Ontology for functional annotation.\nhttp://bcb.cs.tufts.edu/dflat/" []
synonym: "Developmental FunctionaL Annotation at Tufts" EXACT PSI-ID-alternate []
synonym: "dflat" EXACT PSI-ID-short []
synonym: "DFLAT" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! region database or molecule database or experimental construct database ?

[Term]
id: 
name: complex portal
def: "The Complex Portal is a manually curated, encyclopaedic resource of macromolecular complexes from a number of key model organisms, entered into the IntAct molecular interaction database . Data includes protein-only complexes as well as protein-small molecule and protein-nucleic acid complexes. All complexes are derived from physical molecular interaction evidences extracted from the literature and cross-referenced in the entry, or by curator inference from information on homologs in closely related species or by inference from scientific background. All complexes are tagged with Evidence and Conclusion Ontology codes to indicate the type of evidence available for each entry." [PMID:25313161]
synonym: "Complex Portal" EXACT PSI-ID-alternate []
synonym: "complex portal" EXACT PSI-ID-short []
xref: search-url: "http://www.ebi.ac.uk/complexportal/complex/${ac}"
is_a: ??:xxxx ! interaction database
is_a: ??:xxxx ! region database or molecule database or experimental construct database ?


# source database
# in PSI-MI CV this includes mainly interaction and imex databases (not included heer), as well as PDB resources (defined earlier, see feature db)
# we might want to define IDP specific source databases

[Term]
id: 
name: source database
def: "Database that originally provided the IDP data record for exchange purposes." [PMID:31824649]
is_a: ??:xxxx ! database citation

[Term]
id: MI:0731
name: 3d repertoire
def: "The aim of 3D Repertoire is to determine the structures of all amenable complexes in a cell at medium or high resolution, which will later serve to integrate in toponomic and dynamic analyses of protein complexes in a cell. Complex models, EM pictures, expression and purification protocols obtained in the project will be collected in a database connected to the PDB repository." [PMID:14755292]
synonym: "3D Repertoire" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! source database



<!-- EXPERIMENTAL PREPARATION - ROOT TERM FOR EXPERIMENTAL PREPARATION - name and xref elements of idf:experimentalPreparation element to define experimental preparation of experimental construct -->

[Term]
id: 
name: experimental preparation
def: "Set of terms to describe the experimental treatment and status of the experimental region that is analysed. This term groups a number of orthologous short controlled vocabularies delivery method, expression level, molecular source, and sample process. Each experimental region can then be annotated with a maximum of 4 terms selected from each short list." [PMID:31824649]
synonym: "experimental prep" EXACT PSI-ID-short []
relationship: part_of ID:0000 ! intrinsically disordered protein

# conformational status

[Term]
id: 
name: conformational status
def: "Statement about the native/denatured conformation of the protein." [PMID:31824649]
synonym: "conformation" EXACT PSI-ID-short []
is_a: ??:xxxx ! experimental preparation

[Term]
id: 
name: denatured
def: "Altered conformation state of the protein as a result of heat or chemical modification resulting in a changed structure of the protein." [PMID:31824649]
is_a: ??:xxxx ! conformational status

[Term]
id: 
name: native
def: "State of the protein without interference i.e. the natural form." [PMID:31824649]
is_a: ??:xxxx ! conformational status

# delivery method
# the terms listed below have child terms that can also be taken from PSI-MI CV

[Term]
id: 
name: delivery method
def: "Method by which molecule is delivered or engineered into a cell." [PMID:31824649]
is_a: ??:xxxx ! experimental preparation

[Term]
id: 
name: electroporation
def: "Method for temporarily permeabilising cell membranes so as to facilitate the entry of large or hydrophilic molecules (as in transfection). A brief (ca 1 msec) electric pulse is given with potential gradients of about 700V/cm." [PMID:6329708]
is_a: ??:xxxx ! delivery method

[Term]
id: 
name: infection
def: "Molecule introduced into a cell via an external organism, usually a virus or bacteria." [PMID:31824649]
is_a: ??:xxxx ! delivery method

[Term]
id: 
name: microinjection
def: "The insertion of a substance into a cell through a microneedle. To extrude the substances through the very fine needle tip, either hydrostatic pressure (pressure injection) or electric currents (ionophoresis) is employed." [PMID:3016916]
synonym: "micro-injection" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! delivery method

[Term]
id: MI:0704
name: nucleic acid delivery
def: "Method by which nucleic acids are delivered or engineered into a cell." [PMID:31824649]
synonym: "nucl delivery" EXACT PSI-ID-short []
is_a: ??:xxxx ! delivery method

[Term]
id: 
name: passive uptake
def: "Entrance of molecules into cells that does not involved specific treatments but relies on natural cellular processes." [PMID:31824649]
is_a: ??:xxxx ! delivery method

[Term]
id: 
name: protein delivery
def: "Method by which proteins are delivered into a cell." [PMID:31824649]
is_a: ??:xxxx ! delivery method

# expression level

[Term]
id: 
name: expression level
def: "Synthesis rate of a molecule under investigation described in comparison with its naturally occurring expression level in a cell." [PMID:14755292]
is_a: ??:xxxx ! experimental preparation

[Term]
id: 
name: physiological level
def: "A molecule whose synthesis is under control of its natural gene promoter or estimated to be expressed at a similar rate." [PMID:14755292]
synonym: "endogenous" EXACT PSI-ID-alternate []
synonym: "endogenous level" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! expression level

[Term]
id: 
name: under expressed level
def: "A molecule is estimated to be expressed at lower levels than in physiological condition." [PMID:14755292]
synonym: "under-expressed" EXACT PSI-ID-short []
is_a: ??:xxxx ! expression level
is_a: ??:xxxx ! expression level alteration

[Term]
id: 
name: over expressed level
def: "A molecule is estimated to be expressed at higher levels than in physiological condition." [PMID:14755292]
synonym: "over-expressed" EXACT PSI-ID-short []
is_a: ??:xxxx ! expression level
is_a: ??:xxxx ! expression level alteration

# genetic experimental form (Descriptor of an experimental form involved in a genetic interaction)
# these terms will probably not be needed in PSI-ID schema, as related to genetic interactions

# molecular source

[Term]
id: 
name: molecular source
def: "Defines whether molecule is endogenously expressed or has in any way been altered, in sequence or expression level, from its native state. For a complete description of the experimental molecule form use the orthogonal CVs expression level, delivery method, and sample process." [PMID:14755272]
is_a: ??:xxxx ! experimental preparation

[Term]
id: 
name: engineered
def: "Molecule has been added into system from an external source or altered within the cell." [PMID:14755292]
is_a: ??:xxxx ! molecular source

[Term]
id: 
name: naturally occurring
def: "Unaltered endogenous molecule in its naturally occurring state." [PMID:14755292]
synonym: "endogenous" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! molecular source

# sample process

[Term]
id: 
name: sample process
def: "Indicates the sample context in which each experimental construct is presented." [PMID:14755292]
is_a: ??:xxxx ! experimental preparation

[Term]
id: 
name: cdna library
def: "Mixed population of cDNAs (complementaryDNA) made from mRNA from a defined source, usually a specific cell type. This term should be associated only to nucleic acid experimental constructs not to their proteins product." [PMID:6110205]
is_a: ??:xxxx ! sample process

[Term]
id: 
name: cell lysate
def: "Cell has been physically or chemically broken open and experimental construct present in resulting mixture of cellular components." [PMID:14755292]
is_a: ??:xxxx ! sample process

[Term]
id: 
name: subcellular preparation
def: "Cell lysates are partially fractionated to isolate a specific subcellular fraction." [PMID:14755292]
synonym: "subcellular prep" EXACT PSI-ID-short []
is_a: ??:xxxx ! cell lysate

[Term]
id: 
name: fixed cell
def: "Cells has been fixed by treatment with organic solvent, staining and inclusion in a resin for microscopic analysis." [PMID:14755292]
is_a: ??:xxxx ! sample process

[Term]
id: 
name: living cell
def: "Experimental construct is observed within in a living cell." [PMID:14755292]
is_a: ??:xxxx ! sample process

[Term]
id: 
name: purified
def: "Experimental construct has undergone one or more purification steps to isolate it from the cellular environment." [PMID:14755292]
is_a: ??:xxxx ! sample process

[Term]
id: 
name: homogeneous
def: "The author states an experimental construct is completely pure, i.e. no other molecular species are present." [PMID:14755292]
synonym: "pure" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! purified

[Term]
id: 
name: partially purified
def: "The author states an experimental construct is only partially purified, i.e. other molecular species also known to be present." [PMID:14755292]
is_a: ??:xxxx ! purified

[Term]
id: 
name: in vitro translated protein
def: "Protein sample collected by in vitro translation of its mRNA taking advantage of purified translation machinery." [PMID:14755292]
synonym: "in vitro translated" EXACT PSI-MI-short []
is_a: ??:xxxx ! sample process

[Term]
id: 
name: conditioned medium
def: "Experimental construct present in media harvested from cultured cells." [PMID:14755292]
is_a: ??:xxxx ! sample process

[Term]
id: 
name: phage library
def: "A bacteriophage library of genes encoding proteins or peptides fused to a phage coat protein that are expressed on the surface of the phage virion." [PMID:9661810]
is_a: ??:xxxx ! sample process



<!-- EXPERIMENTAL ROLE - Role played by the participant within the experiment. -->
<!-- currently we don't use/need this branch -->



<!-- FEATURE DETECTION METHOD - Method to determine the features of the proteins involved in the interaction. -->
<!-- if we want to annotate feature detection methods, we can use terms from ECO CV for this? -->



<!-- BRANCH FOR FEATURE RANGE STATUS ANNOTATION -->

[Term]
id: 
name: feature range status
def: "Describes sequence positions resolution of a given feature of a region or experimental construct. In the PSI-ID schema this CV is associated with the start and end position of a feature range." [PMID:31824649]
synonym: "endStatus" EXACT PSI-ID-alternate []
synonym: "startStatus" EXACT PSI-ID-alternate []
relationship: part_of ID:0000 ! intrinsically disordered protein

[Term]
id: 
name: c-terminal position
def: "Term describing the last amino acid of a peptide chain." [PMID:31824649]
comment: Displayed as 'c'.
synonym: "c-term" EXACT PSI-ID-alternate []
synonym: "c-terminal" EXACT PSI-ID-short []
synonym: "c-terminus" EXACT PSI-ID-alternate []
synonym: "carboxy-terminus" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! feature range status

[Term]
id: 
name: certain sequence position
def: "Position within the sequence clearly defined." [PMID:31824649]
synonym: "certain" EXACT PSI-ID-short []
is_a: ??:xxxx ! feature range status

[Term]
id: 
name: greater-than
def: "Partially determined sequence position known to be in a location higher than a given position." [PMID:31824649]
comment: Displayed as '>'.
is_a: ??:xxxx ! feature range status

[Term]
id: 
name: less-than
def: "Partially determined sequence position known to be in a position lower than a given position." [PMID:31824649]
comment: Displayed as '<'.
is_a: ??:xxxx ! feature range status

[Term]
id: 
name: range
def: "Describes a sequence position known to be in a certain range, where the exact position is unclear." [PMID:31824649]
comment: For instance when an amino acid modification is known to be in the region from 5 to 7. Displayed as '..'.
is_a: ??:xxxx ! feature range status

[Term]
id: 
name: undetermined sequence position
def: "Term describing a completely unknown or unspecified sequence position." [PMID:31824649]
comment: Displayed as '?'.
synonym: "undetermined" EXACT PSI-ID-short []
is_a: ??:xxxx ! feature range status

[Term]
id: 
name: n-terminal position
def: "Term describing the first amino acid of a peptide chain." [PMID:31824649]
comment: Displayed as 'n'.
synonym: "amino-terminus" EXACT PSI-ID-alternate []
synonym: "n-term" EXACT PSI-ID-alternate []
synonym: "n-terminal " EXACT PSI-ID-short []
synonym: "n-terminus" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! feature range status

[Term]
id: 
name: ragged n-terminus
def: "Mixture of protein forms where N-terminus has been progressively truncated." [PMID:31824649]
is_a: ??:xxxx ! n-terminal position

[Term]
id: 
name: c-terminal range
def: "The C-terminal region of a sequence, exact coordinates not available." [PMID:31824649]
synonym: "c-term range" EXACT PSI-ID-short []
is_a: ??:xxxx ! feature range status

[Term]
id: 
name: n-terminal range
def: "The N-terminal region of a sequence, exact coordinates not available." [PMID:31824649]
synonym: "n-term range" EXACT PSI-ID-short []
is_a: ??:xxxx ! feature range status



<!-- BRANCH FOR FEATURE TYPE ANNOTATION -->

[Term]
id: 
name: feature type
def: "Property of a subsequence that may interfere with the function and/or structure state of a molecule or molecule region." [PMID:14755292]
relationship: part_of ID:0000 ! intrinsically disordered protein

# biological features - some of the terms below have child terms (not listed here) that specify the effect of the feature on an interaction; these might be adapted to annotate the effect on the structure state or function of a molecule or molecule region

[Term]
id: 
name: biological feature
def: "Property of a subsequence that may be involved with or interfere with the function and/or structure state of a molecule or molecule region." [PMID:14755292]
is_a: ??:xxxx ! feature type

[Term]
id: 
name: binding-associated region
def: "A region of a molecule or a component of a complex involved in an interaction. This may or may not be a region of the molecule in direct contact with the interacting partner." [PMID:14755292]
synonym: "binding component" RELATED []
synonym: "binding region" EXACT PSI-ID-short []
synonym: "binding site" BROAD []
is_a: ??:xxxx ! biological feature

[Term]
id: 
name: mutation
def: "A change in a sequence or structure in comparison to a reference entity due to a  insertion, deletion or substitution event." [PMID:14755292]
is_a: ??:xxxx ! biological feature

[Term]
id: 
name: polyprotein fragment
def: "Subpart of a polyprotein that is naturally cleaved in vivo." [PMID:14577292]
synonym: "chain" RELATED []
synonym: "polyprotein frag" EXACT PSI-ID-short []
is_a: ??:xxxx ! biological feature

[Term]
id: 
name: allosteric post-translational modification
def: "A post-translational modification that elicits an allosteric response upon addition to a target molecule. An allosteric post-translational modification is identified by referring to its feature id." [PMID:18706817]
subset: PSI-MI_slim
synonym: "allosteric ptm" EXACT PSI-MI-short []
is_a: ??:xxxx ! biological feature

[Term]
id: 
name: variant
def: "A natural change in a sequence or structure in comparison to a reference entity." []
is_a: ??:xxxx ! biological feature

[Term]
id: 
name: DNA chemical modification
def: "Chemical alterations occurring at the nucleotide level in a DNA molecule. The process can involve covalent modifications (i.e. methylations) or other forms of chemical modification." [PMID:14755292]
synonym: "dna chemical modification" EXACT PSI-ID-short []
synonym: "DNA chemical modification" EXACT PSI-ID-alternate []
synonym: "DNA epigenetic modification" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! biological feature

[Term]
id: 
name: RNA chemical modification
def: "Chemical alterations occurring at the nucleotide level in an RNA molecule. The process can involve covalent modifications (i.e. 2'-O-methylation) or other forms of chemical modification, such as isomerizations (i.e. pseudouridylation)." [PMID:14755292]
synonym: "post-transcriptional modification" EXACT PSI-ID-alternate []
synonym: "rna chemical modification" EXACT PSI-ID-short []
synonym: "RNA chemical modification" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! biological feature

[Term]
id: 
name: carbohydrate chemical modification
def: "Chemical alterations occurring in a carbohydrate molecule. The process can involve covalent modifications (i.e. sulfations) or other forms of chemical modification." [PMID:14755292]
synonym: "carbohydrate chemical modification" EXACT PSI-ID-short []
is_a: ??:xxxx ! biological feature

[Term]
id: 
name: attached carbohydrate
def: "Carbohydrate species chemically attached to proteins or protein regions, or other organic molecules." [PMID:14755292]
comment: Specific carbohydrate species can be represented through the MOD ontology and their representation escapes the scope of this CV.
synonym: "attached glycan" EXACT PSI-ID-alternate []
synonym: "glycosylation" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! biological feature

# experimental features - some of the terms below have child terms (not listed here) that specify the type of feature; these might be added as needed

[Term]
id: 
name: experimental feature
def: "The form of a molecule or molecule region that was actually used to experimentally demonstrate the structure state (i.e. the experimental construct), that may differ from the sequence described by the identifying accession number." [PMID:14755292]
is_a: ??:xxxx ! feature type

[Term]
id: 
name: isotope label
def: "One of several nuclides having the same number of protons in their nuclei and hence having the same atomic number, but differing in the number of neutrons and therefore, in the mass number." [PMID:14755292]
is_a: ??:xxxx ! experimental feature

[Term]
id: 
name: radiolabel
def: "A radiolabelled molecule has radio isotopes among its constituent atoms that can be used to identify, localize or quantify the full molecule." [PMID:14755292]
synonym: "radiolabeled" EXACT PSI-ID-alternate []
synonym: "radiolabelled" EXACT PSI-ID-short []
is_a: ??:xxxx ! isotope label

[Term]
id: 
name: 131i radiolabel
def: "Molecule labelled with 131 radio isotope of iodine atoms." [PMID:14755292]
synonym: "131I" EXACT PSI-ID-alternate []
synonym: "I131" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! radiolabel

[Term]
id: 
name: 14c radiolabel
def: "Molecule labelled with the radio isotope 14 of carbon atoms." [PMID:14755292]
synonym: "14C" EXACT PSI-ID-alternate []
synonym: "C14" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! radiolabel

[Term]
id: 
name: 32p radiolabel
def: "Molecule labelled with the radio isotope 32 of phosphorus atoms." [PMID:14755292]
synonym: "32P" EXACT PSI-ID-alternate []
synonym: "P32" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! radiolabel

[Term]
id: 
name: 33p radiolabel
def: "Molecule labelled with the radio isotope 33 of phosphorus atoms." [PMID:14755292]
synonym: "33P" EXACT PSI-ID-alternate []
synonym: "P33" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! radiolabel

[Term]
id: 
name: 3h radiolabel
def: "Molecules labelled with isotope 3 of hydrogen atoms." [PMID:14755292]
synonym: "3H" EXACT PSI-ID-alternate []
synonym: "H3" EXACT PSI-ID-alternate []
synonym: "tritium" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! radiolabel

[Term]
id: 
name: 35s radiolabel
def: "Molecule labelled with 35 radio isotope of sulfur. Proteins are often metabolically labelled, usually be growth in 35S labelled culture medium." [PMID:14755292]
synonym: "35S" EXACT PSI-ID-alternate []
synonym: "S35" EXACT PSI-ID-alternate []
synonym: "s35 radiolabelled" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! radiolabel

[Term]
id: 
name: 125i radiolabel
def: "Molecule labelled with 125 radio isotope of iodine atoms." [PMID:14755292]
synonym: "125I" EXACT PSI-ID-alternate []
synonym: "I125" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! radiolabel

[Term]
id: 
name: rare isotope label
def: "Molecule can be labelled including rare isotopes among its constituent atoms that can be used to identify, localize or quantify the full molecule." [PMID:14577292]
synonym: "rare isotope label" EXACT PSI-ID-short []
is_a: ??:xxxx ! isotope label

[Term]
id: 
name: 13c label
def: "Molecules labelled with isotope 13 of carbon atoms." [PMID:14577292]
synonym: "13C" EXACT PSI-ID-alternate []
synonym: "C13" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! rare isotope label

[Term]
id: 
name: 15n label
def: "Molecules labelled with isotope 15 of nytrogen atoms." [PMID:14577292]
synonym: "15N" EXACT PSI-ID-alternate []
synonym: "N15" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! rare isotope label

[Term]
id: 
name: 2h label
def: "Molecules labelled with isotope 2 of hydrogen atoms." [PMID:14577292]
subset: PSI-MI_slim
synonym: "2H2" EXACT PSI-ID-alternate []
synonym: "D2" EXACT PSI-ID-alternate []
synonym: "deuterium" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! rare isotope label

[Term]
id: 
name: dye label
def: "Dye coupled to a molecule allowing its identification isolation and monitoring." [PMID:14577292]
synonym: "dye labelled" EXACT PSI-ID-short []
is_a: ??:xxxx ! experimental feature

# many different types of dye label are listed as child terms (not listed here), and can be added to PSI-ID CV as needed

[Term]
id: 
name: tag
def: "Small molecules, peptides or full proteins that can be used as label as they confer some property that facilitates identification, purification and monitoring to the labeled molecule." [PMID:14755292]
is_a: ??:xxxx ! experimental feature

# many different types of tag are listed as child terms (not listed here), and can be added to PSI-ID CV as needed

[Term]
id: 
name: identified peptide
def: "Peptide whose sequence is experimentally identified and can lead to a full protein identification." [PMID:14755292]
is_a: ??:xxxx ! experimental feature

[Term]
id: 
name: spin label
def: "Paramagnetic fragment, most often a cyclic nitroxide derivative, covalently attached to a molecule of interest." [PMID:10966640]
is_a: ??:xxxx ! experimental feature

# different types of spin label are listed as child terms (not listed here), and can be added to PSI-ID CV as needed

[Term]
id: 
name: dna overhang
def: "An overhang is a stretch of unpaired nucleotides in the end of a DNA molecule. These unpaired nucleotides can be in either strand, creating either 3' or 5' overhangs. Longer overhangs are called cohessive ends or sticky ends. They are most often created by restriction endonucleases when they cut DNA. Very often they cut the two DNA strands four base pairs from each other, creating a four-base 3' overhang in the other molecule and a complementary 5' overhang in the other. These ends are called cohessive since they are easily joined back together by a ligase" [PMID:14755292]
synonym: "cohessive ends" EXACT PSI-ID-alternate []
synonym: "sticky ends" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! experimental feature

[Term]
id: 
name: 3 prime overhang
def: "An overhang is a stretch of unpaired nucleotides in the end of a 3' strand of a DNA molecule." [PMID:14755292]
subset: PSI-MI_slim
synonym: "3 prime sticky end" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! dna overhang

[Term]
id: 
name: 5 prime overhang
def: "An overhang is a stretch of unpaired nucleotides in the end of a 5' strand of a DNA molecule." [PMID:14755292]
synonym: "5 prime sticky end" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! dna overhang

[Term]
id: 
name: fluorophore
def: "A fluorophore is a component of a molecule which causes a molecule to be fluorescent. It is a functional group in a molecule which will absorb energy of a specific wavelength and re-emit energy at a different (but equally specific) wavelength. The amount and wavelength of the emitted energy depend on both the fluorophore and the chemical environment of the fluorophore." [PMID:14755292]
is_a: ??:xxxx ! experimental feature

# many different types of fluorophore are listed as child terms (not listed here), and can be added to PSI-ID CV as needed

[Term]
id: 
name: fluorescent dye label
def: "Dye label containing a  fluorophore  which  absorb energy of a specific wavelength and re-emit energy at a different (but equally specific) wavelength." [PMID:14755292]
synonym: "fluorescent dye" EXACT PSI-ID-short []
is_a: ??:xxxx ! dye label
is_a: ??:xxxx ! fluorophore

# many different types of fluorescent dye label are listed as child terms (not listed here), and can be added to PSI-ID CV as needed

[Term]
id: 
name: cross linker
def: "A variety of crosslinkers are used to analyze subunit structure of proteins, protein interactions and various parameters of protein function. Subunit structure is deduced since crosslinkers only bind surface amino residues in relatively close proximity in the native state. Protein interactions are often too weak or transient to be easily detected, but by crosslinking, the interactions can be captured and analyzed." [PMID:14755292]
synonym: "crosslinker" EXACT PSI-ISDalternate []
is_a: ??:xxxx ! experimental feature

[Term]
id: 
name: spdp cross linker
def: "N -Succinimidyl 3-(2-pyridyldithio)-propionate, is heterobifunctional, thiol-cleavable \nand membrane permeable crosslinkers. It contains an amine-reactive N-hydroxysuccinimide (NHS) ester \nthat will react with lysine residues to form a stable amide bond. The other end of the spacer arm is terminated in the pyridyl disulfide group that will react with sulfhydryls to form a reversible disulfide bond." [PMID:17360572]
synonym: "N -Succinimidyl 3-(2-pyridyldithio)-propionate" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! cross linker

[Term]
id: 
name: lc-spdp cross linker
def: "Succinimidyl 6-(3-[2-pyridyldithio]-propionamido)hexanoate, is an heterobifunctional, thiol-cleavable \nand membrane permeable crosslinkers. It contains an amine-reactive N-hydroxysuccinimide (NHS) ester \nthat will react with lysine residues to form a stable amide bond. The other end of the spacer arm is terminated in the pyridyl disulfide group that will react with sulfhydryls to form a reversible disulfide bond. LC-SPDP is a derivative of the classical SPDP with a longer spacer arm." [PMID:17360572]
synonym: "Succinimidyl 6-(3-[2-pyridyldithio]-propionamido)hexanoate" EXACT PSI-ID-alternate []
is_a: ??:xxxx ! spdp cross linker

[Term]
id: 
name: trapping mutant
def: "Permits the identification of substrates of enzymes by mutating residues, usually in the active site such that the enzyme will bind but not act on its substrate." [PMID:9050838]
synonym: "trap-mutant" EXACT PSI-MI-short []
is_a: ??:xxxx ! experimental feature



<!-- INTERACTION CONFIDENCE - A method used to derive a numerical or empirical measure of confidence in a particular interaction, or in the identification of the participants in an interaction. -->
<!-- currently we don't use/need this branch -->



<!-- INTERACTION DETECTION METHOD - Method to determine the interaction. -->
<!-- currently we don't use/need this branch -->
<!-- structure determination methods will be taken from ECO -->



<!-- INTERACTOR TYPE - Molecular species involved in the interaction. -->
<!-- currently we don't use/need this branch -->
<!-- in a later version we might want to annotate type of molecules; as the PSI-MI branch is specific to species involved in an interaction, this needs to be adopted for IDP schema, or we can use a different ontology, e.g. CHEBI? -->



<!-- PARAMETER TYPE - Parameter for enzymatic or binding kinetic studies. -->
<!-- parameters in PSI-MI CV are specific for interactions, e.g. 'temperature of interaction' -->
<!-- can we use ontology of units of measure (OM) to annotate parameter types ? --> 



<!-- PARAMETER UNIT - Controlled vocabulary for kinetic constant units. -->
<!-- except for the root term, available units are general, however only 4 are available in PSI-MI CV (Kelvin, molar, per mole per second, and second -->
<!-- can we use ontology of units of measure (OM) to annotate parameter units ? -->



<!-- PARTICIPANT IDENTIFICATION METHOD - Method to determine the molecules involved in the interaction. -->
<!-- if we want to annotate molecule/experimental construct/region identification methods, we can use terms from ECO CV for this? -->

















# UNUSED TERMS


<!-- UNUSED ALIAS TYPES/SYNONYMS -->

[Term]
id: MI:0305
name: ordered locus name
def: "A name used to represent an ORF in a completely sequenced genome or chromosome. It is generally based on a prefix representing the organism and a number which usually represents the sequential ordering of genes on the chromosome. Depending on the genome sequencing center, numbers are attributed only to protein-coding genes, or also to pseudogenes, or also to tRNAs and other features." [PMID:14755292]
comment: For instance HI0934, Rv3245c, At5g34500, YER456W.
subset: PSI-MI_slim
synonym: "CDS number" EXACT PSI-MI-alternate []
synonym: "locus name" EXACT PSI-MI-short []
synonym: "ONL" EXACT PSI-MI-alternate []
synonym: "Ordered locus name" EXACT PSI-MI-alternate []
synonym: "ORF number" EXACT PSI-MI-alternate []
synonym: "systematic gene number" EXACT PSI-MI-alternate []
is_a: MI:1041 ! synonym

[Term]
id: MI:0306
name: open reading frame name
def: "A name temporarily attributed by a sequencing project to an open reading frame. This name is generally based on a cosmid numbering system." [PMID:14755292]
comment: For instance MtCY277-28c, SYGP-ORF50, SpBC2F12-04, C06E1, CG10954. Also called Sequencing names or Contig names or Temporary ORFNames.
subset: PSI-MI_slim
synonym: "orf name" EXACT PSI-MI-short []
is_a: MI:1041 ! synonym

[Term]
id: MI:0616
name: example
def: "Example generally associated to Cv terms. Test." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0667 ! controlled vocabulary attribute name
is_a: MI:1041 ! synonym

[Term]
id: MI:0673
name: complex synonym
def: "Alternative names to describe a complex." [PMID:14755292]
subset: PSI-MI_slim
synonym: "complex-synonym" EXACT []
is_a: MI:1041 ! synonym

[Term]
id: MI:1315
name: complex recommended name
def: "The most accepted name in the literature for this complex." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1041 ! synonym
created_by: orchard
creation_date: 2013-10-14T15:00:37Z

[Term]
id: MI:1316
name: complex systematic name
def: "A name for a complex built of the component parts of that complex." []
subset: PSI-MI_slim
is_a: MI:1041 ! synonym
created_by: orchard
creation_date: 2013-10-14T15:04:57Z

[Term]
id: MI:2003
name: commercial name
def: "Standard name of drug or any reagent as provided by its manufacturer." [PMID:14755292]
subset: Drugable
synonym: "generic name" EXACT PSI-MI-alternate []
is_a: MI:1041 ! synonym

[Term]
id: MI:2004
name: drug brand name
def: "Alternate names of the drug, brand names from different manufacturers." [PMID:14755292]
subset: Drugable
is_a: MI:1041 ! synonym

[Term]
id: MI:2005
name: drug mixture brand name
def: "Brand names and composition of mixtures that include the drug described in this DrugCard file." [PMID:14755292]
subset: Drugable
synonym: "mix brand name" EXACT PSI-MI-short []
is_a: MI:1041 ! synonym

[Term]
id: MI:2007
name: iupac name
def: "IUPAC or standard chemical name for a drug, or a chemical." [PMID:14755292]
subset: Drugable
is_a: MI:1041 ! synonym


<!-- UNUSED ATTRIBUTE NAMES -->
<!-- some of these (if modified) might be interesting for later versions: descriptions of how PTM affects structure state; description of chemicals/drugs affecting structure state -->

[Term]
id: MI:0664
name: interaction attribute name
def: "Attribute name of annotation associated to an interaction element." [PMID:14755292]
subset: PSI-MI_slim
synonym: "interaction att name" EXACT PSI-MI-short []
is_a: MI:0590 ! attribute name

[Term]
id: MI:0665
name: experiment attribute name
def: "Attribute name of annotation associated to an experiment element." [PMID:14755292]
subset: PSI-MI_slim
synonym: "experiment att name" EXACT PSI-MI-short []
is_a: MI:0590 ! attribute name

[Term]
id: MI:0666
name: participant attribute name
def: "Attribute name of annotation associated to a participant element." [PMID:14755292]
subset: PSI-MI_slim
synonym: "participant att name" EXACT PSI-MI-short []
is_a: MI:0590 ! attribute name

[Term]
id: MI:0667
name: controlled vocabulary attribute name
def: "Attribute name of annotation associated to a CV term." [PMID:14755292]
subset: PSI-MI_slim
synonym: "cv att name" EXACT PSI-MI-short []
is_a: MI:0590 ! attribute name

[Term]
id: MI:0668
name: feature attribute name
def: "Attribute name of annotation associated to a feature element." [PMID:14755292]
subset: PSI-MI_slim
synonym: "feature att name" EXACT PSI-MI-short []
is_a: MI:0590 ! attribute name

[Term]
id: MI:0669
name: organism attribute name
def: "Attribute name of annotation associated to an organism element." [PMID:14755292]
subset: PSI-MI_slim
synonym: "organism att name" EXACT PSI-MI-short []
is_a: MI:0590 ! attribute name

[Term]
id: MI:2086
name: physicochemical attribute name
def: "Chemical and physical properties of a molecule." [PMID:14755292]
subset: Drugable
synonym: "physicochemical att" EXACT PSI-MI-short []
is_a: MI:0590 ! attribute name

[Term]
id: MI:2089
name: bioactive entity attribute name
def: "Properties of a chemical tested or used as a drug, herbicide, insecticide etc." [PMID:14755292]
subset: Drugable
synonym: "bioactive entity att" EXACT PSI-MI-short []
is_a: MI:0590 ! attribute name

[Term]
id: MI:2091
name: structure representation attribute name
def: "Human artefact to describe and report the structure of a molecule." [PMID:14755292]
subset: Drugable
synonym: "struc representation" EXACT PSI-MI-short []
is_a: MI:0590 ! attribute name

[Term]
id: MI:1150
name: affected interaction
def: "For an interaction that has a cooperative effect on a subsequent interaction, this term indicates which subsequent interaction is affected. The affected interaction is identified by referring to its interaction id." [PMID:18641616]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
relationship: part_of MI:1149 ! cooperative interaction
created_by: orchard
creation_date: 2012-06-07T12:26:42Z

[Term]
id: MI:1151
name: participant-ref
def: "Referring to a previously described interaction as a participant allows the description of ordered assembly of molecular complexes in PSI-MI2.5. When one of the components of the preformed complex has a feature, the participant-ref term indicates on which component this feature is located. The component is identified by referring to its participant id in the previous interaction." [PMID:18641616]
subset: PSI-MI_slim
is_a: MI:0668 ! feature attribute name
created_by: orchard
creation_date: 2012-06-07T12:30:48Z

[Term]
id: MI:1152
name: cooperative effect value
def: "This value quantifies the cooperative effect of an interaction on a subsequent interaction. It is the fold change of the affinity or a catalytic parameter of a molecule for one ligand in the absence, versus presence, of a second ligand or a post-translational modification." [PMID:18706817]
subset: PSI-MI_slim
synonym: "cooperative coupling" EXACT []
is_a: MI:0664 ! interaction attribute name
relationship: part_of MI:1149 ! cooperative interaction
created_by: orchard
creation_date: 2012-06-07T12:35:01Z

[Term]
id: MI:1153
name: cooperative effect outcome
def: "For an interaction that has a cooperative effect on a subsequent interaction, this term indicates whether this effect is positive or negative, i.e. whether the subsequent interaction is augmented or diminished." [PMID:18706817]
is_a: MI:1149 ! cooperative interaction
created_by: orchard
creation_date: 2012-06-07T12:40:41Z

[Term]
id: MI:1154
name: positive cooperative effect
def: "This term specifies that an interaction augments a subsequent interaction." [PMID:18706817]
is_a: MI:0664 ! interaction attribute name
is_a: MI:1153 ! cooperative effect outcome
created_by: orchard
creation_date: 2012-06-07T12:42:19Z

[Term]
id: MI:1155
name: negative cooperative effect
def: "This term specifies that an interaction diminishes a subsequent interaction." [PMID:18706817]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1153 ! cooperative effect outcome
created_by: orchard
creation_date: 2012-06-07T12:43:48Z

[Term]
id: MI:1156
name: cooperative mechanism
def: "For an interaction that has a cooperative effect on a subsequent interaction, this term indicates the process that mediates this effect." [PMID:18641616]
subset: PSI-MI_slim
is_a: MI:1149 ! cooperative interaction
created_by: orchard
creation_date: 2012-06-07T12:46:30Z

[Term]
id: MI:1157
name: allostery
def: "Reciprocal energetic coupling between two binding events at distinct sites on the same molecule. The first binding event alters the binding or catalytic properties of the molecule for the second binding event." [PMID:18641616, PMID:18706817]
subset: PSI-MI_slim
synonym: "allosteric regulation" EXACT []
is_a: MI:0664 ! interaction attribute name
is_a: MI:1156 ! cooperative mechanism
created_by: orchard
creation_date: 2012-06-07T12:50:20Z

[Term]
id: MI:1158
name: pre-assembly
def: "A non-allosteric mechanism where the strength of an interaction depends on whether or not a particular molecular complex already exists." [PMID:18641616]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1156 ! cooperative mechanism
created_by: orchard
creation_date: 2012-06-07T12:52:44Z

[Term]
id: MI:1159
name: allosteric molecule
def: "A molecule whose binding or catalytic properties at one site are altered by allosteric post-translational modification or binding of an allosteric effector at a distinct site. An allosteric molecule is identified by referring to its participant id." [PMID:18706817]
subset: PSI-MI_slim
is_a: MI:0500 ! biological role
is_a: MI:0664 ! interaction attribute name
relationship: part_of MI:1149 ! cooperative interaction
created_by: orchard
creation_date: 2012-06-07T12:55:09Z

[Term]
id: MI:1160
name: allosteric effector
def: "A ligand that elicits an allosteric response upon binding to a target molecule." [PMID:18706817]
subset: PSI-MI_slim
is_a: MI:0500 ! biological role
is_a: MI:0664 ! interaction attribute name
relationship: part_of MI:1149 ! cooperative interaction
created_by: orchard
creation_date: 2012-06-07T12:57:50Z

[Term]
id: MI:1161
name: allosteric response
def: "This term describes the effect of an allosteric binding event. It specifies which properties of the allosteric molecule are altered, i.e. whether the interaction alters either (a) binding or (b) catalytic properties of the allosteric molecule at a site distinct from the allosteric site." []
subset: PSI-MI_slim
is_a: MI:1149 ! cooperative interaction
created_by: orchard
creation_date: 2012-06-07T01:05:17Z

[Term]
id: MI:1162
name: allosteric k-type response
def: "An allosteric response in which the affinity of a molecule is altered." [PMID:18706817]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1161 ! allosteric response
created_by: orchard
creation_date: 2012-06-07T01:08:01Z

[Term]
id: MI:1163
name: allosteric v-type response
def: "An allosteric response in which catalysis (kcat or Vmax) of an enzyme is altered." [PMID:18706817]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1161 ! allosteric response
created_by: orchard
creation_date: 2012-06-07T01:09:07Z

[Term]
id: MI:1164
name: allosteric mechanism
def: "The process that mediates the allosteric response of a molecule upon allosteric post-translational modification or binding of an allosteric effector." []
is_a: MI:1149 ! cooperative interaction
created_by: orchard
creation_date: 2012-06-07T01:10:45Z

[Term]
id: MI:1165
name: allosteric change in structure
def: "The allosteric mechanism where changes in the local structure of an allosteric molecule result in altered binding or catalytic properties." [PMID:18706817]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1164 ! allosteric mechanism
created_by: orchard
creation_date: 2012-06-07T01:16:20Z

[Term]
id: MI:1166
name: allosteric change in dynamics
def: "The allosteric mechanism where changes in the local dynamics of an allosteric molecule result in altered binding or catalytic properties." [PMID:18706817]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1164 ! allosteric mechanism
created_by: orchard
creation_date: 2012-06-07T01:17:54Z

[Term]
id: MI:1167
name: allostery type
def: "This term indicates the chemical relationship between the two ligands whose binding is allosterically coupled." [PMID:18706817]
subset: PSI-MI_slim
is_a: MI:1149 ! cooperative interaction
created_by: orchard
creation_date: 2012-06-07T01:19:57Z

[Term]
id: MI:1168
name: heterotropic allostery
def: "The type of allostery that occurs when the two ligands whose binding is allosterically coupled are not chemically identical." [PMID:18706817]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1167 ! allostery type
created_by: orchard
creation_date: 2012-06-07T01:21:25Z

[Term]
id: MI:1169
name: homotropic allostery
def: "The type of allostery that occurs when the two ligands whose binding is allosterically coupled are chemically identical." [PMID:18706817]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1167 ! allostery type
created_by: orchard
creation_date: 2012-06-07T01:22:35Z

[Term]
id: MI:1170
name: pre-assembly response
def: "This term describes the way in which preformation of a molecular complex has a non-allosteric cooperative effect on subsequent interactions of its components." [PMID:18641616]
subset: PSI-MI_slim
is_a: MI:1149 ! cooperative interaction
created_by: orchard
creation_date: 2012-06-07T01:24:42Z

[Term]
id: MI:1171
name: composite binding site formation
def: "The preformation of a complex results in the generation of a continuous binding site that spans more than one component of this complex. The functional binding site does not exist outside the context of the preformed complex." [PMID:18641616]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1170 ! pre-assembly response
created_by: orchard
creation_date: 2012-06-07T01:25:50Z

[Term]
id: MI:1172
name: altered physicochemical compatibility
def: "The addition of a PTM to an interaction interface affects the physicochemical compatibility of the binding site with its binding partner. This can either induce or enhance an interaction, or result in inhibition or even abrogation of an interaction. Multisite modification can mediate rheostatic regulation of the interaction." [PMID:22480932]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1170 ! pre-assembly response
created_by: orchard
creation_date: 2012-06-07T01:26:56Z

[Term]
id: MI:1173
name: binding site hiding
def: "The occurrence of overlapping or adjacent, mutually exclusive binding sites promotes competitive binding. When there is a large difference in affinity of the different sites or in local abundance of competitors, binding at one site results in hiding of the second site, thereby precluding it from interacting when the hiding molecule is present." [PMID:22480932]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1170 ! pre-assembly response
created_by: orchard
creation_date: 2012-06-07T01:28:07Z

[Term]
id: MI:1174
name: configurational pre-organization
def: "Multivalent ligands form multiple discrete interactions with one or more binding partners. In some cases, An initial binding event can pre-organize other sites for binding. This reduces the degrees of freedom of these sites, thus reducing the entropic costs of their interactions. In addition, the combined strength of multiple interactions increases the enthalpic stability of each interaction (avidity effect). As a result of such effects, interactions of this kind can have a cooperative effect on subsequent interactions." [PMID:18641616]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1170 ! pre-assembly response
created_by: orchard
creation_date: 2012-06-07T01:29:13Z

[Term]
id: MI:1175
name: allosteric post-translational modification
def: "A post-translational modification that elicits an allosteric response upon addition to a target molecule. An allosteric post-translational modification is identified by referring to its feature id." [PMID:18706817]
subset: PSI-MI_slim
synonym: "allosteric ptm" EXACT PSI-MI-short []
is_a: MI:0252 ! biological feature
is_a: MI:0664 ! interaction attribute name
relationship: part_of MI:1149 ! cooperative interaction
created_by: orchard
creation_date: 2012-06-07T01:33:16Z

[Term]
id: MI:0598
name: feature constraint
def: "The feature constraint free text will specificity whether a biological feature is shown to be possible (just observed) or required (experimentally demonstrated to be necessary for an interaction)." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0668 ! feature attribute name

[Term]
id: MI:0616
name: example
def: "Example generally associated to Cv terms. Test." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0667 ! controlled vocabulary attribute name
is_a: MI:1041 ! synonym

[Term]
id: MI:2112
name: chemical stability at pH 2
def: "Chemical stability at pH 2" [PMID:14755292]
comment: Qualitative prediction of this parameter is possible.
subset: Drugable
synonym: "chem stab ph 2" EXACT PSI-MI-short []
is_a: MI:2055 ! chemical stability

[Term]
id: MI:2147
name: chemical stability at pH 7.4
def: "Chemical stabilityat at pH 7.4" [PMID:14755292]
comment: Qualitative prediction of this parameter is possible.
subset: Drugable
synonym: "chem stab ph 7.4" EXACT PSI-MI-short []
is_a: MI:2055 ! chemical stability

[Term]
id: MI:2133
name: neutralization by glucuronidation or sulfatation
def: "Neutralization of a compound occuring via its glucuronidation or sulfatation." [PMID:14755292]
comment: Quantitative prediction of this parameter is possible.
subset: Drugable
synonym: "neutraliz gluc/sulf" EXACT PSI-MI-short []
is_a: MI:2048 ! drug biotransformation

[Term]
id: MI:2128
name: ABCB1 transporter substrate
def: "Substrate for the representitive member of the ABC transprorter family ABCB1 (MDR1, pgy1, P08183). ABC transporters preventing uptake or facilitating clearance of toxic substances, playing an important role in drug excretion through the bile." [PMID:14755292]
comment: Algorithms have been published to predict the value of this parameter but the quality of the prediction is unknown.
subset: Drugable
synonym: "abcb1 substrate" EXACT PSI-MI-short []
synonym: "pgp(mdr1) substrate " EXACT PSI-MI-alternate []
is_a: MI:2121 ! transporter binding

[Term]
id: MI:2129
name: bile transporter substrate
def: "Substrate of the bile acid carrier system in both the intestinal tract and the liver. System catalyses of the transfer of bile acid from one side of the membrane to the other. Bile acids are any of a group of steroid carboxylic acids occurring in bile, where they are present as the sodium salts of their amides with glycine or taurine." [PMID:14755292]
comment: The prediction of the value for this paramater is currently not possible.
subset: Drugable
synonym: "bile trans substrate" EXACT PSI-MI-short []
is_a: MI:2121 ! transporter binding

[Term]
id: MI:2023
name: material safety data sheet
def: "Material Safety Data Sheet (if it exists). A Material Safety Data Sheet (MSDS) is designed to provide both workers and emergency personnel with the proper procedures for handling or working with a particular substance. MSDS's include information such as physical data (melting point, boiling point, flash point etc.), toxicity, health effects, first aid, reactivity, storage, disposal, protective equipment, andspill/leak procedures. These are of particular use if a spill or other accident occurs." [PMID:14755292]
subset: Drugable
synonym: "msds" EXACT PSI-MI-short []
synonym: "MSDS Material Safety Sheet" EXACT PSI-MI-alternate []
is_a: MI:2086 ! physicochemical attribute name

[Term]
id: MI:2055
name: chemical stability
def: "chemical stability occurs when a substance is in a (dynamic) chemical equilibrium with its environment. In this well-defined state, the substance is expected to persist indefinitely (assuming that the environment does not change).  A substance which is not chemically stable (yet exists) is metastable or kinetically persistent." [PMID:14755292]
subset: Drugable
synonym: "thermodynamic stability" EXACT PSI-MI-alternate []
is_a: MI:2086 ! physicochemical attribute name

[Term]
id: MI:2084
name: organisms affected
def: "Names of organisms which are affected, positively or negatively, by the drug." [PMID:14755292]
subset: Drugable
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2115
name: pharmacokinetics attribute name
def: "Determination of the fate of substances administered externally to a living organism i.e. the study of what the body does to a drug." [PMID:14755292]
subset: Drugable
is_a: MI:2086 ! physicochemical attribute name

[Term]
id: MI:2121
name: transporter binding
def: "Substrate of a carrier system allowing the intake of an agent into an organ or part of body." [PMID:14755292]
comment: The prediction of the value for this parameter is currently not possible.
subset: Drugable
is_a: MI:2115 ! pharmacokinetics attribute name

[Term]
id: MI:2132
name: gsh adducts
def: "Derivative molecule which has formed from a reaction with glutathione." [PMID:14755292]
comment: Algorithms have been published to predict the value of this parameter but the quality of the prediction is unknown.
subset: Drugable
is_a: MI:2115 ! pharmacokinetics attribute name

[Term]
id: MI:2133
name: neutralization by glucuronidation or sulfatation
def: "Neutralization of a compound occuring via its glucuronidation or sulfatation." [PMID:14755292]
comment: Quantitative prediction of this parameter is possible.
subset: Drugable
synonym: "neutraliz gluc/sulf" EXACT PSI-MI-short []
is_a: MI:2048 ! drug biotransformation

[Term]
id: MI:2135
name: toxicity attribute name
def: "The mechanism by which a substance can harm humans or animals." [PMID:14755292]
subset: Drugable
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2136
name: herg binding
def: "Binds to the hERG (human Ether-a-go-go Related Gene) (Q12809) which encodes the Kv11.1 potassium ion channel responsible for the repolarizing IKr current in the cardiac action potential." [PMID:14755292]
comment: Algorithms have been published to predict the value of this parameter but the quality of the prediction is unknown.
subset: Drugable
is_a: MI:2135 ! toxicity attribute name

[Term]
id: MI:2137
name: genotoxicity
def: "Tendency of a bioactive entity to induce damage at the level of the gene." [PMID:14755292]
comment: Algorithms have been published to predict the value of this parameter but the quality of the prediction is unknown.
subset: Drugable
is_a: MI:2135 ! toxicity attribute name

[Term]
id: MI:2138
name: mutagenicity
def: "Tendency of a bioactive entity to induce genetic mutations at the nucleotide level e.g. substitution of nucleotide base-pairs and insertions and deletions of one or more nucleotides in DNA sequences." [PMID:14755292]
comment: Algorithms have been published to predict the value of this parameter but the quality of the prediction is unknown.
subset: Drugable
is_a: MI:2135 ! toxicity attribute name

[Term]
id: MI:2139
name: carcinogenicity
def: "Tendency of a bioactive entity to induce a cancer." [PMID:14755292]
comment: Algorithms have been published to predict the value of this parameter but the quality of the prediction is unknown.
subset: Drugable
synonym: "cancerogenicity" EXACT PSI-MI-alternate []
is_a: MI:2135 ! toxicity attribute name

[Term]
id: MI:2140
name: chromosome damage
def: "Tendency of a bioactive entity to induce damage at the level of the chromosome e.g. induce a change in chromosome structure and number." [PMID:14755292]
comment: Algorithms have been published to predict the value of this parameter but the quality of the prediction is unknown.
subset: Drugable
is_a: MI:2135 ! toxicity attribute name

[Term]
id: MI:2141
name: hepatotoxicity
def: "Tendency of a bioactive entity to affect liver function." [PMID:14755292]
comment: Algorithms have been published to predict the value of this parameter but the quality of the prediction is unknown.
subset: Drugable
is_a: MI:2135 ! toxicity attribute name

[Term]
id: MI:2142
name: phospholipidosis
def: "Causes excess phospholipids to accumulate within cells." [PMID:14755292]
comment: Algorithms have been published to predict the value of this parameter but the quality of the prediction is unknown.
subset: Drugable
is_a: MI:2135 ! toxicity attribute name

[Term]
id: MI:2151
name: other drug interaction
def: "Effect of additional drug treatments on a given drug action." [PMID:14755292]
subset: Drugable
synonym: "drug interaction" EXACT PSI-MI-short []
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2152
name: food interaction
def: "Effect of food ingestion on a given drug treatment." [PMID:14755292]
comment: IntAct MeSH term or SNOWMAN.
subset: Drugable
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2206
name: observed nucleic acid chemical modification
def: "Chemical modification observed on a nucleic acid molecule in the context of an interaction. Modifications involving full nucleotide substitutions/deletions are excluded from this definition." [PMID:14755292]
subset: PSI-MI_slim
synonym: "observed na chemical modification" EXACT PSI-MI-alternate []
synonym: "observed nucleic acid chemical modification" EXACT PSI-MI-short []
is_a: MI:0668 ! feature attribute name
created_by: ppm
creation_date: 2016-01-21T14:50:29Z

[Term]
id: MI:2207
name: resulting nucleic acid chemical modification
def: "Chemical modification observed on an RNA molecule resulting subsequently of an interaction. Modifications involving full nucleotide substitutions/deletions are excluded from this definition." [PMID:14755292]
subset: PSI-MI_slim
synonym: "resulting na chemical modification" EXACT PSI-MI-alternate []
synonym: "resulting nucleic acid chemical modification" EXACT PSI-MI-short []
is_a: MI:2206 ! observed nucleic acid chemical modification
created_by: ppm
creation_date: 2016-01-21T15:02:23Z

[Term]
id: MI:2208
name: prerequisite-nucleic acid chemical modification
def: "Chemical modification observed on a nucleic acid molecule required for an interaction to occur. Modifications involving full nucleotide substitutions/deletions are excluded from this definition." [PMID:14755292]
subset: PSI-MI_slim
synonym: "prerequisite-na chemical modification" EXACT PSI-MI-alternate []
synonym: "prerequisite-nucleic acid chemical modification" EXACT PSI-MI-short []
is_a: MI:2206 ! observed nucleic acid chemical modification
created_by: ppm
creation_date: 2016-01-21T15:12:35Z

[Term]
id: MI:2209
name: nucleic acid chemical modification decreasing an interaction
def: "Chemical modification observed on a nucleic acid molecule observed to decrease the strength or rate of an interaction. Modifications involving full nucleotide substitutions/deletions are excluded from this definition." [PMID:14755292]
synonym: "na chemical modification decreasing" EXACT PSI-MI-short []
synonym: "nucleic acid chemical modification decreasing an interaction" EXACT PSI-MI-alternate []
is_a: MI:2206 ! observed nucleic acid chemical modification
created_by: ppm
creation_date: 2016-01-21T15:17:08Z

[Term]
id: MI:2210
name: nucleic acid chemical modification disrupting an interaction
def: "Chemical modification observed on a nucleic acid molecule observed to disrupt an interaction. Modifications involving full nucleotide substitutions/deletions are excluded from this definition." [PMID:14755292]
subset: PSI-MI_slim
synonym: "na chemical modification disrupting" EXACT PSI-MI-short []
synonym: "nucleic acid chemical modification disrupting an interaction" EXACT PSI-MI-alternate []
is_a: MI:2206 ! observed nucleic acid chemical modification
created_by: ppm
creation_date: 2016-01-21T15:18:52Z

[Term]
id: MI:2211
name: nucleic acid chemical modification increasing an interaction
def: "Chemical modification observed on a nucleic acid molecule observed to increase the strength or rate of an interaction. Modifications involving full nucleotide substitutions/deletions are excluded from this definition." [PMID:14755292]
subset: PSI-MI_slim
synonym: "na chemical modification increasing" EXACT PSI-MI-short []
synonym: "nucleic acid chemical modification increasing an interaction" EXACT PSI-MI-alternate []
is_a: MI:2206 ! observed nucleic acid chemical modification
created_by: ppm
creation_date: 2016-01-21T15:25:51Z

[Term]
id: MI:2097
name: anti-convulsant
def: "Therapeutic category or general category of drug -anti-convulsant" [PMID:14755292]
subset: Drugable
is_a: MI:2041 ! drug category

[Term]
id: MI:2098
name: anti-bacterial
def: "Therapeutic category or general category of drug -anti-bacterial" [PMID:14755292]
subset: Drugable
is_a: MI:2041 ! drug category

[Term]
id: MI:2099
name: fda approved drug
def: "A drug licensed for sale in the USA by the FDA." [PMID:14755292]
subset: Drugable
is_a: MI:2040 ! drug type

[Term]
id: MI:2100
name: experimental drug
def: "A drug which has yet to be formally approved for the indication which it is currently being used to treat." [PMID:14755292]
subset: Drugable
is_a: MI:2040 ! drug type

[Term]
id: MI:2101
name: biotech drug
def: "A natural product, such as a protein or peptide, which is produced used biotechnology as a drug." [PMID:14755292]
subset: Drugable
is_a: MI:2040 ! drug type

[Term]
id: MI:2102
name: nutraceutical drug
def: "A drug which may also be regarded as a foodstuff." [PMID:14755292]
subset: Drugable
is_a: MI:2040 ! drug type

[Term]
id: MI:2040
name: drug type
def: "Type of drug (approved, experimental, biotech, nutraceutical)" [PMID:14755292]
subset: Drugable
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2148
name: investigational drug
def: "A drug currently under clinical development." [PMID:14755292]
comment: Intact.
subset: Drugable
is_a: MI:2040 ! drug type

[Term]
id: MI:2149
name: withdrawn drug
def: "A drug for which the licencing for prescriptive use has been withdrawn." [PMID:14755292]
comment: Intact.
subset: Drugable
is_a: MI:2040 ! drug type

[Term]
id: MI:2150
name: illicit drug
def: "A drug which has not been approved for sale, a drug taken for recreational purposes or a licensed drug sold without a prescription." [PMID:14755292]
subset: Drugable
is_a: MI:2040 ! drug type

[Term]
id: MI:0623
name: inhibition
def: "The interaction between the proteins or the formation of a complex is disrupted by a biological molecule or by a modification of the interactors." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name

[Term]
id: MI:0624
name: stimulant
def: "Reaction occurs at a faster rate in the presence of this compound or molecule i.e. the molecule directly physically co-operates with the interaction. Reaction may not occur at all in the absence of this molecule." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name

[Term]
id: MI:0625
name: agonist
def: "Any chemical applied externally to cells or any type of environmental condition, such as hypoxia, that stimulates an interaction, potentially by causing modification of one or more of the interactors." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name

[Term]
id: MI:0626
name: antagonist
def: "Any chemical applied externally to cells or any type of environmental condition, such as hypoxia, that inhibits an interaction, potentially by alteration of amount or binding affinity of one or more of the interactors." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name

[Term]
id: MI:0925
name: observed-ptm
def: "Post translational modification observed on a protein in the context of an interaction." [PMID:14755292]
subset: PSI-MI_slim
synonym: "observed ptm" EXACT PSI-MI-alternate []
synonym: "observed-ptm" EXACT PSI-MI-short []
is_a: MI:0668 ! feature attribute name

[Term]
id: MI:1223
name: ptm decreasing an interaction
def: "Post translational modification on a protein observed to decrease the strength or rate of an interaction." [PMID:14744292]
subset: PSI-MI_slim
synonym: "decreasing-ptm" EXACT PSI-MI-short []
is_a: MI:0925 ! observed-ptm
created_by: orchard
creation_date: 2012-06-11T12:56:47Z

[Term]
id: MI:1224
name: ptm increasing an interaction
def: "Post translational modification on a protein observed to increase the strength or rate of an interaction." [PMID:14744292]
subset: PSI-MI_slim
synonym: "increasing-ptm" EXACT PSI-MI-short []
is_a: MI:0925 ! observed-ptm
created_by: orchard
creation_date: 2012-06-11T12:58:43Z

[Term]
id: MI:1225
name: ptm disrupting an interaction
def: "Post translational modification on a protein observed to disrupt the strength or rate of an interaction." [PMID:14744292]
subset: PSI-MI_slim
synonym: "disrupting-ptm" EXACT PSI-MI-short []
is_a: MI:0925 ! observed-ptm
created_by: orchard
creation_date: 2012-06-11T12:59:28Z

[Term]
id: MI:0638
name: prerequisite-ptm
def: "Post translational modification required for an interaction to occur." [PMID:14755292]
subset: PSI-MI_slim
synonym: "prerequisite ptm" EXACT PSI-MI-alternate []
synonym: "prerequisite-ptm" EXACT PSI-MI-short []
synonym: "required ptm" EXACT PSI-MI-alternate []
synonym: "required-ptm" EXACT PSI-MI-alternate []
is_a: MI:0925 ! observed-ptm

[Term]
id: MI:0639
name: resulting-ptm
def: "Post translational modification occurs subsequently to an interaction." [PMID:14755292]
subset: PSI-MI_slim
synonym: "resulting ptm" EXACT PSI-MI-alternate []
synonym: "resulting-ptm" EXACT PSI-MI-short []
is_a: MI:0925 ! observed-ptm

[Term]
id: MI:0948
name: kinetic conditions
def: "A brief description (such as temp, pH) of the conditions under which a kinetic measurment has been performed." [PMID:14755292]
subset: PSI-MI_slim
synonym: "kinetic_conditions" EXACT PSI-MI-short []
is_a: MI:0664 ! interaction attribute name

[Term]
id: MI:1334
name: rigid
def: "A global unique identifier to identify interactions that are identical. A RIG identifier (RIGID) is constructed by concatenating ROGID MI:1335 (after sorting them in ascending lexicographical order ), applying the SHA-1 algorithm to the resulting string, converting the digest to its base64 representation and removing all trailing \"=\" characters used for padding." [PMID:18823568]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1212 ! checksum
created_by: orchard
creation_date: 2014-01-09T11:17:32Z

[Term]
id: MI:2006
name: biotech product preparation
def: "Description of the drug (for biotech drugs) describing its composition and/or preparation." [PMID:14755292]
subset: Drugable
synonym: "biotech prep" EXACT PSI-MI-short []
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2008
name: chemical formula
def: "Chemical formula describing atomic or elemental composition" [PMID:14755292]
subset: Drugable
is_a: MI:2086 ! physicochemical attribute name

[Term]
id: MI:2009
name: chemical structure
def: "Image of the drug structure (if small molecule) or its sequence (if biotech drug)" [PMID:14755292]
subset: Drugable
is_a: MI:2086 ! physicochemical attribute name

[Term]
id: MI:2010
name: standard inchi
def: "IUPAC International Chemical Identifier (InChI) - a machine-readable character string describing a chemical structure, developed by IUPAC and the InChI Trust as a standard to allow interoperability and linking between chemical resources. The standard InChI differs from the non-standard InChI in that it is generated with a fixed set of parameters, ensuring consistency between different resources. The current version of the standard InChI software is 1.03." [PMID:14755292]
subset: PSI-MI_slim
synonym: "inchi id" RELATED []
synonym: "standard inchi" EXACT PSI-MI-short []
is_a: MI:1212 ! checksum
is_a: MI:2091 ! structure representation attribute name

[Term]
id: MI:2039
name: smiles string
def: "SMILES string corresponding to drug structure" [PMID:14755292]
subset: Drugable
is_a: MI:1212 ! checksum
is_a: MI:2091 ! structure representation attribute name

[Term]
id: MI:2040
name: drug type
def: "Type of drug (approved, experimental, biotech, nutraceutical)" [PMID:14755292]
subset: Drugable
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2041
name: drug category
def: "Therapeutic category or general category of drug (anti-convulsant, antibacterial, etc.)." [PMID:14755292]
subset: Drugable
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2042
name: disease indication
def: "Description or common names of diseases that the drug is used to treat." [PMID:14755292]
comment: Source of further terms could be MeSH term or SNOWMAN.
subset: Drugable
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2043
name: pharmacology
def: "Text description of how the drug works at a clinical or physiological level." [PMID:14755292]
subset: Drugable
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2044
name: mechanism of action
def: "Description of how the drug works or what it binds to at a molecular level." [PMID:14755292]
subset: Drugable
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2048
name: drug biotransformation
def: "The chemical conversion of drugs to other compounds in the body, excluding degradation due to any inherent chemical instability of drugs in biological media." [PMID:14755292]
subset: Drugable
synonym: "drug metabolism" EXACT PSI-MI-short []
is_a: MI:2115 ! pharmacokinetics attribute name

[Term]
id: MI:2050
name: dosage form
def: "How the drug is dispensed (tablets, capsules, solutions), packing material." [PMID:14755292]
subset: Drugable
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2051
name: patient information
def: "Information on the disease indications and treatment regime for the drug. May also include contra-indications." [PMID:14755292]
subset: Drugable
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2053
name: contraindications
def: "Cautions or conditions indicating why or when the drug should not be taken or prescribed." [PMID:14755292]
subset: Drugable
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2130
name: cyp-450 inhibition
def: "Inhibitor of one or more of the family of cytochrome p450 enzymes, probably the most important elements of oxidative metabolism of exogenous compounds." [PMID:14755292]
comment: Algorithms have been published to predict the value of this parameter but the quality of the prediction is unknown.
subset: Drugable
synonym: "cyp-450 inhibition" EXACT PSI-MI-alternate []
synonym: "Cytochrome P450 inhibition" EXACT PSI-MI-alternate []
is_a: MI:2135 ! toxicity attribute name

[Term]
id: MI:2131
name: metabolite identification
def: "Identification of the breakdown products of a substance, either through chemical instability or the actions of enzymes within the body" [PMID:14755292]
comment: Algorithms have been published to predict the value of this parameter but the quality of the prediction is unknown.
subset: Drugable
synonym: "metabolite identific" EXACT PSI-MI-short []
is_a: MI:2115 ! pharmacokinetics attribute name

[Term]
id: MI:2278
name: polymer chain length
def: "Length of a repetitive polymer chain. Applicable to carbohydrates and other non-protein, non-nucleic acid polymers." [PMID:14755292]
subset: PSI-MI_slim
synonym: "polymer chain length" EXACT PSI-MI-short []
is_a: MI:0666 ! participant attribute name
created_by: ppm
creation_date: 2017-07-05T10:27:19Z

[Term]
id: MI:1333
name: rogid
def: "SEGUID's are SHA-1 keys written in canonical base64 form with trailing = characters removed. ROG identifiers concatenate a SEGUID with a numerical taxonomy identifier. Therefore, the allowable characters in a SEGUID or ROG identifier are (in ascending ASCII or Unicode value):\n+/0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz\nLists of SEGUID or ROG identifiers were sorted in ascending ASCII-based lexicographical order." [PMID:18823568]
subset: PSI-MI_slim
is_a: MI:1212 ! checksum
created_by: orchard
creation_date: 2014-01-09T11:17:18Z

[Term]
id: MI:1334
name: rigid
def: "A global unique identifier to identify interactions that are identical. A RIG identifier (RIGID) is constructed by concatenating ROGID MI:1335 (after sorting them in ascending lexicographical order ), applying the SHA-1 algorithm to the resulting string, converting the digest to its base64 representation and removing all trailing \"=\" characters used for padding." [PMID:18823568]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1212 ! checksum
created_by: orchard
creation_date: 2014-01-09T11:17:32Z

[Term]
id: MI:1150
name: affected interaction
def: "For an interaction that has a cooperative effect on a subsequent interaction, this term indicates which subsequent interaction is affected. The affected interaction is identified by referring to its interaction id." [PMID:18641616]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
relationship: part_of MI:1149 ! cooperative interaction
created_by: orchard
creation_date: 2012-06-07T12:26:42Z

[Term]
id: MI:1151
name: participant-ref
def: "Referring to a previously described interaction as a participant allows the description of ordered assembly of molecular complexes in PSI-MI2.5. When one of the components of the preformed complex has a feature, the participant-ref term indicates on which component this feature is located. The component is identified by referring to its participant id in the previous interaction." [PMID:18641616]
subset: PSI-MI_slim
is_a: MI:0668 ! feature attribute name
created_by: orchard
creation_date: 2012-06-07T12:30:48Z

[Term]
id: MI:0620
name: search-url-ascii
def: "Search URL to retrieve an external entry in ASCII format. Generally associated to Cv Database terms." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0667 ! controlled vocabulary attribute name

[Term]
id: MI:0629
name: complex-properties
def: "Information on the complex being annotated. Attribute generally associated to an interaction." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:0665 ! experiment attribute name

[Term]
id: MI:0970
name: inchi key
def: "InChIKeys consist of 14 characters resulting from a hash of the connectivity information of the InChI, followed by a hyphen, followed by 9 characters resulting from a hash of the remaining layers of the InChI, followed by a single character indication the version of InChI used, another hyphen, followed by single checksum character" [PMID:15889163]
subset: Drugable
synonym: "inchi key" EXACT PSI-MI-short []
is_a: MI:1212 ! checksum
is_a: MI:2091 ! structure representation attribute name

[Term]
id: MI:0977
name: no-imex-export
def: "Prevents export of experiment and associated interactions to IMEx" [PMID:17893861]
subset: PSI-MI_slim
is_a: MI:0665 ! experiment attribute name
created_by: orchard
creation_date: 2010-04-21T02:49:48Z

[Term]
id: MI:0978
name: author-name
def: "Author given name for a participant, not commonly found in source databases." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0666 ! participant attribute name
created_by: orchard
creation_date: 2010-04-21T02:55:39Z


<!-- UNUSED CROSS-REFERENCE TYPES -->

[Term]
id: MI:0242
name: gene ontology definition reference
def: "This qualifier is used when the crossreference is imported from the Gene Ontology tag definition_reference." [PMID:14755292]
subset: PSI-MI_slim
synonym: "go-definition-ref" EXACT PSI-MI-short []
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:0685
name: source reference
def: "Publication or document describing the originating resource where an interaction, or other curated information, was first described." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:0868
name: author identifier
def: "Author published identifier." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:0869
name: originally assigned identifier
def: "Identifier assigned when the record was created by a source database." [PMID:14755292]
subset: PSI-MI_slim
synonym: "original identifier" EXACT PSI-MI-short []
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:0951
name: chain parent sequence reference
def: "Reference to the master sequence from which this chain has been derived." [PMID:17925023]
subset: PSI-MI_slim
synonym: "chain-parent" EXACT PSI-MI-short []
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:1102
name: mapped-identity
def: "Sequence has been computationally remapped following removal or update of the original sequence in the underlying sequence database." [PMID:14760721]
synonym: "mapped-identity" EXACT PSI-MI-short []
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:2284
name: complex component
def: "Indicates that the cross-referenced molecule is a component of a containing complex." [PMID:25313161]
subset: PSI-MI_slim
synonym: "complex component" EXACT PSI-MI-short []
synonym: "complex-component" EXACT PSI-MI-alternate []
is_a: MI:0353 ! cross-reference type


<!-- UNUSED FEATURE RANGE STATUS -->

[Term]
id: MI:2293
name: 5' position
def: "Term describing the upstream end of a nucleotide sequence." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0333 ! feature range status
created_by: pporras
creation_date: 2018-09-14T09:15:05Z

[Term]
id: MI:2294
name: 5' range
def: "Term describing the upstream region of a nucleotide sequence, exact coordinates not available." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0333 ! feature range status
created_by: pporras
creation_date: 2018-09-14T09:25:33Z

[Term]
id: MI:2295
name: 3' position
def: "Term describing the downstream end of a nucleotide sequence." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0333 ! feature range status
created_by: pporras
creation_date: 2018-09-14T09:26:47Z

[Term]
id: MI:2296
name: 3' range
def: "Term describing the downstream region of a nucleotide sequence, exact coordinates not available." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0333 ! feature range status
created_by: pporras
creation_date: 2018-09-14T09:27:33Z










































<!-- PSI-MI CV -->

format-version: 1.2
date: 14:12:2020 14:01
saved-by: pporras
auto-generated-by: OBO-Edit 2.3.1
subsetdef: Drugable "Drugable Genome Project"
subsetdef: PSI-MI_slim "Subset of PSI-MI"
subsetdef: PSI-MOD_slim "subset of protein modifications"
synonymtypedef: DeltaMass-label "Label from MS DeltaMass" EXACT
synonymtypedef: PSI-MI-alternate "Alternate label curated by PSI-MI" EXACT
synonymtypedef: PSI-MI-short "Unique short label curated by PSI-MI" EXACT
synonymtypedef: PSI-MOD-alternate "Alternate label curated by PSI-MOD" EXACT
synonymtypedef: PSI-MOD-short "Unique short label curated by PSI-MOD" EXACT
synonymtypedef: PSI-MS-label "Agreed label from MS communfinteraction ity" RELATED
synonymtypedef: RESID-alternate "Alternate name from RESID" EXACT
synonymtypedef: RESID-misnomer "Misnomer label from RESID" RELATED
synonymtypedef: RESID-name "Name from RESID" EXACT
synonymtypedef: RESID-systematic "Systematic name from RESID" EXACT
synonymtypedef: UniMod-alternate "Alternate name from UniMod" RELATED
synonymtypedef: UniMod-description "Description (full_name) from UniMod" RELATED
synonymtypedef: UniMod-interim "Interim label from UniMod" RELATED
synonymtypedef: UniMod-label "Label (title) from UniMod" RELATED
synonymtypedef: UniProt-feature "Protein feature description from UniProtKB" EXACT
default-namespace: PSI-MI
remark: Notes:
remark: Each of the top level terms in this file is the root term of an independent controlled vocabulary
remark: mapping an element of the PSI Molecular Interaction XML schema.
remark: The correct use of these vocabularies in the PSI Molecular Interaction XML schema is
remark: formalized in a mapping file available at http://www.psidev.info/files/validator/xml/MI-CVMapping.xml.
remark: The PSI MI schema defines short labels for controlled vocabulary terms
remark: short labels are reported as PSI-MI-short synonyms that are created when a term is more than 20 characteres long.
remark: The last accession number used in this file is stored in a separate file,
remark: psi-mi.lastac. It MUST be updated when this file is updated.
remark: The maintenance of this file is ensured by Pablo Porras Millán pporras@ebi.ac.uk and Sandra Orchard orchard@ebi.ac.uk
remark: coverage: This file collect controlled vocabularies describing different aspects of molecular interactions.
remark: publisher: This file is published by the PSI MI working group see http://psidev.info/MI
remark: CVversion: 2.5.5
ontology: mi

[Term]
id: MI:0000
name: molecular interaction
def: "Controlled vocabularies originally created for protein protein interactions, extended to other molecules interactions." [PMID:14755292]
subset: Drugable
subset: PSI-MI_slim
synonym: "mi" EXACT PSI-MI-short []

[Term]
id: MI:0001
name: interaction detection method
def: "Method to determine the interaction." [PMID:14755292]
subset: Drugable
subset: PSI-MI_slim
synonym: "interaction detect" EXACT PSI-MI-short []
relationship: part_of MI:0000 ! molecular interaction

[Term]
id: MI:0002
name: participant identification method
def: "Method to determine the molecules involved in the interaction." [PMID:14755292]
subset: PSI-MI_slim
synonym: "participant detection" EXACT PSI-MI-alternate []
synonym: "participant ident" EXACT PSI-MI-short []
relationship: part_of MI:0000 ! molecular interaction

[Term]
id: MI:0003
name: feature detection method
def: "Method to determine the features of the proteins involved in the interaction." [PMID:14755292]
subset: PSI-MI_slim
synonym: "feature detection" EXACT PSI-MI-short []
relationship: part_of MI:0000 ! molecular interaction

[Term]
id: MI:0004
name: affinity chromatography technology
def: "This class of approaches is characterised by the use of affinity resins as tools to purify molecule of interest (baits) and their binding partners. The baits can be captured by a variety of high affinity ligands linked to a resin - for example, antibodies specific for the bait itself, antibodies for specific tags engineered to be expressed as part of the bait or other high affinity binders such as glutathione resins for GST fusion proteins, metal resins for histidine-tagged proteins." [PMID:7708014]
subset: PSI-MI_slim
synonym: "affinity chrom" EXACT PSI-MI-short []
synonym: "Affinity purification" EXACT PSI-MI-alternate []
is_a: MI:0091 ! chromatography technology
is_a: MI:0400 ! affinity technology

[Term]
id: MI:0005
name: alanine scanning
def: "This approach is used to identify the residues that are involved in an interaction. Several variants of the native protein are prepared by sequentially  mutating each residue of interest to an alanine. The mutated proteins are expressed and probed in the binding assay." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0810 ! substitution analysis

[Term]
id: MI:0006
name: anti bait coimmunoprecipitation
def: "A specific antibody for the molecule of interest (bait) is available, this is used to generate a high affinity resin to capture the endogenous bait present in a sample." [PMID:7708014]
subset: PSI-MI_slim
synonym: "anti bait coip" EXACT PSI-MI-short []
is_a: MI:0019 ! coimmunoprecipitation

[Term]
id: MI:0007
name: anti tag coimmunoprecipitation
def: "A specific antibody for the molecule of interest is not available, therefore the bait protein is expressed as a hybrid protein fused to a tag peptide/protein for which efficient and specific antibodies or a specific ligand are available." [PMID:7708014]
subset: PSI-MI_slim
synonym: "anti tag coip" EXACT PSI-MI-short []
is_a: MI:0019 ! coimmunoprecipitation

[Term]
id: MI:0008
name: array technology
def: "In this class of methodologies, the molecules to be tested are presented ordered in an array format (typically at high density) on planar supports. The characteristics and chemical nature of the planar support can vary. This format permits the simultaneous assay, in controlled conditions, of several thousand proteins/peptides/nucleic acids for different functions, for instance their ability to bind any given molecule." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0400 ! affinity technology

[Term]
id: MI:0009
name: bacterial display
def: "The protein of interest is presented on the outer membrane of Gram negative bacteria by expressing it as a fusion partner to peptide signals that direct heterologous proteins to the cell surface. For instance, a single chain Fv (scFv) antibody fragment, consisting of the variable heavy and variable light domains from two separate anti-digoxin monoclonal antibodies, was displayed on the outer membrane of Escherichia coli by fusing it to an Lpp-OmpA. Similar systems have also been developed for gram positive bacteria. Fluorescence-activated cell sorting (FACS), is used to specifically select clones displaying a protein binding to scFv-producing cells." [PMID:10436088, PMID:8248129]
subset: PSI-MI_slim
is_a: MI:0034 ! display technology
is_a: MI:0054 ! fluorescence-activated cell sorting

[Term]
id: MI:0010
name: beta galactosidase complementation
def: "Beta-galactosidase activity can be used to monitor the interaction of chimeric proteins. Pairs of inactive beta gal deletion mutants are capable of complementing to restore activity when fused to interacting protein partners. Critical to the success of this system is the choice of two poorly complementing mutant moieties, since strongly complementing mutants spontaneously assemble and produce functional beta-gal activity detectable in absence of any fused protein fragment." [PMID:12042868, PMID:9237989]
subset: PSI-MI_slim
synonym: "beta galactosidase" EXACT PSI-MI-short []
is_a: MI:0090 ! protein complementation assay

[Term]
id: MI:0011
name: beta lactamase complementation
def: "This strategy is based on a protein fragment complementation assay (PCA) of the enzyme TEM-1 beta-lactamase. The approach includes a simple colorimetric in vitro assays using the cephalosporin nitrocefin and assays in intact cells using the fluorescent substrate CCF2/AM. The combination of in vitro colorimetric and in vivo fluorescence assays of beta-lactamase in mammalian cells permits a variety of sensitive and high-throughput large-scale applications." [PMID:12042868]
subset: PSI-MI_slim
synonym: "beta lactamase" EXACT PSI-MI-short []
is_a: MI:0090 ! protein complementation assay

[Term]
id: MI:0012
name: bioluminescence resonance energy transfer
def: "In this variation of the FRET assay the donor fluorophore is replaced by a luciferase (typically Renilla luciferase). In the presence of its substrate, the luciferase catalyses a bioluminescent reaction that excites the acceptor fluorophore through a resonance energy transfer mechanism. As with FRET the energy transfer occurs only if the protein fused to the luciferase and the one fused to the acceptor fluorophore are in close proximity (10-100 Angstrom)." [PMID:10725388, PMID:9874787]
subset: PSI-MI_slim
synonym: "BRET" EXACT PSI-MI-alternate []
synonym: "bret" EXACT PSI-MI-short []
synonym: "LRET" EXACT PSI-MI-alternate []
is_a: MI:0051 ! fluorescence technology

[Term]
id: MI:0013
name: biophysical
def: "The application of physical principles and methods to biological experiments." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0045 ! experimental interaction detection

[Term]
id: MI:0014
name: adenylate cyclase complementation
def: "Adenylate cyclase is encoded by the cyaA gene and contains a catalytic domain which can be proteolytically cleaved into two complementary fragments, T25 and T18, which remain associated in the presence of calmodulin in a fully active ternary complex. In the absence of calmodulin, the mixture of the two fragments does not exhibit detectable activity, suggesting that the two fragments do not associate. When expressed in an adenylate cyclase-deficient E. coli strain (E. coli lacks calmodulin or calmodulin-related proteins), the T25 and T18 fragments fused to putative interacting proteins are brought into close association which result in cAMP synthesis. The level of reconstructed adenylate cyclase can be estimated by monitoring the expression of a cAMP dependent reporter gene. The T25 tagged protein is generally regarded as the bait, the T18 as the prey." [PMID:9576956]
subset: PSI-MI_slim
synonym: "adenylate cyclase" EXACT PSI-MI-short []
synonym: "bacterial two-hybrid" EXACT PSI-MI-alternate []
is_a: MI:0090 ! protein complementation assay

[Term]
id: MI:0016
name: circular dichroism
def: "Circular dichroism (CD) is observed when optically active molecules absorb left and right hand circularly polarized light slightly differently. Linearly polarized light can be viewed as a superposition of two components of circularly polarized light of equal amplitude and phase but opposite handness. When this light passes through an optically active sample the two polarized components are absorbed differently. The difference in left and right handed absorbance A(l)- A(r) is the signal registered in CD spectra. This signal displays distinct features corresponding to different secondary structures present in peptides, proteins and nucleic acids. The analysis of CD spectra can therefore yield valuable information about the secondary structure of biological macromolecules and the interactions among molecules that influence their structure." [PMID:11578931]
subset: PSI-MI_slim
synonym: "CD" EXACT PSI-MI-alternate []
synonym: "cd" EXACT PSI-MI-short []
is_a: MI:0013 ! biophysical

[Term]
id: MI:0017
name: classical fluorescence spectroscopy
def: "Proteins contain endogenous fluorophores such as tryptophan residue and heme or flavins groups. Protein folding and protein-protein interaction can be studied by monitoring changes in the tryptophan environment detected by changes in its intrinsic fluorescence. Changes in the fluorescence emission spectrum on complex formation can occur either due to a shift in the wavelength of maximum fluorescence emission or by a shift in fluorescence intensity caused by the mixing of two proteins. The interaction of two proteins causes a shift in the fluorescence emission spectrum relative to the sum of the individual fluorescence spectra, resulting in a difference spectrum [F (complex)-2 F (sum)], which is a measurable effect of the interaction. Loss of fluorescence signal from a substrate can be used to measure protein cleavage." [PMID:7708014]
subset: PSI-MI_slim
synonym: "fluorescence spectr" EXACT PSI-MI-short []
is_a: MI:0051 ! fluorescence technology

[Term]
id: MI:0018
name: two hybrid
def: "The classical two-hybrid system is a method that uses transcriptional activity as a measure of protein-protein interaction. It relies on the modular nature of many site-specific transcriptional activators (GAL 4) , which consist of a DNA-binding domain and a transcriptional activation domain. The DNA-binding domain serves to target the activator to the specific genes that will be expressed, and the activation domain contacts other proteins of the transcriptional machinery to enable transcription to occur. The two-hybrid system is based on the observation that the two domains of the activator need to be non-covalently brought together by the interaction of any two proteins. The application of this system requires the expression of two hybrid. Generally this assay is performed in yeast cell, but it can also be carried out in other organism. The bait protein is fused to the DNA binding molecule, the prey to the transcriptional activator." [PMID:10967325, PMID:12634794, PMID:1946372]
subset: PSI-MI_slim
synonym: "2 hybrid" EXACT PSI-MI-short []
synonym: "2-hybrid" EXACT PSI-MI-alternate []
synonym: "2H" EXACT PSI-MI-alternate []
synonym: "2h" EXACT PSI-MI-alternate []
synonym: "classical two hybrid" EXACT PSI-MI-alternate []
synonym: "Gal4 transcription regeneration" EXACT PSI-MI-alternate []
synonym: "two-hybrid" EXACT PSI-MI-alternate []
synonym: "Y-2H" RELATED []
synonym: "Y2H" EXACT []
synonym: "yeast two hybrid" EXACT PSI-MI-alternate []
is_a: MI:0232 ! transcriptional complementation assay

[Term]
id: MI:0019
name: coimmunoprecipitation
def: "In this approach an antibody, specific for the molecule of interest (bait) or any tag expressed within a fusion protein, is used to separate the bait from a molecular mixture or a cell lysate and to capture its ligand simultaneously. The partners that bind to the bait molecule retained by the resin can then be eluted and identified. The antibody may be free or bound to a matrix during this process." [PMID:7708014]
subset: PSI-MI_slim
synonym: "co-immunoprecipitation" EXACT PSI-MI-alternate []
synonym: "Co-IP" EXACT PSI-MI-alternate []
synonym: "CoIp" EXACT PSI-MI-alternate []
synonym: "coip" EXACT PSI-MI-short []
synonym: "immunoprecipitation" EXACT PSI-MI-alternate []
is_a: MI:0004 ! affinity chromatography technology

[Term]
id: MI:0020
name: transmission electron microscopy
def: "Microscopy technique in which a beam of electrons is transmitted through a sample to form an image. Samples can be purified molecules, for which no staining is required in order to detect interaction, or tissue/cells. In the latter case, during the treatment for microscope analysis a tissue section is incubated with high-specificity antibodies coupled to heavy metals (e.g. gold). Any tissue section can then be analysed by electron microscopy to localise the target proteins within the cell. This method supports very high resolution colocalisation of different molecules in a cell." [PMID:14755292]
subset: PSI-MI_slim
synonym: "tem" EXACT PSI-MI-short []
is_a: MI:0040 ! electron microscopy

[Term]
id: MI:0021
name: colocalization by fluorescent probes cloning
def: "Two proteins can be localised to cell compartments, in the same experiment, if they are expressed as chimeric proteins fused to distinct proteins fluorescing at different wavelengths (Green Fluorescent Protein and Red Fluorescent Protein for example). Using a confocal microscope the two proteins can be visualized in living cells and it can be determined whether they have the same subcellular location. Fluorescence microscopy of cells expressing a GFP fusion protein can also demonstrate dynamic processes such as its translocation from one subcellular compartment to another.\nOBSOLETE: use imaging technique (MI:0428) and specific probe as feature of each interacting protein." [PMID:14755292]
subset: PSI-MI_slim
synonym: "coloc fluoresc probe" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0022
name: colocalization by immunostaining
def: "The subcellular location of a protein can be demonstrated by treating cells fixed on a microscope slide with an antibody specific for the protein of interest. A secondary antibody conjugated with a reactive enzyme (e.g. horseradish peroxidase) is then added. Following a washing step to remove the unbound secondary ligand, a chromogenic substrate (e.g. 3,3', 5,5' tetramethyl benzidine chromogen [TMB]) is converted to a soluble coloured product by the conjugated enzyme and can then be visualised by standard microscopic techniques.\nOBSOLETE since combination of Interaction Detection Method and Interaction Type.Consider using the Interaction Detection Method imaging techniques (MI:0428) coupled with Interaction Type colocalisation (MI:0403) and Participant detection immunostaining (MI:0422) instead." [PMID:14755292]
subset: PSI-MI_slim
synonym: "coloc immunostaining" EXACT PSI-MI-short []
synonym: "Immunofluorescence Staining" EXACT PSI-MI-alternate []
synonym: "Immunostaining" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0023
name: colocalization/visualisation technologies
def: "Techniques enabling the identification of the subcellular localisation of a protein or complex. Two different proteins show a similar distribution in the cell are said to co-localise. Obsolete since combination of Interaction Detection Method and Interaction Type.\nOBSOLETE. Consider using imaging techniques (MI:0428) as interaction detection method coupled with colocalisation (MI:0401) as interaction type and predetermined (MI:0396) as participant detection." [PMID:14755292]
subset: PSI-MI_slim
synonym: "coloc visual technol" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0024
name: confirmational text mining
def: "Text mining is used to support interactions which have been determined by other methods." [PMID:14755292]
subset: PSI-MI_slim
synonym: "conformational tm" EXACT PSI-MI-short []
is_a: MI:0110 ! text mining

[Term]
id: MI:0025
name: copurification
def: "Approaches designed to separate cell components on the basis of their physicochemical properties. The observation that two or more proteins copurify in one or several conditions is taken as an indication that they form a molecular complex.\nOBSOLETE since too non-specific. Consider use of cosedimentation (MI:0027) or comigration in non denaturing gel electrophoresis (MI:0404) or affinity chromatography technologies (MI:0004) or molecular sieving (MI:0071) or for unspecific cases biochemical (MI:0401)." [PMID:14755292]
subset: PSI-MI_slim
is_obsolete: true

[Term]
id: MI:0026
name: correlated mutations
def: "Pairs of multiple alignments of orthologous sequences are used to identify potential interacting partners as proteins that show covariation of their residue identities between different species. Proteins displaying inter-protein correlated mutations during evolution are likely to be interacting proteins due to co-adapted evolution of their protein interacting interfaces." [PMID:11933068]
subset: PSI-MI_slim
is_a: MI:0101 ! sequence based prediction
is_a: MI:0660 ! feature prediction

[Term]
id: MI:0027
name: cosedimentation
def: "Separation of a mixture of molecules under the influence of a force such as artificial gravity. Molecules sedimenting together are assumed to interact." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0401 ! biochemical

[Term]
id: MI:0028
name: cosedimentation in solution
def: "The ultracentrifuge can be used to characterise and/or purify macromolecules in solution according to their mass and hydrodynamic properties. Sedimentation studies provide information about the molecular weight and shape of a molecule. It is also possible to measure the association state of the sample. Both the mass of a molecule and its shape, that influences the friction forces and diffusion that counterbalances gravity, determine the sedimentation speed." [PMID:10410796]
subset: PSI-MI_slim
synonym: "solution sedimentati" EXACT PSI-MI-short []
is_a: MI:0027 ! cosedimentation

[Term]
id: MI:0029
name: cosedimentation through density gradient
def: "Sedimentation through a density gradient measures the sedimentation rate of a mixture of proteins through either a glycerol or sucrose gradient. Two interacting proteins will sediment mostly as a complex at concentrations above the binding constant. By varying the concentration of one or both of the complex constituents and taking into account the dilution of the species during sedimentation, one can reasonably accurately estimate the binding constant." [PMID:10410796]
subset: PSI-MI_slim
synonym: "density sedimentation" EXACT PSI-MI-short []
is_a: MI:0027 ! cosedimentation

[Term]
id: MI:0030
name: cross-linking study
def: "Analysis of complexes obtained by input of energy or chemical treatments, or by introducing cysteines followed by oxidation to promote the formation of covalent bonds among molecules in close proximity." [PMID:14755292]
subset: PSI-MI_slim
synonym: "crosslink" EXACT PSI-MI-short []
is_a: MI:0401 ! biochemical

[Term]
id: MI:0031
name: protein cross-linking with a bifunctional reagent
def: "Cross-linking agents induce the formation of covalent bonds among proteins that are neighbours. The cross-linker may be a bifunctional molecule having two reactive ends linked by a spacer, often containing a disulfide bond.  When a reducing agent is added the disulfide bridge is cleaved, the cross-linked pairs are released and can be identified. There are various classes of cross-linkers, the most common are those having photoreactive groups that become reactive fluorophores when activated by UV light thereby resulting in photolabeling the cross-linked moieties." [PMID:10679368, PMID:7708014]
subset: PSI-MI_slim
synonym: "bifunctional agent crosslink" EXACT PSI-MI-short []
synonym: "Label transfer techniques" EXACT PSI-MI-alternate []
synonym: "Photoaffinity labelling" EXACT PSI-MI-alternate []
is_a: MI:0030 ! cross-linking study

[Term]
id: MI:0032
name: de novo protein sequencing by mass spectrometry
def: "The strategy to determine the complete amino acid sequence of a protein by mass spectrometry relies on the generation of a nested set of fragments differing by one amino acid. This reveals the identity of the residue that has been removed at each degradation step by measuring the mass difference of fragments differing of one residue. Peptide fragments can be obtained by protease treatment combined with the fragmentation promoted by collision (or other methods) within a tandem mass spectrometer. This approach can be carried out with LC MS/MS (Liquid Chromatography Tandem Mass Spectrometry), nanoESI MS/MS (nanoElectrospray Ionisation tandem mass spectrometry), or FTMS (Fourier Transform mass spectrometry) instruments." [PMID:10984529]
subset: PSI-MI_slim
synonym: "de novo protein sequence" EXACT PSI-MI-short []
synonym: "MS/MS" RELATED []
is_a: MI:0093 ! protein sequence identification
is_a: MI:0427 ! Identification by mass spectrometry
is_a: MI:0659 ! experimental feature detection

[Term]
id: MI:0033
name: deletion analysis
def: "In this approach, once a molecule is demonstrated to participate in an interaction, several deletion derivatives are produced and tested in the binding assay to identify the minimal fragment (domain) that can still support the interaction." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0074 ! mutation analysis

[Term]
id: MI:0034
name: display technology
def: "All the methods that permit the physical linking of a protein/peptide to its coding sequence. As a consequence affinity purification of the displayed peptide results in the genetic enrichment of its coding sequence. By these technologies genes encoding a peptide with desired binding properties can be selected over an excess of up to 1012 unrelated molecules." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0400 ! affinity technology

[Term]
id: MI:0035
name: docking
def: "Predicts the structure of a molecular complex from the unbound structures of its components. The initial approach in the majority of docking procedures is based largely on the 'rigid-body' assumption, whereby the proteins are treated as solid objects. Initial scoring of a complex is based on geometric fit or surface complementarity. This generally requires some knowledge of the binding site to limit the number of solutions." [PMID:11478868, PMID:9631301]
subset: PSI-MI_slim
is_a: MI:0105 ! structure based prediction
is_a: MI:0577 ! feature prediction from structure

[Term]
id: MI:0036
name: domain fusion
def: "The rosetta stone, or domain fusion procedure, is based on the assumption that proteins whose homologues in other organisms happen to be fused into a single protein chain are likely to interact or to be functionally related." [PMID:10573422]
subset: PSI-MI_slim
synonym: "Rosetta Stone" EXACT PSI-MI-alternate []
is_a: MI:0058 ! genome based prediction
is_a: MI:0101 ! sequence based prediction

[Term]
id: MI:0037
name: domain profile pairs
def: "This approach uses a protein interaction network of a given organism to infer interaction in another organism using information about the interacting region. The regions or domains involved in interactions are clustered if they share sequence similarity and have common interacting partners. The resulting domain profiles are then used to screen the proteome of another organism and domain-domain interactions are inferred. Ultimately, an inferred protein interaction map is built in this second organism." [PMID:11473021]
subset: PSI-MI_slim
is_a: MI:0046 ! experimental knowledge based
is_a: MI:0101 ! sequence based prediction
is_a: MI:0660 ! feature prediction

[Term]
id: MI:0038
name: dynamic light scattering
def: "In dynamic light scattering, particle diffusion in solution gives rise to fluctuations in the intensity of the scattered light on the microsecond scale. The hydrodynamic radius of the particles can be easily calculated." [PMID:9013660]
subset: PSI-MI_slim
synonym: "dls" EXACT PSI-MI-short []
is_a: MI:0067 ! light scattering

[Term]
id: MI:0039
name: edman degradation
def: "In this procedure the N-terminus amino acid is cleaved from a polypeptide and identified by high-pressure liquid chromatography. The cycle is repeated on the ever-shortening polypeptide until all the residues are identified. On average only 20-30 consecutive cycles can be performed and lead to amino acid identification. Longer polypeptides or full length proteins must be cleaved by specific protease before Edman degradation and their sequences built by fragment overlapping." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0433 ! partial identification of protein sequence

[Term]
id: MI:0040
name: electron microscopy
def: "Electron microscopy methods provide insights into the structure of biological macromolecules and their supramolecular assemblies. Resolution is on average around 10 Angstroms but can reach the atomic level when the samples analysed are 2D crystals. Different types of samples can be analysed by electron microscopy: crystals, single particles like viruses, macromolecular complexes or entire cells and tissue sections. Samples can be chemically fixed or vitrified by rapid freezing in liquid ethane, and then transferred into the electron microscope. Data collection consists of the recording of electron diffraction data (2D crystals) and images. Depending on the type of sample, different approaches are used to analyse and merge images and electron diffraction data." [PMID:11785754]
subset: PSI-MI_slim
synonym: "Electron cryomicroscopy" EXACT PSI-MI-alternate []
synonym: "Electron crystallography" EXACT PSI-MI-alternate []
is_a: MI:0428 ! imaging technique

[Term]
id: MI:0041
name: electron nuclear double resonance
def: "A combination of NMR and EPR. The lines in the EPR spectrum that are caused by coupling of an unpaired electron nearby nuclei change in intensity when these nuclei are excited at their NMR frequency." [PMID:11817959, PMID:11988476, PMID:12186859]
subset: PSI-MI_slim
synonym: "ENDOR" EXACT PSI-MI-alternate []
synonym: "endor" EXACT PSI-MI-short []
is_a: MI:0043 ! electron resonance

[Term]
id: MI:0042
name: electron paramagnetic resonance
def: "EPR (also called ESR, Electron Spin Resonance) spectroscopy is analogous to NMR, but is based on the excitation of unpaired electrons instead of nuclei. Unpaired (single) electrons are only found in radicals and some metal ions (paramagnetic species); the EPR spectrum provides information about the environment and mobility of the paramagnetic species. The magnetic interaction of two paramagnetic centres in a protein can be used to calculate the distance between them; this allows studies of the movements and interactions of protein segments. In proteins without any intrinsic unpaired electrons it is possible to attach a radical probe (spin label). Stable nitroxide radicals can be bound to amino acid residues, in analogy with fluorescent probes. In combination with site directed mutagenesis this method is used in particular to study structure and assembly of membrane proteins, by measuring with EPR whether an amino acid is in a polar or non polar environment." [PMID:11817959]
subset: PSI-MI_slim
synonym: "EPR" EXACT PSI-MI-alternate []
synonym: "epr" EXACT PSI-MI-short []
synonym: "ESR" EXACT PSI-MI-alternate []
is_a: MI:0043 ! electron resonance

[Term]
id: MI:0043
name: electron resonance
def: "A form of spectroscopy in which the absorption of microwave by a sample in a strong magnetic field is used to study atoms or molecules with unpaired electrons." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0013 ! biophysical
is_a: MI:0659 ! experimental feature detection

[Term]
id: MI:0045
name: experimental interaction detection
def: "Methods based on laboratory experiments to determine an interaction." [PMID:14755292]
subset: PSI-MI_slim
synonym: "experimental interac" EXACT PSI-MI-short []
is_a: MI:0001 ! interaction detection method

[Term]
id: MI:0046
name: experimental knowledge based
def: "Predictive algorithms that rely on the information obtained by experimental results." [PMID:14755292]
subset: PSI-MI_slim
synonym: "experimental info" EXACT PSI-MI-short []
is_a: MI:0063 ! interaction prediction

[Term]
id: MI:0047
name: far western blotting
def: "Proteins are fractionated by PAGE (SDS-polyacrylamide gel electrophoresis), transferred to a nitrocellulose membrane and tested for the ability to bind to a protein, a peptide, or any other ligand. Cell lysates can also be fractionated before gel electrophoresis to increase the sensitivity of the method for detecting interactions with rare proteins. Denaturants are removed during the blotting procedure, which allows many proteins to recover (or partially recover) activity. However, if biological activity is not recoverable, the proteins can be fractionated by a non denaturing gel system. This variation of the method eliminates the problem of activity regeneration and allows the detection of binding when the presence of a protein complex is required for binding. The protein probe can be prepared by any one of several procedures, while fusion affinity tags greatly facilitate purification. Synthesis in E. coli with a GST fusion, epitope tag, or other affinity tag is most commonly used. The protein of interest can then be radioactively labelled, biotinylated, or used in the blotting procedure as an unlabeled probe that is detected by a specific antibody." [PMID:7708014]
subset: PSI-MI_slim
synonym: "Affinity blotting" EXACT PSI-MI-alternate []
is_a: MI:0892 ! solid phase assay

[Term]
id: MI:0048
name: filamentous phage display
def: "Filamentous phages (M13, f1, fd) have been extensively used to develop and implement the technology of phage display. Repertoires of relatively short peptides of random amino acid sequences or cDNA libraries have been constructed and searched successfully. Most experiments have taken advantage of the ability to assemble phages decorated with hybrid versions of the receptor protein pIII or of the major coat protein pVIII. Both systems allow the display of foreign peptides by fusion to the amino-terminus of the capsid protein but differ in the number of peptide copies that can be displayed on each phage particle. Display libraries of very diverse protein fragments have been constructed by fusing either genomic or cDNA fragments to gene III or gene VIII." [PMID:7682645]
subset: PSI-MI_slim
synonym: "filamentous phage" EXACT PSI-MI-short []
is_a: MI:0084 ! phage display

[Term]
id: MI:0049
name: filter binding
def: "A method in which separation depends upon the ability of one participant to bind to a filter or membrane which the other participants do not. Molecules interacting with the bound molecule will also be retain on the filter. For example, proteins expressed by different clones of an expression library are bound to a nitrocellulose membrane, by colony (bacterial library) or plaque (phage library) blotting. A labelled protein can then be used as a probe to identify clones expressing proteins that interact with the probe. Interactions occur on the nitrocellulose filters. The method is highly general and therefore widely applicable. A variety of approaches can be used to label the ligand, alternatively the ligand can be detected by a specific antibody." [PMID:7708014]
subset: PSI-MI_slim
synonym: "dot blot" RELATED []
synonym: "Filter overlay assay" EXACT PSI-MI-alternate []
is_a: MI:0892 ! solid phase assay

[Term]
id: MI:0050
name: flag tag coimmunoprecipitation
def: "The protein of interest is expressed as a fusion to the peptide DYKDDDDKV for which antibodies are commercially available. Sometimes multiple copies of the peptide are fused in tandem.\nOBSOLETE redundant term. Map to feature type: flag-tagged (MI:0518) and Interaction detection method: anti tag coimmunoprecipitation (MI:0007)." [PMID:14755292]
subset: PSI-MI_slim
synonym: "flag tag coip" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0051
name: fluorescence technology
def: "Techniques based upon the measurement of the emission of one or more photons by a molecule activated by the absorption of a quantum of electro-magnetic radiation. Typically the emission, which is characterised by a wavelength that is longer than the one of excitatory radiation, occurs within 10-8 seconds." [PMID:14755292]
subset: PSI-MI_slim
synonym: "fluorescence" EXACT PSI-MI-short []
is_a: MI:0013 ! biophysical

[Term]
id: MI:0052
name: fluorescence correlation spectroscopy
def: "FCS monitors the random motion of fluorescently labelled molecules inside a defined volume irradiated by a focused laser beam. These fluctuations provide information on the rate of diffusion or diffusion time of a particle and this is directly dependent on the particle mass. As a consequence, any increase in the mass of a biomolecule, e.g. as a result of an interaction with a second molecule, is readily detected as an increase in the diffusion time of the particle. From these results the concentration of the different molecules can be calculated as well as their binding constant." [PMID:10733953]
subset: PSI-MI_slim
synonym: "FCS" EXACT PSI-MI-alternate []
synonym: "fcs" EXACT PSI-MI-short []
synonym: "fluctuation correlation specctrometry" RELATED []
is_a: MI:0051 ! fluorescence technology

[Term]
id: MI:0053
name: fluorescence polarization spectroscopy
def: "Because of the long lifetimes of excited fluorescent molecules (nanoseconds), fluorescence can be used to monitor the rotational motion of molecules, which occurs on this timescale. This is accomplished experimentally by excitation with plane-polarized light, followed by measurement of the emission at parallel and perpendicular planes. Since rotational correlation times depend on the size of the molecule, this method can be used to measure the binding of two proteins because the observed polarization increase when a larger complex is formed. A fluorescence anisotropy experiment is normally carried out with a protein bearing a covalently added fluorescent group, which increases both the observed fluorescence lifetime of the excited state and the intensity of the fluorescent signal. Residue modification can be assessed by addition of an antibody which binds to the modified residue and alters the molecular weight of the complex. A variation of this technique has been used to show interaction of a DNA binding protein with another protein. In this case the DNA rather than protein is fluorescently labelled." [PMID:12805227, PMID:7708014]
subset: PSI-MI_slim
synonym: "Fluorescence anisotropy" EXACT PSI-MI-alternate []
synonym: "FPS" EXACT PSI-MI-alternate []
synonym: "fps" EXACT PSI-MI-short []
is_a: MI:0051 ! fluorescence technology

[Term]
id: MI:0054
name: fluorescence-activated cell sorting
def: "Cells in suspension flow through a laser beam, the scattered light or emitted fluorescence is measured, filtered and converted to digital values. Cells can be sorted according to their properties. Using flow cytometry, any fluorescent or light scattering experiment can be carried out on entire cells. With this instrument, interactions occurring either on cell surfaces or in any other subcellular location can be studied by using suitable fluorescent labels." [PMID:11988464]
subset: PSI-MI_slim
synonym: "FACS" EXACT PSI-MI-alternate []
synonym: "facs" EXACT PSI-MI-short []
synonym: "Flow cytometry" EXACT PSI-MI-alternate []
is_a: MI:0051 ! fluorescence technology

[Term]
id: MI:0055
name: fluorescent resonance energy transfer
def: "FRET is a quantum mechanical process involving the radiationless transfer of energy from a donor fluorophore to an appropriately positioned acceptor fluorophore. The fluorophores are genetically fused to the protein in analysis and cotransfected. Three basic conditions must be fulfilled for FRET to occur between a donor molecule and acceptor molecule. First, the donor emission spectrum must significantly overlap the absorption spectrum of the acceptor. Second, the distance between the donor and acceptor fluorophores must fall within the range 20 to 100 Angstrom. Third, the donor and acceptor fluorophores must be in favourable orientations." [PMID:11558993]
subset: PSI-MI_slim
synonym: "FRET" EXACT PSI-MI-alternate []
synonym: "fret" EXACT PSI-MI-short []
synonym: "FRET analysis" EXACT PSI-MI-alternate []
synonym: "RET" EXACT PSI-MI-alternate []
is_a: MI:0051 ! fluorescence technology

[Term]
id: MI:0056
name: full identification by DNA sequencing
def: "Sequencing occurs during the course of the experiment. DNA sequencing is the process of determining the nucleotide order of a given DNA fragment. Thus far, most DNA sequencing has been performed using the chain termination method developed by Frederick Sanger. This technique uses sequence-specific termination of a DNA synthesis reaction using modified nucleotide substrates. However, new sequencing technologies such as Pyrosequencing are generating the majority of data." [PMID:14755292]
subset: PSI-MI_slim
synonym: "full dna sequence" EXACT PSI-MI-short []
is_a: MI:0078 ! nucleotide sequence identification
is_a: MI:0659 ! experimental feature detection

[Term]
id: MI:0057
name: gene neighbourhood
def: "Gene pairs that show a conserved topological neighbourhood in many prokaryotic genomes are considered by this approach to encode interacting or functionally related proteins. By measuring the physical distance of any given gene pair in different genomes, interacting partners are inferred." [PMID:9787636]
subset: PSI-MI_slim
is_a: MI:0058 ! genome based prediction

[Term]
id: MI:0058
name: genome based prediction
def: "Methods that require fully sequenced genomes either because they are based on the comparison of genome topology or on the identification of orthologous sequences in different genomes." [PMID:14755292]
subset: PSI-MI_slim
synonym: "genome prediction" EXACT PSI-MI-short []
is_a: MI:0063 ! interaction prediction

[Term]
id: MI:0059
name: gst pull down
def: "The bait protein is expressed and purified as a fusion to the glutathione S-tranferase protein. The bait protein is normally attached to a glutathione sepharose resin or alternatively to a support containing an anti-GST antibody.\nOBSOLETE redundant term. Map to feature type : gst-tagged (MI:0519) and Interaction detection method: pull down (MI:0096)." [PMID:14755292]
subset: PSI-MI_slim
is_obsolete: true

[Term]
id: MI:0060
name: ha tag coimmunoprecipitation
def: "The protein of interest is expressed as a fusion to the peptide YPYDVPDYA (a fragment of the influenza hemaglutinin protein) for which antibodies are commercially available.\nOBSOLETE redundant term. Map to feature type : ha-tagged (MI:0520) and Interaction detection method: anti tag coimmunoprecipitation (MI:0007)." [PMID:14755292]
subset: PSI-MI_slim
synonym: "ha tag coip" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0061
name: his pull down
def: "The bait protein is expressed and purified fused to an amino or carboxyterminal tail containing a variable number of histidines. The bait protein is normally attached to a metal (usually nickel) resin.\nOBSOLETE redundant term. Map to feature type : his-tagged (MI:0521) and Interaction detection method: pull down (MI:0096)." [PMID:14755292]
subset: PSI-MI_slim
is_obsolete: true

[Term]
id: MI:0062
name: his tag coimmunoprecipitation
def: "The protein of interest is expressed as a fusion to a poly-His tail. This permits purification by chromatography over a metal column or by binding to commercially available anti poly-His antibodies.\nOBSOLETE redundant term. Map to feature type: his-tagged (MI:0521) and Interaction detection method: anti tag coimmunoprecipitation (MI:0007)." [PMID:14755292]
subset: PSI-MI_slim
synonym: "his tag coip" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0063
name: interaction prediction
def: "Computational methods to predict an interaction." [PMID:14755292]
subset: PSI-MI_slim
synonym: "in silico methods" EXACT PSI-MI-alternate []
synonym: "predicted interac" EXACT PSI-MI-short []
is_a: MI:0001 ! interaction detection method

[Term]
id: MI:0064
name: interologs mapping
def: "Protein interactions, experimentally detected in an organism, are extended to a second organism assuming that homologue proteins, in different organisms, maintain their interaction properties." [PMID:11731503]
subset: PSI-MI_slim
synonym: "Homology based interaction prediction" EXACT PSI-MI-alternate []
is_a: MI:0046 ! experimental knowledge based
is_a: MI:0101 ! sequence based prediction

[Term]
id: MI:0065
name: isothermal titration calorimetry
def: "Isothermal titration calorimetry (ITC) measures directly the energy associated with a chemical reaction triggered by the mixing of two components. A typical ITC experiment is carried out by the stepwise addition of one of the reactants (~10-6 L per injection) into the reaction cell (~1mL) containing the second reactant. The chemical reaction occurring after each injection either releases or absorbs heat (qi) proportional to the amount of ligand that binds to the protein with a characteristic binding enthalpy (DH). As modern ITC instruments operate on the heat compensation principle, the instrumental response (measured signal) is the amount of power (microcalories per second) necessary to maintain constant the temperature difference between the reaction and the reference cells. Because the amount of uncomplexed protein available progressively decreases after each successive injection, the magnitude of the peaks becomes progressively smaller until complete saturation is achieved. The difference between the concentration of bound ligand in the ith and (i-1)th injections depends on the binding constant Ka and the total ligand injected. The calculations depend on the binding model (number of substrates). Analysis of the data yields DH and DG = -RTlnKa. The entropy change is obtained by using the standard thermodynamic expression DG = DH-TDS." [PMID:11785756]
subset: PSI-MI_slim
synonym: "ITC" EXACT PSI-MI-alternate []
synonym: "itc" EXACT PSI-MI-short []
is_a: MI:0013 ! biophysical

[Term]
id: MI:0066
name: lambda phage display
def: "Morphologically classified as one of the siphoviridae, lambda is a temperate bacteriophage of E.coli, with a double-stranded DNA genome. It has an icosahedral head attached to a flexible helical tail. Both the tail protein pV and the head protein pD have been used for displaying (C or N terminally) foreign peptides on the viral capsid." [PMID:7682645]
subset: PSI-MI_slim
synonym: "lambda phage" EXACT PSI-MI-short []
is_a: MI:0084 ! phage display

[Term]
id: MI:0067
name: light scattering
def: "Dynamic and static laser light scattering probes the size, shape, and structure of biological macromolecules or of their assemblies. A beam is focused on an optically clear cylindrical cell containing the sample. Most of the light passes directly through the sample. A small portion of the light is scattered; the scattered light intensity containing information about the scattering particle is detected at an angle (typically in the range 15-180degrees) from the direction of the incident beam." [PMID:9013660]
subset: PSI-MI_slim
is_a: MI:0013 ! biophysical

[Term]
id: MI:0068
name: mass detection of residue modification
def: "Mass spectrometry can be used to characterise chemical modifications within peptides. One approach consists in the observation of a mass difference when a sample is treated with an enzyme that can specifically remove a peptide modification, for instance a phosphatase. The mass difference corresponds to the mass of the chemical group covalently linked to a residue. Such experiments carried out with a MALDI-TOF (Matrix-assisted laser desorption ionization time-of-flight ) do not allow the mapping of the modification site within the sequence, whereas any tandem mass spectrometer (LC MS/MS Liquid Chromatography Tandem Mass Spectrometry, nanoESI MS/MS nanoElectrospray Ionisation tandem mass spectrometry, FTMS Fourier Transform mass spectrometry) provide such information. A second approach consists of the direct mass measurement of the ionized chemical group dissociated from the residue within a tandem mass spectrometer. Both approaches need a prior enrichment of the modified peptide population in the samples with IMAC (Immobilized Metal Affinity Chromatography)or specific anti-modification antibodies." [PMID:11395414, PMID:11875433]
subset: PSI-MI_slim
synonym: "modified residue ms" EXACT PSI-MI-short []
is_a: MI:0659 ! experimental feature detection

[Term]
id: MI:0069
name: mass spectrometry studies of complexes
def: "Mass spectrometric approaches to the study of macromolecular complexes permits the identification of subunit stoichiometry and transient associations. By preserving complexes intact in the mass spectrometer, mass measurement can be used for monitoring changes in different experimental conditions, or to investigate how variations of collision energy affect their dissociation." [PMID:12057199, PMID:12504676]
subset: PSI-MI_slim
synonym: "ms of complexes" EXACT PSI-MI-short []
is_a: MI:0943 ! detection by mass spectrometry

[Term]
id: MI:0070
name: mobility shift
def: "Protein modifications can be identified by gel electrophoresis since any change in the mass and/or the charge of the protein can alter its mobility in PAGE. Although this method does not allow the unequivocal identification of the type of modification that has caused the shift, it is possible, by combining this approach with more direct methods, to correlate the extent of the shift to a specific modification." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0659 ! experimental feature detection

[Term]
id: MI:0071
name: molecular sieving
def: "In sizing columns (gel filtration), the elution position of a protein or of a complex depends on its Stokes radius. Molecules with a radius that is smaller than the bead size are retained and retarded by the interaction with the matrix. The observation that two proteins, loaded on a sieving column, elute in a fraction(s) corresponding to a MW that is larger than the MW of either protein may be taken as an indication that the two proteins interact. Furthermore this technique provides a conceptually simple method for evaluating the affinity of the interaction." [PMID:7708014]
subset: PSI-MI_slim
synonym: "Gel Filtration" EXACT PSI-MI-alternate []
synonym: "Size Exclusion Chromatography" EXACT PSI-MI-alternate []
synonym: "Sizing column" EXACT PSI-MI-alternate []
is_a: MI:0013 ! biophysical
is_a: MI:0091 ! chromatography technology

[Term]
id: MI:0072
name: monoclonal antibody western blot
def: "Western blot assay carried out using monospecific antibodies produced in the supernatant of a cell line obtained by fusing a lymphocyte B to a myeloma cell line or selected by phage display technology." [PMID:14755292]
subset: PSI-MI_slim
synonym: "monoclonal western" EXACT PSI-MI-short []
is_a: MI:0113 ! western blot

[Term]
id: MI:0073
name: mrna display
def: "This method relies on the covalent coupling of mRNA to the nascent polypeptide. The mRNA (natural or artificial) is first covalently linked to a short DNA linker carrying a puromycin moiety. The mRNA mixture is then translated in vitro. When the ribosome reaches the RNA-DNA junction the ribosome stalls and the puromycin moiety enters the peptidyltransferase site of the ribosome and forms a covalent linkage to the nascent polypeptide. As a result the protein and the mRNA are covalently joined and can be isolated from the ribosome and purified. In the current protocol, a cDNA strand is then synthesised to form a less sticky RNA-DNA hybrid and these complexes are finally used for affinity selection. As in most display approaches, several selections cycles (3-6) are sufficient to enrich for mRNAs encoding ligand proteins." [PMID:11551470]
subset: PSI-MI_slim
is_a: MI:0034 ! display technology

[Term]
id: MI:0074
name: mutation analysis
def: "Mutant molecules are produced by random or directed techniques and assayed for their ability to support binding." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0659 ! experimental feature detection

[Term]
id: MI:0075
name: myc tag coimmunoprecipitation
def: "The protein of interest is expressed as a fusion to the peptide EUKLISEED (a fragment of the Myc oncogene protein) for which antibodies are commercially available. Sometimes multiple copies of the peptide are fused in tandem.\nOBSOLETE redundant term. Map to feature type: myc-tagged (MI:0522) and Interaction detection method: anti tag coimmunoprecipitation (MI:0007)." [PMID:14755292]
subset: PSI-MI_slim
synonym: "myc tag coip " EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0076
name: neural network on interface properties
def: "Neural networks are trained on the properties of residues belonging to a cluster of residues that are neighbours in space on protein surface. The predictor permits the inference of the residues that are likely to be on an interaction interface." [PMID:11455607, PMID:11874449]
subset: PSI-MI_slim
synonym: "interface predictor" EXACT PSI-MI-short []
is_a: MI:0577 ! feature prediction from structure

[Term]
id: MI:0077
name: nuclear magnetic resonance
def: "Nuclear magnetic resonance (NMR) is an effect whereby magnetic nuclei in a magnetic field absorb and re-emit electromagnetic (EM) energy. Certain atomic nuclei, and in particular hydrogen, have a magnetic moment or spin; i.e., they have an intrinsic magnetisation, like a bar magnet. The spin aligns along the strong magnetic field, but can be changed to a misaligned excited state in response to applied radio frequency (RF) pulses of electromagnetic radiation. When the excited hydrogen nuclei relax to their aligned state, they emit RF radiation, which can be measured and displayed as a spectrum. The nature of the emitted radiation depends on the environment of each hydrogen nucleus, and if one nucleus is excited, it will influence the absorption and emission of radiation by other nuclei that lie close to it. It is consequently possible, by an ingenious elaboration of the basic NMR technique known as two-dimensional NMR, to distinguish the signals from hydrogen nuclei in different amino acid residues and to identify and measure the small shifts in these signals that occur when these hydrogen nuclei lie close enough to interact: the size of such a shift reveals the distance between the interacting pair of hydrogen atoms. In this way NMR can give information about the distances between the parts of the interacting molecule. NMR provides information about interacting atoms thereby permitting to obtain information about macromolecular structure and molecular interactions." [PMID:12062432, PMID:12120505]
subset: PSI-MI_slim
synonym: "NMR" EXACT PSI-MI-alternate []
synonym: "nmr" EXACT PSI-MI-short []
is_a: MI:0013 ! biophysical
is_a: MI:0659 ! experimental feature detection

[Term]
id: MI:0078
name: nucleotide sequence identification
def: "Identification of a nucleotide sequence. Depending on the experimental design, nucleotide sequence can be determined before the interaction detection while building a collection of clones or after the selection of randomly generated clones." [PMID:14755292]
subset: PSI-MI_slim
synonym: "nucleotide sequence" EXACT PSI-MI-short []
synonym: "sequence cloning" EXACT PSI-MI-alternate []
is_a: MI:0659 ! experimental feature detection
is_a: MI:0661 ! experimental participant identification

[Term]
id: MI:0079
name: other biochemical technologies
def: "Experimental methods that could not be assigned to the other large group of technologies.\nOBSOLETE use biochemical (MI:0401) instead." [PMID:14755292]
subset: PSI-MI_slim
synonym: "other biochemic tech" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0080
name: partial DNA sequence identification by hybridization
def: "Genes are recognised by hybridization of a probe with a fragment of the gene sequence." [PMID:14755292]
subset: PSI-MI_slim
synonym: "partial dna sequence hybrid" EXACT PSI-MI-short []
is_a: MI:1180 ! partial DNA sequence identification

[Term]
id: MI:0081
name: peptide array
def: "The peptide synthesis methods offer numerous opportunities to synthesise and subsequently screen large arrays of synthetic peptides on planar cellulose supports. Discrete spots are arranged as arrays on membrane sheets where each spot is individually accessed by manual or automated delivery of the appropriate reagent solutions. Over the past few years protein-protein recognition, peptide-metal ion interactions, peptide-nucleic acid binding, enzymatic modification of peptides experiments, have been explored using synthetic peptide arrays on planar support." [PMID:11167074]
subset: PSI-MI_slim
is_a: MI:0008 ! array technology

[Term]
id: MI:0082
name: peptide massfingerprinting
def: "This approach leads to protein identification by matching peptide masses, as measured by mass spectrometry, to the ones calculated from in silico fragmentation of a protein sequence database. A peptide mixture from a tryptic digest is analysed by MALDI-MS (Matrix-assisted laser desorption ionization mass spectrometry). The list of peptide masses obtained by MALDI MS is automatically compared to the calculated masses of the predicted peptide fragments for each entry in the database. High mass accuracy is very important in order to obtain a statistically significant and unambiguous match This method is best applied to completely sequenced genomes and well characterised proteomes. However, depending on the data quality, proteins that are highly homologous to already characterised proteins (greater than 80 to 90% sequence identity) can also be identified. The retrieved sequence are evaluated by mass accuracy of the peptides, matching of additional peptide masses in the MALDI spectrum after accounting for common modifications such as oxidation, acrylamidation of cysteine and missed cleavages and the use of secondary information (apparent isoelectric point and molecular weight). If any ambiguity about the identification by MALDI-MS still exists, the results must verified by an other identification method. Peptide mass fingerprint is generally carried out with a MALDI-TOF (Matrix-assisted laser desorption ionization time-of-flight ) instrument but can also be achieved ESI-TOF (Electrospray Ionisation time-of-flight) or LC-MS (Liquid Chromatography-Mass Spectrometry) mass spectrometer." [PMID:10967324, PMID:11752590, PMID:11805826]
subset: PSI-MI_slim
synonym: "fingerprinting" EXACT PSI-MI-short []
is_a: MI:0427 ! Identification by mass spectrometry
is_a: MI:0433 ! partial identification of protein sequence

[Term]
id: MI:0083
name: peptide synthesis
def: "When one of the partners participates in the interaction with a relatively short peptide fragment, it is often convenient to precisely identify the minimal region that supports the interaction by synthesising a series of overlapping peptides and by testing them in the binding assay. Synthetic peptides that are identical with peptides synthesised in vivo are useful experimental tools for such studies. Peptides are routinely synthesised in a test tube from monomeric amino acids by condensation reactions that form peptide bonds. Peptides are constructed sequentially by coupling the C-terminus of a monomeric amino acid to the N-terminus of the growing peptide. To prevent unwanted reactions involving the amino groups and carboxyl groups of the side chains during the coupling steps, a protecting (blocking) group is attached to the side chains. Without these protecting groups, branched peptides would be generated. In the last steps of synthesis, the side chain-protecting groups are removed and the peptide is cleaved from the resin on which synthesis occurs." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0093 ! protein sequence identification

[Term]
id: MI:0084
name: phage display
def: "Peptide sequences or entire proteins can be displayed on phage capsids by fusion to coat proteins to generate a library of fusion phages each displaying a different peptide. Such a library can then be exploited to identify specific phages that display peptides that bind to any given bait molecule for instance an antibody. The selection is performed by a series of cycles of affinity purification known as panning. The bait protein, immobilized on a solid support (plastic, agarose, sepharose, magnetic beads and others) is soaked in the phage mixture and that phage that remains attached to the bait is amplified and carried through a further affinity purification step. Each cycle results in an approximately 1,000-fold enrichment of specific phage and after a few selection rounds (2-4), DNA sequencing of the tight-binding phage reveals only a small number of sequences. Phage display panning experiments can be carried out either on libraries of peptides of random amino acid sequence or on libraries of displaying natural peptides obtained by inserting cDNA fragments into the phage vector (cDNA libraries). Libraries have been assembled on several different phages (Fd, Lambda or T7)." [PMID:10975452, PMID:7708014]
subset: PSI-MI_slim
is_a: MI:0034 ! display technology

[Term]
id: MI:0085
name: phylogenetic profile
def: "The phylogenetic profile of a protein stores information about the presence and the absence of that protein in a set of genomes. By clustering identical or similar profiles, proteins with similar functions and potentially interacting are identified." [PMID:10200254]
subset: PSI-MI_slim
is_a: MI:0058 ! genome based prediction

[Term]
id: MI:0086
name: polyclonal antibody western blot
def: "Western blot assay carried out using a mixture of different antibodies that represent the immune response, normally in an experimental animal, to the protein of interest." [PMID:14755292]
subset: PSI-MI_slim
synonym: "polyclonal western" EXACT PSI-MI-short []
is_a: MI:0113 ! western blot

[Term]
id: MI:0087
name: predictive text mining
def: "Methods based on natural language processing to detect possible interactions between proteins (direct physical interactions or indirect genetic interactions). This includes the detection of non ambiguous protein or gene names and analysis of the relation expressed in a sentence among them." [PMID:11791231]
subset: PSI-MI_slim
synonym: "predictive tm" EXACT PSI-MI-short []
is_a: MI:0110 ! text mining

[Term]
id: MI:0088
name: primer specific pcr
def: "Sequences can be identified in a DNA mixture by launching a PCR (Polymerase Chain Reaction) controlled by sequence specific primers. Such reaction starts only when the hybridization of the primer with a complementary sequence occurs." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0080 ! partial DNA sequence identification by hybridization

[Term]
id: MI:0089
name: protein array
def: "The protein array technology allows the screening of biochemical activities or binding abilities of hundreds or thousands of protein samples in parallel. After synthesis and purification by high-throughput methodologies, the proteins are printed onto the chip by using an instrument (micro-arrayer) that is capable of spotting liquid samples in a reproducible manner onto a planar support. The ordered protein array can then be probed with labelled molecules to identify proteins that bind to the bait." [PMID:10976071, PMID:12067604]
subset: PSI-MI_slim
is_a: MI:0008 ! array technology

[Term]
id: MI:0090
name: protein complementation assay
def: "In the protein-fragment complementation assay, the proteins of interest (\"Bait\" and \"Prey\") are covalently linked at the genetic level to incomplete fragments of a third protein (known as the \"reporter\") and are expressed in vivo, Interaction between the \"bait\" and the \"prey\" proteins brings the fragments of the \"reporter\" protein in close enough proximity to allow them to reform and become the functional reporter protein. Typically enzymes which confer resistance to antibiotics, such as Dihydrofolate reductase or Beta-lactamase, or proteins that give colorimetric or fluorescent signals are used. The Bait protein is generally the protein under study and the methods are readily adaptable to highthroughput mode." [PMID:11495741]
subset: PSI-MI_slim
synonym: "complementation" EXACT PSI-MI-short []
synonym: "PCA" EXACT PSI-MI-alternate []
is_a: MI:0045 ! experimental interaction detection

[Term]
id: MI:0091
name: chromatography technology
def: "Used to separate and/or analyse complex mixtures. The components to be separated are distributed between two phases: a stationary phase (bed) and a mobile phase which percolates through the stationary bed. The nature of the two phases determines the separation criteria exploited by the column such as affinity, ionic charges, size or hydrophobicity of the molecules under analysis. Each type of column can be implemented with the mobile phase under atmospheric or high pressure condition. In this later case columns are designated as High Pressure Liquid Chromatography (HPLC)." [PMID:14755292]
subset: PSI-MI_slim
synonym: "chromatography" EXACT PSI-MI-short []
synonym: "column chromatography" EXACT PSI-MI-alternate []
is_a: MI:0401 ! biochemical

[Term]
id: MI:0092
name: protein in situ array
def: "Protein In Situ Array is a method by which protein arrays are rapidly generated in one step directly from DNA, by cell-free protein expression and simultaneous in situ immobilisation at a surface. Individual genes or fragments are produce by PCR or RT-PCR depending on the source of genetic material using properly designed primers. The PISA is generated by cell-free protein synthesis using coupled transcription and translation to produce a tagged protein, the reaction being carried out on a surface to which the protein adheres as soon as it is synthesised." [PMID:11470888]
subset: PSI-MI_slim
synonym: "PISA" EXACT PSI-MI-alternate []
synonym: "pisa" EXACT PSI-MI-short []
is_a: MI:0089 ! protein array

[Term]
id: MI:0093
name: protein sequence identification
def: "Single amino acid identification along a protein sequence." [PMID:14755292]
subset: PSI-MI_slim
synonym: "protein sequence" EXACT PSI-MI-short []
is_a: MI:0661 ! experimental participant identification

[Term]
id: MI:0094
name: protein staining
def: "A wide range of dyes have been used over the years to visualise proteins in polyacrylamide gels - Coomasie Blue and silver-staining being two classical methods. Fluorescent dyes such as Nile Red and SYPRO Orange are now increasingly used due to their superior dynamic range. Use of non-denaturing gels can allow visualisation of protein protein interactions. Several dyes can be used to specifically indicate residue modification, however this methodology will give no information as the number of residues modified or their position within the protein sequence. Examples include the use of acid fuscian or the fluorescent dansyl hydrazine to show protein glycosylation." [PMID:12015990]
subset: PSI-MI_slim
is_a: MI:0659 ! experimental feature detection

[Term]
id: MI:0095
name: proteinchip(r) on a surface-enhanced laser desorption/ionization
def: "ProteinChip(r) Array technology is a surface-enhanced laser desorption/ionization (SELDI) approach (Ciphergen Biosystems Inc. Fremont, CA, USA) for sample fractionation accomplished by retentate chromatography. Retentate chromatography is performed on ProteinChip Arrays with varying chromatographic properties (e.g. anion exchange, cation exchange, metal affinity and reverse phase). By utilising arrays with differing surface chemistries in parallel and in series, a complex mixture of proteins, as from cells or body fluids, can be resolved into subsets of proteins with common properties. Specific analytes can also be examined by using preactivated arrays to which a bait molecule (such as an antibody or biotinylated DNA) is immobilized and a solution containing the binding partner(s) is presented to the array. This array-based immunoprecipitation or protein-binding experiment has been used with good success to study DNA-binding proteins, receptor-ligand interactions, and protein complexes. Any ligand retained on a SELDI chip can directly be identified by mass spectrometry." [PMID:11827829]
subset: PSI-MI_slim
synonym: "seldi chip" EXACT PSI-MI-short []
synonym: "SELDI ProteinChip" EXACT PSI-MI-alternate []
is_a: MI:0089 ! protein array

[Term]
id: MI:0096
name: pull down
def: "A specific affinity chromatography method where a molecule of interest (bait) is bound to a column, often via an affinity tag expressed as a protein fusion  (GST, HIS tag and others) or chemically linked to the bait molecule . The molecule may be expressed or synthesised and purified first, often in an heterologous system, bound to the matrix at high concentration and then challenged with a solution or cellular extract containing the candidate partner molecules. Alternatively, a multi-molecular complex may be adsorbed to the resin and the retained binding molecules subsequently identified." [PMID:14755292]
subset: PSI-MI_slim
synonym: "affinity capture" RELATED []
synonym: "pulldown" RELATED []
is_a: MI:0004 ! affinity chromatography technology

[Term]
id: MI:0097
name: reverse ras recruitment system
def: "In this complementation approach the bait can be any membrane protein (for example a receptor or a channel protein), the prey is cloned as a fusion protein of any cDNA from a library and the coding sequence of cytoplasmic RAS (cdc25 in yeast). If the bait and the prey interact, RAS is recruited close to the membrane and can activate cell growth. This procedure must take place in cells having a mutated RAS (Cdc25-2 yeast strain having a temperature sensitive mutation of RAS) to avoid constitutive growth activation." [PMID:11160938]
subset: PSI-MI_slim
synonym: "reverse RRS" EXACT PSI-MI-alternate []
synonym: "reverse rrs" EXACT PSI-MI-short []
is_a: MI:0090 ! protein complementation assay

[Term]
id: MI:0098
name: ribosome display
def: "This method permits the coupling of phenotype to genotype via the formation of a non-covalent ternary complex between mRNAs and their encoded polypeptides while they are translated in an in vitro system. As a first step a cDNA library is constructed that encodes chimeric proteins in which the natural proteins or protein domains are fused to a C-terminal tether. As a consequence when the mRNA is translated in vitro the domain can fold while the tether is still in the ribosomal tunnel. Furthermore this chimeric mRNAs lack a stop codon, thus preventing release of the mRNA and the polypeptide from the ribosome. High concentrations of magnesium and low temperature further stabilise the ternary complex. Similarly to phage display, these complexes can be used directly to select for nucleic acids encoding proteins with desired properties." [PMID:11551470, PMID:12167034]
subset: PSI-MI_slim
is_a: MI:0034 ! display technology

[Term]
id: MI:0099
name: scintillation proximity assay
def: "SPA relies upon the fact that a beta particle emitted from a radioisotope decay can excite a fluorophore only when it is at a very short distance in water solution (few micrometers). The ligand is labelled with a radioactive atom and its potential partner is fixed to fluorophore containing beads, the emitted fluorescence proving their interaction can be measured in a scintillation counter. The scintillator measures only the amount of bound radiolabelled ligand. Competition experiment with cold competitor can be done to estimate the binding affinities (50% inhibitory concentration [IC50], cold ligand versus labelled ligand). Loss of signal can also be used to measure substrate cleavage by an enzyme, and labelled antibodies used to titrate the degree of modified residue present." [PMID:3866247]
subset: PSI-MI_slim
synonym: "RIA Radio Immuno Assay" EXACT PSI-MI-alternate []
synonym: "SPA" EXACT PSI-MI-alternate []
synonym: "spa" EXACT PSI-MI-short []
is_a: MI:0013 ! biophysical

[Term]
id: MI:0100
name: sequence based phylogenetic profile
def: "Multiple alignments of orthologous sequences in the same species and their corresponding phylogenetic trees are built. Every phylogenetic tree is computed as a matrix of distances between all possible interacting pairs. The covariation of the distance matrices reveals interacting pairs." [PMID:11707606]
subset: PSI-MI_slim
synonym: "sequence phylogeny" EXACT PSI-MI-short []
is_a: MI:0058 ! genome based prediction
is_a: MI:0101 ! sequence based prediction

[Term]
id: MI:0101
name: sequence based prediction
def: "Computational methods based on evolutionary hypothesis, used as criteria to browse sequences and predict interacting pairs." [PMID:14755292]
subset: PSI-MI_slim
synonym: "predict from sequenc" EXACT PSI-MI-short []
is_a: MI:0063 ! interaction prediction

[Term]
id: MI:0102
name: sequence tag identification
def: "This approach leads to protein identification by combining mass measurement and short amino acid sequence information obtained by tandem mass spectrometry. This information is then used to automatically find the best match in a sequence database. A mixture of peptides derived from a protease digestion is analysed by nanoelectrospray LC-MS/MS (Liquid Chromatography Tandem Mass Spectrometer or nanoESI MS/MS) mass spectrometry. Electrospray mass spectrometry cannot be applied to dilute samples and is affected by high salt. As a consequence peptides, normally extracted from acrylamide gels by in situ proteolysis, are desalted and concentrated on a microcolumn followed by elution into a capillary used for nanoelectrospray tandem mass spectrometry. A first mass spectrum (Normal mass spectrum or Q1 mass spectrum) gives information about the masses of all the peptides. Peptides observed in the normal mass spectrum are isolated in turn and dissociated into fragments by collision with gas molecules within the mass spectrometer. Some of the fragments obtained from a peptide constitute a nested set, differing by one amino acid, and the mass difference between them allows assignment of a partial sequence. The masses of the fragments define the position of the partial sequence in the peptide. Together with the cleavage specificity of the protease used to cleave the protein, and mass information such sequence tag provides much higher search specificity to match the a database entry. The procedure is repeated with several peptides from the digest, resulting in multiple identifications of the same protein or identification of several proteins from the peptide mixture. Unknown proteins can easily be identified by using the high specificity of the peptide sequence tag for searches in most sequence databases including EST or genome databases." [PMID:10967324, PMID:11752590, PMID:11805837]
subset: PSI-MI_slim
synonym: "MS/MS" RELATED []
synonym: "sequence tag" EXACT PSI-MI-short []
is_a: MI:0427 ! Identification by mass spectrometry
is_a: MI:0433 ! partial identification of protein sequence

[Term]
id: MI:0103
name: southern blot
def: "A standard procedure to identify DNA fragments containing specific gene sequences. In this procedure i) a genome is fragmented using a restriction enzyme ii) the generated fragments are separated by electrophoresis iii) the fragments are transferred to a membrane iv)the membrane is incubated with a radio labelled probe that hybridises any complementary subsequence." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0080 ! partial DNA sequence identification by hybridization

[Term]
id: MI:0104
name: static light scattering
def: "In static light scattering, the average intensity of scattered light at multiple angles is measured. The data yield information on particle molecular weight, particle size and shape, and particle-particle interactions." [PMID:9013660]
subset: PSI-MI_slim
synonym: "sls" EXACT PSI-MI-short []
is_a: MI:0067 ! light scattering

[Term]
id: MI:0105
name: structure based prediction
def: "Methods based on 3D structure information." [PMID:14755292]
subset: PSI-MI_slim
synonym: "predict from struct" EXACT PSI-MI-short []
is_a: MI:0063 ! interaction prediction

[Term]
id: MI:0106
name: surface patches
def: "Surface patches are built using 6 criteria: solvation potential, residue interface propensity, hydrophobicity, planarity, protrusion and accessible surface area. Protein structures having similar patches are likely to have the same interactions." [PMID:9299343]
subset: PSI-MI_slim
is_a: MI:0577 ! feature prediction from structure

[Term]
id: MI:0107
name: surface plasmon resonance
def: "This method measures formation of complex by monitoring changes in the resonance angle of light impinging on a gold surface as a result of changes in the refractive index of the surface. A ligand of interest (small molecule, peptide, protein, sugar, lipid, nucleic acid) is immobilized on a gold surface, and the interacting partner is injected in buffer flow over it. Biomolecules that interact with the immobilized ligand are retained on the surface, and alter the resonance angle of impinging light as a result of the change in refractive index brought about by the increased biomolecule mass retained on the surface. Since all the biomolecules belonging to the same class have the same refractive index and since there is a linear correlation between resonance angle shift and biomolecule concentration near the surface, this allows one to measure changes in concentration at the surface as a consequence of interaction. Furthermore, this is done in real time, allowing direct measurement of both the on-rate and the off-rate and of the affinity constant of complex formation." [PMID:11896282, PMID:12120258, PMID:16338355]
subset: PSI-MI_slim
synonym: "BIAcore(r)" EXACT PSI-MI-alternate []
synonym: "Optical biosensor" EXACT PSI-MI-alternate []
synonym: "spr" EXACT PSI-MI-short []
is_a: MI:0659 ! experimental feature detection
is_a: MI:0968 ! biosensor

[Term]
id: MI:0108
name: t7 phage display
def: "T7 is a double stranded DNA bacteriophage with a thin-walled icosahedral capsid, ~550 Angstrom in diameter, which is decorated by 415 copies of the capsid protein, the product of gene 10. gp10 can tolerate insertions at the carboxyterminus without loosing its ability to be inserted into functional phage capsids. Both low density and high density display (albeit only with short peptides) can be achieved." [PMID:14755292]
comment: Reference not index in medline: Rosenberg, A, Griffin, K, Studier, WS, McCormick, M, Berg, J, Novy, R, Mierendorf, R inNovations, 1996, 6, 1.
subset: PSI-MI_slim
synonym: "t7 phage" EXACT PSI-MI-short []
is_a: MI:0084 ! phage display

[Term]
id: MI:0109
name: tap tag coimmunoprecipitation
def: "The TAP method involves the fusion of the TAP tag (encoding a calmodulin binding peptide, a TEV cleavage site, and the Staphylococcus aureus Protein A) to the target protein and the introduction of the construct into the host cell or organism, maintaining the expression of the fusion protein at, or close to, its natural level. The fusion protein and associated components are recovered from cell extracts by affinity selection on an IgG matrix. After washing, the TEV protease is added to release the bound material. The eluate is incubated with calmodulin-coated beads in the presence of calcium. This second affinity step is required to remove the TEV protease as well as traces of contaminants remaining after the first affinity selection. After washing, the bound material is released with EGTA. This two steps purification steps ensures a highly selective complex purification of the tapped protein (first round of selection on the protein A, a high affinity tag) under mild condition (non denaturant pH or conditions required to remove the tag).\nOBSOLETE redundant term. Map to feature type: tap tagged (MI:0524) and  as interaction detection method  tandem affinity purification (MI:0676)." [PMID:10504710]
subset: PSI-MI_slim
synonym: "tap tag coip" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0110
name: text mining
def: "Text mining methods can be used to predict or confirm interactions by automated processing of scientific literature. Co-occurrence in the same sentence of an abstract of gene products labels are analysed to evaluate whether it represents a valid evidence of an interaction." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0046 ! experimental knowledge based

[Term]
id: MI:0111
name: dihydrofolate reductase reconstruction
def: "The gene for DHFR is rationally dissected into two fragments called F[1,2] and F[3]. Two proteins or protein domains that are thought to bind to each other can then be fused to either of the two DHFR fragments. Reconstitution of enzyme activity can be monitored in vivo by cell survival in DHFR-negative cells grown in the absence of nucleotides. A fluorescence assay can also be carried out taking advantage of fMTX binding to reconstituted DHFR. The basis of this assay is that complementary fragments of DHFR, when expressed and reassembled in cells, will bind with high affinity (Kd 5 540 pM) to fMTX in a 1:1 complex. fMTX is retained in cells by this complex, whereas the unbound fMTX is actively and rapidly transported out of the cells. Survival depends only on the number of molecules of DHFR reassembled." [PMID:10318894]
subset: PSI-MI_slim
synonym: "dhfr reconstruction" EXACT PSI-MI-short []
is_a: MI:0090 ! protein complementation assay

[Term]
id: MI:0112
name: ubiquitin reconstruction
def: "The split-ubiquitin system provides a method for examining the interactions of membrane proteins.  In the split-ubiquitin system, two integral membrane proteins to be studied are fused to two different ubiquitin moieties: a C-terminal ubiquitin moiety (\"Cub\", residues 35-76) and an N-terminal ubiquitin moiety (\"Nub\", residues 1-34). These fused proteins are called the bait and prey, respectively. In addition to being fused to an integral membrane protein, the Cub moiety is also fused to a transcription factor  that can be cleaved off by ubiquitin specific proteases. Upon bait-prey interaction, Nub and Cub-moieties assemble, reconstituting the split-ubiquitin. The reconstituted split-ubiquitin molecule is recognized by ubiquitin specific proteases, which cleave off the reporter protein, allowing it to induce the transcription of reporter genes." [PMID:9560251]
subset: PSI-MI_slim
synonym: "membrane yeast two-hybrid" RELATED []
synonym: "myth" RELATED []
synonym: "split-ubiquitin" RELATED []
synonym: "ub reconstruction" EXACT PSI-MI-short []
is_a: MI:1320 ! membrane yeast two hybrid

[Term]
id: MI:0113
name: western blot
def: "Western blot is a procedure to identify and quantify proteins. A mixture of protein is first submitted to an electrophoresis in denaturing condition and then electro-transferred from the gel to a membrane. The membrane is then incubated with a primary antibody specific for a given protein or a specific residue modification in the sample under analysis. A secondary antibody, radiolabelled or fused to fluorophore or to a chromogenic enzyme, targets the first antibody and allows the visualisation of the protein band on the membrane." [PMID:14755292]
subset: PSI-MI_slim
synonym: "Immuno blot" EXACT PSI-MI-alternate []
is_a: MI:0421 ! identification by antibody
is_a: MI:0659 ! experimental feature detection

[Term]
id: MI:0114
name: x-ray crystallography
def: "Analysis of a diffraction pattern generated by a single crystal. X-rays have a wavelength, typically around 1 Angstrom (the diameter of a hydrogen atom). If a narrow parallel beam of X-rays is directed at a sample of a pure protein, most of the X-rays will pass straight through it. A small fraction, however, will be scattered by the atoms in the sample. If the sample is a well-ordered crystal, the scattered waves will reinforce one another at certain points and will appear as diffraction spots when the X-rays are recorded by a suitable detector. The position and intensity of each spot in the X-ray diffraction pattern contain information about the position and nature of the atoms in the crystal. The three-dimensional structure of a large molecule can be deduced from the electron-density map of its crystal. In recent years X-ray diffraction analysis has become increasingly automated, and now the slowest step is likely to be the production of suitable macromolecule crystals. This requires high concentration of very pure macromolecule and empirical searching for the proper crystallization conditions." [PMID:14755292]
subset: PSI-MI_slim
synonym: "co-crystallization" RELATED []
synonym: "co-crystallography" RELATED []
synonym: "X-ray" EXACT PSI-MI-alternate []
synonym: "x-ray diffraction" EXACT PSI-MI-short []
is_a: MI:0013 ! biophysical
is_a: MI:0659 ! experimental feature detection

[Term]
id: MI:0115
name: yeast display
def: "The proteins are displayed on the surface of the yeast S. cerevisiae by fusion to signal sequences for protein secretion. This method is limited by the low efficiency of the yeast display system but can take full advantage of exploiting cell sorting methods (FACS) to isolate cells that display molecules with desired binding properties." [PMID:9181578]
subset: PSI-MI_slim
is_a: MI:0034 ! display technology
is_a: MI:0054 ! fluorescence-activated cell sorting

[Term]
id: MI:0116
name: feature type
def: "Property of a subsequence that may interfere with the binding of a molecule." [PMID:14755292]
subset: PSI-MI_slim
relationship: part_of MI:0000 ! molecular interaction

[Term]
id: MI:0117
name: binding-associated region
def: "A region of a molecule or a component of a complex identified as being involved in an interaction. This may or may not be a region of the molecule in direct contact with the interacting partner." [PMID:14755292]
subset: PSI-MI_slim
synonym: "binding component" RELATED []
synonym: "binding region" EXACT PSI-MI-short []
synonym: "binding site" BROAD []
is_a: MI:0252 ! biological feature

[Term]
id: MI:0118
name: mutation
def: "A change in a sequence or structure in comparison to a reference entity due to a  insertion, deletion or substitution event." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0252 ! biological feature

[Term]
id: MI:0119
name: mutation decreasing interaction
def: "Region of a molecule whose mutation or deletion decreases significantly interaction strength  or rate (in the case of interactions inferred from enzymatic reaction)." [PMID:14755292]
subset: PSI-MI_slim
synonym: "hotspot" EXACT PSI-MI-alternate []
synonym: "mutation decreasing" EXACT PSI-MI-short []
is_a: MI:0118 ! mutation

[Term]
id: MI:0120
name: post translation modification
def: "Residue covalent modifications occurring in the specific protein form involved in an interaction.\nOBSOLETE remap to MOD:00000." [PMID:14755292]
synonym: "ptm" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0121
name: acetylated residue
def: "Residue modification.\nOBSOLETE remap to MOD:00394." [PMID:11125103]
is_obsolete: true

[Term]
id: MI:0122
name: n-acetyl-alanine
def: "Residue modification.\nOBSOLETE remap to MOD:00050." [PMID:11125103, RESID:AA0041]
synonym: "(S)-2-(acetylamino)propanoic acid" EXACT PSI-MI-alternate []
synonym: "[A:ac]" EXACT PSI-MI-alternate []
synonym: "AAC" EXACT PSI-MI-alternate []
synonym: "acetylalanine" EXACT PSI-MI-alternate []
synonym: "acetylalanine" EXACT PSI-MI-short []
synonym: "N-acetyl-L-alanine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0123
name: n2-acetyl-arginine
def: "Residue modification.\nOBSOLETE remap to MOD:00359." [PMID:11125103, RESID:AA0354]
synonym: "[R:ac]" EXACT PSI-MI-alternate []
synonym: "acetylarginine" EXACT PSI-MI-alternate []
synonym: "acetylarginine" EXACT PSI-MI-short []
synonym: "alpha-acetylamino-delta-guanidinovaleric acid" EXACT PSI-MI-alternate []
synonym: "N2-acetyl-L-arginine" EXACT PSI-MI-alternate []
synonym: "RAC" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0124
name: n-acetyl-asparagine
def: "Residue modification.\nOBSOLETE remap to MOD:00780." [PMID:11125103]
synonym: "[N:ac]" EXACT PSI-MI-alternate []
synonym: "acetylasparagine" EXACT PSI-MI-short []
synonym: "N-acetyl-L-asparagine" EXACT PSI-MI-alternate []
synonym: "NAC" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0125
name: n-acetyl-aspartic acid
def: "Residue modification.\nOBSOLETE remap to MOD:00051." [PMID:11125103, RESID:AA0042]
synonym: "(S)-2-(acetylamino)butanedioic acid" EXACT PSI-MI-alternate []
synonym: "[D:ac]" EXACT PSI-MI-alternate []
synonym: "acetylaspartate" EXACT PSI-MI-short []
synonym: "acetylaspartic acid" EXACT PSI-MI-alternate []
synonym: "DAC" EXACT PSI-MI-alternate []
synonym: "N-acetyl-L-aspartic acid" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0126
name: n-acetyl-cysteine
def: "Residue modification.\nOBSOLETE remap to MOD:00052." [PMID:11125103, RESID:AA0043]
synonym: "(R)-2-acetylamino-3-sulfanylpropanoic acid" EXACT PSI-MI-alternate []
synonym: "2-acetylamino-3-mercaptopropanoic acid" EXACT PSI-MI-alternate []
synonym: "[C:ac]" EXACT PSI-MI-alternate []
synonym: "acetylcysteine" EXACT PSI-MI-short []
synonym: "CAC" EXACT PSI-MI-alternate []
synonym: "N-acetyl-L-cysteine" EXACT PSI-MI-alternate []
synonym: "N-acetylcysteine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0127
name: n-acetyl-glutamine
def: "Residue modification.\nOBSOLETE remap to MOD:00054." [PMID:11125103, RESID:AA0045]
synonym: "(S)-2-acetylamino-5-pentanediamic acid" EXACT PSI-MI-alternate []
synonym: "[Q:ac]" EXACT PSI-MI-alternate []
synonym: "acetylglutamine" EXACT PSI-MI-alternate []
synonym: "acetylglutamine" EXACT PSI-MI-short []
synonym: "N-acetyl-L-glutamine" EXACT PSI-MI-alternate []
synonym: "QAC" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0128
name: n-acetyl-glutamic acid
def: "Residue modification.\nOBSOLETE remap to MOD:00053." [PMID:11125103, RESID:AA0044]
synonym: "(S)-2-(acetylamino)pentanedioic acid" EXACT PSI-MI-alternate []
synonym: "[E:ac]" EXACT PSI-MI-alternate []
synonym: "acetylglutamate" EXACT PSI-MI-short []
synonym: "acetylglutamic acid" EXACT PSI-MI-alternate []
synonym: "EAC" EXACT PSI-MI-alternate []
synonym: "N-acetyl-L-glutamic acid" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0129
name: n-acetylglycine
def: "Residue modification.\nOBSOLETE remap to MOD:00055." [PMID:11125103, RESID:AA0046]
synonym: "2-(acetylamino)ethanoic acid" EXACT PSI-MI-alternate []
synonym: "[G:ac]" EXACT PSI-MI-alternate []
synonym: "aceturic acid" EXACT PSI-MI-alternate []
synonym: "acetylglycine" EXACT PSI-MI-short []
synonym: "GAC" EXACT PSI-MI-alternate []
synonym: "N-acetylglycine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0130
name: n-acetyl-histidine
def: "Residue modification.\nOBSOLETE remap to MOD:00781." [PMID:11125103]
synonym: "[H:ac]" EXACT PSI-MI-alternate []
synonym: "acetylhistidine" EXACT PSI-MI-short []
synonym: "HAC" EXACT PSI-MI-alternate []
synonym: "N-acetyl-L-histidine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0131
name: n-acetyl-isoleucine
def: "Residue modification.\nOBSOLETE remap to MOD:00056." [PMID:11125103, RESID:AA0047]
synonym: "(2S,3S)-2-acetylamino-3-methylpentanoic acid" EXACT PSI-MI-alternate []
synonym: "[I:ac]" EXACT PSI-MI-alternate []
synonym: "acetylisoleucine" EXACT PSI-MI-alternate []
synonym: "acetylisoleucine" EXACT PSI-MI-short []
synonym: "IAC" EXACT PSI-MI-alternate []
synonym: "N-acetyl-L-isoleucine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0132
name: n-acetyl-leucine
def: "Residue modification.\nOBSOLETE remap to MOD:00782." [PMID:11125103]
synonym: "[L:ac]" EXACT PSI-MI-alternate []
synonym: "acetylleucine" EXACT PSI-MI-short []
synonym: "LAC" EXACT PSI-MI-alternate []
synonym: "N-acetyl-L-leucine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0133
name: n2-acetyl-lysine
def: "Residue modification.\nOBSOLETE remap to MOD:00057." [PMID:11125103, RESID:AA0048]
synonym: "(S)-2-acetylamino-6-aminohexanoic acid" EXACT PSI-MI-alternate []
synonym: "[K:ac]" EXACT PSI-MI-alternate []
synonym: "KAC" EXACT PSI-MI-alternate []
synonym: "N2-acetyl-L-lysine" EXACT PSI-MI-alternate []
synonym: "N2-acetyllysine" EXACT PSI-MI-alternate []
synonym: "n2-acetyllysine" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0134
name: n6-acetyl-lysine
def: "Residue modification.\nOBSOLETE remap to MOD:00064." [PMID:11125103, RESID:AA0055]
synonym: "(S)-2-amino-6-(acetylamino)hexanoic acid" EXACT PSI-MI-alternate []
synonym: "[K:N6ac]" EXACT PSI-MI-alternate []
synonym: "epsilon-acetyllysine" EXACT PSI-MI-alternate []
synonym: "KA6" EXACT PSI-MI-alternate []
synonym: "N(zeta)-acetyllysine" EXACT PSI-MI-alternate []
synonym: "N6-acetyl-L-lysine" EXACT PSI-MI-alternate []
synonym: "n6-acetyllysine" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0135
name: n-acetyl-methionine
def: "Residue modification.\nOBSOLETE remap to MOD:00058." [PMID:11125103, RESID:AA0049]
synonym: "(S)-2-acetylamino-4-(methylsulfanyl)butanoic acid" EXACT PSI-MI-alternate []
synonym: "2-acetylamino-4-(methylthio)butanoic acid" EXACT PSI-MI-alternate []
synonym: "[M:ac]" EXACT PSI-MI-alternate []
synonym: "acetylmethionine" EXACT PSI-MI-alternate []
synonym: "acetylmethionine" EXACT PSI-MI-short []
synonym: "MAC" EXACT PSI-MI-alternate []
synonym: "methionamine" EXACT PSI-MI-alternate []
synonym: "N-acetyl-L-methionine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0136
name: n-acetyl-phenylalanine
def: "Residue modification.\nOBSOLETE remap to MOD:00784." [PMID:11125103]
synonym: "[F:ac]" EXACT PSI-MI-alternate []
synonym: "acetylphenylalanine" EXACT PSI-MI-short []
synonym: "FAC" EXACT PSI-MI-alternate []
synonym: "N-acetyl-L-phenylalanine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0137
name: n-acetyl-proline
def: "Residue modification.\nOBSOLETE remap to MOD:00059." [PMID:11125103, RESID:AA0050]
synonym: "(2S)-1-acetyl-2-pyrrolidinecarboxylic acid" EXACT PSI-MI-alternate []
synonym: "[P:ac]" EXACT PSI-MI-alternate []
synonym: "acetylproline" EXACT PSI-MI-alternate []
synonym: "acetylproline" EXACT PSI-MI-short []
synonym: "N-acetyl-L-proline" EXACT PSI-MI-alternate []
synonym: "PAC" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0138
name: n-acetyl-serine
def: "Residue modification.\nOBSOLETE remap to MOD:00060." [PMID:11125103, RESID:AA0051]
synonym: "(S)-2-acetylamino-3-hydroxypropanoic acid" EXACT PSI-MI-alternate []
synonym: "[S:ac]" EXACT PSI-MI-alternate []
synonym: "acetylserine" EXACT PSI-MI-short []
synonym: "N-acetyl-L-serine" EXACT PSI-MI-alternate []
synonym: "N-acetylserine" EXACT PSI-MI-alternate []
synonym: "SAC" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0139
name: n-acetyl-threonine
def: "Residue modification.\nOBSOLETE remap to MOD:00061." [PMID:11125103, RESID:AA0052]
synonym: "(2S,3R)-2-acetylamino-3-hydroxybutanoic acid" EXACT PSI-MI-alternate []
synonym: "[T:ac]" EXACT PSI-MI-alternate []
synonym: "acetylthreonine" EXACT PSI-MI-short []
synonym: "N-acetyl-L-threonine" EXACT PSI-MI-alternate []
synonym: "N-acetylthreonine" EXACT PSI-MI-alternate []
synonym: "TAC" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0140
name: n-acetyl-tryptophan
def: "Residue modification.\nOBSOLETE remap to MOD:00785." [PMID:11125103]
synonym: "[W:ac]" EXACT PSI-MI-alternate []
synonym: "acetyltryptophan" EXACT PSI-MI-short []
synonym: "N-acetyl-L-tryptophan" EXACT PSI-MI-alternate []
synonym: "WAC" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0141
name: n-acetyl-tyrosine
def: "Residue modification.\nOBSOLETE remap to MOD:00062." [PMID:11125103, RESID:AA0053]
synonym: "(S)-2-acetylamino-3-(4-hydoxyphenyl)propanoic acid" EXACT PSI-MI-alternate []
synonym: "[Y:ac]" EXACT PSI-MI-alternate []
synonym: "acetyltyrosine" EXACT PSI-MI-short []
synonym: "N-acetyl-L-tyrosine" EXACT PSI-MI-alternate []
synonym: "N-acetyltyrosine" EXACT PSI-MI-alternate []
synonym: "YAC" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0142
name: n-acetyl-valine
def: "Residue modification.\nOBSOLETE remap to MOD:00063." [PMID:11125103, RESID:AA0054]
synonym: "(S)-2-acetylamino-3-methylbutanoic acid" EXACT PSI-MI-alternate []
synonym: "[V:ac]" EXACT PSI-MI-alternate []
synonym: "acetylvaline" EXACT PSI-MI-short []
synonym: "N-acetyl-L-valine" EXACT PSI-MI-alternate []
synonym: "N-acetylvaline" EXACT PSI-MI-alternate []
synonym: "VAC" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0143
name: amidated residue
def: "Residue modification.\nOBSOLETE remap to MOD:00674." [PMID:11125103]
is_obsolete: true

[Term]
id: MI:0145
name: arginine amide
def: "Residue modification.\nOBSOLETE remap to MOD:00091." [PMID:11125103, RESID:AA0082]
synonym: "(S)-2-amino-5-guanidinopentanamide" EXACT PSI-MI-alternate []
synonym: "[R:am]" EXACT PSI-MI-alternate []
synonym: "argininamide" EXACT PSI-MI-alternate []
synonym: "arginineamide" EXACT PSI-MI-short []
synonym: "L-arginine amide" EXACT PSI-MI-alternate []
synonym: "RAM" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0146
name: formylated residue
def: "Residue modification.\nOBSOLETE remap to MOD:00493." [PMID:11125103]
is_obsolete: true

[Term]
id: MI:0147
name: n-formyl-methionine
def: "Residue modification.\nOBSOLETE remap to MOD:00030." [PMID:11125103, RESID:AA0021]
synonym: "(S)-2-formylamino-4-(methylsulfanyl)butanoic acid" EXACT PSI-MI-alternate []
synonym: "2-formylamino-4-(methylthio)butanoic acid" EXACT PSI-MI-alternate []
synonym: "[M:form]" EXACT PSI-MI-alternate []
synonym: "formylmethionine" EXACT PSI-MI-short []
synonym: "MFM" EXACT PSI-MI-alternate []
synonym: "N-formyl-L-methionine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0148
name: hydroxylated residue
def: "Residue modification.\nOBSOLETE remap to MOD:00428." [PMID:11125103]
is_obsolete: true

[Term]
id: MI:0150
name: lipid modification
def: "Residue modification.\nOBSOLETE remap to MOD:01155." [PMID:11125103]
is_obsolete: true

[Term]
id: MI:0151
name: s-farnesyl-cysteine
def: "Residue modification.\nOBSOLETE remap to MOD:00111." [PMID:11125103, RESID:AA0102]
synonym: "(R,E,E)-2-amino-3-(3,7,11-trimethyl-2,6,10-dodecatrienylsulfanyl)propanoic acid" EXACT PSI-MI-alternate []
synonym: "2-amino-3-(3,7,11-trimethyl-2,6,10-dodecatrienylthio)propanoic acid" EXACT PSI-MI-alternate []
synonym: "[C:farn]" EXACT PSI-MI-alternate []
synonym: "CFN" EXACT PSI-MI-alternate []
synonym: "farnesylcysteine" EXACT PSI-MI-short []
synonym: "S-farnesyl-L-cysteine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0152
name: s-geranylgeranyl-cysteine
def: "Residue modification.\nOBSOLETE remap to MOD:00113." [PMID:11125103, RESID:AA0104]
synonym: "(R,E,E,E)-2-amino-3-(3,7,11,15-tetramethyl-2,6,10,14-hexadecatetraenylsulfanyl)propanoic acid" EXACT PSI-MI-alternate []
synonym: "2-amino-3-(3,7,11,15-tetramethyl-2,6,10,14-hexadecatetraenylthio)propanoic acid" EXACT PSI-MI-alternate []
synonym: "[C:ger]" EXACT PSI-MI-alternate []
synonym: "CGR" EXACT PSI-MI-alternate []
synonym: "geranylgeranylcys" EXACT PSI-MI-short []
synonym: "S-geranylgeranyl-L-cysteine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0153
name: n-palmitoyl-cysteine
def: "Residue modification.\nOBSOLETE remap to MOD:00069." [PMID:11125103, RESID:AA0060]
synonym: "(R)-2-hexadecanoylamino-3-sulfanylpropanoic acid" EXACT PSI-MI-alternate []
synonym: "2-hexadecanoylamino-3-mercaptopropanoic acid" EXACT PSI-MI-alternate []
synonym: "[C:palm_n]" EXACT PSI-MI-alternate []
synonym: "CPN" EXACT PSI-MI-alternate []
synonym: "N-(1-oxahexadecyl)-L-cysteine" EXACT PSI-MI-alternate []
synonym: "N-palmitoyl-L-cysteine" EXACT PSI-MI-alternate []
synonym: "n-palmitoylcysteine" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0154
name: s-palmitoyl-cysteine
def: "Residue modification.\nOBSOLETE remap to MOD:00115." [PMID:11125103, RESID:AA0106]
synonym: "(R)-2-amino-3-(hexadecanoylsulfanyl)propanoic acid" EXACT PSI-MI-alternate []
synonym: "2-amino-3-(hexadecanoylthio)propanoic acid" EXACT PSI-MI-alternate []
synonym: "[C:palm_s]" EXACT PSI-MI-alternate []
synonym: "CPS" EXACT PSI-MI-alternate []
synonym: "cysteine hexadecanoate thioester" EXACT PSI-MI-alternate []
synonym: "cysteine palmitate thioester" EXACT PSI-MI-alternate []
synonym: "S-palmitoyl-L-cysteine" EXACT PSI-MI-alternate []
synonym: "s-palmitoylcysteine" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0155
name: n-myristoyl-glycine
def: "Residue modification.\nOBSOLETE remap to MOD:00068." [PMID:11125103, RESID:AA0059]
synonym: "[G:myr]" EXACT PSI-MI-alternate []
synonym: "GMY" EXACT PSI-MI-alternate []
synonym: "myristoylglycine" EXACT PSI-MI-short []
synonym: "N-myristoyl-glycine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0156
name: n6-myristoyl-lysine
def: "Residue modification.\nOBSOLETE remap to MOD:00087." [PMID:11125103, RESID:AA0078]
synonym: "(S)-2-amino-6-(tetradecanoylamino)hexanoic acid" EXACT PSI-MI-alternate []
synonym: "[K:myr]" EXACT PSI-MI-alternate []
synonym: "epsilon-myristoyllysine" EXACT PSI-MI-alternate []
synonym: "KMY" EXACT PSI-MI-alternate []
synonym: "myristoyllysine" EXACT PSI-MI-short []
synonym: "N(zeta)-myristoyllysine" EXACT PSI-MI-alternate []
synonym: "N6-(1-oxotetradecyl)-L-lysine" EXACT PSI-MI-alternate []
synonym: "N6-myristoyl-L-lysine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0157
name: methylated residue
def: "Residue modification.\nOBSOLETE remap to MOD:00427." [PMID:11125103]
is_obsolete: true

[Term]
id: MI:0158
name: n-methyl-alanine
def: "Residue modification.\nOBSOLETE remap to MOD:00070." [PMID:11125103, RESID:AA0061]
synonym: "(S)-2-methylaminopropanoic acid" EXACT PSI-MI-alternate []
synonym: "[A:meth_n]" EXACT PSI-MI-alternate []
synonym: "AMT" EXACT PSI-MI-alternate []
synonym: "methylalanine" EXACT PSI-MI-short []
synonym: "N-methyl-L-alanine" EXACT PSI-MI-alternate []
synonym: "N-methylalanine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0159
name: n,n,n-trimethyl-alanine
def: "Residue modification.\nOBSOLETE remap to MOD:00071." [PMID:11125103, RESID:AA0062]
synonym: "(S)-1-carboxy-N,N,N-trimethylethanaminium" EXACT PSI-MI-alternate []
synonym: "(S)-2-(trimethylammonio)propanoic acid" EXACT PSI-MI-alternate []
synonym: "[A:meth_n3]" EXACT PSI-MI-alternate []
synonym: "AM3" EXACT PSI-MI-alternate []
synonym: "N,N,N-trimethyl-L-alanine" EXACT PSI-MI-alternate []
synonym: "trimethylalanine" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0160
name: omega-n,omega-n-dimethyl-arginine
def: "Residue modification.\nOBSOLETE remap to MOD:00077." [PMID:11125103, RESID:AA0068]
synonym: "(S)-2-amino-5-[((dimethylamino)iminomethyl)amino]pentanoic acid" EXACT PSI-MI-alternate []
synonym: "[R:meth_n7]" EXACT PSI-MI-alternate []
synonym: "asymmetric dimethylarginine" EXACT PSI-MI-alternate []
synonym: "dimethylarginine" EXACT PSI-MI-short []
synonym: "NG,NG-dimethylarginine" EXACT PSI-MI-alternate []
synonym: "omega-N,omega-N-dimethyl-L-arginine" EXACT PSI-MI-alternate []
synonym: "RM2" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0161
name: beta-methylthioaspartic acid
def: "Residue modification.\nOBSOLETE remap to MOD:00237." [PMID:11125103, RESID:AA0232]
synonym: "(2R,3Xi)-2-amino-3-methylsulfanylbutanedioic acid" EXACT PSI-MI-alternate []
synonym: "3-carboxy-S-methyl-cysteine" EXACT PSI-MI-alternate []
synonym: "3-methylthio-aspartic acid" EXACT PSI-MI-alternate []
synonym: "[D:meth_b]" EXACT PSI-MI-alternate []
synonym: "beta-methylthio-aspartic acid" EXACT PSI-MI-alternate []
synonym: "DM2" EXACT PSI-MI-alternate []
synonym: "L-beta-methylthioaspartic acid" EXACT PSI-MI-alternate []
synonym: "methylthioaspartate" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0162
name: n5-methyl-glutamine
def: "Residue modification.\nOBSOLETE remap to MOD:00080." [PMID:11125103, RESID:AA0071]
synonym: "(S)-2-amino-N5-methylpentanediamic acid" EXACT PSI-MI-alternate []
synonym: "[Q:meth_n5]" EXACT PSI-MI-alternate []
synonym: "gamma-methylglutamine" EXACT PSI-MI-alternate []
synonym: "methylglutamine" EXACT PSI-MI-short []
synonym: "N(delta)-methylglutamine" EXACT PSI-MI-alternate []
synonym: "N-methylglutamine" EXACT PSI-MI-alternate []
synonym: "N5-methyl-L-glutamine" EXACT PSI-MI-alternate []
synonym: "QM5" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0163
name: glutamic acid 5-methyl ester
def: "Residue modification.\nOBSOLETE remap to MOD:00081." [PMID:11125103, RESID:AA0072]
synonym: "(S)-2-aminopentanedioic acid 5-methyl ester" EXACT PSI-MI-alternate []
synonym: "5-methyl-L-glutamate" EXACT PSI-MI-alternate []
synonym: "[E:meth_o5]" EXACT PSI-MI-alternate []
synonym: "EM5" EXACT PSI-MI-alternate []
synonym: "glutamatemethylester" EXACT PSI-MI-short []
synonym: "glutamic acid gamma-methyl ester" EXACT PSI-MI-alternate []
synonym: "L-glutamic acid 5-methyl ester" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0165
name: n6-methyl-lysine
def: "Residue modification.\nOBSOLETE remap to MOD:00085." [PMID:11125103]
synonym: "(S)-2-amino-6-methylaminohexanoic acid" EXACT PSI-MI-alternate []
synonym: "[K:meth_1]" EXACT PSI-MI-alternate []
synonym: "epsilon-methyllysine" EXACT PSI-MI-alternate []
synonym: "methyllysine" EXACT PSI-MI-short []
synonym: "MLZ" EXACT PSI-MI-alternate []
synonym: "N(zeta)-methyllysine" EXACT PSI-MI-alternate []
synonym: "N6-methyl-L-lysine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0166
name: n6,n6-dimethyl-lysine
def: "Residue modification.\nOBSOLETE remap to MOD:00084." [PMID:11125103, RESID:AA0075]
synonym: "(S)-2-amino-6-dimethylaminohexanoic acid" EXACT PSI-MI-alternate []
synonym: "[K:meth_2]" EXACT PSI-MI-alternate []
synonym: "dimethyllysine" EXACT PSI-MI-short []
synonym: "epsilon-dimethyllysine" EXACT PSI-MI-alternate []
synonym: "lysine derivative Lys(y)" EXACT PSI-MI-alternate []
synonym: "MLY" EXACT PSI-MI-alternate []
synonym: "N(zeta)-dimethyllysine" EXACT PSI-MI-alternate []
synonym: "N6,N6-dimethyl-L-lysine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0167
name: n6,n6,n6-trimethyl-lysine
def: "Residue modification.\nOBSOLETE remap to MOD:00083." [PMID:11125103, RESID:AA0074]
synonym: "(S)-2-amino-6-(trimethylammonio)hexanoic acid" EXACT PSI-MI-alternate []
synonym: "(S)-5-amino-5-carboxy-N,N,N-trimethylpentanaminium" EXACT PSI-MI-alternate []
synonym: "[K:meth_3]" EXACT PSI-MI-alternate []
synonym: "epsilon-trimethyllysine" EXACT PSI-MI-alternate []
synonym: "M3L" EXACT PSI-MI-alternate []
synonym: "N(zeta)-trimethyllysine" EXACT PSI-MI-alternate []
synonym: "N6,N6,N6-trimethyl-L-lysine" EXACT PSI-MI-alternate []
synonym: "trimethyllysine" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0168
name: n-methyl-methionine
def: "Residue modification.\nOBSOLETE remap to MOD:00073." [PMID:11125103, RESID:AA0064]
synonym: "(S)-2-methylamino-4-(methylsulfanyl)butanoic acid" EXACT PSI-MI-alternate []
synonym: "2-methylamino-4-(methylthio)butanoic acid" EXACT PSI-MI-alternate []
synonym: "[M:meth]" EXACT PSI-MI-alternate []
synonym: "methylmethionine" EXACT PSI-MI-short []
synonym: "MMT" EXACT PSI-MI-alternate []
synonym: "N-methyl-L-methionine" EXACT PSI-MI-alternate []
synonym: "N-methylmethionine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0169
name: n-methyl-phenylalanine
def: "Residue modification.\nOBSOLETE remap to MOD:00074." [PMID:14755292]
synonym: "(S)-2-methylamino-3-phenylpropanoic acid" EXACT PSI-MI-alternate []
synonym: "[F:meth]" EXACT PSI-MI-alternate []
synonym: "FMT" EXACT PSI-MI-alternate []
synonym: "methylphenylalanine" EXACT PSI-MI-short []
synonym: "N-methyl-L-phenylalanine" EXACT PSI-MI-alternate []
synonym: "N-methylphenylalanine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0170
name: phosphorylated residue
def: "Residue modification.\nOBSOLETE remap to MOD:00696." [PMID:11125103]
synonym: "phosphorylated" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0171
name: omega-n-phospho-arginine
def: "Residue modification.\nOBSOLETE remap to MOD:00227." [PMID:11125103, RESID:AA0222]
synonym: "(S)-2-amino-5-[imino(phosphonoamino)methyl]aminopentanoic acid" EXACT PSI-MI-alternate []
synonym: "[R:po]" EXACT PSI-MI-alternate []
synonym: "alpha-amino-delta-phosphonoguanidinovaleric acid" EXACT PSI-MI-alternate []
synonym: "N5-[imino(phosphonoamino)methyl]-L-ornithine" EXACT PSI-MI-alternate []
synonym: "omega-N-phospho-L-arginine" EXACT PSI-MI-alternate []
synonym: "phosphoarginine" EXACT PSI-MI-short []
synonym: "RPO" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0172
name: aspartic 4-phosphoric anhydride
def: "Residue modification.\nOBSOLETE remap to MOD:00042." [PMID:11125103, RESID:AA0033]
synonym: "(S)-2-aminobutanedioic 4-phosphoric anhydride" EXACT PSI-MI-alternate []
synonym: "[D:po]" EXACT PSI-MI-alternate []
synonym: "beta-aspartyl phosphate" EXACT PSI-MI-alternate []
synonym: "DPO" EXACT PSI-MI-alternate []
synonym: "L-aspartic 4-phosphoric anhydride" EXACT PSI-MI-alternate []
synonym: "phosphoaspartic acid" EXACT PSI-MI-alternate []
synonym: "phosphoaspartic acid" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0173
name: s-phospho-cysteine
def: "Residue modification.\nOBSOLETE remap to MOD:00043." [PMID:11125103, RESID:AA0034]
synonym: "(R)-2-amino-3-(phosphonosulfanyl)propanoic acid" EXACT PSI-MI-alternate []
synonym: "[C:po]" EXACT PSI-MI-alternate []
synonym: "CPO" EXACT PSI-MI-alternate []
synonym: "cysteine phosphate thioester" EXACT PSI-MI-alternate []
synonym: "phosphocysteine" EXACT PSI-MI-short []
synonym: "S-phospho-L-cysteine" EXACT PSI-MI-alternate []
synonym: "S-phosphonocysteine" EXACT PSI-MI-alternate []
synonym: "S3-phosphocysteine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0176
name: o-phospho-serine
def: "Residue modification.\nOBSOLETE remap to MOD:00046." [PMID:11125103, RESID:AA0037]
synonym: "(S)-2-amino-3-(phosphonooxy)propanoic acid" EXACT PSI-MI-alternate []
synonym: "2-amino-3-hydroxypropanoic acid 3-phosphate" EXACT PSI-MI-alternate []
synonym: "2-amino-3-hydroxypropanoic acid 3-phosphate;O-phosphonoserine;O3-phosphoserine" EXACT PSI-MI-alternate []
synonym: "[S:po]" EXACT PSI-MI-alternate []
synonym: "O-phospho-L-serine" EXACT PSI-MI-alternate []
synonym: "O-phosphonoserine" EXACT PSI-MI-alternate []
synonym: "O3-phosphoserine" EXACT PSI-MI-alternate []
synonym: "phosphoserine" EXACT PSI-MI-short []
synonym: "serine phosphate ester" EXACT PSI-MI-alternate []
synonym: "SPO" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0177
name: o-phospho-threonine
def: "Residue modification.\nOBSOLETE remap to MOD:00047." [PMID:11125103, RESID:AA0038]
synonym: "(2S,3R)-2-amino-3-phosphonooxybutanoic acid" EXACT PSI-MI-alternate []
synonym: "2-amino-3-hydroxybutanoic acid 3-phosphate" EXACT PSI-MI-alternate []
synonym: "[T:po]" EXACT PSI-MI-alternate []
synonym: "O-phospho-L-threonine" EXACT PSI-MI-alternate []
synonym: "O3-phosphothreonine" EXACT PSI-MI-alternate []
synonym: "phosphothreonine" EXACT PSI-MI-short []
synonym: "threonine phosphate ester" EXACT PSI-MI-alternate []
synonym: "TPO" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0178
name: o4'-phospho-tyrosine
def: "Residue modification.\nOBSOLETE remap to MOD:00048." [PMID:11125103, RESID:AA0039]
synonym: "(S)-2-amino-3-(4-phosphonooxyphenyl)propanoic acid" EXACT PSI-MI-alternate []
synonym: "2-amino-3-(4-hydroxyphenyl)propanoic acid 4'-phosphate" EXACT PSI-MI-alternate []
synonym: "[Y:po]" EXACT PSI-MI-alternate []
synonym: "O4'-phospho-L-tyrosine" EXACT PSI-MI-alternate []
synonym: "O4-phosphotyrosine" EXACT PSI-MI-alternate []
synonym: "phosphotyrosine" EXACT PSI-MI-short []
synonym: "tyrosine phosphate" EXACT PSI-MI-alternate []
synonym: "YPO" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0179
name: other modification
def: "Residue modification.\nOBSOLETE remap to MOD:00032." [PMID:11125103]
is_obsolete: true

[Term]
id: MI:0180
name: selenocysteine
def: "Residue modification.\nOBSOLETE remap to MOD:00031." [PMID:11125103, RESID:AA0022]
synonym: "3-selenylalanine" EXACT PSI-MI-alternate []
synonym: "[C:sel]" EXACT PSI-MI-alternate []
synonym: "CSE" EXACT PSI-MI-alternate []
synonym: "L-selenocysteine" EXACT PSI-MI-alternate []
synonym: "selenium cysteine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0181
name: selenomethionine
def: "Residue modification.\nOBSOLETE remap to MOD:00530." [PMID:11125103]
synonym: "[M:sel]" EXACT PSI-MI-alternate []
synonym: "L-selenomethionine" EXACT PSI-MI-alternate []
synonym: "MSE" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0182
name: 3-oxoalanine
def: "Residue modification.\nOBSOLETE remap to MOD:01169." [PMID:11125103, RESID:AA0185]
synonym: "(S)-2-amino-3-oxopropanoic acid" EXACT PSI-MI-alternate []
synonym: "2-amino-3-oxopropionic acid" EXACT PSI-MI-alternate []
synonym: "[S:oxal]" EXACT PSI-MI-alternate []
synonym: "L-3-oxoalanine" EXACT PSI-MI-alternate []
synonym: "L-alpha-formylglycine" EXACT PSI-MI-alternate []
synonym: "L-amino-malonic acid semialdehyde" EXACT PSI-MI-alternate []
synonym: "L-aminomalonaldehydic acid" EXACT PSI-MI-alternate []
synonym: "L-serinesemialdehyde [misnomer]" EXACT PSI-MI-alternate []
synonym: "oxoalanine" EXACT PSI-MI-short []
synonym: "SOX" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0184
name: glutamyl 5-glycerylphosphorylethanolamine
def: "Residue modification.\nOBSOLETE remap to MOD:00179." [PMID:11125103, RESID:AA0170]
synonym: "(S)-2-amino-5-[2-([([2,3-dihydroxypropyl]oxy)(hydroxy)phosphoryl]oxy)ethyl]amino-5-oxopentanoic acid" EXACT PSI-MI-alternate []
synonym: "[E:gpe]" EXACT PSI-MI-alternate []
synonym: "EGE" EXACT PSI-MI-alternate []
synonym: "glycerylpo4etohamine" EXACT PSI-MI-short []
synonym: "L-glutamyl 5-glycerophosphoethanolamine" EXACT PSI-MI-alternate []
synonym: "L-glutamyl 5-glycerophosphorylethanolamine" EXACT PSI-MI-alternate []
synonym: "L-glutamyl 5-glycerylphosphorylethanolamine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0186
name: n6-biotinyl-lysine
def: "Residue modification.\nOBSOLETE remap to MOD:00126." [PMID:11125103, RESID:AA0117]
synonym: "(3aS-(3aalpha,4beta,6aalpha))-N6-(5-(hexahydro-2-oxo-1H-thieno(3,4-d)imidazol-4-yl)-1-oxopentyl)-L-lysine" EXACT PSI-MI-alternate []
synonym: "(S)-2-amino-6-[5-((3aS,4S,6aR)-hexahydro-2-oxo-1H-thieno[3,4-d]imidazol-4-yl)-1-oxopentyl]aminohexanoic acid" EXACT PSI-MI-alternate []
synonym: "[K:biotin]" EXACT PSI-MI-alternate []
synonym: "biocytin" EXACT PSI-MI-alternate []
synonym: "biotinyllysine" EXACT PSI-MI-short []
synonym: "epsilon-N-biotinyllysine" EXACT PSI-MI-alternate []
synonym: "KBT" EXACT PSI-MI-alternate []
synonym: "N6-[5-((3aS,4S,6aR)-hexahydro-2-oxo-1H-thieno[3,4-d]imidazol-4-yl)-1-oxopentyl]-L-lysine" EXACT PSI-MI-alternate []
synonym: "N6-biotinyl-L-lysine" EXACT PSI-MI-alternate []
synonym: "N6-biotinyllysine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0187
name: n6-(4-amino-2-hydroxybutyl)-lysine
def: "Residue modification.\nOBSOLETE remap to MOD:00125." [PMID:11125103, RESID:AA0116]
synonym: "(S,R)-2-amino-6-(4-amino-2-hydroxybutylamino)hexanoic acid" EXACT PSI-MI-alternate []
synonym: "[K:hypu]" EXACT PSI-MI-alternate []
synonym: "hypusine" EXACT PSI-MI-alternate []
synonym: "hypusine" EXACT PSI-MI-short []
synonym: "KHY" EXACT PSI-MI-alternate []
synonym: "N6-(4-amino-2-hydroxybutyl)-L-lysine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0188
name: n6-retinal-lysine
def: "Residue modification.\nOBSOLETE remap to MOD:00129." [PMID:11125103, RESID:AA0120]
synonym: "(S)-2-amino-6-[(2E,4E,6E,8E)-3,7-dimethyl-9-(2,6,6-trimethylcyclohex-1-en-1-yl)-2,4,6,8-nonatetraenylidene]aminohexanoic acid" EXACT PSI-MI-alternate []
synonym: "[K:retin]" EXACT PSI-MI-alternate []
synonym: "KRT" EXACT PSI-MI-alternate []
synonym: "N6-retinal-L-lysine" EXACT PSI-MI-alternate []
synonym: "N6-retinyl-lysine" EXACT PSI-MI-alternate []
synonym: "N6-retinylidene-L-lysine" EXACT PSI-MI-alternate []
synonym: "retinallysine" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0189
name: ubiquitinated lysine
def: "Residue modification due to a cross-link between a lysine and a glycine from the ubiquitine protein.\nOBSOLETE remap to MOD:00134." [PMID:11125103, RESID:AA0125]
synonym: "[K:ub]" EXACT PSI-MI-alternate []
synonym: "KUB" EXACT PSI-MI-alternate []
synonym: "N6-glycyl-L-lysine" EXACT PSI-MI-alternate []
synonym: "N6-glycyllysine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0190
name: interaction type
def: "Connection between molecule." [PMID:14755292]
subset: PSI-MI_slim
relationship: part_of MI:0000 ! molecular interaction

[Term]
id: MI:0191
name: aggregation
def: "Physical association among molecules.\nOBSOLETE since too non-specific. Consider using physical interaction (MI:0218) instead." [PMID:14755292]
subset: PSI-MI_slim
is_obsolete: true

[Term]
id: MI:0192
name: acetylation reaction
def: "Reaction, that can affect K,C,A,D,E,Q,G,I,K,M,P,S,T,Y,V residues." [GO:0006473, PMID:14755292, RESID:AA0041, RESID:AA0042, RESID:AA0043, RESID:AA0044, RESID:AA0045, RESID:AA0046, RESID:AA0047, RESID:AA0048, RESID:AA0049, RESID:AA0050, RESID:AA0051, RESID:AA0052, RESID:AA0053, RESID:AA0054, RESID:AA0055, RESID:AA0056]
subset: PSI-MI_slim
synonym: "acetylation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction

[Term]
id: MI:0193
name: amidation reaction
def: "Irreversible reaction that can affect A,R,N,D,C,Q,E,G,H,I,L,K,M,F,P,S,T,W,Y or V residues. It involves the addition of an amide group from a glycine to the target residue." [GO:0001519, PMID:14755292, RESID:AA0081, RESID:AA0082, RESID:AA0083, RESID:AA0084, RESID:AA0085, RESID:AA0086, RESID:AA0087, RESID:AA0088, RESID:AA0089, RESID:AA0090, RESID:AA0091, RESID:AA0092, RESID:AA0093, RESID:AA0094, RESID:AA0095, RESID:AA0096, RESID:AA0097, RESID:AA0098, RESID:AA0099, RESID:AA0100]
subset: PSI-MI_slim
synonym: "amidation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction

[Term]
id: MI:0194
name: cleavage reaction
def: "Covalent bond breakage in a molecule leading to the formation of smaller molecules." [PMID:14755292]
subset: PSI-MI_slim
synonym: "cleavage" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction

[Term]
id: MI:0195
name: covalent binding
def: "Interaction leading to the formation of covalent bond within an autocatalytic molecule or between partners." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0407 ! direct interaction

[Term]
id: MI:0196
name: covalent interaction
def: "Physical interaction mediated by covalent bond rearrangement.\nOBSOLETE use covalent binding (MI:0195) instead." [PMID:14755292]
subset: PSI-MI_slim
is_obsolete: true

[Term]
id: MI:0197
name: deacetylation reaction
def: "N6-acetyl-L-lysine or S-acetyl-L-cysteine are cleaved and return K or C residues." [GO:0006476, PMID:14755292, RESID:AA0055, RESID:AA0056]
subset: PSI-MI_slim
synonym: "deacetylation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction

[Term]
id: MI:0198
name: defarnesylation reaction
def: "S-farnesyl-L-cysteined is cleaved and returns a C residue." [PMID:14755292, RESID:AA0102]
subset: PSI-MI_slim
synonym: "defarnesylation" EXACT PSI-MI-short []
is_a: MI:0212 ! lipoprotein cleavage reaction

[Term]
id: MI:0199
name: deformylation reaction
def: "N6-formyl-L-lysine is cleaved and returns a K residue." [PMID:14755292, RESID:AA0211]
subset: PSI-MI_slim
synonym: "deformylation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction

[Term]
id: MI:0200
name: degeranylation reaction
def: "S-geranylgeranyl-L-cysteine is cleaved and returns a C residue." [PMID:14755292, RESID:AA0104]
subset: PSI-MI_slim
synonym: "degeranylation" EXACT PSI-MI-short []
is_a: MI:0212 ! lipoprotein cleavage reaction

[Term]
id: MI:0201
name: demyristoylation reaction
def: "N6-myristoyl-L-lysine is cleaved and returns a K residue." [PMID:14755292, RESID:AA0078]
subset: PSI-MI_slim
synonym: "demyristoylation" EXACT PSI-MI-short []
is_a: MI:0212 ! lipoprotein cleavage reaction

[Term]
id: MI:0202
name: depalmitoylation reaction
def: "S-palmitoyl-L-cysteine, N6-palmitoyl-L-lysine, O-palmitoyl-L-threonine or O-palmitoyl-L-serine are cleaved and return C,K,T or S residues." [PMID:14755292, RESID:AA0060, RESID:AA0077, RESID:AA0106]
subset: PSI-MI_slim
synonym: "depalmitoylation" EXACT PSI-MI-short []
is_a: MI:0212 ! lipoprotein cleavage reaction

[Term]
id: MI:0203
name: dephosphorylation reaction
def: "Phosphoresidues are cleaved and return D,C,H,S,T,Y or R residues." [GO:0016311, PMID:14755292, RESID:AA0033, RESID:AA0034, RESID:AA0035, RESID:AA0036, RESID:AA0037, RESID:AA0038, RESID:AA0039, RESID:AA0222]
subset: PSI-MI_slim
synonym: "dephosphorylation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction

[Term]
id: MI:0204
name: deubiquitination reaction
def: "Cleavage of the G-K bond and release of ubiquitin or ubiquitin like proteins." [GO:0016579, PMID:11583613, RESID:AA0125]
subset: PSI-MI_slim
synonym: "deubiquitination" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction

[Term]
id: MI:0205
name: disaggregation
def: "Dissociation of partners interacting via non-covalent bond.\nOBSOLETE because considered misleading." [PMID:14755292]
subset: PSI-MI_slim
is_obsolete: true

[Term]
id: MI:0206
name: farnesylation reaction
def: "Reversible reaction that can affect C residue." [GO:0018347, PMID:14755292, RESID:AA0102]
subset: PSI-MI_slim
synonym: "farnesylation" EXACT PSI-MI-short []
is_a: MI:0211 ! lipid addition

[Term]
id: MI:0207
name: formylation reaction
def: "Reaction that can affect K or G residues. Reside is functionalised with a formyl group." [GO:0018256, PMID:14755292, RESID:AA0057, RESID:AA0211]
subset: PSI-MI_slim
synonym: "formylation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction

[Term]
id: MI:0208
name: genetic interaction
def: "An effect in which two genetic perturbations, when combined, result in a phenotype that does not appear to be merely explained by the superimposition or addition of effects of the original perturbations.\nab (not=) E" [PMID:16527956]
subset: PSI-MI_slim
is_a: MI:0190 ! interaction type

[Term]
id: MI:0209
name: geranylgeranylation reaction
def: "Attachment of one or two 20-carbon lipophilic geranylgeranyl isoprene units from geranylgeranyl diphosphate to one or more cysteine residue(s).Reversible reaction that can affect C residue." [GO:0018348, PMID:14755292, RESID:AA0104]
subset: PSI-MI_slim
synonym: "geranylgeranylation" EXACT PSI-MI-short []
is_a: MI:0211 ! lipid addition

[Term]
id: MI:0210
name: hydroxylation reaction
def: "Irreversible introduction of a hydroxyl group that can affect K,P,Y or R residues. Hydroxylation is the first step in the oxidative degeneration of organic compounds." [GO:0018126, PMID:14755292, RESID:AA0028, RESID:AA0029, RESID:AA0030, RESID:AA0146, RESID:AA0215]
subset: PSI-MI_slim
synonym: "hydroxylation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction

[Term]
id: MI:0211
name: lipid addition
def: "Covalent or non covalent binding of lipid group on a protein residue." [GO:0006497, PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0414 ! enzymatic reaction

[Term]
id: MI:0212
name: lipoprotein cleavage reaction
def: "Cleavage of a lipid group covalently bound to a protein residue." [PMID:14755292]
subset: PSI-MI_slim
synonym: "lipid cleavage" EXACT PSI-MI-short []
is_a: MI:0194 ! cleavage reaction

[Term]
id: MI:0213
name: methylation reaction
def: "The covalent attachment of a methyl residue to one or more monomeric units in a polypeptide, polynucleotide, polysaccharide, or other biological polymer. Irreversible reaction that can affect A,G,M,F,P,C,R,N,Q,E,H,or K residues." [GO:0043414, PMID:14755292, RESID:AA0061, RESID:AA0062, RESID:AA0063, RESID:AA0064, RESID:AA0065, RESID:AA0066, RESID:AA0067, RESID:AA0068, RESID:AA0069, RESID:AA0070, RESID:AA0071, RESID:AA0072, RESID:AA0073, RESID:AA0074, RESID:AA0075, RESID:AA0076, RESID:AA0234, RESID:AA0272]
subset: PSI-MI_slim
synonym: "methylation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction

[Term]
id: MI:0214
name: myristoylation reaction
def: "Irreversible covalent addition of a myristoyl group via an amide bond to the alpha-amino group of an amino acid. Reaction that can affect K or G residues." [GO:0018319, PMID:14755292, RESID:AA0059, RESID:AA0078]
subset: PSI-MI_slim
synonym: "myristoylation" EXACT PSI-MI-short []
is_a: MI:0211 ! lipid addition

[Term]
id: MI:0215
name: non covalent interaction
def: "Interaction mediated by non-covalent, weak forces rearrangement.\nOBSOLETE use physical interaction (MI:0218) instead." [PMID:14755292]
subset: PSI-MI_slim
synonym: "non covalent inter" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0216
name: palmitoylation reaction
def: "Covalent attachment of palmitic acid to the cysteine residues of membrane proteins. Reversible reaction that can affect C,K,T or S residues." [GO:0018318, PMID:14755292, RESID:AA0060, RESID:AA0077, RESID:AA0079, RESID:AA0080, RESID:AA0106]
subset: PSI-MI_slim
synonym: "palmitoylation" EXACT PSI-MI-short []
is_a: MI:0211 ! lipid addition

[Term]
id: MI:0217
name: phosphorylation reaction
def: "Reversible reaction that can affect D,C,H,S,T,Y,R residues." [GO:0016310, PMID:14755292, RESID:AA0033, RESID:AA0034, RESID:AA0035, RESID:AA0036, RESID:AA0037, RESID:AA0038, RESID:AA0039, RESID:AA0222]
subset: PSI-MI_slim
synonym: "phosphorylation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction

[Term]
id: MI:0218
name: physical interaction
def: "Interaction among molecules that can be direct or indirect.\nOBSOLETE: splitted to 'association' MI:0914 and 'physical association' MI:0915. For remapping consider the experimental setting of an interaction. For bulk remapping a possible criteria is to whatever physical interaction that has among its participant a bait should become 'association' MI:0914 the others can become 'physical association' MI:0915. Two hybrid interactions are an expection and can be 'physical association' MI:0915." [PMID:14755292]
is_obsolete: true

[Term]
id: MI:0219
name: synthetic lethal
def: "Death phenotype observed on cells carrying combination of two independently silent mutations.\nOBSOLETE: remap to CV intraction type 'synthetic interaction' MI:0794 and external CV for phenotype description (lethal FBcv:0000351)" [PMID:15608217]
subset: PSI-MI_slim
is_obsolete: true

[Term]
id: MI:0220
name: ubiquitination reaction
def: "Reversible reaction that create a covalent bond between a C-terminus G of ubiquitin and a K residue of the target." [GO:0016567, PMID:11583613, RESID:AA0125]
subset: PSI-MI_slim
synonym: "ubiquitination" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction

[Term]
id: MI:0221
name: expression level
def: "Synthesis rate of a molecule under investigation described in comparison with its naturally occurring expression level in a cell." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0346 ! experimental preparation

[Term]
id: MI:0222
name: physiological level
def: "A molecule whose synthesis is under control of its natural gene promoter or estimated to be expressed at a similar rate." [PMID:14755292]
subset: PSI-MI_slim
synonym: "endogenous" EXACT PSI-MI-alternate []
synonym: "endogenous level" EXACT PSI-MI-alternate []
is_a: MI:0221 ! expression level

[Term]
id: MI:0223
name: under expressed level
def: "A molecule is estimated to be expressed at lower levels than in physiological condition." [PMID:14755292]
subset: PSI-MI_slim
synonym: "under-expressed" EXACT PSI-MI-short []
is_a: MI:0221 ! expression level
is_a: MI:0803 ! expression level alteration

[Term]
id: MI:0225
name: chromatin immunoprecipitation array
def: "The method combines a modified chromatin immunoprecipitation (ChIP) procedure, with DNA microarray analysis. Cells are fixed with formaldehyde, harvested, and disrupted by sonication. The DNA fragments cross-linked to a protein of interest are enriched by immunoprecipitation with a specific antibody. After reversal of the cross-links, the enriched DNA is amplified and labeled with a fluorescent dye (Cy5) by using a ligation-mediatedpolymerase chain reaction (LM-PCR). In parallel a sample of DNA that is not enriched by immunoprecipitation is subjected to LM-PCR in the presence of a different fluorophore (Cy3), and both immunoprecipitation (IP)-enriched and unenriched pools of labeled DNA were hybridized to a single DNA microarray containing a set of intergenic sequences. The ratio of the Cy5 to Cy3 fluorescence intensities measured at each DNA element in the microarray provided a measure of the extent of binding of the transcription factor to the corresponding genomic locus." [PMID:11125145, PMID:11206552]
subset: PSI-MI_slim
synonym: "chip-chip" EXACT PSI-MI-short []
is_a: MI:0008 ! array technology
is_a: MI:0402 ! chromatin immunoprecipitation assay

[Term]
id: MI:0226
name: ion exchange chromatography
def: "Stable complexes and their component proteins can be separated on the basis of their net charge by ion-exchange chromatography. If a protein has a net positive charge at pH 7, it will usually bind to a column of beads containing carboxylate groups, and can then be eluted by increasing the concentration of sodium chloride or another salt in the eluting buffer by competition of sodium ions with positively charged groups on the protein for binding to the column. Protein that have a low density of net positive charge will tend to emerge first, followed by those having a higher charge density. Positively charged complexes or proteins (cationic proteins) can be separated on negatively charged carboxymethyl-cellulose (CM-cellulose) columns. Conversely, negatively charged complexes or proteins (anionic proteins) can be separated by chromatography on positively charged diethylaminoethyl-cellulose (DEAE-cellulose) columns." [PMID:14755292]
subset: PSI-MI_slim
synonym: "IEC" EXACT PSI-MI-alternate []
synonym: "ion exchange chrom" EXACT PSI-MI-short []
is_a: MI:0091 ! chromatography technology

[Term]
id: MI:0227
name: reverse phase chromatography
def: "Reverse phase chromatography operates on the basis of hydrophilicity and lipophilicity. The stationary phase consists of silica based packings with n-alkyl chains covalently bound. For example, C-8 signifies an octyl chain and C-18 an octadecyl ligand in the matrix. The more hydrophobic the matrix on each ligand, the greater is the tendency of the column to retain hydrophobic moieties. Thus hydrophilic compounds elute more quickly than do hydrophobic compounds." [PMID:14755292]
subset: PSI-MI_slim
synonym: "reverse phase chrom" EXACT PSI-MI-short []
is_a: MI:0091 ! chromatography technology

[Term]
id: MI:0228
name: cytoplasmic complementation assay
def: "Protein complementation assay performed by dissecting a cytoplasmic protein activity and restoring it through the two hybrid proteins interaction. OBSOLETE remap to MI:0090 protein complementation assay" [PMID:14755292]
subset: PSI-MI_slim
synonym: "cytoplasmic compl" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0230
name: membrane bound complementation assay
def: "OBSOLETE remap to MI:0090 protein complementation assay." [PMID:14755292]
subset: PSI-MI_slim
synonym: "membrane compl" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0231
name: mammalian protein protein interaction trap
def: "The MAPPIT(mammalian protein-protein interaction Trap) is a screening method for protein-protein interaction in mammalian cells, based on the reconstitution of a membrane STAT (signal transducers and activators of transcription) receptor. The bait protein is fused to a STAT recruitment-deficient receptor and the prey protein to a functional STAT recruitment sites. In such a configuration, a given baitprey interaction restores a STAT-dependent responses leading to the expression of a reporter gene. This system, enable to demonstrate not only protein interaction but also modification-independent and tyrosine phosphorylation- dependent interactions." [PMID:12853652]
subset: PSI-MI_slim
synonym: "mappit" EXACT PSI-MI-short []
is_a: MI:0090 ! protein complementation assay

[Term]
id: MI:0232
name: transcriptional complementation assay
def: "Protein complementation assay performed by dissecting a transcription factor activity (DNA binding domain and transcription activation domain) its restoration through the two hybrid proteins interaction that lead to a reporter gene expression." [PMID:14755292]
subset: PSI-MI_slim
synonym: "transcription compl" EXACT PSI-MI-short []
is_a: MI:0090 ! protein complementation assay

[Term]
id: MI:0233
name: protein dna complex
def: "A stable set of interacting protein and DNA that can be copurified and operate as a functional unit." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1299 ! complex composition

[Term]
id: MI:0234
name: 131i radiolabel
def: "Molecule labelled with 131 radio isotope of iodine atoms." [PMID:14755292]
subset: PSI-MI_slim
synonym: "131I" EXACT PSI-MI-alternate []
synonym: "I131" EXACT PSI-MI-alternate []
is_a: MI:0517 ! radiolabel

[Term]
id: MI:0235
name: 14c radiolabel
def: "Molecule labelled with the radio isotope 14 of carbon atoms." [PMID:14755292]
subset: PSI-MI_slim
synonym: "14C" EXACT PSI-MI-alternate []
synonym: "C14" EXACT PSI-MI-alternate []
is_a: MI:0517 ! radiolabel

[Term]
id: MI:0236
name: 32p radiolabel
def: "Molecule labelled with the radio isotope 32 of phosphorus atoms." [PMID:14755292]
subset: PSI-MI_slim
synonym: "32P" EXACT PSI-MI-alternate []
synonym: "P32" EXACT PSI-MI-alternate []
is_a: MI:0517 ! radiolabel

[Term]
id: MI:0237
name: 33p radiolabel
def: "Molecule labelled with the radio isotope 33 of phosphorus atoms." [PMID:14755292]
subset: PSI-MI_slim
synonym: "33P" EXACT PSI-MI-alternate []
synonym: "P33" EXACT PSI-MI-alternate []
is_a: MI:0517 ! radiolabel

[Term]
id: MI:0238
name: 3h radiolabel
def: "Molecules labelled with isotope 3 of hydrogen atoms." [PMID:14755292]
subset: PSI-MI_slim
synonym: "3H" EXACT PSI-MI-alternate []
synonym: "H3" EXACT PSI-MI-alternate []
synonym: "tritium" EXACT PSI-MI-alternate []
is_a: MI:0517 ! radiolabel

[Term]
id: MI:0239
name: biotin tag
def: "Biotin, a 244 Dalton vitamin found in tissue and blood, binds with high affinity to avidin and streptavidin protein. Since biotin is a relatively small molecule, it can be conjugated to many proteins or nucleic acids without significantly altering their biological activity. Biotinylation reagents are available for targeting a variety of specific functional groups, including primary amines, sulfhydryls, carboxyls and carbohydrates that lead to nucleotides or amino acid biotinilation." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0507 ! tag

[Term]
id: MI:0240
name: fusion protein
def: "The protein under study is expressed as a fusion with a labelling protein, having either fluorescence properties or an enzymatic activity that facilitates its purification, identification, localisation or quantification." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0507 ! tag

[Term]
id: MI:0241
name: horseradish peroxidase tag
def: "Protein is fused to horseradish peroxidase, and the measure of this enzyme activity can be taken as indicative of presence of protein." [PMID:14755292]
subset: PSI-MI_slim
synonym: "hrp tag" EXACT PSI-MI-short []
is_a: MI:0365 ! enzyme tag

[Term]
id: MI:0242
name: gene ontology definition reference
def: "This qualifier is used when the crossreference is imported from the Gene Ontology tag definition_reference." [PMID:14755292]
subset: PSI-MI_slim
synonym: "go-definition-ref" EXACT PSI-MI-short []
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:0243
name: isoform parent sequence reference
def: "Reference to the master sequence from which this isoform has been derived." [PMID:14755292]
subset: PSI-MI_slim
synonym: "isoform-parent" EXACT PSI-MI-short []
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:0244
name: reactome complex
def: "Collection of functional complexes within Reactome - a knowledgebase of biological processes.\nhttp://www.reactome.org/. OSOLETE - this concept no longer exists within Reactome." [PMID:21067998]
subset: PSI-MI_slim
xref: id-validation-regexp: "REACT_[0-9]{1,5}\\.[0-9]{1,3}|[0-9]+"
xref: search-url: "http://www.reactome.org/cgi-bin/eventbrowser?ID=${ac}"
is_obsolete: true

[Term]
id: MI:0245
name: reactome protein
def: "Collection of protein within the Reactome database - a knowledgebase of biological processes.\nhttp://www.reactome.org/. OBSOLETE - this concept no longer exists within Reactome." [PMID:21067998]
subset: PSI-MI_slim
xref: id-validation-regexp: "REACT_[0-9]{1,4}\\.[0-9]{1,3}|[OPQ][0-9][A-Z0-9]{3}[0-9]|[OPQ][0-9][A-Z0-9]{3}[0-9]-[0-9]+|[A-Z]{3}[0-9]{5}|[OPQ][0-9][A-Z0-9]{3}[0-9]-PRO_[0-9]{10}"
xref: search-url: "http://www.reactome.org/cgi-bin/link?SOURCE=UNIPROT&ID=${ac}"
is_obsolete: true

[Term]
id: MI:0246
name: cabri
def: "CABRI cell lines catalogue available at.\nhttp://www.cabri.org/" [PMID:14755292]
subset: PSI-MI_slim
xref: id-validation-regexp: "[0-9]+|ACC\\s[A-Z0-9]+|ECACC\\s[A-Z0-9]+|LMBP\\s[A-Z0-9]+|ICLC\\s[A-Z0-9]+|CIP-[0-9]+|DSMZ_MUTZ\\:ACC\\s[0-9]+"
xref: search-url: "http://www.cabri.org/CABRI/srs-bin/wgetz?-e+-page+EntryPage+[$id]"
is_a: MI:0473 ! participant database

[Term]
id: MI:0247
name: newt
def: "New EBI Web Taxonomy.\nhttp://www.ebi.ac.uk/newt OBSOLETE: Consider remapping to uniprot taxonomy MI:0942" [PMID:14755292]
subset: PSI-MI_slim
xref: id-validation-regexp: "[0-9]+"
xref: search-url: "http://www.ebi.ac.uk/newt/display?search=${ac}"
is_obsolete: true

[Term]
id: MI:0248
name: resid
def: "The RESID Database of Protein Modifications is a comprehensive collection of annotations and structures for protein modifications including amino-terminal, carboxyl-terminal and peptide chain cross-link post-translational modifications.\nhttp://www.ebi.ac.uk/RESID/index.html" [PMID:14755292]
subset: PSI-MI_slim
xref: id-validation-regexp: "AA[0-9]{4}"
xref: search-url: "http://srs.ebi.ac.uk/cgi-bin/wgetz?[resid-id:${ac}]+-e"
is_a: MI:0447 ! feature database

[Term]
id: MI:0249
name: huge
def: "A Database of Human Unidentified Gene-Encoded Large Proteins Analyzed by Kazusa Human cDNA Project.\nhttp://www.kazusa.or.jp/huge/" [PMID:14755292]
subset: PSI-MI_slim
xref: id-validation-regexp: "KIAA[0-9]{4}[A-Z]{0,1}"
xref: search-url: "http://www.kazusa.or.jp/huge/gfpage/${ac}"
is_a: MI:0683 ! sequence database

[Term]
id: MI:0250
name: gene
def: "A genomic region (or regions) that includes all of the sequence elements necessary to encode a functional transcript. A gene may include regulatory regions, transcribed regions and/or other functional sequence regions." [PMID:14755292, SO:0000704]
subset: PSI-MI_slim
is_a: MI:0313 ! interactor type

[Term]
id: MI:0251
name: gene product
def: "Reference of a protein object pointing to its genomic or nucleic acid sequence." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:0252
name: biological feature
def: "Property of a subsequence that may be involved with or interfere with the binding of a molecule and are supported by experimental evidences." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0116 ! feature type

[Term]
id: MI:0253
name: isotope label
def: "One of several nuclides having the same number of protons in their nuclei and hence having the same atomic number, but differing in the number of neutrons and therefore, in the mass number." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0505 ! experimental feature

[Term]
id: MI:0254
name: genetic interference
def: "This term refers to methods that aim at interfering with the activity of a specific gene by altering the gene regulatory or coding sequences. This goal can be achieved either by a classical genetic approach (random mutagenesis followed by phenotype characterization and genetic mapping) or by a reverse genetics approach where a gene of interest is modified by directed mutagenesis." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0045 ! experimental interaction detection

[Term]
id: MI:0255
name: post transcriptional interference
def: "This term refers to methods designed to interfere with gene expression at post-transcriptional level rather than with the gene itself." [PMID:14755292]
subset: PSI-MI_slim
synonym: "expression interfer" EXACT PSI-MI-short []
is_a: MI:0045 ! experimental interaction detection

[Term]
id: MI:0256
name: rna interference
def: "RNA interference (RNAi) is a post-transcriptional gene silencing method reproducing a naturally occurring phenomena. RNAi is the process whereby double-stranded RNA (dsRNA) induces the sequence-specific degradation of homologous mRNA. RNAi or dsRNA-induced silencing phenomena are present in evolutionarily diverse organisms, e.g., nematodes, plants, fungi, and trypanosomes. The mechanisms by which RNAi works is initiated by a progressive cleavage of dsRNA into 21 to 23 nucleotide (nt) short interfering RNAs (siRNAs). These native siRNA duplexes are then incorporated into a protein complex called RNA-induced silencing complex (RISC). ATP-dependent unwinding of the siRNA duplex generates an active RISC complex. Guided by the antisense strand of siRNA, the active RISC complex recognizes and cleaves the corresponding mRNA." [PMID:12110901, PMID:12408823]
subset: PSI-MI_slim
synonym: "rnai" EXACT PSI-MI-short []
is_a: MI:0255 ! post transcriptional interference

[Term]
id: MI:0257
name: antisense rna
def: "This approach is based on the observation that expression of RNA that is complementary to a specific mRNA can decrease the synthesis of its gene product either by increasing the degradation of the targeted mRNA or by interfering with its translation." [PMID:1340158]
subset: PSI-MI_slim
is_a: MI:0255 ! post transcriptional interference

[Term]
id: MI:0258
name: inhibitor antibodies
def: "Intracellular or extracellular expression of antibodies is used to target specific gene products in order to inactivate them. Most of the times the antibody scaffold need s to reengineered for efficient expression and solubility in the cytoplasm.\nOBSOLETE as such method can be described using the biological role inhibitor (MI:0586)." [PMID:10189716]
subset: PSI-MI_slim
is_obsolete: true

[Term]
id: MI:0259
name: perturbagens peptides
def: "This approach is based on the expression of peptides that bind to specific target proteins thereby interfering with their activity. In a standard approach the interfering peptide is expressed by genetic fusion to a stable protein scaffold. Interfering peptides can also be introduced into cells by fusing them to proteins or peptides (homeodomains, Tat protein.) having the property of penetrating the cell membrane. The peptide-carrier fusion protein is either synthesized chemically or produced in vivo, normally in bacteria. When the purified fusion protein is added to a cell culture, it penetrates the cell membrane thereby permitting the fused peptide to interfere with its target protein.\nOBSOLETE as such method can be described using the biological role inhibitor (MI:0586)." [PMID:11731788, PMID:8606778]
subset: PSI-MI_slim
synonym: "perturbagens pep" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0260
name: inhibitor small molecules
def: "Protein activity is inhibited by small inorganic molecules (drugs) that specifically bind to their targets. Recently this classical pharmacological approach is sometime referred to as 'chemical genetics'.\nOBSOLETE as such method can be described using the biological role inhibitor (MI:0586)." [PMID:10542155, PMID:10780927]
subset: PSI-MI_slim
synonym: "inhibitor small mol" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0261
name: suppression
def: "A supressed gene mutation cause of an altered phenotype that is reverted to wild type phenotype when cell also carry a suppressor gene with a specific mutation or altered expression level.\nOBSOLETE: remap to CV intraction type 'suppressive interaction' MI:0793." [PMID:15608217]
subset: PSI-MI_slim
is_obsolete: true

[Term]
id: MI:0262
name: suppression mutation
def: "A given (suppressed) mutation phenotype is reverted by a supressor gene mutation.\nOBSOLETE: remap to CV intraction type 'suppressive interaction' MI:0793 and genetic experimental form 'mutated gene' MI:0804. " [PMID:15608217]
subset: PSI-MI_slim
is_obsolete: true

[Term]
id: MI:0263
name: suppression knockout
def: "Knocked out gene is the suppressor of a phenotype.\nOBSOLETE: remap to CV intraction type 'suppressive interaction' MI:0793 and genetic experimental form 'knock out' MI:0788. " [PMID:15608217]
subset: PSI-MI_slim
synonym: "suppress knockout" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0264
name: suppression partial alteration
def: "A mutation is the partial suppressor of a mutant phenotype.\nOBSOLETE: remap to CV intraction type 'suppressive interaction' MI:0793 and genetic experimental form 'knock down' MI:0789. " [PMID:15608217]
subset: PSI-MI_slim
synonym: "suppression partial" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0265
name: suppression expression alteration
def: "An altered expression is the suppressor of a phenotype.\nOBSOLETE: remap to CV intraction type 'suppressive interaction' MI:0793 and genetic experimental form 'expression level alteration' MI:0803. " [PMID:15608217]
subset: PSI-MI_slim
synonym: "suppress expression" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0266
name: suppression overexpression
def: "Overexpression is the suppressor of a phenotype.\nOBSOLETE: remap to CV intraction type 'suppressive interaction' MI:0793 and genetic experimental form 'over expressed' MI:0506. " [PMID:15608217]
subset: PSI-MI_slim
synonym: "suppress overexpress" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0267
name: suppression scalable
def: "Level of over/underexpression scales the 'extend' of a phenotype.\nOBSOLETE: remap to CV intraction type 'suppressive interaction' MI:0793 and genetic experimental form 'expression level alteration' MI:0803. " [PMID:15608217]
subset: PSI-MI_slim
is_obsolete: true

[Term]
id: MI:0268
name: suppression underexpression
def: "Underexpression is the suppressor of a phenotype.\nOBSOLETE: remap to CV intraction type 'suppressive interaction' MI:0793 and genetic experimental form 'under expressed' MI:0223. " [PMID:15608217]
subset: PSI-MI_slim
synonym: "suppress underexpres" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0269
name: synthetic phenotype
def: "Two silent mutations show an altered phenotype when they co-occur on the same cell.\nOBSOLETE: remap to CV intraction type 'synthetic interaction' MI:0794." [PMID:15608217]
subset: PSI-MI_slim
is_obsolete: true

[Term]
id: MI:0270
name: conditional synthetic lethal
def: "Two silent mutations show a conditional synthetic lethal phenotype when they co-occur on the same cell.\nOBSOLETE: remap to CV intraction type 'synthetic interaction' MI:0794 and external CV for phenotype description (lethal FBcv:0000351)" [PMID:15608217]
subset: PSI-MI_slim
synonym: "cond syntetic lethal" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0271
name: conditional synthetic lethal temperature-sensitivity
def: "Two silent mutations show a temperature sensitive lethal phenotype when they co-occur on the same cell.\nOBSOLETE: remap to CV intraction type 'synthetic interaction' MI:0794 and external CV for phenotype description (FBcv:0000310 'temperature conditional')" [PMID:15608217]
subset: PSI-MI_slim
synonym: "temprtr synt lethal" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0273
name: synthetic growth effect
def: "Two silent mutations show altered growth effect when they co-occur on the same cell.\nOBSOLETE: remap to CV intraction type 'synthetic interaction' MI:0794 and external CV for phenotype description ( FBcv:0000427 'cell growth defective')" [PMID:15608217]
subset: PSI-MI_slim
synonym: "synt growth effect" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0274
name: synthetic growth defect
def: "Two silent mutations show growth defect when they co-occur on the same cell.\nOBSOLETE: remap to CV intraction type 'synthetic interaction' MI:0794 and external CV for phenotype description ( FBcv:0000427 'cell growth defective')" [PMID:15608217]
subset: PSI-MI_slim
synonym: "synt growth defect" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0275
name: synthetic growth increase
def: "Two silent mutations show growth increase when they co-occur on the same cell.\nOBSOLETE: remap to CV intraction type 'synthetic interaction' MI:0794 and external CV for phenotype description ( FBcv:0000427 'cell growth defective')" [PMID:15608217]
subset: PSI-MI_slim
synonym: "synt growth increase" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0276
name: blue native page
def: "Blue native PAGE (BN-PAGE) permits a high-resolution separation of multi-protein complexes under native conditions. Blue native (BN)-PAGE is a charge shift method, in which the electrophoretic mobility of a complex is determined by the negative charge of the bound Coomassie dye and the size and shape of the complex. Coomassie does not act as a detergent and preserves the structure of complexes. Importantly, the resolution of BN-PAGE is much higher than that of other methods such as gel filtration or sucrose-gradient ultracentrifugation. Combined with other pre-purifications or dialysis steps this method permits the analysis of multi-protein complexes of whole cellular lysates by BN-PAGE." [PMID:14665681]
subset: PSI-MI_slim
synonym: "bn-page" EXACT PSI-MI-short []
is_a: MI:0404 ! comigration in non denaturing gel electrophoresis

[Term]
id: MI:0300
name: alias type
def: "Descriptor of type of nomenclature used to describe interactor." [PMID:14755292]
subset: Drugable
subset: PSI-MI_slim
synonym: "CvAliasType" EXACT PSI-MI-alternate []
relationship: part_of MI:0000 ! molecular interaction

[Term]
id: MI:0301
name: gene name
def: "Gene name." [PMID:14755292]
subset: PSI-MI_slim
synonym: "gene" EXACT PSI-MI-alternate []
is_a: MI:1041 ! synonym

[Term]
id: MI:0302
name: gene name synonym
def: "Gene name synonym." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1041 ! synonym

[Term]
id: MI:0303
name: gene ontology synonym
def: "Synonym as used in Gene Ontology." [PMID:14755292]
subset: PSI-MI_slim
synonym: "go synonym" EXACT PSI-MI-short []
is_a: MI:1041 ! synonym

[Term]
id: MI:0304
name: isoform synonym
def: "Isoform synonym." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1041 ! synonym

[Term]
id: MI:0305
name: ordered locus name
def: "A name used to represent an ORF in a completely sequenced genome or chromosome. It is generally based on a prefix representing the organism and a number which usually represents the sequential ordering of genes on the chromosome. Depending on the genome sequencing center, numbers are attributed only to protein-coding genes, or also to pseudogenes, or also to tRNAs and other features." [PMID:14755292]
comment: For instance HI0934, Rv3245c, At5g34500, YER456W.
subset: PSI-MI_slim
synonym: "CDS number" EXACT PSI-MI-alternate []
synonym: "locus name" EXACT PSI-MI-short []
synonym: "ONL" EXACT PSI-MI-alternate []
synonym: "Ordered locus name" EXACT PSI-MI-alternate []
synonym: "ORF number" EXACT PSI-MI-alternate []
synonym: "systematic gene number" EXACT PSI-MI-alternate []
is_a: MI:1041 ! synonym

[Term]
id: MI:0306
name: open reading frame name
def: "A name temporarily attributed by a sequencing project to an open reading frame. This name is generally based on a cosmid numbering system." [PMID:14755292]
comment: For instance MtCY277-28c, SYGP-ORF50, SpBC2F12-04, C06E1, CG10954. Also called Sequencing names or Contig names or Temporary ORFNames.
subset: PSI-MI_slim
synonym: "orf name" EXACT PSI-MI-short []
is_a: MI:1041 ! synonym

[Term]
id: MI:0307
name: delivery method
def: "Method by which molecule is delivered or engineered into a cell." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0346 ! experimental preparation

[Term]
id: MI:0308
name: electroporation
def: "Method for temporarily permeabilising cell membranes so as to facilitate the entry of large or hydrophilic molecules (as in transfection). A brief (ca 1 msec) electric pulse is given with potential gradients of about 700V/cm." [PMID:6329708]
subset: PSI-MI_slim
is_a: MI:0307 ! delivery method

[Term]
id: MI:0309
name: genomic tagging
def: "A cassette coding for a protein tag is inserted by homologous recombination onto the genomic copy of an open reading frame. The advantage of this delivery method is that the resulting engineered protein is expressed under its natural promoter control.\nOBSOLETE redundant term. Map to feature type : tag (MI:0507)." [PMID:14755292]
subset: PSI-MI_slim
synonym: "genetic tag insertion" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0310
name: infection
def: "Molecule introduced into a cell via an external organism, usually a virus or bacteria." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0307 ! delivery method

[Term]
id: MI:0311
name: microinjection
def: "The insertion of a substance into a cell through a microneedle. To extrude the substances through the very fine needle tip, either hydrostatic pressure (pressure injection) or electric currents (ionophoresis) is employed." [PMID:3016916]
subset: PSI-MI_slim
synonym: "micro-injection" EXACT PSI-MI-alternate []
is_a: MI:0307 ! delivery method

[Term]
id: MI:0312
name: nucleic acid transfection
def: "Introducing DNA into eukaryotic cells, such as animal cells, is called transfection. Transfection typically involves opening transient \"holes\" or gates in cells to allow the entry of extracellular molecules, typically supercoiled plasmid DNA, but also siRNA, among others. Transfection differs from transformation since the DNA is not generally incorporated into the cell's genome, it is only transiently expressed." [PMID:14755292]
subset: PSI-MI_slim
synonym: "nucl transfection" EXACT PSI-MI-short []
is_a: MI:0704 ! nucleic acid delivery

[Term]
id: MI:0313
name: interactor type
def: "Molecular species involved in the interaction." [PMID:14755292]
subset: Drugable
subset: PSI-MI_slim
synonym: "participant type" EXACT PSI-MI-alternate []
relationship: part_of MI:0000 ! molecular interaction

[Term]
id: MI:0314
name: complex
def: "Set of interacting molecules that can be copurified. This term and its children should be use only at PARTICIPANT level." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0313 ! interactor type

[Term]
id: MI:0315
name: protein complex
def: "A stable set of interacting proteins that can be copurified and operate as a functional unit." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1299 ! complex composition

[Term]
id: MI:0316
name: ribonucleoprotein complex
def: "A macromolecular complex containing both protein and RNA molecules." [GO:0030529, PMID:14755292]
subset: PSI-MI_slim
synonym: "protein rna complex" EXACT PSI-MI-alternate []
synonym: "ribonucleoprot compl" EXACT PSI-MI-short []
is_a: MI:1299 ! complex composition

[Term]
id: MI:0317
name: interaction
def: "Previously described interaction now being used as an interactor to describe hierarchical build-up of complexes." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0313 ! interactor type

[Term]
id: MI:0318
name: nucleic acid
def: "Linear polymers of nucleotides, linked by 3',5' phosphodiester linkages." [PMID:14755292, SO:0000348]
subset: PSI-MI_slim
is_a: MI:0383 ! biopolymer

[Term]
id: MI:0319
name: deoxyribonucleic acid
def: "Polymer formed by the deoxyribose sugar group, and the nucleotides bases adenine, guanine, thymine and cytosine." [PMID:14755292, SO:0000352]
subset: PSI-MI_slim
synonym: "deoxyribonucleic acid" EXACT PSI-MI-alternate []
synonym: "DNA" EXACT PSI-MI-alternate []
synonym: "dna" EXACT PSI-MI-short []
is_a: MI:0318 ! nucleic acid

[Term]
id: MI:0320
name: ribonucleic acid
def: "Polymer formed by ribose sugar group, and the bases of the nucleotides adenine, guanine, uracil and cytosine." [PMID:14755292, SO:0000356]
subset: PSI-MI_slim
synonym: "RNA" EXACT PSI-MI-alternate []
synonym: "rna" EXACT PSI-MI-short []
is_a: MI:0318 ! nucleic acid

[Term]
id: MI:0321
name: catalytic rna
def: "Species of RNA that catalyses cleavage or trans-esterification of the phosphodiester link." [PMID:14755292]
subset: PSI-MI_slim
synonym: "catalytic ribonucleic acid" EXACT PSI-MI-alternate []
synonym: "catalytic RNA" EXACT PSI-MI-alternate []
synonym: "crna" EXACT PSI-MI-short []
is_a: MI:0320 ! ribonucleic acid

[Term]
id: MI:0322
name: guide rna
def: "Small RNA molecules that hybridize to specific mRNAs and direct their RNA editing." [PMID:14755292]
subset: PSI-MI_slim
synonym: "grna" EXACT PSI-MI-short []
synonym: "guide RNA" EXACT PSI-MI-alternate []
is_a: MI:0320 ! ribonucleic acid

[Term]
id: MI:0323
name: heterogeneous nuclear rna
def: "A heterogeneous mixture of RNA molecules with a rapid turnover rate that occurs in cell nuclei during protein synthesis; it is the form of RNA synthesized in eukaryotes by RNA polymerase II, which is translated into protein." [PMID:14755292]
subset: PSI-MI_slim
synonym: "heterogeneous nuclear ribonucleic acid" EXACT PSI-MI-alternate []
synonym: "heterogeneous nuclear RNA" EXACT PSI-MI-alternate []
synonym: "hnrna" EXACT PSI-MI-short []
is_a: MI:0320 ! ribonucleic acid

[Term]
id: MI:0324
name: messenger rna
def: "Single-stranded RNA molecule that specifies the amino acid sequence of one or more polypeptide chains." [PMID:14755292]
subset: PSI-MI_slim
synonym: "mRNA" EXACT PSI-MI-alternate []
synonym: "mrna" EXACT PSI-MI-short []
is_a: MI:0320 ! ribonucleic acid

[Term]
id: MI:0325
name: transfer rna
def: "The low molecular weight RNAs that specifically bind amino acids by aminoacetylation to form aminoacyl tRNA and which possess a special nucleotide triplet, the anticodon." [PMID:14755292]
subset: PSI-MI_slim
synonym: "transfer ribonucleic acid" EXACT PSI-MI-alternate []
synonym: "transfer RNA" EXACT PSI-MI-alternate []
synonym: "tRNA" EXACT PSI-MI-alternate []
synonym: "trna" EXACT PSI-MI-short []
is_a: MI:0320 ! ribonucleic acid

[Term]
id: MI:0326
name: protein
def: "A linear polymer of amino acids joined by peptide bonds in a specific sequence." [PMID:14755292, SO:0000358]
subset: PSI-MI_slim
is_a: MI:0383 ! biopolymer

[Term]
id: MI:0327
name: peptide
def: "Chains of amino acids joined by peptide bonds. Distinction between peptides, oligopeptides and polypeptides is arbitrarily by length; a polypeptide is perhaps more than 15 residues." [PMID:14755292]
subset: PSI-MI_slim
synonym: "oligopeptide" EXACT PSI-MI-alternate []
synonym: "polypeptide" EXACT PSI-MI-alternate []
is_a: MI:0383 ! biopolymer

[Term]
id: MI:0328
name: small molecule
def: "Molecule not part of or directly encoded by the genome, encompasses any constitutionally or isotopically distinct atom, molecule, ion, ion pair, radical, radical ion, complex, conformer, etc., identifiable as a separately distinguishable entity." [PMID:14755292]
subset: Drugable
subset: PSI-MI_slim
is_a: MI:1100 ! bioactive entity

[Term]
id: MI:0329
name: unknown participant
def: "Any type of molecule, including complexes, that may be observed but not identified. This term should be use only at PARTICIPANT level." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0313 ! interactor type

[Term]
id: MI:0330
name: molecular source
def: "Defines whether molecule is endogenously expressed or has in any way been altered, in sequence or expression level, from its native state. For a complete description of the experimental molecule form use the orthogonal CVs expression level, delivery method, and sample process." [PMID:14755272]
subset: PSI-MI_slim
is_a: MI:0346 ! experimental preparation

[Term]
id: MI:0331
name: engineered
def: "Molecule has been added into system from an external source or altered within the cell." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0330 ! molecular source

[Term]
id: MI:0332
name: naturally occurring
def: "Unaltered endogenous molecule in its naturally occurring state." [PMID:14755292]
subset: PSI-MI_slim
synonym: "endogenous" EXACT PSI-MI-alternate []
is_a: MI:0330 ! molecular source

[Term]
id: MI:0333
name: feature range status
def: "Describes sequence positions resolution of a given participant feature. In PSI schema this CV is associated with the start and end position of a feature range." [PMID:14755292]
subset: PSI-MI_slim
synonym: "CvFuzzyType" EXACT PSI-MI-alternate []
synonym: "endStatus" EXACT PSI-MI-alternate []
synonym: "startStatus" EXACT PSI-MI-alternate []
relationship: part_of MI:0000 ! molecular interaction

[Term]
id: MI:0334
name: c-terminal position
def: "Term describing the last amino acid of a peptide chain." [PMID:14755292]
comment: Displayed as 'c'.
subset: PSI-MI_slim
synonym: "c-term" EXACT PSI-MI-alternate []
synonym: "c-terminal" EXACT PSI-MI-short []
synonym: "c-terminus" EXACT PSI-MI-alternate []
synonym: "carboxy-terminus" EXACT PSI-MI-alternate []
is_a: MI:0333 ! feature range status

[Term]
id: MI:0335
name: certain sequence position
def: "Position within the sequence clearly defined." [PMID:14755292]
subset: PSI-MI_slim
synonym: "certain" EXACT PSI-MI-short []
is_a: MI:0333 ! feature range status

[Term]
id: MI:0336
name: greater-than
def: "Partially determined sequence position known to be in a location higher than a given position." [PMID:14755292]
comment: Displayed as '>'.
subset: PSI-MI_slim
is_a: MI:0333 ! feature range status

[Term]
id: MI:0337
name: less-than
def: "Partially determined sequence position known to be in a position lower than a given position." [PMID:14755292]
comment: Displayed as '<'.
subset: PSI-MI_slim
is_a: MI:0333 ! feature range status

[Term]
id: MI:0338
name: range
def: "Describes a sequence position known to be in a certain range, where the exact position is unclear." [PMID:14755292]
comment: For instance when an amino acid modification is known to be in the region from 5 to 7. Displayed as '..'.
subset: PSI-MI_slim
is_a: MI:0333 ! feature range status

[Term]
id: MI:0339
name: undetermined sequence position
def: "Term describing a completely unknown or unspecified sequence position." [PMID:14755292]
comment: Displayed as '?'.
subset: PSI-MI_slim
synonym: "undetermined" EXACT PSI-MI-short []
is_a: MI:0333 ! feature range status

[Term]
id: MI:0340
name: n-terminal position
def: "Term describing the first amino acid of a peptide chain." [PMID:14755292]
comment: Displayed as 'n'.
subset: PSI-MI_slim
synonym: "amino-terminus" EXACT PSI-MI-alternate []
synonym: "n-term" EXACT PSI-MI-alternate []
synonym: "n-terminal " EXACT PSI-MI-short []
synonym: "n-terminus" EXACT PSI-MI-alternate []
is_a: MI:0333 ! feature range status

[Term]
id: MI:0341
name: ragged n-terminus
def: "Mixture of protein forms where N-terminus has been progressively truncated." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0340 ! n-terminal position

[Term]
id: MI:0342
name: sample process
def: "Indicates the sample context in which each interacting molecule is presented to its partner." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0346 ! experimental preparation

[Term]
id: MI:0343
name: cdna library
def: "Mixed population of cDNAs (complementaryDNA) made from mRNA from a defined source, usually a specific cell type. This term should be associated only to nucleic acid interactors not to their proteins product. For instance in 2h screening use living cells (MI:0349) as sample process." [PMID:6110205]
subset: PSI-MI_slim
is_a: MI:0342 ! sample process

[Term]
id: MI:0344
name: cell lysate
def: "Cell has been physically or chemically broken open and molecule present in resulting mixture of cellular components." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0342 ! sample process

[Term]
id: MI:0345
name: author assigned name
def: "Name assigned to a molecule by the authors within a paper that may differ from the reference database." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1041 ! synonym

[Term]
id: MI:0346
name: experimental preparation
def: "Set of terms to describe the participant experimental treatment and status. This term groups a number of orthologous short controlled vocabularies delivery method, expression level, molecular source, and sample process. Each participant can then be annotated with a maximum of 4 terms selected from each short list." [PMID:14755292]
subset: PSI-MI_slim
synonym: "experimental prep" EXACT PSI-MI-short []
relationship: part_of MI:0000 ! molecular interaction

[Term]
id: MI:0348
name: fixed cell
def: "Cells has been fixed by treatment with organic solvent, staining and inclusion in a resin for microscopic analysis." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0342 ! sample process

[Term]
id: MI:0349
name: living cell
def: "Molecule is observed within in a living cell." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0342 ! sample process

[Term]
id: MI:0350
name: purified
def: "Molecule has undergone one or more purification steps to isolate it from the cellular environment." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0342 ! sample process

[Term]
id: MI:0351
name: homogeneous
def: "The author states a molecule is completely pure, i.e. no other molecular species are present." [PMID:14755292]
subset: PSI-MI_slim
synonym: "pure" EXACT PSI-MI-alternate []
is_a: MI:0350 ! purified

[Term]
id: MI:0352
name: partially purified
def: "The author states a molecule is only partially purified, i.e. other molecular species also known to be present." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0350 ! purified

[Term]
id: MI:0353
name: cross-reference type
def: "Qualifier to describe the type of information a cross-reference is pointing to." [PMID:14755292]
subset: Drugable
subset: PSI-MI_slim
synonym: "CvXrefQualifier" EXACT PSI-MI-alternate []
synonym: "refType" EXACT PSI-MI-alternate []
synonym: "xref type" EXACT PSI-MI-short []
relationship: part_of MI:0000 ! molecular interaction

[Term]
id: MI:0354
name: cellular component
def: "Cross reference pointing to a Gene Ontology -'cellular component' term." [PMID:14681407]
subset: PSI-MI_slim
synonym: "component" EXACT PSI-MI-short []
synonym: "go component term" EXACT PSI-MI-alternate []
xref: search-url: "https://www.ebi.ac.uk/QuickGO/term/${ac}"
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:0355
name: molecular function
def: "Cross reference pointing to a Gene Ontology -'molecular function' term." [PMID:14681407]
subset: PSI-MI_slim
synonym: "function" EXACT PSI-MI-short []
synonym: "go function term" EXACT PSI-MI-alternate []
xref: search-url: "https://www.ebi.ac.uk/QuickGO/term/${ac}"
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:0356
name: identical object in an external resource
def: "Reference to the corresponding object in another database. Correspondence may be complete or partial." [PMID:14755292]
comment: For instance this qualifier, in an interaction entry, can be associated to a cross reference to the same interaction in an other database.
subset: Drugable
subset: PSI-MI_slim
synonym: "identity" EXACT PSI-MI-short []
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:0357
name: method reference
def: "Reference to a related paper which more fully describes either the experimental method or one or more of the interactors used within the experiment." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:0358
name: primary-reference
def: "Used to indicate the PMID from which the experimental data is extracted." [PMID:14755292]
subset: Drugable
subset: PSI-MI_slim
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:0359
name: biological process
def: "Cross reference pointing to a Gene Ontology -'cellular process' term." [PMID:14681407]
subset: PSI-MI_slim
synonym: "go process term" EXACT PSI-MI-alternate []
synonym: "process" EXACT PSI-MI-short []
xref: search-url: "https://www.ebi.ac.uk/QuickGO/term/${ac}"
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:0360
name: secondary accession number
def: "Reference to the corresponding object in another database (like identity xref qualifier) but the identifier used in the external database is a secondary identifier or former accession number." [PMID:14755292]
subset: PSI-MI_slim
synonym: "secondary-ac" EXACT PSI-MI-short []
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:0361
name: additional information
def: "Related object within the same database or pointing to an external database." [PMID:14755292]
subset: PSI-MI_slim
synonym: "see-also" EXACT PSI-MI-short []
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:0362
name: inference
def: "Evidence based on human assumption, either when the complete experimental support is not available or when the results are extended by homology to closely related orthologues sequences." [PMID:14755292]
subset: PSI-MI_slim
synonym: "modeled" EXACT PSI-MI-alternate []
synonym: "modelled" EXACT PSI-MI-alternate []
is_a: MI:0001 ! interaction detection method
is_a: MI:0002 ! participant identification method
is_a: MI:0003 ! feature detection method

[Term]
id: MI:0363
name: inferred by author
def: "Evidence based on the author of a paper assumption, either when the complete experimental support is not available or when the results are extended by homology to closely related orthologues sequences." [PMID:14755292]
subset: PSI-MI_slim
synonym: "modeled by author" EXACT PSI-MI-alternate []
synonym: "modelled by author" EXACT PSI-MI-alternate []
is_a: MI:0362 ! inference

[Term]
id: MI:0364
name: inferred by curator
def: "Evidence based on a curator assumption, either when the complete experimental support is not available or when the results are extended by homology to closely related orthologues sequences." [PMID:14755292]
subset: PSI-MI_slim
synonym: "modeled by curator" EXACT PSI-MI-alternate []
synonym: "modelled by curator" EXACT PSI-MI-alternate []
is_a: MI:0362 ! inference

[Term]
id: MI:0365
name: enzyme tag
def: "Molecule under study is fused to an enzyme, for example alkaline phosphatase, and measure of enzyme activity can be taken as indicative of presence of protein." [PMID:10935637]
subset: PSI-MI_slim
is_a: MI:0240 ! fusion protein

[Term]
id: MI:0366
name: alkaline phosphatase tag
def: "Protein is fused to alkaline phosphatase, and the measure of this enzyme activity can be taken as indicative of presence of protein." [PMID:10935637]
subset: PSI-MI_slim
synonym: "alk phosphatase tag" EXACT PSI-MI-short []
is_a: MI:0365 ! enzyme tag

[Term]
id: MI:0367
name: green fluorescent protein tag
def: "The green fluorescent protein of organisms such as the bioluminescent jellyfish Aequorea victoria can be fused to individual proteins which then acquire fluorescence excitation and emission spectra virtually identical to those of the native." [PMID:7491768]
subset: PSI-MI_slim
synonym: "GFP" EXACT PSI-MI-alternate []
synonym: "gfp tag" EXACT PSI-MI-short []
synonym: "green fluorescent protein" EXACT PSI-MI-alternate []
is_a: MI:0687 ! fluorescent protein tag

[Term]
id: MI:0368
name: yellow fluorescent protein tag
def: "Yellow fluorescent protein from species such as Vibrio fischeri can be fused to individual proteins which then acquire fluorescence excitation and emission spectra virtually identical to those of the native." [PMID:10929120]
subset: PSI-MI_slim
synonym: "yellow fluorescent protein" EXACT PSI-MI-alternate []
synonym: "YFP" EXACT PSI-MI-alternate []
synonym: "yfp tag" EXACT PSI-MI-short []
is_a: MI:0687 ! fluorescent protein tag

[Term]
id: MI:0369
name: lex-a dimerization assay
def: "The method is based on the repression of a reporter gene activity by two LexA DNA binding domains with different binding specificities. LexA is a transcription factor with an N-terminal DNA binding/activation domain (DBAct) and a C-terminal dimerization domain. LexA dimerization is required to repress transcription efficiently. The discovery of LexA DNA binding domains that bind to different DNA sequence enabled the development of this system." [PMID:12446730]
subset: PSI-MI_slim
synonym: "gallex" EXACT PSI-MI-alternate []
synonym: "gallex" EXACT PSI-MI-short []
is_a: MI:0232 ! transcriptional complementation assay

[Term]
id: MI:0370
name: tox-r dimerization assay
def: "This assay allow identification of interactions in the inner membrane of E. coli. by using a chimeric construct ToxR-TM-MBP composed of the N-terminal DNA binding/transcriptional activation domain of ToxR (a dimerization dependant transcription factor) fused to a transmembrane domain of interest (TM) and a monomeric periplasmic anchor (the maltose binding protein). Association of the two TM results in the ToxR-mediated activation of a reporter gene such as CAT (chloroamphenicol acetyltransferase activity). The level of CAT expression indicates the strength of TM association. CAT expression can then be tested and quantify by measuring CAM resistance with disk diffusion assay or CAT activity assays on cell-free extracts." [PMID:9927659]
subset: PSI-MI_slim
synonym: "toxcat" EXACT PSI-MI-alternate []
synonym: "toxcat" EXACT PSI-MI-short []
is_a: MI:0090 ! protein complementation assay

[Term]
id: MI:0371
name: 35s radiolabel
def: "Molecule labelled with 35 radio isotope of sulfur. Proteins are often metabolically labelled, usually be growth in 35S labelled culture medium." [PMID:14755292]
subset: PSI-MI_slim
synonym: "35S" EXACT PSI-MI-alternate []
synonym: "S35" EXACT PSI-MI-alternate []
synonym: "s35 radiolabelled" EXACT PSI-MI-alternate []
is_a: MI:0517 ! radiolabel

[Term]
id: MI:0372
name: subcellular preparation
def: "Cell lysates are partially fractionated to isolate a specific subcellular fraction." [PMID:14755292]
subset: PSI-MI_slim
synonym: "subcellular prep" EXACT PSI-MI-short []
is_a: MI:0344 ! cell lysate

[Term]
id: MI:0373
name: dye label
def: "Dye coupled to a molecule allowing its identification isolation and monitoring." [PMID:14577292]
subset: PSI-MI_slim
synonym: "dye labelled" EXACT PSI-MI-short []
is_a: MI:0505 ! experimental feature

[Term]
id: MI:0374
name: cyanine label
def: "The organic polymethine  cyanine dyes which, depending on  structure, cover the spectrum from IR to UV.s. Their emission range is such that background fluorescence is often reduced. In addition these molecules can be linked directly to specific locations in synthetically produced nucleic acids." [PMID:14577292]
subset: PSI-MI_slim
is_a: MI:0373 ! dye label
is_a: MI:0857 ! fluorescent dye label

[Term]
id: MI:0375
name: cy3 label
def: "The organic cyanine Cy3 emits maximally at 570 nm." [PMID:14577292]
subset: PSI-MI_slim
is_a: MI:0374 ! cyanine label

[Term]
id: MI:0376
name: cy5 label
def: "The organic cyanine Cy5 emits maximally at 670 nm." [PMID:14577292]
subset: PSI-MI_slim
is_a: MI:0374 ! cyanine label

[Term]
id: MI:0377
name: fluorescein isothiocyanate label
def: "Fluorescein isothiocyanate is a yellow-green coloured low molecular weight dye which couples to proteins via reaction with primary amine groups at high pH. FITC is excitable at 488nm, close to its absorption maximum at 494nm, and produces maximum fluorescence emission around 520nm." [PMID:14577292]
subset: PSI-MI_slim
synonym: "FITC labelled" EXACT PSI-MI-alternate []
synonym: "fitc labelled" EXACT PSI-MI-short []
synonym: "fluorescein isothiocyanate labbeled" EXACT PSI-MI-alternate []
is_a: MI:0939 ! fluorescein label

[Term]
id: MI:0378
name: rare isotope label
def: "Molecule can be labelled including rare isotopes among its constituent atoms that can be used to identify, localize or quantify the full molecule." [PMID:14577292]
subset: PSI-MI_slim
synonym: "rare isotope label" EXACT PSI-MI-short []
is_a: MI:0253 ! isotope label

[Term]
id: MI:0379
name: 13c label
def: "Molecules labelled with isotope 13 of carbon atoms." [PMID:14577292]
subset: PSI-MI_slim
synonym: "13C" EXACT PSI-MI-alternate []
synonym: "C13" EXACT PSI-MI-alternate []
is_a: MI:0378 ! rare isotope label

[Term]
id: MI:0380
name: 15n label
def: "Molecules labelled with isotope 15 of nytrogen atoms." [PMID:14577292]
subset: PSI-MI_slim
synonym: "15N" EXACT PSI-MI-alternate []
synonym: "N15" EXACT PSI-MI-alternate []
is_a: MI:0378 ! rare isotope label

[Term]
id: MI:0381
name: 2h label
def: "Molecules labelled with isotope 2 of hydrogen atoms." [PMID:14577292]
subset: PSI-MI_slim
synonym: "2H2" EXACT PSI-MI-alternate []
synonym: "D2" EXACT PSI-MI-alternate []
synonym: "deuterium" EXACT PSI-MI-alternate []
is_a: MI:0378 ! rare isotope label

[Term]
id: MI:0382
name: mutation increasing interaction
def: "Region of a molecule whose mutation or deletion increases significantly interaction strength or rate (in the case of interactions inferred from enzymatic reaction)." [PMID:14577292]
subset: PSI-MI_slim
synonym: "mutation increasing" EXACT PSI-MI-short []
is_a: MI:0118 ! mutation

[Term]
id: MI:0383
name: biopolymer
def: "Molecule consisting of a specific sequence of amino acidic or nucleotidic monomers strung together through chemical bonds." [PMID:14577292]
subset: PSI-MI_slim
is_a: MI:0313 ! interactor type

[Term]
id: MI:0384
name: alexa label
def: "All Alexa dyes are fluorescent iodoacetamide dyes that can be conjugated with the primary amines of biomolecules. All Alexa dyes and their conjugates are more fluorescent and more photostable than the commonly used dyes. The numbers in the Alexa names indicate the approximate excitation wavelength maximum in nm)." [PMID:10449539]
subset: PSI-MI_slim
is_a: MI:0857 ! fluorescent dye label

[Term]
id: MI:0385
name: alexa 350 label
def: "Alexa fluorescent dye analogue to AMCA (7-amino-4-methylcoumarin-3-acetic acid) with an approximate excitation wavelength maximum of 350 nm." [PMID:10449539]
subset: PSI-MI_slim
is_a: MI:0384 ! alexa label

[Term]
id: MI:0386
name: alexa 430 label
def: "Alexa fluorescent dye analogue to Lucifer Yellow with an approximate excitation wavelength maximum of 430 nm." [PMID:10449539]
subset: PSI-MI_slim
is_a: MI:0384 ! alexa label

[Term]
id: MI:0387
name: alexa 488 label
def: "Alexa fluorescent dye analogue to Oregon Green 488 with an approximate excitation wavelength maximum of 488 nm." [PMID:10449539]
subset: PSI-MI_slim
is_a: MI:0384 ! alexa label

[Term]
id: MI:0388
name: alexa 532 label
def: "Alexa fluorescent dye analogue to Rhodamine 6G with an approximate excitation wavelength maximum of 532nm." [PMID:10449539]
subset: PSI-MI_slim
is_a: MI:0384 ! alexa label

[Term]
id: MI:0389
name: alexa 546 label
def: "Alexa fluorescent dye analogue to Cy3 with an approximate excitation wavelength maximum of 546nm." [PMID:10449539]
subset: PSI-MI_slim
is_a: MI:0384 ! alexa label

[Term]
id: MI:0390
name: alexa 568 label
def: "Alexa fluorescent dye analogue to Rhodamine Red-X with an approximate excitation wavelength maximum of 568nm." [PMID:10449539]
subset: PSI-MI_slim
is_a: MI:0384 ! alexa label

[Term]
id: MI:0391
name: alexa 594 label
def: "Alexa fluorescent dye analogue to Texas Red-X with an approximate excitation wavelength maximum of 594nm." [PMID:10449539]
subset: PSI-MI_slim
is_a: MI:0384 ! alexa label

[Term]
id: MI:0396
name: predetermined participant
def: "Molecule whose sequence identity is not checked and has been assumed from external or previous experimental evidence(s)." [PMID:14755292]
subset: PSI-MI_slim
synonym: "predetermined" EXACT PSI-MI-short []
is_a: MI:0661 ! experimental participant identification

[Term]
id: MI:0397
name: two hybrid array
def: "Two-hybrid screening can be done in a colony array format, in which each colony expresses a defined pair of proteins. Because the particular protein pair expressed in each colony is defined by its position in the array, positive signals identify interacting proteins without further characterization, thus obviating the need for DNA purification and sequencing. The interrogation of a two-hybrid colony array usually involves a mating strategy in which every DNA binding domain hybrid (the bait) is tested against all activation domain hybrids (the preys) in a grid pattern. Arrays usually use full-length open reading frames." [PMID:10688190, PMID:11827624]
subset: PSI-MI_slim
is_a: MI:0018 ! two hybrid

[Term]
id: MI:0398
name: two hybrid pooling approach
def: "In the pooling strategy sets of either both bait and prey hybrid vectors are mated or, more commonly, individual baits are mated against pools of preys. This approach required cloning baits and preys into both two-hybrid vectors, followed by pooling sets of transformants. The positive double hybrid clones are the interacting partners. The pooling of both baits and prey molecules is now a rarely used technique as the pooling of baits often leads to misleading results." [PMID:11283351, PMID:20946815]
subset: PSI-MI_slim
synonym: "two hybrid pooling" EXACT PSI-MI-short []
is_a: MI:0018 ! two hybrid

[Term]
id: MI:0399
name: two hybrid fragment pooling approach
def: "Individual baits are mated against pools of random fragmented preys. The usage of degenerated fragment allows identification of the minimal protein region required for the interaction. Since multiple clones that encode overlapping regions of protein are often identified, the minimal domain for interaction may be readily apparent from the initial screen." [PMID:12634794]
subset: PSI-MI_slim
synonym: "2h fragment pooling" EXACT PSI-MI-short []
is_a: MI:1112 ! two hybrid prey pooling approach

[Term]
id: MI:0400
name: affinity technology
def: "Techniques which depend upon the strength of the interaction between two entities." [PMID:14755292]
subset: PSI-MI_slim
synonym: "affinity techniques" EXACT PSI-MI-short []
is_a: MI:0401 ! biochemical

[Term]
id: MI:0401
name: biochemical
def: "The application of chemical principles and methods to biological experiments to demonstrate an interaction." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0045 ! experimental interaction detection

[Term]
id: MI:0402
name: chromatin immunoprecipitation assay
def: "Chromatin immunoprecipitation (ChIP) is a powerful approach that allows one to define the interaction of factors with specific chromosomal sites in living cells. An antibody against a protein suspected of binding a given cis-element is used to immunoprecipitate fragmented chromatin fragments. Cells or tissue may first be briefly treated with an agent such formaldehyde to crosslink proteins to DNA.  Nucleic acids are then identified by sequencing, for example polymerase chain reaction analysis of the immunoprecipitate with primers flanking the cis-element  or next-generation sequencing techniques" [PMID:12054902]
subset: PSI-MI_slim
synonym: "ch-ip" EXACT PSI-MI-short []
is_a: MI:0019 ! coimmunoprecipitation

[Term]
id: MI:0403
name: colocalization
def: "Coincident occurrence of molecules in a given subcellular fraction observed with a low resolution methodology from which a physical interaction among those molecules cannot be inferred." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0190 ! interaction type

[Term]
id: MI:0404
name: comigration in non denaturing gel electrophoresis
def: "A method allowing the detection of strong interactions between two or more molecules as running, all of them, within a single band in a non-denaturing gel." [PMID:14755292]
subset: PSI-MI_slim
synonym: "comig non denat gel" EXACT PSI-MI-short []
is_a: MI:0807 ! comigration in gel electrophoresis

[Term]
id: MI:0405
name: competition binding
def: "Competitive binding experiments measure equilibrium binding of a single concentration of ligand at various concentrations of an unlabeled competitor. Analysis of these data gives the affinity of the receptor for the competitor." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0400 ! affinity technology

[Term]
id: MI:0406
name: deacetylase assay
def: "Measures the catalysis of the hydrolysis of an acetyl group or groups from a substrate molecule." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0415 ! enzymatic study

[Term]
id: MI:0407
name: direct interaction
def: "Interaction between molecules that are in direct contact with each other." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0915 ! physical association

[Term]
id: MI:0408
name: disulfide bond
def: "Covalent bond mediated by 2 sulfur atoms." [PMID:14755292]
subset: PSI-MI_slim
synonym: "disulfide bridge" EXACT PSI-MI-alternate []
synonym: "SS-bond" EXACT PSI-MI-alternate []
is_a: MI:0195 ! covalent binding

[Term]
id: MI:0409
name: dna footprinting
def: "Experimental method used to identify the region of a nucleic acid involved in an interaction with a protein. One sample of a radiolabeled nucleic acid of known sequence is submitted to partial digestion. A second sample is incubated with its interacting partner and then is submitted to the same partial digestion. The two samples are then analyzed in parallel by electrophoresis on a denaturing acrylamide gel. After autoradiography the identification of the bands that correspond to fragments missing from the lane loaded with the second sample reveals the region of the nucleic acid that is protected from nuclease digestion upon binding.\nOBSOLETE because redundant with MI:0417 'footprinting' combined with interactor type MI:0319 'DNA' \nreplace by:MI:0417" [PMID:14755292]
subset: PSI-MI_slim
is_obsolete: true

[Term]
id: MI:0410
name: 3D electron microscopy
def: "Three-dimensional (3D) reconstruction of single, transparent objects from a collection of projection images recorded with a transmission electron microscope. It offers the opportunity to obtain 3D information on structural cellular arrangements with a high resolution." [PMID:12160704]
subset: PSI-MI_slim
synonym: "3D-EM" EXACT PSI-MI-short []
synonym: "electron tomog" EXACT PSI-MI-alternate []
is_a: MI:0020 ! transmission electron microscopy

[Term]
id: MI:0411
name: enzyme linked immunosorbent assay
def: "Following non-covalent binding of a purified primary ligand to a solid phase, a blocking reagent is added to prevent any non-specific binding. A specific antigen is then allowed to bind to the primary ligand. Unbound antigen is removed by washing and a secondary antibody conjugated to an enzyme (e.g. horseradish peroxidase) is added. Following a washing step to remove unbound secondary ligand, the extent to which a chromogenic substrate (e.g. 3,3', 5,5' tetramethyl benzidine chromogen [TMB]) is converted to a soluble coloured product by the conjugated enzyme in a given time is determined by spectrophotometry using a standard microplate absorbance reader. A similar type of approach can be utilized to detect enzymatic activities. The substrate, attached to a solid phase is incubated in the presence of the enzyme and the enzymatic modification is monitored by an antibody that is specific for the modified substrate (for instance a phosphorylated protein)." [PMID:11906746]
subset: PSI-MI_slim
synonym: "ELISA" EXACT PSI-MI-alternate []
synonym: "elisa" EXACT PSI-MI-short []
is_a: MI:0421 ! identification by antibody
is_a: MI:0892 ! solid phase assay

[Term]
id: MI:0412
name: electrophoretic mobility supershift assay
def: "The EMSA supershift is a EMSA experiment carried out using a third lane loaded with the radiolabeled nucleic acid, a protein mixture and an antibody for a specific protein. If an extra retardation is observed, this is due to the formation of a larger complex including the antibody. By this approach, at least one protein of the complex is directly identified." [PMID:12169687]
subset: PSI-MI_slim
synonym: "emsa supershift" EXACT PSI-MI-short []
is_a: MI:0413 ! electrophoretic mobility shift assay

[Term]
id: MI:0413
name: electrophoretic mobility shift assay
def: "This method proves the interaction between a nucleic acid and a protein partner. On the same electrophoresis gel 1 lane is loaded with a nucleic acid of known sequence, a second lane is loaded with the same nucleic acid together with a purified protein (or a protein mixture). The nucleic acid is often radio-labelled to enable visualisation by autoradiography. Comparison of the nucleic acid migration in the two lanes enables the retardation of the nucleic acid due to its interaction with a protein to be observed." [PMID:12169687]
subset: PSI-MI_slim
synonym: "band shift" EXACT PSI-MI-alternate []
synonym: "emsa" EXACT PSI-MI-short []
synonym: "Gel retardation assay" EXACT PSI-MI-alternate []
is_a: MI:0807 ! comigration in gel electrophoresis

[Term]
id: MI:0414
name: enzymatic reaction
def: "terms aiming to represent biochemical reactions referring to their resulting product modifications." [PMID:14755292]
subset: PSI-MI_slim
synonym: "Biochemical reaction" EXACT PSI-MI-alternate []
is_a: MI:0407 ! direct interaction

[Term]
id: MI:0415
name: enzymatic study
def: "Participants are enzyme or substrate in a biochemical reaction." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0401 ! biochemical

[Term]
id: MI:0416
name: fluorescence microscopy
def: "Fluorescent microscopy uses a high intensity light to illuminate the sample. This light excites fluorescence species in the sample, which then emit light of a longer wavelength. A fluorescent microscope also produces a magnified image of the sample, but the image is based on the second light source -- the light emanating from the fluorescent species -- rather than from the light originally used to illuminate, and excite, the sample." [PMID:14755292]
subset: PSI-MI_slim
synonym: "fluorescence imaging" EXACT PSI-MI-short []
is_a: MI:0428 ! imaging technique

[Term]
id: MI:0417
name: footprinting
def: "Footprinting analysis is used to identify regions of molecules involved in binding other macromolecules and therefore protected from the effects of degradative enzymes, chemical treatment or other deleterious treatments." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0401 ! biochemical

[Term]
id: MI:0418
name: genetic
def: "methods supporting genetic interactions.\nOBSOLETE as too unspecific use Genetic interference instead MI:0254." [PMID:14755292]
subset: PSI-MI_slim
is_obsolete: true

[Term]
id: MI:0419
name: gtpase assay
def: "Measures the catalysis of the reaction: GTP + H2O = GDP + phosphate." [PMID:14755292]
subset: PSI-MI_slim
synonym: "gtp hydrolisis" EXACT PSI-MI-alternate []
synonym: "GTPase" EXACT PSI-MI-alternate []
is_a: MI:0879 ! nucleoside triphosphatase assay

[Term]
id: MI:0420
name: kinase homogeneous time resolved fluorescence
def: "Measures quenching of the nonradiative energy transfer between fluorescent long-lifetime lanthanide chelates and different acceptors. Relies on a fluorescence energy donor and acceptor being added from close proximity on the phosphorylated substrate due to the action of the kinase." [PMID:14987100]
subset: PSI-MI_slim
synonym: "homogeneous time-resolved fluorescence" EXACT PSI-MI-alternate []
synonym: "kinase HTRF" EXACT PSI-MI-alternate []
synonym: "kinase htrf" EXACT PSI-MI-short []
is_a: MI:0424 ! protein kinase assay
is_a: MI:0510 ! homogeneous time resolved fluorescence

[Term]
id: MI:0421
name: identification by antibody
def: "Antibody mediated participant identification." [PMID:14755292]
subset: PSI-MI_slim
synonym: "antibody detection" EXACT PSI-MI-short []
is_a: MI:0661 ! experimental participant identification

[Term]
id: MI:0422
name: immunostaining
def: "Method using an antibody coupled with some colouring agent to detect a specific protein within a cell or tissue sample. In some cases the primary antibody is directly linked to a colouring agent, more often the primary antibody is targeted by a secondary antibody, targeting the primary antibody." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0421 ! identification by antibody

[Term]
id: MI:0423
name: in-gel kinase assay
def: "Substrate protein radio-labelled by kinase transferring an isotope of phosphate from the nucleotide. Substrate isolated by gel electrophoresis and radio-labelling confirmed by autoradiography." [PMID:14755292]
subset: PSI-MI_slim
synonym: "in gel kinase assay" EXACT PSI-MI-short []
is_a: MI:0424 ! protein kinase assay

[Term]
id: MI:0424
name: protein kinase assay
def: "Catalysis of the transfer of a phosphate group, usually from ATP, to a protein substrate." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0841 ! phosphotransferase assay

[Term]
id: MI:0425
name: kinase scintillation proximity assay
def: "Relies on the radiolabelling of a peptide substrate immobilized on a scintillant coated SPA-bead. The kinase transfers a phosphate isotope from the nucleotide to the substrate." [PMID:14755292]
subset: PSI-MI_slim
synonym: "kinase spa" EXACT PSI-MI-short []
is_a: MI:0099 ! scintillation proximity assay
is_a: MI:0424 ! protein kinase assay

[Term]
id: MI:0426
name: light microscopy
def: "Light visible microscopy uses environmental light to illuminate the sample and produce a magnified image of the sample." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0428 ! imaging technique

[Term]
id: MI:0427
name: Identification by mass spectrometry
def: "identification by mass spectrometry." [PMID:14755292]
subset: PSI-MI_slim
synonym: "ms participant" EXACT PSI-MI-short []
is_a: MI:0661 ! experimental participant identification

[Term]
id: MI:0428
name: imaging technique
def: "Methods that provide images of molecules at various resolution depending on the technology used." [PMID:14755292]
subset: PSI-MI_slim
synonym: "microscopy" EXACT PSI-MI-alternate []
is_a: MI:0045 ! experimental interaction detection

[Term]
id: MI:0429
name: necessary binding region
def: "A sequence range within a molecule identified as being absolutely required for an interaction. The sequence may or may not be in direct physical contact with the interaction partner." [PMID:14755292]
subset: PSI-MI_slim
synonym: "deletion disrupting interaction" EXACT []
synonym: "necessary binding site" EXACT []
synonym: "required to bind" EXACT PSI-MI-short []
is_a: MI:0117 ! binding-associated region
is_a: MI:0573 ! mutation disrupting interaction
is_a: MI:1128 ! mutation disrupting interaction strength
is_a: MI:1129 ! mutation disrupting interaction rate

[Term]
id: MI:0430
name: nucleic acid uv cross-linking assay
def: "Nucleic acids are incubated with purified proteins or a protein mixture and then exposed to a chemical cross-linking agent that may be activated by UV light exposure. The eventual complexes can be identified by sequencing or autoradiography if the nucleic acid is radio-labelled and the sequence is known. The proteins involved in the complex can be recognized by specific antibodies or by retrieving the original protein mixture and carrying further analysis on it." [PMID:14755292]
subset: PSI-MI_slim
synonym: "nucl ac uv crosslink" EXACT PSI-MI-short []
is_a: MI:0030 ! cross-linking study

[Term]
id: MI:0431
name: obsolete
def: "Deprecated terms.\nOBSOLETE term replaced by the default OBO class 'Obsolete'." [PMID:14755292]
subset: PSI-MI_slim
is_obsolete: true

[Term]
id: MI:0432
name: one hybrid
def: "Protein-DNA complementation assay where a single promoter act as bait and is screened against a library of prey transcription factors." [PMID:10589421]
subset: PSI-MI_slim
synonym: "1 hybrid" EXACT PSI-MI-short []
synonym: "one-hybrid" EXACT PSI-MI-alternate []
synonym: "yeast one hybrid" EXACT PSI-MI-alternate []
synonym: "yeast one-hybrid" EXACT PSI-MI-alternate []
is_a: MI:0232 ! transcriptional complementation assay

[Term]
id: MI:0433
name: partial identification of protein sequence
def: "partial protein sequence identification." [PMID:14755292]
subset: PSI-MI_slim
synonym: "partial id prot seq" EXACT PSI-MI-short []
is_a: MI:0093 ! protein sequence identification
is_a: MI:0659 ! experimental feature detection

[Term]
id: MI:0434
name: phosphatase assay
def: "Measures the catalysis of the reaction: a phosphosubstrate + H2O = a substrate + phosphate." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0415 ! enzymatic study

[Term]
id: MI:0435
name: protease assay
def: "Measures the enzymatic hydrolysis of a peptide bond within a peptide or protein substrate." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0990 ! cleavage assay

[Term]
id: MI:0436
name: protein footprinting
def: "Protein footprinting is a technique for identifying structural changes modulated by protein-ligand binding, and mapping protein-ligand interfaces This technique involves attaching cutting reagents randomly to amino acid residue (e.g. lysine or cysteine) on the proteins surface and then using this lysine-labelled protein to cleave polypeptide backbone of the other protein at exposed residues adjacent to its binding site." [PMID:14600024, PMID:14967031, PMID:14987073]
subset: PSI-MI_slim
is_a: MI:0659 ! experimental feature detection

[Term]
id: MI:0437
name: protein three hybrid
def: "Two hybrid assay performed with a third protein component co-transfected into a recombinant yeast strain together with a bait and a prey construct. Negative control shows that the interaction between the bait and the prey do not occur when the third protein is not co-transfected." [PMID:12052864, PMID:12761205, PMID:12935900]
subset: PSI-MI_slim
synonym: "bridge assay" EXACT PSI-MI-alternate []
synonym: "protein 3-hybrid" EXACT PSI-MI-alternate []
synonym: "protein tri hybrid" EXACT PSI-MI-alternate []
synonym: "trihybrid" EXACT PSI-MI-alternate []
is_a: MI:0018 ! two hybrid
is_a: MI:0588 ! three hybrid

[Term]
id: MI:0438
name: rna three hybrid
def: "In vivo reconstruction of specific RNA-proteins interactions. The DNA binding and transcription activator domains of GAL4 are brought together via the interaction of recombinant RNA. The first hybrid protein contains the DNA binding domain of GAL4 fused to RevM10 (a mutated RNA binding protein of HIV-1 that binds specifically to the Rev responsive element RRE of the env gene). A recombinant RNA contains the RRE sequence and a target RNA sequence X. The second hybrid protein contains the activation domain of GAL4 fused to protein Y tested for its ability to bind the target RNA X. If this interaction occurs the three hybrid reconstructs GAL4 and the transcription of a reporter gene is activated." [PMID:12162957, PMID:8972875]
subset: PSI-MI_slim
synonym: "rna 3-hybrid" EXACT PSI-MI-alternate []
synonym: "rna tri hybrid" EXACT PSI-MI-alternate []
synonym: "rna-three hybrid" EXACT PSI-MI-alternate []
synonym: "Three hybrid system" EXACT PSI-MI-alternate []
is_a: MI:0588 ! three hybrid

[Term]
id: MI:0439
name: random spore analysis
def: "A technique used to detect genetic interactions between 2 (or more) genes in a sporulating organism by scoring a large population of haploid spores for a phenotype and correlating the phenotype with the presence of single vs double (multiple) mutations. A diploid heterozygous organism harbouring mutations in two (or more) genes is induced to sporulate. Resulting spores are meiotic segregants that are haploid and are either wild type or mutant at each locus. Spores are scored for a phenotype, such as loss of viability." [PMID:14755292]
subset: PSI-MI_slim
synonym: "random-spore analysis" EXACT PSI-MI-alternate []
synonym: "RSA" EXACT PSI-MI-alternate []
synonym: "rsa" EXACT PSI-MI-short []
synonym: "spore germination" EXACT PSI-MI-alternate []
is_a: MI:0254 ! genetic interference

[Term]
id: MI:0440
name: saturation binding
def: "Saturation binding experiments measure specific ligand binding at equilibrium at various concentrations of the ligand. Analysis of these data can determine receptor number and affinity." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0400 ! affinity technology

[Term]
id: MI:0441
name: synthetic genetic analysis
def: "Identification of genetic interactions by generation of an organism harbouring mutations in 2 or more genes and scoring for a phenotype, such as loss of viability, that is not observed for any of the mutations in isolation." [PMID:14755292]
subset: PSI-MI_slim
synonym: "SGA" EXACT PSI-MI-alternate []
synonym: "sga" EXACT PSI-MI-short []
is_a: MI:0254 ! genetic interference

[Term]
id: MI:0442
name: sufficient binding region
def: "Binding will occur when this sequence range is present within a molecule or part of a molecule. This region will contain the direct binding region but may be longer." [PMID:14755292]
subset: PSI-MI_slim
synonym: "sufficient binding site" EXACT []
synonym: "sufficient to bind" EXACT PSI-MI-short []
is_a: MI:0117 ! binding-associated region

[Term]
id: MI:0443
name: ubiquitin binding
def: "Interaction concerning ubiquitin that is covalently attached to any Lys residue of its interaction partner.\nOBSOLETE remap to ubiquitination reaction (MI:0220) or describe ubiquitine as a participant on the interaction using physical interaction (MI:0218) or covalent binding (MI:0195) as interaction type." [PMID:14755292]
subset: PSI-MI_slim
is_obsolete: true

[Term]
id: MI:0444
name: database citation
def: "Database citation list names of databases commonly used to cross reference interaction data." [PMID:14755292]
subset: Drugable
subset: PSI-MI_slim
relationship: part_of MI:0000 ! molecular interaction

[Term]
id: MI:0445
name: literature database
def: "Databases acting as a source of literature information." [PMID:14755292]
subset: Drugable
subset: PSI-MI_slim
synonym: "literature xref" EXACT PSI-MI-short []
synonym: "publication xref" EXACT PSI-MI-alternate []
is_a: MI:0444 ! database citation

[Term]
id: MI:0446
name: pubmed
def: "PubMed is designed to provide access to citations from biomedical literature. The data can be found at both NCBI PubMed and Europe PubMed Central. \nhttp://www.ncbi.nlm.nih.gov/pubmed\nhttp://europepmc.org" [PMID:14755292]
subset: Drugable
subset: PSI-MI_slim
xref: id-validation-regexp: "[0-9]+"
xref: search-url: "http://europepmc.org/abstract/MED/${ac}"
is_a: MI:0445 ! literature database

[Term]
id: MI:0447
name: feature database
def: "A database describing a feature on a molecule." [PMID:14755292]
subset: PSI-MI_slim
synonym: "feature xref" EXACT PSI-MI-short []
is_a: MI:0444 ! database citation

[Term]
id: MI:0448
name: gene ontology
def: "The objective of Gene Ontology (GO) is to provide controlled vocabularies for the description of the molecular function, biological process and cellular component of gene products.\nhttp://www.ebi.ac.uk/GO" [PMID:14755292]
subset: PSI-MI_slim
synonym: "go" EXACT PSI-MI-short []
xref: id-validation-regexp: "GO:[0-9]{7}"
xref: search-url: "https://www.ebi.ac.uk/QuickGO/term/${ac}"
is_a: MI:0447 ! feature database
is_a: MI:0461 ! interaction database

[Term]
id: MI:0449
name: interpro
def: "InterPro combines a number of databases (referred to as member databases) that use different methodologies and a varying degree of biological information on well-characterised proteins to derive protein signatures that predict family membership and domain composition of naive protein sequences.\nhttps://www.ebi.ac.uk/interpro/" [PMID:1252001]
subset: PSI-MI_slim
synonym: "InterPro" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "IPR[0-9]{6}"
xref: search-url: "https://www.ebi.ac.uk/interpro/entry/InterPro/${ac}"
is_a: MI:0447 ! feature database

[Term]
id: MI:0450
name: cdd
def: "The Conserved Domain Database may be used to identify the conserved domains present in a protein sequence.\nhttp://www.ncbi.nlm.nih.gov/Structure/cdd/cdd.shtml" [PMID:14755292]
subset: PSI-MI_slim
synonym: "CDD" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "[0-9]+"
is_a: MI:0447 ! feature database

[Term]
id: MI:0451
name: pfam
def: "Pfam is a large collection of multiple sequence alignments and hidden Markov models covering many common protein domains.\nhttp://www.sanger.ac.uk/Software/Pfam" [PMID:14755292]
subset: PSI-MI_slim
synonym: "Pfam" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "PF[0-9]{5}"
is_a: MI:0449 ! interpro

[Term]
id: MI:0452
name: pirsf
def: "PIRSF is a classification system based on evolutionary relationship of whole proteins.\nhttp://pir.georgetown.edu/pirwww/dbinfo/pirsf.shtml" [PMID:14755292]
subset: PSI-MI_slim
synonym: "PIRSF" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "PIRSF[0-9]{5}"
is_a: MI:0449 ! interpro

[Term]
id: MI:0453
name: prints
def: "PRINTS is a compendium of protein fingerprints. A fingerprint is a group of conserved motifs used to characterise a protein family.\nhttp://umber.sbs.man.ac.uk/dbbrowser/PRINTS/" [PMID:14755292]
subset: PSI-MI_slim
synonym: "PRINTS" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "PR[0-9]{6}"
is_a: MI:0449 ! interpro

[Term]
id: MI:0454
name: prodom
def: "The ProDom protein domain database consists of an automatic compilation of homologous domains.\nhttp://protein.toulouse.inra.fr/prodom.html" [PMID:14755292]
subset: PSI-MI_slim
synonym: "ProDom" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "PD[0-9]{6}"
is_a: MI:0449 ! interpro

[Term]
id: MI:0455
name: prosite
def: "PROSITE is a database of protein families and domains. It consists of biologically significant sites, patterns and profiles.\nhttp://us.expasy.org/prosite/" [PMID:14755292]
subset: PSI-MI_slim
synonym: "Prosite" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "PS[0-9]{5}"
is_a: MI:0449 ! interpro

[Term]
id: MI:0456
name: scop superfamily
def: "SUPERFAMILY is a library of profile hidden Markov models that represent all proteins of known structure. The library is based on the SCOP classification of proteins: each model corresponds to a SCOP domain.\nhttp://supfam.mrc-lmb.cam.ac.uk/SUPERFAMILY/" [PMID:14755292]
subset: PSI-MI_slim
synonym: "SCOP superfamily" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "[0-9]+"
is_a: MI:0449 ! interpro

[Term]
id: MI:0457
name: smart
def: "SMART (a Simple Modular Architecture Research Tool) allows the identification and annotation of genetically mobile domains and the analysis of domain architectures.\nhttp://smart.embl-heidelberg.de/" [PMID:14755292]
subset: PSI-MI_slim
synonym: "SMART" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "SM[0-9]{5}"
is_a: MI:0449 ! interpro

[Term]
id: MI:0458
name: tigrfams
def: "TIGRFAMs is a collection of protein families, featuring curated multiple sequence alignments, Hidden Markov Models (HMMs) and annotation.\nhttp://www.tigr.org/TIGRFAMs" [PMID:14755292]
subset: PSI-MI_slim
synonym: "TIGRFAMs" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "TIGR[0-9]+"
is_a: MI:0449 ! interpro

[Term]
id: MI:0459
name: mmdb
def: "MMDB (Molecular Modeling DataBase), is a subset of three-dimensional structures obtained from the Protein Data Bank.\nhttp://www.ncbi.nlm.nih.gov/Structure" [PMID:14755292]
subset: PSI-MI_slim
synonym: "MMDB" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "[0-9]+"
is_a: MI:0447 ! feature database
is_a: MI:0461 ! interaction database

[Term]
id: MI:0460
name: rcsb pdb
def: "The RCSB PDB provides a variety of tools and resources for studying the structures of biological macromolecules and their relationships to sequence, function, and disease. \nhttp://www.pdb.org/" [PMID:14634627]
subset: Drugable
subset: PSI-MI_slim
synonym: "PDB" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "[0-9][a-zA-Z0-9]{3}"
xref: search-url: "http://www.pdb.org/pdb/explore/explore.do?structureId=${ac}"
is_a: MI:0805 ! wwpdb

[Term]
id: MI:0461
name: interaction database
def: "Databases that contain experimental or predictive molecular interaction data." [PMID:14755292]
subset: Drugable
subset: PSI-MI_slim
synonym: "interaction xref" EXACT PSI-MI-short []
is_a: MI:0444 ! database citation

[Term]
id: MI:0462
name: bind
def: "The Biomolecular Interaction Network Database (BIND) is a collection of records documenting molecular interactions.\nhttp://www.blueprint.org/bind" [PMID:14755292]
subset: PSI-MI_slim
synonym: "BIND" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "[0-9]+"
is_a: MI:0461 ! interaction database
is_a: MI:0489 ! source database

[Term]
id: MI:0463
name: biogrid
def: "The General Repository for Interaction Datasets (BioGRID) is a database of genetic and physical interactions.\nhttp://thebiogrid.org" [PMID:21071413]
subset: PSI-MI_slim
synonym: "BioGRID" EXACT PSI-MI-alternate []
is_a: MI:0461 ! interaction database
is_a: MI:0489 ! source database

[Term]
id: MI:0464
name: cygd
def: "The MIPS Comprehensive Yeast Genome Database (CYGD) aims to present information on the molecular structure and functional network of the entirely sequenced, well-studied model eukaryote, the budding yeast Saccharomyces cerevisiae. In addition the data of various projects on related yeasts are used for comparative analysis.\nhttp://mips.gsf.de/proj/yeast/CYGD.\nhttp://mips.gsf.de/genre/proj/mpact" [PMID:14755292]
subset: PSI-MI_slim
synonym: "CYGD" EXACT PSI-MI-alternate []
synonym: "CYGD (MIPS)" EXACT PSI-MI-alternate []
synonym: "MIPS" EXACT PSI-MI-alternate []
synonym: "MPact" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "[0-9]+|[A-Z]{3}[0-9]{3}[A-Za-z](-[A-Za-z])?|[A-Z0-9]+\\.[0-9]+|YM[A-Z][0-9]{3}[a-z][0-9]"
is_a: MI:0489 ! source database
is_a: MI:1094 ! genome databases
is_a: MI:1106 ! pathways database

[Term]
id: MI:0465
name: dip
def: "The database of interacting protein (DIP) database stores experimentally determined interactions between proteins. It combines information from a variety of sources to create a single, consistent set of protein-protein interactions.\nhttp://dip.doe-mbi.ucla.edu/" [PMID:14755292]
subset: PSI-MI_slim
synonym: "DIP" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "DIP[0-9]+[NE]"
xref: search-url: "http://identifiers.org/dip/"
is_a: MI:0461 ! interaction database
is_a: MI:0973 ! imex source

[Term]
id: MI:0466
name: ecocyc
def: "EcoCyc is a bioinformatics database that describes the genome and the biochemical machinery of E. coli K12 MG1655.\nhttp://ecocyc.org/" [PMID:14755292]
subset: PSI-MI_slim
synonym: "EcoCyc" EXACT PSI-MI-alternate []
is_a: MI:1106 ! pathways database

[Term]
id: MI:0467
name: reactome
def: "The Reactome project is a collaboration among Cold Spring Harbor Laboratory, The European Bioinformatics Institute, and The Gene Ontology Consortium to develop a curated resource of core pathways and reactions in human biology.\nhttp://www.reactome.org/" [PMID:21067998]
subset: PSI-MI_slim
synonym: "Genome Knowledge Base" EXACT PSI-MI-alternate []
synonym: "GKB" EXACT PSI-MI-alternate []
synonym: "Reactome" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "REACT_\\d+(\\.\\d+)?$"
xref: search-url: "http://www.reactome.org/content/detail/${ac}"
is_a: MI:1106 ! pathways database

[Term]
id: MI:0468
name: hprd
def: "The Human Protein Reference Database represents a centralized platform to visually depict and integrate information pertaining to domain architecture, post-translational modifications, interaction networks and disease association for each protein in the human proteome.\nhttp://www.hprd.org/" [PMID:14755292]
subset: Drugable
subset: PSI-MI_slim
synonym: "HPRD" EXACT PSI-MI-alternate []
is_a: MI:0461 ! interaction database

[Term]
id: MI:0469
name: intact
def: "INTerAction database (IntAct) provides an open source database and toolkit for the storage, presentation and analysis of molecular interactions.\nhttp://www.ebi.ac.uk/intact" [PMID:14681455, PMID:19850723, PMID:22121220]
subset: PSI-MI_slim
synonym: "IntAct" EXACT PSI-MI-alternate []
synonym: "intact" EXACT PSI-MI-short []
xref: id-validation-regexp: "EBI-[0-9]+|IA:[0-9]+"
xref: search-url: "http://www.ebi.ac.uk/intact/query/${ac}"
is_a: MI:0461 ! interaction database
is_a: MI:0973 ! imex source

[Term]
id: MI:0470
name: kegg
def: "KEGG (Kyoto Encyclopedia of Genes and Genomes) is a knowledge base for systematic analysis of gene functions, linking genomic information with higher order functional information and also supplies information about chemical compounds, enzyme molecules and enzymatic reactions.\nhttp://www.genome.ad.jp/kegg/" [PMID:14755292]
subset: Drugable
subset: PSI-MI_slim
synonym: "KEGG" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "[a-zA-Z]+:[a-zA-Z]+[0-9]+"
is_a: MI:0473 ! participant database
is_a: MI:1106 ! pathways database

[Term]
id: MI:0471
name: mint
def: "The Molecular INTeraction database (MINT) is a relational database designed to store interactions between biological molecules.\nhttp://mint.bio.uniroma2.it" [PMID:14755292]
subset: PSI-MI_slim
synonym: "MINT" EXACT PSI-MI-short []
xref: id-validation-regexp: "MINT-[0-9]+"
xref: search-url: "https://mint.bio.uniroma2.it/index.php/results-interactions/?id=${ac}"
is_a: MI:0461 ! interaction database
is_a: MI:0973 ! imex source

[Term]
id: MI:0472
name: pdbe
def: "The Protein Data Bank in Europe - the European project for the collection, management and distribution of data about macromolecular structures, derived in part from the Protein Data Bank (PDB).\nhttp://www.ebi.ac.uk/pdbe/" [PMID:16381867]
subset: PSI-MI_slim
synonym: "e-MSD" EXACT []
synonym: "MSD" RELATED []
synonym: "PQS" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "[0-9][a-zA-Z0-9]{3}"
xref: search-url: "http://www.ebi.ac.uk/pdbe/entry/pdb/${ac}"
is_a: MI:0805 ! wwpdb

[Term]
id: MI:0473
name: participant database
def: "Database of molecules participating in molecular interactions." [PMID:14755292]
subset: Drugable
subset: PSI-MI_slim
synonym: "participant xref" EXACT PSI-MI-short []
is_a: MI:0444 ! database citation

[Term]
id: MI:0474
name: chebi
def: "A definitive, freely available database of Chemical compounds of Biological Interest (ChEBI).\nhttp://www.ebi.ac.uk/chebi/" [PMID:14755292]
subset: Drugable
subset: PSI-MI_slim
synonym: "ChEBI" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "CHEBI:[0-9]+"
xref: search-url: "http://www.ebi.ac.uk/chebi/searchId.do?chebiId=${ac}"
is_a: MI:2054 ! bioactive entity reference

[Term]
id: MI:0475
name: ddbj/embl/genbank
def: "DDBJ EMBL GenBank Nucleotide Sequence Database Collaboration exchange new and updated data on a daily basis to achieve optimal synchronisation.\nhttp://www.ebi.ac.uk/embl/Contact/collaboration" [PMID:14755292]
subset: PSI-MI_slim
synonym: "DDBJ" EXACT PSI-MI-alternate []
synonym: "DDBJ/EMBL/GenBank" EXACT PSI-MI-alternate []
synonym: "EMBL" EXACT PSI-MI-alternate []
synonym: "GenBank" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "[A-Z][0-9]{5}|[A-Z][0-9]{5}\\.[0-9]+|[A-Z]{2}[0-9]{6}|[A-Z]{2}[0-9]{6}\\.[0-9]+|[A-Z]{4}[0-9]{8}|[A-Z]{4}[0-9]{8}\\.[0-9]+"
xref: search-url: "http://www.ebi.ac.uk/cgi-bin/dbfetch?db=EMBLSVA&id=${ac}"
is_a: MI:0683 ! sequence database

[Term]
id: MI:0476
name: ensembl
def: "Ensembl is a joint project between the EMBL-EBI and the Wellcome Trust Sanger Institute that aims at developing a system that maintains automatic annotation of large eukaryotic genomes.\nhttp://www.ensembl.org" [PMID:15078858]
subset: PSI-MI_slim
synonym: "Ensembl" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "ENS[A-Z]+[0-9]{11}|[A-Z]{3}[0-9]{3}[A-Za-z](-[A-Za-z])?|CG[0-9]+|[A-Z0-9]+\\.[0-9]+|YM[A-Z][0-9]{3}[a-z][0-9]"
xref: search-url: "http://www.ensembl.org/Multi/Search/Results?q=${ac}"
is_a: MI:1094 ! genome databases

[Term]
id: MI:0477
name: entrez gene/locuslink
def: "LocusLink provides a single query interface to curated sequence and descriptive information about genetic loci.\nhttp://www.ncbi.nlm.nih.gov/LocusLink/" [PMID:14755292]
subset: PSI-MI_slim
synonym: "Entrez gene/locuslink" EXACT PSI-MI-alternate []
synonym: "entrezgene/locuslink" EXACT PSI-MI-short []
xref: id-validation-regexp: "[0-9]+|[A-Z]{1,2}_[0-9]+|[A-Z]{1,2}_[A-Z]{1,4}[0-9]+"
is_a: MI:1109 ! gene database

[Term]
id: MI:0478
name: flybase
def: "FlyBase is a comprehensive database for information on the genetics and molecular biology of Drosophila.\nhttp://flybase.org" [PMID:14755292]
subset: PSI-MI_slim
synonym: "FlyBase" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "FB[a-z]{2}[0-9]{7}"
xref: search-url: "http://flybase.org/reports/${ac}"
is_a: MI:1094 ! genome databases

[Term]
id: MI:0479
name: mgd/mgi
def: "Mouse Genome Informatics (MGI) provides integrated access to data on the genetics, genomics, and biology of the laboratory mouse.\nhttp://www.informatics.jax.org/" [PMID:14755292]
subset: PSI-MI_slim
synonym: "MGD/MGI" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "MGI:[0-9]+"
is_a: MI:1094 ! genome databases

[Term]
id: MI:0480
name: omim
def: "Online Mendelian Inheritance in Man (OMIM) is a catalogue of human genes and genetic disorders, with links to literature references, sequence records, maps, and related databases.\nhttp://www.ncbi.nlm.nih.gov/entrez/query.fcgi?db=OMIM" [PMID:14755292]
subset: PSI-MI_slim
synonym: "OMIM" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "[0-9]+"
xref: search-url: "http://www.omim.org/entry/${ac}"
is_a: MI:0683 ! sequence database

[Term]
id: MI:0481
name: refseq
def: "The Reference Sequence (RefSeq) collection aims to provide a comprehensive, integrated, non-redundant set of sequences, including genomic DNA, transcript (RNA), and protein products, for a number of organisms.\nhttp://www.ncbi.nlm.nih.gov/RefSeq/" [PMID:14755292]
subset: PSI-MI_slim
synonym: "Refseq" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "[XNZ][A-Z]_[0-9]+|[0-9]+|[XNZ][A-Z]_[0-9]+\\.[0-9]+"
is_a: MI:1096 ! protein sequence databases

[Term]
id: MI:0482
name: rfamƒrnacentral
def: "Rfam is a large collection of multiple sequence alignments and covariance models covering many common non-coding RNA families.\nhttp://www.sanger.ac.uk/Software/Rfam/" [PMID:14755292]
subset: PSI-MI_slim
synonym: "rfam" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "RF[0-9]{5}"
is_a: MI:0683 ! sequence database

[Term]
id: MI:0483
name: rgd
def: "The Rat Genome Database (RGD) curates and integrates rat genetic and genomic data.\nhttp://rgd.mcw.edu/" [PMID:14755292]
subset: PSI-MI_slim
synonym: "RGD" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "[0-9]+"
is_a: MI:1094 ! genome databases

[Term]
id: MI:0484
name: sgd
def: "SGD is a scientific database of the molecular biology and genetics of the yeast Saccharomyces cerevisiae.\nhttp://www.yeastgenome.org/" [PMID:14755292]
subset: PSI-MI_slim
synonym: "Saccharomyces Genome Database" EXACT PSI-MI-alternate []
synonym: "SGD" EXACT PSI-MI-short []
xref: id-validation-regexp: "S[0-9]{9}"
xref: search-url: "http://www.yeastgenome.org/locus/${ac}/overview"
is_a: MI:1094 ! genome databases

[Term]
id: MI:0485
name: uniparc
def: "UniProt Archive (UniParc) is part of UniProt project. It is a non-redundant archive of protein sequences derived from many sources.\nhttp://www.ebi.ac.uk/uniparc/" [PMID:14681372]
subset: PSI-MI_slim
synonym: "UniParc" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "UPI[A-F0-9]{10}"
xref: search-url: "http://www.ebi.uniprot.org/entry/${ac}"
is_a: MI:1097 ! uniprot

[Term]
id: MI:0486
name: uniprot knowledge base
def: "UniProt (Universal Protein Resource) is the world's most comprehensive catalogue of information on proteins. It is a central repository of protein sequence and function created by joining the information contained in Swiss-Prot, TrEMBL, and PIR.\nhttp://www.uniprot.org" [PMID:14681372]
subset: PSI-MI_slim
synonym: "uniprotkb" EXACT PSI-MI-short []
synonym: "UniProtKB" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "[OPQ][0-9][A-Z0-9]{3}[0-9]|[A-NR-Z][0-9]([A-Z][A-Z0-9]{2}[0-9]){1,2}-PRO_[0-9]{10}"
xref: search-url: "http://www.uniprot.org/uniprot/${ac}"
is_a: MI:0461 ! interaction database
is_a: MI:0973 ! imex source
is_a: MI:1097 ! uniprot

[Term]
id: MI:0487
name: wormbase
def: "WormBase is the central worm database that houses the gene reports, locus reports, translation reports, expression pattern data and genome browser.\nhttp://www.wormbase.org/" [PMID:14755292]
subset: PSI-MI_slim
synonym: "WormBase" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "WBGene[0-9]{8}"
is_a: MI:1094 ! genome databases

[Term]
id: MI:0488
name: psi-mi
def: "PSI-MI." [PMID:14755292]
subset: PSI-MI_slim
synonym: "PSI-MI" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "MI:[0-9]{4}"
xref: search-url: "http://www.ebi.ac.uk/ols/ontologies/mi/terms?obo_id=${ac}"
is_a: MI:0444 ! database citation

[Term]
id: MI:0489
name: source database
def: "Database that originally provided the interaction record for exchange purposes." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0444 ! database citation

[Term]
id: MI:0490
name: experiment condition
def: "Describes the location of the experiment.\nOBSOLETE as a full host organisms description is recommended using tax id == -1 as convention to refer to 'in vitro' interaction." [PMID:14755292]
subset: PSI-MI_slim
is_obsolete: true

[Term]
id: MI:0491
name: in silico
def: "Results generated by predictive bioinformatics approaches rather than experimental data.\nOBSOLETE as a full host organisms description is recommended using tax id == -1 as convention to refer to 'in vitro' interaction." [PMID:14755292]
subset: PSI-MI_slim
synonym: "Predictive" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0492
name: in vitro
def: "Experiments performed with participants removed from the cellular environment e.g. cell extracts, isolated proteins.\nOBSOLETE as a full host organisms description is recommended using tax id == -1 as convention to refer to 'in vitro' interaction." [PMID:14755292]
subset: PSI-MI_slim
is_obsolete: true

[Term]
id: MI:0493
name: in vivo
def: "Experiment undertaken within a cellular environment, although this may not be the natural host of the proteins in the study.\nOBSOLETE as a full host organisms description is recommended using tax id == -1 as convention to refer to 'in vitro' interaction." [PMID:14755292]
subset: PSI-MI_slim
is_obsolete: true

[Term]
id: MI:0494
name: in situ
def: "Literally, in place i.e. the protein is in its natural environment during the experiment.\nOBSOLETE as a full host organisms is recommended using tax id == -1 as convention to refer to 'in vitro' interaction." [PMID:14755292]
subset: PSI-MI_slim
is_obsolete: true

[Term]
id: MI:0495
name: experimental role
def: "Role played by the participant within the experiment." [PMID:14755292]
subset: PSI-MI_slim
relationship: part_of MI:0000 ! molecular interaction

[Term]
id: MI:0496
name: bait
def: "Molecule experimentally treated to capture its interacting partners." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0495 ! experimental role

[Term]
id: MI:0497
name: neutral component
def: "Molecule role in an experimental setting that does not have an embedded asymmetry." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0495 ! experimental role

[Term]
id: MI:0498
name: prey
def: "Molecule experimentally identified as being captured by a given bait." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0495 ! experimental role

[Term]
id: MI:0499
name: unspecified role
def: "Role not specified or not applicable to the data." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0495 ! experimental role
is_a: MI:0500 ! biological role

[Term]
id: MI:0500
name: biological role
def: "Physiological role of an interactor in a cell or in vivo environment, which is reproduced in the current experiment." [PMID:14755292]
subset: PSI-MI_slim
relationship: part_of MI:0000 ! molecular interaction

[Term]
id: MI:0501
name: enzyme
def: "Molecule catalyzing a modification on its interacting partner." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0500 ! biological role

[Term]
id: MI:0502
name: enzyme target
def: "Molecule that is the target of its binding partner catalytic activity." [PMID:14755292]
subset: PSI-MI_slim
synonym: "substrate" EXACT PSI-MI-alternate []
is_a: MI:0500 ! biological role

[Term]
id: MI:0503
name: self
def: "Molecule that makes intramolecular interactions." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0495 ! experimental role
is_a: MI:0500 ! biological role

[Term]
id: MI:0505
name: experimental feature
def: "The form of a molecule that was actually used to experimentally demonstrate the interaction, that may differ from the sequence described by the identifying accession number." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0116 ! feature type

[Term]
id: MI:0506
name: over expressed level
def: "A molecule is estimated to be expressed at higher levels than in physiological condition." [PMID:14755292]
subset: PSI-MI_slim
synonym: "over-expressed" EXACT PSI-MI-short []
is_a: MI:0221 ! expression level
is_a: MI:0803 ! expression level alteration

[Term]
id: MI:0507
name: tag
def: "Small molecules, peptides or full proteins that can be used as label as they confer some property that facilitates identification purification and monitoring to the labeled molecule." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0505 ! experimental feature

[Term]
id: MI:0508
name: deacetylase radiometric assay
def: "Measures the release of radiolabelled acetic acid from a pre-labeled molecule." [PMID:14755292]
subset: PSI-MI_slim
synonym: "radiolabeled acetate" EXACT PSI-MI-short []
is_a: MI:0406 ! deacetylase assay

[Term]
id: MI:0509
name: phosphatase homogeneous time resolved fluorescence
def: "Measures quenching of the nonradiative energy transfer between fluorescent long-lifetime lanthanide chelates and different acceptors. Relies on a fluorescence energy donor and acceptor being removed from close proximity on the phosphorylated substrate due to the action of the phosphatase." [PMID:14987100]
subset: PSI-MI_slim
synonym: "homogeneous time-resolved fluorescence" EXACT PSI-MI-alternate []
synonym: "phosphatase HTRF" EXACT PSI-MI-alternate []
synonym: "phosphatase htrf" EXACT PSI-MI-short []
is_a: MI:0434 ! phosphatase assay
is_a: MI:0510 ! homogeneous time resolved fluorescence

[Term]
id: MI:0510
name: homogeneous time resolved fluorescence
def: "Methods based on the exceptionally long fluorescence lifetime characteristics of certain fluorophores, which allows the elimination of the effects of background fluorescence. Uses nonradiative energy transfer or quenching between fluorescent lanthanide chelates and different acceptors to measure reaction rates." [PMID:14987100]
subset: PSI-MI_slim
synonym: "homogeneous time-resolved fluorescence" EXACT PSI-MI-alternate []
synonym: "htrf" EXACT PSI-MI-short []
is_a: MI:0051 ! fluorescence technology

[Term]
id: MI:0511
name: protease homogeneous time resolved fluorescence
def: "Measures quenching of the nonradiative energy transfer between fluorescent long-lifetime lanthanide chelates and different acceptors. Fluorescence donor and acceptor are on the same peptide molecule and separated by the action of the protease." [PMID:14987100]
subset: PSI-MI_slim
synonym: "Protease HTRF" EXACT PSI-MI-alternate []
synonym: "protease htrf" EXACT PSI-MI-short []
is_a: MI:0435 ! protease assay
is_a: MI:0510 ! homogeneous time resolved fluorescence

[Term]
id: MI:0512
name: zymography
def: "Samples run on a gelatine containing gels under non-reducing condition, gels then incubated under conditions in which the enzyme is active. Gels are stained with coomasie and gelatine-free regions of the gel taken as a measure of enzyme activity." [PMID:2071592]
subset: PSI-MI_slim
is_a: MI:0435 ! protease assay

[Term]
id: MI:0513
name: collagen film assay
def: "Measures the amount of radiolabel released into the medium when enzyme is added onto a film of isotope-labelled collagen." [PMID:6247938]
subset: PSI-MI_slim
is_a: MI:0435 ! protease assay

[Term]
id: MI:0514
name: in gel phosphatase assay
def: "Substrate pre-radiolabelled either synthetically or through the action of a kinase transferring an isotope of phosphate from a nucleotide. Substrate then exposed to phosphate under assay conditions. Substrate isolated by gel electrophoresis and loss of radiolabelling confirmed by autoradiography." [PMID:14755292]
subset: PSI-MI_slim
synonym: "in gel phosphatase" EXACT PSI-MI-short []
is_a: MI:0434 ! phosphatase assay

[Term]
id: MI:0515
name: methyltransferase assay
def: "Measures the catalysis of the transfer of a methyl group to an acceptor molecule." [PMID:14755292]
subset: PSI-MI_slim
synonym: "methyltransferase as" EXACT PSI-MI-short []
is_a: MI:0415 ! enzymatic study

[Term]
id: MI:0516
name: methyltransferase radiometric assay
def: "Measures the transfer of a radiolabelled methyl group of a donor, for example S-adenosyl-L-methionine (SAM) to a carboxyl group of an acceptor." [PMID:14755292]
subset: PSI-MI_slim
synonym: "radiolabeled methyl" EXACT PSI-MI-short []
is_a: MI:0515 ! methyltransferase assay

[Term]
id: MI:0517
name: radiolabel
def: "A radiolabelled molecule has radio isotopes among its constituent atoms that can be used to identify, localize or quantify the full molecule." [PMID:14755292]
subset: PSI-MI_slim
synonym: "radiolabeled" EXACT PSI-MI-alternate []
synonym: "radiolabelled" EXACT PSI-MI-short []
is_a: MI:0253 ! isotope label

[Term]
id: MI:0518
name: flag tag
def: "The protein of interest is expressed as a fusion to the peptide DYKDDDDKV for which antibodies are commercially available. Sometimes multiple copies of the peptide are fused in tandem." [PMID:14755292]
subset: PSI-MI_slim
synonym: "DYKDDDDKV epitope tag" EXACT PSI-MI-alternate []
synonym: "FLAG" EXACT PSI-MI-alternate []
synonym: "FLAG-tagged" EXACT PSI-MI-alternate []
is_a: MI:0507 ! tag

[Term]
id: MI:0519
name: glutathione s tranferase tag
def: "The protein is expressed and purified as a fusion to the glutathione S-tranferase protein." [PMID:14755292]
subset: PSI-MI_slim
synonym: "glutathione S-tranferase tag" EXACT PSI-MI-alternate []
synonym: "gst tag" EXACT PSI-MI-short []
is_a: MI:0365 ! enzyme tag

[Term]
id: MI:0520
name: ha tag
def: "The protein of interest is expressed as a fusion to the peptide YPYDVPDYA (a fragment of the influenza hemagglutinin protein) for which antibodies are commercially available." [PMID:14755292]
subset: PSI-MI_slim
synonym: "YPYDVPDYA epitope tag" EXACT PSI-MI-alternate []
is_a: MI:0507 ! tag

[Term]
id: MI:0521
name: his tag
def: "The protein of interest is expressed as a fusion to a poly-His tail. This permits purification by chromatography over a metal column or by binding to commercially available anti poly-His antibodies." [PMID:14755292]
subset: PSI-MI_slim
synonym: "6-His-tag" EXACT PSI-MI-alternate []
synonym: "Hexa-His-tag" EXACT PSI-MI-alternate []
synonym: "Histidine-tag" EXACT PSI-MI-alternate []
is_a: MI:0507 ! tag

[Term]
id: MI:0522
name: myc tag
def: "The protein of interest is expressed as a fusion to the peptide EUKLISEED (a fragment of the Myc oncogene protein) for which antibodies are commercially available. Sometimes multiple copies of the peptide are fused in tandem." [PMID:14755292]
subset: PSI-MI_slim
synonym: "EUKLISEED epitope tag" EXACT PSI-MI-alternate []
is_a: MI:0507 ! tag

[Term]
id: MI:0523
name: t7 tag
def: "The protein of interest is expressed as a fusion to the peptide MASMTGGQQMG for which antibodies are commercially available." [PMID:14755292]
subset: PSI-MI_slim
synonym: "MASMTGGQQMG epitope tag" EXACT PSI-MI-alternate []
is_a: MI:0507 ! tag

[Term]
id: MI:0524
name: calmodulin binding peptide plus protein a tag
def: "Tag encoding a calmodulin binding peptide, a TEV cleavage site, and the Staphylococcus aureus Protein A fused to a target protein. The tag allows two purification steps ensuring a highly selective purification of the tagged protein." [PMID:14755292]
subset: PSI-MI_slim
synonym: "CBP-ProtA tagged" EXACT PSI-MI-alternate []
synonym: "tap tagged" EXACT PSI-MI-short []
is_a: MI:0677 ! tandem tag

[Term]
id: MI:0525
name: v5 tag
def: "The protein of interest is expressed as a fusion to the peptide GKPIPNPLLGLDST for which antibodies are commercially available." [PMID:14755292]
subset: PSI-MI_slim
synonym: "GKPIPNPLLGLDST epitope tag" EXACT PSI-MI-alternate []
is_a: MI:0507 ! tag

[Term]
id: MI:0526
name: n-acetyl-lysine
def: "Residue modification.\nOBSOLETE remap to MOD:00723." [PMID:14755292, RESID:AA0048, RESID:AA0055]
synonym: "acetyllysine" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0527
name: adp ribosylated residue
def: "Residue modification.\nOBSOLETE remap to MOD:00752." [PMID:14755292]
synonym: "adp-ribosylated" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0528
name: omega-n-(adp-ribosyl)-arginine
def: "Residue modification.\nOBSOLETE remap to MOD:00177." [PMID:14755292, RESID:AA0168]
synonym: "(S)-2-amino-5-([imino([adenosine 5'-(trihydrogen diphosphate) 5'->5'-ester with alpha-D-ribofuranosyl]amino)methyl]amino)pentanoic acid" EXACT PSI-MI-alternate []
synonym: "adp-ribosylarginine" EXACT PSI-MI-short []
synonym: "N(omega)-[alpha-D-ribofuranoside 5'->5'-ester with adenosine 5'-(trihydrogen diphosphate)]-L-arginine" EXACT PSI-MI-alternate []
synonym: "N(omega)-alpha-D-ribofuranosyl-L-arginine 5'->5'-ester with adenosine 5'-(trihydrogen diphosphate)" EXACT PSI-MI-alternate []
synonym: "omega-N-(ADP-ribosyl)-L-arginine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0529
name: s-(adp-ribosyl)-cysteine
def: "Residue modification.\nOBSOLETE remap to MOD:00178." [PMID:14755292, RESID:AA0169]
synonym: "(R)-2-amino-3-([adenosine 5'-(trihydrogen diphosphate) 5'->5'-ester with alpha-D-ribofuranosyl]sulfanyl)propanoic acid" EXACT PSI-MI-alternate []
synonym: "adp-ribosylcysteine" EXACT PSI-MI-short []
synonym: "S-(ADP-ribosyl)-L-cysteine" EXACT PSI-MI-alternate []
synonym: "S-alpha-D-ribofuranosyl-L-cysteine 5'->5'-ester with adenosine 5'-(trihydrogen diphosphate)" EXACT PSI-MI-alternate []
synonym: "S-L-cysteine alpha-D-ribofuranoside 5'->5'-ester with adenosine 5'-(trihydrogen diphosphate)" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0530
name: glutamyl-5-poly(adp-ribose)
def: "Residue modification.\nOBSOLETE remap to MOD:00300." [PMID:14755292, RESID:AA0295]
synonym: "(S)-2-amino-5-poly[2'-adenosine 5'-(trihydrogen diphosphate) 5'->5'-ester with 1alpha-D-ribofuranosyl]oxy-5-oxopentanoic acid" EXACT PSI-MI-alternate []
synonym: "adp-ribosylglutamate" EXACT PSI-MI-short []
synonym: "L-glutamyl-5-poly(ADP-ribose)" EXACT PSI-MI-alternate []
synonym: "L-isoglutamyl-poly(ADP-ribose)" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0531
name: o-(adp-ribosyl)-serine
def: "Residue modification.\nOBSOLETE remap to MOD:00242." [PMID:14755292, RESID:AA0237]
synonym: "(S)-2-amino-3-([adenosine 5'-(trihydrogen diphosphate) 5'->5'-ester with alpha-D-ribofuranosyl]oxy)-propanoic acid Formula" EXACT PSI-MI-alternate []
synonym: "adp-ribosylserine" EXACT PSI-MI-short []
synonym: "O-(ADP-ribosyl)-L-serine" EXACT PSI-MI-alternate []
synonym: "O3-(ADP-ribosyl)-L-serine" EXACT PSI-MI-alternate []
synonym: "O3-[alpha-D-ribofuranoside 5'->5'-ester with adenosine 5'-(trihydrogen diphosphate)]-L-serine" EXACT PSI-MI-alternate []
synonym: "O3-alpha-D-ribofuranosyl-L-serine 5'->5'-ester with adenosine 5'-(trihydrogen diphosphate)" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0532
name: n4-(adp-ribosyl)-asparagine
def: "Residue modification.\nOBSOLETE remap to MOD:00236." [PMID:14755292, RESID:AA0231]
synonym: "(S)-2-amino-4-([adenosine 5'-(trihydrogen diphosphate) 5'->5'-ester with alpha-D-ribofuranosyl]amino)-4-oxobutanoic acid" EXACT PSI-MI-alternate []
synonym: "adpribosylasparagine" EXACT PSI-MI-short []
synonym: "N4-(ADP-ribosyl)-L-asparagine" EXACT PSI-MI-alternate []
synonym: "N4-[alpha-D-ribofuranoside 5'->5'-ester with adenosine 5'-(trihydrogen diphosphate)]-L-asparagine" EXACT PSI-MI-alternate []
synonym: "N4-alpha-D-ribofuranosyl-L-asparagine 5'->5'-ester with adenosine 5'-(trihydrogen diphosphate)" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0533
name: glycosylated residue
def: "Residue modification.\nOBSOLETE remap to MOD:00693." [PMID:14755292]
is_obsolete: true

[Term]
id: MI:0534
name: glycosyl-cysteine
def: "Residue modification.\nOBSOLETE remap to MOD:00131." [PMID:14755292, RESID:AA0122]
synonym: "S-glycosyl-L-cysteine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0535
name: glycosyl-serine
def: "Residue modification.\nOBSOLETE remap to MOD:00163." [PMID:14755292, RESID:AA0154]
synonym: "O-glycosyl-L-serine" EXACT PSI-MI-alternate []
synonym: "O3-glycosyl-L-serine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0536
name: glycosyl-threonine
def: "Residue modification.\nOBSOLETE remap to MOD:00164." [PMID:14755292, RESID:AA0155]
synonym: "O-glycosyl-L-threonine" EXACT PSI-MI-alternate []
synonym: "O3-glycosyl-L-threonine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0537
name: omega-n-glycosyl-arginine
def: "Residue modification.\nOBSOLETE remap to MOD:00332." [PMID:14755292, RESID:AA0327]
synonym: "glycosylarginine" EXACT PSI-MI-short []
synonym: "omega-N-glycosyl-L-arginine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0538
name: n4-glycosyl-asparagine
def: "Residue modification.\nOBSOLETE remap to MOD:00160." [PMID:14755292, RESID:AA0151]
synonym: "glycosylasparagine" EXACT PSI-MI-short []
synonym: "N4-glycosyl-L-asparagine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0539
name: gpi anchor residue
def: "Residue modification.\nOBSOLETE remap to MOD:00818." [PMID:14755292]
is_obsolete: true

[Term]
id: MI:0540
name: gpi-anchor amidated alanine
def: "Residue modification.\nOBSOLETE remap to MOD:00172." [PMID:14755292, RESID:AA0163]
synonym: "gpi-alanine" EXACT PSI-MI-short []
synonym: "N-alanyl-glycosylphosphatidylinositolethanolamine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0541
name: gpi-anchor amidated asparagine
def: "Residue modification.\nOBSOLETE remap to MOD:00167." [PMID:14755292, RESID:AA0158]
synonym: "gpi-asparagine" EXACT PSI-MI-short []
synonym: "N-asparaginyl-glycosylphosphatidylinositolethanolamine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0542
name: gpi-anchor amidated aspartate
def: "Residue modification.\nOBSOLETE remap to MOD:00168." [PMID:14755292, RESID:AA0159]
synonym: "gpi-aspartate" EXACT PSI-MI-short []
synonym: "N-aspartyl-glycosylphosphatidylinositolethanolamine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0543
name: gpi-anchor amidated cysteine
def: "Residue modification.\nOBSOLETE remap to MOD:00169." [PMID:14755292, RESID:AA0160]
synonym: "gpi-cysteine" EXACT PSI-MI-short []
synonym: "N-cysteinyl-glycosylphosphatidylinositolethanolamine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0544
name: gpi-anchor amidated glycine
def: "Residue modification.\nOBSOLETE remap to MOD:00170." [PMID:14755292, RESID:AA0161]
synonym: "gpi-glycine" EXACT PSI-MI-short []
synonym: "N-glycyl-glycosylphosphatidylinositolethanolamine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0545
name: gpi-anchor amidated serine
def: "Residue modification.\nOBSOLETE remap to MOD:00171." [PMID:14755292, RESID:AA0162]
synonym: "gpi-serine" EXACT PSI-MI-short []
synonym: "N-seryl-glycosylphosphatidylinositolethanolamine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0546
name: gpi-anchor amidated threonine
def: "Residue modification.\nOBSOLETE remap to MOD:00173." [PMID:14755292, RESID:AA0164]
synonym: "gpi-threonine" EXACT PSI-MI-short []
synonym: "N-threonyl-glycosylphosphatidylinositolethanolamine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0547
name: s-prenyl-cysteine
def: "Residue modification.\nOBSOLETE remap to MOD:01110." [PMID:14755292]
synonym: "prenylcysteine" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0548
name: methylated-lysine
def: "Residue modification.\nOBSOLETE remap to MOD:00663." [PMID:14755292, RESID:AA0074, RESID:AA0075, RESID:AA0076]
synonym: "methylatedlysine" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0549
name: alkylated cysteine
def: "Artificial residue modification enabling studies of cysteine binding status.\nOBSOLETE remap to MOD:00660." [PMID:15325307]
is_obsolete: true

[Term]
id: MI:0550
name: gamma-carboxyglutamic acid
def: "Residue modification.\nOBSOLETE remap to MOD:00041." [PMID:14755292, RESID:AA0032]
synonym: "(S)-3-amino-1,1,3-propanetricarboxylic acid" EXACT PSI-MI-alternate []
synonym: "1-carboxyglutamic acid [misnomer]" EXACT PSI-MI-alternate []
synonym: "4-carboxyglutamic acid" EXACT PSI-MI-alternate []
synonym: "carboxyglutamic acid" EXACT PSI-MI-short []
synonym: "L-gamma-carboxyglutamic acid" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0551
name: nitro-tyrosine
def: "Residue modification.\nOBSOLETE remap to MOD:00461." [PMID:15657065, PMID:9636206]
synonym: "nitrated tyrosine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0552
name: s-nitrosyl-cysteine
def: "Residue modification.\nOBSOLETE remap to MOD:00235." [PMID:14755292, RESID:AA0230]
synonym: "(R)-2-amino-3-nitrososulfanyl-propanoic acid" EXACT PSI-MI-alternate []
synonym: "L-cysteine nitrite ester" EXACT PSI-MI-alternate []
synonym: "nitrosylcysteine" EXACT PSI-MI-short []
synonym: "S-nitrosocysteine" EXACT PSI-MI-alternate []
synonym: "S-nitrosyl-L-cysteine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0553
name: o4'-sulfo-tyrosine
def: "Residue modification.\nOBSOLETE remap to MOD:00181." [PMID:14755292, RESID:AA0172]
synonym: "(S)-2-amino-3-(4-sulfooxyphenyl)propanoic acid" EXACT PSI-MI-alternate []
synonym: "2-amino-3-(4-hydroxyphenyl)propanoic acid 4'-sulfate" EXACT PSI-MI-alternate []
synonym: "O4'-sulfo-L-tyrosine" EXACT PSI-MI-alternate []
synonym: "O4-sulfotyrosine" EXACT PSI-MI-alternate []
synonym: "sulfotyrosine" EXACT PSI-MI-short []
synonym: "tyrosine sulfate" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0554
name: sumoylated lysine
def: "Residue modification due to a cross-link between a lysine and a glycine from the sumo (Small Ubiquitin-related MOdifier) protein.\nOBSOLETE remap to MOD:01149." [PMID:12612601, RESID:AA0125]
synonym: "(S)-2-amino-6-[(aminoacetyl)amino]hexanoic acid" EXACT PSI-MI-alternate []
synonym: "N6-glycyl-L-lysine" EXACT PSI-MI-alternate []
synonym: "N6-glycyllysine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0555
name: phospho-histidine
def: "Residue modification.\nOBSOLETE remap to MOD:00890." [PMID:14755292, RESID:AA0035, RESID:AA0036]
synonym: "phosphoshistidine" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0556
name: transglutamination reaction
def: "Gln-Lys cross-link catalyzed by a transglutaminase." [PMID:14755292, RESID:AA0124]
subset: PSI-MI_slim
synonym: "transglutamination" EXACT PSI-MI-short []
is_a: MI:0195 ! covalent binding

[Term]
id: MI:0557
name: adp ribosylation reaction
def: "Involves the addition of one or more ADP-ribose moieties to proteins. Reaction that can affect Arg, Cys, Glu, Arg and Asn residues." [GO:0006471, PMID:14755292, RESID:AA0168, RESID:AA0169, RESID:AA0231, RESID:AA0237, RESID:AA0295]
subset: PSI-MI_slim
synonym: "adp ribosylation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction

[Term]
id: MI:0558
name: deglycosylation reaction
def: "Reaction catalyzed by PNGase, a deglycosylating enzyme that promotes the hydrolysis of the beta-aspartylglycosylamine bond of aspargine-linked glycopeptides and glycoproteins." [GO:0006517, PMID:15670854]
subset: PSI-MI_slim
synonym: "deglycosylation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction

[Term]
id: MI:0559
name: glycosylation reaction
def: "The covalent attachment of a glycosyl residue to one or more monomeric units in a polypeptide, polynucleotide, polysaccharide, or other biological polymer. Reaction that can affect Ser, Thr, Cys, Arg, and Asn residues. This reaction is known to be reversible in the case of Asn substrate." [GO:0043413, PMID:14755292, RESID:AA0122, RESID:AA0151, RESID:AA0154, RESID:AA0155, RESID:AA0327]
subset: PSI-MI_slim
synonym: "glycosylation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction

[Term]
id: MI:0560
name: myristoylated residue
def: "Residue modification.\nOBSOLETE remap to MOD:00438." [PMID:14755292]
synonym: "myristoylated aa" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0561
name: palmitoylated residue
def: "Residue modification.\nOBSOLETE remap to MOD:00440." [PMID:14755292]
synonym: "palmitoylated aa" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0562
name: methylated alanine
def: "Residue modification.\nOBSOLETE remap to MOD:00665." [PMID:14755292, RESID:AA0061, RESID:AA0062]
is_obsolete: true

[Term]
id: MI:0563
name: methylated arginine
def: "Residue modification.\nOBSOLETE remap to MOD:00658." [PMID:14755292, RESID:AA0068, RESID:AA0069]
is_obsolete: true

[Term]
id: MI:0564
name: omega-n-methyl-arginine
def: "Residue modification.\nOBSOLETE remap to MOD:00078." [PMID:14755292, RESID:AA0069]
synonym: "(S)-2-amino-5-[(imino(methylamino)methyl)amino]pentanoic acid" EXACT PSI-MI-alternate []
synonym: "methylarginine" EXACT PSI-MI-short []
synonym: "NG-methylarginine;" EXACT PSI-MI-alternate []
synonym: "omega-N-methyl-L-arginine" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0565
name: neddylated lysine
def: "Residue modification due to a cross-link between a lysine and a glycine from the Nedd8 protein family.\nOBSOLETE remap to MOD:01150." [PMID:111]
is_obsolete: true

[Term]
id: MI:0566
name: sumoylation reaction
def: "Reversible reaction that create a covalent bond between a C-terminus G of an ubiquitine like sumo protein and a K residue of the target." [GO:0016925, PMID:15985640]
subset: PSI-MI_slim
synonym: "sumoylation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction

[Term]
id: MI:0567
name: neddylation reaction
def: "Reversible reaction that create a covalent bond between a Glycine residue of an ubiquitine like NEDD8 protein and a lysine residue of the target." [GO:0045116, PMID:16127432]
subset: PSI-MI_slim
synonym: "neddylation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction

[Term]
id: MI:0568
name: desumoylation reaction
def: "Cleavage of the G-K bond and release of the SUMO ubiquitin like proteins." [GO:0016926, PMID:15985640]
subset: PSI-MI_slim
synonym: "desumoylation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction

[Term]
id: MI:0569
name: deneddylation reaction
def: "Cleavage of the G-K bond and release of the NEDD8 ubiquitin like proteins. Deneddylation, which removes the NEDD8 moiety, requires the isopeptidase activity of the COP9 signalosome." [GO:0000338, PMID:16127432]
subset: PSI-MI_slim
synonym: "deneddylation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction

[Term]
id: MI:0570
name: protein cleavage
def: "Covalent modification of a polypeptide occuring during its maturation or its proteolytic degradation." [PMID:14744292]
subset: PSI-MI_slim
is_a: MI:0194 ! cleavage reaction

[Term]
id: MI:0571
name: mrna cleavage
def: "Any process by which a pre-mRNA or mRNA molecule is cleaved at specific sites or in a regulated manner." [GO:0006379, PMID:14681407]
subset: PSI-MI_slim
is_a: MI:0902 ! rna cleavage

[Term]
id: MI:0572
name: dna cleavage
def: "Covalent bond breakage of a DNA molecule leading to the formation of smaller fragments." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0910 ! nucleic acid cleavage

[Term]
id: MI:0573
name: mutation disrupting interaction
def: "Region of a molecule whose mutation or deletion totally disrupts an interaction strength or rate (in the case of interactions inferred from enzymatic reaction).." [PMID:14755292]
subset: PSI-MI_slim
synonym: "mutation disrupting" EXACT PSI-MI-short []
is_a: MI:0119 ! mutation decreasing interaction

[Term]
id: MI:0574
name: digital object identifier
def: "Identifier of a publication prior to pubmed indexing." [PMID:14755292]
subset: PSI-MI_slim
synonym: "doi" EXACT PSI-MI-short []
xref: id-validation-regexp: "\\d+.\\d+/[a-zA-Z0-9\\.\\:]+"
xref: search-url: "http://dx.doi.org/${ac}"
is_a: MI:0445 ! literature database

[Term]
id: MI:0575
name: alliance for cellular signaling
def: "Alliance for Cellular Signaling (AfCS -Nature) store yeast 2-hybrid Interaction data and expression data. Information and data are freely available to all.\nhttp://www.signaling-gateway.org" [PMID:14755292]
subset: PSI-MI_slim
synonym: "AfCS" EXACT PSI-MI-alternate []
synonym: "afcs" EXACT PSI-MI-short []
xref: id-validation-regexp: "[0-9]+"
xref: search-url: "http://www.signaling-gateway.org/data/Y2H/cgi-bin/y2h_int.cgi?id=${ac}"
is_a: MI:0461 ! interaction database
is_a: MI:0489 ! source database

[Term]
id: MI:0576
name: structural proximity
def: "Method to identify domain-domain interactions within the same resolved structure. Domains are first projected onto a pdb structure and then the distance between all pairs of residues in different domains are calculated. When the distance between 2 residues is below the non covalent bond threshold, the corresponding pair of domains is predicted to interact." [PMID:15353450]
subset: PSI-MI_slim
is_a: MI:0577 ! feature prediction from structure

[Term]
id: MI:0577
name: feature prediction from structure
def: "Group of method taking advantage of 3D structure to calculate and infer the feature of interacting molecules." [PMID:14755292]
subset: PSI-MI_slim
synonym: "feature struct pred" EXACT PSI-MI-short []
is_a: MI:0660 ! feature prediction

[Term]
id: MI:0578
name: maltose binding protein tag
def: "The protein is expressed and purified as a fusion to the glutathione maltose-binding protein (MBP). The MBP-fusion protein can be purified by affinity chromatography using an amylose resin." [PMID:14755292]
subset: PSI-MI_slim
synonym: "maltose binding protein tag" EXACT PSI-MI-alternate []
synonym: "mbp tag" EXACT PSI-MI-short []
is_a: MI:0240 ! fusion protein

[Term]
id: MI:0579
name: electron donor
def: "Any molecule that is able to transfer an electron to another chemical species." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0918 ! donor

[Term]
id: MI:0580
name: electron acceptor
def: "Molecule to which an electron may be transferred from an electron donor." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0919 ! acceptor

[Term]
id: MI:0581
name: suppressor gene
def: "A gene whose genetic perturbation suppresses the phenotype resulting from a different genetic perturbation." [PMID:14755292]
subset: PSI-MI_slim
synonym: "suppressor" EXACT PSI-MI-short []
is_a: MI:0495 ! experimental role

[Term]
id: MI:0582
name: suppressed gene
def: "A gene whose genetic perturbation phenotype is suppressed by a different genetic perturbation." [PMID:14755292]
subset: PSI-MI_slim
synonym: "suppressed" EXACT PSI-MI-short []
is_a: MI:0495 ! experimental role

[Term]
id: MI:0583
name: fluorescence donor
def: "Fluorophore which emits electromagnetic radiation of given wavelength." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:2334 ! luminescence donor

[Term]
id: MI:0584
name: fluorescence acceptor
def: "Fluorophore able to absorb the electromagnetic radiation at given wavelength from a specific donor fluorophore, then re-emiting its own characteristic fluorescence." [PMID:14755292]
subset: PSI-MI_slim
synonym: "fluorescence accept" EXACT PSI-MI-short []
is_a: MI:2335 ! luminescence acceptor

[Term]
id: MI:0585
name: intenz
def: "IntEnz is the name for the Integrated relational Enzyme database and is the official version of the Enzyme Nomenclature. The Enzyme Nomenclature comprises recommendations of the Nomenclature Committee of the International Union of Bio chemistry and Molecular Biology (NC-IUBMB) on the nomenclature and classification of enzyme-catalysed reactions. IntEnz is supported by NC-IUBMB and contains enzyme data curated and approved by this committee. The database IntEnz is available at.\nhttp://www.ebi.ac.uk/intenz" [PMID:14681451]
subset: PSI-MI_slim
xref: id-validation-regexp: "[0-6]{1}\\.(\\d+|-)\\.(\\d+|-)\\.(\\d+|-)"
xref: search-url: "http://www.ebi.ac.uk/intenz/query?cmd=Search&q=${ac}&t=exact&fields=ec"
is_a: MI:0461 ! interaction database

[Term]
id: MI:0586
name: inhibitor
def: "Molecule inhibiting an interaction by interacting with one or more of its participants." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:2274 ! regulator

[Term]
id: MI:0587
name: inhibited
def: "Molecule being identified as target of an inhibitor.\nOBSOLETE as term is deprecated to describe the target of an inhibitor that can have any other biological role." [PMID:14755292]
subset: PSI-MI_slim
is_obsolete: true

[Term]
id: MI:0588
name: three hybrid
def: "Group of methods based on complementation assay where a third participant is shown to be necessary for the binding of a given bait prey pair. The molecule fused to the DNA binding domain is the bait, that fused to the transcriptional activator is the prey." [PMID:14755292]
subset: PSI-MI_slim
synonym: "3 hybrid" EXACT PSI-MI-short []
synonym: "3-hybrid" EXACT PSI-MI-alternate []
synonym: "tri hybrid" EXACT PSI-MI-alternate []
synonym: "tri-hybrid assay" EXACT PSI-MI-alternate []
is_a: MI:0232 ! transcriptional complementation assay

[Term]
id: MI:0589
name: in vitro translated protein
def: "Protein sample collected by in vitro translation of its mRNA taking advantage of purified translation machinery." [PMID:14755292]
subset: PSI-MI_slim
synonym: "in vitro translated" EXACT PSI-MI-short []
is_a: MI:0342 ! sample process

[Term]
id: MI:0590
name: attribute name
def: "Collection of topics describing the free text stored as an attribute value." [PMID:14755292]
subset: Drugable
subset: PSI-MI_slim
synonym: "CvTopic" EXACT PSI-MI-alternate []
relationship: part_of MI:0000 ! molecular interaction

[Term]
id: MI:0591
name: experiment description
def: "The experimental condition text description, should contain information about the organisms hosting the interaction." [PMID:14755292]
subset: PSI-MI_slim
synonym: "experiment descripti" EXACT PSI-MI-short []
is_a: MI:0665 ! experiment attribute name

[Term]
id: MI:0592
name: ipfam
def: "Web resource that allows the investigation of protein interactions in the Protein Data Bank structures at the level of Pfam domains and amino acid residues. iPfam is available on the Web for browsing at.\nhttp://www.sanger.ac.uk/Software/Pfam/iPfam/" [PMID:15353450]
subset: PSI-MI_slim
is_a: MI:0447 ! feature database

[Term]
id: MI:0593
name: translocation
def: "Xref pointing to a GO process term describing the start and end location of a migrating molecule, for instance see GO:0006611, 'protein-nucleus export'." [PMID:14681407]
subset: PSI-MI_slim
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:0594
name: translocation start
def: "Xref pointing to a GO compartment term describing the start location of a migrating molecule." [PMID:14681407]
subset: PSI-MI_slim
is_a: MI:0593 ! translocation

[Term]
id: MI:0595
name: translocation end
def: "Xref pointing to a GO compartment term describing the end location of a migrating molecule." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0593 ! translocation

[Term]
id: MI:0596
name: experimental form description
def: "Free text description of all the tags and artificial process undergone by a molecule during an experiment." [PMID:14755292]
subset: PSI-MI_slim
synonym: "experimental form de" EXACT PSI-MI-short []
is_a: MI:0666 ! participant attribute name

[Term]
id: MI:0597
name: feature description
def: "The feature text description may include information about the feature detection method." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0668 ! feature attribute name

[Term]
id: MI:0598
name: feature constraint
def: "The feature constraint free text will specificity whether a biological feature is shown to be possible (just observed) or required (experimentally demonstrated to be necessary for an interaction)." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0668 ! feature attribute name

[Term]
id: MI:0599
name: figure legend
def: "Text pointing to a specific paper figure legend where the experimental evidences for an interaction are to be found." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:0665 ! experiment attribute name

[Term]
id: MI:0600
name: conditional synthetic lethal nutrition-sensitivity
def: "Two silent mutations show a nutrition sensitive lethal phenotype when they co-occur on the same cell.\nOBSOLETE: remap to CV intraction type 'synthetic interaction' MI:0794 and external CV for phenotype description." [PMID:15608217]
subset: PSI-MI_slim
synonym: "nutrition synt letal" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0601
name: sequence ontology
def: "The Sequence Ontology (SO) is a structured controlled vocabulary for the parts of a genomic annotation. SO provides a common set of terms and definitions that will facilitate the exchange, analysis and management of genomic data." [PMID:15892872]
subset: PSI-MI_slim
synonym: "so" EXACT PSI-MI-short []
xref: id-validation-regexp: "SO:[0-9]{7}"
is_a: MI:0447 ! feature database
is_a: MI:0473 ! participant database

[Term]
id: MI:0602
name: chemical footprinting
def: "Binding sites are identified by altered reactivity of a complex to a chemical treatment compared to the unbound molecules. Residues in close contact with the binding partner are protected from chemical modification. When these chemicals are administrated to intact cells, the pattern of protection from the probes identifies the location of DNA-protein or protein-protein interactions in vivo." [PMID:8238889]
subset: PSI-MI_slim
synonym: "chemical footprint" EXACT PSI-MI-short []
is_a: MI:0417 ! footprinting

[Term]
id: MI:0603
name: dimethylsulphate footprinting
def: "Dimethylsulphate (DMS) is the most commonly used chemical to study DNA-protein interactions. DMS induces methylation of guanine residues so DNA interaction with protein binding to AT rich sequences or to the phosphate backbone may be not detected by DMS footprinting. However as DMS diffuses across membrane it can also be used for in vivo footprinting. The experiment involves the treatment with DMS of two DNA samples with identical sequence, one protein bound and the other naked. The two samples are treated with piperidine to induce chemical cleavage of the DMS modified guanine residues followed by digestion with restriction enzymes. Once labelled the samples are run in parallel on a gel to visualize the pattern of nested fragments sharing a common end generated by restriction enzyme(or PCR primer extension) and a variable end guanine dependent. The missing bands of the protein bound sample correspond to the guanine residues protected from modification by an interaction." [PMID:8238889]
subset: PSI-MI_slim
synonym: "dms footprinting" EXACT PSI-MI-short []
is_a: MI:0602 ! chemical footprinting

[Term]
id: MI:0604
name: potassium permanganate footprinting
def: "Potassium permanganate bind to single-stranded pyrimidine residues, it is commonly used to detect promoters opening regions in vivo. KMnO4 treatment of cells, followed by treatment with piperidine, followed by either PCR and/or acrylamide gel electrophoresis allows detection of interaction between transcription factor and the DNA sequence under their control." [PMID:8238889]
subset: PSI-MI_slim
synonym: "k-mn-04 footprinting" EXACT PSI-MI-short []
is_a: MI:0602 ! chemical footprinting

[Term]
id: MI:0605
name: enzymatic footprinting
def: "Binding sites are identified by altered reactivity of a complex to an enzymatic probe compared to the unbound molecules. Residues in close contact with the binding partner are protected from cleavage by the enzyme. When these enzymes are administrated to intact cells, the pattern of protection from the probes identifies the location of DNA-protein or protein-protein interactions in vivo." [PMID:8238889]
subset: PSI-MI_slim
synonym: "enzymatic footprint" EXACT PSI-MI-short []
is_a: MI:0417 ! footprinting

[Term]
id: MI:0606
name: DNase I footprinting
def: "Deoxyribonuclease I (DNase I) does not have high specificity for given sequences or residues, thus footprinting with DNase I permits the exact delineation of the protein-DNA binding site. Moreover DNase I, can be used for in vivo footprinting by treating intact cells with permeabilising drugs. In this latter case DNase I in vivo footprinting allow studies of the chromatin structure in genomic DNA." [PMID:8238889]
subset: PSI-MI_slim
synonym: "dnase 1 footprinting" EXACT PSI-MI-short []
synonym: "DNase I protection" RELATED []
is_a: MI:1183 ! nuclease footprinting

[Term]
id: MI:0607
name: small nuclear rna
def: "These RNA molecules are relatively short (less than 200 nucleotides each), and there are five of them (U1, U2, U4, U5, and U6) involved in the major form of pre-mRNA splicing. Known as snRNAs (small nuclear RNAs), each is complexed with at least seven protein subunits to form a snRNP (small nuclear ribonucleoprotein). These snRNPs form the core of the spliceosome." [PMID:14755292]
subset: PSI-MI_slim
synonym: "snRNA" EXACT PSI-MI-alternate []
synonym: "snrna" EXACT PSI-MI-short []
is_a: MI:0320 ! ribonucleic acid

[Term]
id: MI:0608
name: ribosomal rna
def: "RNA that is transcribed from the DNA of the nucleolus and is found, together with characteristic proteins, in the ribosomes." [PMID:14755292]
subset: PSI-MI_slim
synonym: "rRNA" EXACT PSI-MI-alternate []
synonym: "rrna" EXACT PSI-MI-short []
is_a: MI:0320 ! ribonucleic acid

[Term]
id: MI:0609
name: small nucleolar rna
def: "The small nucleolar RNAs, are stable RNA contained in the nucleoli and these RNAs exist as snoRNA: protein complexes called snoRNPs (also called 'snorps'). The snoRNPs function is in the maturation of ribosomal RNA and other RNAs, by: creating two types of modified nucleotides, (2'-O-methylated nucleotides and pseudouridine), and mediating endonucleolytic cleavages of pre-rRNA." [PMID:14755292]
subset: PSI-MI_slim
synonym: "snoRNA" EXACT PSI-MI-alternate []
synonym: "snorna" EXACT PSI-MI-short []
is_a: MI:0320 ! ribonucleic acid

[Term]
id: MI:0610
name: small interfering rna
def: "Ribonucleic acid used in RNAi study. These RNA have the reverse complementary sequence of a target gene's mRNA transcript and inhibit its expression." [PMID:10542148]
subset: PSI-MI_slim
synonym: "dicer RNA" EXACT PSI-MI-alternate []
synonym: "micro RNA" EXACT PSI-MI-alternate []
synonym: "siRNA" EXACT PSI-MI-alternate []
synonym: "sirna" EXACT PSI-MI-short []
is_a: MI:0320 ! ribonucleic acid

[Term]
id: MI:0611
name: signal recognition particle rna
def: "Small (300 nucleotides) stable RNAs transcribed by RNA pol III that are part of the signal-recognition particle (SRP). This particle comprises one RNA and six proteins bound to the RNA. SRP function is to assist secretory proteins sorting in the endoplasmic reticulum (ER). SRP is a cytosolic particle that transiently binds to the ER signal sequence of a nascent protein, to the large ribosomal unit, and to the SRP receptor in the ER membrane." [PMID:14755292]
subset: PSI-MI_slim
synonym: "srpRNA" EXACT PSI-MI-alternate []
synonym: "srprna" EXACT PSI-MI-short []
is_a: MI:0320 ! ribonucleic acid

[Term]
id: MI:0612
name: comment
def: "Comment for public view. This attribute can be associated to interaction, experiment, CV term, an organism and any participant." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:0665 ! experiment attribute name
is_a: MI:0666 ! participant attribute name
is_a: MI:0667 ! controlled vocabulary attribute name
is_a: MI:0668 ! feature attribute name
is_a: MI:0669 ! organism attribute name

[Term]
id: MI:0613
name: function
def: "Biological function of a participant or of an interaction." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:0666 ! participant attribute name

[Term]
id: MI:0614
name: url
def: "URL/Web address describing an experiment, an interaction, a Cv term or an organism." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:0665 ! experiment attribute name
is_a: MI:0667 ! controlled vocabulary attribute name
is_a: MI:0669 ! organism attribute name

[Term]
id: MI:0615
name: search-url
def: "Search engine URL associated to Cv Database terms." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0667 ! controlled vocabulary attribute name

[Term]
id: MI:0616
name: example
def: "Example generally associated to Cv terms. Test." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0667 ! controlled vocabulary attribute name
is_a: MI:1041 ! synonym

[Term]
id: MI:0617
name: disease
def: "The interaction has a known or demonstrated disease association." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name

[Term]
id: MI:0618
name: caution
def: "Warning about errors or grounds for confusion. Can be associated to an interaction, experiment, CV term or any participant." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:0665 ! experiment attribute name
is_a: MI:0666 ! participant attribute name
is_a: MI:0667 ! controlled vocabulary attribute name
is_a: MI:0668 ! feature attribute name
is_a: MI:0669 ! organism attribute name

[Term]
id: MI:0619
name: pathway
def: "Refers to the metabolic or signalling pathway involving an interaction or a complex." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name

[Term]
id: MI:0620
name: search-url-ascii
def: "Search URL to retrieve an external entry in ASCII format. Generally associated to Cv Database terms." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0667 ! controlled vocabulary attribute name

[Term]
id: MI:0621
name: author-confidence
def: "Confidence classification assigned by the author of the publication to a specific interaction." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name

[Term]
id: MI:0622
name: confidence-mapping
def: "Description of confidence assessment method generally associated to the experiment." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0665 ! experiment attribute name

[Term]
id: MI:0623
name: inhibition
def: "The interaction between the proteins or the formation of a complex is disrupted by a biological molecule or by a modification of the interactors." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name

[Term]
id: MI:0624
name: stimulant
def: "Reaction occurs at a faster rate in the presence of this compound or molecule i.e. the molecule directly physically co-operates with the interaction. Reaction may not occur at all in the absence of this molecule." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name

[Term]
id: MI:0625
name: agonist
def: "Any chemical applied externally to cells or any type of environmental condition, such as hypoxia, that stimulates an interaction, potentially by causing modification of one or more of the interactors." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name

[Term]
id: MI:0626
name: antagonist
def: "Any chemical applied externally to cells or any type of environmental condition, such as hypoxia, that inhibits an interaction, potentially by alteration of amount or binding affinity of one or more of the interactors." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name

[Term]
id: MI:0627
name: experiment modification
def: "Modifications of the standard experimental method described in the CV." [PMID:14755292]
subset: PSI-MI_slim
synonym: "exp-modification" EXACT PSI-MI-short []
is_a: MI:0665 ! experiment attribute name

[Term]
id: MI:0628
name: validation regular expression
def: "Regular Expression used to check the validity of cross references' identifier. Attribute generally associated to terms in Cv Database." [PMID:14755292]
subset: PSI-MI_slim
synonym: "id-validation-regexp" EXACT PSI-MI-short []
is_a: MI:0667 ! controlled vocabulary attribute name

[Term]
id: MI:0629
name: complex-properties
def: "Information on the complex being annotated. Attribute generally associated to an interaction." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:0665 ! experiment attribute name

[Term]
id: MI:0630
name: 3d-structure
def: "Comments on the 3D structure. This attribute is generally associated to an interaction." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name

[Term]
id: MI:0631
name: 3d-r-factors
def: "Free R-Factor and working R-Factor for the quality of the crystallographic model. This attribute is generally associated to an interaction." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name

[Term]
id: MI:0632
name: 3d-resolution
def: "Resolution of the 3D structure. This attribute is generally associated to an interaction." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name

[Term]
id: MI:0633
name: data-processing
def: "Information about how the data was processed. This attribute is used mainly for large scale experiment." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0665 ! experiment attribute name

[Term]
id: MI:0634
name: contact-email
def: "E-mail address to contact the author or organisation which has produced the data. This attribute is generally associated to an experiment." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1093 ! bibliographic attribute name

[Term]
id: MI:0635
name: contact-comment
def: "Free text notes on how to contact the author or organisation which has produced the data This attribute is generally associated to an experiment." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1093 ! bibliographic attribute name

[Term]
id: MI:0636
name: author-list
def: "List of authors associated to a publication. This attribute is generally associated to an experiment." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1093 ! bibliographic attribute name

[Term]
id: MI:0637
name: isoform-comment
def: "Participant isoform's comment. This attribute can be attached to interactions or participants." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:0666 ! participant attribute name

[Term]
id: MI:0638
name: prerequisite-ptm
def: "Post translational modification required for an interaction to occur." [PMID:14755292]
subset: PSI-MI_slim
synonym: "prerequisite ptm" EXACT PSI-MI-alternate []
synonym: "prerequisite-ptm" EXACT PSI-MI-short []
synonym: "required ptm" EXACT PSI-MI-alternate []
synonym: "required-ptm" EXACT PSI-MI-alternate []
is_a: MI:0925 ! observed-ptm

[Term]
id: MI:0639
name: resulting-ptm
def: "Post translational modification occurs subsequently to an interaction." [PMID:14755292]
subset: PSI-MI_slim
synonym: "resulting ptm" EXACT PSI-MI-alternate []
synonym: "resulting-ptm" EXACT PSI-MI-short []
is_a: MI:0925 ! observed-ptm

[Term]
id: MI:0640
name: parameter type
def: "Parameter for enzymatic or binding kinetic studies." [PMID:14755292]
subset: Drugable
subset: PSI-MI_slim
relationship: part_of MI:0000 ! molecular interaction

[Term]
id: MI:0641
name: ic50
def: "Molar concentration of an antagonist which produces 50% of the maximum possible inhibitory response for that antagonist. Note this measure depends on the specific antagonist used and upon experimental conditions, notably temperature, pH and solution composition (e.g., salts, chelating agents and others). Thus the ic50 is a relative measure and its values can be compared only when sharing the same experimental setting. Unit Molar." [PMID:14755292]
subset: PSI-MI_slim
synonym: "IC50" EXACT PSI-MI-alternate []
is_a: MI:0640 ! parameter type

[Term]
id: MI:0642
name: ec50
def: "Molar concentration of an agonist which produces 50% of the maximum possible response for that agonist. Note this measure depends on the specific agonist used and upon experimental conditions, notably temperature, pH and solution composition (e.g., salts, chelating agents and others). Thus the ec50 is a relative measure and its values can be compared only when sharing the same experimental setting. Unit Molar." [PMID:14755292]
subset: PSI-MI_slim
synonym: "EC50" EXACT PSI-MI-alternate []
is_a: MI:0640 ! parameter type

[Term]
id: MI:0643
name: ki
def: "Equilibrium constant for dissociation of an inhibitor. Unit Molar." [PMID:14755292]
subset: PSI-MI_slim
synonym: "Ki" EXACT PSI-MI-alternate []
is_a: MI:0640 ! parameter type

[Term]
id: MI:0644
name: km
def: "Michaelis-Menten constant: concentration of substrate at which the reaction rate is equal to half the maximal rate (i.e. Km={s} when Vo=1/2Vmax). Unit Molar." [PMID:14755292]
subset: PSI-MI_slim
synonym: "Km" EXACT PSI-MI-alternate []
is_a: MI:0640 ! parameter type

[Term]
id: MI:0645
name: kcat
def: "The number of substrate molecules converted to product in a given unit of time, on a single enzyme molecule when the enzyme is saturated with substrate. Unit per second, or s-1." [PMID:14755292]
subset: PSI-MI_slim
synonym: "turnover number" EXACT PSI-MI-alternate []
is_a: MI:0640 ! parameter type

[Term]
id: MI:0646
name: Kd
def: "The equilibrium dissociation constant of a receptor/ligand or proteinA/proteinB complex. Unit Molar (generally M-1)." [PMID:14755292]
subset: PSI-MI_slim
synonym: "Kd" EXACT PSI-MI-alternate []
is_a: MI:0640 ! parameter type

[Term]
id: MI:0647
name: parameter unit
def: "Controlled vocabulary for kinetic constant units." [PMID:14755292]
subset: PSI-MI_slim
relationship: part_of MI:0000 ! molecular interaction

[Term]
id: MI:0648
name: molar
def: "Molarity is the number of moles of solute dissolved in one liter of solution. The units, therefore are moles per liter, specifically it's moles of solute per liter of solution. These units are abbreviated as M and it means moles per liter (not just moles)." [PMID:14755292]
subset: PSI-MI_slim
synonym: "M" EXACT PSI-MI-alternate []
is_a: MI:0647 ! parameter unit

[Term]
id: MI:0649
name: second
def: "The second is the duration of 9 192 631 770 periods of the radiation corresponding to the transition between the two hyperfine levels of the ground state of the cesium-133 atom. The second was originally defined as 1/86 400 mean solar day until astronomers discovered that the mean solar day is actually not constant." [PMID:14755292]
subset: PSI-MI_slim
synonym: "s" EXACT PSI-MI-alternate []
synonym: "sec" EXACT PSI-MI-alternate []
is_a: MI:0647 ! parameter unit

[Term]
id: MI:0650
name: millimolar
def: "10E-3 moles per liter of solution.\nOBSOLETE: term redundant with the schema exponent attribute of the parameter." [PMID:14755292]
subset: PSI-MI_slim
synonym: "mM" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0651
name: micromolar
def: "10E-6 moles per liter of solution.\nOBSOLETE: term redundant with the schema exponent attribute of the parameter." [PMID:14755292]
subset: PSI-MI_slim
synonym: "uM" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0652
name: nanomolar
def: "10E-9 moles per liter of solution.\nOBSOLETE: term redundant with the schema exponent attribute of the parameter." [PMID:14755292]
subset: PSI-MI_slim
synonym: "nM" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0653
name: picomolar
def: "10E-12 moles per liter of solution.\nOBSOLETE: term redundant with the schema exponent attribute of the parameter." [PMID:14755292]
subset: PSI-MI_slim
synonym: "pM" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0654
name: fentomolar
def: "10E-15 moles per liter of solution.\nOBSOLETE: term redundant with the schema exponent attribute of the parameter." [PMID:14755292]
subset: PSI-MI_slim
synonym: "fM" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0655
name: lambda repressor two hybrid
def: "A protein of interest (the bait) is fused to the full-length bacteriophage lambda repressor protein (lambdacI, 237 amino acids), containing the amino terminal DNA-binding domain and the carboxylterminal dimerization domain. The corresponding target (prey) protein is fused to the N-terminal domain of the alfa-subunit of RNA polymerase (248 amino acids). The bait is tethered to the lambda operator sequence upstream of the reporter promoter through the DNA-binding domain of lambdacI. When the bait and prey interact, they recruit and stabilize the binding of RNA polymerase at the promoter and activate the transcription of the HIS3 reporter gene. Due to the tendency of both the lambda repressor protein and the N-terminal domain of the alfa-subunit of RNA polymerase to dimerize, this system might not be optimal for the analysis of proteins that self-associate unless their interaction with other protein partners depends on the oligomerization." [PMID:15792953]
subset: PSI-MI_slim
synonym: "BacterioMatch" EXACT PSI-MI-alternate []
synonym: "lambda two hybrid" EXACT PSI-MI-short []
is_a: MI:0232 ! transcriptional complementation assay

[Term]
id: MI:0656
name: identified peptide
def: "Peptide whose sequence is experimentally identified and can lead to a full protein identification." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0505 ! experimental feature

[Term]
id: MI:0657
name: systematic evolution of ligands by exponential enrichment
def: "RNA and cDNA constructs with variable central sequences and a constant flanking region are collected in a complex library. The library is then screened to select either specific binding partners of a bait molecule (generally a protein) or particular enzymatic activities of the nucleic acid molecules themselves. The selected nucleic acids are amplified using the constant flanking regions to increase their abundance. Cycles of selection-amplification can be repeated to increase the specificity of the targets that, at the end, are individually identified by sequencing." [PMID:11539574]
subset: PSI-MI_slim
synonym: "in vitro evolution of nucleic acids" EXACT PSI-MI-alternate []
synonym: "selex" EXACT PSI-MI-short []
is_a: MI:0400 ! affinity technology

[Term]
id: MI:0658
name: multidimensional protein identification technology
def: "MudPIT is a method for rapid and large-scale protein identification by multidimensional liquid chromatography associated with tandem mass spectrometry. The chromatography step consists of strong cation exchange material back-to-back with reversed phase material inside fused silica capillaries. The peptides bound to the cation-exchange resin are freed by the gradually increasing salt concentration of the buffer and are subsequently retained by the reversed phase resin. Increasing buffers hydrophobicity progressively elute peptides from the reversed phase packing directly into the mass spectrometer. Typically this mass spectrometer will be a tandem electrospray, so peptides undergo ionization in the liquid phase, are separated in a primary mass spectrometer, analysed in the second mass spectrometer and identified." [PMID:11231557]
subset: PSI-MI_slim
synonym: "mudpit" EXACT PSI-MI-short []
is_a: MI:0093 ! protein sequence identification
is_a: MI:0427 ! Identification by mass spectrometry
is_a: MI:0815 ! confirmation by molecular weight

[Term]
id: MI:0659
name: experimental feature detection
def: "Experimental method by which a feature is detected or identified." [PMID:14755292]
subset: PSI-MI_slim
synonym: "exp feature detect" EXACT PSI-MI-short []
is_a: MI:0003 ! feature detection method

[Term]
id: MI:0660
name: feature prediction
def: "Feature detection based on computational analysis." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0003 ! feature detection method

[Term]
id: MI:0661
name: experimental participant identification
def: "experimental participant identification." [PMID:14755292]
subset: PSI-MI_slim
synonym: "experimental particp" EXACT PSI-MI-short []
is_a: MI:0002 ! participant identification method

[Term]
id: MI:0662
name: imex-primary
def: "IMEx primary identifier that is assigned to an experiment record by the database that created the record in the context of IMEx consortium. The identifiers are unique across all member database as they are all generated by a centralized key-assigner.\nhttp://imex.sourceforge.net/" [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:0663
name: confocal microscopy
def: "A confocal is a standard epifluorescence microscope with improvement essentially coming from the rejection of out-of-focus light interference. Confocal imaging system achieves this by two strategies: a) by illuminating a single point of the specimen at any one time with a focused beam, so that illumination intensity drops off rapidly and b) by the use of blocking a pinhole aperture in a conjugate focal plane to the specimen so that light emitted away from the point in the specimen being illuminated is blocked from reaching the detector. Only the light from the single point illuminated of the specimen passing through the image pinhole is detected by a photodetector. Usually a computer is used to control the sequential scanning of the sample and to assemble the image for display onto a video screen." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0428 ! imaging technique

[Term]
id: MI:0664
name: interaction attribute name
def: "Attribute name of annotation associated to an interaction element." [PMID:14755292]
subset: PSI-MI_slim
synonym: "interaction att name" EXACT PSI-MI-short []
is_a: MI:0590 ! attribute name

[Term]
id: MI:0665
name: experiment attribute name
def: "Attribute name of annotation associated to an experiment element." [PMID:14755292]
subset: PSI-MI_slim
synonym: "experiment att name" EXACT PSI-MI-short []
is_a: MI:0590 ! attribute name

[Term]
id: MI:0666
name: participant attribute name
def: "Attribute name of annotation associated to a participant element." [PMID:14755292]
subset: PSI-MI_slim
synonym: "participant att name" EXACT PSI-MI-short []
is_a: MI:0590 ! attribute name

[Term]
id: MI:0667
name: controlled vocabulary attribute name
def: "Attribute name of annotation associated to a CV term." [PMID:14755292]
subset: PSI-MI_slim
synonym: "cv att name" EXACT PSI-MI-short []
is_a: MI:0590 ! attribute name

[Term]
id: MI:0668
name: feature attribute name
def: "Attribute name of annotation associated to a feature element." [PMID:14755292]
subset: PSI-MI_slim
synonym: "feature att name" EXACT PSI-MI-short []
is_a: MI:0590 ! attribute name

[Term]
id: MI:0669
name: organism attribute name
def: "Attribute name of annotation associated to an organism element." [PMID:14755292]
subset: PSI-MI_slim
synonym: "organism att name" EXACT PSI-MI-short []
is_a: MI:0590 ! attribute name

[Term]
id: MI:0670
name: imex
def: "International Molecular Interaction Exchange." [PMID:22453911]
subset: PSI-MI_slim
synonym: "IMEx" EXACT PSI-MI-alternate []
xref: search-url: "http://www.ebi.ac.uk/intact/imex/main.xhtml?query=${ac}"
is_a: MI:0461 ! interaction database

[Term]
id: MI:0671
name: antibodies
def: "This annotation topic should contain information about antibodies when specific antibodies (monoclonal or polyclonal raised against specific regions of the proteins or purified in a specific manner) have been used." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0665 ! experiment attribute name

[Term]
id: MI:0672
name: library-used
def: "This annotation topic will be used to store information about the cDNA library. If a name is available this should be reported along with a short description of the library." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0665 ! experiment attribute name

[Term]
id: MI:0673
name: complex synonym
def: "Alternative names to describe a complex." [PMID:14755292]
subset: PSI-MI_slim
synonym: "complex-synonym" EXACT []
is_a: MI:1041 ! synonym

[Term]
id: MI:0674
name: peptide parent sequence reference
def: "Describe a cross reference pointing to a peptide parent sequence." [PMID:14755292]
subset: PSI-MI_slim
synonym: "peptide-parent" EXACT PSI-MI-short []
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:0675
name: international protein index
def: "IPI provides a top level guide to the main databases that describe the proteomes of higher eukaryotic organisms. IPI effectively maintains a database of cross references between the primary data sources, provides minimally redundant yet maximally complete sets of proteins for featured species (one sequence per transcript) and maintains stable identifiers (with incremental versioning) to allow the tracking of sequences in IPI between IPI releases. IPI is updated monthly in accordance with the latest data released by the primary data sources." [PMID:15221759]
subset: PSI-MI_slim
synonym: "ipi" EXACT PSI-MI-short []
xref: id-validation-regexp: "IPI[0-9]+.[0-9]+|IPI[0-9]+"
is_a: MI:1096 ! protein sequence databases

[Term]
id: MI:0676
name: tandem affinity purification
def: "Tandem affinity purification allows rapid purification under native conditions of complexes, even when expressed at their natural level. Prior knowledge of complex composition or function is not required. The TAP method requires fusion of the a multiple tag, either N- or C-terminally, to the target (or bait) protein of interest. The multiple tag allows two steps purification steps ensuring a highly selective complex purification." [PMID:11403571]
subset: PSI-MI_slim
synonym: "TAP" EXACT PSI-MI-alternate []
synonym: "tap" EXACT PSI-MI-short []
is_a: MI:0004 ! affinity chromatography technology

[Term]
id: MI:0677
name: tandem tag
def: "A tandem tag consists of the concatenation of simple distinct tags that is engineered to be cloned as a unique element onto a sequence of interest. Note that when a protein is fused to many simple tags that are inserted individually and possibly in different sequence positions these should be reported as independent features." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0507 ! tag

[Term]
id: MI:0678
name: antibody array
def: "A microarray consisting of antibodies spotted on a solid support in appropriate orientation is incubated with a biological sample (or antigen). Some proteins are captured by the antibodies in the array. Protein of  forming complexes on the array are identified according to their prior labelling (tag, ELISA, biotin and others)." [PMID:12454649]
subset: PSI-MI_slim
synonym: "antigen capture assay" EXACT PSI-MI-alternate []
synonym: "sandwich immunoassay" EXACT PSI-MI-alternate []
is_a: MI:0089 ! protein array

[Term]
id: MI:0679
name: poly adenine
def: "A sequence of adenine nucleotides that is added to the 3' end of some primary transcript messenger RNA molecules in eukaryotes during post-transcriptional processing. The added tail is believed to confer stability to the molecule." [PMID:14755292]
subset: PSI-MI_slim
synonym: "poly A" EXACT PSI-MI-alternate []
synonym: "poly a" EXACT PSI-MI-short []
is_a: MI:0320 ! ribonucleic acid

[Term]
id: MI:0680
name: single stranded deoxyribonucleic acid
def: "DNA that consists of only one chain of nucleotides rather than the two base pairing strands found in DNA in the double helix form." [PMID:14755292]
subset: PSI-MI_slim
synonym: "ss DNA" EXACT PSI-MI-alternate []
synonym: "ss dna" EXACT PSI-MI-short []
is_a: MI:0319 ! deoxyribonucleic acid

[Term]
id: MI:0681
name: double stranded deoxyribonucleic acid
def: "DNA that consists of two base pairing strands. The 2 nucleotide chains are held together by hydrogen bonds between base pairs of nucleotides.\n" [PMID:14755292]
subset: PSI-MI_slim
synonym: "ds DNA" EXACT PSI-MI-alternate []
synonym: "ds dna" EXACT PSI-MI-short []
is_a: MI:0319 ! deoxyribonucleic acid

[Term]
id: MI:0682
name: cofactor
def: "A cofactor is a small molecule required for the catalysis of an enzyme." [PMID:14755292]
subset: PSI-MI_slim
synonym: "coenzyme" EXACT PSI-MI-alternate []
is_a: MI:0500 ! biological role

[Term]
id: MI:0683
name: sequence database
def: "Database collecting nucleic or amino acid sequences mainly derived from genomic or mRNA sequencing." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0473 ! participant database

[Term]
id: MI:0684
name: ancillary
def: "Molecule required for an observed binary interaction to occur. This molecule may act as stabilizer of any of the interaction partners or may act as a bridge molecule between them but the method does not provide resolution or evidence to demonstrate its actual molecular function (i.e.Mudpit, tri hybrid etc)." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0495 ! experimental role
is_a: MI:0500 ! biological role

[Term]
id: MI:0685
name: source reference
def: "Publication or document describing the originating resource where an interaction, or other curated information, was first described." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:0686
name: unspecified method
def: "Yet to be identified interaction detection method associated with interaction data imported from a third party database. This database may have potentially different standards of curation." [PMID:14755292]
subset: Drugable
subset: PSI-MI_slim
is_a: MI:0001 ! interaction detection method

[Term]
id: MI:0687
name: fluorescent protein tag
def: "Protein having well characterized fluorescence excitation and emission spectra used as fusion with a protein under study to facilitate its  localisation or identification." [PMID:14755292]
subset: PSI-MI_slim
synonym: "fluorescent prot tag" EXACT PSI-MI-short []
is_a: MI:0240 ! fusion protein

[Term]
id: MI:0688
name: dna binding domain tag
def: "Part of a transcription factor responsible for the binding of gene regulatory region prior to their transcription. Such tags are generally used in two hybrid experiments where they are fused to a bait polypeptide tested for its ability to interact with a prey fused to an activation domain tag." [PMID:14755292]
subset: PSI-MI_slim
synonym: "dna binding domain" EXACT PSI-MI-short []
is_a: MI:0240 ! fusion protein

[Term]
id: MI:0689
name: activation domain tag
def: "Part of a transcription factor responsible for the activation of DNA transcription. Such tags are generally used in two hybrid experiments where they are fused to a prey polypeptide tested for its ability to interact with a bait fused to a DNA binding domain tag." [PMID:14755292]
subset: PSI-MI_slim
synonym: "activation domain" EXACT PSI-MI-short []
is_a: MI:0240 ! fusion protein

[Term]
id: MI:0690
name: gal4 activation domain
def: "Part of the yeast transcription factor GAL4 (amino acids 766-881) specifically responsible for DNA transcription activation." [PMID:14755292]
subset: PSI-MI_slim
synonym: "gal4 ad" EXACT PSI-MI-short []
is_a: MI:0689 ! activation domain tag

[Term]
id: MI:0691
name: vp16 activation domain
def: "Full viral protein vp16 exclusively responsible for preferential transcriptional activation of viral genes. Activation requires the formation of a complex with the host cell transcription factor." [PMID:14755292]
subset: PSI-MI_slim
synonym: "vp16 ad" EXACT PSI-MI-short []
is_a: MI:0689 ! activation domain tag

[Term]
id: MI:0692
name: b42 activation domain
def: "B42 is an acidic sequence of 89 residues  derived from Escherichia coli acting as weak transcription activation domain. When use in two hybrid experiments, the weakness of B42 as activator increases the sensitivity of the interaction detection." [PMID:14613974]
subset: PSI-MI_slim
synonym: "b42 ad" EXACT PSI-MI-short []
is_a: MI:0689 ! activation domain tag

[Term]
id: MI:0693
name: gal4 dna binding domain
def: "Part of the yeast transcription factor GAL4 (amino acids 11-38) specifically responsible for DNA binding of a 17 base-pair long sequence in the upstream activating sequence of galactose-induced genes.\n" [PMID:14755292]
subset: PSI-MI_slim
synonym: "gal4 dna bd" EXACT PSI-MI-short []
is_a: MI:0688 ! dna binding domain tag

[Term]
id: MI:0694
name: lexa dna binding domain
def: "Amino terminal (1-220) part of the Escherichia coli lexA repressor, binding to 16 base pair palindromic DNA sequences." [PMID:14755292]
subset: PSI-MI_slim
synonym: "lexa dna bd" EXACT PSI-MI-short []
is_a: MI:0688 ! dna binding domain tag

[Term]
id: MI:0695
name: sandwich immunoassay
def: "Antibody array where proteins retained by the arrayed antibodies are identified using a detector antibody. The detector antibody is either modified with a directly detectable label (enzyme, fluorescent molecule, isotope, etc.), or it is biotinylated for detection after subsequent probing with labeled streptavidin." [PMID:12454649]
subset: PSI-MI_slim
is_a: MI:0678 ! antibody array

[Term]
id: MI:0696
name: polymerase assay
def: "Measures the catalysis of the transfer of a free nucleotidyl group to a nucleic acid chain." [PMID:14755292]
subset: PSI-MI_slim
synonym: "nucleotidyltransferase assay" EXACT PSI-MI-alternate []
is_a: MI:0415 ! enzymatic study

[Term]
id: MI:0697
name: dna directed dna polymerase assay
def: "Measures the catalysis of the reaction: deoxynucleoside triphosphate + DNA(n) = diphosphate + DNA(n+1); the synthesis of DNA from deoxyribonucleotide triphosphates in the presence of a DNA template or primer." [PMID:14755292]
subset: PSI-MI_slim
synonym: "dna dna pol assay" EXACT PSI-MI-short []
is_a: MI:0696 ! polymerase assay

[Term]
id: MI:0698
name: dna directed rna polymerase assay
def: "Measures the catalysis of the reaction: nucleoside triphosphate + RNA(n) = diphosphate + RNA(n+1). Utilizes a DNA template, i.e. the catalysis of DNA-template-directed extension of the 3'-end of an RNA strand by one nucleotide at a time. Can initiate a chain 'de novo'." [PMID:14755292]
subset: PSI-MI_slim
synonym: "dna rna pol assay" EXACT PSI-MI-short []
is_a: MI:0696 ! polymerase assay

[Term]
id: MI:0699
name: rna directed dna polymerase assay
def: "Measures the catalysis of the reaction: deoxynucleoside triphosphate + DNA(n) = diphosphate + DNA(n+1). Catalyzes RNA-template-directed extension of the 3'- end of a DNA strand by one deoxynucleotide at a time." [PMID:14755292]
subset: PSI-MI_slim
synonym: "rna dna pol assay" EXACT PSI-MI-short []
is_a: MI:0696 ! polymerase assay

[Term]
id: MI:0700
name: rna directed rna polymerase assay
def: "Measures the catalysis of the reaction: nucleoside triphosphate + RNA (n) = diphosphate + RNA (n+1); uses an RNA template." [PMID:14755292]
subset: PSI-MI_slim
synonym: "rna rna pol assay" EXACT PSI-MI-short []
is_a: MI:0696 ! polymerase assay

[Term]
id: MI:0701
name: dna strand elongation
def: "The process by which a DNA strand is synthesized from template DNA by the action of polymerases, which add nucleotides to the 3' end of the nascent DNA strand." [GO:0006271, PMID:14755292]
subset: PSI-MI_slim
synonym: "dna elongation" EXACT PSI-MI-short []
synonym: "DNA replication elongation " EXACT PSI-MI-alternate []
is_a: MI:0986 ! nucleic acid strand elongation reaction

[Term]
id: MI:0702
name: panther
def: "The PANTHER (Protein ANalysis THrough Evolutionary Relationships) Classification System is a unique resource that classifies genes by their functions using published scientific experimental evidence and evolutionary relationships to predict function even in the absence of direct experimental evidence.\nwww.pantherdb.org/" [PMID:14755292]
subset: PSI-MI_slim
synonym: "PANTHER" EXACT PSI-MI-alternate []
is_a: MI:0449 ! interpro

[Term]
id: MI:0703
name: gene3d
def: "The Gene3D database provides a combined structural, functional and evolutionary view of the protein world. It is focused on providing structural annotation for protein sequences without structural representatives--including the complete proteome sets of over 240 different species.\nhttp://cathwww.biochem.ucl.ac.uk:8080/Gene3D/" [PMID:14755292]
subset: PSI-MI_slim
synonym: "Gene3D" EXACT PSI-MI-alternate []
is_a: MI:0449 ! interpro

[Term]
id: MI:0704
name: nucleic acid delivery
def: "Method by which nucleic acids are delivered or engineered into a cell." [PMID:14755292]
subset: PSI-MI_slim
synonym: "nucl delivery" EXACT PSI-MI-short []
is_a: MI:0307 ! delivery method

[Term]
id: MI:0705
name: anti tag western blot
def: "Western blot assay performed when specific antibodies for the protein of interest are not available. Therefore the protein is expressed as a hybrid protein fused to a tag for which efficient antibodies are available. The antibody may be either monoclonal or polyclonal." [PMID:14755292]
subset: PSI-MI_slim
synonym: "anti tag western" EXACT PSI-MI-short []
is_a: MI:0113 ! western blot
is_a: MI:0866 ! tag visualisation

[Term]
id: MI:0706
name: nucleic acid transformation
def: "Transformation is the genetic alteration of a cell resulting from the introduction, uptake and expression of foreign genetic material incorporated into the cell's genome (DNA or RNA)." [PMID:14755292]
subset: PSI-MI_slim
synonym: "nucl transformation" EXACT PSI-MI-short []
is_a: MI:0704 ! nucleic acid delivery

[Term]
id: MI:0707
name: anti tag immunostaining
def: "Immunostaining assay performed when specific antibodies for the protein of interest are not available. Therefore the  protein is expressed as a hybrid protein fused to a tag peptide/protein for which efficient antibodies are available. The anti tag antibody may be either monoclonal or polyclonal." [PMID:14755292]
subset: PSI-MI_slim
synonym: "anti tag immunost" EXACT PSI-MI-short []
is_a: MI:0422 ! immunostaining

[Term]
id: MI:0708
name: monoclonal antibody immunostaining
def: "A monospecific antibody for the protein of interest is available, this is used to detect a specific protein within a cell or tissue sample." [PMID:14755292]
subset: PSI-MI_slim
synonym: "monoclonal immunost" EXACT PSI-MI-short []
is_a: MI:0422 ! immunostaining

[Term]
id: MI:0709
name: polyclonal antibody immunostaining
def: "Immunostaining assay carried out using a mixture of different antibodies that represent the immune response, normally in an experimental animal, to the protein of interest. These antibodies are used to detect the protein within a cell or tissue sample." [PMID:14755292]
subset: PSI-MI_slim
synonym: "polyclonal immunost" EXACT PSI-MI-short []
is_a: MI:0422 ! immunostaining

[Term]
id: MI:0710
name: nucleic acid transformation by treatment with divalent cation
def: "Stable introduction and expression of nucleic acid carried out by treatment with divalent cation." [PMID:14755292]
subset: PSI-MI_slim
synonym: "n transformat cation" EXACT PSI-MI-short []
is_a: MI:0706 ! nucleic acid transformation

[Term]
id: MI:0711
name: nucleic acid electroporation
def: "Electroporation, or electropermeabilization, is a significant increase in the electrical conductivity and permeability of the cell plasma membrane caused by externally applied electrical field. It is usually used in molecular biology as a way of introducing some substance inside the cell, such as loading it with a molecular probe, a drug that can change cell's function, or a piece of coding DNA." [PMID:14755292]
subset: PSI-MI_slim
synonym: "nucl electroporation" EXACT PSI-MI-short []
is_a: MI:0308 ! electroporation
is_a: MI:0704 ! nucleic acid delivery

[Term]
id: MI:0712
name: nucleic acid microinjection
def: "Microinjection refers to the process of using a micro needle to insert substances at a microscopic level into a single living cell. It is a simple mechanical process in which an extremely fine micro needle penetrates the cell membrane and sometimes the nuclear envelope and releases nucleic acids." [PMID:14755292]
subset: PSI-MI_slim
synonym: "nucl microinjection" EXACT PSI-MI-short []
is_a: MI:0311 ! microinjection
is_a: MI:0704 ! nucleic acid delivery

[Term]
id: MI:0713
name: nucleic acid passive uptake
def: "Nucleic acid entrance into cells that does not involved specific treatments but rely on natural cellular processes." [PMID:14755292]
subset: PSI-MI_slim
synonym: "nucl passive uptake" EXACT PSI-MI-short []
is_a: MI:0704 ! nucleic acid delivery
is_a: MI:0716 ! passive uptake

[Term]
id: MI:0714
name: nucleic acid transduction
def: "Transduction is the process by which bacterial DNA is moved from one bacterium to another by a virus." [PMID:14755292]
subset: PSI-MI_slim
synonym: "nucl transduction" EXACT PSI-MI-short []
is_a: MI:0704 ! nucleic acid delivery

[Term]
id: MI:0715
name: nucleic acid conjugation
def: "Bacterial conjugation is the transfer of genetic material between bacteria through cell-to-cell contact. Bacterial conjugation is often incorrectly regarded as the bacterial equivalent of sexual reproduction or mating. It is not actually sexual, as it does not involve the fusing of gametes and the creation of a zygote. It is merely the transfer of  a conjugative plasmid from a donor cell to a recipient" [PMID:14755292]
subset: PSI-MI_slim
synonym: "nucl conjugation" EXACT PSI-MI-short []
is_a: MI:0704 ! nucleic acid delivery

[Term]
id: MI:0716
name: passive uptake
def: "Entrance of molecules into cells that does not involved specific treatments but relies on natural cellular processes." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0307 ! delivery method

[Term]
id: MI:0717
name: nucleic acid transfection with liposome
def: "Lipofection (or liposome transfection) is a technique used to inject genetic material into a cell by means of liposomes which are vesicles that can easily merge with the cell membrane since they are both made of a phospholipid bilayer." [PMID:14755292]
subset: PSI-MI_slim
synonym: "nucl lipotransfect" EXACT PSI-MI-short []
is_a: MI:0312 ! nucleic acid transfection

[Term]
id: MI:0718
name: nucleic acid transfection by treatment
def: "Transient introduction and expression of nucleic acid carried out by treatment with chemicals." [PMID:14755292]
subset: PSI-MI_slim
synonym: "n transfection treat" EXACT PSI-MI-short []
is_a: MI:0312 ! nucleic acid transfection

[Term]
id: MI:0719
name: calcium phosphate nucleic acid transfection
def: "Transient introduction and expression of nucleic acid carried out by treatment with calcium phosphate." [PMID:14755292]
subset: PSI-MI_slim
synonym: "ca po nuc transfect" EXACT PSI-MI-short []
is_a: MI:0718 ! nucleic acid transfection by treatment

[Term]
id: MI:0720
name: nucleic acid delivery by infection
def: "Nucleic acid introduced into a cell via an external organism, usually a virus or bacteria.." [PMID:14755292]
subset: PSI-MI_slim
synonym: "nucl infection" EXACT PSI-MI-short []
is_a: MI:0310 ! infection
is_a: MI:0704 ! nucleic acid delivery

[Term]
id: MI:0721
name: protein delivery
def: "Method by which proteins are delivered into a cell." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0307 ! delivery method

[Term]
id: MI:0722
name: protein electroporation
def: "Method for temporarily permeabilising cell membranes in order to facilitate the entry of a protein." [PMID:14755292]
subset: PSI-MI_slim
synonym: "prot electroporation" EXACT PSI-MI-short []
is_a: MI:0308 ! electroporation
is_a: MI:0721 ! protein delivery

[Term]
id: MI:0723
name: protein microinjection
def: "Microinjection refers to the process of using a micro needle to insert substances at a microscopic level into a single living cell. It is a simple mechanical process in which an extremely fine micro needle penetrates the cell membrane and sometimes the nuclear envelope and releases proteins." [PMID:14755292]
subset: PSI-MI_slim
synonym: "prot microinjection" EXACT PSI-MI-short []
is_a: MI:0311 ! microinjection
is_a: MI:0721 ! protein delivery

[Term]
id: MI:0724
name: protein delivery by cationic lipid treatment
def: "Proteins are delivered into cells by treatment with cationic lipids." [PMID:14755292]
subset: PSI-MI_slim
synonym: "prot cationic lipid" EXACT PSI-MI-short []
is_a: MI:0721 ! protein delivery

[Term]
id: MI:0725
name: protein delivery by infection
def: "Protein introduced into a cell via an external organism, usually a virus or bacteria." [PMID:14755292]
subset: PSI-MI_slim
synonym: "prot infection" EXACT PSI-MI-short []
is_a: MI:0310 ! infection
is_a: MI:0721 ! protein delivery

[Term]
id: MI:0726
name: reverse two hybrid
def: "Yeast strains are generated in which expression of DB-X/AD-Y or DBPX hybrid proteins is toxic under particular conditions (negative selection). Under these conditions, dissociation of an interaction should provide a selective advantage thereby facilitating detection: a few growing yeast colonies in which DB-X/AD-Y (or DBPX/binding site) fail to interact should be identified among many nongrowing colonies containing interacting DB-X/AD-Y or DBPX/binding site." [PMID:8816797]
subset: PSI-MI_slim
is_a: MI:0003 ! feature detection method
is_a: MI:0232 ! transcriptional complementation assay

[Term]
id: MI:0727
name: lexa b52 complementation
def: "Yeast two-hybrid system using Escherichia coli LexA amino acids 1-202 as the DNA-binding domain (BD), E. coli B42 acidic sequence as the activation domain (AD), and two reporters, lacZ and LEU2, each containing upstream LexA binding elements." [PMID:14613974]
subset: PSI-MI_slim
synonym: "lexa b52 complement" EXACT PSI-MI-short []
synonym: "LexA B52 transcription complementation" EXACT PSI-MI-alternate []
is_a: MI:0018 ! two hybrid

[Term]
id: MI:0728
name: gal4 vp16 complementation
def: "A chimeric protein consisting of the GAL4 DNA-binding domain (aa 1-147 of GAL4) and a transcriptional activation domain from the herpes simplex virus protein VP16 (either aa 411-490 or aa 411-455) can specifically activate transcription of a reporter gene located downstream ofGAL4 DNA binding sites and the E1B minimal promoter. Similarly, two chimeric proteins, one encoding a chimeric GAL4 protein and the other encoding a chimeric VP16 protein, can activate the reporter gene, if the domains fused to the GAL4 and VP16 sequences can complex with appropriate conformation. However, if the domains fused to the GAL4 and VP16 sequences do not interact specifically to form a + complex that reconstitutes GAL4 function, the reporter gene cannot be activated." [PMID:1387709]
subset: PSI-MI_slim
synonym: "gal4 vp16 complement" EXACT PSI-MI-short []
synonym: "karyoplasmic interaction ion strategy" EXACT PSI-MI-alternate []
synonym: "KISS" EXACT PSI-MI-alternate []
synonym: "mammalian two hybrid" EXACT PSI-MI-alternate []
is_a: MI:0018 ! two hybrid

[Term]
id: MI:0729
name: luminescence based mammalian interactome mapping
def: "This strategy uses a luciferase enzyme fused to proteins of interest, which are then coexpressed with individual epitope-tagged partners in mammalian cells. Their interactions are determined by performing an enzymatic assay on anti-tag immunoprecipitates." [PMID:15761153]
subset: PSI-MI_slim
synonym: "lumier" EXACT PSI-MI-short []
is_a: MI:0004 ! affinity chromatography technology

[Term]
id: MI:0730
name: pubchem
def: "PubChem provides information on the biological activities of small molecules.\nhttp://pubchem.ncbi.nlm.nih.gov/" [PMID:16381840]
subset: PSI-MI_slim
synonym: "PubChem" EXACT PSI-MI-alternate []
is_a: MI:2054 ! bioactive entity reference

[Term]
id: MI:0731
name: 3d repertoire
def: "The aim of 3D Repertoire is to determine the structures of all amenable complexes in a cell at medium or high resolution, which will later serve to integrate in toponomic and dynamic analyses of protein complexes in a cell. Complex models, EM pictures, expression and purification protocols obtained in the project will be collected in a database connected to the PDB repository." [PMID:14755292]
subset: PSI-MI_slim
synonym: "3D Repertoire" EXACT PSI-MI-alternate []
is_a: MI:0489 ! source database

[Term]
id: MI:0732
name: red fluorescent protein tag
def: "The red fluorescent protein derived from, for example, marine anemone Discosoma striata and reef corals belonging to the class Anthozoacan can be fused to individual proteins which then acquire fluorescence excitation and emission spectra virtually identical to those of the native." [PMID:14755292]
subset: PSI-MI_slim
synonym: "red fluorescent protein" EXACT PSI-MI-alternate []
synonym: "RFP" EXACT PSI-MI-alternate []
synonym: "rfp tag" EXACT PSI-MI-short []
is_a: MI:0687 ! fluorescent protein tag

[Term]
id: MI:0733
name: cyan fluorescent protein tag
def: "The cyan fluorescent protein derived from Anthozoa reef coral can be fused to individual proteins which then acquire fluorescence excitation and emission spectra virtually identical to those of the native." [PMID:14755292]
subset: PSI-MI_slim
synonym: "CFP" EXACT PSI-MI-alternate []
synonym: "cfp tag" EXACT PSI-MI-short []
synonym: "cyan fluorescent protein" EXACT PSI-MI-alternate []
is_a: MI:0687 ! fluorescent protein tag

[Term]
id: MI:0734
name: enhanced green fluorescent protein tag
def: "Variation of the green fluorescent protein derived from the bioluminescent jellyfish Aequorea victoria, can be fused to individual proteins which then acquire fluorescence excitation and emission spectra virtually identical to those of the native." [PMID:14755292]
subset: PSI-MI_slim
synonym: "EGFP" EXACT PSI-MI-alternate []
synonym: "egfp tag" EXACT PSI-MI-short []
synonym: "enhanced green fluorescent protein" EXACT PSI-MI-alternate []
is_a: MI:0367 ! green fluorescent protein tag

[Term]
id: MI:0735
name: transactivating tag
def: "Tag derived from the transactivating (Tat) protein of human immunodeficiency virus 1 (HIV-1) that can enter cells efficiently when added exogenously in tissue culture. The Tat tag can carry other molecules into cells, by fusion of Tat peptides (residues 1-72 or 37-72,) to any molecule under study. Tat-mediated uptake may allow the delivery of macromolecules previously thought to be impermeable to living cells." [PMID:8290579]
subset: PSI-MI_slim
synonym: "Tat tag" EXACT PSI-MI-alternate []
synonym: "tat tag" EXACT PSI-MI-short []
is_a: MI:0740 ! cell penetrating peptide tag

[Term]
id: MI:0736
name: protein passive uptake
def: "Proteins entrance into cells that does not involved specific treatments but rely on natural cellular processes." [PMID:14755292]
subset: PSI-MI_slim
synonym: "prot passive uptake" EXACT PSI-MI-short []
is_a: MI:0716 ! passive uptake
is_a: MI:0721 ! protein delivery

[Term]
id: MI:0737
name: peptide sequence database
def: "database storing sequences detected by peptide identification methods." [PMID:14755292]
subset: PSI-MI_slim
synonym: "pep seq db" EXACT PSI-MI-short []
is_a: MI:0683 ! sequence database

[Term]
id: MI:0738
name: pride
def: "PRIDE is a public repository of protein and peptide identifications for the proteomics community.\nhttp://www.ebi.ac.uk/pride/" [PMID:16381953]
subset: PSI-MI_slim
xref: search-url: "http://www.ebi.ac.uk/pride/archive/projects/${ac}"
is_a: MI:0737 ! peptide sequence database

[Term]
id: MI:0739
name: penetrating tag
def: "Membrane shuttling peptide derived from the Drosophila homeobox protein Antennapedia: RQIKIWFQNRRMKWKK" [PMID:16574060]
subset: PSI-MI_slim
is_a: MI:0740 ! cell penetrating peptide tag

[Term]
id: MI:0740
name: cell penetrating peptide tag
def: "The peptides named CPPs vary greatly in size, amino acid sequence, and charge, but share the common feature that they have the ability to rapidly translocate the plasma membrane and enable delivery to the cytoplasm or nucleus." [PMID:16574060]
subset: PSI-MI_slim
synonym: "cell penetrating pep" EXACT PSI-MI-short []
synonym: "cell-penetrating peptides" EXACT PSI-MI-alternate []
synonym: "CPPs" EXACT PSI-MI-alternate []
synonym: "membrane translocating sequences" EXACT PSI-MI-alternate []
synonym: "MTS" EXACT PSI-MI-alternate []
synonym: "protein transduction domains" EXACT PSI-MI-alternate []
synonym: "PTDs" EXACT PSI-MI-alternate []
synonym: "Trojan peptides" EXACT PSI-MI-alternate []
is_a: MI:0507 ! tag

[Term]
id: MI:0741
name: peptide atlas
def: "PeptideAtlas addresses these needs by identifying peptides by tandem mass spectrometry (MS/MS), statistically validating those identifications and then mapping identified sequences to the genomes of eukaryotic organisms.\nhttp://www.peptideatlas.org/" [PMID:15642101, PMID:16381952]
subset: PSI-MI_slim
synonym: "PeptideAtlas" EXACT PSI-MI-alternate []
is_a: MI:0737 ! peptide sequence database

[Term]
id: MI:0742
name: gpm
def: "Global Proteome Machine aim to improve the quality of analysis, make the results portable and to provide a common platform for testing and validating proteomics results.\nhttp://www.thegpm.org" [PMID:15595733]
subset: PSI-MI_slim
synonym: "Global Proteome Machine" EXACT PSI-MI-alternate []
is_a: MI:0737 ! peptide sequence database

[Term]
id: MI:0787
name: genetic experimental form
def: "Descriptor of an experimental form involved in a genetic interaction" [PMID:14755292]
subset: PSI-MI_slim
synonym: "genetic exp form" EXACT PSI-MI-short []
is_a: MI:0346 ! experimental preparation

[Term]
id: MI:0788
name: knock out
def: "The gene has been completely removed e.g. by genetic engineering " [PMID:14755292]
subset: PSI-MI_slim
synonym: "knock-out" EXACT PSI-MI-short []
is_a: MI:0804 ! mutated gene

[Term]
id: MI:0789
name: knock down
def: "The gene expression has been significantly reduced compared to wild-type by introduction of an external substance, e.g. by RNA interference." [PMID:14755292]
subset: PSI-MI_slim
synonym: "knock-down" EXACT PSI-MI-short []
is_a: MI:0804 ! mutated gene

[Term]
id: MI:0790
name: hypermorph
def: "The gene function has been partially improved compared to wild-type by altering its sequence." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0787 ! genetic experimental form

[Term]
id: MI:0791
name: hypomorph
def: "The gene function has been partially reduced compared to wild-type by altering its sequence e.g. a temperature sensitive mutant." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0787 ! genetic experimental form

[Term]
id: MI:0792
name: antimorph
def: "The gene function has been antagonized by a mutation in another copy of the gene." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0787 ! genetic experimental form

[Term]
id: MI:0793
name: amorph
def: "The gene function has been abolished by mutation, though the type of mutation is not known." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0787 ! genetic experimental form

[Term]
id: MI:0794
name: synthetic
def: "An effect in which two genetic perturbations, when combined, result in a mutant phenotype that is not observed (to any degree) as a result of any of the individual perturbations.\nwt = a = b = E (not=) ab" [PMID:15833125]
subset: PSI-MI_slim
synonym: "synthetic genetic interaction (sensu inequality)" EXACT []
synonym: "synthetic genetic interaction defined by inequality" EXACT []
is_a: MI:0933 ! negative genetic interaction

[Term]
id: MI:0795
name: asynthetic
def: "An effect in which individual perturbations of different genes and their combination result in the same mutant phenotype, to the same degree of severity/penetrance. With respect to any single quantifiable phenotype, this may be expressed as an inequality as: \na = b = ab != wt\nwhere 'a' and 'b' are the observed phenotype values of the individual perturbations, 'ab' is the observed phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:15833125]
subset: PSI-MI_slim
synonym: "asynthetic" EXACT PSI-MI-short []
synonym: "asynthetic genetic interaction (sensu inequality)" EXACT PSI-MI-alternate []
is_a: MI:0935 ! positive genetic interaction

[Term]
id: MI:0796
name: suppression
def: "An effect in which two genetic perturbations, when combined, result in a phenotype that is less severe/penetrant than the most severe phenotype of the original perturbations, in effect making the organism more \"wild type\" in character with regards to the phenotype in question. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\na* < ab <= wt [E = a*]\nOR\nwt <= ab < a* [E = a*]\nwhere 'a*' is the most severe observed phenotype value of the individual perturbations, 'ab' is the observed phenotype value of the double perturbation, 'E' is the expected phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:15833125]
subset: PSI-MI_slim
synonym: "Alleviating interaction" RELATED []
synonym: "suppression" EXACT PSI-MI-short []
synonym: "suppressive genetic interaction (sensu inequality)" EXACT PSI-MI-alternate []
is_a: MI:0935 ! positive genetic interaction

[Term]
id: MI:0797
name: epistasis
def: "An effect in which individual perturbations of two different genes result in different mutant phenotypes, and the resulting phenotype of their combination (the double mutant) is equal to that of only one of the perturbations. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\n(a != wt AND b != wt AND a != b) AND (ab = a OR ab = b)\nwhere 'a' and 'b' are the observed phenotype values of the individual perturbations, 'ab' is the observed phenotype value of the double perturbation, 'wt' is the wild type phenotype value and 'a != b' indicates qualitatively or quantitatively different phenotypes." [PMID:15833125]
subset: PSI-MI_slim
synonym: "epistatic" EXACT PSI-MI-short []
synonym: "epistatic genetic interaction (sensu inequality)" EXACT PSI-MI-alternate []
is_a: MI:0208 ! genetic interaction

[Term]
id: MI:0798
name: conditional genetic interaction defined by inequality
def: "The phenotype resulting from genetic perturbation of A has an effect only in the b background, or the b mutant has an effect only in the a background. a has an effect only in the b background, or the b mutant has an effect only in the a background. E. g., WT = a > ab > b or WT > a > b > ab." [PMID:15833125]
subset: PSI-MI_slim
synonym: "conditional" EXACT PSI-MI-short []
synonym: "conditional genetic interaction (sensu inequality)" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0799
name: additive genetic interaction defined by inequality
def: "Single-mutant phenotype effects combine to give a double-mutant effect different from the wild type and different from single mutant effect. For instance, WT < a = b < ab, b < WT = ab < a, WT < a < b < ab, b < WT < ab < a, and all additional inequalities obtained by interchanging a and b, or reversing the effect of both a and b." [PMID:15833125]
subset: PSI-MI_slim
synonym: "additive" EXACT PSI-MI-short []
synonym: "additive genetic interaction (sensu inequality)" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0800
name: single nonmonotonic genetic interaction defined by inequality
def: "The phenotype resulting from genetic perturbation of B shows opposing effects in the WT and a backgrounds (for example, b > WT and ab < a); or, a shows opposing effects in the WT and b backgrounds, but not both. E.g., WT > a > ab > b." [PMID:15833125]
subset: PSI-MI_slim
synonym: "single nonmonotonic" EXACT PSI-MI-short []
synonym: "single nonmonotonic genetic interaction (sensu inequality)" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0801
name: double nonmonotonic genetic interaction defined by inequality
def: "The phenotype resulting from genetic perturbation of both A and B show opposing effects in the WT background and the background with the other mutant gene. E.g., WT >= ab > a >= b" [PMID:15833125]
subset: PSI-MI_slim
synonym: "double nonmonotonic" EXACT PSI-MI-short []
synonym: "double nonmonotonic genetic interaction (sensu inequality)" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0802
name: enhancement interaction
def: "The A genetic perturbation enhances the phenotype of the B perturbation, or vice versa (e.g. WT = A < B < AB or WT = B < A < AB). This could be conditional or additive by the above scheme.\nOBSOLETE: remap to MI:0933 'negative genetic interaction'" [PMID:15833125]
subset: PSI-MI_slim
synonym: "enhancement" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0803
name: expression level alteration
def: "Synthesis rate of a molecule under investigation differs from its naturally occurring expression level in a cell." [PMID:14755292]
subset: PSI-MI_slim
synonym: "expression modif" EXACT PSI-MI-short []
is_a: MI:0787 ! genetic experimental form

[Term]
id: MI:0804
name: mutated gene
def: "The gene is mutated in some unknown manner" [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0787 ! genetic experimental form

[Term]
id: MI:0805
name: wwpdb
def: "The Worldwide Protein Data Bank (wwPDB) consists of organizations that act as deposition, data processing and distribution centers for PDB data. The founding members are RCSB PDB (USA), MSD-EBI (Europe) and PDBj (Japan). The BMRB (USA) group joined the wwPDB in 2006. The mission of the wwPDB is to maintain a single Protein Data Bank Archive of macromolecular structural data that is freely and publicly available to the global community.\nhttp://www.wwpdb.org/" [PMID:14634627]
subset: Drugable
subset: PSI-MI_slim
synonym: "wwPDB" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "[0-9][a-zA-Z0-9]{3}"
xref: search-url: "http://www.pdbe.org/${ac}"
is_a: MI:0447 ! feature database
is_a: MI:0461 ! interaction database
is_a: MI:0489 ! source database

[Term]
id: MI:0806
name: pdbj
def: "PDBj(Protein Data Bank Japan) maintains the database for the protein structures with financial assistance from the Institute for Bioinformatics Research and Development of Japan Science and Technology Corporation(BIRD-JST), collaborating with the Research Collaboration for Structural Bioinformatics(RCSB) and the MSD in the European Bioinformatics Institute(MSD-EBI) in EU. All three organizations serve as deposition, data processing and distribution sites.\nhttp://www.pdbj.org/" [PMID:12099029]
subset: PSI-MI_slim
synonym: "PDBj" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "[0-9][a-zA-Z0-9]{3}"
xref: search-url: "http://pdbjs3.protein.osaka-u.ac.jp/xPSSS/DetailServlet?PDBID=${ac}&PAGEID=Summary"
is_a: MI:0805 ! wwpdb

[Term]
id: MI:0807
name: comigration in gel electrophoresis
def: "The interaction of two or more molecules is determined by their very close proximity or the overlap of their respective bands in a gel." [PMID:14755292]
subset: PSI-MI_slim
synonym: "comigration in gel" EXACT PSI-MI-short []
is_a: MI:0982 ! electrophoretic mobility-based method

[Term]
id: MI:0808
name: comigration in sds page
def: "A method allowing the detection of strong interactions between two or more molecules as running, all of them, within a single band in a denaturing gel." [PMID:14755292, PMID:16732283]
subset: PSI-MI_slim
synonym: "comigration in sds" EXACT PSI-MI-short []
is_a: MI:0807 ! comigration in gel electrophoresis

[Term]
id: MI:0809
name: bimolecular fluorescence complementation
alt_id: MI:0229
def: "The bimolecular fluorescence complementation (BiFC) is an assay for determination of protein interactions and/or their location in living cells. This approach is based on complementation between two non- fluorescent fragments of a protein fluorophore such as green fluorescent protein (GFP) or its derivatives. Interactions between proteins fused to each fragment bring the fragments together resulting in the reconstitution of a fully functional flourophore that can be identified through fluorescence spectroscopy or microscopy." [PMID:11983170]
subset: PSI-MI_slim
synonym: "bifc" EXACT PSI-MI-short []
synonym: "gfp complementation" EXACT []
synonym: "green fluorescence protein complementation assay" EXACT []
is_a: MI:0051 ! fluorescence technology
is_a: MI:0090 ! protein complementation assay

[Term]
id: MI:0810
name: substitution analysis
def: "In this approach, once a molecule is demonstrated to participate in an interaction, several substitution mutants are produced and tested in the binding assay to identify the residues which identity is crucial for the interaction." [PMID:14755292]
subset: PSI-MI_slim
synonym: "substitut analysis" EXACT PSI-MI-short []
is_a: MI:0074 ! mutation analysis

[Term]
id: MI:0811
name: insertion analysis
def: "In this approach, once a molecule is demonstrated to participate in an interaction, several insertion derivatives are produced and tested in the binding assay to detect the regions that are important for the interaction." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0074 ! mutation analysis

[Term]
id: MI:0812
name: calmodulin binding protein tag
def: "The protein is expressed and purified as a fusion to the calmoduling-binding protein. The fusion protein can be purified by affinity chromatography using a calmodulin resin." [PMID:14755292]
subset: PSI-MI_slim
synonym: "cam  tag" EXACT PSI-MI-short []
is_a: MI:0240 ! fusion protein

[Term]
id: MI:0813
name: proximity ligation assay
def: "Upon binding of two proximity probes (usually antibodies conjugated to DNA) to the same target protein complex, the oligonucleotides on the proximity probes are brought close together. These antibody-conjugated oligonucleotides hybridize to two connector oligonucleotides that are ligated to form a circular DNA molecule. This newly formed DNA-molecule can be amplified by rolling circle amplification. The resulting single-stranded DNA-molecule collapses into a bundle, which is detectable through hybridization of fluorescently labeled complementary oligonucleotides." [PMID:15155907, PMID:\:17072308]
subset: PSI-MI_slim
synonym: "in situ proximity ligation assay" RELATED []
synonym: "p elisa" EXACT []
synonym: "pELISA" EXACT PSI-MI-alternate []
synonym: "PLA" EXACT PSI-MI-short []
synonym: "pLISA" RELATED []
synonym: "proximity ligation" RELATED []
is_a: MI:0400 ! affinity technology
is_a: MI:0421 ! identification by antibody

[Term]
id: MI:0814
name: protease accessibility laddering
def: "In protease accessibility laddering (PAL) tagged proteins are purified on magnetic beads in their natively folded  state. While attached to the beads, proteins are probed with proteases. Proteolytic fragments are eluted and detected by immunoblotting with antibodies against the tag (e.g., Protein A, GFP, and 6xHis)." [PMID:16615907]
subset: PSI-MI_slim
synonym: "pal" EXACT PSI-MI-alternate []
synonym: "protease access" EXACT PSI-MI-short []
is_a: MI:0605 ! enzymatic footprinting

[Term]
id: MI:0815
name: confirmation by molecular weight
def: "Molecule whose sequence identity is derived from their molecular weight" [PMID:14755292]
subset: PSI-MI_slim
synonym: "weight identificat" EXACT PSI-MI-short []
is_a: MI:0396 ! predetermined participant

[Term]
id: MI:0816
name: molecular weight estimation by staining
def: "Molecule whose sequence identity is derived from their molecular weight after a comigration in a gel with molecular weight marker." [PMID:14755292]
subset: PSI-MI_slim
synonym: "weight by staining" EXACT PSI-MI-short []
is_a: MI:0815 ! confirmation by molecular weight

[Term]
id: MI:0817
name: molecular weight estimation by silver staining
def: "Molecule whose sequence identity is derived from their molecular weight after a comigration in a gel with molecular weight marker and staining of the molecules with silver." [PMID:14755292]
subset: PSI-MI_slim
synonym: "weight silver stain" EXACT PSI-MI-short []
is_a: MI:0816 ! molecular weight estimation by staining

[Term]
id: MI:0818
name: molecular weight estimation by coomasie staining
def: "Molecule whose sequence identity is derived from their molecular weight after a comigration in a gel with molecular weight marker and staining of the molecules with comassie dye." [PMID:14755292]
subset: PSI-MI_slim
synonym: "weight by comassie" EXACT PSI-MI-short []
is_a: MI:0816 ! molecular weight estimation by staining

[Term]
id: MI:0819
name: molecular weight estimation by bromide staining
def: "Molecule whose sequence identity is derived from their molecular weight after a comigration in a gel with molecular weight marker and staining of the molecules with bromide dyes." [PMID:14755292]
subset: PSI-MI_slim
synonym: "weight by bromide" EXACT PSI-MI-short []
is_a: MI:0816 ! molecular weight estimation by staining

[Term]
id: MI:0820
name: molecular weight estimation by sybr staining
def: "Molecule whose sequence identity is derived from their molecular weight after a comigration in a gel with molecular weight marker and staining of the molecules with sybr dyes." [PMID:14755292]
subset: PSI-MI_slim
synonym: "safe DNA gel stain" EXACT PSI-MI-alternate []
synonym: "weight by sybr" EXACT PSI-MI-short []
is_a: MI:0816 ! molecular weight estimation by staining

[Term]
id: MI:0821
name: molecular weight estimation by autoradiography
def: "Molecule whose sequence identity is derived from their molecular weight after a comigration in a gel with molecular weight marker and staining by autoradiography." [PMID:14755292]
subset: PSI-MI_slim
synonym: "weight autoradiogra" EXACT PSI-MI-short []
is_a: MI:0815 ! confirmation by molecular weight

[Term]
id: MI:0822
name: molecular weight estimation by hoechst staining
def: "Molecule whose sequence identity is derived from their molecular weight after a comigration in a gel with molecular weight marker and staining of the molecules with Hoechst dyes." [PMID:14755292]
subset: PSI-MI_slim
synonym: "weight by hoechst" EXACT PSI-MI-short []
is_a: MI:0816 ! molecular weight estimation by staining

[Term]
id: MI:0823
name: predetermined feature
def: "Feature detection not verified in the context of an experiment but assumed from external or previous experimental evidence(s)." [PMID:14755292]
subset: PSI-MI_slim
synonym: "predetermined featur" EXACT PSI-MI-short []
is_a: MI:0093 ! protein sequence identification
is_a: MI:0427 ! Identification by mass spectrometry
is_a: MI:0659 ! experimental feature detection

[Term]
id: MI:0824
name: x-ray powder diffraction
def: "Analysis of a diffraction pattern generated by an isotropic sample composed of many randomly oriented crystals." [PMID:14755292]
subset: PSI-MI_slim
synonym: "X-ray" EXACT PSI-MI-alternate []
synonym: "x-ray powder diffrac" EXACT PSI-MI-short []
is_a: MI:0114 ! x-ray crystallography

[Term]
id: MI:0825
name: x-ray fiber diffraction
def: "Analysis of the diffraction pattern of a partially ordered sample composed of fibers oriented parallel to each other using X-ray." [PMID:14755292]
subset: PSI-MI_slim
synonym: "X-ray" EXACT PSI-MI-alternate []
synonym: "x-ray fiber diffrac" EXACT PSI-MI-short []
is_a: MI:0114 ! x-ray crystallography

[Term]
id: MI:0826
name: x ray scattering
def: "Method where the internal structure of a sample is derived from the intensity distribution of the scattered monochromatic X-ray beam at very low scattering angles." [PMID:14755292]
subset: PSI-MI_slim
synonym: "saxs" EXACT PSI-MI-short []
is_a: MI:0067 ! light scattering

[Term]
id: MI:0827
name: x-ray tomography
def: "X-ray Tomography is a branch of X-ray microscopy. A series of projection images are used to calculate a three dimensional reconstruction of an object. The technique has found many applications in materials science and later in biology and biomedical research. In terms of the latter, the National Center for X-ray Tomography (NCXT) is one of the principle developers of this technology, in particular for imaging whole, hydrated cells." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0428 ! imaging technique

[Term]
id: MI:0828
name: polyprotein fragment
def: "Subpart of a polyprotein that is naturally cleaved in vivo." [PMID:14577292]
subset: PSI-MI_slim
synonym: "chain" RELATED []
synonym: "polyprotein frag" EXACT PSI-MI-short []
is_a: MI:0252 ! biological feature

[Term]
id: MI:0829
name: multiple parent reference
def: "This qualifier is used  for hybrid or composite molecules with more than one cross-reference to parent molecules." [PMID:14755292]
subset: PSI-MI_slim
synonym: "multiple parent" EXACT PSI-MI-short []
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:0830
name: tissue list
def: "List of tissue used as  topic in UniProt RC line.\nhttp://www.expasy.org/cgi-bin/lists?tisslist.txt" [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0473 ! participant database

[Term]
id: MI:0831
name: cell ontology
def: "Ontology of cell types.\nhttp://obo.sourceforge.net/cgi-bin/detail.cgi?cell" [PMID:16381901]
subset: PSI-MI_slim
is_a: MI:0473 ! participant database

[Term]
id: MI:0832
name: half cystine
def: "A protein modification that is effectively either one half of a cystine cross-link, or a cysteine residue with one hydrogen atom or proton removed" [MOD:00798, RESID:AA0025]
synonym: "Half of a disulfide bridge" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:0833
name: autoradiography
def: "Experimental method by which radiolabel is detected by exposure to a photographic emulsion forming a pattern on the film." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0659 ! experimental feature detection
is_a: MI:0866 ! tag visualisation

[Term]
id: MI:0834
name: ka
def: "Association rate constant or rate of complex formation. Unit MOLE per SECOND (M-1 s-1)" [PMID:14755292]
subset: PSI-MI_slim
synonym: "kon" EXACT PSI-MI-short []
is_a: MI:0640 ! parameter type

[Term]
id: MI:0835
name: koff
def: "Dissociation rate constant measuring the stability of a complex. Unit SECOND (s-1)" [PMID:14755292]
subset: PSI-MI_slim
synonym: "Kd" RELATED []
synonym: "koff" EXACT PSI-MI-short []
is_a: MI:0640 ! parameter type

[Term]
id: MI:0836
name: temperature of interaction
def: "Temperature at which interaction was determined. Unit KELVIN (K)" [PMID:14755292]
subset: PSI-MI_slim
synonym: "T interaction" EXACT PSI-MI-alternate []
synonym: "temp interaction" EXACT PSI-MI-short []
synonym: "Tint" EXACT PSI-MI-alternate []
is_a: MI:0640 ! parameter type

[Term]
id: MI:0837
name: pH of interaction
def: "pH at which interaction was determined." [PMID:14755292]
subset: PSI-MI_slim
synonym: "pHint" EXACT PSI-MI-alternate []
is_a: MI:0640 ! parameter type

[Term]
id: MI:0838
name: kelvin
def: "The kelvin (K) is the SI unit of thermodynamic temperature. It is defined by taking the fixed numerical value of the Boltzmann constant k to be 1.380649×10-23 when expressed in the unit J·K-1, which is equal to kg·m2·s-2·K-1, where the kilogram, metre and second are defined in terms of h, c and caesium frequency. It is equivalent to -273.15°C / -459.67°F." [PMID:14755292]
subset: PSI-MI_slim
synonym: "K" EXACT PSI-MI-alternate []
is_a: MI:0647 ! parameter unit

[Term]
id: MI:0839
name: per mole per second
def: "Per mole per second, unit for association rate constant." [PMID:14755292]
subset: PSI-MI_slim
synonym: "M-1s-1" EXACT PSI-MI-alternate []
is_a: MI:0647 ! parameter unit

[Term]
id: MI:0840
name: stimulator
def: "Molecule stimulating an interaction by interacting with one or more of the participants." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:2274 ! regulator

[Term]
id: MI:0841
name: phosphotransferase assay
def: "Measures the rate of a phosphate transfer between two molecules." [PMID:14755292]
subset: PSI-MI_slim
synonym: "phosphotransfer assay" RELATED []
synonym: "phosphotransferase" EXACT PSI-MI-short []
is_a: MI:0415 ! enzymatic study

[Term]
id: MI:0842
name: phosphate donor
def: "Any molecule that is able to transfer a phosphate group to another chemical species." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0918 ! donor

[Term]
id: MI:0843
name: phosphate acceptor
def: "Molecule to which a phosphate group may be transferred from a phosphate donor." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0919 ! acceptor

[Term]
id: MI:0844
name: phosphotransfer reaction
def: "Reaction where a phosphate is transferred between two proteins of a phosphorelay system." [PMID:14755292, PMID:16712436]
subset: PSI-MI_slim
synonym: "phosphotransfer" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction

[Term]
id: MI:0845
name: spin label
def: "Paramagnetic fragment, most often a cyclic nitroxide derivative, covalently attached to a molecule of interest." [PMID:10966640]
subset: PSI-MI_slim
is_a: MI:0505 ! experimental feature

[Term]
id: MI:0846
name: r1 spin label
def: "Paramagnetic molecule (1-oxyl-2,2,5,5-tetramethylpyrroline-\n3-methyl)-methanethiosulfonate. that can be covalently attached to any cysteine aminoacid producing a nitroxide\nside chain designated R1." [PMID:10966640]
subset: PSI-MI_slim
is_a: MI:0845 ! spin label

[Term]
id: MI:0847
name: dansyl label
def: "Dansyl is the acronym of 5-dimethylaminonaphthalene-1-sulfonyl radical group reacting with any NH2 groups." [PMID:14755292]
subset: PSI-MI_slim
synonym: "5-dimethylaminonaphthalene-1-sulfonyl tag" EXACT PSI-MI-alternate []
synonym: "dansyl tag" EXACT PSI-MI-alternate []
is_a: MI:0857 ! fluorescent dye label

[Term]
id: MI:0848
name: 125i radiolabel
def: "Molecule labelled with 125 radio isotope of iodine atoms." [PMID:14755292]
subset: PSI-MI_slim
synonym: "125I" EXACT PSI-MI-alternate []
synonym: "I125" EXACT PSI-MI-alternate []
is_a: MI:0517 ! radiolabel

[Term]
id: MI:0849
name: ncbi taxonomy
def: "The NCBI taxonomy database indexes over 55 000 organisms that are represented in the sequence databases with at least one nucleotide or protein sequence. The Taxonomy Browser can be used to view the taxonomic position or retrieve sequence and structural data for a particular organism or group of organisms. Searches of the NCBI taxonomy may be made on the basis of whole or partial organism names, and direct links to organisms commonly used in biological research are also provided. The Taxonomy Browser can also be used to display the number of nucleic acid sequences, protein sequences, and protein structures available for organisms included in the branch. From the data display for a particular organism, one can retrieve and download the sequence data for that organism, or protein 3D structure data if available.\nhttp://www.ncbi.nlm.nih.gov/Taxonomy/" [PMID:10592169]
subset: PSI-MI_slim
xref: id-validation-regexp: "[0-9]+"
xref: search-url: "http://www.ncbi.nlm.nih.gov/Taxonomy/Browser/wwwtax.cgi?mode=Info&id=${ac}&lvl=3&lin=f&keep=1&srchmode=1&unlock"
is_a: MI:0473 ! participant database

[Term]
id: MI:0850
name: encode
def: "ENCODE (the Encyclopedia Of DNA Elements) seeks to identify all protein-coding genes. The current ENCODE data set is derived from 1% of the human genome and has been selected for analysis in the pilot phase of the project.\nhttp://www.genome.gov/10005107" [PMID:17372197]
subset: PSI-MI_slim
synonym: "ENCODE" EXACT PSI-MI-alternate []
synonym: "Encyclopedia Of DNA Elements" EXACT PSI-MI-alternate []
is_a: MI:1094 ! genome databases

[Term]
id: MI:0851
name: protein genbank identifier
def: "GenBank Identifier or GI numbers for proteins." [PMID:17170002]
subset: PSI-MI_slim
synonym: "GenBank Protein GI" EXACT PSI-MI-alternate []
synonym: "genbank protein gi" EXACT PSI-MI-alternate []
synonym: "genbank_protein_gi" EXACT PSI-MI-short []
synonym: "genpept id" EXACT []
xref: id-validation-regexp: "[0-9]+"
xref: search-url: "http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?db=protein&cmd=Retrieve&dopt=Graphics&list_uids=${ac}"
is_a: MI:0860 ! genbank identifier

[Term]
id: MI:0852
name: nucleotide genbank identifier
def: "GenBank Identifier or GI numbers for nucleotide." [PMID:17170002]
subset: PSI-MI_slim
synonym: "genbank nucleotide" EXACT PSI-MI-alternate []
synonym: "GenBank Nucleotide" EXACT PSI-MI-alternate []
synonym: "genbank_nucl_gi" EXACT PSI-MI-short []
xref: id-validation-regexp: "[0-9]+"
xref: search-url: "http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?db=nucleotide&cmd=Retrieve&dopt=Graphics&list_uids=$"
is_a: MI:0860 ! genbank identifier

[Term]
id: MI:0853
name: dna overhang
def: "An overhang is a stretch of unpaired nucleotides in the end of a DNA molecule. These unpaired nucleotides can be in either strand, creating either 3' or 5' overhangs. Longer overhangs are called cohessive ends or sticky ends. They are most often created by restriction endonucleases when they cut DNA. Very often they cut the two DNA strands four base pairs from each other, creating a four-base 3' overhang in the other molecule and a complementary 5' overhang in the other. These ends are called cohessive since they are easily joined back together by a ligase" [PMID:14755292]
subset: PSI-MI_slim
synonym: "cohessive ends" EXACT PSI-MI-alternate []
synonym: "sticky ends" EXACT PSI-MI-alternate []
is_a: MI:0505 ! experimental feature

[Term]
id: MI:0854
name: 3 prime overhang
def: "An overhang is a stretch of unpaired nucleotides in the end of a 3' strand of a DNA molecule." [PMID:14755292]
subset: PSI-MI_slim
synonym: "3 prime sticky end" EXACT PSI-MI-alternate []
is_a: MI:0853 ! dna overhang

[Term]
id: MI:0855
name: 5 prime overhang
def: "An overhang is a stretch of unpaired nucleotides in the end of a 5' strand of a DNA molecule." [PMID:14755292]
subset: PSI-MI_slim
synonym: "5 prime sticky end" EXACT PSI-MI-alternate []
is_a: MI:0853 ! dna overhang

[Term]
id: MI:0856
name: fluorophore
def: "A fluorophore is a component of a molecule which causes a molecule to be fluorescent. It is a functional group in a molecule which will absorb energy of a specific wavelength and re-emit energy at a different (but equally specific) wavelength. The amount and wavelength of the emitted energy depend on both the fluorophore and the chemical environment of the fluorophore." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0505 ! experimental feature

[Term]
id: MI:0857
name: fluorescent dye label
def: "Dye label containing a  fluorophore  which  absorb energy of a specific wavelength and re-emit energy at a different (but equally specific) wavelength." [PMID:14755292]
subset: PSI-MI_slim
synonym: "fluorescent dye" EXACT PSI-MI-short []
is_a: MI:0373 ! dye label
is_a: MI:0856 ! fluorophore

[Term]
id: MI:0858
name: immunodepleted coimmunoprecipitation
def: "Method involving consecutive coimmunoimmunoprecipitations on the same sample, a control  where an interaction is detected, and other CoIPs where the sample is previously treated with a specific antibody that precipitates a candidate interactor and leads to the suppression of an interaction or a change in composition of a complex." [PMID:17081976]
subset: PSI-MI_slim
synonym: "immunodepleted coip" EXACT PSI-MI-alternate []
synonym: "immunodepletion" EXACT PSI-MI-short []
is_a: MI:0019 ! coimmunoprecipitation

[Term]
id: MI:0859
name: force spectroscopy
def: "A single-molecule technique that measures the behavior of a molecular complex under stretching or torsional mechanical force." [PMID:18511917]
synonym: "force measurement" RELATED []
synonym: "intermolecular force" EXACT PSI-MI-alternate []
synonym: "molecular force measurement" RELATED []
synonym: "single molecule force measurement" RELATED []
synonym: "surface adhesion force measurement" RELATED []
is_a: MI:0013 ! biophysical
is_a: MI:2318 ! force measurement

[Term]
id: MI:0860
name: genbank identifier
def: " edit" [PMID:15078858]
subset: PSI-MI_slim
xref: id-validation-regexp: "ENS[A-Z]+[0-9]{11}"
is_a: MI:0683 ! sequence database

[Term]
id: MI:0861
name: protein a tag
def: "The protein A is a bacterial cell wall  isolated from Staphylococcus aureus that  binds to mammalian IgGs mainly through Fc regions. The protein A can be use to retaint antibodies or as fusion tag of a protein under analysis." [PMID:14755292]
subset: PSI-MI_slim
synonym: "protein A" EXACT PSI-MI-alternate []
is_a: MI:0240 ! fusion protein

[Term]
id: MI:0862
name: zz tag
def: "The ZZ tag is a tag made out of two tandem repeats of the Protein A IgG binding domain. " [PMID:11694505]
subset: PSI-MI_slim
synonym: "ZZ tag" EXACT PSI-MI-alternate []
is_a: MI:0861 ! protein a tag

[Term]
id: MI:0863
name: thiol reactive lanthanide label
def: "Thiol-reactive lanthanide complexes have been synthesized that are luminescent when bound to terbium and/or europium. The Tb3+-DTPA-cs124-EMCH complexes consist of a diethylenetriaminepentaacetate (DTPA) chelate covalently joined through one amide bond to a chromophore, carbostyril 124, and via a second amide bond to a maleimide, bromoacetamide, or pyridyldithio moiety. This label can be Site-specific attached to both proteins and DNA." [PMID:10077482]
subset: PSI-MI_slim
synonym: "Tb3+-DTPA-cs124-EMCH" EXACT PSI-MI-alternate []
synonym: "thiol lanthanide" EXACT PSI-MI-short []
is_a: MI:1256 ! luminscent dye label

[Term]
id: MI:0864
name: brenda
def: "A structured controlled vocabulary for the source of an enzyme. It comprises terms for tissues, cell lines, cell types and cell cultures from uni- and multicellular organisms.\nhttp://www.brenda-enzymes.info" [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0473 ! participant database

[Term]
id: MI:0865
name: fluorescence acceptor donor pair
def: "Pair of fluorophores attached to the same molecule used in a fret  experiment to observe the details of conformational  changes." [PMID:14755292]
subset: PSI-MI_slim
synonym: "fret pair" EXACT PSI-MI-short []
is_a: MI:2336 ! luminescence acceptor donor pair

[Term]
id: MI:0866
name: tag visualisation
def: "Molecule whose sequence identity is not checked after the interaction but its presence is detected through its tag." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0396 ! predetermined participant

[Term]
id: MI:0867
name: tag visualisation by fluorescence
def: "The molecule is produced fused to a tag containing a fluorophore, such as GFP tagged to a recombinant protein, or a fluorophore has been chemically attached to the molecule. Subsequence observation or measurement of fluorescence is used to identify the presence of the molecule in an interaction." [PMID:14755292]
subset: PSI-MI_slim
synonym: "tag fluorescence" EXACT PSI-MI-short []
is_a: MI:0866 ! tag visualisation

[Term]
id: MI:0868
name: author identifier
def: "Author published identifier." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:0869
name: originally assigned identifier
def: "Identifier assigned when the record was created by a source database." [PMID:14755292]
subset: PSI-MI_slim
synonym: "original identifier" EXACT PSI-MI-short []
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:0870
name: demethylase assay
def: "Measures the catalysis of the hydrolysis of an methyl group from a substrate molecule." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0415 ! enzymatic study

[Term]
id: MI:0871
name: demethylation reaction
def: "The cleavage of a methyl group from a polypeptide. Methylation is generally an irreversible reaction except in mamalian." [GO:0006482, PMID:17277772]
subset: PSI-MI_slim
synonym: "demethylation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction

[Term]
id: MI:0872
name: atomic force microscopy
def: "The atomic force microscope (AFM) is a very high-resolution type of scanning probe microscope, with demonstrated resolution of fractions of a nanometer, more than 1000 times better than the optical diffraction limit. The AFM was invented by Binnig, Quate and Gerber in 1986, and is one of the foremost tools for imaging, measuring and manipulating matter at the nanoscale.The term 'microscope' in the name is actually a misnomer because it implies looking, while in fact the information is gathered by feeling out the surface with a mechanical feeler.\nhttp://en.wikipedia.org/wiki/Atomic_force_microscope" [PMID:17502105]
subset: PSI-MI_slim
synonym: "AFM" EXACT PSI-MI-alternate []
synonym: "atomic force microsc" EXACT PSI-MI-short []
is_a: MI:0428 ! imaging technique

[Term]
id: MI:0873
name: curation request
def: "Annotation of a published paper which has been externally requested." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1093 ! bibliographic attribute name

[Term]
id: MI:0875
name: dataset
def: "Targeted curation dataset grouping experiments by topic or dataset origin." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1093 ! bibliographic attribute name

[Term]
id: MI:0878
name: author submitted
def: "Data directly submitted by the authors to a database prior to publication." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0665 ! experiment attribute name

[Term]
id: MI:0879
name: nucleoside triphosphatase assay
def: "Measures the catalysis of the hydrolysis of a nucleoside triphosphate into a nucleoside diphosphate plus phosphate." [PMID:14755292]
subset: PSI-MI_slim
synonym: "triphosphatase ass" EXACT PSI-MI-short []
is_a: MI:0415 ! enzymatic study
is_a: MI:0434 ! phosphatase assay

[Term]
id: MI:0880
name: atpase assay
def: "Measures the catalysis of the hydrolysis of ATP+ H2O = ADP + phosphate." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0879 ! nucleoside triphosphatase assay

[Term]
id: MI:0881
name: nucleoside triphosphatase reaction
def: "Catalysis of the hydrolysis of a  nucleoside triphosphate into a nucleoside diphosphate plus phosphate." [GO:0017111, PMID:14755292]
subset: PSI-MI_slim
synonym: "triphosphatase react" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction

[Term]
id: MI:0882
name: atpase reaction
def: "Catalysis of the hydrolisis of ATP+ H2O = ADP + phosphate." [GO:0016887, PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0881 ! nucleoside triphosphatase reaction

[Term]
id: MI:0883
name: gtpase reaction
def: "Catalysis of the hydrolisis of GTP+ H2O = GDP + phosphate." [GO:0003924, PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0881 ! nucleoside triphosphatase reaction

[Term]
id: MI:0884
name: vsv tag
def: "Epitope tag derived from vesicular stomatitis virus (VSV) glycoprotein. The tag sequence is YTDIEMNRLGK and many antibodies against it are commercially available." [PMID:14755292]
subset: PSI-MI_slim
synonym: "vesicular stomatitis virus tag" EXACT PSI-MI-alternate []
is_a: MI:0507 ! tag

[Term]
id: MI:0885
name: journal
def: "Name and details of a journal from which paper has been taken." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1093 ! bibliographic attribute name

[Term]
id: MI:0886
name: publication year
def: "Year of publication of a paper." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1093 ! bibliographic attribute name

[Term]
id: MI:0887
name: histone acetylase assay
def: "In histone acetylation the histones are acetylated on lysine residues in the N-terminal tail as part of gene regulation. Typically, these reactions are catalyzed by enzymes with \"histone acetyltransferase\" (HAt)" [PMID:14755292]
subset: PSI-MI_slim
synonym: "HAt" EXACT PSI-MI-alternate []
synonym: "hat" EXACT PSI-MI-short []
synonym: "histone acetylation" RELATED []
is_a: MI:0889 ! acetylase assay

[Term]
id: MI:0888
name: small angle neutron scattering
def: "During a SANS experiment a beam of neutrons is directed at a sample. The neutrons are elastically scattered by a sample and the resulting scattering pattern is analyzed to provide information about the size, shape and orientation of some component of the sample." [PMID:11578931]
subset: PSI-MI_slim
synonym: "SANS" EXACT PSI-MI-alternate []
synonym: "sans" EXACT PSI-MI-short []
is_a: MI:0013 ! biophysical

[Term]
id: MI:0889
name: acetylase assay
def: "Measures the catalysis of the addition of an acetyl group to a target molecule." [PMID:14755292]
subset: PSI-MI_slim
synonym: "acetylation" RELATED []
is_a: MI:0415 ! enzymatic study

[Term]
id: MI:0890
name: qdot
def: "Qdot are nanocrystals fluorophores . Nanocrystals a are extremely efficient materials for generating and they have a highly customizable surface for directing their bioactivity, producing a fluorescent probe that outperforms traditional dyes in many fluorescence applications." [PMID:17569782]
subset: PSI-MI_slim
is_a: MI:0857 ! fluorescent dye label

[Term]
id: MI:0891
name: neutron fiber diffraction
def: "Analysis of diffraction pattern of a partially ordered sample composed of fibers oriented parallel to each other using neutron beam." [PMID:10771422, PMID:15272083, PMID:15546977, PMID:15914673, PMID:16041074, PMID:16707576]
subset: PSI-MI_slim
synonym: "neutron fiber diff" EXACT PSI-MI-short []
is_a: MI:0013 ! biophysical

[Term]
id: MI:0892
name: solid phase assay
def: "Assay where at least one molecule under analysis is bound to a solid surface, such as a microplate wall or the sides of a tube, the other reactants being free in solution." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0400 ! affinity technology

[Term]
id: MI:0893
name: neutron diffraction
def: "Analysis of diffraction pattern using neutron beam" [PMID:10771422, PMID:15272083, PMID:15546977, PMID:15914673, PMID:16041074, PMID:16707576]
subset: PSI-MI_slim
is_a: MI:0013 ! biophysical

[Term]
id: MI:0894
name: electron diffraction
def: "Analysis of diffraction pattern using electron beam." [PMID:10949309, PMID:11034202, PMID:11171962, PMID:11532455, PMID:11700061, PMID:15141214, PMID:16325200]
subset: PSI-MI_slim
is_a: MI:0013 ! biophysical

[Term]
id: MI:0895
name: protein kinase A complementation
def: "This method uses Renilla luciferase (Rluc)-based protein fragment complementation assay (PCA) that is designed specifically to investigate dynamic protein complexes (association and dissociation). It is chose to generate a PCA based on the Rluc, which is, because of its simplicity and sensitivity, a widely used bioluminescence reporter. The general scheme for construction and detection of the Rluc-PCA PKA sensor consists of fusing complementary fragments of Rluc to the regulatory (Reg) and catalytic (Cat) PKA subunits of PKA." [PMID:17942691]
subset: PSI-MI_slim
synonym: "pka complementation" EXACT PSI-MI-short []
is_a: MI:0090 ! protein complementation assay

[Term]
id: MI:0896
name: renilla luciferase protein tag
def: "Renilla luciferase, is an enzyme of the sea pansy catalyzing the oxidation of the coelenterazine pigment)  that produces light. Renilla luciferase produces a blue light of 480nm." [PMID:14755292]
subset: PSI-MI_slim
synonym: "renilla luciferase" EXACT PSI-MI-short []
is_a: MI:1205 ! luciferase tag

[Term]
id: MI:0897
name: protein modification ontology
def: "Catalogue of covalent modification of, or a change resulting in an alteration of the measured molecular mass of, a peptide or protein amino acid residue." [PMID:14755292]
subset: PSI-MI_slim
synonym: "psi-mod" EXACT PSI-MI-short []
xref: id-validation-regexp: "MOD:[0-9]{5}"
is_a: MI:0447 ! feature database

[Term]
id: MI:0898
name: putative self
def: "Molecule that is reported to self-interact but the experimental condition does not allow to resolve whether the interaction is intramolecular (true self interaction) or intermolecular (homodimer)." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0495 ! experimental role
is_a: MI:0500 ! biological role

[Term]
id: MI:0899
name: p3 filamentous phage display
def: "pIII is one of the minor coat proteins that decorates in five copies the emerging tip of filamentous phage. Similarly to pVIII pIII also tolerates peptide insertions at the amino-terminus. The sequences to be displayed can either be encoded in the phage copy of the coat gene or in an extra pIII gene copy carried on a phagemid. In the first case 5 copies o the hybrid proteins are displayed while in the latter only a few capsid display one copy and the majority display none.  Because of the low copy number pIII display is often referred to as low valency display." [PMID:1696028]
subset: PSI-MI_slim
synonym: "low valency display" EXACT PSI-MI-alternate []
synonym: "p3 filamentous phage" EXACT PSI-MI-short []
is_a: MI:0048 ! filamentous phage display

[Term]
id: MI:0900
name: p8 filamentous phage display
def: "pVIII is the major coat protein of filamentous phage. Its amino-terminus is exposed to solvent and tolerates the insertion of relatively large peptide fragments. By inserting the peptide coding sequence into the phage copy of the pVIII gene up to 3000 copies of the hybrid proteins can be displayed along the phage capsid. Alternatively the hybrid protein can be encoded on a phagemid that is incorporated in a virus like particle by infection with a helper phage. In this latter case one obtains a chimeric capsid where hybrid proteins are interspersed at different density in an otherwise wild type coat. Because of the high copy number pVIII display is also referred to as high valency display." [PMID:1720463]
subset: PSI-MI_slim
synonym: "high valency display" EXACT PSI-MI-alternate []
synonym: "p8 filamentous phage" EXACT PSI-MI-short []
is_a: MI:0048 ! filamentous phage display

[Term]
id: MI:0901
name: isotope label footprinting
def: "Exposed amino acid residues undergo a rapid exchange of a specific radio-isotope e.g. hydrogen/deuterium. Residues involved in a molecular interaction are protected from this exchange and exhibit a much slower rate of exchange. This method of binding range identification must be coupled to NMR or mass spectrometry  technologies in order to detect the radio-isotope exchange." [PMID:18184591]
subset: PSI-MI_slim
synonym: "isotope footprinting" EXACT PSI-MI-short []
is_a: MI:0605 ! enzymatic footprinting

[Term]
id: MI:0902
name: rna cleavage
def: "Any process by which an RNA molecule is cleaved at specific sites or in a regulated manner." [GO:0006396, PMID:14681407]
subset: PSI-MI_slim
is_a: MI:0910 ! nucleic acid cleavage

[Term]
id: MI:0903
name: mpidb
def: "The microbial protein-protein interactions database (MPDIB) aims to collect and provide all known physical prokaryotic interactions. Note as of 2013, this database is no longer active, but all IMEx curation was imported and is now maintained by the IntAct database (www.ebi.ac.uk/intact)." [PMID:14755292]
subset: PSI-MI_slim
synonym: "MPDIB" EXACT PSI-MI-alternate []
is_a: MI:0461 ! interaction database
is_a: MI:0973 ! imex source

[Term]
id: MI:0904
name: polysaccharide
def: "A polysaccharide is a complex polymer of carbohydrate monormers. They are polymers made up of many monosaccharides joined together by glycosidic bonds. They are therefore very large, often branched, macromolecules." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1100 ! bioactive entity

[Term]
id: MI:0905
name: amplified luminescent proximity homogeneous assay
def: "AlphaScreen relies on the use of Donor and Acceptor beads that are coated with a layer of hydrogel providing functional groups for bioconjugation. When a biological interaction between molecules brings the beads into proximity, a cascade of chemical reactions is initiated to produce a greatly amplified signal. Upon laser excitation, a photosensitizer in the Donor bead converts ambient oxygen to a more excited singlet state. The singlet state oxygen molecules diffuse across to react with a chemiluminescer in the Acceptor bead that further activates fluorophores contained within the same bead. The fluorophores subsequently emit light at 520-620 nm. In the absence of a specific biological interaction, the singlet state oxygen molecules produced by the Donor bead go undetected without the close proximity of the Acceptor bead. AlphaScreen has successfully been developed for enzyme assays (kinase, helicase, protease, ...), interaction assays (ligand/receptor, protein/protein, protein/DNA), immunoassays, and GPCR functional assays (cAMP, IP3)." [PMID:17092917]
subset: PSI-MI_slim
synonym: "alpha-screen" EXACT PSI-MI-short []
synonym: "AlphaScreen" EXACT PSI-MI-alternate []
is_a: MI:0051 ! fluorescence technology

[Term]
id: MI:0906
name: au1 tag
def: "The protein of interest is expressed as a fusion to the peptide DTYRYI for which antibodies are commercially available." [PMID:18216269]
subset: PSI-MI_slim
synonym: "DTYRYI epitope tag" EXACT PSI-MI-alternate []
is_a: MI:0507 ! tag

[Term]
id: MI:0907
name: conformational status
def: "Statement about the native/denatured conformation of the protein." [PMID:14755292]
subset: PSI-MI_slim
synonym: "conformation" EXACT PSI-MI-short []
is_a: MI:0346 ! experimental preparation

[Term]
id: MI:0908
name: denatured
def: "Altered conformation state of the protein as a result of heat or chemical modification resulting in a changed structure of the protein." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0907 ! conformational status

[Term]
id: MI:0909
name: native
def: "State of the protein without interference i.e. the natural form." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0907 ! conformational status

[Term]
id: MI:0910
name: nucleic acid cleavage
def: "Covalent bond breakage of a nucleic acid molecule leading to the formation of smaller fragments." [PMID:14755292]
subset: PSI-MI_slim
synonym: "ncl acid cleavage" EXACT PSI-MI-short []
is_a: MI:0194 ! cleavage reaction

[Term]
id: MI:0911
name: cross linker
def: "A variety of crosslinkers are used to analyze subunit structure of proteins, protein interactions and various parameters of protein function. Subunit structure is deduced since crosslinkers only bind surface amino residues in relatively close proximity in the native state. Protein interactions are often too weak or transient to be easily detected, but by crosslinking, the interactions can be captured and analyzed." [PMID:14755292]
subset: PSI-MI_slim
synonym: "crosslinker" EXACT PSI-MI-alternate []
is_a: MI:0505 ! experimental feature

[Term]
id: MI:0912
name: spdp cross linker
def: "N -Succinimidyl 3-(2-pyridyldithio)-propionate, is heterobifunctional, thiol-cleavable \nand membrane permeable crosslinkers. It contains an amine-reactive N-hydroxysuccinimide (NHS) ester \nthat will react with lysine residues to form a stable amide bond. The other end of the spacer arm is terminated in the pyridyl disulfide group that will react with sulfhydryls to form a reversible disulfide bond." [PMID:17360572]
subset: PSI-MI_slim
synonym: "N -Succinimidyl 3-(2-pyridyldithio)-propionate" EXACT PSI-MI-alternate []
is_a: MI:0911 ! cross linker

[Term]
id: MI:0913
name: lc-spdp cross linker
def: "Succinimidyl 6-(3-[2-pyridyldithio]-propionamido)hexanoate, is an heterobifunctional, thiol-cleavable \nand membrane permeable crosslinkers. It contains an amine-reactive N-hydroxysuccinimide (NHS) ester \nthat will react with lysine residues to form a stable amide bond. The other end of the spacer arm is terminated in the pyridyl disulfide group that will react with sulfhydryls to form a reversible disulfide bond. LC-SPDP is a derivative of the classical SPDP with a longer spacer arm." [PMID:17360572]
subset: PSI-MI_slim
synonym: "Succinimidyl 6-(3-[2-pyridyldithio]-propionamido)hexanoate" EXACT PSI-MI-alternate []
is_a: MI:0912 ! spdp cross linker

[Term]
id: MI:0914
name: association
def: "Interaction between molecules that may participate in formation of one, but possibly more, physical complexes. Often describes a set of molecules that are co-purified in a single pull-down or coimmunoprecipitation but might participate in formation of distinct physical complexes sharing a common bait." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:2232 ! molecular association

[Term]
id: MI:0915
name: physical association
def: "Interaction between molecules within the same physical complex. Often identified under conditions which suggest that the molecules are in close proximity but not necessarily in direct contact with each other." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0914 ! association

[Term]
id: MI:0916
name: lexa vp16 complementation
def: "Yeast two-hybrid system using Escherichia coli LexA amino acids 1-202 as the DNA-binding domain (BD), and a transcriptional activation domain from the herpes simplex virus protein VP16 (either aa 411-490 or aa 411-455) that can specifically activate transcription of a reporter gene located downstream." [PMID:9371806]
subset: PSI-MI_slim
synonym: "lexa vp16 complement" EXACT PSI-MI-short []
synonym: "LexA VP16 transcription complementation" EXACT PSI-MI-alternate []
is_a: MI:0018 ! two hybrid

[Term]
id: MI:0917
name: matrixdb
def: "Knowledgebase of the extracellular matrix storing experimentally determined interactions involving extracellular biomolecules. It includes protein-protein, protein-polysaccharide, and protein-lipid interactions." [PMID:19147664]
subset: PSI-MI_slim
synonym: "MatrixDB" EXACT PSI-MI-alternate []
xref: search-url: "http://matrixdb.univ-lyon1.fr/cgi-bin/current/newPort?type=biomolecule&value=${ac}"
is_a: MI:0461 ! interaction database
is_a: MI:0973 ! imex source

[Term]
id: MI:0918
name: donor
def: "Molecule which emits active chemical groups, electrons or ions that are transfered to an acceptor molecule." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0500 ! biological role

[Term]
id: MI:0919
name: acceptor
def: "Molecule able to receive active chemical groups, electrons or ions from a donor molecule." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0500 ! biological role

[Term]
id: MI:0920
name: ribonuclease assay
def: "Measures the catalysis of the hydrolysis of phosphodiester bonds in chains of RNA." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1034 ! nuclease assay

[Term]
id: MI:0921
name: surface plasmon resonance array
def: "This array technology allows the screening of binding abilities of hundreds or thousands of biomolecules (small molecule, peptide, protein, sugar, lipid, nucleic acid, and their fragments) printed onto the gold-coated chip by using an instrument (micro-arrayer) that is capable of spotting liquid samples in a reproducible manner onto a planar support. The ordered protein array can then be probed with a non-labelled sample (small molecule, peptide, protein, sugar, lipid, nucleic acid, and their fragments) to identify the baits that can bind to it.  This is done in real time, allowing direct measurement of both the on-rate and the off-rate and of the affinity constant of complex formation on each spot." [PMID:16510109, PMID:16837183, PMID:17889820]
subset: PSI-MI_slim
synonym: "Biacore Flexchip(r)" EXACT PSI-MI-alternate []
synonym: "spr array" EXACT PSI-MI-short []
synonym: "SPRi-Plex " EXACT PSI-MI-alternate []
synonym: "SPRImager" EXACT PSI-MI-alternate []
is_a: MI:0008 ! array technology
is_a: MI:0107 ! surface plasmon resonance

[Term]
id: MI:0922
name: imex evidence
def: "Experimental evidence supporting an interaction curated and released under the IMEx agreement." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:0923
name: irefindex
def: "iRefIndex provides an index of protein interactions available in a number of primary interaction databases including BIND, BioGRID, DIP, HPRD, IntAct, MINT, MPact, MPPI and OPHID.  This index allows the user to search for a protein and retrieve a non-redundant list of interactors for that protein. iRefIndex uses the Sequence Global Unique Identifier (SEGUID) to group proteins and interactions into redundant groups.  This method allows users to integrate their own data with the iRefIndex in a way that ensures proteins with the exact same sequence will be represented only once.\nhttp://irefindex.uio.no/" [PMID:18823568]
subset: PSI-MI_slim
synonym: "iRefIndex" EXACT PSI-MI-alternate []
is_a: MI:0461 ! interaction database
is_a: MI:0489 ! source database

[Term]
id: MI:0924
name: camjedb
def: "Camjedb is a comprehensive database for information on the genome of Campylobacter jejuni.\nhttp://www.sanger.ac.uk/Projects/C_jejuni/" [PMID:106882042]
subset: PSI-MI_slim
is_a: MI:1094 ! genome databases

[Term]
id: MI:0925
name: observed-ptm
def: "Post translational modification observed on a protein in the context of an interaction." [PMID:14755292]
subset: PSI-MI_slim
synonym: "observed ptm" EXACT PSI-MI-alternate []
synonym: "observed-ptm" EXACT PSI-MI-short []
is_a: MI:0668 ! feature attribute name

[Term]
id: MI:0926
name: fiash label
def: "This fluorescent label is a small ligand  membrane-permeant and nonfluorescent until it binds with high affinity and specificity to the tetracysteine domain. Such in situ labeling adds much less mass than does green fluorescent protein and offers greater versatility in attachment sites as well as potential spectroscopic and chemical properties." [PMID:9657724]
subset: PSI-MI_slim
synonym: "4',5'-bis(1,3,2-dithioarsolan-2-yl)fluorescein " EXACT PSI-MI-alternate []
synonym: "FIAsH label" EXACT PSI-MI-alternate []
is_a: MI:0857 ! fluorescent dye label

[Term]
id: MI:0927
name: iaedans label
def: "IAEDANS is fluorescent tag that bind to cysteines. IAEDANS is the acronyme of (5((((2-iodoacetyl)amino)ethyl)amino)-naphthalene-1-sulfonic acid)  with free SH groups." [PMID:11052891]
subset: PSI-MI_slim
synonym: "(5((((2-iodoacetyl)amino)ethyl)amino)-naphthalene-1-sulfonic acid) " EXACT PSI-MI-alternate []
synonym: "1,5-IAEDANS" EXACT PSI-MI-alternate []
synonym: "IAEDANS" EXACT PSI-MI-alternate []
is_a: MI:0857 ! fluorescent dye label

[Term]
id: MI:0928
name: filter trap assay
def: "Biomolecules are mixed in a buffer and the resulting mixture is passed through a filter. Large aggregates are retained on the filter and the pariticipants may then be identified." [PMID:10859365]
subset: PSI-MI_slim
synonym: "filter binding" EXACT []
synonym: "filter retardation assay" RELATED []
synonym: "Filter retention assay" EXACT PSI-MI-alternate []
synonym: "membrane filtration" RELATED []
is_a: MI:0013 ! biophysical
is_a: MI:0091 ! chromatography technology

[Term]
id: MI:0929
name: northern blot
def: "A standard procedure to identify RNA fragments containing specific\nsequences. In this procedure RNA fragments are separated by\nelectrophoresis, the fragments are transferred to a membrane and the\nmembrane is incubated with a radio labelled probe that hybridises any\ncomplementary subsequence." [PMID:414220]
subset: PSI-MI_slim
synonym: "northen" EXACT PSI-MI-alternate []
is_a: MI:0078 ! nucleotide sequence identification

[Term]
id: MI:0930
name: epistatis
def: "An effect in which individual perturbations of two different genes result in different mutant phenotypes, and the resulting phenotype of their combination (the double mutant) is equal to that of only one of the perturbations. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\n(a != wt AND b != wt AND a != b) AND (ab = a OR ab = b)\nwhere 'a' and 'b' are the observed phenotype values of the individual perturbations, 'ab' is the observed phenotype value of the double perturbation, 'wt' is the wild type phenotype value and 'a != b' indicates qualitatively or quantitatively different phenotypes." [PMID:11988766]
subset: PSI-MI_slim
synonym: "epistatic genetic interaction" EXACT []
is_obsolete: true

[Term]
id: MI:0931
name: genetic interaction defined by inequality
def: "Two genes A and B present an genetic interaction defined by inequality  if the phenotypes of the two single mutants a and b, the double mutant  ab and the wild-type WT can be measured quantitatively and described  relative to each other by an inequality relationship." [PMID:14755292]
subset: PSI-MI_slim
synonym: "genetic inequality" EXACT PSI-MI-short []
is_obsolete: true

[Term]
id: MI:0932
name: noninteractive
def: "The observation that, when tested, no interaction was observed between two or more genes, for a given phenotype. In other words, the phenotype of the combined perturbations a and b result in the expected phenotype." [PMID:15833125]
subset: PSI-MI_slim
synonym: "noninteractive genetic interaction (sensu inequality)" EXACT PSI-MI-alternate []
synonym: "noninteractive genetic interaction defined by inequality" EXACT []
is_a: MI:0934 ! neutral genetic interaction

[Term]
id: MI:0933
name: negative genetic interaction
def: "An effect in which two genetic perturbations, when combined, result in a phenotype that is more severe/penetrant than expected given the phenotypes of the individual perturbations. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\nab < E <= wt\nOR\nwt <= E < ab\nwhere 'ab' is the observed phenotype value of the double perturbation, 'E' is the expected phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:14755292]
subset: PSI-MI_slim
synonym: "negative gen int" EXACT PSI-MI-short []
is_a: MI:0208 ! genetic interaction

[Term]
id: MI:0934
name: neutral genetic interaction
def: "An effect in which the observed phenotype of individual perturbations and/or the double perturbation collectively exhibit values both greater than AND less than wild type (on the same scale). Alternatively, this could describe a scenario in which individual perturbations result in qualitatively different phenotypes. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\na < wt < b [ab != E]\nOR\nWith respect to two qualitatively different phenotypes, this may be expressed as an inequality as: \n(a != wt AND b != wt AND a != b)\nwhere 'a' and 'b' are the observed phenotype values of the individual perturbations, 'ab' is the observed phenotype value of the double perturbation, 'E' is the expected phenotype value of the double perturbation, 'wt' is the wild type phenotype value and 'a != b' indicates qualitatively different phenotypes." [PMID:14755292]
subset: PSI-MI_slim
synonym: "neutral gent int" EXACT PSI-MI-short []
is_a: MI:0208 ! genetic interaction

[Term]
id: MI:0935
name: positive genetic interaction
def: "An effect in which two genetic perturbations, when combined, result in a phenotype that is less severe/penetrant than would be expected from the original phenotypes, in effect making the organism more \"wild type\" in character with regards to the phenotype in question. With respect to any single quantifiable phenotype, this may be expressed as an inequality as: \nE < ab <= wt\nOR\nwt <= ab < E\nwhere 'ab' is the observed phenotype value of the double perturbation, 'E' is the expected phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:14755292]
subset: PSI-MI_slim
synonym: "positive gent int" EXACT PSI-MI-short []
is_a: MI:0208 ! genetic interaction

[Term]
id: MI:0936
name: emdb
def: "The Electron Microscopy Data Bank (EMDB) contains experimentally determined three-dimensional maps and associated experimental data and files." [PMID:14643225]
subset: PSI-MI_slim
synonym: "Electron Microscopy Data Bank" EXACT PSI-MI-alternate []
synonym: "eMDB" EXACT PSI-MI-short []
xref: search-url: "https://www.ebi.ac.uk/pdbe/entry/emdb/${ac}"
is_a: MI:0472 ! pdbe

[Term]
id: MI:0937
name: glu tag
def: "This peptide is a 314 to 319 amino acids fragment of the middle T antigen of mouse polymavirus. Glu-Glu epitope peptide." [PMID:8077219]
subset: PSI-MI_slim
synonym: "glu tag" EXACT PSI-MI-short []
is_a: MI:0507 ! tag

[Term]
id: MI:0938
name: rheology measurement
def: "Characterization of viscoelastic properties of biomolecule solution is used to infer interactions between molecules." [PMID:18445655]
subset: PSI-MI_slim
synonym: "rheology" EXACT PSI-MI-short []
is_a: MI:0013 ! biophysical

[Term]
id: MI:0939
name: fluorescein label
def: "Fluorescence label used to monitor the presence of a protein." [PMID:14755292]
subset: PSI-MI_slim
synonym: "fluorescein" EXACT PSI-MI-short []
is_a: MI:0857 ! fluorescent dye label

[Term]
id: MI:0940
name: fluorescein-5-maleimide label
def: "Fluorescein-5-maleimide is one of the most popular fluorescent dyes for thiol modifications of proteins at cysteine residues that either are intrinsically present or result from reduction of cystines. Unlike iodoacetamides, maleimides do not react with histidines and methionines under physiological conditions." [PMID:18066077]
subset: PSI-MI_slim
synonym: "fluor-5-maleimide" EXACT PSI-MI-short []
is_a: MI:0939 ! fluorescein label

[Term]
id: MI:0941
name: competitor
def: "Binds to an interacting molecule in competition with other interaction candidates, for example at a shared binding site." [PMID:14755292]
subset: PSI-MI_slim
synonym: "competitor" EXACT PSI-MI-short []
is_a: MI:0500 ! biological role

[Term]
id: MI:0942
name: uniprot taxonomy
def: "Based on NCBO Taxonomy but adapted for UniProt\nhttp://www.uniprot.org/taxonomy/" [PMID:18836194]
subset: PSI-MI_slim
synonym: "uniprot taxon" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "[0-9]+"
xref: search-url: "http://www.uniprot.org/taxonomy/${ac}"
is_a: MI:0473 ! participant database

[Term]
id: MI:0943
name: detection by mass spectrometry
def: "'Study of interactions by an analytical technique based on measurements of mass-to-charge ratio of charged particles in a mass spectrometer." [PMID:14755292]
subset: PSI-MI_slim
synonym: "ms interact detect" EXACT PSI-MI-short []
is_a: MI:0013 ! biophysical

[Term]
id: MI:0944
name: mass spectrometry study of hydrogen/deuterium exchange
def: "Mass spectroscopy based measurement of the rate and/or extent of the hydrogen/deuterium exchange." [PMID:18948593]
subset: PSI-MI_slim
synonym: "h1-h2 ms" EXACT PSI-MI-short []
is_a: MI:0943 ! detection by mass spectrometry

[Term]
id: MI:0945
name: oxidoreductase activity electron transfer reaction
def: "An oxidation-reduction (redox) reaction, a reversible chemical reaction in which the oxidation state of an atom or atoms within a molecule is altered. One substrate acts as a hydrogen or electron donor and becomes oxidized, while the other acts as hydrogen or electron acceptor and becomes reduced." [GO:GO\:0016491, PMID:14755292]
subset: PSI-MI_slim
synonym: "redox reaction" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction

[Term]
id: MI:0946
name: miniaturized immunoprecipitation
def: "Combines on-chip in-vitro protein synthesis with an in situ microfluidic affinity assay. Co-spotted DNA microarray containing a linear template encoding the proteins is aligned and bonded with a microfluidic device that creates chambers in the array chip. The experiment consists of three main stages: (i) an antibody that recognizes the bait protein or a specific tag is deposited on a circular area inside each individual chamber; (ii) proteins are expressed in vitro by transcription and translation of DNA spotted on the chip; (iii) the bait is immobilized on the chamber surface by the antibody and the chamber is washed, retaining only interacting bait-prey pairs." [PMID:19098921]
subset: PSI-MI_slim
synonym: " protein interaction network generator" EXACT []
synonym: "mIP" EXACT PSI-MI-short []
synonym: "MITOMI" EXACT PSI-MI-alternate []
synonym: "ping" EXACT []
is_a: MI:0019 ! coimmunoprecipitation
is_a: MI:0092 ! protein in situ array

[Term]
id: MI:0947
name: bead aggregation assay
def: "Binding of proteins bound to beads leads to a measurable aggregation of the beads." [PMID:19114658]
subset: PSI-MI_slim
synonym: "bead aggregation" EXACT PSI-MI-short []
is_a: MI:0892 ! solid phase assay

[Term]
id: MI:0948
name: kinetic conditions
def: "A brief description (such as temp, pH) of the conditions under which a kinetic measurment has been performed." [PMID:14755292]
subset: PSI-MI_slim
synonym: "kinetic_conditions" EXACT PSI-MI-short []
is_a: MI:0664 ! interaction attribute name

[Term]
id: MI:0949
name: gdp/gtp exchange assay
def: "Experiments monitoring\ninteractions of GTP-GDP exchange factors with their cognate GTPases." [PMID:17925023]
subset: PSI-MI_slim
synonym: "gdp_gtp exchange" EXACT PSI-MI-short []
synonym: "gtp/gdp exchange" EXACT PSI-MI-alternate []
synonym: "guanine nucleotide exchange assay" EXACT PSI-MI-alternate []
is_a: MI:1036 ! nucleotide exchange assay

[Term]
id: MI:0950
name: trapping mutant
def: "Permits the identification of substrates of enzymes by mutating residues, usually in the active site such that the enzyme will bind but not act on its substrate." [PMID:9050838]
subset: PSI-MI_slim
synonym: "trap-mutant" EXACT PSI-MI-short []
is_a: MI:0505 ! experimental feature

[Term]
id: MI:0951
name: chain parent sequence reference
def: "Reference to the master sequence from which this chain has been derived." [PMID:17925023]
subset: PSI-MI_slim
synonym: "chain-parent" EXACT PSI-MI-short []
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:0952
name: imex secondary
def: "Deprecated IMEx identifiers should be exchanged in IMEx records and stored as cross reference with this qualifier." [PMID:17925023]
subset: PSI-MI_slim
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:0953
name: polymerization
def: "Interaction inferred by monitoring polymerization/depolymerization of an interactor" [PMID:19081060]
subset: PSI-MI_slim
synonym: "polymerization" EXACT []
is_a: MI:0401 ! biochemical

[Term]
id: MI:0954
name: curation quality
def: "An assessment of the depth and extent to which a paper has been curated" [PMID:17893861]
subset: PSI-MI_slim
relationship: part_of MI:0000 ! molecular interaction

[Term]
id: MI:0955
name: curation depth
def: "Assessment of the depth to which a paper has been curated" [PMID:17893861]
relationship: part_of MI:0954 ! curation quality

[Term]
id: MI:0956
name: curation coverage
def: "Assessment to the extent of interactions captured in this paper" [PMID:17893861]
subset: PSI-MI_slim
relationship: part_of MI:0954 ! curation quality

[Term]
id: MI:0957
name: full coverage
def: "All interactions which can be ascribed to an unambiguous identified in this paper have been captured." [PMID:17893861]
subset: PSI-MI_slim
is_a: MI:0956 ! curation coverage

[Term]
id: MI:0958
name: partial coverage
def: "Not all interactions which can be ascribed to an unambiguous identified in this paper have been captured." [PMID:17893861]
subset: PSI-MI_slim
is_a: MI:0956 ! curation coverage

[Term]
id: MI:0959
name: imex curation
def: "Paper has been curated to full IMEx specifications" [PMID:17893861]
subset: PSI-MI_slim
is_a: MI:0955 ! curation depth

[Term]
id: MI:0960
name: mimix curation
def: "Paper has been curated to meet MIMIx specifications" [PMID:17687370]
subset: PSI-MI_slim
is_a: MI:0955 ! curation depth

[Term]
id: MI:0961
name: rapid curation
def: "Minimal interaction data has been extracted from the paper" [PMID:17687370]
subset: PSI-MI_slim
is_a: MI:0955 ! curation depth

[Term]
id: MI:0962
name: strep ii tag
def: "The protein of interest is expressed with a StrepII fusion peptide Ser-Ala-Trp-Ser-His-Pro-Gln-Phe-Glu-Lys (SAWSHPQFEK)." [PMID:17571060]
subset: PSI-MI_slim
synonym: "Strep (II)" EXACT PSI-MI-alternate []
synonym: "Strep II" EXACT PSI-MI-alternate []
is_a: MI:0507 ! tag

[Term]
id: MI:0963
name: interactome parallel affinity capture
def: "A specific pull down method where the protein of interest (bait) is endogenously expressed with at least two affinity tags (GFP, FLAG or others). The bait is purified in parallel using different purification protocols in contrast to tandem affinity purification (TAP) (publication currently in press)." [PMID:14681455]
synonym: "ipac" EXACT PSI-MI-short []
is_a: MI:0096 ! pull down
created_by: orchard
creation_date: 2009-05-14T10:56:21Z

[Term]
id: MI:0964
name: infrared spectroscopy
def: "Subset of spectroscopy that deals with the infrared region of the electromagnetic spectrum." [PMID:15212548]
subset: PSI-MI_slim
synonym: "ir spectrometry" EXACT PSI-MI-short []
is_a: MI:0013 ! biophysical
created_by: orchard
creation_date: 2009-10-28T10:55:01Z

[Term]
id: MI:0965
name: 2d-infrared spectrometry
def: "Two-dimensional infrared correlation spectroscopy analysis is the application of 2D correlation analysis on infrared spectra. 2D IR spectroscopy probes molecular structures by means of vibrational frequencies, couplings, and transition dipole angles." [PMID:17502604]
subset: PSI-MI_slim
synonym: "2d-ir" EXACT PSI-MI-short []
is_a: MI:0964 ! infrared spectroscopy
created_by: orchard
creation_date: 2009-10-28T11:05:01Z

[Term]
id: MI:0966
name: ultraviolet-visible spectroscopy
def: "Ultraviolet-visible spectroscopy or ultraviolet-visible spectrophotometry (UV-Vis or UV/Vis) involves the spectroscopy of photons in the UV-visible region. This means it uses light in the visible and adjacent (near ultraviolet (UV) and near infrared (NIR)) ranges." [PMID:18799738]
synonym: "ultraviolet-visible spectrophotometry" EXACT []
synonym: "uv-vis" EXACT PSI-MI-short []
synonym: "UV/Vis" EXACT []
is_a: MI:0013 ! biophysical
created_by: orchard
creation_date: 2009-10-28T11:12:27Z

[Term]
id: MI:0967
name: chembl compound
def: "ChEMBL focuses on mapping the interactions of small molecules binding to their macromolecular targets." [PMID:19194660, PMID:24214965]
subset: Drugable
subset: PSI-MI_slim
synonym: "chembl" EXACT []
xref: id-validation-regexp: "[0-9]+"
xref: search-url: "http://www.ebi.ac.uk/chembldb/index.php/compound/inspect/${ac}"
is_a: MI:2054 ! bioactive entity reference
relationship: part_of MI:1349 ! chembl
created_by: orchard
creation_date: 2009-10-28T11:20:55Z

[Term]
id: MI:0968
name: biosensor
def: "A biosensor is a device for the detection of an analyte that combines a biological component with a physicochemical detector component" [PMID:10872504]
subset: PSI-MI_slim
is_a: MI:0013 ! biophysical
created_by: orchard
creation_date: 2009-10-28T11:44:32Z

[Term]
id: MI:0969
name: bio-layer interferometry
def: "BLI is an optical analytical technique that analyzes the interference pattern of white light reflected from two surfaces: a layer of immobilized protein on the biosensor tip, and an internal reference layer" [PMID:19561609]
subset: PSI-MI_slim
synonym: "bli" EXACT PSI-MI-alternate []
is_a: MI:0968 ! biosensor
created_by: orchard
creation_date: 2009-10-28T11:48:40Z

[Term]
id: MI:0970
name: inchi key
def: "InChIKeys consist of 14 characters resulting from a hash of the connectivity information of the InChI, followed by a hyphen, followed by 9 characters resulting from a hash of the remaining layers of the InChI, followed by a single character indication the version of InChI used, another hyphen, followed by single checksum character" [PMID:15889163]
subset: Drugable
synonym: "inchi key" EXACT PSI-MI-short []
is_a: MI:1212 ! checksum
is_a: MI:2091 ! structure representation attribute name
created_by: orchard
creation_date: 2009-10-28T01:13:25Z

[Term]
id: MI:0971
name: phosphopantetheinylation
def: "The posttranslational phosphopantetheinylation of peptidyl-serine to form peptidyl-O-phosphopantetheine-L-serine." [PMID:19679086]
subset: PSI-MI_slim
synonym: "p_patetheinylation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction
created_by: orchard
creation_date: 2009-10-28T01:20:40Z

[Term]
id: MI:0972
name: phosphopantetheinylase assay
def: "Assay of the posttranslational phosphopantetheinylation of peptidyl-serine to form peptidyl-O-phosphopantetheine-L-serine." [PMID:19346479]
synonym: "p_pantethinyl assay" EXACT PSI-MI-short []
synonym: "phosphopantetheinylation" RELATED []
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2009-10-28T01:23:19Z

[Term]
id: MI:0973
name: imex source
def: "Databases that contain curated experimental interaction data and exchanging it with other IMEx databases." [PMID:17893861]
subset: PSI-MI_slim
is_a: MI:0489 ! source database
created_by: orchard
creation_date: 2009-12-18T10:24:37Z

[Term]
id: MI:0974
name: innatedb
def: "Human and mouse experimentally verified interactions and pathways involved in innate immunity." [PMID:18766178]
subset: PSI-MI_slim
synonym: "InnateDB" EXACT PSI-MI-alternate []
is_a: MI:0461 ! interaction database
is_a: MI:0973 ! imex source
created_by: orchard
creation_date: 2010-04-09T03:11:54Z

[Term]
id: MI:0975
name: fc-igg tag
def: "A fusion protein tag consisting of a portion of the constant region of IgG." [PMID:11757069]
subset: PSI-MI_slim
is_a: MI:0240 ! fusion protein
created_by: orchard
creation_date: 2010-04-21T02:18:04Z

[Term]
id: MI:0976
name: total internal reflection fluorescence spectroscopy
def: "Used to study surface-associated interactions at the molecular level. In this method, the evanescent field from an internally reflected excitation source selectively excites fluorescent molecules on or near a surface." [PMID:9013655]
subset: PSI-MI_slim
synonym: "tirfs" EXACT PSI-MI-short []
is_a: MI:0051 ! fluorescence technology
created_by: orchard
creation_date: 2010-04-21T02:30:46Z

[Term]
id: MI:0977
name: no-imex-export
def: "Prevents export of experiment and associated interactions to IMEx" [PMID:17893861]
subset: PSI-MI_slim
is_a: MI:0665 ! experiment attribute name
created_by: orchard
creation_date: 2010-04-21T02:49:48Z

[Term]
id: MI:0978
name: author-name
def: "Author given name for a participant, not commonly found in source databases." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0666 ! participant attribute name
created_by: orchard
creation_date: 2010-04-21T02:55:39Z

[Term]
id: MI:0979
name: oxidoreductase assay
def: "Catalysis of oxido-reductions. The substrate oxidized is regarded as the hydrogen or electron donor. The classification is based on 'donor:acceptor oxidoreductase'. The common name is 'dehydrogenase', wherever this is possible; as an alternative, 'acceptor reductase' can be used. 'Oxidase' is used only where O2 is an acceptor." [PMID:14755292]
subset: PSI-MI_slim
synonym: "oxidoreduct assay" EXACT PSI-MI-short []
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2010-04-21T03:04:54Z

[Term]
id: MI:0980
name: tag visualisation by enzyme assay
def: "The protein is expressed as a hybrid protein fused to a tag containing an enzyme activity e.g. peroxidase. Subsequence observation or measurement of enzyme activity is used to identify the presence of the molecule in an interaction." [PMID:14755292]
subset: PSI-MI_slim
synonym: "tag enzyme assay" EXACT PSI-MI-short []
is_a: MI:0866 ! tag visualisation
created_by: orchard
creation_date: 2010-04-21T03:18:09Z

[Term]
id: MI:0981
name: tag visualisation by peroxidase activity
def: "The protein is expressed as a hybrid protein fused to a tag containing a peroxidase activity. Subsequent observation or measurement of peroxidase activity is used to identify the presence of the molecule in an interaction." [PMID:14755292]
subset: PSI-MI_slim
synonym: "tag perox activity" EXACT PSI-MI-short []
is_a: MI:0980 ! tag visualisation by enzyme assay
created_by: orchard
creation_date: 2010-04-21T03:34:14Z

[Term]
id: MI:0982
name: electrophoretic mobility-based method
def: "Any method which relies on the motion of particles relative to a matrix under the influence of an electrical field." [PMID:19517512]
subset: PSI-MI_slim
synonym: "electrophoresis" EXACT PSI-MI-short []
is_a: MI:0401 ! biochemical
created_by: orchard
creation_date: 2010-04-26T10:30:36Z

[Term]
id: MI:0983
name: gemma
def: "GEMMA is a method to study protein complexes in solution: a diluted protein sample is transmitted\ninto the gas phase by a charged reduced electrospray process. The generated particles, each\ncontaining one protein molecule with a +1 charge, are separated according to size in a differential\nmobility analyzer and subsequently quantified by a particle counter. In contrast to mass spectrometry,\nthis method is run at atmospheric pressure and measures the diameter of the particle rather than the mass." [PMID:16861739]
subset: PSI-MI_slim
is_a: MI:0982 ! electrophoretic mobility-based method
created_by: orchard
creation_date: 2010-04-26T10:36:41Z

[Term]
id: MI:0984
name: deamination assay
def: "The measurement of the removal of an amine group from a molecule." [PMID:14755292]
subset: PSI-MI_slim
synonym: "aminase assay" EXACT PSI-MI-alternate []
synonym: "deamination" EXACT PSI-MI-short []
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2010-04-26T10:45:01Z

[Term]
id: MI:0985
name: deamination reaction
def: "The removal of an amine group from a molecule." [PMID:14760721]
subset: PSI-MI_slim
synonym: "deamination" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction
created_by: orchard
creation_date: 2010-04-26T10:49:06Z

[Term]
id: MI:0986
name: nucleic acid strand elongation reaction
def: "The lengthening of a strand of a nucleic acid by the systematic addition of bases by a polymerase." [PMID:159156]
subset: PSI-MI_slim
synonym: "strand elongation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction
created_by: orchard
creation_date: 2010-04-26T10:52:22Z

[Term]
id: MI:0987
name: rna strand elongation
def: "The process by which an RNA strand is synthesized from template DNA by the action of polymerases, which add nucleotides to the 3' end of the nascent RNA strand." [PMID:14755292]
subset: PSI-MI_slim
synonym: "rna elongation" EXACT PSI-MI-short []
is_a: MI:0986 ! nucleic acid strand elongation reaction
created_by: orchard
creation_date: 2010-04-26T11:00:08Z

[Term]
id: MI:0988
name: strep tag
def: "Synthetic peptide consisting of 8 amino acids Trp-Ser-His-Pro-Gln-Phe-Glu-Lys (WSHPQFEK)." [PMID:17571060]
subset: PSI-MI_slim
is_a: MI:0507 ! tag
created_by: orchard
creation_date: 2010-04-26T11:07:37Z

[Term]
id: MI:0989
name: amidase assay
def: "The measurement of the addition of an amine group to a molecule." [PMID:14760721]
subset: PSI-MI_slim
synonym: "amidation" EXACT PSI-MI-short []
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2010-04-26T11:20:23Z

[Term]
id: MI:0990
name: cleavage assay
def: "The cleavage of a biomolecule either into its component parts or sub-parts." [PMID:14760721]
subset: PSI-MI_slim
synonym: "cleavage" EXACT PSI-MI-short []
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2010-04-26T11:27:22Z

[Term]
id: MI:0991
name: lipoprotein cleavage assay
def: "The cleavage of a lipid molecule from a larger biomolecule." [PMID:14760721]
subset: PSI-MI_slim
is_a: MI:0990 ! cleavage assay
created_by: orchard
creation_date: 2010-04-26T11:30:12Z

[Term]
id: MI:0992
name: defarnesylase assay
def: "Measures the removal of S-farnesyl-L-cysteined, which is cleaved and returns a C residue." [PMID:14760721]
subset: PSI-MI_slim
synonym: "defarnesylation assay" EXACT PSI-MI-short []
is_a: MI:0991 ! lipoprotein cleavage assay
created_by: orchard
creation_date: 2010-04-26T12:27:47Z

[Term]
id: MI:0993
name: degeranylase assay
def: "Measures the removal of S-geranylgeranyl-L-cysteine, which is cleaved and returns a C residue." [PMID:14760721]
subset: PSI-MI_slim
synonym: "degeranylation assay" EXACT PSI-MI-short []
is_a: MI:0991 ! lipoprotein cleavage assay
created_by: orchard
creation_date: 2010-04-26T12:36:51Z

[Term]
id: MI:0994
name: demyristoylase assay
def: "measures the removal of N6-myristoyl-L-lysine, which is cleaved and returns a K residue." [PMID:14760721]
subset: PSI-MI_slim
synonym: "demyristoylation assay" EXACT PSI-MI-short []
is_a: MI:0991 ! lipoprotein cleavage assay
created_by: orchard
creation_date: 2010-04-26T12:39:30Z

[Term]
id: MI:0995
name: depalmitoylase assay
def: "Measures the removal of S-palmitoyl-L-cysteine, N6-palmitoyl-L-lysine, O-palmitoyl-L-threonine or O-palmitoyl-L-serine, which are cleaved and return C,K,T or S residues." [PMID:14760721]
subset: PSI-MI_slim
synonym: "depalmitoylation assay" EXACT PSI-MI-short []
is_a: MI:0991 ! lipoprotein cleavage assay
created_by: orchard
creation_date: 2010-04-26T12:42:00Z

[Term]
id: MI:0996
name: deformylase assay
def: "Measures the removal of N6-formyl-L-lysine, which is cleaved and returns a K residue." [PMID:14760721]
subset: PSI-MI_slim
synonym: "deformylase reaction" EXACT PSI-MI-short []
synonym: "deformylation" RELATED []
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2010-04-26T12:50:38Z

[Term]
id: MI:0997
name: ubiquitinase assay
def: "Measures the reversible reaction that creates a covalent bond between a C-terminus G of ubiquitin and a K residue of the target." [PMID:14760721]
subset: PSI-MI_slim
synonym: "ubiquitinase assay" EXACT PSI-MI-short []
synonym: "ubiquitination" RELATED []
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2010-04-26T12:54:02Z

[Term]
id: MI:0998
name: deubiquitinase assay
def: "Measures the cleavage of the G-K bond and release of ubiquitin or ubiquitin like proteins." [PMID:14760721]
subset: PSI-MI_slim
synonym: "deubiquinase assay" RELATED []
synonym: "deubiquitinase assay" EXACT PSI-MI-short []
synonym: "deubiquitination" RELATED []
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2010-04-26T12:56:41Z

[Term]
id: MI:0999
name: formylase assay
def: "Measurement of the reaction that can affect K or G residues. Reside is functionalised with a formyl group." [PMID:14760721]
subset: PSI-MI_slim
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2010-04-26T01:01:44Z

[Term]
id: MI:1000
name: hydroxylase assay
def: "Measurement of the irreversible introduction of a hydroxyl group that can affect K,P,Y or R residues." [PMID:14760721]
subset: PSI-MI_slim
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2010-04-26T01:05:19Z

[Term]
id: MI:1001
name: lipidase assay
def: "The covalent binding of a lipid group to a peptide chain." [PMID:14760721]
subset: PSI-MI_slim
synonym: "lipidation" RELATED []
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2010-04-26T01:09:49Z

[Term]
id: MI:1002
name: myristoylase assay
def: "Measurement of the irreversible covalent addition of a myristoyl group via an amide bond to the alpha-amino group of an amino acid." [PMID:14707621]
subset: PSI-MI_slim
synonym: "myristoylation" RELATED []
is_a: MI:1001 ! lipidase assay
created_by: orchard
creation_date: 2010-04-26T01:16:11Z

[Term]
id: MI:1003
name: geranylgeranylase assay
def: "Measurement of the attachment of one or two 20-carbon lipophilic geranylgeranyl isoprene units from geranylgeranyl diphosphate to one or more cysteine residue(s)." [PMID:14760721]
subset: PSI-MI_slim
synonym: "geranylgeranylase" EXACT PSI-MI-short []
synonym: "geranylgeranylation" RELATED []
is_a: MI:1001 ! lipidase assay
created_by: orchard
creation_date: 2010-04-26T01:20:07Z

[Term]
id: MI:1004
name: palmitoylase assay
def: "Measurement of the covalent attachment of palmitic acid to a protein." [PMID:14760721]
subset: PSI-MI_slim
synonym: "myristoylation" RELATED []
synonym: "palmitoylase assay" EXACT PSI-MI-short []
is_a: MI:1001 ! lipidase assay
created_by: orchard
creation_date: 2010-04-26T01:27:50Z

[Term]
id: MI:1005
name: adp ribosylase assay
def: "Measurement of the addition of one or more ADP-ribose moieties to molecules." [PMID:14760721]
subset: PSI-MI_slim
synonym: "adp ribosylase" EXACT PSI-MI-short []
synonym: "adp ribosylation" RELATED []
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2010-04-26T01:30:24Z

[Term]
id: MI:1006
name: deglycosylase assay
def: "Measurement of the removal of a glycosyl residue to one or more monomeric units in a polypeptide, polynucleotide, polysaccharide, or other biological polymer." [PMID:14760721]
subset: PSI-MI_slim
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2010-04-26T01:34:07Z

[Term]
id: MI:1007
name: glycosylase assay
def: "Measurement of the covalently attachment of glycosyl residues to one or more monomeric units in a polypeptide, polynucleotide, polysaccharide, or other biological polymer." [PMID:14760721]
subset: PSI-MI_slim
synonym: "glycosylation" RELATED []
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2010-04-26T01:35:37Z

[Term]
id: MI:1008
name: sumoylase assay
def: "Measurement of the reversible reaction that creates a covalent bond between a C-terminus G of an ubiquitine like sumo protein and a K residue of the target." [PMID:14760721]
subset: PSI-MI_slim
synonym: "sumoylation" RELATED []
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2010-04-26T01:37:31Z

[Term]
id: MI:1009
name: desumoylase assay
def: "Measurement of the reaction that breaks a covalent bond between a C-terminus G of an ubiquitine like sumo protein and a K residue of the target." [PMID:14760721]
subset: PSI-MI_slim
synonym: "desumylation" RELATED []
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2010-04-26T01:38:56Z

[Term]
id: MI:1010
name: neddylase assay
def: "Measurement of a reversible reaction that create a covalent bond between a Glycine residue of an ubiquitine like NEDD8 protein and a lysine residue of the target." [PMID:14760721]
subset: PSI-MI_slim
synonym: "neddylation" RELATED []
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2010-04-26T01:41:40Z

[Term]
id: MI:1011
name: deneddylase assay
def: "Measurement of the reaction that breaks a covalent bond between a Glycine residue of an ubiquitine like NEDD8 protein and a lysine residue of the target." [PMID:14760721]
subset: PSI-MI_slim
synonym: "deneddylation" RELATED []
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2010-04-26T01:42:49Z

[Term]
id: MI:1012
name: sbp
def: "38 amino acid (MDEKTTGWRGGHWEGLAGELEQLRARLEHHPQGQREP) Streptavidin binding peptide." [PMID:117222181]
subset: PSI-MI_slim
synonym: "steptavidin binding peptide" RELATED []
is_a: MI:0507 ! tag
created_by: orchard
creation_date: 2010-04-29T08:42:26Z

[Term]
id: MI:1013
name: ensemblgenomes
def: "Genome browser complementary to Ensembl which extends the search space across a broader taxonomic range.\nhttp://www.ensemblgenomes.org" [PMID:19884133]
subset: PSI-MI_slim
xref: search-url: "http://ensemblgenomes.org/search/eg/${ac}"
is_a: MI:1094 ! genome databases
created_by: orchard
creation_date: 2010-05-06T08:09:20Z

[Term]
id: MI:1014
name: string
def: "STRING is a database and web resource dedicated to protein interactions, including both physical and functional interactions. It weights and integrates information from numerous sources, including experimental repositories, computational prediction methods and public text collections, thus acting as a meta-database that maps all interaction evidence onto a common set of genomes and proteins." [PMID:18940858]
subset: PSI-MI_slim
is_a: MI:0461 ! interaction database
created_by: orchard
creation_date: 2010-07-15T11:00:57Z

[Term]
id: MI:1015
name: dictybase
def: "dictyBase (http://dictybase.org) is the model organism database for Dictyostelium discoideum. It houses the complete genome sequence, ESTs and the entire body of literature relevant to Dictyostelium. This information is curated to provide accurate gene models and functional annotations, with the goal of fully annotating the genome." []
subset: PSI-MI_slim
xref: id-validation-regexp: "DDB_G(0-9){7}"
is_a: MI:1094 ! genome databases
created_by: orchard
creation_date: 2010-07-29T01:19:40Z

[Term]
id: MI:1016
name: fluorescence recovery after photobleaching
def: "Slow rate of FRAP recovery when molecule is bound to another compared to inert, non-binding molecule taken as a measure of an interaction." [PMID:15695095, PMID:17711354]
subset: PSI-MI_slim
synonym: "frap" EXACT PSI-MI-short []
is_a: MI:0051 ! fluorescence technology
created_by: orchard
creation_date: 2010-11-11T10:39:37Z

[Term]
id: MI:1017
name: rna immunoprecipitation
def: "Proteins are crosslinked to nucleic acids, for example by the addition of formaldehyde. RNA sequences that cross-link with a given protein are isolated by immunoprecipitation of the protein, and reversal of the cross-linking permits recovery and quantitative analysis of the immunoprecipitated RNA by reverse transcription PCR." [PMID:18265380]
subset: PSI-MI_slim
synonym: "rip" RELATED []
synonym: "rna-ip" EXACT PSI-MI-short []
is_a: MI:0019 ! coimmunoprecipitation
created_by: orchard
creation_date: 2010-11-11T10:58:47Z

[Term]
id: MI:1018
name: deltamass
def: "A database of protein post translational modifications. www.abrf.org/index.cfm/dm.home" [PMID:8322616]
subset: PSI-MI_slim
is_a: MI:0447 ! feature database
created_by: orchard
creation_date: 2010-11-11T11:04:13Z

[Term]
id: MI:1019
name: protein phosphatase assay
def: "Measures the catalysis of the reaction: a phosphoprotein + H2O = a protein + phosphate." []
subset: PSI-MI_slim
is_a: MI:0434 ! phosphatase assay
created_by: orchard
creation_date: 2010-11-11T11:30:47Z

[Term]
id: MI:1020
name: hilyte fluor 488
def: "A carbonyl-reactive fluorescent labelling dye." [PMID:19795889]
subset: PSI-MI_slim
synonym: "hilyte 488" EXACT PSI-MI-short []
is_a: MI:0857 ! fluorescent dye label
created_by: orchard
creation_date: 2010-11-11T11:35:48Z

[Term]
id: MI:1021
name: qx 520
def: "Nonfluorescent dye, act as a quencher in FRET assays." []
subset: PSI-MI_slim
is_a: MI:0373 ! dye label
created_by: orchard
creation_date: 2010-11-11T11:40:16Z

[Term]
id: MI:1022
name: field flow fractionation
def: "A separation technique where a field is applied to a mixture perpendicular to the mixtures flow. The filed can be graviational, centrifugal, magnetic or a cross flow of fluids." [PMID:959835]
subset: PSI-MI_slim
is_a: MI:0027 ! cosedimentation
created_by: orchard
creation_date: 2010-11-11T11:55:40Z

[Term]
id: MI:1023
name: luminogreen
def: "A  nonfluorescent, biarsenical derivative of fluorescein. LumioGreen is supplied pre-complexed to EDT, is membrane-permeable, and readily enters the cell." [PMID:19935683]
subset: PSI-MI_slim
is_a: MI:0373 ! dye label
created_by: orchard
creation_date: 2010-11-11T12:10:26Z

[Term]
id: MI:1024
name: scanning electron microscopy
def: "A type of electron microscope that images the sample surface by scanning it with a high-energy beam of electrons  in a raster scan pattern. The electrons interact with the atoms that make up the sample producing signals that contain information about the sample's surface topography, composition and other properties such as electrical conductivity." [PMID:20463740]
subset: PSI-MI_slim
synonym: "sem" EXACT PSI-MI-alternate []
is_a: MI:0040 ! electron microscopy
created_by: orchard
creation_date: 2010-11-11T12:17:54Z

[Term]
id: MI:1025
name: unimod
def: "A database of protein modifications for mass spectrometry. www.unimod.org" [PMID:15174123]
is_a: MI:0447 ! feature database
created_by: orchard
creation_date: 2010-11-11T12:24:10Z

[Term]
id: MI:1026
name: diphtamidase assay
def: "Measurement of a modification that converts an L-histidine residue to diphthamide." [PMID:14760721]
subset: PSI-MI_slim
synonym: "diphtamidase" EXACT PSI-MI-short []
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2010-11-11T12:33:29Z

[Term]
id: MI:1027
name: diphtamidation reaction
def: "A modification that converts an L-histidine residue to diphthamide." [PMID:14760721]
subset: PSI-MI_slim
synonym: "diphthamidation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction
created_by: orchard
creation_date: 2010-11-11T12:36:51Z

[Term]
id: MI:1028
name: modified chromatin immunoprecipitation
def: "Chromatin-bound protein networks isolated using magnetic beads coated with antibodies." [PMID:19106085]
subset: PSI-MI_slim
synonym: "mch-ip" EXACT PSI-MI-short []
is_a: MI:0402 ! chromatin immunoprecipitation assay
created_by: orchard
creation_date: 2010-11-11T12:58:52Z

[Term]
id: MI:1029
name: proteomics of isolated chromatin segments
def: "Specific nucleic acid probes are fixed to solid supports (e.g. beads) and act as affinity probes. The molecules associated with the nucleic acid probes can then be isolated and identified." [PMID:19135898]
subset: PSI-MI_slim
synonym: "pich" EXACT PSI-MI-alternate []
is_a: MI:0402 ! chromatin immunoprecipitation assay
created_by: orchard
creation_date: 2010-11-11T01:03:21Z

[Term]
id: MI:1030
name: excimer fluorescence
def: "Excimer (excited-dimer) fluorescence is produced by complexes formed by two molecules, at least one of which is in an excited state. It is characterized by a lower energy (i.e. red shift) than fluorescence of a single, non-interacting molecule." [PMID:18480256]
subset: PSI-MI_slim
synonym: "excimer fluoresc" EXACT PSI-MI-short []
is_a: MI:0051 ! fluorescence technology
created_by: orchard
creation_date: 2010-11-11T01:15:19Z

[Term]
id: MI:1031
name: protein folding/unfolding
def: "A change in the rate of protein folding/unfolding is taken as a measure of chaperone protein binding." [PMID:19940245]
subset: PSI-MI_slim
synonym: "protein folding" EXACT PSI-MI-short []
is_a: MI:0400 ! affinity technology
created_by: orchard
creation_date: 2010-11-11T01:24:11Z

[Term]
id: MI:1032
name: atto 488
def: "Fluorescent tag - maleimide couples to thiols." [PMID:14760721]
subset: PSI-MI_slim
synonym: "atto 488 maleimide" EXACT []
synonym: "atto488" RELATED []
is_a: MI:1092 ! atto label
created_by: orchard
creation_date: 2010-11-11T01:33:13Z

[Term]
id: MI:1033
name: atto 550
def: "Fluorescent tag - maleimide couples to thiols." [PMID:14760721]
subset: PSI-MI_slim
synonym: "atto550" RELATED []
is_a: MI:1092 ! atto label
created_by: orchard
creation_date: 2010-11-11T01:39:43Z

[Term]
id: MI:1034
name: nuclease assay
def: "Measures the cleavage of phosphodiesterase bonds between the nucleotide subunits of nucleic acids." [PMID:14760721]
subset: PSI-MI_slim
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2010-11-11T01:43:11Z

[Term]
id: MI:1035
name: deoxyribonuclease assay
def: "Measures the catalysis of the hydrolysis of phosphodiester bonds in chains of DNA." [PMID:14760721]
subset: PSI-MI_slim
synonym: "deoxyribonuclease" EXACT PSI-MI-short []
is_a: MI:1034 ! nuclease assay
created_by: orchard
creation_date: 2010-11-11T01:45:29Z

[Term]
id: MI:1036
name: nucleotide exchange assay
def: "Experiments monitoring\ninteractions of nucleotide exchange factors with their cognate nucleotidases." [PMID:14760721]
subset: PSI-MI_slim
synonym: "nucleotide exchange" EXACT PSI-MI-short []
is_a: MI:0401 ! biochemical
created_by: orchard
creation_date: 2010-11-11T01:54:00Z

[Term]
id: MI:1037
name: Split renilla luciferase complementation
def: "The N-terminal portion of synthetic renilla luciferase (hrluc) is attached to one protein through the linker peptide (GGGS)2 and C-terminal portion of synthetic renilla luciferase is connected to the second protein through the linker (GGGGS)2. Interaction of the 2 proteins recovers hrluc activity and produces light." [PMID:12705589, PMID:22070901]
subset: PSI-MI_slim
synonym: "renilla luciferase" EXACT PSI-MI-alternate []
is_a: MI:1203 ! split luciferase complementation
created_by: orchard
creation_date: 2010-11-11T02:54:08Z

[Term]
id: MI:1038
name: silicon nanowire field-effect transistor
def: "Measures selective electrical response to molecules binding to the immobilised bait." [PMID:20080536]
subset: PSI-MI_slim
synonym: "nanowire transistor" EXACT PSI-MI-alternate []
is_a: MI:0968 ! biosensor
created_by: orchard
creation_date: 2010-11-11T03:11:33Z

[Term]
id: MI:1039
name: c-terminal range
def: "The C-terminal region of a sequence, exact coordinates not available." [PMID:14760721]
subset: PSI-MI_slim
synonym: "c-term range" EXACT PSI-MI-short []
is_a: MI:0333 ! feature range status
created_by: orchard
creation_date: 2010-11-11T03:20:34Z

[Term]
id: MI:1040
name: n-terminal range
def: "The N-terminal region of a sequence, exact coordinates not available." [PMID:14760721]
subset: PSI-MI_slim
synonym: "n-term range" EXACT PSI-MI-short []
is_a: MI:0333 ! feature range status
created_by: orchard
creation_date: 2010-11-11T03:27:57Z

[Term]
id: MI:1041
name: synonym
def: "Alternative name or descriptor for an entity." [PMID:14681455]
subset: PSI-MI_slim
is_a: MI:0300 ! alias type
created_by: orchard
creation_date: 2010-12-02T10:26:35Z

[Term]
id: MI:1042
name: pubmed central
def: "PubMed Central is the US National Institute of Health free digital archive of biomedical and life science journals." [PMID:12519941]
subset: PSI-MI_slim
synonym: "pmc" EXACT PSI-MI-short []
is_a: MI:0445 ! literature database
created_by: orchard
creation_date: 2010-12-08T01:20:48Z

[Term]
id: MI:1043
name: flannotator
def: "A repository for collecting, storing and and searching the annotation of gene or protein expression patterns in Drosophila melongaster. CPTI (Cambridge Protein Trap Identifier)" [PMID:19126575]
subset: PSI-MI_slim
xref: id-validation-regexp: "CPTO-[0-9]{6}"
is_a: MI:0683 ! sequence database
created_by: orchard
creation_date: 2011-01-06T01:16:48Z

[Term]
id: MI:1044
name: rice genome annotation project
def: "NSF funded annotation project." [PMID:17145706]
subset: PSI-MI_slim
synonym: "RGAP" RELATED []
is_a: MI:1094 ! genome databases
created_by: orchard
creation_date: 2011-02-11T01:33:28Z

[Term]
id: MI:1045
name: curation content
def: "Indicates source, depth and standards by which an entry has been  added to a database." [PMID:14755292]
subset: PSI-MI_slim
relationship: part_of MI:0000 ! molecular interaction
created_by: orchard
creation_date: 2011-03-11T01:16:55Z

[Term]
id: MI:1046
name: interacting molecules
def: "Defines an interaction by the type of binary molecule pairs it can generates." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1045 ! curation content
created_by: orchard
creation_date: 2011-03-11T01:19:27Z

[Term]
id: MI:1047
name: protein-protein
def: "Interaction between a protein or peptide and a corresponding protein or peptide." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1046 ! interacting molecules
created_by: orchard
creation_date: 2011-03-11T01:21:28Z

[Term]
id: MI:1048
name: smallmolecule-protein
def: "Interaction between a small molecule and a corresponding protein or peptide." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1046 ! interacting molecules
created_by: orchard
creation_date: 2011-03-11T01:22:36Z

[Term]
id: MI:1049
name: nucleicacid-protein
def: "Interaction between a nucleic acid and a corresponding protein or peptide." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1046 ! interacting molecules
created_by: orchard
creation_date: 2011-03-11T01:23:29Z

[Term]
id: MI:1050
name: interaction representation
def: "Provides an indication of the level of post-processing of experimental data relating to specific binary pairs" [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1045 ! curation content
created_by: orchard
creation_date: 2011-03-11T01:25:29Z

[Term]
id: MI:1051
name: evidence
def: "Binary pair is defined by a single piece of experimental evidence." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1050 ! interaction representation
created_by: orchard
creation_date: 2011-03-11T01:27:00Z

[Term]
id: MI:1052
name: clustered
def: "Binary pair is defined by multiple pieces of experimental evidence which have been clustered together." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1050 ! interaction representation
created_by: orchard
creation_date: 2011-03-11T01:28:50Z

[Term]
id: MI:1053
name: data source
def: "The source of the data entered into the database." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1045 ! curation content
created_by: orchard
creation_date: 2011-03-11T01:32:16Z

[Term]
id: MI:1054
name: experimentally-observed
def: "Data has been directly curated into the database from the paper describing the experimental evidence or by direct submission by the experimenter." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1053 ! data source
created_by: orchard
creation_date: 2011-03-11T01:33:48Z

[Term]
id: MI:1055
name: internally-curated
def: "Data has been directly curated into this database from the paper describing the experimental evidence" [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1053 ! data source
created_by: orchard
creation_date: 2011-03-11T01:35:12Z

[Term]
id: MI:1056
name: text-mining
def: "The data has been entered into the database following extraction from the literature by a computational process." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1053 ! data source
created_by: orchard
creation_date: 2011-03-11T01:36:34Z

[Term]
id: MI:1057
name: predicted
def: "The interaction has been predicted using a specific algorithm." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1053 ! data source
created_by: orchard
creation_date: 2011-03-11T01:37:47Z

[Term]
id: MI:1058
name: imported
def: "The data has been imported into the database form an external resource." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1053 ! data source
created_by: orchard
creation_date: 2011-03-11T01:39:23Z

[Term]
id: MI:1059
name: complex expansion
def: "The method by which complex n-ary data is expanded into binary data. This may be performed manually on data input, or computationally on data export." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1045 ! curation content
created_by: orchard
creation_date: 2011-03-11T01:41:16Z

[Term]
id: MI:1060
name: spoke expansion
def: "Complex n-ary data has been expanded to binary using the spoke model. This assumes that all molecules in the complex interact with a single designated molecule, usually the bait." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1059 ! complex expansion
created_by: orchard
creation_date: 2011-03-11T01:42:35Z

[Term]
id: MI:1061
name: matrix expansion
def: "Complex n-ary data has been expanded to binary using the spoke model. This assumes that all molecules in the complex interact with each other." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1059 ! complex expansion
created_by: orchard
creation_date: 2011-03-11T01:45:52Z

[Term]
id: MI:1062
name: bipartite expansion
def: "Complex n-ary data has been expanded to binary using the bipartite model. This assumes that all molecules in the complex interact with a single externally designated entity." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1059 ! complex expansion
created_by: orchard
creation_date: 2011-03-11T01:49:08Z

[Term]
id: MI:1063
name: consensuspathdb
def: "ConsensusPathDB-human integrates functional interaction networks including complex protein-protein, metabolic, signaling and gene regulatory interaction networks in Homo sapiens. Data originate from currently 20 public resources for functional interactions (listed below), as well as interactions that we have curated from literature. Data are integrated in a complementary manner and redundancies are avoided." [PMID:21071422]
subset: PSI-MI_slim
is_a: MI:1106 ! pathways database
created_by: orchard
creation_date: 2011-06-21T02:40:16Z

[Term]
id: MI:1064
name: interaction confidence
def: "A method used to derive a numerical or empirical measure of confidence in a particular interaction, or in the identification of the participants in an interaction." [PMID:19420069]
subset: PSI-MI_slim
synonym: "confidence" EXACT PSI-MI-short []
synonym: "scoring system" EXACT []
relationship: part_of MI:0000 ! molecular interaction
created_by: orchard
creation_date: 2011-07-05T07:13:57Z

[Term]
id: MI:1065
name: replication-based confidence
def: "Methods based on counting the number of replicates in which an interaction has been observed." [PMID:19420069]
subset: PSI-MI_slim
synonym: "replication score" EXACT PSI-MI-alternate []
synonym: "replication-based scoring system" RELATED []
is_a: MI:1064 ! interaction confidence
created_by: orchard
creation_date: 2011-07-05T07:22:02Z

[Term]
id: MI:1066
name: structure-based confidence
def: "Confidence score based on similarity to interacting molecules of known structure, presence of known interacting domains etc." [PMID:15044803]
subset: PSI-MI_slim
synonym: "structure score" EXACT PSI-MI-alternate []
synonym: "structure-based scoring system" EXACT []
is_a: MI:1064 ! interaction confidence
created_by: orchard
creation_date: 2011-07-05T07:38:50Z

[Term]
id: MI:1067
name: function-based confidence
def: "Confidence in an interaction is based on shared functionality of interacting molecules e.g. co-occurrence of GO function terms." [PMID:21443973]
subset: PSI-MI_slim
synonym: "function score" EXACT PSI-MI-short []
synonym: "function-based scoring system" EXACT []
is_a: MI:1064 ! interaction confidence
is_a: MI:1221 ! author-based confidence
created_by: orchard
creation_date: 2011-07-05T07:46:28Z

[Term]
id: MI:1068
name: location-based confidence
def: "Confidence in an interaction is based on shared functionality of interacting molecules e.g. co-occurrence of GO component terms or co-occurrence in the same tissues." [PMID:18624398]
subset: PSI-MI_slim
synonym: "colocation score" EXACT PSI-MI-short []
synonym: "location-based scoring system" EXACT []
is_a: MI:1064 ! interaction confidence
created_by: orchard
creation_date: 2011-07-05T07:52:36Z

[Term]
id: MI:1069
name: network-based confidence
def: "Network-based confidence scoring systems assign confidence based on multiple parameters, potentially shared by interacting proteins e.g. interaction partners, topological parameters, comparison\nwith genetic interactions." [PMID:19010802]
subset: PSI-MI_slim
synonym: "network score" EXACT PSI-MI-short []
synonym: "network-based scoring system" EXACT PSI-MI-short []
is_a: MI:1064 ! interaction confidence
created_by: orchard
creation_date: 2011-07-05T07:59:13Z

[Term]
id: MI:1070
name: standard-based confidence
def: "Confidence scoring system based on comparison to a 'gold standard' set of known interacting molecules." [PMID:16554755]
subset: PSI-MI_slim
synonym: "gold standard" RELATED []
synonym: "standard score" EXACT PSI-MI-short []
synonym: "standard-based scoring system" EXACT []
is_a: MI:1064 ! interaction confidence
created_by: orchard
creation_date: 2011-07-05T08:09:46Z

[Term]
id: MI:1071
name: literature-based confidence
def: "Confidence in an interaction is based on co-occurrence of an interacting pair or molecules in the same article, or sentence within an article, usually identified by text-mining." [PMID:18005433]
subset: PSI-MI_slim
synonym: "literature score" EXACT PSI-MI-short []
synonym: "literature-based scoring system" EXACT []
is_a: MI:1064 ! interaction confidence
created_by: orchard
creation_date: 2011-07-05T08:24:46Z

[Term]
id: MI:1072
name: method-based confidence
def: "The confidence of an interaction is assessed on the number of different methods by which it is observed." [PMID:19420069]
subset: PSI-MI_slim
synonym: "method score" EXACT PSI-MI-short []
synonym: "method-based scoring system" EXACT []
is_a: MI:1064 ! interaction confidence
created_by: orchard
creation_date: 2011-07-05T08:42:47Z

[Term]
id: MI:1073
name: statistical-based confidence
def: "Confidence in an interaction is based on a measure of the probability of these molecules interacting." [PMID:19420069]
subset: PSI-MI_slim
synonym: "statistical score" EXACT PSI-MI-short []
synonym: "statistical-based scoring system" EXACT []
is_a: MI:1064 ! interaction confidence
created_by: orchard
creation_date: 2011-07-05T08:50:05Z

[Term]
id: MI:1074
name: rgs-his tag
def: "The protein of interest is expressed as a fusion to a RGS(His)n tag." [PMID:19223579]
synonym: "rgs-his" EXACT PSI-MI-short []
is_a: MI:0521 ! his tag
created_by: orchard
creation_date: 2011-07-05T09:52:28Z

[Term]
id: MI:1075
name: beilstein
def: "The Beilstein database is in the field of organic chemistry, in which compounds are uniquely identified by their Beilstein Registry Number." [PMID:ID\:11604014]
subset: PSI-MI_slim
synonym: "beilstein" EXACT PSI-MI-short []
is_a: MI:2054 ! bioactive entity reference
created_by: orchard
creation_date: 2011-07-05T10:03:13Z

[Term]
id: MI:1076
name: einecs
def: "The EINECS database provides general information such as CAS number, EINECS number, Substance Name and Chemical Formula for 100,204 chemical substances. Where available each compound entry is linked to risk and safety phrases and IUCLID and OECD chemical data sheets." [PMID:17125194]
subset: PSI-MI_slim
synonym: "einecs" EXACT PSI-MI-short []
synonym: "European Inventory of Existing Commercial Chemical Substances " EXACT []
is_a: MI:2054 ! bioactive entity reference
created_by: orchard
creation_date: 2011-07-05T10:09:35Z

[Term]
id: MI:1077
name: merck index
def: "Comprehensive information on chemicals, drugs, and biologicals." [PMID:17832605]
subset: PSI-MI_slim
synonym: "merck index" EXACT PSI-MI-short []
is_a: MI:2054 ! bioactive entity reference
created_by: orchard
creation_date: 2011-07-05T10:15:56Z

[Term]
id: MI:1078
name: plantgdb
def: "PlantGDB  develops plant species-specific EST and GSS databases, to provide web-accessible tools and inter-species query capabilities, and to provide genome browsing and annotation capabilities." [PMID:18063570]
subset: PSI-MI_slim
synonym: "plantgdb" EXACT PSI-MI-short []
is_a: MI:1094 ! genome databases
created_by: orchard
creation_date: 2011-07-05T10:27:50Z

[Term]
id: MI:1079
name: ratmap
def: "The rat genome database RatMap (http://ratmap.org or http://ratmap.gen.gu.se) has been one of the main resources for rat genome information since 1994. The database is maintained by CMB Genetics at Gothenburg University in Sweden and provides information on rat genes, polymorphic rat DNA-markers and rat quantitative trait loci (QTLs), all curated at RatMap." [PMID:15608244]
subset: PSI-MI_slim
synonym: "ratmap" EXACT PSI-MI-short []
is_a: MI:1094 ! genome databases
created_by: orchard
creation_date: 2011-07-05T10:32:10Z

[Term]
id: MI:1080
name: tair
def: "The Arabidopsis Information Resource (TAIR) maintains a database of genetic and molecular biology data for the model higher plant Arabidopsis thaliana . Data available from TAIR includes the complete genome sequence along with gene structure, gene product information, metabolism, gene expression, DNA and seed stocks, genome maps, genetic and physical markers, publications, and information about the Arabidopsis research community." [PMID:20521243]
subset: PSI-MI_slim
synonym: "tair" EXACT PSI-MI-short []
synonym: "The Arabidopsis Information Resource" EXACT []
is_a: MI:1094 ! genome databases
created_by: orchard
creation_date: 2011-07-05T10:34:26Z

[Term]
id: MI:1081
name: tigr/jcvi
def: "The J. Craig Venter Institute was formed in October 2006 through the merger of several affiliated and legacy organizations including The Institute for Genomic Research (TIGR)." [PMID:18287690]
subset: PSI-MI_slim
synonym: "J. Craig Venter Institute" EXACT []
synonym: "The Institute for Genomic Research" EXACT PSI-MI-short []
synonym: "tigr/jcvi" EXACT PSI-MI-short []
is_a: MI:1094 ! genome databases
created_by: orchard
creation_date: 2011-07-05T10:44:11Z

[Term]
id: MI:1082
name: zfin
def: "Extensive information on Danio rerio, including genomics databases, developmental stages, publications and molecular tools." [PMID:21036866]
synonym: "The Zebrafish Model Organism Database " EXACT []
synonym: "zfin" EXACT PSI-MI-short []
is_a: MI:1094 ! genome databases
created_by: orchard
creation_date: 2011-07-05T10:53:21Z

[Term]
id: MI:1083
name: cog
def: "Clusters of Orthologous Groups of proteins (COGs) were delineated by comparing protein sequences encoded in complete genomes, representing major phylogenetic lineages. Each COG consists of individual proteins or groups of paralogs from at least 3 lineages and thus corresponds to an ancient conserved domain." [PMID:11125040]
subset: PSI-MI_slim
synonym: "Clusters of Orthologous Groups" EXACT []
synonym: "cogg" EXACT PSI-MI-short []
is_a: MI:0447 ! feature database
created_by: orchard
creation_date: 2011-07-05T10:59:06Z

[Term]
id: MI:1084
name: photon donor
def: "Any molecule that is able to transfer a photon to another chemical species." [PMID:14755292]
subset: PSI-MI_slim
synonym: "photon donor" EXACT PSI-MI-short []
is_a: MI:0918 ! donor
created_by: orchard
creation_date: 2011-07-05T11:03:38Z

[Term]
id: MI:1085
name: photon acceptor
def: "Molecule to which a photon may be transferred from an photon donor." [PMID:14755292]
subset: PSI-MI_slim
synonym: "photon acceptor" EXACT PSI-MI-short []
is_a: MI:0919 ! acceptor
created_by: orchard
creation_date: 2011-07-05T11:06:47Z

[Term]
id: MI:1086
name: equilibrium dialysis
def: "Two chambers are separated by a dialysis membrane. The molecular weight cut off (MWCO) of this membrane is chosen such that it will retain the receptor component of the sample (the element which will bind the ligand). A known concentration and volume of ligand is placed into one of the chambers. The ligand is small enough to pass freely through the membrane. A known concentration of receptor is then placed in the remaining chamber in an equivalent volume to that placed in the first chamber. As the ligand diffuses across the membrane some of it will bind to the receptor and some will remain free in solution. The higher the affinity of the interaction, the higher the concentration of ligand that will be bound at any time." [PMID:21609686]
synonym: "equilib. dialysis" EXACT PSI-MI-short []
is_a: MI:0013 ! biophysical
created_by: orchard
creation_date: 2011-07-05T11:12:25Z

[Term]
id: MI:1087
name: monoclonal antibody blockade
def: "Method to block a binding site on a molecule, such as a protein, using a monoclonal antibody to test that the binding site is involved in an interaction with another molecule." [PMID:14755292]
subset: PSI-MI_slim
synonym: "mab blockade" EXACT PSI-MI-short []
is_a: MI:0400 ! affinity technology
is_a: MI:2197 ! probe interaction assay
created_by: orchard
creation_date: 2011-07-05T11:19:37Z

[Term]
id: MI:1088
name: phenotype-based detection assay
def: "Assays that are used to determine interactions by monitoring, for example activation of a certain pathway when screening for inhibitors of a given receptor." [PMID:14755292]
synonym: "phenotype-based" EXACT PSI-MI-short []
is_a: MI:0045 ! experimental interaction detection
created_by: orchard
creation_date: 2011-07-05T11:24:37Z

[Term]
id: MI:1089
name: nuclear translocation assay
def: "Method to detect interaction by inducing nuclear localization of one participant, which would then pull an interacting participant along with it into the nucleus. As both participants are labeled, the difference in nuclear localization between the induced and non-induced states provides an indication of the interaction between the two molecules." [PMID:21684252]
subset: PSI-MI_slim
synonym: "nuclear translocation" EXACT PSI-MI-short []
is_a: MI:1088 ! phenotype-based detection assay
created_by: orchard
creation_date: 2011-07-05T11:27:16Z

[Term]
id: MI:1090
name: bimane label
def: "Bromobimanes are low molecular weight non-fluorescent alkyl halides which react with thiol groups to produce highly fluorescent derivatives. The bimane labels, monobromobimane, dibromobimane, and monobromotrimethylammoniobimane, are derivatives of syn-9,10-dioxabimane:1,5-diazabicyclo[3.3.0]octa-3,6-diene-2,8-dione." [PMID:7378449]
subset: PSI-MI_slim
synonym: "bimane" EXACT PSI-MI-short []
is_a: MI:0857 ! fluorescent dye label
created_by: orchard
creation_date: 2011-07-05T12:03:52Z

[Term]
id: MI:1091
name: publication title
def: "Title of the publication." [PMID:14755292]
subset: PSI-MI_slim
synonym: "title" EXACT PSI-MI-short []
is_a: MI:1093 ! bibliographic attribute name
created_by: orchard
creation_date: 2011-07-05T12:07:49Z

[Term]
id: MI:1092
name: atto label
def: "Fluorescent dyes - spectral range 500 to 700 nm." [PMID:14755292]
synonym: "atto label" EXACT PSI-MI-short []
is_a: MI:0857 ! fluorescent dye label
created_by: orchard
creation_date: 2011-07-05T12:14:52Z

[Term]
id: MI:1093
name: bibliographic attribute name
def: "Attributes specific to the publication." [PMID:14755292]
subset: PSI-MI_slim
synonym: "bib attribute" EXACT PSI-MI-short []
synonym: "publication attribute" EXACT []
is_a: MI:0665 ! experiment attribute name
created_by: orchard
creation_date: 2011-07-05T12:55:21Z

[Term]
id: MI:1094
name: genome databases
def: "Databases which are the responsible for the maintenance and subsequent annotation of one or more genomic sequences." [PMID:14755292]
subset: PSI-MI_slim
synonym: "genome databases" EXACT PSI-MI-short []
is_a: MI:0683 ! sequence database
created_by: orchard
creation_date: 2011-07-06T07:57:46Z

[Term]
id: MI:1095
name: hgnc
def: "HGNC is the nomenclature committee responsible for the naming of human genes." [PMID:20929869]
synonym: "hgnc" EXACT PSI-MI-short []
synonym: "Human Genome Nomenclature Committee" EXACT PSI-MI-short []
is_a: MI:1109 ! gene database
created_by: orchard
creation_date: 2011-07-06T08:02:03Z

[Term]
id: MI:1096
name: protein sequence databases
def: "Databases dedicated to the collection and annotation of protein sequences." [PMID:21447597]
subset: PSI-MI_slim
synonym: "protein seq db" EXACT PSI-MI-short []
is_a: MI:0683 ! sequence database
created_by: orchard
creation_date: 2011-07-06T08:10:40Z

[Term]
id: MI:1097
name: uniprot
def: "UniProt is a centralized repository of protein sequences with comprehensive coverage and a systematic approach to protein annotation, incorporating, interpreting, integrating and standardizing data from numerous sources and is the most comprehensive catalog of protein sequences and functional annotation." [PMID:21051339]
subset: PSI-MI_slim
synonym: "uniprot" EXACT PSI-MI-short []
is_a: MI:1096 ! protein sequence databases
created_by: orchard
creation_date: 2011-07-06T08:14:40Z

[Term]
id: MI:1098
name: uniprot/swiss-prot
def: "UniProt (Universal Protein Resource) is the world's most comprehensive catalogue of information on proteins. It is a central repository of protein sequence and function created by joining the information contained in Swiss-Prot, TrEMBL, and PIR. UniProtKB/Swiss-Prot is manually curated which means that the information in each entry is annotated and reviewed by a curator. \nhttp://www.uniprot.org" [PMID:14681372, PMID:21447597]
subset: PSI-MI_slim
synonym: "swiss-prot" EXACT PSI-MI-short []
synonym: "UniProt" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "[OPQ][0-9][A-Z0-9]{3}[0-9]|[A-NR-Z][0-9]([A-Z][A-Z0-9]{2}[0-9]){1,2}-PRO_[0-9]{10}"
xref: search-url: "http://www.uniprot.org/uniprot/${ac}"
is_a: MI:0486 ! uniprot knowledge base
created_by: orchard
creation_date: 2011-07-06T08:17:34Z

[Term]
id: MI:1099
name: uniprot/trembl
def: "UniProt (Universal Protein Resource) is the world's most comprehensive catalogue of information on proteins. It is a central repository of protein sequence and function created by joining the information contained in Swiss-Prot, TrEMBL, and PIR. The records in UniProtKB/TrEMBL are automatically generated and are enriched with automatic annotation and classification.\nhttp://www.uniprot.org" [PMID:14681372, PMID:21447597]
subset: PSI-MI_slim
synonym: "trembl" EXACT PSI-MI-short []
synonym: "UniProt" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "[OPQ][0-9][A-Z0-9]{3}[0-9]|[A-NR-Z][0-9]([A-Z][A-Z0-9]{2}[0-9]){1,2}-PRO_[0-9]{10}"
xref: search-url: "http://www.uniprot.org/uniprot/${ac}"
is_a: MI:0486 ! uniprot knowledge base
created_by: orchard
creation_date: 2011-07-06T08:20:24Z

[Term]
id: MI:1100
name: bioactive entity
def: "Molecules showing activity in a living system but not encoded by a genomic sequence." [PMID:14760721]
synonym: "bioactive entity" EXACT PSI-MI-short []
is_a: MI:0313 ! interactor type
created_by: orchard
creation_date: 2011-07-06T08:23:48Z

[Term]
id: MI:1101
name: standard inchi key
def: "The Standard InChIKey has five distinct components, a 14-character hash of the basic (Mobile-H) InChI layer, an 8-character hash of the remaining layers (except for the /p segment, which accounts for added or removed protons: it is not hashed at all; the number of protons is encoded at the end of the standard InChIKey.) , a 1 flag character, a 1 version character and the last character is a [de]protonation indicator. The overall length of InChIKey is fixed at 27 characters, including separators (dashes)." [PMID:23343401]
subset: PSI-MI_slim
is_a: MI:0970 ! inchi key
created_by: orchard
creation_date: 2014-01-21T10:14:02Z

[Term]
id: MI:1102
name: mapped-identity
def: "Sequence has been computationally remapped following removal or update of the original sequence in the underlying sequence database." [PMID:14760721]
synonym: "mapped-identity" EXACT PSI-MI-short []
is_a: MI:0353 ! cross-reference type
created_by: orchard
creation_date: 2011-07-06T09:07:02Z

[Term]
id: MI:1103
name: solution state nmr
def: "NMR solution state analysis provides useful data regarding the type, quantity and arrangement of different atoms in chemical systems, liquids and solids. Samples are dissolved in deuterated solvents and spectra consist of a series of very sharp\ntransitions, due to averaging of anisotropic NMR interactions\nby rapid random tumbling. Solution-state NMR only requires that the molecule be soluble at sufficient concentration for data collection, but becomes increasingly difficult for biomolecules over 30 kDa so that a practical size limitation is placed on full structure determinations." [PMID:20951674]
subset: PSI-MI_slim
synonym: "solution nmr" EXACT PSI-MI-short []
synonym: "solution state nmr" EXACT []
is_a: MI:0077 ! nuclear magnetic resonance
created_by: orchard
creation_date: 2011-07-06T09:16:45Z

[Term]
id: MI:1104
name: solid state nmr
def: "Solid-state NMR (ssNMR) does not require that the sample be soluble or form a crystal, and the approach can be used to study molecules larger than 100 kD. Solid-state NMR spectra are very broad, as the full\neffects of anisotropic or orientation-dependent interactions are observed in the spectrum." [PMID:20951674]
subset: PSI-MI_slim
synonym: "solid state nmr" EXACT PSI-MI-short []
synonym: "ssnmr" EXACT []
is_a: MI:0077 ! nuclear magnetic resonance
created_by: orchard
creation_date: 2011-07-06T09:23:11Z

[Term]
id: MI:1105
name: biocyc
def: "BioCyc is a collection of  Pathway/Genome Databases. Each database in the BioCyc collection describes the genome and metabolic pathways of a single organism. (http://biocyc.org/)." [PMID:19850718]
subset: PSI-MI_slim
synonym: "biocyc" EXACT PSI-MI-short []
is_a: MI:1106 ! pathways database
created_by: orchard
creation_date: 2011-07-06T09:43:03Z

[Term]
id: MI:1106
name: pathways database
def: "Databases which primarily exist to display biomolecular information in structured pathways. Interactions data can be inferred from the published pathways." [PMID:14755292]
subset: PSI-MI_slim
synonym: "pathways db" EXACT PSI-MI-short []
is_a: MI:0461 ! interaction database
created_by: orchard
creation_date: 2011-07-07T02:52:18Z

[Term]
id: MI:1107
name: pid
def: "Curated collection of information about known biomolecular interactions and key cellular processes assembled into signaling pathways. It is a collaborative project between the US National Cancer Institute (NCI) and Nature Publishing Group (NPG), and is an open access online resource (http://pid.nci.nih.gov/)." [PMID:18832364]
synonym: "pathways interaction database" EXACT []
synonym: "pid" EXACT PSI-MI-short []
is_a: MI:1106 ! pathways database
created_by: orchard
creation_date: 2011-07-07T03:00:27Z

[Term]
id: MI:1108
name: biocarta
def: "BioCarta, whose core business is in assays and reagents, has also developed a collection of diagrams representing molecular and cellular signal transduction pathways." [PMID:14760721]
synonym: "biocarta" EXACT PSI-MI-short []
is_a: MI:1106 ! pathways database
created_by: orchard
creation_date: 2011-07-07T03:05:55Z

[Term]
id: MI:1109
name: gene database
def: "Primarily nomenclature/cross-reference databases, used by curators to establish a link between a gene and protein ID.  In some cases, database records do not contain actual sequence but point to loci on specific reference genomes." [PMID:14755292]
subset: PSI-MI_slim
synonym: "gene dbs" EXACT PSI-MI-short []
is_a: MI:0473 ! participant database
created_by: orchard
creation_date: 2011-07-08T08:00:33Z

[Term]
id: MI:1110
name: predicted interaction
def: "Interaction has been predicted by either interologue mapping, by an algorithm or by a computational method." [PMID:14755292]
subset: PSI-MI_slim
synonym: "predicted" EXACT PSI-MI-short []
is_a: MI:0190 ! interaction type
created_by: orchard
creation_date: 2011-08-03T11:14:11Z

[Term]
id: MI:1111
name: two hybrid bait or prey pooling approach
def: "Individual baits are mated against pools of preys, or pools of baits are mated against individual preys. This approach required cloning baits and preys into both two-hybrid vectors, followed by pooling sets of transformants. The positive double hybrid clones are the interacting partners." [PMID:11283351, PMID:20946815]
subset: PSI-MI_slim
is_a: MI:0398 ! two hybrid pooling approach
created_by: orchard
creation_date: 2011-09-29T03:19:21Z

[Term]
id: MI:1112
name: two hybrid prey pooling approach
def: "Individual baits are mated against pools of preys. This approach required cloning baits and preys into both two-hybrid vectors, followed by pooling sets of transformants. The positive double hybrid clones are the interacting partners." [PMID:20946815]
subset: PSI-MI_slim
is_a: MI:1111 ! two hybrid bait or prey pooling approach
created_by: orchard
creation_date: 2011-09-29T03:21:01Z

[Term]
id: MI:1113
name: two hybrid bait and prey pooling approach
def: "def" [PMID:10655498]
subset: PSI-MI_slim
is_a: MI:0398 ! two hybrid pooling approach
created_by: orchard
creation_date: 2011-09-29T03:23:17Z

[Term]
id: MI:1114
name: virhostnet
def: "A database of viral-host interactions." [PMID:18984613]
subset: PSI-MI_slim
is_a: MI:0461 ! interaction database
created_by: orchard
creation_date: 2011-10-19T01:28:24Z

[Term]
id: MI:1115
name: spike
def: "SPIKE" [PMID:21097778]
subset: PSI-MI_slim
synonym: "Signalling Pathways Integrated Knowledge Engine" EXACT []
is_a: MI:1106 ! pathways database
created_by: orchard
creation_date: 2011-11-09T10:27:04Z

[Term]
id: MI:1116
name: genemania
def: "GeneMANIA predicts interactions based on multiple evidences including physical and genetic interactions, pathways, co-localisation, co-expression and protein domain similarity." [PMID:20576703]
subset: PSI-MI_slim
is_a: MI:0461 ! interaction database
created_by: orchard
creation_date: 2011-11-09T02:13:28Z

[Term]
id: MI:1117
name: topfind
def: "TopFIND provides information on protein N- and C-termini. Information of proteases and their substrates is provided." [PMID:21822272]
subset: PSI-MI_slim
synonym: "Termini-oriented protein function inferred database" EXACT []
is_a: MI:0461 ! interaction database
created_by: orchard
creation_date: 2011-11-16T11:09:25Z

[Term]
id: MI:1118
name: enhanced yellow fluorescent protein tag
def: "A variation of yellow fluorescent protein derived from eGFP." [PMID:10929120]
subset: PSI-MI_slim
synonym: "eyfp" EXACT PSI-MI-short []
is_a: MI:0368 ! yellow fluorescent protein tag
created_by: orchard
creation_date: 2011-11-24T03:17:33Z

[Term]
id: MI:1119
name: nYFP
def: "n-terminal fragment of yellow fluorescent protein used as a tag in bimolecular fluorescence complementation (BiFC)." [PMID:11983170]
subset: PSI-MI_slim
synonym: "N-terminal part of YFP" RELATED []
is_a: MI:0368 ! yellow fluorescent protein tag
is_a: MI:1215 ! bifc tag
created_by: orchard
creation_date: 2011-11-24T03:30:18Z

[Term]
id: MI:1120
name: cYFP
def: "c-terminal fragment of yellow fluorescent protein used as a tag in bimolecular fluorescence complementation (BiFC)." [PMID:11983170]
subset: PSI-MI_slim
synonym: "C-terminal part of YFP" RELATED []
is_a: MI:0368 ! yellow fluorescent protein tag
is_a: MI:1215 ! bifc tag
created_by: orchard
creation_date: 2011-11-24T03:43:07Z

[Term]
id: MI:1121
name: ceYFP
def: "c-terminal fragment of enhanced yellow fluorescent protein used as a tag in bimolecular fluorescence complementation (BiFC)." [PMID:11983170]
subset: PSI-MI_slim
synonym: "C-terminal part of EYFP" RELATED []
is_a: MI:1118 ! enhanced yellow fluorescent protein tag
created_by: orchard
creation_date: 2011-11-24T03:43:30Z

[Term]
id: MI:1122
name: neYFP
def: "n-terminal fragment of enhanced yellow fluorescent protein used as a tag in bimolecular fluorescence complementation (BiFC)." [PMID:11983170]
subset: PSI-MI_slim
synonym: "N-terminal part of EYFP" RELATED []
is_a: MI:1118 ! enhanced yellow fluorescent protein tag
created_by: orchard
creation_date: 2011-11-24T03:44:40Z

[Term]
id: MI:1123
name: bindingdb
def: "BindingDB is a web-accessible public database of experimentally determined protein-ligand binding affinities for drug discovery. http://BindingDB.org" [PMID:11812264, PMID:11836221, PMID:11987162, PMID:17145705]
subset: PSI-MI_slim
is_a: MI:0461 ! interaction database
created_by: orchard
creation_date: 2011-11-28T08:55:26Z

[Term]
id: MI:1124
name: pathwaycommons
def: "Allows the user to browse and search pathways across multiple public pathway databases.\nhttp://www.pathwaycommons.org" [PMID:21071392]
subset: PSI-MI_slim
synonym: "Pathway Commons" EXACT []
is_a: MI:1106 ! pathways database
created_by: orchard
creation_date: 2011-11-30T03:04:14Z

[Term]
id: MI:1125
name: direct binding region
def: "The defined region of protein which makes physical contact with the interacting partner." [PMID:14755292]
comment: Should normally be used with X-ray crystallography or NMR data.
subset: PSI-MI_slim
synonym: "direct binding" EXACT PSI-MI-short []
is_a: MI:0442 ! sufficient binding region
created_by: orchard
creation_date: 2012-01-03T01:10:25Z

[Term]
id: MI:1126
name: self interaction
def: "Intra-molecular interaction between two or more regions of the same molecule." [PMID:14755292]
comment: The corresponding experimental role will be self/putative self. Not to be used for autocatalysis, when the additional biological role self/putative self will supply this information.
subset: PSI-MI_slim
is_a: MI:0407 ! direct interaction
created_by: orchard
creation_date: 2012-01-03T01:19:22Z

[Term]
id: MI:1127
name: putative self interaction
def: "Interaction between two or more regions of possibly the same molecule but it is also possible that the observation is due to an interaction between two identical molecules." [PMID:14755292]
comment: The corresponding experimental role should be self/putative self. Not to be used for autocatalysis, when the additional biological role self/putative self will supply this information.
subset: PSI-MI_slim
is_a: MI:0407 ! direct interaction
created_by: orchard
creation_date: 2012-01-03T01:21:58Z

[Term]
id: MI:1128
name: mutation disrupting interaction strength
def: "Region of a molecule whose mutation or deletion totally disrupts an interaction strength." [PMID:14755292]
subset: PSI-MI_slim
synonym: "mutation disrupting strength" EXACT PSI-MI-short []
is_a: MI:0573 ! mutation disrupting interaction
created_by: orchard
creation_date: 2012-01-03T01:36:37Z

[Term]
id: MI:1129
name: mutation disrupting interaction rate
def: "Region of a molecule whose mutation or deletion totally disrupts an interaction  rate (in the case of interactions inferred from enzymatic reaction).." [PMID:14755292]
subset: PSI-MI_slim
synonym: "mutation disrupting rate" EXACT PSI-MI-short []
is_a: MI:0573 ! mutation disrupting interaction
created_by: orchard
creation_date: 2012-01-03T01:37:43Z

[Term]
id: MI:1130
name: mutation decreasing interaction rate
def: "Region of a molecule whose mutation or deletion decreases significantly interaction rate (in the case of interactions inferred from enzymatic reaction)." [PMID:14755292]
subset: PSI-MI_slim
synonym: "mutation decreasing rate" EXACT PSI-MI-short []
is_a: MI:0119 ! mutation decreasing interaction
created_by: orchard
creation_date: 2012-01-03T01:38:58Z

[Term]
id: MI:1131
name: mutation increasing interaction rate
def: "Region of a molecule whose mutation or deletion increases significantly interaction rate (in the case of interactions inferred from enzymatic reaction)." [PMID:14577292]
subset: PSI-MI_slim
synonym: "mutation increasing rate" EXACT PSI-MI-short []
is_a: MI:0382 ! mutation increasing interaction
created_by: orchard
creation_date: 2012-01-03T01:45:09Z

[Term]
id: MI:1132
name: mutation increasing interaction strength
def: "Region of a molecule whose mutation or deletion increases significantly interaction strength." [PMID:14577292]
subset: PSI-MI_slim
synonym: "mutation increasing strength" EXACT PSI-MI-short []
is_a: MI:0382 ! mutation increasing interaction
created_by: orchard
creation_date: 2012-01-03T01:45:42Z

[Term]
id: MI:1133
name: mutation decreasing interaction strength
def: "Region of a molecule whose mutation or deletion decreases significantly interaction strength." [PMID:14755292]
subset: PSI-MI_slim
synonym: "mutation decreasing strength" EXACT PSI-MI-short []
is_a: MI:0119 ! mutation decreasing interaction
created_by: orchard
creation_date: 2012-01-03T01:48:40Z

[Term]
id: MI:1134
name: mcherry fluorescent protein tag
def: "mCherry is a red monomer which matures extremely rapidly, making it possible to see results very soon after activating transcription. It is highly photostable and resistant to photobleaching. Excitation maximum: 587 nm. Emission maximum: 610 nm." []
synonym: "mcherry" EXACT PSI-MI-short []
is_a: MI:0732 ! red fluorescent protein tag
created_by: orchard
creation_date: 2012-01-03T02:53:23Z

[Term]
id: MI:1135
name: venus fluorescent protein tag
def: "Introduction of a point mutation into Aequorea-derived YFP, the substitution of leucine for phenylalanine at position 46 (F46L), produced  Venus. This mutation dramatically accelerates oxidation of the chromophore, the rate-limiting step in fluorescent protein maturation. Additional mutations were also introduced in order to increase the tolerance of Venus to acidic environments and to reduce the sensitivity to chloride. The absorption and emission spectral peaks are 515 and 528 nanometers, respectively." [PMID:14755292]
subset: PSI-MI_slim
synonym: "venus" EXACT PSI-MI-short []
is_a: MI:0368 ! yellow fluorescent protein tag
created_by: orchard
creation_date: 2012-01-03T03:05:01Z

[Term]
id: MI:1136
name: kusabira-green protein tag
def: "Monomeric coral fluorescent reporter protein." [PMID:14755292]
subset: PSI-MI_slim
synonym: "kusabira-green" EXACT PSI-MI-short []
is_a: MI:0367 ! green fluorescent protein tag
created_by: orchard
creation_date: 2012-01-03T03:10:28Z

[Term]
id: MI:1137
name: carboxylation assay
def: "The measurement of a the introduction of a carboxylic acid group into a substrate." [PMID:14755292]
subset: PSI-MI_slim
synonym: "carboxylation assay" EXACT PSI-MI-short []
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2012-01-03T03:17:56Z

[Term]
id: MI:1138
name: decarboxylation assay
def: "The measurement of a the introduction of a carboxylic acid group into a substrate." [PMID:14755292]
subset: PSI-MI_slim
synonym: "decarboxxylation assay" EXACT PSI-MI-short []
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2012-01-03T03:22:04Z

[Term]
id: MI:1139
name: carboxylation reaction
def: "Carboxylation is a posttranslational modification of glutamate residues, to gamma-carboxyglutamate, in proteins." [PMID:14755292]
subset: PSI-MI_slim
synonym: "carboxylation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction
created_by: orchard
creation_date: 2012-01-03T03:24:05Z

[Term]
id: MI:1140
name: decarboxylation reaction
def: "Decarboxylation is a chemical reaction that releases carbon dioxide (CO2). Usually, decarboxylation refers to a reaction of carboxylic acids, removing a carbon atom from a carbon chain. Enzymes that catalyze decarboxylations are called decarboxylases or, the more formal term, carboxy-lyases (EC number 4.1.1)." [PMID:14755292]
subset: PSI-MI_slim
synonym: "decarboxylation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction
created_by: orchard
creation_date: 2012-01-03T03:31:42Z

[Term]
id: MI:1141
name: s tag
def: "S-tag is the name of an oligopeptide derived from pancreatic ribonuclease A (RNase A). The amino acid sequence of the S-tag is: Lys-Glu-Thr-Ala-Ala-Ala-Lys-Phe-Glu-Arg-Gln-His-Met-Asp-Ser." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0507 ! tag
created_by: orchard
creation_date: 2012-01-03T03:37:51Z

[Term]
id: MI:1142
name: aminoacylation assay
def: "The measurement of the addition of an aminoacyl group to a compound." [PMID:14755292]
subset: PSI-MI_slim
synonym: "aminoacylation" EXACT PSI-MI-short []
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2012-01-03T03:46:46Z

[Term]
id: MI:1143
name: aminoacylation reaction
def: "Aminoacylation is the process of adding an aminoacyl group to a compound." [PMID:14755292]
subset: PSI-MI_slim
synonym: "aminoacylation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction
created_by: orchard
creation_date: 2012-01-03T03:49:50Z

[Term]
id: MI:1144
name: protein a tag visualisation
def: "Protein A tag is visualized by interacting with IgG antibodies (or their derivatives) that are specifically recognized by protein A." [PMID:14755292]
subset: PSI-MI_slim
synonym: "protein a visualisation" EXACT PSI-MI-short []
is_a: MI:0866 ! tag visualisation
created_by: orchard
creation_date: 2012-01-03T03:54:35Z

[Term]
id: MI:1145
name: phospholipase assay
def: "A phospholipase is an enzyme that hydrolyzes phospholipids into fatty acids and other lipophilic substances. There are four major classes, termed A, B, C and D, distinguished by the type of reaction which they catalyze." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2012-01-03T04:04:16Z

[Term]
id: MI:1146
name: phospholipase reaction
def: "Measurement of the hydrolysis of phospholipids into fatty acids and other lipophilic substances. There are four major classes, termed A, B, C and D, distinguished by the type of reaction which they catalyze." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0414 ! enzymatic reaction
created_by: orchard
creation_date: 2012-01-03T04:08:14Z

[Term]
id: MI:1147
name: ampylation assay
def: "Measurement of AMPylation, the formation of a phosphodiester or phosphoramide ester of AMP on Tyr (RESID:AA0203), Lys (RESID:AA0227), Thr (RESID:AA0267), His (RESID:AA0371) and other amino\nacids." [PMID:14755292]
subset: PSI-MI_slim
synonym: "ampylation assay" EXACT PSI-MI-short []
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2012-01-03T04:18:27Z

[Term]
id: MI:1148
name: ampylation reaction
def: "AMPylation, previously known as adenylylation, is formation of a\nphosphodiester or phosphoramide ester of AMP on Tyr (RESID:AA0203), Lys\n(RESID:AA0227), Thr (RESID:AA0267), His (RESID:AA0371) and other amino\nacids." [PMID:14755292]
subset: PSI-MI_slim
synonym: "ampylation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction
created_by: orchard
creation_date: 2012-01-03T04:21:12Z

[Term]
id: MI:1149
name: cooperative interaction
def: "A set of molecular binding events that influence each other either positively or negatively through allostery or pre-assembly. In this context, covalent post-translational modifications are considered as binding events. CV terms that are part of this term allow the description of cooperative interactions using the current PSI-MI schema." [PMID:18641616]
subset: PSI-MI_slim
synonym: "cooperativity" EXACT []
is_a: MI:0000 ! molecular interaction
created_by: orchard
creation_date: 2012-06-07T12:21:30Z

[Term]
id: MI:1150
name: affected interaction
def: "For an interaction that has a cooperative effect on a subsequent interaction, this term indicates which subsequent interaction is affected. The affected interaction is identified by referring to its interaction id." [PMID:18641616]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
relationship: part_of MI:1149 ! cooperative interaction
created_by: orchard
creation_date: 2012-06-07T12:26:42Z

[Term]
id: MI:1151
name: participant-ref
def: "Referring to a previously described interaction as a participant allows the description of ordered assembly of molecular complexes in PSI-MI2.5. When one of the components of the preformed complex has a feature, the participant-ref term indicates on which component this feature is located. The component is identified by referring to its participant id in the previous interaction." [PMID:18641616]
subset: PSI-MI_slim
is_a: MI:0668 ! feature attribute name
created_by: orchard
creation_date: 2012-06-07T12:30:48Z

[Term]
id: MI:1152
name: cooperative effect value
def: "This value quantifies the cooperative effect of an interaction on a subsequent interaction. It is the fold change of the affinity or a catalytic parameter of a molecule for one ligand in the absence, versus presence, of a second ligand or a post-translational modification." [PMID:18706817]
subset: PSI-MI_slim
synonym: "cooperative coupling" EXACT []
is_a: MI:0664 ! interaction attribute name
relationship: part_of MI:1149 ! cooperative interaction
created_by: orchard
creation_date: 2012-06-07T12:35:01Z

[Term]
id: MI:1153
name: cooperative effect outcome
def: "For an interaction that has a cooperative effect on a subsequent interaction, this term indicates whether this effect is positive or negative, i.e. whether the subsequent interaction is augmented or diminished." [PMID:18706817]
is_a: MI:1149 ! cooperative interaction
created_by: orchard
creation_date: 2012-06-07T12:40:41Z

[Term]
id: MI:1154
name: positive cooperative effect
def: "This term specifies that an interaction augments a subsequent interaction." [PMID:18706817]
is_a: MI:0664 ! interaction attribute name
is_a: MI:1153 ! cooperative effect outcome
created_by: orchard
creation_date: 2012-06-07T12:42:19Z

[Term]
id: MI:1155
name: negative cooperative effect
def: "This term specifies that an interaction diminishes a subsequent interaction." [PMID:18706817]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1153 ! cooperative effect outcome
created_by: orchard
creation_date: 2012-06-07T12:43:48Z

[Term]
id: MI:1156
name: cooperative mechanism
def: "For an interaction that has a cooperative effect on a subsequent interaction, this term indicates the process that mediates this effect." [PMID:18641616]
subset: PSI-MI_slim
is_a: MI:1149 ! cooperative interaction
created_by: orchard
creation_date: 2012-06-07T12:46:30Z

[Term]
id: MI:1157
name: allostery
def: "Reciprocal energetic coupling between two binding events at distinct sites on the same molecule. The first binding event alters the binding or catalytic properties of the molecule for the second binding event." [PMID:18641616, PMID:18706817]
subset: PSI-MI_slim
synonym: "allosteric regulation" EXACT []
is_a: MI:0664 ! interaction attribute name
is_a: MI:1156 ! cooperative mechanism
created_by: orchard
creation_date: 2012-06-07T12:50:20Z

[Term]
id: MI:1158
name: pre-assembly
def: "A non-allosteric mechanism where the strength of an interaction depends on whether or not a particular molecular complex already exists." [PMID:18641616]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1156 ! cooperative mechanism
created_by: orchard
creation_date: 2012-06-07T12:52:44Z

[Term]
id: MI:1159
name: allosteric molecule
def: "A molecule whose binding or catalytic properties at one site are altered by allosteric post-translational modification or binding of an allosteric effector at a distinct site. An allosteric molecule is identified by referring to its participant id." [PMID:18706817]
subset: PSI-MI_slim
is_a: MI:0500 ! biological role
is_a: MI:0664 ! interaction attribute name
relationship: part_of MI:1149 ! cooperative interaction
created_by: orchard
creation_date: 2012-06-07T12:55:09Z

[Term]
id: MI:1160
name: allosteric effector
def: "A ligand that elicits an allosteric response upon binding to a target molecule." [PMID:18706817]
subset: PSI-MI_slim
is_a: MI:0500 ! biological role
is_a: MI:0664 ! interaction attribute name
relationship: part_of MI:1149 ! cooperative interaction
created_by: orchard
creation_date: 2012-06-07T12:57:50Z

[Term]
id: MI:1161
name: allosteric response
def: "This term describes the effect of an allosteric binding event. It specifies which properties of the allosteric molecule are altered, i.e. whether the interaction alters either (a) binding or (b) catalytic properties of the allosteric molecule at a site distinct from the allosteric site." []
subset: PSI-MI_slim
is_a: MI:1149 ! cooperative interaction
created_by: orchard
creation_date: 2012-06-07T01:05:17Z

[Term]
id: MI:1162
name: allosteric k-type response
def: "An allosteric response in which the affinity of a molecule is altered." [PMID:18706817]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1161 ! allosteric response
created_by: orchard
creation_date: 2012-06-07T01:08:01Z

[Term]
id: MI:1163
name: allosteric v-type response
def: "An allosteric response in which catalysis (kcat or Vmax) of an enzyme is altered." [PMID:18706817]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1161 ! allosteric response
created_by: orchard
creation_date: 2012-06-07T01:09:07Z

[Term]
id: MI:1164
name: allosteric mechanism
def: "The process that mediates the allosteric response of a molecule upon allosteric post-translational modification or binding of an allosteric effector." []
is_a: MI:1149 ! cooperative interaction
created_by: orchard
creation_date: 2012-06-07T01:10:45Z

[Term]
id: MI:1165
name: allosteric change in structure
def: "The allosteric mechanism where changes in the local structure of an allosteric molecule result in altered binding or catalytic properties." [PMID:18706817]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1164 ! allosteric mechanism
created_by: orchard
creation_date: 2012-06-07T01:16:20Z

[Term]
id: MI:1166
name: allosteric change in dynamics
def: "The allosteric mechanism where changes in the local dynamics of an allosteric molecule result in altered binding or catalytic properties." [PMID:18706817]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1164 ! allosteric mechanism
created_by: orchard
creation_date: 2012-06-07T01:17:54Z

[Term]
id: MI:1167
name: allostery type
def: "This term indicates the chemical relationship between the two ligands whose binding is allosterically coupled." [PMID:18706817]
subset: PSI-MI_slim
is_a: MI:1149 ! cooperative interaction
created_by: orchard
creation_date: 2012-06-07T01:19:57Z

[Term]
id: MI:1168
name: heterotropic allostery
def: "The type of allostery that occurs when the two ligands whose binding is allosterically coupled are not chemically identical." [PMID:18706817]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1167 ! allostery type
created_by: orchard
creation_date: 2012-06-07T01:21:25Z

[Term]
id: MI:1169
name: homotropic allostery
def: "The type of allostery that occurs when the two ligands whose binding is allosterically coupled are chemically identical." [PMID:18706817]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1167 ! allostery type
created_by: orchard
creation_date: 2012-06-07T01:22:35Z

[Term]
id: MI:1170
name: pre-assembly response
def: "This term describes the way in which preformation of a molecular complex has a non-allosteric cooperative effect on subsequent interactions of its components." [PMID:18641616]
subset: PSI-MI_slim
is_a: MI:1149 ! cooperative interaction
created_by: orchard
creation_date: 2012-06-07T01:24:42Z

[Term]
id: MI:1171
name: composite binding site formation
def: "The preformation of a complex results in the generation of a continuous binding site that spans more than one component of this complex. The functional binding site does not exist outside the context of the preformed complex." [PMID:18641616]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1170 ! pre-assembly response
created_by: orchard
creation_date: 2012-06-07T01:25:50Z

[Term]
id: MI:1172
name: altered physicochemical compatibility
def: "The addition of a PTM to an interaction interface affects the physicochemical compatibility of the binding site with its binding partner. This can either induce or enhance an interaction, or result in inhibition or even abrogation of an interaction. Multisite modification can mediate rheostatic regulation of the interaction." [PMID:22480932]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1170 ! pre-assembly response
created_by: orchard
creation_date: 2012-06-07T01:26:56Z

[Term]
id: MI:1173
name: binding site hiding
def: "The occurrence of overlapping or adjacent, mutually exclusive binding sites promotes competitive binding. When there is a large difference in affinity of the different sites or in local abundance of competitors, binding at one site results in hiding of the second site, thereby precluding it from interacting when the hiding molecule is present." [PMID:22480932]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1170 ! pre-assembly response
created_by: orchard
creation_date: 2012-06-07T01:28:07Z

[Term]
id: MI:1174
name: configurational pre-organization
def: "Multivalent ligands form multiple discrete interactions with one or more binding partners. In some cases, An initial binding event can pre-organize other sites for binding. This reduces the degrees of freedom of these sites, thus reducing the entropic costs of their interactions. In addition, the combined strength of multiple interactions increases the enthalpic stability of each interaction (avidity effect). As a result of such effects, interactions of this kind can have a cooperative effect on subsequent interactions." [PMID:18641616]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1170 ! pre-assembly response
created_by: orchard
creation_date: 2012-06-07T01:29:13Z

[Term]
id: MI:1175
name: allosteric post-translational modification
def: "A post-translational modification that elicits an allosteric response upon addition to a target molecule. An allosteric post-translational modification is identified by referring to its feature id." [PMID:18706817]
subset: PSI-MI_slim
synonym: "allosteric ptm" EXACT PSI-MI-short []
is_a: MI:0252 ! biological feature
is_a: MI:0664 ! interaction attribute name
relationship: part_of MI:1149 ! cooperative interaction
created_by: orchard
creation_date: 2012-06-07T01:33:16Z

[Term]
id: MI:1176
name: sequence based prediction of gene regulatory region binding sites
def: "Sequence analysis of the regulatory region of a gene used to predict specific elements, transcription factor binding sites (TFBS), where binding of specific transcription factors can occur." [PMID:15131651]
subset: PSI-MI_slim
synonym: "gene regulatory region prediction" RELATED []
synonym: "sequence based prediction of TG regulatory region binding sites  for TF " RELATED []
is_a: MI:0101 ! sequence based prediction
created_by: orchard
creation_date: 2012-06-07T01:40:25Z

[Term]
id: MI:1177
name: phylogenetic profiling of predicted gene regulatory region binding sites
def: "Sequence analysis based on multiple homologous alignments of the regulatory region of a gene used to predict specific elements, transcription factor binding sites (TFBS), where binding of specific transcription factors can occur. These methods often also use transcription factor binding motif models." [PMID:12671656]
subset: PSI-MI_slim
synonym: "gene regulatory region phylogeny" EXACT []
synonym: "phylogenetic footprinting" RELATED []
is_a: MI:0100 ! sequence based phylogenetic profile
is_a: MI:1176 ! sequence based prediction of gene regulatory region binding sites
created_by: orchard
creation_date: 2012-06-07T01:41:59Z

[Term]
id: MI:1178
name: sequence based prediction of binding of transcription factor to transcribed gene regulatory elements
def: "Computational methods based on evolutionary hypothesis, used as criteria to browse sequences and predict a transcription factor using structural and sequence features of the protein, e.g., by evaluating if the potential transcription factor protein contains a DNA-binding domain that is known to bind to some regulatory elements, or prediction of transcription factor functional domains (DNA binding, transcription factor dimerization, etc.), all based on sequence or structural features of the transcription factor." [PMID:16381970]
subset: PSI-MI_slim
synonym: "sequence based prediction of binding of TF to TG promoter" EXACT []
synonym: "transcription factor prediction" EXACT []
is_a: MI:0101 ! sequence based prediction
created_by: orchard
creation_date: 2012-06-07T01:43:57Z

[Term]
id: MI:1179
name: partial nucleotide sequence identification
def: "Identification of a part of a nucleotide sequence, usually then related to the full length sequence by alignment. Depending on the experimental design, nucleotide sequence can be determined before the interaction detection while building a collection of clones or after the selection of randomly generated clone.s" [PMID:14755292]
subset: PSI-MI_slim
synonym: "partial nucleotide sequence" EXACT PSI-MI-short []
is_a: MI:0078 ! nucleotide sequence identification
created_by: orchard
creation_date: 2012-06-07T01:47:03Z

[Term]
id: MI:1180
name: partial DNA sequence identification
def: "Identification of a part of a DNA sequence, usually then related to the full length sequence by alignment. Depending on the experimental design, nucleotide sequence can be determined before the interaction detection while building a collection of clones or after the selection of randomly generated clones." [PMID:14755292]
subset: PSI-MI_slim
synonym: "partial dna sequence" EXACT PSI-MI-short []
is_a: MI:1179 ! partial nucleotide sequence identification
created_by: orchard
creation_date: 2012-06-07T01:52:27Z

[Term]
id: MI:1181
name: paired end tags sequence identification
def: "Paired-end tags (PET) are the short sequences at the 5 prime and 3 prime ends of the DNA fragment of interest, which can be a piece of genomic DNA or cDNA." [PMID:19339662]
subset: PSI-MI_slim
synonym: "paired end tags" EXACT PSI-MI-short []
is_a: MI:1180 ! partial DNA sequence identification
created_by: orchard
creation_date: 2012-06-07T01:53:38Z

[Term]
id: MI:1182
name: full identification by RNA sequencing
def: "Sequencing occurs during the course of the experiment. To sequence RNA, the usual method is first to reverse transcribe the sample to generate cDNA fragments." []
subset: PSI-MI_slim
is_a: MI:0078 ! nucleotide sequence identification
created_by: orchard
creation_date: 2012-06-07T02:02:37Z

[Term]
id: MI:1183
name: nuclease footprinting
def: "Binding of a molecule to a strand of nucleic acid protects that region of nucleic acid from the action of a nuclease. The protected region can subsequently be sequenced and the binding site identified." [PMID:7685766]
subset: PSI-MI_slim
synonym: "nuclease protection" RELATED []
is_a: MI:0605 ! enzymatic footprinting
created_by: orchard
creation_date: 2012-06-07T02:08:36Z

[Term]
id: MI:1184
name: dna adenine methyltransferase identification
def: "DNA adenine methyltransferase identification is used to map the binding sites of DNA- and chromatin-binding proteins in eukaryotes. DamID identifies binding sites by expressing the proposed DNA-binding protein as a fusion protein with DNA methyltransferase. Binding of the protein of interest to DNA localizes the methyltransferase in the region of the binding site. Adenosine methylation does not occur naturally in eukaryotes and therefore adenine methylation in any region can be concluded to have been caused by the fusion protein, implying the region is located near a binding site." [PMID:10748524]
subset: PSI-MI_slim
synonym: "DamID" EXACT PSI-MOD-short []
is_a: MI:1313 ! proximity labelling technology
created_by: orchard
creation_date: 2012-06-07T02:13:03Z

[Term]
id: MI:1185
name: tag visualisation by dna adenine methyltransferase
def: "Proteins of interest are tagged with Escherichia coli DNA adenine methyltransferase (dam). Expression of this fusion protein in vivo leads to preferential methylation of adenines in DNA surrounding the native binding sites of the dam fusion partner. Because adenine methylation does not occur endogenously in most eukaryotes, it provides a unique tag to mark protein interaction sites. The adenine-methylated DNA fragments are isolated by selective polymerase chain reaction amplification and can be identified by microarray hybridization." [PMID:10748524]
subset: PSI-MI_slim
synonym: "tag DNA methyltransferase" EXACT PSI-MI-short []
is_a: MI:0980 ! tag visualisation by enzyme assay
created_by: orchard
creation_date: 2012-06-07T02:22:19Z

[Term]
id: MI:1186
name: dna methyltransferase tag
def: "The protein of interest is fused to Escherichia coli DNA adenine methyltransferase (dam). Expression of this fusion protein in vivo leads to preferential methylation of adenines in DNA surrounding the native binding sites of the dam fusion partner. Because adenine methylation does not occur endogenously in most eukaryotes, it provides a unique tag to mark protein interaction sites." [PMID:10748524]
subset: PSI-MI_slim
is_a: MI:0365 ! enzyme tag
created_by: orchard
creation_date: 2012-06-07T02:32:02Z

[Term]
id: MI:1187
name: damip
def: "A mutant form of DNA adenine methyltransferase (DamK9A) from E. coli is fused to the protein of interest and expressed. The fusion protein will bind to target binding sites and introduce N-6-adenine methylation in nearby sites in the genomic DNA. Methylated DNA fragments are enriched with an antibody against N-6-methyladenine and used for further analysis." [PMID:21472695]
subset: PSI-MI_slim
is_a: MI:1184 ! dna adenine methyltransferase identification
created_by: orchard
creation_date: 2012-06-07T02:41:40Z

[Term]
id: MI:1188
name: tag visualisation by mutated dna adenine methyltransferase
def: "A mutant form of DNA adenine methyltransferase (DamK9A) from E. coli is fused to the protein of interest and expressed. The fusion protein will bind to target binding sites and introduce N-6-adenine methylation in nearby sites in the genomic DNA." []
is_a: MI:1185 ! tag visualisation by dna adenine methyltransferase
created_by: orchard
creation_date: 2012-06-07T02:46:08Z

[Term]
id: MI:1189
name: methylation interference assay
def: "In interference assays, the DNA will be methylated before the binding assay.  Protein binding to DNA protects DNA from methylation  by dimethylsulphate. If the contact points are methylated, the protein binding is prevented. After isolating the protein-DNA complex, the methylation sites are cleaved by chemical method. As a result, only those regions out of the binding sites will be cleaved. The protein binding region is not methylated; hence, this region is not cleaved. Although the pattern looks like a footprint, the blank region means \"contact points\"." [PMID:21720958]
subset: PSI-MI_slim
synonym: "contact point analysis" RELATED []
synonym: "methylation interference" EXACT PSI-MI-short []
synonym: "methylation protection assay" RELATED []
is_a: MI:0605 ! enzymatic footprinting
created_by: orchard
creation_date: 2012-06-07T02:54:00Z

[Term]
id: MI:1190
name: hydroxy radical footprinting
def: "Hydroxyl radicals are created from the Fenton reaction, which involves reducing Fe2+ with H2O2 to form free hydroxyl molecules. These hydroxyl molecules react with the DNA backbone, resulting in a break. Protein bound regions of the DNA are protected." [PMID:3090544]
subset: PSI-MI_slim
is_a: MI:0602 ! chemical footprinting
created_by: orchard
creation_date: 2012-06-07T03:10:48Z

[Term]
id: MI:1191
name: ultraviolet (uv) footprinting
def: "Ultraviolet irradiation excites nucleic acids and creates photoreactions, which results in damaged bases in the DNA strand. Protein bound regions of the DNA are protected. UV footprinting technique can detect sequence-specific protein-DNA interactions in vivo. Protein contacts can inhibit of enhance UV photoproduct formation by affecting the ability of DNA to adopt a geometry necessary for the formation of a UV photoproduct. Thus, differences in the strand-breakage patterns of protein-free and protein-bound DNA can be used to detect protein-DNA contacts." [PMID:2842760, PMID:6728031]
subset: PSI-MI_slim
is_a: MI:0417 ! footprinting
created_by: orchard
creation_date: 2012-06-07T03:13:02Z

[Term]
id: MI:1192
name: antisense oligonucleotides
def: "This approach is based on the observation that  a synthesized nucleic acid that is complementary to a specific mRNA can decrease the synthesis of its gene product either by increasing the degradation of the targeted mRNA or by interfering with its translation." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0255 ! post transcriptional interference
created_by: orchard
creation_date: 2012-06-07T03:19:22Z

[Term]
id: MI:1193
name: partial RNA sequence identification
def: "Identification of a part of a RNA sequence, usually then related to the full length sequence by alignment." [PMID:14755292]
synonym: "partial rna sequence" EXACT PSI-MI-short []
is_a: MI:1179 ! partial nucleotide sequence identification
created_by: orchard
creation_date: 2012-06-07T03:40:14Z

[Term]
id: MI:1194
name: reverse transcription pcr
def: "Reverse Transcription PCR (RT-PCR) is used for amplifying DNA from RNA. Reverse transcriptase reverse transcribes RNA into cDNA, which is then amplified by PCR." [PMID:12958470]
subset: PSI-MI_slim
synonym: "reverse PCR" RELATED []
synonym: "RPCR" RELATED []
synonym: "RT-PCR" EXACT PSI-MI-short []
is_a: MI:0088 ! primer specific pcr
created_by: orchard
creation_date: 2012-06-07T03:47:13Z

[Term]
id: MI:1195
name: quantitative pcr
def: "Quantitative PCR (Q-PCR) is used to measure the quantity of a PCR product (commonly in real-time). It quantitatively measures starting amounts of DNA, cDNA, or RNA." [PMID:12958470]
subset: PSI-MI_slim
synonym: "q-pcr" EXACT PSI-MI-short []
synonym: "QRT-PCR" RELATED []
synonym: "RQ-PCR" RELATED []
synonym: "RTQ-PCR" RELATED []
is_a: MI:0088 ! primer specific pcr
created_by: orchard
creation_date: 2012-06-07T03:56:38Z

[Term]
id: MI:1196
name: quantitative reverse transcription pcr
def: "Technique used to measure the quantity of DNA amplified from RNA." [PMID:12958470]
subset: PSI-MI_slim
synonym: "QRT-PCR" EXACT PSI-MI-short []
synonym: "RTQ-PCR" RELATED []
is_a: MI:1194 ! reverse transcription pcr
created_by: orchard
creation_date: 2012-06-07T04:04:42Z

[Term]
id: MI:1197
name: radioimmunoassay
def: "To perform a radioimmunoassay, a known quantity of an antigen is made radioactive, frequently by labeling it with gamma-radioactive isotopes of iodine attached to tyrosine. This radiolabeled antigen is then mixed with a known amount of antibody for that antigen, and as a result, the two chemically bind to one another. Then, a sample containing an unknown quantity of that same antigen is added. This causes the unlabeled (or \"cold\") antigen from the serum to compete with the radiolabeled antigen (\"hot\") for antibody binding sites. As the concentration of \"cold\" antigen is increased, more of it binds to the antibody, displacing the radiolabeled variant, and reducing the ratio of antibody-bound radiolabeled antigen to free radiolabeled antigen. The bound antigens are then separated from the unbound ones, and the radioactivity of the free antigen remaining in the supernatant is measured." [PMID:13846364.]
synonym: "RIA" EXACT []
is_a: MI:0421 ! identification by antibody
created_by: orchard
creation_date: 2012-06-07T04:13:30Z

[Term]
id: MI:1198
name: immunohistochemistry
def: "Method using an antibody coupled with some colouring agent to detect a specific protein within a tissue sample. In some cases the primary antibody is directly linked to a colouring agent, more often the primary antibody is targeted by a secondary antibody, targeting the primary antibody." [PMID:16006601]
subset: PSI-MI_slim
is_a: MI:0422 ! immunostaining
created_by: orchard
creation_date: 2012-06-07T04:17:12Z

[Term]
id: MI:1199
name: anti-tag immunohistochemistry
def: "Method using an antibody coupled with some colouring agent to detect a tag fused to a specific protein within a tissue sample. In some cases the primary antibody is directly linked to a colouring agent, more often the primary antibody is targeted by a secondary antibody, targeting the primary antibody." [PMID:16006601]
subset: PSI-MI_slim
is_a: MI:1198 ! immunohistochemistry
created_by: orchard
creation_date: 2012-06-07T04:21:23Z

[Term]
id: MI:1200
name: immunocytochemistry
def: "Method using an antibody coupled with some colouring agent to detect a specific protein within a cell. In some cases the primary antibody is directly linked to a colouring agent, more often the primary antibody is targeted by a secondary antibody, targeting the primary antibody." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0422 ! immunostaining
created_by: orchard
creation_date: 2012-06-07T04:22:00Z

[Term]
id: MI:1201
name: anti-tag immunocytochemistry
def: "Method using an antibody coupled with some colouring agent to detect a specific tag fused to a protein within a cell. In some cases the primary antibody is directly linked to a colouring agent, more often the primary antibody is targeted by a secondary antibody, targeting the primary antibody." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1200 ! immunocytochemistry
created_by: orchard
creation_date: 2012-06-07T04:33:37Z

[Term]
id: MI:1202
name: one-strep-tag
def: "Synthetic peptide tag (SAWSHPQFEK-(GGGS)2-SAWSHPQFEK)" [PMID:19688738]
subset: PSI-MI_slim
synonym: "<new synonym>" RELATED []
synonym: "twin-strep-tag" EXACT PSI-MI-alternate []
is_a: MI:0507 ! tag
created_by: orchard
creation_date: 2012-06-07T04:44:55Z

[Term]
id: MI:1203
name: split luciferase complementation
def: "Two proteins of interest, a bait and prey, which are genetically fused to amino- and carboxy-terminal fragments of luciferase, are transiently expressed. Physical interactions of these bait and prey proteins reconstitute some of the luciferase activity and result in light emission in the presence of the luciferase substrate." [PMID:20734273]
subset: PSI-MI_slim
is_a: MI:0090 ! protein complementation assay
created_by: orchard
creation_date: 2012-06-07T04:56:59Z

[Term]
id: MI:1204
name: split firefly luciferase complementation
def: "Two proteins of interest, a bait and prey, which are genetically fused to amino- and carboxy-terminal fragments of firefly (Photinus pyralis) luciferase, are transiently expressed. Physical interactions of these bait and prey proteins reconstitute some of the luciferase activity and result in light emission in the presence of the luciferase substrate." [PMID:20734273, PMID:22070901]
subset: PSI-MI_slim
is_a: MI:1203 ! split luciferase complementation
created_by: orchard
creation_date: 2012-06-07T05:05:36Z

[Term]
id: MI:1205
name: luciferase tag
def: "Luciferase is a generic term for the class of oxidative enzymes used in bioluminescence and is distinct from a photoprotein. Luciferase catalyzes a bioluminescent reaction which requires the substrate luciferin as well as Mg2+ and ATP, produces green light with a wavelength of 562 nm." []
subset: PSI-MI_slim
is_a: MI:0240 ! fusion protein
created_by: orchard
creation_date: 2012-06-07T05:20:20Z

[Term]
id: MI:1206
name: renilla-n
def: "The n-terminus of the renilla luciferase protein, fused to a protein of interest for use in the split luciferase complementation assay." [PMID:12705589]
subset: PSI-MI_slim
synonym: "N-terminal fragment of renilla luciferase" RELATED []
is_a: MI:0896 ! renilla luciferase protein tag
is_a: MI:1215 ! bifc tag
created_by: orchard
creation_date: 2012-06-07T05:26:34Z

[Term]
id: MI:1207
name: renilla-c
def: "The c-terminus of the renilla luciferase protein, fused to a protein of interest for use in the split luciferase complementation assay." [PMID:12705589]
synonym: "C-terminal fragment of renilla luciferase" EXACT []
is_a: MI:0896 ! renilla luciferase protein tag
is_a: MI:1215 ! bifc tag
created_by: orchard
creation_date: 2012-06-07T05:31:32Z

[Term]
id: MI:1208
name: firefly luciferase protein tag
def: "Firefly luciferase, is an enzyme from beetles (Photinus pyralis) catalyzing the oxidation of the lucifering pigment (reaction with ATP or oxygen)  that produces light. Firefly luciferase produces a greenish yellow light in the 550-570nm range." [PMID:22070901]
subset: PSI-MI_slim
is_a: MI:1205 ! luciferase tag
created_by: orchard
creation_date: 2012-06-07T05:32:53Z

[Term]
id: MI:1209
name: firefly-c
def: "The c-terminus of the firefly luciferase protein, fused to a protein of interest for use in the split luciferase complementation assay." [PMID:22070901]
subset: PSI-MI_slim
synonym: "C-terminal fragment of firefly luciferase" EXACT []
is_a: MI:1208 ! firefly luciferase protein tag
is_a: MI:1215 ! bifc tag
created_by: orchard
creation_date: 2012-06-07T05:40:04Z

[Term]
id: MI:1210
name: firefly-n
def: "The n-terminus of the firefly luciferase protein, fused to a protein of interest for use in the split luciferase complementation assay." [PMID:22070901]
subset: PSI-MI_slim
synonym: "N-terminal fragment of firefly luciferase" RELATED []
is_a: MI:1208 ! firefly luciferase protein tag
is_a: MI:1215 ! bifc tag
created_by: orchard
creation_date: 2012-06-07T05:41:30Z

[Term]
id: MI:1211
name: liposome binding assay
def: "Lipid binding proteins incubated with liposomes of known lipid content. Mixture is then centrifuged and proteins bound to liposomes separated out." [PMID:14734570]
subset: PSI-MI_slim
synonym: "liposome centrifugation assay" RELATED []
is_a: MI:0027 ! cosedimentation
created_by: orchard
creation_date: 2012-06-07T05:51:15Z

[Term]
id: MI:1212
name: checksum
def: "A fixed-size datum calculated (by using a hash function) for a molecular sequence or structure, typically for purposes of error detection or indexing." [PMID:14755292]
subset: PSI-MI_slim
synonym: "hashsum" RELATED []
is_a: MI:0666 ! participant attribute name
created_by: orchard
creation_date: 2012-06-07T05:54:41Z

[Term]
id: MI:1213
name: n-venus
def: "N-terminal region of the Venus fusion protein, created by the introduction of a point mutation into Aequorea-derived YFP, the substitution of leucine for phenylalanine at position 46 (F46L). This tag is used for split flurescence complementation assays." [PMID:22229727]
subset: PSI-MI_slim
is_a: MI:1135 ! venus fluorescent protein tag
is_a: MI:1215 ! bifc tag
created_by: orchard
creation_date: 2012-06-07T06:33:51Z

[Term]
id: MI:1214
name: c-venus
def: "C-terminal region of the Venus fusion protein, created by the introduction of a point mutation into Aequorea-derived YFP, the substitution of leucine for phenylalanine at position 46 (F46L). This tag is used for split flurescence complementation assays." [PMID:22229727]
subset: PSI-MI_slim
is_a: MI:1135 ! venus fluorescent protein tag
is_a: MI:1215 ! bifc tag
created_by: orchard
creation_date: 2012-06-07T06:39:30Z

[Term]
id: MI:1215
name: bifc tag
def: "Fusion protein which consists of either the N- or C-terminal sequence of a fluorescent or luciferase protein. Binding of the proteins of interest enable the reassembly of the molecule, indicating that an interaction has occured." [PMID:17406412]
subset: PSI-MI_slim
is_a: MI:0240 ! fusion protein
created_by: orchard
creation_date: 2012-06-07T07:13:53Z

[Term]
id: MI:1216
name: cGFP
def: "c-terminal fragment of green fluorescent protein used as a tag in bimolecular fluorescence complementation (BiFC)." [PMID:17406412]
subset: PSI-MI_slim
is_a: MI:0367 ! green fluorescent protein tag
is_a: MI:1215 ! bifc tag
created_by: orchard
creation_date: 2012-06-07T07:19:55Z

[Term]
id: MI:1217
name: nGFP
def: "n-terminal fragment of green fluorescent protein used as a tag in bimolecular fluorescence complementation (BiFC)." [PMID:17406412]
subset: PSI-MI_slim
is_a: MI:0367 ! green fluorescent protein tag
is_a: MI:1215 ! bifc tag
created_by: orchard
creation_date: 2012-06-07T07:20:57Z

[Term]
id: MI:1218
name: chromosome conformation capture assay
def: "Chromosome conformation capture,[1] or 3C, is a high-throughput molecular biology technique used to analyze the organization of chromosomes in a cell's natural state. The basic 3C technique consists of cross-linking by addition of formaldehyde followed by addition of a restriction enzyme in excess to the cross-linked DNA, separating the non-cross-linked DNA from the cross-linked chromatin. A intramolecular ligation step using very low concentrations of DNA favors the ligation of relevant DNA fragments with the corresponding junctions instead of the ligation of random fragments. There are two major types of ligation junctions that are over-represented. One is the junction that forms between neighboring DNA fragments due to incomplete digestion, which represents about 20-30% of all junctions. This number is decreased by reducing the cross-linking stringency in the first step. The other type of junctions over-represented in this technique is the junction that forms when one end of the fragment ligates with the other end of the same fragment, and contributes up to 30% of all junctions formed. High temperature then results in the reversal of the previously formed cross-links. The resulting linear DNA fragment has specific restriction ends as well as a central restriction site corresponding to the site of ligation. The pool of these fragments is collectively referred to as the 3C library." [PMID:11847345]
subset: PSI-MI_slim
synonym: "chip-3c" EXACT PSI-MI-short []
is_a: MI:0030 ! cross-linking study
created_by: orchard
creation_date: 2012-06-07T07:25:28Z

[Term]
id: MI:1219
name: enzyme-mediated activation of radical sources
def: "Enzyme-mediated activation of radical sources is used  to identify partners of a given molecule on the cell surface in living cells Activation of the cross-linking reagent arylazide-biotin tag is accomplished  by an enzyme, horseradish peroxidase is featured by radical formation of the labelling reagent by horseradish peroxidase (HRP)." [PMID:21214558]
subset: PSI-MI_slim
synonym: "emars" EXACT PSI-MI-short []
is_a: MI:0013 ! biophysical
created_by: orchard
creation_date: 2012-06-07T07:34:30Z

[Term]
id: MI:1220
name: tag visualisation by luciferase assay
def: "The protein is expressed as a hybrid protein fused to a tag containing a luciferase activity. Subsequence observation or measurement of luciferase activity is used to identify the presence of the molecule in an interaction." [PMID:20609414]
subset: PSI-MI_slim
synonym: "tag luciferase" EXACT PSI-MI-short []
is_a: MI:0980 ! tag visualisation by enzyme assay
created_by: orchard
creation_date: 2012-06-11T11:52:57Z

[Term]
id: MI:1221
name: author-based confidence
def: "A score generated by an author, usually only relevant for that particular dataset." [PMID:14755292]
subset: PSI-MI_slim
synonym: "author score" EXACT PSI-MI-short []
is_a: MI:1064 ! interaction confidence
created_by: orchard
creation_date: 2012-06-11T11:54:23Z

[Term]
id: MI:1222
name: mbinfo
def: "MBInfo is a wiki based, multimedia, educational resource providing up to date reviews on topics relating to mechanobiology (http://www.mechanobio.info/)." [PMID:14755292]
subset: PSI-MI_slim
synonym: "MBInfo" EXACT PSI-MI-alternate []
is_a: MI:0461 ! interaction database
is_a: MI:0973 ! imex source
created_by: orchard
creation_date: 2012-06-11T12:20:53Z

[Term]
id: MI:1223
name: ptm decreasing an interaction
def: "Post translational modification on a protein observed to decrease the strength or rate of an interaction." [PMID:14744292]
subset: PSI-MI_slim
synonym: "decreasing-ptm" EXACT PSI-MI-short []
is_a: MI:0925 ! observed-ptm
created_by: orchard
creation_date: 2012-06-11T12:56:47Z

[Term]
id: MI:1224
name: ptm increasing an interaction
def: "Post translational modification on a protein observed to increase the strength or rate of an interaction." [PMID:14744292]
subset: PSI-MI_slim
synonym: "increasing-ptm" EXACT PSI-MI-short []
is_a: MI:0925 ! observed-ptm
created_by: orchard
creation_date: 2012-06-11T12:58:43Z

[Term]
id: MI:1225
name: ptm disrupting an interaction
def: "Post translational modification on a protein observed to disrupt the strength or rate of an interaction." [PMID:14744292]
subset: PSI-MI_slim
synonym: "disrupting-ptm" EXACT PSI-MI-short []
is_a: MI:0925 ! observed-ptm
created_by: orchard
creation_date: 2012-06-11T12:59:28Z

[Term]
id: MI:1226
name: ampylation assay
def: "Formation of phosphodiester or phosphoramide ester of AMP on Tyr (RESID:AA0203), Lys (RESID:AA0227), Thr (RESID:AA0267), His (RESID:AA0371) and other amino acids" [PMID:14755292]
subset: PSI-MI_slim
synonym: "ampylation" RELATED []
is_obsolete: true
created_by: orchard
creation_date: 2012-06-11T01:06:07Z

[Term]
id: MI:1227
name: lap tag
def: "Tag encoding green fluorescent protein (GFP) , a TEV cleavage site, and a second purification tag such as S peptide or 6xHis. The tag can therefore be used for both localisation and affinity purification." [PMID:15644491]
subset: PSI-MI_slim
synonym: "lap tag" EXACT PSI-MI-short []
synonym: "location and purification tag" RELATED []
is_a: MI:0677 ! tandem tag
created_by: orchard
creation_date: 2012-06-11T01:16:05Z

[Term]
id: MI:1228
name: pyo tag
def: "A polyoma virus-derived (Pyo) epitope tag (amino acids MEYMPME)." [PMID:9371754]
subset: PSI-MI_slim
is_a: MI:0507 ! tag
created_by: orchard
creation_date: 2012-08-10T07:28:55Z

[Term]
id: MI:1229
name: uridylation assay
def: "Measures  the formation of a phosphodiester or phosphoramide ester of UMP and an amino acid (MOD:01166)." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2012-08-10T07:46:07Z

[Term]
id: MI:1230
name: uridylation reaction
def: "The formation of a phosphodiester or phosphoramide ester of UMP and amino acid (MOD:01166)." [PMID:14755292]
subset: PSI-MI_slim
synonym: "umpylation" RELATED []
synonym: "uridylation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction
created_by: orchard
creation_date: 2012-08-10T07:50:08Z

[Term]
id: MI:1231
name: aminomethylcoumarin label
def: "AMC (aminomethylcoumarin ) is a blue fluorescent tag with reactive derivatives that are used as contrasting probes for double- and triple-labeling in immunofluorescence microscopy, arrays and in situ hybridization and can be attached to proteins or small molecules for reaction monitoring." [PMID:14755292]
subset: PSI-MI_slim
synonym: "AMC label" EXACT PSI-MI-short []
is_a: MI:1328 ! coumarin label
created_by: orchard
creation_date: 2012-08-10T07:59:18Z

[Term]
id: MI:1232
name: aggregation assay
def: "An interaction between two proteins is inferred from monitoring the effect of the presence of one of them  on the aggregation state of the second." [PMID:22179788]
subset: PSI-MI_slim
synonym: "aggregation" EXACT PSI-MI-short []
is_a: MI:0401 ! biochemical
created_by: orchard
creation_date: 2012-08-10T08:07:15Z

[Term]
id: MI:1233
name: resulting-cleavage
def: "The cleavage which results due to the action of a proteolytic enzyme on its substrate." [PMID:14755292]
comment: Any feature range given should span the cleavage region e.g. 102-103 if the peptide bond between residues 102 and 103 is cut.
subset: PSI-MI_slim
is_a: MI:0639 ! resulting-ptm
created_by: orchard
creation_date: 2012-08-10T08:14:45Z

[Term]
id: MI:1234
name: silac
def: "SILAC (Stable Isotope Labeling by Amino acids in Cell culture) can be used to detect  features (typically PTMs) required for a given interaction." [PMID:17139335, PMID:18369856]
subset: PSI-MI_slim
is_a: MI:0659 ! experimental feature detection
created_by: orchard
creation_date: 2012-08-10T08:45:50Z

[Term]
id: MI:1235
name: thermal shift binding
def: "Ligand binding to a target protein can stabilize a protein's native state, as shown in the increase of the bound protein's melting temperature. The midpoint of the melting curve of a protein will increase in the presence of ligands that bind more tightly to the native state than the unfolded state." [PMID:22052482]
subset: PSI-MI_slim
synonym: "thermal shift" EXACT PSI-MI-short []
synonym: "thermshift binding assay" RELATED []
is_a: MI:0013 ! biophysical
created_by: orchard
creation_date: 2012-08-10T08:52:14Z

[Term]
id: MI:1236
name: proline isomerase assay
def: "Measurment of the  conversion between cis- and trans- peptide bonds formed by the amine group of a proline. Peptide bonds to proline, and to other N-substituted amino acids (such as sarcosine), are able to populate both the cis and trans isomers  the cis and trans isomers of the X-Pro peptide bond (where X represents any amino acid) both experience steric clashes with the neighboring substitution and are nearly equal energetically. Hence, the fraction of X-Pro peptide bonds in the cis isomer under unstrained conditions ranges from 10-40%; the fraction depends slightly on the preceding amino acid, with aromatic residues favoring the cis isomer slightly." [PMID:9344417]
subset: PSI-MI_slim
is_a: MI:1249 ! isomerase assay
created_by: orchard
creation_date: 2012-08-10T08:56:38Z

[Term]
id: MI:1237
name: proline isomerization  reaction
def: "The conversion between cis- and trans- peptide bonds formed by the amine group of a proline." [PMID:9344417]
subset: PSI-MI_slim
is_a: MI:1250 ! isomerase reaction
created_by: orchard
creation_date: 2012-08-10T09:02:28Z

[Term]
id: MI:1238
name: mass spectrometry studies of subunit exchange
def: "Heavy/light isotope-labelled subunits are prepared and allowed to form their respective mature oligomeric structure. Oligomers are then mixed and subunit exchange is monitored, usually by electrospray ionisation-ion mobility spectrometry-mass spectrometry." [PMID:20351246]
subset: PSI-MI_slim
synonym: "ms subunit exchange" EXACT PSI-MI-short []
is_a: MI:0069 ! mass spectrometry studies of complexes
created_by: orchard
creation_date: 2012-08-10T09:11:36Z

[Term]
id: MI:1239
name: amino-acid variant
def: "A naturally-occuring amino-acid variation to the reference sequence, including polymorphisms, variations between strains, isolates or cultivars, disease-associated mutations and RNA editing events." [PMID:18175334]
subset: PSI-MI_slim
synonym: "SAP" RELATED []
synonym: "single amino-acid polymorphism" RELATED []
is_a: MI:1241 ! variant
created_by: orchard
creation_date: 2012-08-10T09:20:55Z

[Term]
id: MI:1240
name: disease causing amino-acid variant
def: "A naturally-occuring amino-acid variation to the reference sequence which results in the organism developing, or becoming susceptible to a particular disease condition." [PMID:18175334]
synonym: "disease aa variant" EXACT PSI-MI-short []
synonym: "disease sap" RELATED []
synonym: "disease single amino acid polymorphism" RELATED []
is_a: MI:1239 ! amino-acid variant
created_by: orchard
creation_date: 2012-08-10T09:28:06Z

[Term]
id: MI:1241
name: variant
def: "A natural change in a sequence or structure in comparison to a reference entity." []
is_a: MI:0252 ! biological feature
created_by: orchard
creation_date: 2012-08-10T09:32:29Z

[Term]
id: MI:1242
name: fc-igg1
def: "A fusion protein tag consisting of a portion of the constant region of IgG1." [PMID:11757069]
subset: PSI-MI_slim
is_a: MI:0975 ! fc-igg tag
created_by: orchard
creation_date: 2012-08-10T10:10:25Z

[Term]
id: MI:1243
name: fc-igg2
def: "A fusion protein tag consisting of a portion of the constant region of IgG2." [PMID:11757069]
subset: PSI-MI_slim
is_a: MI:0975 ! fc-igg tag
created_by: orchard
creation_date: 2012-08-10T10:14:13Z

[Term]
id: MI:1244
name: mkate2
def: "Monomeric far-red fluorescent protein generated from the wild-type RFP from sea anemone Entacmaea quadricolor. It possesses bright fluorescence with excitation/emission maxima at 588 and 635 nm, respectively." [PMID:17721542]
subset: PSI-MI_slim
is_a: MI:0732 ! red fluorescent protein tag
created_by: orchard
creation_date: 2012-08-10T11:22:13Z

[Term]
id: MI:1245
name: mkate
def: "Monomeric far-red fluorescent protein generated from the wild-type RFP from sea anemone Entacmaea quadricolor. It possesses bright fluorescence with excitation/emission maxima at 588 and 635 nm, respectively." [PMID:17721542]
subset: PSI-MI_slim
synonym: "TagFP635" RELATED []
is_a: MI:0732 ! red fluorescent protein tag
created_by: orchard
creation_date: 2012-08-10T11:48:12Z

[Term]
id: MI:1246
name: ion mobility mass spectrometry of complexes
def: "IM-MS analysis is performed by first ionizing the protein complex of interest followed by ion mobility separation according to their cross-section-to-charge (Q/z) ratio. After separation, ions are sampled by a mass spectrometer and analyzed according to their mass-to-charge (m/z) ratio. Combined knowledge of both Q/z and m/z can be used to infer the size and shape of the complex." [PMID:18600219]
subset: PSI-MI_slim
synonym: "iM-MS" RELATED []
synonym: "ion mobility mass spec" EXACT PSI-MI-short []
is_a: MI:0069 ! mass spectrometry studies of complexes
created_by: orchard
creation_date: 2012-08-10T11:56:05Z

[Term]
id: MI:1247
name: microscale thermophoresis
def: "Measurement of the directed movement of particles in a microscopic temperature gradient. Any change of the hydration shell of biomolecules due to changes in their structure/conformation results in a relative change of movement along the temperature gradient and is used to determine binding affinities, binding kinetics and activity kinetics. Events such as the phosphorylation of a protein or the binding of small molecules to a target can be monitored." [PMID:17164337]
subset: PSI-MI_slim
synonym: "mst" EXACT PSI-MI-short []
is_a: MI:0013 ! biophysical
created_by: orchard
creation_date: 2012-08-10T12:20:37Z

[Term]
id: MI:1248
name: bodipy label
def: "Composed of dipyrromethene complexed with a disubstituted boron atom, typically a BF2 unit. Notable for their uniquely small Stokes shift, high, environment-independent fluorescence quantum yields." [PMID:19067126]
subset: PSI-MI_slim
synonym: "4,4-difluoro-4-bora-3a,4a-diaza-s-indacene" RELATED []
synonym: "boron-dipyrromethene label" RELATED []
is_a: MI:0857 ! fluorescent dye label
created_by: orchard
creation_date: 2012-08-10T12:34:54Z

[Term]
id: MI:1249
name: isomerase assay
def: "Measurement of the catalysis of the structural rearrangement of isomers." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2012-08-10T12:45:27Z

[Term]
id: MI:1250
name: isomerase reaction
def: "The catalysis of the structural rearrangement of isomers." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0414 ! enzymatic reaction
created_by: orchard
creation_date: 2012-08-10T12:51:00Z

[Term]
id: MI:1251
name: methylmalonyl-CoA isomerase reaction
def: "The catalysis of the conversion of methylmalonyl-CoA to succinyl-CoA by transfer of the carbonyl group. It requires a cobamide coenzyme. EC 5.4.99.2." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1250 ! isomerase reaction
created_by: orchard
creation_date: 2012-08-10T01:23:35Z

[Term]
id: MI:1252
name: methylmalonyl-CoA isomerase asf say
def: "The catalysis othe conversion of methylmalonyl-CoA to succinyl-CoA by transfer of the carbonyl group. It requires a cobamide coenzyme. EC 5.4.99.2" [PMID:147292]
subset: PSI-MI_slim
is_a: MI:1249 ! isomerase assay
created_by: orchard
creation_date: 2012-08-10T01:29:23Z

[Term]
id: MI:1253
name: atto 532
def: "Fluorescent tag - maleimide couples to thiols." [PMID:14760721]
subset: PSI-MI_slim
synonym: "atto 532 maleimide" EXACT []
synonym: "atto532" RELATED []
is_a: MI:1092 ! atto label
created_by: orchard
creation_date: 2012-08-10T01:49:01Z

[Term]
id: MI:1254
name: atto 647
def: "Fluorescent tag - maleimide couples to thiols." [PMID:14760721]
subset: PSI-MI_slim
synonym: "atto 647 maleimide" EXACT []
synonym: "atto647" RELATED []
is_a: MI:1092 ! atto label
created_by: orchard
creation_date: 2012-08-10T01:51:00Z

[Term]
id: MI:1255
name: stilbene label
def: "1,2-Diphenylethene" [PMID:16287229]
subset: PSI-MI_slim
is_a: MI:0857 ! fluorescent dye label
created_by: orchard
creation_date: 2012-08-10T01:56:28Z

[Term]
id: MI:1256
name: luminscent dye label
def: "Luminescent dyes such as cyanines,commonly used for DNA labelling." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0373 ! dye label
created_by: orchard
creation_date: 2012-08-10T02:18:02Z

[Term]
id: MI:1257
name: rhodamine label
def: "Rhodamines are supplements to fluoresceins, as they offer longer wavelength emission maxima and provide opportunities for multicolor labeling or staining." [PMID:12622145]
subset: PSI-MI_slim
is_a: MI:0857 ! fluorescent dye label
created_by: orchard
creation_date: 2012-08-10T02:39:00Z

[Term]
id: MI:1258
name: tetramethyl rhodamine label
def: "Tetramethyl rhodamine - a derivative of rhodamine." [PMID:12622145]
subset: PSI-MI_slim
is_a: MI:1257 ! rhodamine label
created_by: orchard
creation_date: 2012-08-10T02:44:52Z

[Term]
id: MI:1259
name: acrylodan label
def: "The thiol reactive acrylodan (6-acryloyl-2-dimethylaminonaphthalene) generally reacts with thiols more slowly than iodoacetamides or maleimides, but does form very strong thioether bonds that are expected to remain stable under conditions required for complete amino acid analysis. The fluorescence emission peak and intensity of these adducts are particularly sensitive to conformational changes or ligand binding." [PMID:12622145]
subset: PSI-MI_slim
synonym: "6-acryloyl-2-dimethylaminonaphthalene" RELATED []
is_a: MI:0857 ! fluorescent dye label
created_by: orchard
creation_date: 2012-08-10T02:55:26Z

[Term]
id: MI:1260
name: pyrene label
def: "Pyrene is a polycyclic aromatic hydrocarbon (PAH) consisting of four fused benzene rings, resulting in a flat aromatic system. The chemical formula is C16H10. Its derivatives are  valuable molecular probes via fluorescence spectroscopy, having a high quantum yield and lifetime." [PMID:12622145]
is_a: MI:0857 ! fluorescent dye label
created_by: orchard
creation_date: 2012-08-10T03:09:54Z

[Term]
id: MI:1261
name: oregon green label
def: "Oregon Green 488 and Oregon Green 514 dyes are fluorinated analogs of fluoresceins" [PMID:12622145]
subset: PSI-MI_slim
is_a: MI:0939 ! fluorescein label
created_by: orchard
creation_date: 2012-08-10T03:17:05Z

[Term]
id: MI:1262
name: iid
def: "Interologous Interaction Database is an on-line database of known and predicted mammalian and eukaryotic protein-protein interactions." [PMID:19850753]
subset: PSI-MI_slim
synonym: "I2D" EXACT PSI-MI-alternate []
synonym: "IID" EXACT PSI-MI-alternate []
synonym: "Interologous Interaction Database" EXACT PSI-MI-alternate []
xref: url:http\://iid.ophid.utoronto.ca/iid/
is_a: MI:0461 ! interaction database
is_a: MI:0973 ! imex source
created_by: orchard
creation_date: 2012-10-22T02:57:59Z

[Term]
id: MI:1263
name: molecular connections
def: "Molecular Connections Private Limited is an in silico discovery Services Company  with expertise in drug-discovery, informatics and information technology. They perform pro bono work for the IMEx Consortium. http://www.molecularconnections.com" [PMID:22453911]
subset: PSI-MI_slim
synonym: "MolCon" RELATED []
synonym: "Molecular Connections" EXACT PSI-MI-alternate []
is_a: MI:0461 ! interaction database
is_a: MI:0973 ! imex source
created_by: orchard
creation_date: 2012-10-22T03:03:01Z

[Term]
id: MI:1264
name: ntnu
def: "Norwegian University of Science and Technology. www.ntnu.no/home." [PMID:14755292]
subset: PSI-MI_slim
synonym: "NTNU" EXACT PSI-MI-alternate []
is_a: MI:0489 ! source database
created_by: orchard
creation_date: 2012-10-22T03:15:27Z

[Term]
id: MI:1265
name: ubiquitin reconstruction tag
def: "In the split-ubiquitin system, two integral membrane proteins to be studied are fused to two different ubiquitin moieties: a C-terminal ubiquitin moiety (residues 35-76) and an N-terminal ubiquitin moiety  (residues 1-34). These fused proteins are called the bait and prey, respectively. In addition to being fused to an integral membrane protein, the Cub moiety is also fused to a transcription factor  that can be cleaved off by ubiquitin specific proteases." [PMID:9560251]
subset: PSI-MI_slim
is_a: MI:0240 ! fusion protein
created_by: orchard
creation_date: 2012-10-24T11:08:40Z

[Term]
id: MI:1266
name: cub
def: "A C-terminal ubiquitin moiety (cub, residues 35-76) plus a  transcription factor that can be cleaved off by ubiquitin specific proteases. Regarded as attached to the bait molecules in ubiquitin reconstruction assays." [PMID:9560251]
subset: PSI-MI_slim
synonym: "c-terminal ubiquitin tag" RELATED []
is_a: MI:1265 ! ubiquitin reconstruction tag
created_by: orchard
creation_date: 2012-10-24T11:10:19Z

[Term]
id: MI:1267
name: nub
def: "N-terminal ubiquitin moiety (nub, residues 1-34)." [PMID:9560251]
subset: PSI-MI_slim
synonym: "N-terminal ubiquitin tag" RELATED []
is_a: MI:1265 ! ubiquitin reconstruction tag
created_by: orchard
creation_date: 2012-10-24T11:12:47Z

[Term]
id: MI:1268
name: nubg
def: "N-terminal ubiquitin moiety (residues 1-34) containing a Ile13Gly mutation." [PMID:9560251]
subset: PSI-MI_slim
synonym: "Ile13Gly N-terminal ubiquitin tag" RELATED []
is_a: MI:1267 ! nub
created_by: orchard
creation_date: 2012-10-24T11:31:11Z

[Term]
id: MI:1269
name: duplicated protein
def: "An identical protein sequence is coded for by the multiple genes within the same organism. These proteins may previously be merged into a single entry by UniProt and subsequently demerged." [PMID:21051339]
subset: PSI-MI_slim
is_a: MI:1341 ! set member
created_by: orchard
creation_date: 2012-11-28T03:23:28Z

[Term]
id: MI:1270
name: xpress tag
def: "Contains a polyhistidine sequence, the Xpress epitope (part of bacteriophage T7 gene 10 protein) and an enterokinase cleavage site. Anti-Xpress antibodies recognise the Xpress epitope sequence found in this leader peptide. Asp-Leu-Tyr-Asp-Asp-Asp-Asp-Lys." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0507 ! tag
created_by: orchard
creation_date: 2013-05-30T08:29:27Z

[Term]
id: MI:1271
name: enhancement
def: "An effect in which the phenotype of one genetic perturbation is enhanced by a second perturbation to a severity/penetrance beyond (further from wild type) that expected by the superimposition or addition of effects of the individual perturbations. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\nab < E < wt\nOR\nwt < E < ab\nwhere 'ab' is the observed phenotype value of the double perturbation, 'E' is the expected phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:15833125]
subset: PSI-MI_slim
synonym: "Aggravating interaction" RELATED []
is_a: MI:0933 ! negative genetic interaction
created_by: orchard
creation_date: 2013-06-05T19:12:17Z

[Term]
id: MI:1272
name: positive epistasis
def: "An effect in which individual perturbations of two different genes result in different mutant phenotypes (which are traits measured on the same quantitative scale but each significantly deviating, in the same direction, from wild type), and the resulting phenotype of their combination is equal to that of only one of the perturbations. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\n((a* < b < wt) OR (wt < b < a*)) AND (ab = a OR ab = b)\nwhere 'a' and 'b' are the observed phenotype values of the individual perturbations ('a*' being the most severe of the two), 'ab' is the observed phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:15833125]
subset: PSI-MI_slim
is_a: MI:0797 ! epistasis
is_a: MI:0935 ! positive genetic interaction
created_by: orchard
creation_date: 2013-06-05T20:05:15Z

[Term]
id: MI:1273
name: maximal epistasis
def: "An effect in which individual perturbations of two different genes result in the same mutant phenotype to varying degrees of severity/penetrance and the resulting phenotype of their combination is equal in severity/penetrance to the most severe/penetrant of the individual perturbations. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\nab = a* < b < wt\nOR\nwt < b < a* = ab\nwhere 'a' and 'b' are the observed phenotype values of the individual perturbations ('a*' being the most severe of the two), 'ab' is the observed phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:15833125]
subset: PSI-MI_slim
is_a: MI:1272 ! positive epistasis
is_a: MI:1284 ! quantitative epistasis
created_by: orchard
creation_date: 2013-06-05T20:11:27Z

[Term]
id: MI:1274
name: minimal epistasis
def: "An effect in which individual perturbations of two different genes result in the same mutant phenotype to varying degrees of severity/penetrance and the resulting phenotype of their combination is equal in severity/penetrance to the least severe/penetrant of the individual perturbations. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\na* < ab = b < wt\nOR\nwt < b = ab < a*\nwhere 'a' and 'b' are the observed phenotype values of the individual perturbations ('a*' being the most severe of the two), 'ab' is the observed phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:15833125]
subset: PSI-MI_slim
is_a: MI:1272 ! positive epistasis
is_a: MI:1282 ! mutual suppression (partial)
is_a: MI:1284 ! quantitative epistasis
created_by: orchard
creation_date: 2013-06-05T20:13:14Z

[Term]
id: MI:1275
name: neutral epistasis
def: "An effect in which individual perturbations of two different genes result in different mutant phenotypes (which are EITHER traits measured on the same quantitative scale but each significantly deviating, in opposite directions, from wild type, OR completely (qualitatively) different phenotypes), and the resulting phenotype of their combination is equal to that of only one of the perturbations. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\n(a < wt < b) AND (ab = a OR ab = b)\nOR\n(a != wt AND b != wt AND a != b) AND (ab = a OR ab = b)\nwhere 'a' and 'b' are the observed phenotype values of the individual perturbations, 'ab' is the observed phenotype value of the double perturbation, 'wt' is the wild type phenotype value, and 'a != b' indicates qualitatively different phenotypes." [PMID:15833125]
subset: PSI-MI_slim
is_a: MI:0797 ! epistasis
is_a: MI:0934 ! neutral genetic interaction
created_by: orchard
creation_date: 2013-06-05T20:22:53Z

[Term]
id: MI:1276
name: opposing epistasis
def: "An effect in which individual perturbations of two different genes result in opposite mutant phenotypes (traits measured on the same scale but each on opposing sides relative to the wild type phenotype), and the resulting phenotype of their combination is equal to that of only one of the perturbations. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\n(a < wt < b) AND (ab = a OR ab = b) \nwhere 'a' and 'b' are the observed phenotype values of the individual perturbations, 'ab' is the observed phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:15833125]
subset: PSI-MI_slim
xref: psi-mi:MI\:1285 "Obsolete, previously existing identical term identifier"
is_a: MI:1275 ! neutral epistasis
is_a: MI:1284 ! quantitative epistasis
created_by: orchard
creation_date: 2013-06-05T20:25:26Z

[Term]
id: MI:1277
name: qualitative epistasis
def: "An effect in which individual perturbations of two different genes result in different mutant phenotypes (which are traits that cannot be measured on the same scale and, hence, qualitatively different), and the resulting phenotype of their combination is equal to that of only one of the perturbations. This may be expressed as an inequality as:\n(a != wt AND b != wt AND a != b) AND (ab = a OR ab = b)    \nwhere 'a' and 'b' are the observed phenotypes of the individual perturbations, 'ab' is the observed phenotype of the double perturbation, 'wt' is the wild type phenotype and 'a != b' indicates qualitatively different phenotypes." [PMID:15833125]
subset: PSI-MI_slim
is_a: MI:1275 ! neutral epistasis
created_by: orchard
creation_date: 2013-06-05T20:26:38Z

[Term]
id: MI:1278
name: mutual enhancement
def: "An effect in which individual perturbations of different genes result in the same mutant phenotype (but, perhaps, to varying degrees of severity/penetrance) and the resulting phenotype of their combination is more severe/penetrant (further from wild type) than expected by the superimposition or addition of effects of the individual perturbations. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\nab < a* <= b < wt [E = a*]\nOR\nwt < b <= a* < ab [E = a*]\nwhere 'a' and 'b' are the observed phenotype values of the individual perturbations ('a*' being the most severe of the two), 'ab' is the observed phenotype value of the double perturbation, 'E' is the expected phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:15833125]
subset: PSI-MI_slim
is_a: MI:1271 ! enhancement
created_by: orchard
creation_date: 2013-06-05T20:31:30Z

[Term]
id: MI:1279
name: unilateral enhancement
def: "An effect in which the phenotype of one genetic perturbation is enhanced by a second perturbation (which, on its own, has no effect on the phenotype in question) to a severity/penetrance beyond (further from wild type) that of the original phenotype. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\nab < a < b = wt [E = a]\nOR\nwt = b < a < ab [E = a]\nwhere 'a' and 'b' are the observed phenotype values of the individual perturbations, 'ab' is the observed phenotype value of the double perturbation, 'E' is the expected phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:15833125]
subset: PSI-MI_slim
is_a: MI:1271 ! enhancement
created_by: orchard
creation_date: 2013-06-05T20:33:13Z

[Term]
id: MI:1280
name: mutual suppression
def: "An effect in which individual perturbations of different genes result in the same mutant phenotype (but, perhaps, to varying degrees of severity/penetrance) and the resulting phenotype of their combination is less severe/penetrant than expected from the original phenotypes. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\n(a* <= b < wt) AND (a* < ab <= wt) [E = a*]\nOR\n(wt < b <= a*) AND (wt <= ab < a*) [E = a*]\nwhere 'a' and 'b' are the observed phenotype values of the individual perturbations ('a*' being the most severe of the two), 'ab' is the observed phenotype value of the double perturbation, 'E' is the expected phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:15833125]
subset: PSI-MI_slim
is_a: MI:0796 ! suppression
created_by: orchard
creation_date: 2013-06-05T20:35:53Z

[Term]
id: MI:1281
name: mutual suppression (complete)
def: "An effect in which individual perturbations of different genes result in the same mutant phenotype (but, perhaps, to varying degrees of severity/penetrance) and the resulting combination is wild type. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\na* <= b < ab = wt\nOR\nwt = ab < b <= a*\nOR\na < wt = ab < b\nwhere 'a' and 'b' are the observed phenotype values of the individual perturbations ('a*' being the most severe of the two), 'ab' is the observed phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:15833125]
subset: PSI-MI_slim
is_a: MI:1280 ! mutual suppression
created_by: orchard
creation_date: 2013-06-05T20:37:41Z

[Term]
id: MI:1282
name: mutual suppression (partial)
def: "An effect in which individual perturbations of different genes result in the same mutant phenotype (but, perhaps, to varying degrees of severity/penetrance) and the resulting phenotype of their combination is less severe/penetrant than expected, but not wild type. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\n(a* <= b < wt) AND (a* < ab < wt) [E = a*]\nOR\n(wt < b <= a*) AND (wt < ab < a*) [E = a*]\nwhere 'a' and 'b' are the observed phenotype values of the individual perturbations ('a*' being the most severe of the two), 'ab' is the observed phenotype value of the double perturbation, 'E' is the expected phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:15833125]
subset: PSI-MI_slim
is_a: MI:1280 ! mutual suppression
created_by: orchard
creation_date: 2013-06-05T20:39:12Z

[Term]
id: MI:1283
name: suppression-enhancement
def: "An effect in which individual perturbations of different genes result in the same mutant phenotype to varying degrees of severity/penetrance and the resulting phenotype of their combination has a phenotype more severe/penetrant than the least severe/penetrant and less severe/penetrant than the most severe/penetrant of the individual perturbations. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\na* < ab < b < wt [E = a*]\nOR\nwt < b < ab < a* [E = a*]\nwhere 'a' and 'b' are the observed phenotype values of the individual perturbations ('a*' being the most severe of the two), 'ab' is the observed phenotype value of the double perturbation, 'E' is the expected phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:15833125]
subset: PSI-MI_slim
is_a: MI:1282 ! mutual suppression (partial)
created_by: orchard
creation_date: 2013-06-05T20:43:52Z

[Term]
id: MI:1284
name: quantitative epistasis
def: "An effect in which individual perturbations of two different genes result in different mutant phenotypes (which are traits measured on the same quantitative scale but each significantly deviating, in any direction, from wild type), and the resulting phenotype of their combination is equal to that of only one of the perturbations. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\n(a != wt AND b != wt AND a != b) AND (ab = a OR ab = b)   \nwhere 'a' and 'b' are the observed phenotype values of the individual perturbations, 'ab' is the observed phenotype value of the double perturbation, 'wt' is the wild type phenotype value and 'a != b' indicates quantitatively different phenotypes." [PMID:15833125]
subset: PSI-MI_slim
is_a: MI:0797 ! epistasis
created_by: orchard
creation_date: 2013-06-05T20:47:35Z

[Term]
id: MI:1285
name: opposing epistasis
def: "An effect in which individual perturbations of two different genes result in opposite mutant phenotypes (traits measured on the same scale but each on opposing sides relative to the wild type phenotype), and the resulting phenotype of their combination is equal to that of only one of the perturbations. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\n(a < wt < b) AND (ab = a OR ab = b) \nwhere 'a' and 'b' are the observed phenotype values of the individual perturbations, 'ab' is the observed phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:15833125]
subset: PSI-MI_slim
is_obsolete: true
created_by: orchard
creation_date: 2013-06-05T20:51:51Z

[Term]
id: MI:1286
name: over-suppression
def: "An effect in which the observed phenotype of a double perturbation is opposite (relative to the wild type phenotype) to that which is expected upon the double perturbation. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\nab < wt < E\nOR\nE < wt < ab\nwhere 'ab' is the observed phenotype value of the double perturbation, 'E' is the expected phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:15833125]
subset: PSI-MI_slim
is_a: MI:0934 ! neutral genetic interaction
created_by: orchard
creation_date: 2013-06-05T21:04:18Z

[Term]
id: MI:1287
name: mutual over-suppression
def: "An effect in which individual perturbations of different genes result in the same mutant phenotype (but, perhaps, to varying degrees of severity/penetrance) and the resulting phenotype of their combination is opposite (relative to wild type) to that expected from the original phenotypes. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\na* <= b < wt < ab [E = a*]\nOR\nab < wt < b <= a* [E = a*]\nwhere 'a' and 'b' are the observed phenotype values of the individual perturbations ('a*' being the most severe of the two), 'ab' is the observed phenotype value of the double perturbation, 'E' is the expected phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:15833125]
subset: PSI-MI_slim
is_a: MI:1286 ! over-suppression
created_by: orchard
creation_date: 2013-06-05T21:06:09Z

[Term]
id: MI:1288
name: over-suppression-enhancement
def: "An effect in which two individual perturbations result in opposite mutant phenotypes (relative to wild type) and their combination results in a phenotype that is more severe than the phenotype observed with the same directionality. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\na < wt < b < ab\nOR\nab < a < wt < b\nwhere 'a' and 'b' are the observed phenotype values of the individual perturbations, 'ab' is the observed phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:15833125]
subset: PSI-MI_slim
is_a: MI:0934 ! neutral genetic interaction
created_by: orchard
creation_date: 2013-06-05T21:11:03Z

[Term]
id: MI:1289
name: phenotype bias
def: "An effect when two individual perturbations result in opposite mutant phenotypes (relative to wild type) and their combination results in a phenotype that is intermediate to the individual mutant phenotypes, but greater or less than wild type. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\n(a < wt < b) AND (a < ab < b) AND (ab != wt)\nwhere 'a' and 'b' are the observed phenotype values of the individual perturbations, 'ab' is the observed phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:15833125]
subset: PSI-MI_slim
is_a: MI:0934 ! neutral genetic interaction
created_by: orchard
creation_date: 2013-06-05T21:15:34Z

[Term]
id: MI:1290
name: suppression (complete)
def: "An effect in which the perturbation of one gene results in complete suppression (to wild type) of the mutant phenotype caused by perturbation of another gene. The phenotype of the suppressing perturbation may or may not be known. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\nwt = ab != a = E\nwhere 'a' is the observed phenotype values of an individual perturbation, 'ab' is the observed phenotype value of the double perturbation, 'E' is the expected phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:15833125]
subset: PSI-MI_slim
is_a: MI:0796 ! suppression
created_by: orchard
creation_date: 2013-06-05T21:34:57Z

[Term]
id: MI:1291
name: suppression (partial)
def: "An effect in which the perturbation of one gene results in the amelioration or lessening of the severity/penetrance of a mutant phenotype caused by perturbation of another gene, in effect making the organism more, but not completely, \"wild type\" in character with regards to the phenotype in question. The phenotype of the suppressing perturbation may or may not be known. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\na* < ab < wt [E = a*]\nOR\nwt < ab < a* [E = a*]\nwhere 'a' and 'b' are the observed phenotype values of the individual perturbations ('a*' being the most severe of the two), 'ab' is the observed phenotype value of the double perturbation, 'E' is the expected phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:15833125]
subset: PSI-MI_slim
is_a: MI:0796 ! suppression
created_by: orchard
creation_date: 2013-06-05T21:36:07Z

[Term]
id: MI:1292
name: unilateral suppression
def: "An effect in which the perturbation of one gene, which has no effect on the phenotype in question, is combined with the perturbation of another gene, which causes the mutant phenotype in question, and results in the amelioration or lessening of the severity/penetrance of the mutant phenotype, in effect making the organism more \"wild type\" in character with regards to the phenotype in question. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\na < ab <= b = wt [E = a]\nOR\nwt = b <= ab < a [E = a]\nwhere 'a' and 'b' are the observed phenotype values of the individual perturbations, 'ab' is the observed phenotype value of the double perturbation, 'E' is the expected phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:15833125]
subset: PSI-MI_slim
is_a: MI:0796 ! suppression
created_by: orchard
creation_date: 2013-06-05T21:37:28Z

[Term]
id: MI:1293
name: unilateral suppression (complete)
def: "An effect in which the perturbation of one gene, which has no effect on the phenotype in question, is combined with the perturbation of another gene, which causes the mutant phenotype in question, and results in the complete suppression (to wild type) of the mutant phenotype. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\na < ab = b = wt [E = a]\nOR\nwt = b = ab < a [E = a]\nwhere 'a' and 'b' are the observed phenotype values of the individual perturbations, 'ab' is the observed phenotype value of the double perturbation, 'E' is the expected phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:15833125]
subset: PSI-MI_slim
is_a: MI:1292 ! unilateral suppression
created_by: orchard
creation_date: 2013-06-05T21:38:36Z

[Term]
id: MI:1294
name: unilateral suppression (partial)
def: "An effect in which the perturbation of one gene, which has no effect on the phenotype in question, is combined with the perturbation of another gene, which causes the mutant phenotype in question, and results in the amelioration or lessening of the severity/penetrance of the mutant phenotype, in effect making the organism more, but not completely, \"wild type\" in character with regards to the phenotype in question. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\na < ab < b = wt [E = a]\nOR\nwt = b < ab < a [E = a]\nwhere 'a' and 'b' are the observed phenotype values of the individual perturbations, 'ab' is the observed phenotype value of the double perturbation, 'E' is the expected phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:15833125]
subset: PSI-MI_slim
is_a: MI:1292 ! unilateral suppression
created_by: orchard
creation_date: 2013-06-05T21:39:32Z

[Term]
id: MI:1295
name: unilateral over-suppression
def: "An effect in which the perturbation of one gene (which has no individual effect on the phenotype in question), when combined with a perturbation of another gene (which causes the phenotype in question), results in a mutant phenotype opposite (relative to wild type) to that of the original phenotype. With respect to any single quantifiable phenotype, this may be expressed as an inequality as:\nE = a < b = wt < ab\nOR\nab < wt = b < a = E\nwhere 'a' and 'b' are the observed phenotype values of the individual perturbations, 'ab' is the observed phenotype value of the double perturbation, 'E' is the expected phenotype value of the double perturbation, and 'wt' is the wild type phenotype value." [PMID:15833125]
subset: PSI-MI_slim
is_a: MI:1286 ! over-suppression
created_by: orchard
creation_date: 2013-06-05T21:54:08Z

[Term]
id: MI:1296
name: amino acid analysis
def: "The presence of particular residues,for example those altered through post-translational modification, can be identified by amino acid analysis. Popular techniques for this include mass spectrometry or residue-specific antibodies." [PMID:19072539]
subset: PSI-MI_slim
is_a: MI:0659 ! experimental feature detection
created_by: orchard
creation_date: 2013-06-06T07:49:49Z

[Term]
id: MI:1297
name: phosphoamino acid analysis
def: "The presence of amino acid residues phosphorylated as a result of post-translational modification, can be identified by amino acid analysis. Popular techniques for this include mass spectrometry or residue-specific antibodies." [PMID:19072539]
subset: PSI-MI_slim
is_a: MI:1296 ! amino acid analysis
created_by: orchard
creation_date: 2013-06-06T07:55:30Z

[Term]
id: MI:1298
name: complex type
def: "A classification of the structural characteristics of a macromolecular complex." [PMID:12853463]
subset: PSI-MI_slim
is_a: MI:0314 ! complex
created_by: orchard
creation_date: 2013-06-06T08:52:34Z

[Term]
id: MI:1299
name: complex composition
def: "A description of the molecule types of which a macromolecular complex is composed." [PMID:12853464]
subset: PSI-MI_slim
is_a: MI:0314 ! complex
created_by: orchard
creation_date: 2013-06-06T08:55:37Z

[Term]
id: MI:1300
name: obligate complex
def: "The protein chains present in the complex are not found as independent stable structures in vivo." [PMID:12853463]
subset: PSI-MI_slim
is_a: MI:1298 ! complex type
created_by: orchard
creation_date: 2013-06-06T08:57:32Z

[Term]
id: MI:1301
name: non-obligate complex
def: "Protein chains present in the complex may also be found as independent stable proteins in vivo." [PMID:12853463]
subset: PSI-MI_slim
is_a: MI:1298 ! complex type
created_by: orchard
creation_date: 2013-06-06T09:02:52Z

[Term]
id: MI:1302
name: stable complex
def: "A stable set (2 or more) of interacting molecules which can be co-purified and have been shown to exist as a functional unit in vivo." [PMID:12853464]
subset: PSI-MI_slim
is_a: MI:1298 ! complex type
created_by: orchard
creation_date: 2013-06-06T09:05:59Z

[Term]
id: MI:1303
name: transient complex
def: "A macromolecular complex of which the participants associate and dissociate in vivo. Weak transient complexes feature a dynamic oligomeric equilibrium in solution where the interaction is broken and formed continuously. Strong transient associations that require a molecular trigger to shift the oligomeric equilibrium." [PMID:12853463]
subset: PSI-MI_slim
is_a: MI:1298 ! complex type
created_by: orchard
creation_date: 2013-06-06T09:09:01Z

[Term]
id: MI:1304
name: molecule set
def: "A group of molecules linked by a high degree of similarity of sequence and/or function and not easily separated by participant identification methods." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0313 ! interactor type
created_by: orchard
creation_date: 2013-06-06T09:20:00Z

[Term]
id: MI:1305
name: candidate set
def: "A group of interactors hypothesized to perform a specified function. Example: Two splice variants of Raptor mRNA encode closely related proteins. One (member) has been shown to participate in formation of active mTORC complex; the other (candidate) is thought to do so." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1304 ! molecule set
created_by: orchard
creation_date: 2013-06-06T10:09:09Z

[Term]
id: MI:1306
name: open set
def: "A group of interactors that can be counted in principle but not in practice, such as mRNA or long-chain fatty acid. Examples - ceruloplasmin mRNA, palmitic acid." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1304 ! molecule set
created_by: orchard
creation_date: 2013-06-06T10:19:10Z

[Term]
id: MI:1307
name: defined set
def: "Two or more interactors, grouped to denote interchangeable function. Thus the addition of a single nucleotide residue during RNA transcription could be annotated with the definedSet NTP (members ATP, CTP, GTP, and UTP)." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1304 ! molecule set
created_by: orchard
creation_date: 2013-06-06T10:22:53Z

[Term]
id: MI:1308
name: resulting sequence
def: "Used to specify the identity of the residue (or residues) introduced by mutation or variant (of child terms). The attribute would be used concurrently with the description\nprovided in the feature name." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0668 ! feature attribute name
created_by: orchard
creation_date: 2013-06-06T10:26:19Z

[Term]
id: MI:1309
name: de-ADP-ribosylation assay
def: "Hydrolytic reactions that release ADP-ribose." [PMID:23474712, PMID:23474714]
subset: PSI-MI_slim
synonym: "mono-ADP-ribosylhydrolase" EXACT []
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2013-06-06T10:31:58Z

[Term]
id: MI:1310
name: de-ADP-ribosylation reaction
def: "Measure of  hydrolytic reactions that release ADP-ribose." [PMID:23474712, PMID:23474714]
subset: PSI-MI_slim
synonym: "mono-ADP-ribosylhydrolase reaction" RELATED []
is_a: MI:0414 ! enzymatic reaction
created_by: orchard
creation_date: 2013-06-06T10:34:18Z

[Term]
id: MI:1311
name: differential scanning calorimetry
def: "Differential scanning calorimetry (DSC) is a thermoanalytical technique in which the difference in the amount of heat required to increase the temperature of a sample and reference in solution is measured as a function of temperature. By measuring the temperature dependence of this partial heat capacity, a basic thermodynamic property, DSC gives immediate access to the thermodynamic mechanism that governs a conformational equilibrium, for example between a protein complex and its individual participants." [PMID:10398392]
subset: PSI-MI_slim
synonym: "dsc" EXACT PSI-MI-short []
is_a: MI:0013 ! biophysical
created_by: orchard
creation_date: 2013-06-06T10:39:30Z

[Term]
id: MI:1312
name: aut-page
def: "Method allowing the detection of interactions between two or more molecules by their very close proximity or the overlap of their respective bands in a SDS gel containing urea as an additional denaturing agent." [PMID:12875839]
subset: PSI-MI_slim
synonym: "acetic acid/urea/triton PAGE" RELATED []
is_a: MI:0807 ! comigration in gel electrophoresis
created_by: orchard
creation_date: 2013-06-06T10:43:24Z

[Term]
id: MI:1313
name: proximity labelling technology
def: "Methods depend on a modification that only takes place with the close proximity of two molecules - a protein fused to the bait can then modify any neighbouring prey proteins, for example. The resulting tag can be used for isolation and/or identification." [PMID:22412018]
subset: PSI-MI_slim
is_a: MI:2198 ! labelling assay
created_by: orchard
creation_date: 2013-06-06T11:20:43Z

[Term]
id: MI:1314
name: proximity-dependent biotin identification
def: "A promiscuous biotin protein ligase is fused to the bait protein, neighbouring prey are then biotinylated. The biotin tag may be used for isolation and/or identification." [PMID:22412018]
subset: PSI-MI_slim
synonym: "BioID" RELATED []
is_a: MI:1313 ! proximity labelling technology
created_by: orchard
creation_date: 2013-06-06T11:23:53Z

[Term]
id: MI:1315
name: complex recommended name
def: "The most accepted name in the literature for this complex." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1041 ! synonym
created_by: orchard
creation_date: 2013-10-14T15:00:37Z

[Term]
id: MI:1316
name: complex systematic name
def: "A name for a complex built of the component parts of that complex." []
subset: PSI-MI_slim
is_a: MI:1041 ! synonym
created_by: orchard
creation_date: 2013-10-14T15:04:57Z

[Term]
id: MI:1317
name: eukaryotic linear motif resource
def: "The ELM resource provides a database of curated short linear motif classes and instances, as well as a sequence analysis tool to detect putative short linear motif instances in query sequences. http://elm.eu.org/" [PMID:22110040]
synonym: "elm" EXACT PSI-MI-short []
xref: id-validation-regexp: "[A-Za-z_0-9]+$"
xref: search-url: "http://elm.eu.org/elms/elmPages/${ac}.html"
is_a: MI:0447 ! feature database
created_by: orchard
creation_date: 2013-10-22T09:49:10Z

[Term]
id: MI:1318
name: sulfate donor
def: "Any molecule that is able to transfer a sulphate group to another chemical species." [PMID:14755292]
subset: PSI-MI_slim
synonym: "sulphate donor" RELATED []
is_a: MI:0918 ! donor
created_by: orchard
creation_date: 2014-01-08T07:51:29Z

[Term]
id: MI:1319
name: sulfate acceptor
def: "Molecule to which a sulphate group may be transferred from a sulphate donor." [PMID:14755292]
subset: PSI-MI_slim
synonym: "sulphate acceptor" RELATED []
is_a: MI:0919 ! acceptor
created_by: orchard
creation_date: 2014-01-08T07:52:46Z

[Term]
id: MI:1320
name: membrane yeast two hybrid
def: "Traditional yeast two hybrid assays are not suitable for the analysis of membrane proteins, as they require the interactions to occur in the nucleus. Methods have been specifically developed to assay for interactions of membrane proteins with both cytosolic or membrane-bound partners." [PMID:2261051]
subset: PSI-MI_slim
synonym: "MYTH" EXACT []
is_a: MI:0232 ! transcriptional complementation assay
created_by: orchard
creation_date: 2014-01-08T10:14:46Z

[Term]
id: MI:1321
name: ire1 reconstruction
def: "Upon interaction of N-terminal generated Ire1p-fusions, the Ire1p kinase domains oligomerize, transphosphorylate and activate their C-terminal RNAseL domains, which specifically splice the mRNA of a transcriptional activator, Hac1.  The expression of the mature form of Hac1p leads to the interaction-specific expression of a reporter. Specifically designed to identify interactors of proteins found in the endoplasmic reticulum." [PMID:22665516]
subset: PSI-MI_slim
synonym: "endoplasmic reticulum membrane yeast-two hybrid" RELATED []
synonym: "ER-MYTH" RELATED []
is_a: MI:1320 ! membrane yeast two hybrid
created_by: orchard
creation_date: 2014-01-08T10:17:38Z

[Term]
id: MI:1322
name: atto 465
def: "Fluorescent tag - maleimide couples to thiols." [PMID:14755292]
subset: PSI-MI_slim
synonym: "atto 465 maleimide" EXACT []
synonym: "atto465" EXACT []
is_a: MI:1092 ! atto label
created_by: orchard
creation_date: 2014-01-08T10:27:34Z

[Term]
id: MI:1323
name: tag visualisation by alkaline phosphatase activity
def: "The protein is expressed as a hybrid protein fused to a tag containing an alkaline phosphatase activity. Subsequent observation or measurement of alkaline phosphatase activity is used to identify the presence of the molecule in an interaction." [PMID:14755292]
subset: PSI-MI_slim
synonym: "tag alk phosphatase activity" EXACT PSI-MI-short []
is_a: MI:0980 ! tag visualisation by enzyme assay
created_by: orchard
creation_date: 2014-01-08T11:00:36Z

[Term]
id: MI:1324
name: conditioned medium
def: "Molecule present in media harvested from cultured cells." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0342 ! sample process
created_by: orchard
creation_date: 2014-01-08T11:07:44Z

[Term]
id: MI:1325
name: sulfurtransferase assay
def: "Measures the rate of a sulphate molecule transfer between two molecules." [PMID:14755292]
subset: PSI-MI_slim
synonym: "sulfertransferase" EXACT PSI-MI-short []
synonym: "sulfurtransfer assay" RELATED []
synonym: "sulphurtransferase assay" RELATED []
is_a: MI:0415 ! enzymatic study
created_by: orchard
creation_date: 2014-01-08T11:13:39Z

[Term]
id: MI:1326
name: CLONE OF phosphotransfer reaction
def: "Reaction where a phosphate is transferred between two proteins of a phosphorelay system. " [PMID:14755292, PMID:16712436]
subset: PSI-MI_slim
synonym: "phosphotransfer" EXACT PSI-MI-short []
is_obsolete: true
created_by: orchard
creation_date: 2014-01-08T11:15:51Z

[Term]
id: MI:1327
name: sulfurtransfer reaction
def: "Reaction where a sulfate group is transferred between two proteins" [GO:GO\:0016783, PMID:14755292]
subset: PSI-MI_slim
synonym: "sulfurtransfer" EXACT PSI-MI-short []
synonym: "sulphurtransfer reaction" EXACT []
is_a: MI:0414 ! enzymatic reaction
created_by: orchard
creation_date: 2014-01-08T11:16:12Z

[Term]
id: MI:1328
name: coumarin label
def: "A class of labels derived from the benzopyrone coumarin." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0857 ! fluorescent dye label
created_by: orchard
creation_date: 2014-01-08T11:25:00Z

[Term]
id: MI:1329
name: cpm
def: "The thiol-reactive coumarin, CPM is very weakly fluorescent until reacted with thiols producing a conjugate with excitation/emission maxima of ~384/470 nm." [PMID:14755292]
synonym: "7-diethylamino-3-(4' maleimidylphenyl)-4-methylcoumarin" EXACT []
is_a: MI:1328 ! coumarin label
created_by: orchard
creation_date: 2014-01-08T11:36:48Z

[Term]
id: MI:1330
name: dnp
def: "Fluorescent dye. Also acts as an uncoupler of oxidative phosphorylation in the mitochondria." [PMID:14755292]
subset: PSI-MI_slim
synonym: "2, 4-DNP" EXACT []
synonym: "2,4-Dinitrophenol" EXACT []
synonym: "dinitrophenol" EXACT []
is_a: MI:0857 ! fluorescent dye label
created_by: orchard
creation_date: 2014-01-08T12:01:24Z

[Term]
id: MI:1331
name: evidence ontology
def: "The Evidence Ontology (ECO) describes types of scientific evidence within the realm of biological research that can arise from laboratory experiments, computational methods, manual literature curation, and other means." [PMID:14755292]
subset: PSI-MI_slim
synonym: "ECO" RELATED []
xref: id-validation-regexp: "ECO:\\d{7}$"
xref: search-url: "http://www.ebi.ac.uk/ols/ontologies/ECO/terms?obo_id=${ac}"
is_a: MI:1336 ! experiment database
created_by: orchard
creation_date: 2014-01-08T12:48:33Z

[Term]
id: MI:1332
name: bhf-ucl
def: "The Cardiovascular Gene Annotation Initiative represents a collaboration between University College London and the European Bioinformatics Institute (EBI), funded by the British Heart Foundation.  This annotation group is a member of the IMEx Consortium." [PMID:21419760]
subset: PSI-MI_slim
synonym: "BHF-UCL" EXACT PSI-MI-alternate []
synonym: "Cardiovascular Gene Annotation Initiative" RELATED []
is_a: MI:0461 ! interaction database
is_a: MI:0973 ! imex source
created_by: orchard
creation_date: 2014-01-08T12:56:27Z

[Term]
id: MI:1333
name: rogid
def: "SEGUID's are SHA-1 keys written in canonical base64 form with trailing = characters removed. ROG identifiers concatenate a SEGUID with a numerical taxonomy identifier. Therefore, the allowable characters in a SEGUID or ROG identifier are (in ascending ASCII or Unicode value):\n+/0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz\nLists of SEGUID or ROG identifiers were sorted in ascending ASCII-based lexicographical order." [PMID:18823568]
subset: PSI-MI_slim
is_a: MI:1212 ! checksum
created_by: orchard
creation_date: 2014-01-09T11:17:18Z

[Term]
id: MI:1334
name: rigid
def: "A global unique identifier to identify interactions that are identical. A RIG identifier (RIGID) is constructed by concatenating ROGID MI:1335 (after sorting them in ascending lexicographical order ), applying the SHA-1 algorithm to the resulting string, converting the digest to its base64 representation and removing all trailing \"=\" characters used for padding." [PMID:18823568]
subset: PSI-MI_slim
is_a: MI:0664 ! interaction attribute name
is_a: MI:1212 ! checksum
created_by: orchard
creation_date: 2014-01-09T11:17:32Z

[Term]
id: MI:1335
name: hpidb
def: "Host-pathogen database. HPIDB integrates experimental PPIs from several public databases into a single, non-redundant web accessible resource.  Manual curation is performed via the IntAct (ww.ebi.ac.uk/intact) curation interface.\nhttp://www.agbase.msstate.edu/hpi/main.html" [PMID:20946599]
subset: PSI-MI_slim
synonym: "Host Pathogen Interaction database" EXACT PSI-MI-alternate []
synonym: "HPIDB" EXACT PSI-MI-alternate []
is_a: MI:0461 ! interaction database
created_by: orchard
creation_date: 2014-03-03T11:43:31Z

[Term]
id: MI:1336
name: experiment database
def: "Databases that contain information used to add additional information to experiments (meta-data)." [PMID:14755292]
subset: Drugable
subset: PSI-MI_slim
synonym: "experiment xref" EXACT PSI-MI-short []
is_a: MI:0444 ! database citation
created_by: orchard
creation_date: 2014-01-20T11:56:03Z

[Term]
id: MI:1337
name: efo
def: "The Experimental Factor Ontology provides a systematic description of many experimental variables, combining parts of several biological ontologies to additional new terms." [pmid:20200009]
subset: PSI-MI_slim
synonym: "Experimental facto ontology" EXACT []
xref: id-validation-regexp: "\\d{7}$"
xref: search-url: "http://www.ebi.ac.uk/ols/ontologies/efo/terms?obo_id=${ac}"
is_a: MI:1336 ! experiment database
created_by: orchard
creation_date: 2014-01-20T11:58:47Z

[Term]
id: MI:1338
name: eef tag
def: "Glu-Glu-Phe epitope tag, allowing its detection with rat monoclonal antibody YL1/2" [PMID:6204858]
subset: PSI-MI_slim
synonym: "Glu-Glu-Phe epitope tag" RELATED []
is_a: MI:0507 ! tag
created_by: orchard
creation_date: 2014-01-20T12:13:30Z

[Term]
id: MI:1339
name: supercharged green fluorescent protein
def: "Mutated green fluorescent protein with altered net charge and thus altered intermolecular properties, such as resistence to aggregation." [PMID:17665911]
subset: PSI-MI_slim
synonym: "stGFP" RELATED []
is_a: MI:0367 ! green fluorescent protein tag
created_by: orchard
creation_date: 2014-01-20T13:13:03Z

[Term]
id: MI:1340
name: human orfeome collection
def: "A central resource of single-colony, fully-sequenced cloned human ORFs which can be readily transferred to Gateway compatible destination vectors for various functional proteomics studies. This set of ORFs ranges in size from 75 to more than 10,000 base pairs, and contains over 1,000 ORFs from genes with multiple splice variants." [PMID:14755292]
subset: PSI-MI_slim
xref: search-url: "http://horfdb.dfci.harvard.edu/"
is_a: MI:1096 ! protein sequence databases
created_by: orchard
creation_date: 2014-04-08T16:15:19Z

[Term]
id: MI:1341
name: set member
def: "Indicates that this protein is a member of a set of proteins with similar sequence and/or function." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0353 ! cross-reference type
created_by: orchard
creation_date: 2014-04-25T09:19:21Z

[Term]
id: MI:1342
name: qcmd
def: "The quartz crystal microbalance is a physical technique that detects changes in the resonance frequency of an electrically driven quartz crystal with changes in mass. It provides qualitative and quantitative information about biomolecular interactions by translating changes in mass at the probe-immobilized surface of the crystal sensor into measurable changes in the resonant frequency of the quartz crystal. QCM-D enables real-time, label free measurements of molecular adsorption and/or interactions on various surfaces and is able to monitor conformational changes upon interactions." [PMID:19137101, PMID:22158962, PMID:23504432]
subset: PSI-MI_slim
synonym: "QCM-D" EXACT []
synonym: "Quartz Crystal Microbalance with Dissipation monitoring" EXACT []
is_a: MI:0968 ! biosensor
created_by: orchard
creation_date: 2014-07-17T08:26:51Z

[Term]
id: MI:1343
name: enzyme regulator
def: "Regulatory subunits of enzyme complexes can determine the activity level or specificity of catalytic subunits." [PMID:14755292]
subset: PSI-MI_slim
synonym: "enzyme complex regulatory subunit" BROAD []
is_a: MI:2274 ! regulator
created_by: orchard
creation_date: 2014-07-17T08:43:17Z

[Term]
id: MI:1344
name: erythrosin iodoacetamide label
def: "Fluoresceine-derived label." [PMID:14755292]
synonym: "ErIA" EXACT []
synonym: "erythrosin-5-iodoacetamide" EXACT []
is_a: MI:0939 ! fluorescein label
created_by: orchard
creation_date: 2014-07-17T08:47:44Z

[Term]
id: MI:1345
name: rho tag
def: "A 9-amino acid peptide representing C terminus of bovine rhodopsin widely used as an epitope tag. A number of anti-rhodopsin antibodies recognize this epitope." [PMID:12110672, PMID:24943310]
subset: PSI-MI_slim
synonym: "1D4 tag" EXACT PSI-MI-alternate []
synonym: "rho1D4 tag" EXACT PSI-MI-alternate []
is_a: MI:0507 ! tag
created_by: orchard
creation_date: 2014-09-19T14:24:43Z

[Term]
id: MI:1346
name: bmrb
def: "Database for NMR spectroscopy information on biomolecules hosted at the University of Wisconsin, Madison, US." [PMID:18288446]
subset: PSI-MI_slim
synonym: "Biological Magnetic Resonance Data Bank" RELATED []
synonym: "BioMagResBank" RELATED []
is_a: MI:0461 ! interaction database
created_by: orchard
creation_date: 2014-09-19T14:42:33Z

[Term]
id: MI:1347
name: protein ontology
def: "PRO provides an ontological representation of protein-related entities by explicitly defining them and showing the relationships between them. Each PRO term represents a distinct class of entities, including specific modified forms, orthologous isoforms, and protein complexes." [PMID:24270789]
subset: PSI-MI_slim
synonym: "PRO" RELATED []
xref: id-validation-regexp: "[0-9]{9}|[A-Z][0-9][A-Z0-9]{3}[0-9]|[A-Z][0-9][A-Z0-9]{3}[0-9]-[1-9]+"
xref: search-url: "http://pir.georgetown.edu/cgi-bin/pro/entry_pro?id=${ac}"
is_a: MI:0461 ! interaction database
created_by: orchard
creation_date: 2014-09-26T14:06:25Z

[Term]
id: MI:1348
name: chembl target
def: "ChEMBL focuses on mapping the interactions of small molecules binding to their macromolecular targets." []
subset: PSI-MI_slim
xref: regexp: "CHEMBL:[0-9]+"
xref: search-url: "http://www.ebi.ac.uk/chembldb/index.php/target/inspect/${ac}"
is_a: MI:0683 ! sequence database
relationship: part_of MI:1349 ! chembl
created_by: orchard
creation_date: 2014-10-16T10:10:03Z

[Term]
id: MI:1349
name: chembl
def: "ChEMBL focuses on mapping the interactions of small molecules binding to their macromolecular targets." [PMID:24214965]
subset: PSI-MI_slim
is_a: MI:0461 ! interaction database
created_by: orchard
creation_date: 2014-10-16T10:16:54Z

[Term]
id: MI:1350
name: orphanet
def: "Orphanet is a reference portal for information on rare diseases and orphan drugs. Its aim is to help improve the diagnosis, care and treatment of patients with rare diseases." [PMID:19058507]
subset: PSI-MI_slim
xref: id-validation-regexp: "^\\d+$"
xref: search-url: "http://www.ebi.ac.uk/ols/ontologies/ordo/terms?obo_id=${ac}"
is_a: MI:1336 ! experiment database
created_by: orchard
creation_date: 2014-10-16T10:27:01Z

[Term]
id: MI:1351
name: inferred-from
def: "Refers to the original experimentally verified object from which the described object has been derived." [PMID:25313161]
subset: PSI-MI_slim
is_a: MI:0353 ! cross-reference type
created_by: orchard
creation_date: 2014-10-16T10:39:21Z

[Term]
id: MI:1352
name: uracil interference assay
def: "In uracil interference assays, the DNA will be amplified by PCR in the presence of a mixture of TTP and dUTP to randomly replace thymine by deoxyuracil residues before the binding assay. If T nucleotides involved in protein-DNA interactions are replaced by deoxyuracil, protein binding is prevented. After isolating the protein-DNA complex, DNA is cleaved with uracil-N-glycosylase, which specifically targets uracil bases, and the products are electrophoresed on a denaturing polyacrylamide gel. As a result, DNA in which a thymine involved in binding is replaced by uracil will be depleted. Hence, although the pattern looks like a footprint, the blank region means \"contact points\"." [PMID:18265086]
subset: PSI-MI_slim
is_a: MI:0605 ! enzymatic footprinting
created_by: orchard
creation_date: 2015-01-28T10:12:25Z

[Term]
id: MI:1353
name: au5 tag
def: "Epitope tag engineered onto the N- or C- terminus of a protein of interest so that the tagged protein can be analyzed and visualized by immunochemical methods. The recognized AU5 epitope represents the amino acid sequence TDFYLK." [PMID:9765280]
subset: PSI-MI_slim
is_a: MI:0507 ! tag
created_by: orchard
creation_date: 2015-01-28T10:23:06Z

[Term]
id: MI:1354
name: lipase assay
def: "Cleavage (hydrolysis) of a lipid molecule." [PMID:14760721]
subset: PSI-MI_slim
is_a: MI:0990 ! cleavage assay
created_by: orchard
creation_date: 2015-02-03T13:18:55Z

[Term]
id: MI:1355
name: lipid cleavage
def: "Reaction monitoring the cleavage (hydrolysis) or a lipid molecule." [PMID:14760721]
subset: PSI-MI_slim
is_a: MI:0194 ! cleavage reaction
created_by: orchard
creation_date: 2015-02-03T13:25:21Z

[Term]
id: MI:1356
name: validated two hybrid
def: "The protein pairs, often initially identified by a separate 2-hybrid screening methodology, are subjected to a rigorous re-analysis which may include independent re-screening of the entire search space, retesting the  assay in different strain backgrounds, and multiple retesting of identified protein pairs reversing bait-prey orientations. Orthogonal data from other experimental and bioinformatic approaches may also be used to support the identification of the final high-confidence protein pairs but the primary means of selection must be experimentally based. This method would be expected to identify protein pairs with a higher degree of confidence than any single protein complementation technique." [PMID:25416956]
subset: PSI-MI_slim
is_a: MI:0018 ! two hybrid
created_by: orchard
creation_date: 2015-02-03T13:36:20Z

[Term]
id: MI:1357
name: RNAcentral
def: "Provides unified access to the ncRNA sequence data supplied by the expert databases." [PMID:25352543]
subset: PSI-MI_slim
xref: id-validation-regexp: "/URS[0-9A-F]{10}/i"
xref: search-url: "http://rnacentral.org/rna/${ac}"
is_a: MI:0683 ! sequence database
created_by: orchard
creation_date: 2015-02-03T13:37:23Z

[Term]
id: MI:2002
name: drugbank
def: "DrugBank Accession number consisting of the 4 letter prefix and a 5 number suffix. Each Accession number is unique to the drug's generic name. The 4 letter suffix (APRD, EXPT, BIOD, NUTR) indicates the type of drug (APRD=approved small molecule drug, EXPT=experimental drug, BIOD=biotech drug, NUTR=nutraceutical or natural product). Biotech drugs consist of FDA approved peptide, protein or nucleic acid drugs, approved small molecule drugs are FDA approved non-biotech drugs, nutraceuticals are natural products (amino acids, vitamins, other metabolites) and experimental drugs include drugs under trial, pre-clinical drugs, unapproved drugs, well known inhibitors and possible toxins." [PMID:14755292]
subset: Drugable
is_a: MI:2054 ! bioactive entity reference

[Term]
id: MI:2003
name: commercial name
def: "Standard name of drug or any reagent as provided by its manufacturer." [PMID:14755292]
subset: Drugable
synonym: "generic name" EXACT PSI-MI-alternate []
is_a: MI:1041 ! synonym

[Term]
id: MI:2004
name: drug brand name
def: "Alternate names of the drug, brand names from different manufacturers." [PMID:14755292]
subset: Drugable
is_a: MI:1041 ! synonym

[Term]
id: MI:2005
name: drug mixture brand name
def: "Brand names and composition of mixtures that include the drug described in this DrugCard file." [PMID:14755292]
subset: Drugable
synonym: "mix brand name" EXACT PSI-MI-short []
is_a: MI:1041 ! synonym

[Term]
id: MI:2006
name: biotech product preparation
def: "Description of the drug (for biotech drugs) describing its composition and/or preparation." [PMID:14755292]
subset: Drugable
synonym: "biotech prep" EXACT PSI-MI-short []
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2007
name: iupac name
def: "IUPAC or standard chemical name for a drug, or a chemical." [PMID:14755292]
subset: Drugable
is_a: MI:1041 ! synonym

[Term]
id: MI:2008
name: chemical formula
def: "Chemical formula describing atomic or elemental composition" [PMID:14755292]
subset: Drugable
is_a: MI:2086 ! physicochemical attribute name

[Term]
id: MI:2009
name: chemical structure
def: "Image of the drug structure (if small molecule) or its sequence (if biotech drug)" [PMID:14755292]
subset: Drugable
is_a: MI:2086 ! physicochemical attribute name

[Term]
id: MI:2010
name: standard inchi
def: "IUPAC International Chemical Identifier (InChI) - a machine-readable character string describing a chemical structure, developed by IUPAC and the InChI Trust as a standard to allow interoperability and linking between chemical resources. The standard InChI differs from the non-standard InChI in that it is generated with a fixed set of parameters, ensuring consistency between different resources. The current version of the standard InChI software is 1.03." [PMID:14755292]
subset: PSI-MI_slim
synonym: "inchi id" RELATED []
synonym: "standard inchi" EXACT PSI-MI-short []
is_a: MI:1212 ! checksum
is_a: MI:2091 ! structure representation attribute name

[Term]
id: MI:2011
name: cas registry number
def: "Chemical Abstract Service identification number" [PMID:14755292]
subset: Drugable
is_a: MI:2054 ! bioactive entity reference

[Term]
id: MI:2012
name: kegg compound
def: "Kyoto Encyclopedia of Genes and Genomes compound identification number (if molecule is in KEGG)" [PMID:14755292]
subset: Drugable
synonym: "KEGG Compound ID" EXACT PSI-MI-alternate []
is_a: MI:0470 ! kegg

[Term]
id: MI:2013
name: pubchem
def: "NCBI's PubChem database identification number (if molecule is in PubChem).\nOBSOLETE as redudant with MI:0730" [PMID:14755292]
subset: Drugable
synonym: "PubChem ID" EXACT PSI-MI-alternate []
is_obsolete: true

[Term]
id: MI:2015
name: pharmgkb
def: "Pharmacogenomics Knowledge Base identification number (if molecule is in PharmGKB)" [PMID:14755292]
subset: Drugable
is_a: MI:2054 ! bioactive entity reference

[Term]
id: MI:2016
name: bind smid
def: "BIND database Small Molecule Identification number (if molecule is in BIND)" [PMID:14755292]
comment: May not be publicly available any more since now owned by Thompson Scientific.
subset: Drugable
is_a: MI:2054 ! bioactive entity reference

[Term]
id: MI:2017
name: heterogen
def: "The HET records are used to describe non-standard residues, such as prosthetic groups, inhibitors, solvent molecules, and ions for\nwhich coordinates are supplied. Groups are considered HET if they are: \n- not one of the standard amino acids, and \n- not one of the nucleic acids (C, G, A, T, U, and I), and \n- not one of the modified versions of nucleic acids (+C, +G, +A,\n+T, +U, and +I), and \n- not an unknown amino acid or nucleic acid where UNK is used to\nindicate the unknown residue name. \nHet records also describe heterogens for which the chemical identity is unknown, in which case the group is assigned the hetID UNK." [PMID:14755292]
subset: Drugable
synonym: "het" EXACT PSI-MI-short []
is_a: MI:0460 ! rcsb pdb
is_a: MI:0472 ! pdbe
is_a: MI:0806 ! pdbj

[Term]
id: MI:2020
name: canadian drug identification number
def: "Drug Identification Number (Canadian Drug ID system)" [PMID:14755292]
subset: Drugable
synonym: "din" EXACT PSI-MI-short []
is_a: MI:2054 ! bioactive entity reference

[Term]
id: MI:2021
name: rxlist link
def: "Hyperlink to RxList entry for the given drug (if it exists)" [PMID:14755292]
subset: Drugable
is_a: MI:2054 ! bioactive entity reference

[Term]
id: MI:2023
name: material safety data sheet
def: "Material Safety Data Sheet (if it exists). A Material Safety Data Sheet (MSDS) is designed to provide both workers and emergency personnel with the proper procedures for handling or working with a particular substance. MSDS's include information such as physical data (melting point, boiling point, flash point etc.), toxicity, health effects, first aid, reactivity, storage, disposal, protective equipment, andspill/leak procedures. These are of particular use if a spill or other accident occurs." [PMID:14755292]
subset: Drugable
synonym: "msds" EXACT PSI-MI-short []
synonym: "MSDS Material Safety Sheet" EXACT PSI-MI-alternate []
is_a: MI:2086 ! physicochemical attribute name

[Term]
id: MI:2024
name: patent number
def: "number of the patent describing a drug's synthesis or use." [PMID:14755292]
subset: Drugable
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:2025
name: molecular weight
def: "Molecular weight in g/mol, determined from molecular formula or sequence." [PMID:14755292]
subset: Drugable
is_a: MI:0640 ! parameter type

[Term]
id: MI:2026
name: melting point
def: "The melting point of a solid is the temperature range at which it changes state from solid to liquid." [PMID:14755292]
subset: Drugable
is_a: MI:0640 ! parameter type

[Term]
id: MI:2027
name: water solubility
def: "Water solubility in mg/mL or g/L" [PMID:14755292]
subset: Drugable
synonym: "logSw" EXACT PSI-MI-alternate []
is_a: MI:2160 ! logs

[Term]
id: MI:2029
name: logp
def: "Water/octanol partition coefficient  of a small molecule." [PMID:14755292]
subset: Drugable
is_a: MI:0640 ! parameter type

[Term]
id: MI:2030
name: isoelectric point
def: "The isoelectric point (pI) is the pH at which a particular molecule or surface carries no net electrical charge. For an amino acid with only one amine and one carboxyl group, the pI can be calculated from the pKas of this molecule." [PMID:14755292]
subset: Drugable
is_a: MI:0640 ! parameter type

[Term]
id: MI:2033
name: hydrophobicity
def: "Physical property of a molecule (known as a hydrophobe) that is repelled from a mass of water. Gravy score." [PMID:14755292]
subset: Drugable
is_a: MI:0640 ! parameter type

[Term]
id: MI:2036
name: boiling point
def: "The boiling point of a liquid is the temperature at which the vapor pressure of the liquid equals the environmental pressure surrounding the liquid. A liquid in a vacuum environment has a lower boiling point than when the liquid is at atmospheric pressure. A liquid in a high pressure environment has a higher boiling point than when the liquid is at atmospheric pressure. In other words, the boiling point of liquids varies with and depends upon the surrounding environmental pressure." [PMID:14755292]
subset: Drugable
is_a: MI:0640 ! parameter type

[Term]
id: MI:2039
name: smiles string
def: "SMILES string corresponding to drug structure" [PMID:14755292]
subset: Drugable
is_a: MI:1212 ! checksum
is_a: MI:2091 ! structure representation attribute name

[Term]
id: MI:2040
name: drug type
def: "Type of drug (approved, experimental, biotech, nutraceutical)" [PMID:14755292]
subset: Drugable
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2041
name: drug category
def: "Therapeutic category or general category of drug (anti-convulsant, antibacterial, etc.)." [PMID:14755292]
subset: Drugable
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2042
name: disease indication
def: "Description or common names of diseases that the drug is used to treat." [PMID:14755292]
comment: Source of further terms could be MeSH term or SNOWMAN.
subset: Drugable
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2043
name: pharmacology
def: "Text description of how the drug works at a clinical or physiological level." [PMID:14755292]
subset: Drugable
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2044
name: mechanism of action
def: "Description of how the drug works or what it binds to at a molecular level." [PMID:14755292]
subset: Drugable
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2045
name: drug absorption
def: "Determination of how quickly and how much of a drug reaches its intended target (site) of action." [PMID:14755292]
subset: Drugable
is_a: MI:0640 ! parameter type

[Term]
id: MI:2046
name: lethal dose 50
def: "The LD50 is the dose that kills half (50%) of the animals tested" [PMID:14755292]
subset: Drugable
synonym: "ld50" EXACT PSI-MI-alternate []
synonym: "lethal dose 50 %" EXACT PSI-MI-alternate []
is_a: MI:0640 ! parameter type

[Term]
id: MI:2047
name: percentage of plasma protein binding
def: "Percentage of the drug that is bound in plasma proteins" [PMID:14755292]
subset: Drugable
synonym: "plasma prot binding" EXACT PSI-MI-short []
synonym: "protein binding %" EXACT PSI-MI-alternate []
is_a: MI:0640 ! parameter type

[Term]
id: MI:2048
name: drug biotransformation
def: "The chemical conversion of drugs to other compounds in the body, excluding degradation due to any inherent chemical instability of drugs in biological media." [PMID:14755292]
subset: Drugable
synonym: "drug metabolism" EXACT PSI-MI-short []
is_a: MI:2115 ! pharmacokinetics attribute name

[Term]
id: MI:2049
name: elimination half life
def: "Rate The time it takes for the body to eliminate or breakdown half of a dose of a pharmacologic agent, in practice the time taken for plasma concentration to reduce by 50%." [PMID:14755292]
subset: Drugable
synonym: "distribution halflife" EXACT PSI-MI-alternate []
synonym: "elimin half life" EXACT PSI-MI-short []
synonym: "t1/2" EXACT PSI-MI-alternate []
is_a: MI:0640 ! parameter type

[Term]
id: MI:2050
name: dosage form
def: "How the drug is dispensed (tablets, capsules, solutions), packing material." [PMID:14755292]
subset: Drugable
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2051
name: patient information
def: "Information on the disease indications and treatment regime for the drug. May also include contra-indications." [PMID:14755292]
subset: Drugable
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2053
name: contraindications
def: "Cautions or conditions indicating why or when the drug should not be taken or prescribed." [PMID:14755292]
subset: Drugable
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2054
name: bioactive entity reference
def: "General on-line reference to other details about a drug or other bioactive entity." [PMID:14755292]
subset: Drugable
subset: PSI-MI_slim
synonym: "bioactive entity ref" EXACT PSI-MI-short []
is_a: MI:0473 ! participant database

[Term]
id: MI:2055
name: chemical stability
def: "chemical stability occurs when a substance is in a (dynamic) chemical equilibrium with its environment. In this well-defined state, the substance is expected to persist indefinitely (assuming that the environment does not change).  A substance which is not chemically stable (yet exists) is metastable or kinetically persistent." [PMID:14755292]
subset: Drugable
synonym: "thermodynamic stability" EXACT PSI-MI-alternate []
is_a: MI:2086 ! physicochemical attribute name

[Term]
id: MI:2064
name: solubility
def: "Potential ability of a substance to dissolve in a liquid." [PMID:14755292]
subset: Drugable
synonym: "dt theoretical pi" EXACT PSI-MI-short []
is_a: MI:0640 ! parameter type

[Term]
id: MI:2084
name: organisms affected
def: "Names of organisms which are affected, positively or negatively, by the drug." [PMID:14755292]
subset: Drugable
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2086
name: physicochemical attribute name
def: "Chemical and physical properties of a molecule." [PMID:14755292]
subset: Drugable
synonym: "physicochemical att" EXACT PSI-MI-short []
is_a: MI:0590 ! attribute name

[Term]
id: MI:2089
name: bioactive entity attribute name
def: "Properties of a chemical tested or used as a drug, herbicide, insecticide etc." [PMID:14755292]
subset: Drugable
synonym: "bioactive entity att" EXACT PSI-MI-short []
is_a: MI:0590 ! attribute name

[Term]
id: MI:2091
name: structure representation attribute name
def: "Human artefact to describe and report the structure of a molecule." [PMID:14755292]
subset: Drugable
synonym: "struc representation" EXACT PSI-MI-short []
is_a: MI:0590 ! attribute name

[Term]
id: MI:2097
name: anti-convulsant
def: "Therapeutic category or general category of drug -anti-convulsant" [PMID:14755292]
subset: Drugable
is_a: MI:2041 ! drug category

[Term]
id: MI:2098
name: anti-bacterial
def: "Therapeutic category or general category of drug -anti-bacterial" [PMID:14755292]
subset: Drugable
is_a: MI:2041 ! drug category

[Term]
id: MI:2099
name: fda approved drug
def: "A drug licensed for sale in the USA by the FDA." [PMID:14755292]
subset: Drugable
is_a: MI:2040 ! drug type

[Term]
id: MI:2100
name: experimental drug
def: "A drug which has yet to be formally approved for the indication which it is currently being used to treat." [PMID:14755292]
subset: Drugable
is_a: MI:2040 ! drug type

[Term]
id: MI:2101
name: biotech drug
def: "A natural product, such as a protein or peptide, which is produced used biotechnology as a drug." [PMID:14755292]
subset: Drugable
is_a: MI:2040 ! drug type

[Term]
id: MI:2102
name: nutraceutical drug
def: "A drug which may also be regarded as a foodstuff." [PMID:14755292]
subset: Drugable
is_a: MI:2040 ! drug type

[Term]
id: MI:2105
name: pka
def: "Negative decimal logarithm of Ka, acid dissociation equilibrium constant for the dissociation of a weak acid." [PMID:14755292]
comment: Quantitative prediction of this parameter is possible.
subset: Drugable
is_a: MI:0640 ! parameter type

[Term]
id: MI:2106
name: degree of ionisation ph 7.4
def: "The degree of ionization refers to the proportion of neutral particles such as those in a gas or aqueous solution, that are ionized into charged particles. A low degree of ionization is sometimes called partially ionized, and a very high degree of ionization as fully ionized. This measurment is performed at pH 7.4" [PMID:14755292]
comment: Quantitative prediction of this parameter is possible.
subset: Drugable
synonym: "ionisation ph 7.4" EXACT PSI-MI-short []
is_a: MI:0640 ! parameter type

[Term]
id: MI:2107
name: logd
def: "The LogD is the ratio of the equilibrium concentrations of all species (unionized and ionized) of a molecule in octanol to same species in the water phase at a given temperature, normally 25 C. It differs from LogP in that ionized species are considered as well as the neutral form of the molecule.pH 7.4" [PMID:14755292]
comment: Quantitative prediction of this parameter is possible.
subset: Drugable
is_a: MI:0640 ! parameter type

[Term]
id: MI:2108
name: solubility ph 7.4
def: "Solubility pH 7.4" [PMID:14755292]
comment: Quantitative prediction of this parameter is possible.
subset: Drugable
is_a: MI:2064 ! solubility

[Term]
id: MI:2109
name: solubility in dmso
def: "Solubility in DMSO" [PMID:14755292]
subset: Drugable
is_a: MI:2064 ! solubility

[Term]
id: MI:2111
name: diffusion coefficient
def: "Diffusion coefficient D is proportional to the velocity of the diffusing particles, which depends on the temperature, viscosity of the fluid and the size of the particles according to the Stokes-Einstein relation. In dilute aqueous solutions the diffusion coefficients of most ions are similar and have values that at room temperature are in the range of 0.6x10-9 to 2x10-9 m2/s. For biological molecules the diffusion coefficients normally range from 10-11 to 10-10 m2/s." [PMID:14755292]
comment: Quantitative prediction of this parameter is possible.
subset: Drugable
synonym: "diffusion coeff" EXACT PSI-MI-short []
is_a: MI:0640 ! parameter type

[Term]
id: MI:2112
name: chemical stability at pH 2
def: "Chemical stability at pH 2" [PMID:14755292]
comment: Qualitative prediction of this parameter is possible.
subset: Drugable
synonym: "chem stab ph 2" EXACT PSI-MI-short []
is_a: MI:2055 ! chemical stability

[Term]
id: MI:2113
name: dissolution profile
def: "The rate of dissolution is a key target for controlling the duration of a drug's effect, and as such, several dosage forms that contain the same active ingredient may be available, differing only in the rate of dissolution. If a drug is supplied in a form that is not readily dissolved, the drug may be released more gradually over time with a longer duration of action. Having a longer duration of action may improve compliance since the medication will not have to be taken as often. Additionally, slow-release dosage forms may maintain concentrations within an acceptable therapeutic range over a long period of time, as opposed to quick-release dosage forms which may result in sharper peaks and troughs in serum concentrations." [PMID:14755292]
comment: The prediction of the value for this paramter is currently not possible.
subset: Drugable
is_a: MI:0640 ! parameter type

[Term]
id: MI:2115
name: pharmacokinetics attribute name
def: "Determination of the fate of substances administered externally to a living organism i.e. the study of what the body does to a drug." [PMID:14755292]
subset: Drugable
is_a: MI:2086 ! physicochemical attribute name

[Term]
id: MI:2116
name: cell permeability
def: "The permitting or activating of the passage of substances into, out of, or through cells." [PMID:14755292]
comment: Quantitative prediction of this parameter is possible.
subset: Drugable
is_a: MI:0640 ! parameter type

[Term]
id: MI:2118
name: volume of distribution
def: "The Volume of Distribution is the amount of drug in the body divided by the concentration in the blood. Drugs that are highly lipid soluble have a very high volume of distribution (500 litres). Drugs which are lipid insoluble remain in the blood, and have a low Vd." [PMID:14755292]
comment: Quantitative prediction of this parameter is possible.
subset: Drugable
synonym: "distribution volume" EXACT PSI-MI-alternate []
synonym: "vd" EXACT PSI-MI-alternate []
synonym: "vol of distribution" EXACT PSI-MI-short []
is_a: MI:0640 ! parameter type

[Term]
id: MI:2120
name: tissue distribution
def: "Accumulation of a drug or chemical substance in various organs (including those not relevant to its pharmacologic or therapeutic action). This distribution depends on the blood flow or perfusion rate of the organ, the ability of the drug to penetrate organ membranes, tissue specificity, protein binding. The distribution is usually expressed as tissue to plasma ratios." [PMID:14755292]
comment: Algorithms have been published to predict the value of this parameter but the quality of the prediction is unknown.
subset: Drugable
is_a: MI:0640 ! parameter type

[Term]
id: MI:2121
name: transporter binding
def: "Substrate of a carrier system allowing the intake of an agent into an organ or part of body." [PMID:14755292]
comment: The prediction of the value for this parameter is currently not possible.
subset: Drugable
is_a: MI:2115 ! pharmacokinetics attribute name

[Term]
id: MI:2122
name: clearance
def: "The ratio of excretion is or measure of the speed at which a constituent is lost from the body." [PMID:14755292]
subset: Drugable
is_a: MI:0640 ! parameter type

[Term]
id: MI:2123
name: renal clearance
def: "The renal clearance ratio or fractional excretion is a measure of the speed at which a constituent of urine passes through the kidneys, in this context the rate at which a pharmacological agent is lost from the body via urine." [PMID:14755292]
comment: Algorithms have been published to predict the value of this parameter but the quality of the prediction is unknown.
subset: Drugable
is_a: MI:0640 ! parameter type

[Term]
id: MI:2124
name: total clearance
def: "The clearance of a drug is the volume of plasma from which the drug is completely removed per unit time. The amount eliminated is proportional to the concentration of the drug in the blood." [PMID:14755292]
comment: The prediction of the value for this paramter is currently not possible.
subset: Drugable
synonym: "cl" EXACT PSI-MI-alternate []
synonym: "clearance" EXACT PSI-MI-alternate []
is_a: MI:0640 ! parameter type

[Term]
id: MI:2125
name: maximum absorbable dose
def: "The Maximum Absorbable Dose (MAD) represents the amount of drug that can permeate across a barrier." [PMID:8987073]
comment: Quantitative prediction of this parameter is possible.
subset: Drugable
synonym: "mad" EXACT PSI-MI-short []
is_a: MI:0640 ! parameter type

[Term]
id: MI:2126
name: paracellular absorption
def: "Water soluble compounds are absorbed in the small intestine mainly via two pathways, the transcellular and the paracellular pathways. The paracellular absorption involves movement of solutes through a restrictive aqueous channel in the tight junctions of adjoining cells  by diffusion." [PMID:14755292]
comment: Quantitative prediction of this parameter is possible.
subset: Drugable
synonym: "paracellular absorp" EXACT PSI-MI-short []
is_a: MI:0640 ! parameter type

[Term]
id: MI:2127
name: tmax/cmax
def: "Ratio between the time value at Cmax (maximum concentration) in a dose response curve, and the Cmax value itself." [PMID:14755292]
comment: The prediction of the value for this paramter is currently not possible.
subset: Drugable
is_a: MI:0640 ! parameter type

[Term]
id: MI:2128
name: ABCB1 transporter substrate
def: "Substrate for the representitive member of the ABC transprorter family ABCB1 (MDR1, pgy1, P08183). ABC transporters preventing uptake or facilitating clearance of toxic substances, playing an important role in drug excretion through the bile." [PMID:14755292]
comment: Algorithms have been published to predict the value of this parameter but the quality of the prediction is unknown.
subset: Drugable
synonym: "abcb1 substrate" EXACT PSI-MI-short []
synonym: "pgp(mdr1) substrate " EXACT PSI-MI-alternate []
is_a: MI:2121 ! transporter binding

[Term]
id: MI:2129
name: bile transporter substrate
def: "Substrate of the bile acid carrier system in both the intestinal tract and the liver. System catalyses of the transfer of bile acid from one side of the membrane to the other. Bile acids are any of a group of steroid carboxylic acids occurring in bile, where they are present as the sodium salts of their amides with glycine or taurine." [PMID:14755292]
comment: The prediction of the value for this paramater is currently not possible.
subset: Drugable
synonym: "bile trans substrate" EXACT PSI-MI-short []
is_a: MI:2121 ! transporter binding

[Term]
id: MI:2130
name: cyp-450 inhibition
def: "Inhibitor of one or more of the family of cytochrome p450 enzymes, probably the most important elements of oxidative metabolism of exogenous compounds." [PMID:14755292]
comment: Algorithms have been published to predict the value of this parameter but the quality of the prediction is unknown.
subset: Drugable
synonym: "cyp-450 inhibition" EXACT PSI-MI-alternate []
synonym: "Cytochrome P450 inhibition" EXACT PSI-MI-alternate []
is_a: MI:2135 ! toxicity attribute name

[Term]
id: MI:2131
name: metabolite identification
def: "Identification of the breakdown products of a substance, either through chemical instability or the actions of enzymes within the body" [PMID:14755292]
comment: Algorithms have been published to predict the value of this parameter but the quality of the prediction is unknown.
subset: Drugable
synonym: "metabolite identific" EXACT PSI-MI-short []
is_a: MI:2115 ! pharmacokinetics attribute name

[Term]
id: MI:2132
name: gsh adducts
def: "Derivative molecule which has formed from a reaction with glutathione." [PMID:14755292]
comment: Algorithms have been published to predict the value of this parameter but the quality of the prediction is unknown.
subset: Drugable
is_a: MI:2115 ! pharmacokinetics attribute name

[Term]
id: MI:2133
name: neutralization by glucuronidation or sulfatation
def: "Neutralization of a compound occuring via its glucuronidation or sulfatation." [PMID:14755292]
comment: Quantitative prediction of this parameter is possible.
subset: Drugable
synonym: "neutraliz gluc/sulf" EXACT PSI-MI-short []
is_a: MI:2048 ! drug biotransformation

[Term]
id: MI:2135
name: toxicity attribute name
def: "The mechanism by which a substance can harm humans or animals." [PMID:14755292]
subset: Drugable
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2136
name: herg binding
def: "Binds to the hERG (human Ether-a-go-go Related Gene) (Q12809) which encodes the Kv11.1 potassium ion channel responsible for the repolarizing IKr current in the cardiac action potential." [PMID:14755292]
comment: Algorithms have been published to predict the value of this parameter but the quality of the prediction is unknown.
subset: Drugable
is_a: MI:2135 ! toxicity attribute name

[Term]
id: MI:2137
name: genotoxicity
def: "Tendency of a bioactive entity to induce damage at the level of the gene." [PMID:14755292]
comment: Algorithms have been published to predict the value of this parameter but the quality of the prediction is unknown.
subset: Drugable
is_a: MI:2135 ! toxicity attribute name

[Term]
id: MI:2138
name: mutagenicity
def: "Tendency of a bioactive entity to induce genetic mutations at the nucleotide level e.g. substitution of nucleotide base-pairs and insertions and deletions of one or more nucleotides in DNA sequences." [PMID:14755292]
comment: Algorithms have been published to predict the value of this parameter but the quality of the prediction is unknown.
subset: Drugable
is_a: MI:2135 ! toxicity attribute name

[Term]
id: MI:2139
name: carcinogenicity
def: "Tendency of a bioactive entity to induce a cancer." [PMID:14755292]
comment: Algorithms have been published to predict the value of this parameter but the quality of the prediction is unknown.
subset: Drugable
synonym: "cancerogenicity" EXACT PSI-MI-alternate []
is_a: MI:2135 ! toxicity attribute name

[Term]
id: MI:2140
name: chromosome damage
def: "Tendency of a bioactive entity to induce damage at the level of the chromosome e.g. induce a change in chromosome structure and number." [PMID:14755292]
comment: Algorithms have been published to predict the value of this parameter but the quality of the prediction is unknown.
subset: Drugable
is_a: MI:2135 ! toxicity attribute name

[Term]
id: MI:2141
name: hepatotoxicity
def: "Tendency of a bioactive entity to affect liver function." [PMID:14755292]
comment: Algorithms have been published to predict the value of this parameter but the quality of the prediction is unknown.
subset: Drugable
is_a: MI:2135 ! toxicity attribute name

[Term]
id: MI:2142
name: phospholipidosis
def: "Causes excess phospholipids to accumulate within cells." [PMID:14755292]
comment: Algorithms have been published to predict the value of this parameter but the quality of the prediction is unknown.
subset: Drugable
is_a: MI:2135 ! toxicity attribute name

[Term]
id: MI:2145
name: solubility ph 6.5
def: "Solubility pH  6.5." [PMID:14755292]
comment: Quantitative prediction of this parameter is possible.
subset: Drugable
is_a: MI:2064 ! solubility

[Term]
id: MI:2146
name: solubility ph 2.0
def: "Solubility pH 2.0" [PMID:14755292]
comment: Quantitative prediction of this parameter is possible.
subset: Drugable
synonym: "solubility ph2.0" EXACT PSI-MI-alternate []
is_a: MI:2064 ! solubility

[Term]
id: MI:s2147
name: chemical stability at pH 7.4
def: "Chemical stabilityat at pH 7.4" [PMID:14755292]
comment: Qualitative prediction of this parameter is possible.
subset: Drugable
synonym: "chem stab ph 7.4" EXACT PSI-MI-short []
is_a: MI:2055 ! chemical stability

[Term]
id: MI:2148
name: investigational drug
def: "A drug currently under clinical development." [PMID:14755292]
comment: Intact.
subset: Drugable
is_a: MI:2040 ! drug type

[Term]
id: MI:2149
name: withdrawn drug
def: "A drug for which the licencing for prescriptive use has been withdrawn." [PMID:14755292]
comment: Intact.
subset: Drugable
is_a: MI:2040 ! drug type

[Term]
id: MI:2150
name: illicit drug
def: "A drug which has not been approved for sale, a drug taken for recreational purposes or a licensed drug sold without a prescription." [PMID:14755292]
subset: Drugable
is_a: MI:2040 ! drug type

[Term]
id: MI:2151
name: other drug interaction
def: "Effect of additional drug treatments on a given drug action." [PMID:14755292]
subset: Drugable
synonym: "drug interaction" EXACT PSI-MI-short []
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2152
name: food interaction
def: "Effect of food ingestion on a given drug treatment." [PMID:14755292]
comment: IntAct MeSH term or SNOWMAN.
subset: Drugable
is_a: MI:2089 ! bioactive entity attribute name

[Term]
id: MI:2153
name: pdr health
def: "Hyperlink to PDRhealth entry for the given drug (if it exists)" [PMID:14755292]
subset: Drugable
synonym: "PDRhealth" EXACT PSI-MI-alternate []
is_a: MI:2054 ! bioactive entity reference

[Term]
id: MI:2154
name: wikipedia
def: "Hyperlink to wikipedia entry for the given drug (if it exists)" [PMID:14755292]
subset: Drugable
is_a: MI:2054 ! bioactive entity reference

[Term]
id: MI:2155
name: average molecular weight
def: "Molecular weight in g/mol, determined from molecular formula or sequence." [PMID:14755292]
subset: Drugable
synonym: "avrg mol weight" EXACT PSI-MI-short []
is_a: MI:2025 ! molecular weight

[Term]
id: MI:2156
name: monoisotopic molecular weight
def: "Molecular weight in g/mol, determined from molecular formula or sequence." [PMID:14755292]
subset: Drugable
synonym: "monoisotopic mol wgt" EXACT PSI-MI-short []
is_a: MI:2025 ! molecular weight

[Term]
id: MI:2157
name: experimental water solubility
def: "Water solubility in mg/mL or g/L." [PMID:14755292]
subset: Drugable
synonym: "exp h2o solubilty" EXACT PSI-MI-short []
synonym: "experimental h2o solubility" EXACT PSI-MI-alternate []
is_a: MI:2027 ! water solubility
is_a: MI:2161 ! experimental logs

[Term]
id: MI:2158
name: predicted water solubility
def: "Water solubility in mg/mL or g/L" [PMID:14755292]
subset: Drugable
synonym: "predicted h2o solub" EXACT PSI-MI-short []
synonym: "predicted h2o solubility" EXACT PSI-MI-alternate []
is_a: MI:2027 ! water solubility

[Term]
id: MI:2160
name: logs
def: "Solubility of a molecule in a given solvant." [PMID:14755292]
subset: Drugable
synonym: "logS" EXACT PSI-MI-alternate []
is_a: MI:0640 ! parameter type

[Term]
id: MI:2161
name: experimental logs
def: "Experimental derived value for the solubility of a molecule in a given solvant." [PMID:14755292]
comment: Quantitative prediction of this parameter is possible.
subset: Drugable
synonym: "experimental logS" EXACT PSI-MI-alternate []
is_a: MI:2160 ! logs

[Term]
id: MI:2162
name: experimental CaCO2 permeability
def: "Experimentally derived value for ability of a  compound to cross epithelial and endothelial cell barriers Using the CaCo2 cell line derived from a human colorectal adenocarcinoma. Used as an in vitro permeability models to predict human intestinal absorption" [PMID:14755292]
comment: Quantitative prediction of this parameter is possible.
subset: Drugable
synonym: "caco2 permeability" EXACT PSI-MI-short []
is_a: MI:0640 ! parameter type

[Term]
id: MI:2163
name: by homology
def: "Reference assigned to a molecule by sequence homology with another similar sequence." [PMID:14755292]
subset: Drugable
is_a: MI:0353 ! cross-reference type

[Term]
id: MI:2164
name: mind
def: "The Membrane-based Interactome Network Database (MIND) holds a network of over 25,000 putative PPI (PPPI) obtained by screening of over 3,000 unique Arabidopsis ORFs for pair-wise interactions using the yeast mating-based split-ubiquitin system (mbSUS). http://cas-biodb.cas.unt.edu/project/mind/index.php" [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0461 ! interaction database
created_by: orchard
creation_date: 2013-02-26T12:27:35Z

[Term]
id: MI:2165
name: bar
def: "The Arabidopsis Interactions Viewer of BAR (the Bio-Array Resource for plant biology) queries a database of 70944 predicted and 28556 confirmed Arabidopsis interacting proteins. The predicted interactions (interologs) were generated by Drs Matt Geisler and Jane Geisler-Lee at the Southern Illinois University. Their current version is Interactome 2.0. The confirmed Arabidopsis interacting proteins come from BIND, the Biomolecular Interaction Network Database, from high-density Arabidopsis protein microarrays, from Braun et al.'s Arabidopsis Interactome 2011 , from Wolf Frommer's Membrane protein INteractome Database MIND, from Etsuko Moryiama's Arabidopsis G-signaling Interactome Database, and over 1190 other literature sources. The interactions in BIND were identified using several different methods, such as yeast two hybrid screens, but also via traditional biochemical methods. http://bar.utoronto.ca/interactions/cgi-bin/arabidopsis_interactions_viewer.cgi\" [PMID:15960624]" [PMID:15960624]
subset: PSI-MI_slim
synonym: "bar-arabidopsis interactions viewer" EXACT []
is_a: MI:0461 ! interaction database
created_by: orchard
creation_date: 2013-02-26T12:49:13Z

[Term]
id: MI:2166
name: ai
def: "The Arabidopsis Interactome network map is a proteome-wide binary protein-protein interaction map for the interactome network of the plant Arabidopsis thaliana containing ~6,200 highly reliable interactions between ~2,700 proteins.\n http://interactome.dfci.harvard.edu/A_thaliana/index.php" [PMID:21798944]
subset: PSI-MI_slim
synonym: "AI" EXACT []
is_a: MI:0461 ! interaction database
created_by: orchard
creation_date: 2013-02-26T12:54:32Z

[Term]
id: MI:2167
name: kinetic exclusion assay
def: "In the kinetic exclusion assay one of the interaction components (bait) is immobilized to a solid phase (beads) and is used to capture the prey from a solution containing free molecules of both the prey and the bait that has reached kinetic equilibrium. This mixture of free components is only allowed to contact the immobilized bait for a very short time, so bait-prey complexes do not dissociate. The immobilized bait captures a small percentage of the prey, which is proportional to the free prey concentration, and the captured prey is detected usually via a fluorescent tag." [PMID:15674023]
subset: PSI-MI_slim
synonym: "kinetic exclusion" EXACT PSI-MI-short []
synonym: "kinexa" EXACT PSI-MI-alternate []
is_a: MI:0892 ! solid phase assay
created_by: ppm
creation_date: 2015-04-27T15:51:46Z

[Term]
id: MI:2168
name: conditional site labelling
def: "The interaction is detected through labelling of a specific site -which can be an active site- that is only accessible once the participants are interacting. This conditional site is then marked with a chemical label for detection." [PMID:19416890]
subset: PSI-MI_slim
synonym: "active site labelling" RELATED []
is_a: MI:1313 ! proximity labelling technology
created_by: ppm
creation_date: 2015-04-29T10:19:28Z

[Term]
id: MI:2169
name: luminiscence technology
def: "Techniques based upon the measurement of the emission of one or more photons in a bioluminescent reaction. Such reactions are typically catalyzed by two groups of enzymes: photoproteins and luciferases. Photoproteins emit light in proportion to the concentration of the protein itself, while in a luciferin-luciferase reaction, photon emission is directly proportional to the amount of luciferin." [PMID:24166364]
is_a: MI:0013 ! biophysical
created_by: ppm
creation_date: 2015-04-29T11:50:41Z

[Term]
id: MI:2170
name: bimolecular luminiscence complementation
def: "The bimolecular luminescence complementation (BiLC) is an assay for determination of protein interactions and/or their location in living cells. This approach is based on complementation between two fragments of a bioluminescent enzyme such as luciferin or aequorin. Interactions between proteins fused to each fragment bring the fragments together resulting in the reconstitution of a fully functional bioluminescent enzyme that can be identified through microscopy or luminescence detection." [PMID:25859972]
synonym: "bilc" EXACT PSI-MI-short []
synonym: "bioluminescence complementation" EXACT PSI-MI-alternate []
synonym: "bioluminescence complementation assay" EXACT PSI-MI-alternate []
synonym: "luminescence complementation assay" EXACT PSI-MI-alternate []
synonym: "luminiscence complementation" EXACT PSI-MI-alternate []
synonym: "split-luciferase complementation" RELATED []
synonym: "split-luciferase complementation assay" RELATED []
is_a: MI:2169 ! luminiscence technology
created_by: ppm
creation_date: 2015-04-29T12:03:27Z

[Term]
id: MI:2171
name: complemented donor-acceptor resonance energy transfer
def: "This technology is based on quantifying the BRET between a pair of participants bearing complementation tags and a participant tagged with a bioluminescent enzyme or a fluorescent tag. The tags held by the pair of participants are complementary halves of either a fluorescent tag (N- and C- fragments of the Venus fluorescent protein, for example) or a bioluminescent enzyme (N- and C- fragments of Renilla luciferase, for example). Interaction between the pair of participants leads to reconstruction of the bioluminescent enzyme/fluorescent protein, which can then emit/accept photons that are accepted/emitted by the tag in the third participant, generating the signal used to detect the interaction. The signals emitted by the bioluminescent enzyme and the fluorescent tag have different wavelengths, so they can be distinguished." [PMID:21785426, PMID:25706338]
subset: PSI-MI_slim
synonym: "bret complementation" EXACT PSI-MI-alternate []
synonym: "bret complementation assay" EXACT PSI-MI-alternate []
synonym: "copa-ret" EXACT PSI-MI-short []
is_a: MI:0051 ! fluorescence technology
is_a: MI:2169 ! luminiscence technology
created_by: ppm
creation_date: 2015-04-29T13:25:55Z

[Term]
id: MI:2172
name: aspgd
def: "AspGD is an organized collection of genetic and molecular biological information about the filamentous fungi of the genus Aspergillus. Among its many species, the genus contains an excellent model organism (A. nidulans, or its teleomorph Emericella nidulans), an important pathogen of the immunocompromised (A. fumigatus), an agriculturally important toxin producer (A. flavus), and two species used in industrial processes (A. niger and A. oryzae). AspGD contains information about genes and proteins of multiple Aspergillus species; descriptions and classifications of their biological roles, molecular functions, and subcellular localizations; gene, protein, and chromosome sequence information; tools for analysis and comparison of sequences; and links to literature information; as well as a multispecies comparative genomics browser tool (Sybil) for exploration of orthology and synteny across multiple sequenced Aspergillus species.\nwww.aspergillusgenome.org/" [PMID:24194595]
synonym: "Aspergillus Genome Database" EXACT PSI-MI-alternate []
synonym: "aspgd" EXACT PSI-MI-short []
synonym: "AspGD" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "ASPL[0-9]{10}"
xref: search-url: "http://www.aspergillusgenome.org/cgi-bin/locus.pl?dbid=${ac}"
is_a: MI:0461 ! interaction database
created_by: ppm
creation_date: 2015-05-05T14:28:59Z

[Term]
id: MI:2173
name: cgd
def: "Candida Genome Database is a resource for genomic sequence data and gene and protein information for Candida albicans and related species. CGD is based on the Saccharomyces Genome Database and is funded by the National Institute of Dental & Craniofacial Research at the US National Institutes of Health.\nwww.candidagenome.org/" [PMID:22064862]
synonym: "Candida Genome Database" EXACT PSI-MI-alternate []
synonym: "cgd" EXACT PSI-MI-short []
synonym: "CGD" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "(CAL|CAF)[0-9]{7}"
xref: search-url: "http://www.candidagenome.org/cgi-bin/locus.pl?dbid=${ac}"
is_a: MI:0461 ! interaction database
created_by: ppm
creation_date: 2015-05-05T14:41:00Z

[Term]
id: MI:2174
name: ecoliwiki
def: "Community annotation portal associated with PortEco (formerly EcoliHub, http://porteco.org/). It aims to generate community-based pages about\neverything related to non-pathogenic E. coli, its phages, plasmids, and\nmobile genetic elements.\nhttp://ecoliwiki.net/colipedia/" [PMID:22064863]
synonym: "ecoliwiki" EXACT PSI-MI-short []
synonym: "EcoliWiki" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "[A-Za-z]{3,4}"
xref: search-url: "http://ecoliwiki.net/colipedia/${ac}"
is_a: MI:0461 ! interaction database
created_by: ppm
creation_date: 2015-05-05T14:55:06Z

[Term]
id: MI:2175
name: genedb
def: "The GeneDB project is a core part of the Sanger Institute's Pathogen Genomics activities. Its primary goals are:\n-to provide reliable access to the latest sequence data and annotation/curation for the whole range of organisms sequenced by the Pathogen group.\n-to develop the website and other tools to aid the community in accessing and obtaining the maximum value from these data.\nGeneDB currently provides access to more than 40 genomes, at various stages of completion, from early access to partial genomes with automatic annotation through to complete genomes with extensive manual curation.\nwww.genedb.org" [PMID:22116062]
synonym: "GeneDB" EXACT PSI-MI-alternate []
synonym: "genedb" EXACT PSI-MI-short []
xref: id-validation-regexp: "((LmjF|LinJ|LmxM)\\.[0-9]{2}\\.[0-9]{4})|(PF3D7_[0-9]{7})|(Tb[0-9]+\\.[A-Za-z0-9]+\\.[0-9]+)|(TcCLB\\.[0-9]{6}\\.[0-9]+)"
xref: search-url: "www.genedb.org/gene/${ac}"
is_a: MI:0461 ! interaction database
created_by: ppm
creation_date: 2015-05-05T15:04:16Z

[Term]
id: MI:2176
name: gramene
def: "Gramene is a curated, open-source, integrated data resource for comparative functional genomics in crops and model plant species. Gramene currently hosts annotated whole genomes in over two dozen plant species and partial assemblies for almost a dozen wild rice species in the Ensembl browser, genetic and physical maps with genes, ESTs and QTLs locations, genetic diversity data sets, structure-function analysis of proteins, plant pathways databases (BioCyc and Plant Reactome platforms), and descriptions of phenotypic traits and mutations.\nhttp://www.gramene.org" [PMID:24217918]
synonym: "gramene" EXACT PSI-MI-short []
synonym: "Gramene" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "[A-Z][0-9][A-Z0-9]{3}[0-9]"
xref: search-url: "http://tools.gramene.org/search?query=${ac}"
is_a: MI:0461 ! interaction database
created_by: ppm
creation_date: 2015-05-05T15:12:03Z

[Term]
id: MI:2177
name: pombase
def: "PomBase is a comprehensive database for the fission yeast Schizosaccharomyces pombe, providing structural and functional annotation, literature curation and access to large-scale data sets. \nwww.pombase.org" [PMID:22039153]
synonym: "pombase" EXACT PSI-MI-short []
synonym: "PomBase" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "S\\w+(\\.)?\\w+(\\.)?"
xref: search-url: "www.pombase.org/spombe/result/${ac}"
is_a: MI:0461 ! interaction database
created_by: ppm
creation_date: 2015-05-05T15:17:42Z

[Term]
id: MI:2178
name: agi_locuscode
def: "The Arabidopsis Genome Initiative comprises TAIR, TIGR and MIPS." []
synonym: "agi_locuscode" EXACT PSI-MI-short []
synonym: "AGI_LocusCode" EXACT PSI-MI-alternate []
synonym: "Arabidopsis Genome Initiative" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "A[Tt][MmCc0-5][Gg][0-9]{5}(\\.[0-9]{1})?"
xref: search-url: "http://arabidopsis.org/servlets/TairObject?type=locus&name=${ac}"
is_a: MI:0461 ! interaction database
created_by: ppm
creation_date: 2015-05-05T16:12:18Z

[Term]
id: MI:2179
name: subset
def: "Reference to the corresponding object in another database. It implies the object is part of a cross-referenced entity (usually a complex)." [PMID:14755292]
subset: PSI-MI_slim
synonym: "part of" EXACT PSI-MI-alternate []
synonym: "subset" EXACT PSI-MI-short []
is_a: MI:0353 ! cross-reference type
created_by: ppm
creation_date: 2015-05-11T09:59:36Z

[Term]
id: MI:2180
name: agbase
def: "AgBase is a curated, open-source, Web-accessible resource for functional analysis of agricultural plant and animal gene products. Their long-term goal is to serve the needs of the agricultural research communities by facilitating post-genome biology for agriculture researchers and for those researchers primarily using agricultural species as biomedical models. They use the Gene Ontology for functional annotation.\nhttp://www.agbase.msstate.edu/" [PMID:21075795]
subset: PSI-MI_slim
synonym: "agbase" EXACT PSI-MI-short []
synonym: "AgBase" EXACT PSI-MI-alternate []
xref: search-url: "http://www.agbase.msstate.edu/cgi-bin/getEntry.pl?db_pick=[ChickGO/MaizeGO]&uid=${ac}"
is_a: MI:0461 ! interaction database
created_by: ppm
creation_date: 2015-05-11T10:23:14Z

[Term]
id: MI:2181
name: cacao
def: "The Community Assessment of Community Annotation with Ontologies (CACAO) is a project to do large-scale manual community annotation of gene function using the Gene Ontology as a multi-institution student competition.\nhttp://gowiki.tamu.edu/wiki/index.php/Category:CACAO" []
subset: PSI-MI_slim
synonym: "cacao" EXACT PSI-MI-short []
synonym: "CACAO" EXACT PSI-MI-alternate []
synonym: "Community Assessment of Community Annotation with Ontologies" EXACT PSI-MI-alternate []
xref: search-url: "http://gowiki.tamu.edu/wiki/index.php/${ac}"
is_a: MI:0461 ! interaction database
created_by: ppm
creation_date: 2015-05-11T10:51:57Z

[Term]
id: MI:2182
name: dflat
def: "Database dedicated to annotating gene function related to human fetal development using the Gene Ontology for functional annotation.\nhttp://bcb.cs.tufts.edu/dflat/" []
subset: PSI-MI_slim
synonym: "Developmental FunctionaL Annotation at Tufts" EXACT PSI-MI-alternate []
synonym: "dflat" EXACT PSI-MI-short []
synonym: "DFLAT" EXACT PSI-MI-alternate []
is_a: MI:0473 ! participant database
created_by: ppm
creation_date: 2015-05-11T11:01:34Z

[Term]
id: MI:2183
name: go_central
def: "The GO Consortium coordinated an effort to maximize and optimize GO annotations for a large and representative set of key genomes, known as 'reference genomes'. The Reference Genome Annotation Project aimed to completely annotate twelve reference genomes, producing a resource that may effectively seed automatic annotation efforts of other genomes. This resource represents manual annotation from PAINT curators into the UniProt Protein2GO curation tool.\nhttp://www.geneontology.org/GO.refgenome.shtml" [PMID:19578431]
subset: PSI-MI_slim
synonym: "GO central" EXACT PSI-MI-alternate []
synonym: "go_central" EXACT PSI-MI-short []
synonym: "GO_central" EXACT PSI-MI-alternate []
synonym: "The Reference Genome Annotation Project" EXACT PSI-MI-alternate []
is_a: MI:0448 ! gene ontology
created_by: ppm
creation_date: 2015-05-11T11:10:30Z

[Term]
id: MI:2184
name: mtbbase
def: "Collection and Refinement of Physiological Data on Mycobacterium tuberculosis in the form of GO annitations. MTBBASE data has also been rendered as pathway information in Reactome. \nhttp://www.ark.in-berlin.de/Site/MTBbase.html\nhttp://www.reactome.org/cgi-bin/eventbrowser_st_id?ST_ID=REACT_121237.1" []
subset: PSI-MI_slim
synonym: "MTBBASE" EXACT PSI-MI-alternate []
synonym: "mtbbase" EXACT PSI-MI-short []
is_a: MI:0461 ! interaction database
created_by: ppm
creation_date: 2015-05-11T11:34:15Z

[Term]
id: MI:2185
name: parkinsonsuk-ucl
def: "The Parkinson's UK Gene Ontology Project represents a collaboration between University College London and the European Bioinformatics Institute (EBI), funded by Parkinson's UK. This annotation group is a member of the IMEx Consortium.\nhttp://www.ucl.ac.uk/functional-gene-annotation/neurological" []
subset: PSI-MI_slim
synonym: "Parkinson-UCL" EXACT PSI-MI-alternate []
synonym: "Parkinsons Disease Gene Ontology Initiative" EXACT PSI-MI-alternate []
synonym: "ParkinsonsUK-UCL" EXACT PSI-MI-alternate []
synonym: "parkinsonsuk-ucl" EXACT PSI-MI-short []
is_a: MI:0461 ! interaction database
created_by: ppm
creation_date: 2015-05-11T11:45:34Z

[Term]
id: MI:2186
name: alut
def: "The Alzheimers-University of Toronto project adds functional annotation to Alzheimer's related gene products using the Gene Ontology.\nhttp://www.ims.utoronto.ca/" []
subset: PSI-MI_slim
synonym: "alut" EXACT PSI-MI-short []
synonym: "Alzheimers Project at University of Toronto" EXACT PSI-MI-alternate []
synonym: "Alzheimers University of Toronto" EXACT PSI-MI-alternate []
synonym: "Alzheimers_University_of_Toronto" EXACT PSI-MI-alternate []
is_a: MI:0461 ! interaction database
created_by: ppm
creation_date: 2015-05-11T13:13:02Z

[Term]
id: MI:2187
name: ri
def: "The Roslin Institute uses the Gene Ontology to add functional annotation to different gene products.\nhttp://www.roslin.ac.uk/" []
subset: PSI-MI_slim
synonym: "ri" EXACT PSI-MI-short []
synonym: "RI" EXACT PSI-MI-alternate []
synonym: "Roslin Institute" EXACT PSI-MI-alternate []
synonym: "roslin_institute" EXACT PSI-MI-alternate []
synonym: "Roslin_Institute" EXACT PSI-MI-alternate []
is_a: MI:0461 ! interaction database
created_by: ppm
creation_date: 2015-05-11T13:18:36Z

[Term]
id: MI:2188
name: par-clip
def: "Photoactivatable-Ribonucleoside-Enhanced Crosslinking and Immunoprecipitation (PAR-CLIP) is a biochemical method used for identifying the binding sites of cellular RNA-binding proteins (RBPs) and microRNA-containing ribonucleoprotein complexes (miRNPs). The method relies on the incorporation of photoreactive ribonucleoside analogs, such as 4-thiouridine (4-SU) and 6-thioguanosine (6-SG) into nascent RNA transcripts by living cells. Irradiation of the cells by UV light of 365 nm induces efficient crosslinking of photoreactive nucleoside-labeled cellular RNAs to interacting RBPs. Immunoprecipitation of the RBP of interest is followed by isolation of the crosslinked and coimmunoprecipitated RNA. The isolated RNA is converted into a cDNA library and deep sequenced using next-generation sequencing technology.\nhttp://en.wikipedia.org/wiki/PAR-CLIP" [PMID:20371350, PMID:20644507]
subset: PSI-MI_slim
synonym: "PAR-CLIP" EXACT PSI-MI-alternate []
synonym: "par-clip" EXACT PSI-MI-short []
synonym: "Photoactivatable-Ribonucleoside-Enhanced Crosslinking and Immunoprecipitation" EXACT PSI-MI-alternate []
is_a: MI:2191 ! clip
created_by: ppm
creation_date: 2015-05-11T15:13:05Z

[Term]
id: MI:2189
name: avexis
def: "Low-affinity interaction detection method designed specifically to detect interactions between extracellular proteins. Recombinant soluble fragments of these proteins are produced in a (generally) mammalian expression cell line and secreted into the medium and produced in two forms: a biotinylated bait which can be captured on a streptavidin-coated solid phase suitable for screening, and a pentamerised enzyme-tagged (beta-lactamase) prey. The bait and prey proteins are presented to each other in a binary fashion to detect direct interactions between them, similar to a conventional ELISA. The pentamerisation of the proteins in the prey is achieved through a peptide sequence from the cartilage oligomeric matrix protein (COMP) and increases the local concentration of the ectodomains thereby providing significant avidity gains to enable even very transient interactions to be detected. By normalising the activities of both the bait and prey to predetermined levels prior to screening, interactions having monomeric half-lives of 0.1 sec can be detected with low false positive rates." [pmid:22414956]
synonym: "avexis" EXACT PSI-MI-short []
synonym: "AVidity-based EXtracellular Interaction Screen" EXACT PSI-MI-alternate []
synonym: "avidity-based extracellular interaction screen" EXACT PSI-MI-alternate []
is_a: MI:0892 ! solid phase assay
created_by: ppm
creation_date: 2015-06-01T15:05:13Z

[Term]
id: MI:2190
name: long non-coding ribonucleic acid
def: "Non-protein coding transcripts longer than 200 nucleotides and that can be involved in a number of functions, like transcription, post-translational and epigenetic regulation. Most lncRNAs do not have a known function so far." [PMID:23750541]
synonym: "lncrna" EXACT PSI-MI-short []
synonym: "lncRNA" EXACT PSI-MI-alternate []
synonym: "long non coding ribonucleic acid" EXACT PSI-MI-alternate []
synonym: "long non coding RNA" EXACT PSI-MI-alternate []
synonym: "long non-coding RNA" EXACT PSI-MI-alternate []
is_a: MI:0320 ! ribonucleic acid
created_by: ppm
creation_date: 2015-06-02T11:33:27Z

[Term]
id: MI:2191
name: clip
def: "Combination of cross-linking and co-immunoprecipitation aimed to find protein-RNA interactions. The canonical method uses first a cross-linking procedure over a tissue sample or lysate, and the immunoprecipitated with specific antibodies for the protein of interest. Unspecific proteins are digested via proteinase K treatment. RNA can be then identified via Northern blotting or using RT-PCR and then sequencing of the generated cDNA.\nhttps://en.wikipedia.org/wiki/CLIP" [PMID:14615540]
subset: PSI-MI_slim
synonym: "CLIP" EXACT PSI-MI-alternate []
synonym: "clip" EXACT PSI-MI-short []
synonym: "cross linking immunoprecipitation" EXACT PSI-MI-alternate []
synonym: "cross-linking immunoprecipitation" EXACT PSI-MI-alternate []
is_a: MI:0430 ! nucleic acid uv cross-linking assay
created_by: ppm
creation_date: 2015-06-15T10:17:34Z

[Term]
id: MI:2192
name: clip-seq
def: "This method combines UV cross-linking and immunoprecipitation with high-throughput sequencing to identify binding sites of RNA-binding proteins.\nhttps://en.wikipedia.org/wiki/HITS-CLIP" [PMID:18978773, PMID:21633356]
subset: PSI-MI_slim
synonym: "CLIP-Seq" EXACT PSI-MI-alternate []
synonym: "clip-seq" EXACT PSI-MOD-short []
synonym: "HITS-CLIP" EXACT PSI-MI-alternate []
synonym: "UV cross-linking immunoprecipitation combined with high-throughput sequencing" EXACT PSI-MI-alternate []
is_a: MI:2191 ! clip
created_by: ppm
creation_date: 2015-06-15T10:44:44Z

[Term]
id: MI:2193
name: iclip
def: "iCLIP allows for the stringent purification of UV cross-linked protein-RNA complexes, using immunoprecipitation followed by SDS-PAGE and membrane transfer. The radiolabelled protein-RNA complexes are then excised from the membrane, and treated with proteinase to release the RNA. This leaves one or two amino acids at the RNA cross-link site. The RNA is then reverse transcribed using barcoded primers. Because reverse transcription stops prematurely at the cross-link site, iCLIP allows RNA-protein interaction sites to be identified at high resolution.\nhttps://en.wikipedia.org/wiki/ICLIP" [PMID:20601959]
subset: PSI-MI_slim
synonym: "iclip" EXACT PSI-MI-short []
synonym: "iCLIP" EXACT PSI-MI-alternate []
synonym: "individual-nucleotide resolution cross-linking and immunoprecipitation" EXACT PSI-MI-alternate []
is_a: MI:2191 ! clip
created_by: ppm
creation_date: 2015-06-15T11:17:22Z

[Term]
id: MI:2194
name: crac
def: "Combination of UV cross-linking and affinity purification where the protein of interest bears a tag used for pull-down or immunoprecipitation. As in CLIP, unspecific proteins are digested via proteinase K treatment and RNAs are tagged with oligonucleotide linkers. RNA can be then identified via Northern blotting or using RT-PCR and then sequencing of the generated cDNA." [PMID:19482942]
synonym: "crac" EXACT PSI-MI-short []
synonym: "CRAC" EXACT PSI-MI-alternate []
synonym: "cross-linking and analysis of cDNAs" EXACT PSI-MI-alternate []
is_a: MI:0430 ! nucleic acid uv cross-linking assay
created_by: ppm
creation_date: 2015-06-15T11:26:33Z

[Term]
id: MI:2195
name: clash
def: "This method is a variation of CRAC where after combined cross-linking and affinity purification of protein-RNA complexes, RNA-RNA interactions are specifically detected. Base-paired RNA molecules can be linked together while tagging RNA with oligonucleotides, generating chimeric RNAs that allow identification of RNA-RNA pairs." [PMID:21610164]
subset: PSI-MI_slim
synonym: "clash" EXACT PSI-MI-short []
synonym: "CLASH" EXACT PSI-MI-alternate []
synonym: "cross-linking, ligation, and sequencing of hybrids" EXACT PSI-MI-alternate []
is_a: MI:2194 ! crac
created_by: ppm
creation_date: 2015-06-15T11:45:38Z

[Term]
id: MI:2196
name: quartz crystal microbalance
def: "A method that monitors ligand binding by measuring the change in frequency of a quartz crystal resonator resulting from the addition or removal of a small mass of a ligand specifically binding at the surface of the resonator." [PMID:23504432]
subset: PSI-MI_slim
synonym: "qcm" EXACT PSI-MI-short []
synonym: "QCM" EXACT PSI-MI-alternate []
is_a: MI:0968 ! biosensor
created_by: ppm
creation_date: 2015-07-07T09:46:51Z

[Term]
id: MI:2197
name: probe interaction assay
def: "An assay that uses molecular probes, such as ions, small molecules or antibodies to monitor interactions between biomolecules under study." [PMID:14755292]
subset: PSI-MI_slim
synonym: "probe interaction assay" EXACT PSI-MI-short []
is_a: MI:0401 ! biochemical
created_by: ppm
creation_date: 2015-07-07T10:11:26Z

[Term]
id: MI:2198
name: labelling assay
def: "The interaction is inferred from the effect it exerts on specific chemical labelling of one of the interacting partners." [PMID:14755292]
subset: PSI-MI_slim
synonym: "labelling assay" EXACT PSI-MI-short []
is_a: MI:2197 ! probe interaction assay
created_by: ppm
creation_date: 2015-07-07T10:14:29Z

[Term]
id: MI:2199
name: specific site-labelling technology
def: "The interaction is detected through selective, chemical blockage of a specific site -which can be an active site- that becomes inaccessible once the participants are interacting. The interaction is detected through loss of signal of the chemical label" [PMID:8441405]
subset: PSI-MI_slim
synonym: "site-labelling technology" EXACT PSI-MI-short []
synonym: "specific site-labelling technology" EXACT PSI-MI-alternate []
is_a: MI:2198 ! labelling assay
created_by: ppm
creation_date: 2015-07-07T11:51:57Z

[Term]
id: MI:2200
name: primesdb
def: "PRIMESDB is a systems biology platform that is developed to enable the collection, integration and analysis of state-of-the-art genomics, proteomics and mathematical modelling data being generated by the PRIMES project. PRIMES iinvestigates the role of protein interaction machines in oncogenic signalling with a particular focus on the EGFR network. PRIMESDB provides a centralised knowledgebase and analysis platform for cancer protein interaction networks.\nhttp://primesdb.eu/" [PMID:22453911]
synonym: "primesdb" EXACT PSI-MI-short []
synonym: "PRIMESDB" EXACT PSI-MI-alternate []
is_a: MI:0461 ! interaction database
created_by: ppm
creation_date: 2015-07-13T16:36:21Z

[Term]
id: MI:2201
name: DNA chemical modification
def: "Chemical alterations occurring at the nucleotide level in the specific DNA molecule involved in an interaction. The process can involve covalent modifications (i.e. methylations) or other forms of chemical modification." [PMID:14755292]
subset: PSI-MI_slim
synonym: "dna chemical modification" EXACT PSI-MI-short []
synonym: "DNA chemical modification" EXACT PSI-MI-alternate []
synonym: "DNA epigenetic modification" EXACT PSI-MI-alternate []
is_a: MI:0252 ! biological feature
created_by: ppm
creation_date: 2015-08-11T15:37:49Z

[Term]
id: MI:2202
name: RNA chemical modification
def: "Chemical alterations occurring at the nucleotide level in the specific RNA molecule involved in an interaction. The process can involve covalent modifications (i.e. 2'-O-methylation) or other forms of chemical modification, such as isomerizations (i.e. pseudouridylation)." [PMID:14755292]
subset: PSI-MI_slim
synonym: "post-transcriptional modification" EXACT PSI-MI-alternate []
synonym: "rna chemical modification" EXACT PSI-MI-short []
synonym: "RNA chemical modification" EXACT PSI-MI-alternate []
is_a: MI:0252 ! biological feature
created_by: ppm
creation_date: 2015-08-11T15:55:40Z

[Term]
id: MI:2203
name: primer extension assay
def: "Primer extension can be used to determine the 3' end of a given sequence of RNA. This technique requires a radiolabelled primer which is complementary to a region near the 3' end of the RNA. The primer is allowed to anneal to the RNA and reverse transcriptase is used to synthesize  a strand of DNA from the RNA until it reaches the 5' end of the RNA. By denaturing the hybrid and using the extended primer DNA strand as a marker on an electrophoretic gel, it is possible to determine the transcriptional start site." [PMID:23378648]
subset: PSI-MI_slim
synonym: "primer extension assay" EXACT PSI-MI-short []
is_a: MI:1193 ! partial RNA sequence identification
created_by: ppm
creation_date: 2015-08-11T17:22:38Z

[Term]
id: MI:2204
name: micro rna
def: "A micro RNA (abbreviated miRNA) is a small non-coding RNA molecule (containing about 22 nucleotides) found in plants, animals, and some viruses, which functions in RNA silencing and post-transcriptional regulation of gene expression." [PMID:14744438]
subset: PSI-MI_slim
synonym: "micro RNA" EXACT PSI-MI-alternate []
synonym: "micro-RNA" EXACT PSI-MI-alternate []
synonym: "micro-rna" EXACT PSI-MI-alternate []
synonym: "mirna" EXACT PSI-MI-short []
synonym: "miRNA" EXACT PSI-MI-alternate []
xref: url: "https://en.wikipedia.org/wiki/MicroRNA"
is_a: MI:0320 ! ribonucleic acid
created_by: ppm
creation_date: 2016-01-20T16:25:10Z

[Term]
id: MI:2205
name: pir
def: "The PIR-International Protein Sequence Database (PIR-PSD) was the world's first database of classified and functionally annotated protein sequences that grew out of the Atlas of Protein Sequence and Structure (1965-1978) edited by Margaret Dayhoff. Produced and distributed by the Protein Information Resource in collaboration with MIPS (Munich Information Center for Protein Sequences) and JIPID (Japan International Protein Information Database), PIR-PSD has been the most comprehensive and expertly-curated protein sequence database in the public domain for over 20 years. In 2002, PIR joined EBI (European Bioinformatics Institute) and SIB (Swiss Institute of Bioinformatics) to form the UniProt consortium. PIR-PSD sequences and annotations have been integrated into UniProt Knowledgebase. Bi-directional cross-references between UniProt (UniProt Knowledgebase and/or UniParc) and PIR-PSD are established to allow easy tracking of former PIR-PSD entries. PIR-PSD unique sequences, reference citations, and experimentally-verified data can now be found in the relevant UniProt records. \n\nLegacy data can be found at \nhttp://pir.georgetown.edu/pirwww/dbinfo/pir_psd.shtml" []
subset: PSI-MI_slim
synonym: "pir" EXACT PSI-MI-short []
synonym: "PIR" EXACT PSI-MI-alternate []
synonym: "Protein Information Resource" EXACT PSI-MI-alternate []
is_a: MI:1096 ! protein sequence databases
created_by: ppm
creation_date: 2016-01-20T16:48:10Z

[Term]
id: MI:2206
name: observed nucleic acid chemical modification
def: "Chemical modification observed on a nucleic acid molecule in the context of an interaction. Modifications involving full nucleotide substitutions/deletions are excluded from this definition." [PMID:14755292]
subset: PSI-MI_slim
synonym: "observed na chemical modification" EXACT PSI-MI-alternate []
synonym: "observed nucleic acid chemical modification" EXACT PSI-MI-short []
is_a: MI:0668 ! feature attribute name
created_by: ppm
creation_date: 2016-01-21T14:50:29Z

[Term]
id: MI:2207
name: resulting nucleic acid chemical modification
def: "Chemical modification observed on an RNA molecule resulting subsequently of an interaction. Modifications involving full nucleotide substitutions/deletions are excluded from this definition." [PMID:14755292]
subset: PSI-MI_slim
synonym: "resulting na chemical modification" EXACT PSI-MI-alternate []
synonym: "resulting nucleic acid chemical modification" EXACT PSI-MI-short []
is_a: MI:2206 ! observed nucleic acid chemical modification
created_by: ppm
creation_date: 2016-01-21T15:02:23Z

[Term]
id: MI:2208
name: prerequisite-nucleic acid chemical modification
def: "Chemical modification observed on a nucleic acid molecule required for an interaction to occur. Modifications involving full nucleotide substitutions/deletions are excluded from this definition." [PMID:14755292]
subset: PSI-MI_slim
synonym: "prerequisite-na chemical modification" EXACT PSI-MI-alternate []
synonym: "prerequisite-nucleic acid chemical modification" EXACT PSI-MI-short []
is_a: MI:2206 ! observed nucleic acid chemical modification
created_by: ppm
creation_date: 2016-01-21T15:12:35Z

[Term]
id: MI:2209
name: nucleic acid chemical modification decreasing an interaction
def: "Chemical modification observed on a nucleic acid molecule observed to decrease the strength or rate of an interaction. Modifications involving full nucleotide substitutions/deletions are excluded from this definition." [PMID:14755292]
synonym: "na chemical modification decreasing" EXACT PSI-MI-short []
synonym: "nucleic acid chemical modification decreasing an interaction" EXACT PSI-MI-alternate []
is_a: MI:2206 ! observed nucleic acid chemical modification
created_by: ppm
creation_date: 2016-01-21T15:17:08Z

[Term]
id: MI:2210
name: nucleic acid chemical modification disrupting an interaction
def: "Chemical modification observed on a nucleic acid molecule observed to disrupt an interaction. Modifications involving full nucleotide substitutions/deletions are excluded from this definition." [PMID:14755292]
subset: PSI-MI_slim
synonym: "na chemical modification disrupting" EXACT PSI-MI-short []
synonym: "nucleic acid chemical modification disrupting an interaction" EXACT PSI-MI-alternate []
is_a: MI:2206 ! observed nucleic acid chemical modification
created_by: ppm
creation_date: 2016-01-21T15:18:52Z

[Term]
id: MI:2211
name: nucleic acid chemical modification increasing an interaction
def: "Chemical modification observed on a nucleic acid molecule observed to increase the strength or rate of an interaction. Modifications involving full nucleotide substitutions/deletions are excluded from this definition." [PMID:14755292]
subset: PSI-MI_slim
synonym: "na chemical modification increasing" EXACT PSI-MI-short []
synonym: "nucleic acid chemical modification increasing an interaction" EXACT PSI-MI-alternate []
is_a: MI:2206 ! observed nucleic acid chemical modification
created_by: ppm
creation_date: 2016-01-21T15:25:51Z

[Term]
id: MI:2212
name: proteomexchange
def: "The ProteomeXchange consortium was set up to provide a single point of submission of MS proteomics data to the main existing proteomics repositories, and to encourage the data exchange between them for optimal data dissemination. The data is actually hosted by consortium member databases like PeptideAtlas or PRIDE. \n\nhttp://www.proteomexchange.org" [PMID:25047258]
subset: PSI-MI_slim
synonym: "proteomexchange" EXACT PSI-MI-short []
synonym: "ProteomExchange" EXACT PSI-MI-alternate []
is_a: MI:0737 ! peptide sequence database
created_by: ppm
creation_date: 2016-02-02T13:52:54Z

[Term]
id: MI:2213
name: super-resolution microscopy
def: "Super-resolution microscopy is a form of light microscopy that allows images to be taken with a higher resolution than the diffraction limit. Several different methods can be used to achieve beyond-diffraction limit resolution and these can be broadly divided in two categories: \"true\" super-resolution techniques, which capture information contained in evanescent waves, and \"functional\" super-resolution techniques, which use clever experimental techniques and known limitations on the matter being imaged to reconstruct a super-resolution image." [PMID:14755292]
synonym: "super resolution microscopy" EXACT PSI-MI-alternate []
synonym: "super-resolution microscopy" EXACT PSI-MI-short []
is_a: MI:0428 ! imaging technique
created_by: ppm
creation_date: 2016-02-11T11:10:32Z

[Term]
id: MI:2214
name: signor
def: "SIGNOR, the SIGnaling Network Open Resource, organizes and stores in a structured format signaling information published in the scientific literature. The captured information is stored as binary causative relationships between biological entities and can be represented graphically as activity flow. The signaling information is mapped to the human proteome even if the experimental evidence is based on experiments on mammalian model organisms." [PMID:26467481]
subset: PSI-MI_slim
synonym: "SIGnaling Network Open Resource" EXACT PSI-MI-alternate []
synonym: "signaling network open resource" EXACT PSI-MI-alternate []
synonym: "SIGNOR" EXACT PSI-MI-alternate []
synonym: "signor" EXACT PSI-MI-short []
xref: search-url: "http://signor.uniroma2.it/relation_result.php?id=${ac}"
is_a: MI:1106 ! pathways database
created_by: ppm
creation_date: 2016-03-15T15:31:08Z

[Term]
id: MI:2215
name: barcode fusion genetics two hybrid
def: "This method allows screening of a full matrix of protein pairs in a single multiplexed strain pool. A doubly engineered clone pool is prepared so that each clone bears two distinct DNA barcodes flanked by site specific recombination sequences. Positive bait-prey combinations allow activation of reporter genes and their respective barcodes undergo recombination, creating unique barcode combinations. Recombined barcode tags are then fused, extracted and sequenced for identification of interacting pairs." [PMID:27107012]
synonym: "barcode fusion genetics two hybrid" EXACT PSI-MI-alternate []
synonym: "bfg two hybrid" EXACT PSI-MI-alternate []
synonym: "bfg-2h" EXACT PSI-MI-short []
synonym: "BGF-2h" EXACT PSI-MI-alternate []
is_a: MI:1113 ! two hybrid bait and prey pooling approach
created_by: ppm
creation_date: 2016-05-05T14:33:32Z

[Term]
id: MI:2216
name: deampylation assay
def: "Measurement of de-AMPylation, the removal of a phosphodiester or phosphoramide ester of AMP from Tyr (RESID:AA0203), Lys (RESID:AA0227), Thr (RESID:AA0267), His (RESID:AA0371) and other amino\nacids." [PMID:14755292]
subset: PSI-MI_slim
synonym: "de-ampylation assay" EXACT PSI-MI-alternate []
synonym: "de-AMPylation assay" EXACT PSI-MI-alternate []
synonym: "deampylation assay" EXACT PSI-MI-short []
synonym: "deAMPylation assay" EXACT PSI-MI-alternate []
is_a: MI:0415 ! enzymatic study
created_by: ppm
creation_date: 2016-05-09T09:40:07Z

[Term]
id: MI:2217
name: luciferase-c
def: "The c-terminus of a luciferase protein, fused to a protein of interest for use in the split luciferase complementation assay." [PMID:22070901]
subset: PSI-MI_slim
synonym: "luciferase-c" EXACT PSI-MI-short []
is_a: MI:1205 ! luciferase tag
created_by: ppm
creation_date: 2016-05-09T09:45:05Z

[Term]
id: MI:2218
name: luciferase-n
def: "The n-terminus of a luciferase protein, fused to a protein of interest for use in the split luciferase complementation assay." [PMID:22070901]
subset: PSI-MI_slim
synonym: "luciferase-n" EXACT PSI-MI-short []
is_a: MI:1205 ! luciferase tag
created_by: ppm
creation_date: 2016-05-09T09:45:23Z

[Term]
id: MI:2219
name: gaussia luciferase protein tag
def: "Gaussia luciferase, is an enzyme from the crustacean Gaussia princeps catalyzing the oxidation of coelenterazine to coelenteramide  that produces light. Gaussia luciferase produces a blue light around the 480 nm range." [PMID:26025768]
synonym: "gaussia luciferase" EXACT PSI-MI-short []
synonym: "gaussia luciferase protein tag" EXACT PSI-MI-alternate []
synonym: "GLuc tag" EXACT PSI-MI-alternate []
synonym: "gluc tag" EXACT PSI-MOD-alternate []
is_a: MI:1205 ! luciferase tag
created_by: ppm
creation_date: 2016-05-09T10:05:39Z

[Term]
id: MI:2220
name: gaussia-c
def: "The c-terminus of the gaussia luciferase protein, fused to a protein of interest for use in the split luciferase complementation assay." [PMID:17099704]
synonym: "gaussia-c" EXACT PSI-MI-short []
is_a: MI:2219 ! gaussia luciferase protein tag
created_by: ppm
creation_date: 2016-05-09T10:13:06Z

[Term]
id: MI:2221
name: gaussia-n
def: "The n-terminus of the gaussia luciferase protein, fused to a protein of interest for use in the split luciferase complementation assay." [PMID:17099704]
synonym: "gaussia-n" EXACT PSI-MI-short []
is_a: MI:2219 ! gaussia luciferase protein tag
created_by: ppm
creation_date: 2016-05-09T10:13:23Z

[Term]
id: MI:2222
name: inference by socio-affinity scoring
def: "Socio-affinity index provides a single measure of the association between each pair of proteins based on an entire AP-MS dataset, considering both the spoke (when one protein retrieves another when tagged) and the matrix (when two proteins are retrieved by another) evidence, and the overall frequency of each protein in the data set." [PMID:16429126]
subset: PSI-MI_slim
synonym: "inference by socio-affinity scoring" EXACT PSI-MI-alternate []
synonym: "socio-affinity index inference" EXACT PSI-MI-alternate []
synonym: "socio-affinity inference" EXACT PSI-MI-alternate []
synonym: "socioaffinity index scoring" EXACT PSI-MI-alternate []
synonym: "socioaffinity inference" EXACT PSI-MI-short []
is_a: MI:0363 ! inferred by author
created_by: ppm
creation_date: 2016-05-13T16:16:06Z

[Term]
id: MI:2223
name: inference by quantitative co-purification
def: "This method measures co-purification of proteins through several orthogonal purification steps, deriving a set of correlation measures that are then computationally weighted and combined to infer interacting pairs." [PMID:27099342]
subset: PSI-MI_slim
synonym: "inference by quantitative co-purification" EXACT PSI-MI-short []
synonym: "quantitative  tagless  co - purification" EXACT PSI-MI-alternate []
is_a: MI:0363 ! inferred by author
created_by: ppm
creation_date: 2016-05-17T10:36:05Z

[Term]
id: MI:2224
name: chemical rna modification plus base pairing prediction
def: "In this method predicted RNA-RNA pairings are tested by knocking down one of the two interacting RNAs and then experimentally determine if its presence is required for the other to be chemically modified." [PMID:10024243]
subset: PSI-MI_slim
synonym: "chemical rna modification plus base pairing prediction" EXACT PSI-MI-short []
is_a: MI:0254 ! genetic interference
created_by: ppm
creation_date: 2016-05-23T13:32:07Z

[Term]
id: MI:2225
name: zinc
def: "ZINC is a database of commercially available compounds for virtual screening. It uses publicly available bioactivity data to allow investigators to access chemical tools for biology.\n\nhttp://zinc15.docking.org/" [PMID:26479676]
subset: PSI-MI_slim
synonym: "ZINC" EXACT PSI-MI-alternate []
synonym: "zinc" EXACT PSI-MI-short []
xref: id-validation-regexp: "[0-9]*"
xref: search-url: "http://zinc15.docking.org/substances/${ac}"
is_a: MI:0461 ! interaction database
created_by: ppm
creation_date: 2016-06-13T15:47:30Z

[Term]
id: MI:2226
name: mutation with no effect
def: "A change in a sequence or structure in comparison to a reference entity due to a  insertion, deletion or substitution event that does not have any effect over an interaction when compared with the wild-type." [PMID:14577292]
subset: PSI-MI_slim
synonym: "mutation not affecting interaction" EXACT PSI-MOD-alternate []
synonym: "mutation with no effect" EXACT PSI-MI-short []
is_a: MI:0118 ! mutation
created_by: ppm
creation_date: 2016-06-13T15:57:12Z

[Term]
id: MI:2227
name: mutation causing an interaction
def: "A change in a sequence or structure in comparison to a reference entity due to a  insertion, deletion or substitution event that enables an interaction when compared with the wild-type, which does not interact." [PMID:14755292]
synonym: "mutation causing" EXACT PSI-MI-short []
synonym: "mutation causing an interaction" EXACT PSI-MI-alternate []
synonym: "mutation enabling interaction" EXACT PSI-MI-alternate []
is_a: MI:0118 ! mutation
created_by: ppm
creation_date: 2016-06-13T16:25:47Z

[Term]
id: MI:2228
name: ceitec
def: "Interactions and complexes curated by scientists at the Central European Institute of Technology (CEITEC)." []
synonym: "ceitec" EXACT PSI-MI-short []
synonym: "CEITEC" EXACT PSI-MI-alternate []
synonym: "Central European Institute of Technology" EXACT PSI-MI-alternate []
xref: search-url: "www.ceitec.eu/"
is_a: MI:0461 ! interaction database
created_by: ppm
creation_date: 2016-09-14T10:41:07Z

[Term]
id: MI:2229
name: nucleicacid-gene
def: "Interaction between a nucleic acid and a gene region." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1046 ! interacting molecules
created_by: ppm
creation_date: 2016-09-21T11:39:49Z

[Term]
id: MI:2230
name: nucleicacid-nucleicacid
def: "Interaction between a nucleic acid and a corresponding nucleic acid." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:1046 ! interacting molecules
created_by: ppm
creation_date: 2016-09-21T11:41:03Z

[Term]
id: MI:2231
name: coexpression
def: "This approach infers interacting pairs of proteins looking at expression data coming from transcript expression datasets. Co-expressed pairs of genes are ranked and predicted to be interacting proteins as well." []
subset: PSI-MI_slim
synonym: "co-expression" EXACT PSI-MI-alternate []
synonym: "coexpression" EXACT PSI-MI-short []
synonym: "coexpression prediction" EXACT PSI-MI-alternate []
is_a: MI:0046 ! experimental knowledge based
created_by: ppm
creation_date: 2016-10-05T11:48:53Z

[Term]
id: MI:2232
name: molecular association
def: "A particular way two or more molecules influence one another." []
subset: PSI-MI_slim
synonym: "molecular association" EXACT PSI-MI-short []
is_a: MI:0190 ! interaction type
created_by: ppm
creation_date: 2016-12-08T15:17:45Z

[Term]
id: MI:2233
name: causal interaction
def: "Binary causative relationships between biological entities. CV terms belonging to this term allow the description of causal interactions using the current PSI-MI schema." [DOI:10.1142/S0219525908001465]
subset: PSI-MI_slim
synonym: "causal interaction" EXACT PSI-MI-short []
relationship: part_of MI:0000 ! molecular interaction
created_by: ppm
creation_date: 2017-01-19T13:17:37Z

[Term]
id: MI:2234
name: causal statement
def: "The effect of modulator entity A on a modulated entity B." [PMID:26467481]
synonym: "causal statement" EXACT PSI-MI-short []
is_a: MI:2233 ! causal interaction
created_by: ppm
creation_date: 2017-01-19T13:20:22Z

[Term]
id: MI:2235
name: up-regulates
def: "The effect of a modulator entity A on a modulated entity B that  increases the concentration and/or frequency and/or rate and/or extent of the molecular function of B." [PMID:26467481]
subset: PSI-MI_slim
synonym: "activates" NARROW []
synonym: "up regulates" EXACT PSI-MI-alternate []
synonym: "up-regulates" EXACT PSI-MI-short []
is_a: MI:2234 ! causal statement
created_by: ppm
creation_date: 2017-01-19T13:47:54Z

[Term]
id: MI:2236
name: up-regulates activity
def: "The effect of a modulator entity A on a modulated entity B that  increases the frequency, rate or extent of the molecular function of B, an elemental biological activity occurring at the molecular level, such as catalysis or binding (GO:0044093)." [PMID:26467481]
subset: PSI-MI_slim
synonym: "activates activity" EXACT PSI-MI-alternate []
synonym: "up-regulates activity" EXACT PSI-MI-short []
xref: GO:GO\:0044093
is_a: MI:2235 ! up-regulates
created_by: ppm
creation_date: 2017-01-19T13:50:43Z

[Term]
id: MI:2237
name: up-regulates quantity
def: "The effect of a modulator entity A on a modulated entity B that  increases the concentration of the modulated entity B." [PMID:26467481]
subset: PSI-MI_slim
synonym: "increases quantity" EXACT PSI-MI-alternate []
synonym: "up-regulates quantity" EXACT PSI-MI-short []
is_a: MI:2235 ! up-regulates
created_by: ppm
creation_date: 2017-01-19T13:53:41Z

[Term]
id: MI:2238
name: up-regulates quantity by expression
def: "The effect of a modulator entity A on a modulated entity B that  increases the concentration of the modulated entity B, by promoting its gene expression." [PMID:26467481]
subset: PSI-MI_slim
synonym: "increases quantity by expression" EXACT PSI-MI-alternate []
synonym: "up-regulates quantity by expression" EXACT PSI-MI-short []
is_a: MI:2237 ! up-regulates quantity
created_by: ppm
creation_date: 2017-01-19T13:56:00Z

[Term]
id: MI:2239
name: up-regulates quantity by stabilization
def: "The effect of a modulator entity A on a modulated entity B that  increases the concentration of the modulated entity B by preventing its degradation." [PMID:26467481]
subset: PSI-MI_slim
synonym: "increases quantity by stabilization" EXACT PSI-MI-alternate []
synonym: "up-regulates quantity by stabilization" EXACT PSI-MI-short []
is_a: MI:2237 ! up-regulates quantity
created_by: ppm
creation_date: 2017-01-19T13:58:03Z

[Term]
id: MI:2240
name: down-regulates
def: "The effect of a modulator entity A on a modulated entity B that  decreases the concentration and/or frequency and/or ate and/or extent of molecular function of B." [PMID:26467481]
subset: PSI-MI_slim
synonym: "down regulates" EXACT PSI-MI-alternate []
synonym: "down-regulates" EXACT PSI-MI-short []
is_a: MI:2234 ! causal statement
created_by: ppm
creation_date: 2017-01-19T14:00:20Z

[Term]
id: MI:2241
name: down-regulates activity
def: "The effect of a modulator entity A on a modulated entity B that  decreases the frequency, rate or extent of the molecular function of B, an elemental biological activity occurring at the molecular level, such as catalysis or binding (GO:0044093)." [PMID:26467481]
subset: PSI-MI_slim
synonym: "down-regulates activity" EXACT PSI-MI-short []
synonym: "inhibits activity" EXACT PSI-MI-alternate []
xref: GO:GO\:0044093
is_a: MI:2240 ! down-regulates
created_by: ppm
creation_date: 2017-01-19T14:13:34Z

[Term]
id: MI:2242
name: down-regulates quantity
def: "The effect of a modulator entity A on a modulated entity B that  decreases the concentration of the modulated entity B." [PMID:26467481]
subset: PSI-MI_slim
synonym: "decreases quantity" EXACT PSI-MI-alternate []
synonym: "down-regulates quantity" EXACT PSI-MI-short []
is_a: MI:2240 ! down-regulates
created_by: ppm
creation_date: 2017-01-19T14:15:10Z

[Term]
id: MI:2243
name: down-regulates quantity by repression
def: "The effect of a modulator entity A on a modulated entity B that  decreases the concentration of the modulated entity B, by preventing its gene expression." [PMID:26467481]
subset: PSI-MI_slim
synonym: "Decrease quantity by repression" EXACT PSI-MI-alternate []
synonym: "down-regulates quantity by repression" EXACT PSI-MI-short []
is_a: MI:2242 ! down-regulates quantity
created_by: ppm
creation_date: 2017-01-19T14:25:28Z

[Term]
id: MI:2244
name: down-regulates quantity by destabilization
def: "The effect of a modulator entity A on a modulated entity B that  decreases the concentration of the modulated entity B by promoting its degradation." [PMID:26467481]
subset: PSI-MI_slim
synonym: "decrease quantity by destabilization" EXACT PSI-MI-alternate []
synonym: "down-regulates quantity by destabilization" EXACT PSI-MI-short []
is_a: MI:2242 ! down-regulates quantity
created_by: ppm
creation_date: 2017-01-19T14:28:52Z

[Term]
id: MI:2245
name: causal regulatory mechanism
def: "Type of relationship between entities involved in a causal interaction. This term is to be used only to describe the effect of a modulator entity A on a modulated entity B when A is not immediately upstream of B." [PMID:26467481]
synonym: "causal regulatory mechanism" EXACT PSI-MI-short []
synonym: "indirect causal regulation" EXACT PSI-MI-alternate []
is_a: MI:2233 ! causal interaction
created_by: ppm
creation_date: 2017-01-19T15:44:29Z

[Term]
id: MI:2246
name: indirect causal regulation
def: "The effect of a modulator entity A on a modulated entity B that  occurs when A is not immediately upstream of B." [PMID:15845847]
subset: PSI-MI_slim
synonym: "indirect" EXACT PSI-MI-alternate []
synonym: "indirect causal regulation" EXACT PSI-MI-short []
is_obsolete: true
created_by: ppm
creation_date: 2017-01-19T15:45:44Z

[Term]
id: MI:2247
name: transcriptional regulation
def: "Any process that modulates the frequency, rate or extent of the chemical reactions resulting in the transcription of DNA to RNA and gene activity regulation." [PMID:25428369]
subset: PSI-MI_slim
synonym: "transcriptional regulation" EXACT PSI-MI-short []
is_a: MI:2245 ! causal regulatory mechanism
created_by: ppm
creation_date: 2017-01-19T15:47:39Z

[Term]
id: MI:2248
name: translation regulation
def: "Any process that modulates the frequency, rate or extent of the chemical reactions and pathways resulting in the formation of proteins by the translation of mRNA." [PMID:25428369]
subset: PSI-MI_slim
synonym: "translation regulation" EXACT PSI-MI-short []
synonym: "translational regulation" EXACT PSI-MI-alternate []
is_a: MI:2245 ! causal regulatory mechanism
created_by: ppm
creation_date: 2017-01-19T15:48:53Z

[Term]
id: MI:2249
name: post transcriptional regulation
def: "Any process that control gene expression at the RNA level, between the transcription and the translation of the gene." [PMID:25428369]
subset: PSI-MI_slim
synonym: "post transcriptional regulation" EXACT PSI-MI-short []
synonym: "post-transcriptional regulation" EXACT PSI-MI-alternate []
is_a: MI:2245 ! causal regulatory mechanism
created_by: ppm
creation_date: 2017-01-19T15:54:32Z

[Term]
id: MI:2250
name: direct causal regulation
def: "The effect of a modulator entity A on a modulated entity B that  occurs when A is immediately upstream of B." [PMID:15845847]
subset: PSI-MI_slim
synonym: "direct" EXACT PSI-MI-alternate []
synonym: "direct causal regulation" EXACT PSI-MI-short []
is_obsolete: true
created_by: ppm
creation_date: 2017-01-19T15:56:00Z

[Term]
id: MI:2251
name: transcriptional regulation by direct binding of dbTF to DNA regulatory element
def: "Direct binding of a DbTF to a DNA regulatory sequence that modulates the frequency, rate or extent of the chemical reactions resulting in the transcription of DNA to RNA and gene activity regulation." [PMID:25428369]
subset: PSI-MI_slim
is_obsolete: true
created_by: ppm
creation_date: 2017-01-19T15:57:01Z

[Term]
id: MI:2252
name: guanine nucleotide exchange factor reaction
def: "The process mediated by guanine nucleotide exchange factors (GEFs) that catalyze the exchange of bound GDP with cytosolic GTP." [PMID:23303910]
subset: PSI-MI_slim
synonym: "GEF reaction" EXACT PSI-MOD-short []
is_a: MI:0414 ! enzymatic reaction
created_by: ppm
creation_date: 2017-01-19T16:13:36Z

[Term]
id: MI:2253
name: gtpase-activating protein reaction
def: "A family of cellular proteins able to increases the activity of a GTPase." [PMID:17173929]
synonym: "GAP reaction" EXACT PSI-MI-short []
synonym: "GTPase-Accelerating Protein reaction" EXACT PSI-MI-alternate []
synonym: "RGS protein reaction" EXACT PSI-MI-alternate []
is_obsolete: true
created_by: ppm
creation_date: 2017-01-19T16:16:04Z

[Term]
id: MI:2254
name: chemical activation reaction
def: "The effect of a chemical compound that results in the activation or in an increased activation of a target molecule." [PMID:26467481]
subset: PSI-MI_slim
synonym: "chemical activation reaction" EXACT PSI-MI-short []
is_obsolete: true
created_by: ppm
creation_date: 2017-01-19T16:23:55Z

[Term]
id: MI:2255
name: chemical inhibition reaction
def: "The effect of a chemical compound that stops, prevents, or reduces the activity of a target molecule." [PMID:26467481]
subset: PSI-MI_slim
synonym: "chemical inhibition reaction" EXACT PSI-MI-short []
is_obsolete: true
created_by: ppm
creation_date: 2017-01-19T16:25:05Z

[Term]
id: MI:2256
name: relocalization
def: "Any process that modulates the frequency, rate or extent of any process in which a cell, a substance, or a cellular entity is transported to, or maintained in, a specific location." [PMID:26467481]
subset: PSI-MI_slim
synonym: "relocalization" EXACT PSI-MI-short []
is_obsolete: true
created_by: ppm
creation_date: 2017-01-19T16:26:15Z

[Term]
id: MI:2257
name: small molecule catalysis reaction
def: "The chemical reactions and pathways resulting in the formation, breakdown, modification of small molecules." [PMID:26467481]
subset: PSI-MI_slim
synonym: "small molecule catalysis reaction" EXACT PSI-MI-short []
is_obsolete: true
created_by: ppm
creation_date: 2017-01-19T16:27:34Z

[Term]
id: MI:2258
name: xenobiotic
def: "Molecule that encompasses any constitutionally or isotopically distinct atom, molecule, ion, ion pair, radical, radical ion, complex, conformer, etc., identifiable as a separately distinguishable entity, which is not physiologically part of a cell, tissue, organ, or organism." [PMID:14755292]
subset: PSI-MI_slim
synonym: "chemical" EXACT PSI-MI-alternate []
synonym: "drug" EXACT PSI-MI-alternate []
synonym: "xenobiotic" EXACT PSI-MI-short []
is_a: MI:0328 ! small molecule
created_by: ppm
creation_date: 2017-01-19T16:46:33Z

[Term]
id: MI:2259
name: causal interactor type
def: "Entity involved in a causative relationship. These terms have to be used as interactor types only if associated with causal statements." [PMID:26467481]
synonym: "causal interactor type" EXACT PSI-MI-short []
is_a: MI:2233 ! causal interaction
created_by: ppm
creation_date: 2017-01-19T16:51:20Z

[Term]
id: MI:2260
name: stimulus
def: "Any detectable change in the internal or external environment of a cell, tissue, organ, or organism." [PMID:14755292]
subset: PSI-MI_slim
synonym: "stimulus" EXACT PSI-MI-short []
is_a: MI:2259 ! causal interactor type
created_by: ppm
creation_date: 2017-01-19T16:52:44Z

[Term]
id: MI:2261
name: phenotype
def: "Cellular phenotype is the conglomerate of multiple cellular processes involving gene and protein expression that result in the elaboration of a cell's particular morphology and function." [PMID:19380745]
subset: PSI-MI_slim
synonym: "phenotype" EXACT PSI-MI-short []
is_a: MI:2259 ! causal interactor type
created_by: ppm
creation_date: 2017-01-19T16:54:07Z

[Term]
id: MI:2262
name: causal regulatory modification
def: "The modification of a subsequence that regulates the concentration and/or frequency and/or rate and/or extent of the molecular function of an entity." [PMID:26467481]
comment: CAUTION: This is a temporary branch. These terms will be soon added in the PSI-MOD ontology and this branch will became obsolete.
synonym: "causal regulatory modification" EXACT PSI-MI-short []
is_a: MI:2233 ! causal interaction
created_by: ppm
creation_date: 2017-01-19T17:03:04Z

[Term]
id: MI:2263
name: s-nitrosylation
def: "Reaction that create a covalent bond between a nitrogen monoxide group and the thiol group of cysteine." [PMID:15688001]
subset: PSI-MI_slim
synonym: "s-nitrosylation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction
created_by: ppm
creation_date: 2017-01-19T17:11:46Z

[Term]
id: MI:2264
name: tyrosinated residue
def: "A protein modification that effectively add a tyrosine residues to the c-terminal end of alpha-tubulin." [PMID:26467481]
subset: PSI-MI_slim
synonym: "tyrosinated residue" EXACT PSI-MI-short []
is_a: MI:2262 ! causal regulatory modification
created_by: ppm
creation_date: 2017-01-23T10:26:40Z

[Term]
id: MI:2265
name: de-acetylated residue
def: "A protein modification that effectively remove an acyl group from a protein." [PMID:26467481]
subset: PSI-MI_slim
synonym: "de-acetylated residue" EXACT PSI-MI-short []
synonym: "deacetylated residue" EXACT PSI-MI-alternate []
is_a: MI:2262 ! causal regulatory modification
created_by: ppm
creation_date: 2017-01-23T10:30:06Z

[Term]
id: MI:2266
name: de-phosphorylated residue
def: "A protein modification that effectively remove a phosphate group  from a protein by hydrolysis." [PMID:26467481]
subset: PSI-MI_slim
synonym: "de-phosphorylated residue" EXACT PSI-MI-short []
synonym: "dephosphorylated residue" EXACT PSI-MI-alternate []
is_a: MI:2262 ! causal regulatory modification
created_by: ppm
creation_date: 2017-01-23T10:32:50Z

[Term]
id: MI:2267
name: de-sumoylated residue
def: "A protein modification that effectively cleaves the G-K bond and releases SUMO proteins." [PMID:26467481]
subset: PSI-MI_slim
synonym: "de-sumoylated residue" EXACT PSI-MI-short []
synonym: "desumoylated residue" EXACT PSI-MI-alternate []
is_a: MI:2262 ! causal regulatory modification
created_by: ppm
creation_date: 2017-01-23T10:46:01Z

[Term]
id: MI:2268
name: de-methylated residue
def: "A protein modification that effectively removes one or more methyl groups from a protein." [PMID:26467481]
subset: PSI-MI_slim
synonym: "de-methylated residue" EXACT PSI-MI-short []
synonym: "demethylated residue" EXACT PSI-MI-alternate []
is_a: MI:2262 ! causal regulatory modification
created_by: ppm
creation_date: 2017-01-23T10:47:33Z

[Term]
id: MI:2269
name: de-ubiquitinylated residue
def: "A protein modification that effectively cleaves the G-K bond and releases ubiquitin or ubiquitin like proteins." [PMID:26467481]
subset: PSI-MI_slim
synonym: "de-ubiquitinylated residue" EXACT PSI-MI-short []
synonym: "deubiquitinylated residue" EXACT PSI-MI-alternate []
is_a: MI:2262 ! causal regulatory modification
created_by: ppm
creation_date: 2017-01-23T10:48:53Z

[Term]
id: MI:2270
name: signalink
def: "SignaLink 2.0 is a signaling pathway resource with multi-layered regulatory networks.\nhttp://signalink.org" [PMID:23331499]
subset: PSI-MI_slim
synonym: "SignaLink" EXACT PSI-MI-alternate []
synonym: "signalink" EXACT PSI-MI-short []
xref: url:http\://signalink.org
is_a: MI:0461 ! interaction database
created_by: ppm
creation_date: 2017-01-23T11:41:20Z

[Term]
id: MI:2271
name: edam
def: "EDAM (EMBRACE Data And Methods) is an ontology of bioinformatics operations (tool, application, or workflow functions), types of data, topics (application domains), and data formats.\nhttp://edamontology.org/" [PMID:23479348]
subset: PSI-MI_slim
synonym: "edam" EXACT PSI-MI-short []
synonym: "EDAM" EXACT PSI-MI-alternate []
synonym: "EMBRACE Data And Methods" EXACT PSI-MI-alternate []
xref: url:http\://edamontology.org/
is_a: MI:1336 ! experiment database
created_by: ppm
creation_date: 2017-01-26T15:09:47Z

[Term]
id: MI:2272
name: tyrosinylation
def: "Reversible reaction that add a tyrosine residue to an amino-acid." []
subset: PSI-MI_slim
synonym: "tyrosinylation" EXACT PSI-MI-short []
xref: GO:GO\:0018322
is_a: MI:0414 ! enzymatic reaction
created_by: ppm
creation_date: 2017-01-26T15:21:43Z

[Term]
id: MI:2273
name: tyrosination
def: "Reversible reaction that add a tyrosine residues to the c-terminal end of alpha-tubulin." [PMID:10842328]
subset: PSI-MI_slim
synonym: "tyrosination" EXACT PSI-MI-short []
xref: GO:GO\:0018166
is_a: MI:2272 ! tyrosinylation
created_by: ppm
creation_date: 2017-01-26T15:22:39Z

[Term]
id: MI:2274
name: regulator
def: "Entity whose activity exerts an effect on the concentration, frequency, rate or extent of the target entity." [PMID:14755292]
subset: PSI-MI_slim
synonym: "modulator" EXACT PSI-MI-alternate []
synonym: "regulator" EXACT PSI-MI-short []
is_a: MI:0500 ! biological role
created_by: ppm
creation_date: 2017-01-26T15:29:51Z

[Term]
id: MI:2275
name: regulator target
def: "Entity whose concentration, frequency, rate or extent are regulated by the regulator entity." [PMID:14755292]
subset: PSI-MI_slim
synonym: "modulator target" EXACT PSI-MI-alternate []
synonym: "regulator target" EXACT PSI-MI-short []
is_a: MI:0500 ! biological role
created_by: ppm
creation_date: 2017-01-26T15:31:14Z

[Term]
id: MI:2276
name: carbohydrate chemical modification
def: "Chemical alterations occurring in the specific carbohydrate molecule involved in an interaction. The process can involve covalent modifications (i.e. sulfations) or other forms of chemical modification." [PMID:14755292]
synonym: "carbohydrate chemical modification" EXACT PSI-MI-short []
is_a: MI:0252 ! biological feature
created_by: ppm
creation_date: 2017-03-06T11:04:25Z

[Term]
id: MI:2277
name: Cr-two hybrid
def: "This method uses Cre recombinase as a two-hybrid protein-protein interaction reporter that functions intracellularly to covalently and unidirectionally link interacting bait and prey plasmids via specialized loxP sites that flank the protein-coding sequences. The linked protein-coding sequences serve as interaction-identifying DNA molecules that enable massively multiplexed screening coupled with next-generation DNA sequencing to detect protein-protein interactions." []
subset: PSI-MI_slim
synonym: "cr-2h" EXACT PSI-MI-alternate []
synonym: "cr-two hybrid" EXACT PSI-MI-short []
synonym: "Cre recombinase two hybrid" EXACT PSI-MI-alternate []
is_a: MI:1113 ! two hybrid bait and prey pooling approach
created_by: ppm
creation_date: 2017-06-20T15:57:41Z

[Term]
id: MI:2278
name: polymer chain length
def: "Length of a repetitive polymer chain. Applicable to carbohydrates and other non-protein, non-nucleic acid polymers." [PMID:14755292]
subset: PSI-MI_slim
synonym: "polymer chain length" EXACT PSI-MI-short []
is_a: MI:0666 ! participant attribute name
created_by: ppm
creation_date: 2017-07-05T10:27:19Z

[Term]
id: MI:2279
name: complex portal
def: "The Complex Portal is a manually curated, encyclopaedic resource of macromolecular complexes from a number of key model organisms, entered into the IntAct molecular interaction database . Data includes protein-only complexes as well as protein-small molecule and protein-nucleic acid complexes. All complexes are derived from physical molecular interaction evidences extracted from the literature and cross-referenced in the entry, or by curator inference from information on homologs in closely related species or by inference from scientific background. All complexes are tagged with Evidence and Conclusion Ontology codes to indicate the type of evidence available for each entry." [PMID:25313161]
subset: PSI-MI_slim
synonym: "Complex Portal" EXACT PSI-MI-alternate []
synonym: "complex portal" EXACT PSI-MI-short []
xref: search-url: "http://www.ebi.ac.uk/complexportal/complex/${ac}"
is_a: MI:0461 ! interaction database
is_a: MI:0473 ! participant database
created_by: ppm
creation_date: 2017-07-28T09:34:45Z

[Term]
id: MI:2280
name: deamidation reaction
def: "Reaction in which an amide functional group in the side chain of the amino acids asparagine or glutamine is removed or converted to another functional group. Typically, asparagine is converted to aspartic acid or isoaspartic acid and glutamine is converted to glutamic acid or pyroglutamic acid (5-oxoproline)." [PMID:2703484, PMID:3440704]
subset: PSI-MI_slim
synonym: "deamidation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction
created_by: ppm
creation_date: 2017-08-08T14:38:29Z

[Term]
id: MI:2281
name: deamidation assay
def: "Assay to measure the catalysis of the reaction: a monocarboxylic acid amide + H2O = a monocarboxylate + NH3." [GO:0004040]
subset: PSI-MI_slim
synonym: "amidase assay" EXACT PSI-MI-alternate []
synonym: "deamidation" EXACT PSI-MI-short []
is_a: MI:0415 ! enzymatic study
created_by: ppm
creation_date: 2017-08-08T14:49:09Z

[Term]
id: MI:2282
name: complex-primary
def: "Complex object unique primary identifier that is assigned to a complex in the Complex Portal." [PMID:25313161]
subset: PSI-MI_slim
synonym: "complex-primary" EXACT PSI-MI-short []
is_a: MI:0353 ! cross-reference type
created_by: ppm
creation_date: 2017-08-25T13:31:03Z

[Term]
id: MI:2283
name: southwestern blotting
def: "Southwestern blotting, is a lab technique which involves identifying and characterizing DNA-binding proteins by their ability to bind to specific oligonucleotide probes, generally radioactively labeled. The proteins are separated by gel electrophoresis and are subsequently transferred to nitrocellulose membranes similar to other types of blotting." [PMID:26404144]
subset: PSI-MI_slim
synonym: "southwestern blot" EXACT PSI-MI-short []
synonym: "southwestern blotting" EXACT PSI-MI-alternate []
is_a: MI:0047 ! far western blotting
created_by: ppm
creation_date: 2017-11-15T15:35:20Z

[Term]
id: MI:2284
name: complex component
def: "Indicates that the cross-referenced molecule is a component of a containing complex." [PMID:25313161]
subset: PSI-MI_slim
synonym: "complex component" EXACT PSI-MI-short []
synonym: "complex-component" EXACT PSI-MI-alternate []
is_a: MI:0353 ! cross-reference type
created_by: ppm
creation_date: 2017-12-15T11:08:53Z

[Term]
id: MI:2285
name: miRNA interference luciferase reporter assay
def: "The method is based on the functional effect of the binding of the microRNA on the target (mRNA or LncRNA), which is the repression of the expression of the target. To validate a sequence as a direct target of a microRNA, a luciferase reporter gene carrying the wt candidate sequence or its mutated form is used, and the expression of the target is evaluated with a luciferase assay. If the wt is significantly less expressed than the mutant, the binding occurs." [PMID:14697198, PMID:21431711]
subset: PSI-MI_slim
synonym: "miRNA interference luciferase assay" EXACT PSI-MI-short []
is_a: MI:0255 ! post transcriptional interference
created_by: pporras
creation_date: 2018-05-02T15:22:12Z

[Term]
id: MI:2286
name: functional association
def: "Binary relationship between biological entities when one of them modulates the other in terms of function, expression, degradation or stability of the other and the relationship between the partners cannot be ascertained as direct, so intermediate steps are implicitly present. This relation specifically does not imply a physical interaction between the entities involved." []
subset: PSI-MI_slim
synonym: "functional association" EXACT PSI-MI-short []
is_a: MI:0190 ! interaction type
created_by: pporras
creation_date: 2018-06-27T15:24:40Z

[Term]
id: MI:2287
name: identification by structure determination
def: "Identity of the participant was established (or confirmed) by\nfitting its molecular model to the experimentally determined\nelectron density." [PMID:7877166]
subset: PSI-MI_slim
synonym: "identification by structure determination" EXACT PSI-MI-alternate []
synonym: "structure determination" EXACT PSI-MI-short []
is_a: MI:0661 ! experimental participant identification
created_by: pporras
creation_date: 2018-06-28T15:00:41Z

[Term]
id: MI:2288
name: DAP-seq
def: "DAP-seq is an in vitro TF-DNA binding assay in which a DAP-seq gDNA library is prepared by attaching a short DNA sequencing adaptor onto purified and fragmented gDNA. In a separate reaction, an affinity-purified TF is prepared by in vitro expression, bound to ligand-coupled beads, and washed to remove non-specific cellular components. The gDNA library is added to the affinity-bound TF and the unbound DNA is washed away. The bound fraction is eluted, amplified with PCR primers to introduce an indexed adaptor, and the DNA is sequenced." [PMID:27203113]
subset: PSI-MI_slim
synonym: "dap-seq" EXACT PSI-MI-short []
synonym: "DNA affinity purification sequencing" EXACT PSI-MI-alternate []
is_a: MI:0004 ! affinity chromatography technology
created_by: pporras
creation_date: 2018-06-28T16:09:45Z

[Term]
id: MI:2289
name: virotrap
def: "The bait fused to a viral protein (e.g. HIV-1 GAG protein) allows the trapping of interaction partners (preys) within virus-like particles (VLPs) that bud from mammalian cells. Once the VLPs are enriched and purified, this technique allows the isolation of multimeric complexes as well as binary interactions and their subsequent identification by methods such as MS and western blots." [PMID:27122307]
subset: PSI-MI_slim
synonym: "viral particle co-purification" EXACT PSI-MI-alternate []
is_a: MI:0401 ! biochemical
created_by: pporras
creation_date: 2018-09-13T10:18:19Z

[Term]
id: MI:2290
name: optical tweezers
def: "Optical tweezers are instruments that use a focused laser beam to apply force  to particles suspended in a liquid medium. This allows to measure forces generated between interacting molecules - either at the level of just single interacting pair of molecules or at the level of larger molecular assemblies." [PMID:17023539, PMID:17081984]
subset: PSI-MI_slim
is_a: MI:0859 ! force spectroscopy
created_by: pporras
creation_date: 2018-09-13T10:39:59Z

[Term]
id: MI:2291
name: atomic force microscopy cantilevers
def: "Molecules adsorbed on a solid surface are picked up by a microscopic tip (nanometers wide) that is located at the end of an elastic cantilever. Piezoelectric controller is used to measure forces generated by single molecules or molecular complexes stretched between the substrate and the cantilever tip." [PMID:18511917]
subset: PSI-MI_slim
synonym: "afm cantilevers" EXACT PSI-MI-short []
is_a: MI:0859 ! force spectroscopy
created_by: pporras
creation_date: 2018-09-13T10:49:44Z

[Term]
id: MI:2292
name: magnetic tweezers
def: "Magnetic tweezers are instruments that use a set of magnets to apply forces to physically hold and move individual molecules attached to ferromagnetic beads. Such instruments allow to measure the forces generated between interacting molecules - either at the level of just single interacting pair of molecules or at the level of larger molecular assemblies." [PMID:18511917]
subset: PSI-MI_slim
synonym: "electromagnetic tweezers" EXACT PSI-MI-alternate []
is_a: MI:0859 ! force spectroscopy
created_by: pporras
creation_date: 2018-09-13T12:04:16Z

[Term]
id: MI:2293
name: 5' position
def: "Term describing the upstream end of a nucleotide sequence." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0333 ! feature range status
created_by: pporras
creation_date: 2018-09-14T09:15:05Z

[Term]
id: MI:2294
name: 5' range
def: "Term describing the upstream region of a nucleotide sequence, exact coordinates not available." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0333 ! feature range status
created_by: pporras
creation_date: 2018-09-14T09:25:33Z

[Term]
id: MI:2295
name: 3' position
def: "Term describing the downstream end of a nucleotide sequence." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0333 ! feature range status
created_by: pporras
creation_date: 2018-09-14T09:26:47Z

[Term]
id: MI:2296
name: 3' range
def: "Term describing the downstream region of a nucleotide sequence, exact coordinates not available." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0333 ! feature range status
created_by: pporras
creation_date: 2018-09-14T09:27:33Z

[Term]
id: MI:2297
name: carbohydrate chemical modification causing an interaction
def: "Chemical alterations occurring in the specific carbohydrate molecule involved in an interaction that enables an interaction when compared with the unaltered carbohydrate, which does not interact." [PMID:14755292]
subset: PSI-MI_slim
synonym: "carbohydrate chemical modification causing" EXACT PSI-MI-short []
is_a: MI:2276 ! carbohydrate chemical modification
created_by: pporras
creation_date: 2018-09-14T09:45:20Z

[Term]
id: MI:2298
name: carbohydrate chemical modification with no effect
def: "Chemical alterations occurring in the specific carbohydrate molecule involved in an interaction that does not have any effect over an interaction when compared with the unaltered form." [PMID:14755292]
subset: PSI-MI_slim
synonym: "carbohydrate chemical modification not affecting interaction" EXACT PSI-MI-alternate []
is_a: MI:2276 ! carbohydrate chemical modification
created_by: pporras
creation_date: 2018-09-14T09:49:02Z

[Term]
id: MI:2299
name: carbohydrate chemical modification decreasing interaction
def: "Chemical alterations occurring in the specific carbohydrate molecule involved in an interaction that decreases significantly interaction strength  or rate (in the case of interactions inferred from enzymatic reaction) when compared with the unaltered carbohydrate." [PMID:14755292]
subset: PSI-MI_slim
synonym: "carbohydrate chemical modification decreasing" EXACT PSI-MI-short []
is_a: MI:2276 ! carbohydrate chemical modification
created_by: pporras
creation_date: 2018-09-14T09:53:05Z

[Term]
id: MI:2300
name: carbohydrate chemical modification decreasing interaction rate
def: "Chemical alterations occurring in the specific carbohydrate molecule involved in an interaction that decreases significantly interaction rate (in the case of interactions inferred from enzymatic reaction) when compared with the unaltered carbohydrate." [PMID:14755292]
subset: PSI-MI_slim
synonym: "carbohydrate chemical modification decreasing rate" EXACT PSI-MI-short []
is_a: MI:2299 ! carbohydrate chemical modification decreasing interaction
created_by: pporras
creation_date: 2018-09-14T09:56:38Z

[Term]
id: MI:2301
name: carbohydrate chemical modification decreasing interaction strength
def: "Chemical alterations occurring in the specific carbohydrate molecule involved in an interaction that decreases significantly interaction strength when compared with the unaltered carbohydrate." [PMID:14755292]
subset: PSI-MI_slim
synonym: "carbohydrate chemical modification decreasing strength" EXACT PSI-MI-short []
is_a: MI:2299 ! carbohydrate chemical modification decreasing interaction
created_by: pporras
creation_date: 2018-09-14T09:58:21Z

[Term]
id: MI:2302
name: carbohydrate chemical modification disrupting interaction
def: "Chemical alterations occurring in the specific carbohydrate molecule involved in an interaction that disrupts interaction strength  or rate (in the case of interactions inferred from enzymatic reaction) when compared with the unaltered carbohydrate." [PMID:14755292]
subset: PSI-MI_slim
synonym: "carbohydrate chemical modification disrupting" EXACT PSI-MI-short []
is_a: MI:2299 ! carbohydrate chemical modification decreasing interaction
created_by: pporras
creation_date: 2018-09-14T10:03:25Z

[Term]
id: MI:2303
name: carbohydrate chemical modification disrupting interaction strength
def: "Chemical alterations occurring in the specific carbohydrate molecule involved in an interaction that disrupts interaction strength when compared with the unaltered carbohydrate." [PMID:14755292]
subset: PSI-MI_slim
synonym: "carbohydrate chemical modification disrupting strength" EXACT PSI-MI-short []
is_a: MI:2302 ! carbohydrate chemical modification disrupting interaction
created_by: pporras
creation_date: 2018-09-14T10:06:44Z

[Term]
id: MI:2304
name: carbohydrate chemical modification disrupting interaction rate
def: "Chemical alterations occurring in the specific carbohydrate molecule involved in an interaction that disrupts interaction rate (in the case of interactions inferred from enzymatic reaction) when compared with the unaltered carbohydrate." [PMID:14755292]
subset: PSI-MI_slim
synonym: "carbohydrate chemical modification disrupting rate" EXACT PSI-MI-short []
is_a: MI:2302 ! carbohydrate chemical modification disrupting interaction
created_by: pporras
creation_date: 2018-09-14T10:08:37Z

[Term]
id: MI:2305
name: carbohydrate chemical modification increasing interaction
def: "Chemical alterations occurring in the specific carbohydrate molecule involved in an interaction that increases significantly interaction strength  or rate (in the case of interactions inferred from enzymatic reaction) when compared with the unaltered carbohydrate." [PMID:14755292]
subset: PSI-MI_slim
synonym: "carbohydrate chemical modification increasing" EXACT PSI-MI-short []
is_a: MI:2276 ! carbohydrate chemical modification
created_by: pporras
creation_date: 2018-09-14T10:11:37Z

[Term]
id: MI:2306
name: carbohydrate chemical modification increasing interaction strength
def: "Chemical alterations occurring in the specific carbohydrate molecule involved in an interaction that increases significantly interaction strength when compared with the unaltered carbohydrate." [PMID:14755292]
subset: PSI-MI_slim
synonym: "carbohydrate chemical modification increasing strength" EXACT PSI-MI-short []
is_a: MI:2305 ! carbohydrate chemical modification increasing interaction
created_by: pporras
creation_date: 2018-09-14T10:22:03Z

[Term]
id: MI:2307
name: carbohydrate chemical modification increasing interaction rate
def: "Chemical alterations occurring in the specific carbohydrate molecule involved in an interaction that increases significantly interaction rate (in the case of interactions inferred from enzymatic reaction) when compared with the unaltered carbohydrate." [PMID:14755292]
subset: PSI-MI_slim
synonym: "carbohydrate chemical modification increasing rate" EXACT PSI-MI-short []
is_a: MI:2305 ! carbohydrate chemical modification increasing interaction
created_by: pporras
creation_date: 2018-09-14T10:23:21Z

[Term]
id: MI:2308
name: attached carbohydrate
def: "Carbohydrate species chemically attached to proteins, or other organic molecules." [PMID:14755292]
comment: Specific carbohydrate species can be represented through the MOD ontology and their representation escapes the scope of this CV.
subset: PSI-MI_slim
synonym: "attached glycan" EXACT PSI-MI-alternate []
synonym: "glycosylation" EXACT PSI-MI-alternate []
is_a: MI:0252 ! biological feature
created_by: pporras
creation_date: 2018-09-14T10:26:12Z

[Term]
id: MI:2309
name: attached carbohydrate causing an interaction
def: "Carbohydrate species chemically attached to proteins, or other organic molecules involved in an interaction that enables an interaction when compared with the non-glycosylated molecule, which does not interact." [PMID:14755292]
subset: PSI-MI_slim
synonym: "attached carbohydrate causing" EXACT PSI-MI-short []
synonym: "glycosylation causing interaction" EXACT PSI-MI-alternate []
is_a: MI:2308 ! attached carbohydrate
created_by: pporras
creation_date: 2018-09-14T10:37:41Z

[Term]
id: MI:2310
name: attached carbohydrate with no effect
def: "Carbohydrate species chemically attached to proteins, or other organic molecules involved in an interaction that has no effect over an interaction when compared with the non-glycosylated molecule, which does not interact." [PMID:14755292]
subset: PSI-MI_slim
synonym: "attached carbohydrate not affecting interaction" EXACT PSI-MI-alternate []
synonym: "glycosylation with no effect" EXACT PSI-MI-alternate []
is_a: MI:2308 ! attached carbohydrate
created_by: pporras
creation_date: 2018-09-14T10:40:12Z

[Term]
id: MI:2311
name: attached carbohydrate decreasing interaction
def: "Carbohydrate species chemically attached to proteins, or other organic molecules involved in an interaction that decreases significantly interaction strength  or rate (in the case of interactions inferred from enzymatic reaction) when compared with the non-glycosylated molecule." [PMID:14755292]
subset: PSI-MI_slim
synonym: "attached carbohydrate decreasing" EXACT PSI-MI-short []
synonym: "glycosylation decreasing interaction" EXACT PSI-MI-alternate []
is_a: MI:2308 ! attached carbohydrate
created_by: pporras
creation_date: 2018-09-14T10:42:27Z

[Term]
id: MI:2312
name: attached carbohydrate increasing interaction
def: "Carbohydrate species chemically attached to proteins, or other organic molecules involved in an interaction that increases significantly interaction strength  or rate (in the case of interactions inferred from enzymatic reaction) when compared with the non-glycosylated molecule." [PMID:14755292]
subset: PSI-MI_slim
synonym: "attached carbohydrate increasing" EXACT PSI-MI-short []
synonym: "glycosylation increasing interaction" EXACT PSI-MI-alternate []
is_a: MI:2308 ! attached carbohydrate
created_by: pporras
creation_date: 2018-09-14T10:46:39Z

[Term]
id: MI:2313
name: attached carbohydrate increasing interaction strength
def: "Carbohydrate species chemically attached to proteins, or other organic molecules involved in an interaction that increases significantly interaction strength when compared with the non-glycosylated molecule." [PMID:14755292]
subset: PSI-MI_slim
synonym: "attached carbohydrate increasing strength" EXACT PSI-MI-short []
synonym: "glycosylation increasing strength" EXACT PSI-MI-alternate []
is_a: MI:2312 ! attached carbohydrate increasing interaction
created_by: pporras
creation_date: 2018-09-14T10:47:14Z

[Term]
id: MI:2314
name: attached carbohydrate increasing interaction rate
def: "Carbohydrate species chemically attached to proteins, or other organic molecules involved in an interaction that increases significantly interaction rate (in the case of interactions inferred from enzymatic reaction) when compared with the non-glycosylated molecule." [PMID:14755292]
subset: PSI-MI_slim
synonym: "attached carbohydrate increasing rate" EXACT PSI-MI-short []
synonym: "glycosylation increasing rate" EXACT PSI-MI-alternate []
is_a: MI:2312 ! attached carbohydrate increasing interaction
created_by: pporras
creation_date: 2018-09-14T10:49:39Z

[Term]
id: MI:2315
name: attached carbohydrate disrupting interaction rate
def: "Carbohydrate species chemically attached to proteins, or other organic molecules involved in an interaction that disrupts interaction rate (in the case of interactions inferred from enzymatic reaction) when compared with the non-glycosylated molecule." [PMID:14755292]
subset: PSI-MI_slim
synonym: "attached carbohydrate disrupting rate" EXACT PSI-MI-short []
synonym: "glycosylation disrupting rate" EXACT PSI-MI-alternate []
is_a: MI:2311 ! attached carbohydrate decreasing interaction
is_a: MI:2317 ! attached carbohydrate disrupting interaction
created_by: pporras
creation_date: 2018-09-14T10:50:23Z

[Term]
id: MI:2316
name: attached carbohydrate disrupting interaction strength
def: "Carbohydrate species chemically attached to proteins, or other organic molecules involved in an interaction that disrupts interaction strength when compared with the non-glycosylated molecule." [PMID:14755292]
subset: PSI-MI_slim
synonym: "attached carbohydrate disrupting strength" EXACT PSI-MI-short []
synonym: "glycosylation disrupting strength" EXACT PSI-MI-alternate []
is_a: MI:2311 ! attached carbohydrate decreasing interaction
is_a: MI:2317 ! attached carbohydrate disrupting interaction
created_by: pporras
creation_date: 2018-09-14T10:51:06Z

[Term]
id: MI:2317
name: attached carbohydrate disrupting interaction
def: "Carbohydrate species chemically attached to proteins, or other organic molecules involved in an interaction that disrupts interaction strength or rate (in the case of interactions inferred from enzymatic reaction) when compared with the non-glycosylated molecule." [PMID:14755292]
subset: PSI-MI_slim
synonym: "attached carbohydrate disrupting" EXACT PSI-MI-short []
synonym: "glycosylation disrupting interaction" EXACT PSI-MI-alternate []
is_a: MI:2311 ! attached carbohydrate decreasing interaction
created_by: pporras
creation_date: 2018-09-18T09:11:58Z

[Term]
id: MI:2318
name: force measurement
def: "A technique that measures forces generated by interactions between molecules." [PMID:14755292]
subset: PSI-MI_slim
synonym: "intermolecular force" EXACT PSI-MI-alternate []
synonym: "molecular force measurement" RELATED []
is_a: MI:0013 ! biophysical
created_by: pporras
creation_date: 2018-10-11T13:41:11Z

[Term]
id: MI:2319
name: surface force measurement
def: "A technique that measures interaction force between two surfaces as they are brought together and retracted." [doi:10.1038/262774a0]
subset: PSI-MI_slim
synonym: "surface adhesion force measurement" RELATED []
is_a: MI:2318 ! force measurement
created_by: pporras
creation_date: 2018-10-11T13:44:53Z

[Term]
id: MI:2320
name: aruk-ucl
def: "The Alzheimer's Research UK Gene Ontology Project represents a collaboration between University College London, the European Bioinformatics Institute (EBI) and the University of Manchester, funded by Alzheimer's Research UK. This annotation group is a member of the IMEx Consortium.\n\nwww.ucl.ac.uk/functional-gene-annotation/neurological" []
subset: PSI-MI_slim
synonym: "Alzheimer's Research UK Gene Ontology Project" EXACT PSI-MI-alternate []
is_a: MI:0461 ! interaction database
created_by: pporras
creation_date: 2018-10-16T09:26:24Z

[Term]
id: MI:2321
name: high-throughput sequencing
def: "High-throughput (a.k.a. \"next-generation\") sequencing applies to  methods that allow for sequencing of genome-scale number of bases." [PMID:19900591]
subset: PSI-MI_slim
synonym: "next-generation sequencing" EXACT PSI-MI-alternate []
synonym: "ngs sequencing" EXACT PSI-MI-short []
is_a: MI:0078 ! nucleotide sequence identification
created_by: pporras
creation_date: 2018-11-13T14:59:35Z

[Term]
id: MI:2322
name: Illumina dye sequencing
def: "This method generates several billion bases of accurate nucleotide sequence per experiment at low cost. Single molecules of DNA are attached to a flat surface, amplified in situ and used as templates for synthetic sequencing with fluorescent reversible terminator deoxyribonucleotides. Images of the surface are analysed to generate high-quality sequence." [PMID:18987734]
subset: PSI-MI_slim
synonym: "illumina sequencing" EXACT PSI-MI-short []
synonym: "solexa sequencing" EXACT PSI-MI-alternate []
is_a: MI:2321 ! high-throughput sequencing
created_by: pporras
creation_date: 2018-11-13T15:23:38Z

[Term]
id: MI:2323
name: kiss
def: "KISS (KInase Substrate Sensor) is a protein complementation technology that allows in situ analysis of protein-protein interactions in intact mammalian cells. In this method, which is derived from MAPPIT (mammalian protein-protein interaction trap), the bait protein is coupled to the kinase domain of TYK2, while the prey protein is fused to a fragment of the gp130 cytokine receptor chain. Bait and prey interaction leads to phosphorylation of the gp130 anchor by TYK2, followed by recruitment and activation of STAT3, resulting in transcription of a STAT3-dependent reporter system. This approach enables the identification of interactions between proteins, including transmembrane and cytosolic proteins, and their modulation in response to physiological or pharmacological challenges." [PMID:25154561, PMID:29855964]
subset: PSI-MI_slim
synonym: "kinase substrate sensor" EXACT PSI-MI-alternate []
synonym: "KISS" EXACT PSI-MI-alternate []
synonym: "kiss" EXACT PSI-MI-short []
is_a: MI:0090 ! protein complementation assay
created_by: pporras
creation_date: 2019-04-02T09:58:26Z

[Term]
id: MI:2324
name: dbsnp
def: "dbSNP contains human single nucleotide variations, microsatellites, and small-scale insertions and deletions along with publication, population frequency, molecular consequence, and genomic and RefSeq mapping information for both common variations and clinical mutations." [PMID:11125122]
subset: PSI-MI_slim
synonym: "dbSNP" EXACT PSI-MI-alternate []
synonym: "dbsnp" EXACT PSI-MI-short []
xref: search-url: "https://www.ncbi.nlm.nih.gov/snp/${ac}"
is_a: MI:0447 ! feature database
created_by: pporras
creation_date: 2019-04-02T10:52:06Z

[Term]
id: MI:2325
name: nanoluc luciferase protein tag
def: "NanoLuc luciferase (Nluc) is a small (19 kDa), highly stable, ATP independent, bioluminescent protein derived from the luciferase complex of the deep-sea shrimp O. gracilirostris." [PMID:22894855]
subset: PSI-MI_slim
synonym: "NanoLuc" EXACT PSI-MI-alternate []
synonym: "nanoluc luciferase" EXACT PSI-MI-alternate []
synonym: "nluc" EXACT PSI-MI-short []
synonym: "NLuc" EXACT PSI-MI-alternate []
is_a: MI:1205 ! luciferase tag
created_by: pporras
creation_date: 2019-04-11T14:07:06Z

[Term]
id: MI:2326
name: nanoluc-n
def: "The n-terminus of the nanoluc luciferase protein, fused to a protein of interest for use in the split luciferase complementation assay." []
subset: PSI-MI_slim
synonym: "N-terminal fragment of nanoluc luciferase" EXACT PSI-MI-alternate []
synonym: "nluc-n" EXACT PSI-MI-short []
is_a: MI:2325 ! nanoluc luciferase protein tag
created_by: pporras
creation_date: 2019-04-11T14:14:54Z

[Term]
id: MI:2327
name: nanoluc-c
def: "The c-terminus of the nanoluc luciferase protein, fused to a protein of interest for use in the split luciferase complementation assay." []
subset: PSI-MI_slim
synonym: "C-terminal fragment of nanoluc luciferase" EXACT PSI-MI-alternate []
synonym: "nluc-c" EXACT PSI-MI-short []
is_a: MI:2325 ! nanoluc luciferase protein tag
created_by: pporras
creation_date: 2019-04-11T14:16:59Z

[Term]
id: MI:2328
name: snap tag
def: "The SNAP-tag protein is an engineered version of the ubiquitous mammalian enzyme AGT, encoded in humans by the O-6-methylguanine-DNA methyltransferase (MGMT) gene. The tag is a 182 residues polypeptide with self-labeling activity that accepts O6-benzylguanine derivatives." [PMID:12725859]
subset: PSI-MI_slim
synonym: "snap tag" EXACT PSI-MI-short []
synonym: "SNAP tag" EXACT PSI-MI-alternate []
is_a: MI:0507 ! tag
created_by: pporras
creation_date: 2019-04-23T10:19:29Z

[Term]
id: MI:2329
name: hydrophobic interaction chromatography
def: "Hydrophobic interaction chromatography (HIC) separates proteins according to differences in their surface hydrophobicity by utilizing a reversible interaction between these proteins and the hydrophobic surface of a HIC matrix." [PMID:27730562]
subset: PSI-MI_slim
synonym: "hic" EXACT PSI-MI-short []
synonym: "HIC" EXACT PSI-MI-alternate []
is_a: MI:0091 ! chromatography technology
created_by: pporras
creation_date: 2019-04-23T13:40:51Z

[Term]
id: MI:2330
name: sumo tag
def: "Covalent attachment of the small ubiquitin-like modifier (SUMO) protein as a fusion protein." [PMID:19107426]
subset: PSI-MI_slim
synonym: "sumo tag" EXACT PSI-MI-short []
synonym: "SUMO tag" EXACT PSI-MI-alternate []
is_a: MI:0240 ! fusion protein
created_by: pporras
creation_date: 2019-07-11T15:50:31Z

[Term]
id: MI:2331
name: phage library
def: "A bacteriophage library of genes encoding proteins or peptides fused to a phage coat protein that are expressed on the surface of the phage virion." [PMID:9661810]
subset: PSI-MI_slim
is_a: MI:0342 ! sample process
created_by: pporras
creation_date: 2019-07-11T15:54:51Z

[Term]
id: MI:2332
name: g1 spin label
def: "Paramagnetic molecule formed by a gadolinium complex based on 4-mercaptomethyl-dipicolinic acid (4MMDPA) attached to a cysteine side chain." [PMID:25438671]
synonym: "g1 spin label" EXACT PSI-MI-short []
synonym: "g1-spin label" EXACT PSI-MI-alternate []
synonym: "Gd3+-4MMDPA tag" EXACT PSI-MI-alternate []
is_a: MI:0845 ! spin label
created_by: pporras
creation_date: 2019-07-11T16:04:14Z

[Term]
id: MI:2333
name: mutation with complex effect
def: "A change in a sequence or structure in comparison to a reference entity due to a  insertion, deletion or substitution event that has a complex effect over the interaction when compared with the wild-type. A complex effect is such that cannot be described in increasing, decreasing, causing, disrupting or no effect terms." []
subset: PSI-MI_slim
is_a: MI:0118 ! mutation
created_by: pporras
creation_date: 2019-07-11T16:17:45Z

[Term]
id: MI:2334
name: luminescence donor
def: "Fluorophore or luminiscence source which emits electromagnetic radiation of given wavelength." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0495 ! experimental role
created_by: pporras
creation_date: 2019-07-11T16:26:29Z

[Term]
id: MI:2335
name: luminescence acceptor
def: "Fluorophore able to absorb the electromagnetic radiation at given wavelength from a specific luminescence donor, then re-emit its own characteristic fluorescence. The luminescence donor may or may not be a fluorophore it self." [PMID:14755292]
subset: PSI-MI_slim
synonym: "luminescence accept" EXACT PSI-MI-short []
is_a: MI:0495 ! experimental role
created_by: pporras
creation_date: 2019-07-11T16:26:47Z

[Term]
id: MI:2336
name: luminescence acceptor donor pair
def: "Pair of luminescence donor-fluorophore or fluorophores attached to the same molecule used in a bret or fret  experiment to observe the details of conformational  changes." [PMID:14755292]
synonym: "luminescence acceptor-donor pair" EXACT PSI-MI-alternate []
is_a: MI:0495 ! experimental role
created_by: pporras
creation_date: 2019-07-11T16:27:09Z

[Term]
id: MI:2337
name: chemiluminiscence donor
def: "Luminiscence source which emits electromagnetic radiation of given wavelength through a chemical process." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:2334 ! luminescence donor
created_by: pporras
creation_date: 2019-07-11T16:37:54Z

[Term]
id: MI:2338
name: electron tomography
def: "Three-dimensional (3D) reconstruction of single, transparent objects from a series of projection images from a tilt series recorded with a transmission electron microscope." [PMID:12160704]
subset: PSI-MI_slim
synonym: "3D-EM-tomo" EXACT PSI-MI-short []
is_a: MI:0410 ! 3D electron microscopy
created_by: pporras
creation_date: 2019-07-17T13:23:36Z

[Term]
id: MI:2339
name: electron microscopy 3D single particle reconstruction
def: "Three-dimensional (3D) reconstruction of single, transparent objects from a collection of images of randomly oriented particles recorded with a transmission electron microscope." [PMID:12160704]
subset: PSI-MI_slim
synonym: "3D-EM-single" EXACT PSI-MI-short []
is_a: MI:0410 ! 3D electron microscopy
created_by: pporras
creation_date: 2019-07-22T13:39:03Z

[Term]
id: MI:2340
name: electron microscopy 3D helical reconstruction
def: "Three-dimensional (3D) reconstruction of helical objects from a collection of fiber images recorded with a transmission electron microscope." [PMID:12160704]
subset: PSI-MI_slim
synonym: "3D-EM-helical" EXACT PSI-MI-short []
is_a: MI:0410 ! 3D electron microscopy
created_by: pporras
creation_date: 2019-07-22T13:40:56Z

[Term]
id: MI:2341
name: luminescence transmitter
def: "Fluorophore able to absorb the electromagnetic radiation at given wavelength from a specific luminescence donor and then act as a donor via re-emission of its own characteristic fluorescence. The luminescence donor may or may not be a fluorophore itself." [PMID:14755292]
subset: PSI-MI_slim
is_a: MI:0495 ! experimental role
created_by: pporras
creation_date: 2019-07-22T13:51:08Z

[Term]
id: MI:2342
name: partial identity match
def: "Reference to the corresponding object in another database. Correspondence  is partial, so the objects are similar but explicitly not identical." [PMID:14755292]
subset: PSI-MI_slim
synonym: "partial match" EXACT PSI-MI-short []
synonym: "similar object in an external resource" EXACT PSI-MI-alternate []
is_a: MI:0353 ! cross-reference type
created_by: pporras
creation_date: 2019-07-30T15:05:43Z

[Term]
id: MI:2343
name: genomic coordinates
def: "Coordinates of a reference DNA sequence in the genome, providing information about the chromosome name, start and end of the sequence, optionally including the strand as well if it applies." [PMID:14755292]
subset: PSI-MI_slim
synonym: "genomic coord" EXACT PSI-MI-short []
is_a: MI:0666 ! participant attribute name
is_a: MI:0668 ! feature attribute name
created_by: pporras
creation_date: 2019-07-30T16:06:16Z

[Term]
id: MI:2344
name: rhea
def: "Rhea is an expert curated resource of biochemical reactions designed for the annotation of enzymes and genome-scale metabolic networks and models. Rhea uses the ChEBI (Chemical Entities of Biological Interest) ontology of small molecules to precisely describe reactions participants and their chemical structures. All reactions are balanced for mass and charge and are linked to source literature, metabolic resources and other functional vocabularies such as the enzyme classification of the NC-IUBMB." [PMID:27980062]
synonym: "Rhea" EXACT PSI-MI-alternate []
xref: search-url: "https://www.rhea-db.org/reaction?id=${ac}"
is_a: MI:0461 ! interaction database
created_by: pporras
creation_date: 2019-10-28T17:31:37Z

[Term]
id: MI:2345
name: pa tag
def: "The protein is fused to a 12-residue peptide segment (GVAMPGAEDDVV) derived from human podoplanin PLAG domain for which antibodies are available." [PMID:24480187]
subset: PSI-MI_slim
synonym: "PA tag" EXACT PSI-MI-alternate []
is_a: MI:0507 ! tag
created_by: pporras
creation_date: 2019-10-30T16:29:27Z

[Term]
id: MI:2346
name: target tag
def: "Protein is fused to a 21 amino acid residues-long peptide (YPGQYPGQYPGQYPGQYPGQV) derived from human PAR-4 N-terminal peptide. The final sequence of the peptide resulted from optimization involving mutagenesis and repetition of the original reference sequence in order to maximize affinity with the P20.1 antibody." [PMID:20566373]
subset: PSI-MI_slim
synonym: "tandemly-arranged recognition motif combined with gentle elution technology tag" EXACT PSI-MI-alternate []
synonym: "TARGET tag" EXACT PSI-MI-alternate []
is_a: MI:0507 ! tag
created_by: pporras
creation_date: 2019-10-30T16:41:19Z

[Term]
id: MI:2347
name: biorxiv
def: "bioRxiv is a free online archive and distribution service for unpublished preprints in the life sciences, operated by Cold Spring Harbor Laboratory. Articles are not peer-reviewed, edited, or typeset before being posted online.\nhttp://biorxiv.org/" []
subset: PSI-MI_slim
synonym: "bioRxiv" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "\\d+.\\d+/[a-zA-Z0-9\\.\\:]+"
xref: search-url: "https://www.biorxiv.org/content/${ac}"
is_a: MI:0445 ! literature database
created_by: pporras
creation_date: 2019-10-30T16:49:12Z

[Term]
id: MI:2348
name: sequential bret-fret
def: "In sequential BRET-FRET (BRET combined with FRET) bioluminiscence generated by a luciferase triggers acceptor excitation by BRET and subsequent energy transfer to a FRET acceptor. This technique can identify multimolecular complexes through detection of the resulting fluoresecence." [PMID:18587404]
subset: PSI-MI_slim
synonym: "Sequential BRET-FRET" EXACT PSI-MI-alternate []
synonym: "sret" EXACT PSI-MI-short []
synonym: "SRET" EXACT PSI-MI-alternate []
is_a: MI:0051 ! fluorescence technology
created_by: pporras
creation_date: 2019-10-30T17:07:01Z

[Term]
id: MI:2349
name: clinvar
def: "ClinVar is a freely accessible, public archive of reports of the relationships among human variations and phenotypes, with supporting evidence. \nhttps://www.ncbi.nlm.nih.gov/clinvar" [PMID:29165669]
synonym: "ClinVAR" EXACT PSI-MI-alternate []
xref: id-validation-regexp: "[0-9]+"
xref: search-url: "https://www.ncbi.nlm.nih.gov/clinvar/variation/${ac}"
is_a: MI:0447 ! feature database
created_by: pporras
creation_date: 2019-10-30T17:16:41Z

[Term]
id: MI:2350
name: empiar
def: "EMPIAR, the Electron Microscopy Public Image Archive, is a public resource for raw, 2D electron microscopy images. The purpose of EMPIAR is to provide easy access to state-of-the-art raw data to facilitate methods development and validation, which will lead to better 3D structures. It complements the Electron Microscopy Data Bank (EMDB), where 3D volumes are stored, and uses the fault-tolerant Aspera platform for data transfers.\n\nhttps://www.ebi.ac.uk/pdbe/emdb/empiar/" [PMID:27067018]
subset: PSI-MI_slim
synonym: "Electron Microscopy Public Image Archive" EXACT PSI-MI-alternate []
synonym: "EMPIAR" EXACT PSI-MI-alternate []
synonym: "empiar" EXACT PSI-MI-short []
xref: id-validation-regex: "EMPIAR-[0-9]{5}"
xref: search-url: "https://dx.doi.org/10.6019/${ac}"
is_a: MI:0936 ! emdb
created_by: pporras
creation_date: 2019-12-17T09:31:30Z

[Term]
id: MI:2351
name: enhancer gene
def: "A gene whose genetic perturbation enhances the phenotype resulting from a different genetic perturbation." [PMID:14755292]
subset: PSI-MI_slim
synonym: "enhancer" EXACT PSI-MI-short []
is_a: MI:0495 ! experimental role
created_by: pporras
creation_date: 2020-02-12T14:19:39Z

[Term]
id: MI:2352
name: enhanced gene
def: "A gene whose genetic perturbation phenotype is enhanced by a different genetic perturbation." [PMID:14755292]
subset: PSI-MI_slim
synonym: "enhanced" EXACT PSI-MI-short []
is_a: MI:0495 ! experimental role
created_by: pporras
creation_date: 2020-02-12T14:21:40Z

[Term]
id: MI:2353
name: epistatic gene
def: "A gene whose genetic perturbation masks the phenotype resulting from a different genetic perturbation." [PMID:14755292]
subset: PSI-MI_slim
synonym: "epistatic" EXACT PSI-MI-short []
is_a: MI:0495 ! experimental role
created_by: pporras
creation_date: 2020-02-12T14:22:57Z

[Term]
id: MI:2354
name: hypostatic gene
def: "A gene whose genetic perturbation phenotype is masked by a different genetic perturbation." [PMID:14755292]
subset: PSI-MI_slim
synonym: "hypostatic" EXACT PSI-MI-short []
is_a: MI:0495 ! experimental role
created_by: pporras
creation_date: 2020-02-12T14:24:11Z

[Term]
id: MI:2355
name: adp deribosylase assay
def: "Measurement of the substraction of one or more ADP-ribose moieties to molecules." [PMID:14760721]
subset: PSI-MI_slim
synonym: "adp deribosylase" EXACT PSI-MI-short []
synonym: "adp deribosylation" RELATED []
is_a: MI:0415 ! enzymatic study
created_by: pporras
creation_date: 2020-06-02T17:02:11Z

[Term]
id: MI:2356
name: adp deribosylation reaction
def: "Involves the substraction of one or more ADP-ribose moieties to proteins. Reaction that can affect Arg, Cys, Glu, Arg and Asn residues." [GO:0051725, PMID:14755292, RESID:AA0168, RESID:AA0169, RESID:AA0231, RESID:AA0237, RESID:AA0295]
subset: PSI-MI_slim
synonym: "adp de-ribosylation" EXACT PSI-MI-alternate []
synonym: "adp deribosylation" EXACT PSI-MI-short []
is_a: MI:0414 ! enzymatic reaction
created_by: pporras
creation_date: 2020-06-02T17:02:30Z

[Term]
id: MI:2357
name: kcat/km
def: "This parameter represents the rate of the reaction at negligible substrate concentration, indicating how the velocity varies according to how often enzyme and substrate combine." [PMID:14755292]
subset: PSI-MI_slim
synonym: "catalytic efficiency" EXACT PSI-MI-alternate []
synonym: "kcat/km" EXACT PSI-MI-short []
synonym: "specificity constant" EXACT PSI-MI-alternate []
is_a: MI:0640 ! parameter type
created_by: pporras
creation_date: 2020-06-30T16:04:54Z

[Term]
id: MI:2358
name: mirbase
def: "A searchable database of published miRNA sequences and annotation. Each entry in the miRBase Sequence database represents a predicted hairpin portion of a miRNA transcript (termed mir in the database), with information on the location and sequence of the mature miRNA sequence (termed miR). Both hairpin and mature sequences are available for searching and browsing, and entries can also be retrieved by name, keyword, references and annotation. All sequence and annotation data are also available for download.\n\nHomepage: http://www.mirbase.org/" [PMID:30423142]
subset: PSI-MI_slim
synonym: "miRBASE" EXACT PSI-MI-alternate []
xref: search-url: "http://www.mirbase.org/cgi-bin/mirna_entry.pl?acc=${ac}"
is_a: MI:0461 ! interaction database
created_by: pporras
creation_date: 2020-06-30T17:05:08Z

[Term]
id: MI:2359
name: ds rna
def: "RNA that consists of two base pairing strands. The 2 nucleotide chains are held together by hydrogen bonds between base pairs of nucleotides." [PMID:14755292]
subset: PSI-MI_slim
synonym: "double stranded ribonucleic acid" EXACT PSI-MI-alternate []
is_a: MI:0320 ! ribonucleic acid
created_by: pporras
creation_date: 2020-07-01T16:15:22Z

[Term]
id: MI:2360
name: beta gal tag
def: "Protein is fused to beta-galactosidase, and the measure of this enzyme activity can be taken as indicative of presence of protein." [PMID:10459153]
subset: PSI-MI_slim
synonym: "beta gal tag" EXACT PSI-MI-short []
synonym: "beta-galactosidase tag" EXACT PSI-MI-alternate []
is_a: MI:0365 ! enzyme tag
created_by: pporras
creation_date: 2020-07-01T16:18:26Z

[Term]
id: MI:2361
name: Split Intein-Mediated Protein Ligation
def: "Bait protein is fused to a standard protein fusion tag and an intein fragment, prey a with a different protein fusion tag and the complementary intein fragment. The bait and prey are co-expressed in a cell line where the association of bait and prey brings the intein fragments into close proximity, allowing them to reconstitute a fully functional intein, which then catalyzes its own excision and the concurrent ligation of the bait and the prey peptides (as well as the standard protein fusion tags). The resulting spliced protein can be resolved by regular western blot analysis due to its altered mobility, while the presence of the standard protein fusion tags allows visualization or purification of protein using regular biochemical techniques." [PMID:32415080]
subset: PSI-MI_slim
synonym: "simpl" EXACT PSI-MI-short []
synonym: "SIMPL" EXACT PSI-MI-alternate []
is_a: MI:0090 ! protein complementation assay
created_by: pporras
creation_date: 2020-12-02T11:31:51Z

[Term]
id: MI:2362
name: ic tag
def: "Intein C-terminal fragment tag, commonly used in SIMPL and related methods." []
subset: PSI-MI_slim
synonym: "IC tag" EXACT PSI-MI-alternate []
synonym: "intein c-terminal fragment tag" EXACT PSI-MI-alternate []
is_a: MI:0507 ! tag
created_by: pporras
creation_date: 2020-12-02T11:39:05Z

[Term]
id: MI:2363
name: in tag
def: "Intein N-terminal fragment tag, commonly used in SIMPL and related methods." []
subset: PSI-MI_slim
synonym: "IN tag" EXACT PSI-MI-alternate []
synonym: "intein n-terminal fragment tag" EXACT PSI-MI-alternate []
is_a: MI:0507 ! tag
created_by: pporras
creation_date: 2020-12-02T11:40:48Z

[Term]
id: MI:2364
name: proximity
def: "Coincident occurrence of molecules within very close proximity (in the nanometer range), detected through molecule-level resolution methodology, but from which a physical interaction among those molecules cannot be inferred." []
subset: PSI-MI_slim
synonym: "close-contact colocalization" EXACT PSI-MI-alternate []
synonym: "neighbourhood interaction" EXACT PSI-MI-alternate []
is_a: MI:0403 ! colocalization
created_by: pporras
creation_date: 2020-12-02T11:42:19Z

[Term]
id: MI:2365
name: fluorescent protein-protein interaction-visualization
def: "FluoPPI system (Fluorescent Protein-Protein Interaction-visualization):-FLUOPPI utilises the formation of fluorescence foci whereby the interacting proteins of interest are genetically fused with either a tetramerizing fluorescent protein (FP-tag) or an assembly helper tag (Ash-tag). The incorporation of these tags onto a pair of interacting proteins  enables the formation of intensely bright foci when co-expressed in mammalian cells. In these foci the FP-tag induces the fused protein to form a tetramer that can now interact with up to 4 copies of the Ash-tagged partner protein. The cognate interacting protein also forms an oligomer through the Ash tag, which in turn can interact with multiple copies of the FP-fused partner protein. The potential of both constructs to interact with multiple copies of each other enable large foci incorporating the fluorescent protein to form, which can be clearly observed when imaging the cell." [PMID:31784573<new dbxref>]
synonym: "fluoppi" EXACT PSI-MI-short []
synonym: "FluoPPI" EXACT PSI-MI-alternate []
is_a: MI:0428 ! imaging technique
created_by: pporras
creation_date: 2020-12-07T17:35:40Z

[Typedef]
id: contains
name: contains
namespace: PSI-MOD
def: "'Entity A' contains 'Entity B' implies that 'Entity B' is a part of the structure of 'Entity A'." [PubMed:18688235]
comment: The inverse relationship to "part of".
is_transitive: true

[Typedef]
id: derives_from
name: derives from
namespace: PSI-MOD
def: "'Entity A' derives_from 'Entity B' implies that 'Entity A' is chemically derived from 'Entity B'." [PubMed:18688235]
is_transitive: true

[Typedef]
id: has_functional_parent
name: has functional parent
namespace: PSI-MOD
def: "'Entity A' has_functional_parent 'Entity B' implies that 'Entity B' has at least one chacteristic group from which 'Entity A' can be derived by functional modification." [PubMed:18688235]
comment: This relationship indicates that the formula and mass of the child are not inherited from the mass of the parent.
is_transitive: true

[Typedef]
id: part_of
name: part of
def: "'Entity A' part_of 'Entity B' implies that 'Entity A' is a part of the structure of 'Entity B'." [PubMed:18688235]
is_transitive: true
