# 2026-09-18 revision notes

This branch refines the DBCLS BioHackathon 2026 manuscript narrative while preserving the original ZebraSeek results and Figs. 1–6.

## Core story

The original ZebraSeek contribution remains the starting point: specialist phenotype, facial, semantic and LLM candidate generators feed a traceable LLM-based integration and verification workflow, with the 74-case benchmark showing complementary retrieval, candidate retention and higher observed final recall than the individual components.

The hackathon work addresses an upstream limitation of that architecture. The current workflow only forwards the top five candidates from each specialist tool. Because the modalities are handled by heterogeneous tools and their internal scores are not assumed to be directly calibrated across tools, downstream ZebraSeek effectively receives ranked disease candidates rather than one common multimodal score space. A correct diagnosis below the accepted depth is therefore invisible to later integration.

The expanded Phenopacket Store v0.1.27 analysis is used to characterize this practical candidate-acquisition bottleneck: how much coverage is lost at shallow depth, how quickly coverage grows with deeper rankings, and how many unique diseases must then be passed to downstream verification. Fixed-depth, zero-shot LLM and oracle-reference conditions are basic baselines for this problem, not final claims of an adaptive solution.

Structured outputs were also strengthened so that candidate IDs and provenance fields, including source URLs where available, remain attached through ranking and verification.

## Remaining author-supplied information

The manuscript still needs author confirmation or additional records for:

- the original 74-case matching procedure, inclusion/exclusion rules, disease counts and GestaltMatcher Database release;
- exact HPO version, input serialization, missing/negative-finding handling and image preprocessing;
- exact component versions/endpoints, Mondo/embedding versions, GPT model snapshot and run dates;
- exact zero-shot candidate-depth prompts, action space, sampling/retry rules, and why one expanded instance is missing (n=461);
- the evaluated ZebraSeek commit/release and archived structured-output schemas/prompts;
- patient-wise analysis or split details for the expanded 368-patient / 462-image dataset;
- ethics/exemption, image-use permissions and external-service data-processing statement;
- funding, author contributions, competing interests, corresponding author and ORCIDs.

Event metadata have been resolved as BH26JP / DBCLS BioHackathon 2026 / Matsuyama, Japan, 2026. The public ZebraSeek implementation repository is now linked in Code availability.
