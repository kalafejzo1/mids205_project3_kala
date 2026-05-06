# MIDS 205 Project 3: Facebook Social Circles Community Detection in Neo4j

## Team Members
- Kala Fejzo
- Prince Hossain
- Chul Park

## Project Overview
This project uses the SNAP Facebook Social Circles dataset to model a social network in Neo4j and demonstrate how graph databases can support community detection, influencer identification, and engagement analysis for a social media platform.

Our business case is a social app that wants to improve:
- feed ranking
- group recommendations
- community discovery
- influencer identification
- user engagement analysis

We use the Facebook ego network dataset as the base graph and add a small synthetic engagement layer to make the analysis more realistic.

## Business Case
A social media platform wants to better understand user communities and identify influential users within those communities. By modeling friendships and engagement as a graph, the platform can:
- detect user communities such as fitness, music, politics, fashion, and gaming
- recommend relevant groups or content to users based on their network structure
- identify influential users for moderation, outreach, or content promotion
- better understand user engagement patterns

## Dataset
Primary dataset:
- SNAP Facebook Social Circles: https://snap.stanford.edu/data/egonets-Facebook.html

Core files:
- `all_edges.csv` — friendship connections
- `all_circles.csv` — ground-truth friend groups
- `all_features.csv` — anonymized user features
- `all_egofeatures.csv` — ego user feature vectors
- `all_featnames.csv` — feature metadata

Synthetic layer:
- `users.csv`
- `friend_edges.csv`
- `posts.csv`
- `likes.csv`

## Graph Design

### Nodes
- `User`
- `Post`
- `Circle`

### Relationships
- `FRIENDS_WITH`
- `MEMBER_OF`
- `POSTED`
- `LIKED`

This graph structure allows us to analyze both social structure and engagement behavior within Neo4j.

## Graph Data Science Algorithms
We use Neo4j Graph Data Science algorithms including:
- **Betweennes Centrality** to identify users who act as bridges connecting different parts of the network
- **Shortest Path** to measure how quickly information can spread between users
- **Degree Centrality** to identify influential users within communities

These algorithms help demonstrate how graph methods can support recommendation systems, user segmentation, and influencer detection.

## Why Neo4j
Neo4j is a strong fit for this project because social network data is highly connected. A graph database makes it easier to model relationships between users, communities, and engagement activity than a relational database would. Neo4j also supports graph-native algorithms, which makes it well suited for community detection and influencer analysis.

## Repository Structure
- `code/` — Neo4j loading scripts, graph creation scripts, and graph algorithm code
- `slides/` — final presentation PDF
- `README.md` — project overview and instructions

## How to Run
1. Download the SNAP Facebook Social Circles dataset.
2. Prepare the CSV files needed for Neo4j import.
3. Load the nodes and relationships into Neo4j.
4. Run the graph data science algorithms.
5. Review the results for communities, central users, and engagement patterns.

## Key Outputs
This project demonstrates:
- creation of a graph in Neo4j
- execution of graph data science algorithms
- identification of communities within a social network
- detection of influential users based on graph structure

## Notes
This project is academic work created for MIDS 205. The goal is to demonstrate how Neo4j can be used to solve business problems involving social network analysis and community detection.
