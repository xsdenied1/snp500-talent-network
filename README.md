# Talent Flow Network Analysis of S&P 500 Companies

This project explores talent mobility between companies using network analysis techniques on LinkedIn-based job transition data. By treating firms as nodes and employee movements as directed edges, we investigate structural patterns, central actors, and industry-level communities.

## Overview

We constructed a directed and weighted network of employee transitions between firms to:

- Identify talent hubs and feeder companies  
- Analyze network centrality (degree, PageRank)  
- Detect communities of firms using clustering algorithms  
- Explore how industry affinity shapes talent flows  

## Key Analyses

### 1. Network Construction
- Nodes: 473 firms (mostly S&P 500)  
- Edges: 81,114 job transitions  
- Directional: from previous employer to new one  
- Weighted: normalized by source firm’s employee count  

### 2. Centrality Measures
- Degree centrality:
  - In-degree → talent attraction (e.g., IBM, Accenture)  
  - Out-degree → talent supply (e.g., AT&T, Bank of America)  
- PageRank:
  - Weighted and unweighted versions to reflect transition significance  
  - Highlights influential firms in the job market  

### 3. Regression Analysis
- Firm size (employee count) strongly predicts both in- and out-degree  
- Linear models explain ~50% of variation in degree centrality  

### 4. Community Detection
- Detected 10+ firm clusters using the Walktrap algorithm  
- Communities align closely with industry (e.g., tech, pharma, real estate)  
- Indicates strong intra-industry talent flow  

### 5. Assortativity by Industry
- Modest positive assortativity coefficient (~0.026) suggests firms slightly prefer connecting with same-industry peers  

## Tools Used

- R (igraph, dplyr, ggplot2)  
- LinkedIn-based job transition data  
- Company metadata with industry and employee size  

## Files

- `talent_flows.csv`: Raw edge list of job transitions  
- `linkedin_company_metadata.csv`: Firm-level attributes  
- `df_edges_with_weight.csv`: Edge list with normalized weights (migration per employee)  
- `talent_flow_network_analysis.Rmd`: Full R Markdown analysis script  
