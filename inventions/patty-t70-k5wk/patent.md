# Real-Time Graph-Based Bot Farm Detection Using Temporal Correlation and Semantic Clustering

## Abstract
A system and method for detecting coordinated bot farms in social media platforms by analyzing temporal activity patterns, semantic content similarity, and graph neighborhood correlations. The invention processes account activity logs in batches, builds dynamic graphs of correlated users using lag-sensitive hashing, clusters nodes by embedding vectors from deep neural networks, and flags clusters exceeding size and similarity thresholds for suspension. It operates at the platform level without new hardware.

## Problem
X platform experiences delayed detection of large bot farms exceeding 100,000 accounts because existing rules-based filters and single-account classifiers miss coordinated inauthentic behavior. Farms register accounts in batches, post similar AI-generated content on topics like energy policy with synchronized timing, and evade detection until manual review or external reports. This allows influence operations to persist for weeks, as seen in networks posting about data centers with minimal authentic engagement.

## Prior art
- US10389745B2, System and methods for detecting bots real-time, uses lag-sensitive hashing for correlation but lacks integration with semantic embeddings from neural networks for content clustering and platform-wide suspension triggers.
- CN111428116B, A detection method of Weibo social robot based on deep neural network, analyzes individual user behaviors with DNN but does not scale to graph-based farm detection across 200k accounts or handle temporal warping in coordinated posting.

## Summary of the invention
The invention comprises a pipeline that ingests platform activity streams, computes pairwise correlations with lag-sensitive hashing on post timestamps and text embeddings, constructs an undirected graph where edges exist for correlation scores above 0.75, applies community detection to identify clusters, and suspends accounts in clusters larger than 500 with average embedding cosine similarity above 0.85. It includes failure handling for sparse data by falling back to attribute-based scoring.

## Claims
1. A method for detecting bot farms comprising: receiving activity data for a plurality of accounts; computing temporal correlation scores using lag-sensitive hashing on post times; generating semantic embeddings via a deep neural network trained on platform text; building a graph with edges for scores exceeding 0.75; detecting clusters; and suspending accounts in clusters meeting size threshold of 500 and similarity threshold of 0.85.
2. The method of claim 1, further comprising batch processing every 3600 seconds to limit computational load.
3. The method of claim 1, wherein the deep neural network uses a transformer architecture with embedding dimension 768.
4. The method of claim 1, further comprising fallback to neighborhood attribute analysis when graph density falls below 0.1.
5. The method of claim 1, wherein suspension occurs only after human review queue insertion for clusters under 1000 accounts.
6. The method of claim 1, wherein the lag-sensitive hashing uses a window of 86400 seconds and 32 hash functions.

## Brief description of the drawings
FIG. 1 shows the system architecture and data flow with labeled components.

## Detailed description
The system receives activity logs from the platform database into ingestion module (10). Timestamps and text are extracted and fed to lag-sensitive hashing unit (20) configured with window parameter of 86400 seconds and 32 hash functions to compute correlation scores tolerant to timing shifts up to 3600 seconds. Parallel path sends text to transformer neural network (30) with embedding dimension 768 producing vectors normalized to unit length. Correlation scores above threshold 0.75 and cosine similarities above 0.85 trigger edge creation in graph builder (40) yielding undirected graph G with nodes as accounts. Community detection algorithm (50) partitions G into clusters. Cluster analyzer (60) flags any cluster with node count exceeding 500 and mean intra-cluster similarity above 0.85. Flagged accounts enter suspension queue (70) with batch interval of 3600 seconds. In failure mode of low graph density below 0.1 edges per node, fallback module (80) computes attribute scores on registration patterns and neighborhood overlap, suspending if score exceeds 0.9. All thresholds are tunable via configuration file with audit logs retained for 90 days. The system processes up to 10 million accounts per batch on standard server hardware with 128 GB RAM.