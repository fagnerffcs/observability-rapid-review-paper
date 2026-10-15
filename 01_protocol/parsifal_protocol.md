# Rapid Review Protocol — Parsifal Export

**Title:** A Rapid Review on Observability of Cloud-Native Applications using Kubernetes  
**Authors:** Fagner Silva, Jackson Raniel, Vinícius Cardoso Garcia  
**Registration Date:** October 2025  
**Management Tool:** Parsifal (parsifal.co)  

---

## 1. Study Objectives
To identify the state of the art in observability of Kubernetes-based cloud-native applications, systematically mapping the essential architectural components, open-source toolchains, reference frameworks, and research gaps reported in the scientific literature.

## 2. Research Questions (RQs)
- **RQ01:** What are the essential components of an observability architecture for Kubernetes-based cloud-native applications?
- **RQ02:** What reference architectures or observability frameworks for Kubernetes-based cloud-native environments have been proposed in the literature?
- **RQ03:** What open-source tools are used or recommended to implement the different components of a Kubernetes-based observability architecture for cloud-native applications?
- **RQ04:** What research gaps and future directions have been identified in the literature on open-source observability architectures for Kubernetes-based cloud-native applications?

## 3. Search Strategy

### Main Search String:
`("cloud native" OR "cloud-native" OR "microservices") AND ("observability" OR "monitoring" OR "tracing" OR "logging" OR "metrics" OR "events") AND ("kubernetes" OR "k8s") AND ("open source" OR "open-source")`

### Queried Scientific Databases:
1. **IEEE Xplore** (`114` records retrieved)
2. **ACM Digital Library** (`88` records retrieved)
3. **SpringerLink** (`68` records retrieved)
4. **ScienceDirect** (`42` records retrieved)

### Temporal Scope:
January 2018 – October 2025

### Database-Specific Query Adaptations:
- **IEEE Xplore:** `(("Full Text & Metadata":"cloud native" OR "cloud-native" OR "microservices") AND ("Full Text & Metadata":"observability" OR "monitoring" OR "tracing" OR "logging" OR "metrics" OR "events") AND ("Full Text & Metadata":"kubernetes" OR "k8s") AND ("Full Text & Metadata":"open source" OR "open-source"))`
- **ACM DL:** `+("cloud native" "cloud-native" microservices) +("observability" "monitoring" "tracing" "logging" "metrics" "events") +("kubernetes" "k8s") +("open source" "open-source")`
- **SpringerLink:** `("cloud-native" OR "microservices") AND ("observability" OR "monitoring") AND ("kubernetes") AND ("open source")`
- **ScienceDirect:** `("cloud-native" OR "microservices") AND ("observability" OR "telemetry") AND "kubernetes" AND "open source"`

## 4. Eligibility Criteria

### Inclusion Criteria (IC):
- **IC01:** Primary focus on Observability for software systems.
- **IC02:** Context related to cloud-native applications or microservices.
- **IC03:** Discussion of Kubernetes as the orchestration platform.
- **IC04:** Focus on open-source observability tools, frameworks, or reference architectures.
- **IC05:** Articles published between January 2018 and October 2025.
- **IC06:** Articles written in English.

### Exclusion Criteria (EC):
- **EC01:** Duplicated papers indexed across multiple scientific databases.
- **EC02:** Informal commercial gray literature (e.g., marketing whitepapers, corporate blog posts, vendor product documentation).
- **EC03:** Focus exclusively on traditional monitoring or operational infrastructure without addressing multi-pillar observability concepts.
- **EC04:** Studies where observability or Kubernetes is only mentioned tangentially as a secondary utility without structural evaluation.
- **EC05:** Short papers, posters, and extended abstracts with fewer than 4 pages lacking methodological details or validation.

*Note on Preprints and Academic Theses:* In alignment with evidence-based Software Engineering standards for Rapid Reviews (Cartaxo et al., 2018), peer-reviewed preprints and institutional master's/doctoral theses recovered through citation network expansion (Connected Papers / snowballing) were considered eligible when presenting rigorous, complete empirical or architectural models fulfilling IC01–IC04, strictly distinguishing them from commercial opinion material discarded under EC02.

## 5. Screening and Conflict Resolution Protocol
1. **Title and Abstract Screening:** Conducted by the primary researcher against IC/EC criteria.
2. **Full-Text Review:** Independent evaluation of candidate papers by the primary researcher, with cross-validation and dual-check by a secondary author.
3. **Conflict Resolution:** Cases of ambiguity were discussed in joint consensus meetings with the senior supervising researcher to reach unanimous decisions.

## 6. Data Extraction Fields
For each included primary study, the following fields were systematically extracted:
- Study Identification (Title, Authors, Year, Venue, Database)
- Addressed Research Questions (RQ01, RQ02, RQ03, RQ04)
- Telemetry Pillars Covered (Metrics, Logs, Traces, Events)
- Open-Source Tools and Frameworks Analyzed
- Architectural Patterns and Lifecycle Phases
- Research Gaps, Overhead Constraints, and Limitations
- Proposed Future Directions and Roadmap Pillars
