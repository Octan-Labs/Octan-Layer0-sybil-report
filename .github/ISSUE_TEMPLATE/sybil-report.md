---
name: Octan Sybil Report
about: Report Sybil Activity on LayerZero
title: "[Octan Sybil Report]"
labels: under review
assignees: LayerZero-GH

---

# Reported Addresses
Pleas contact us to get the full Octan Sybil list for free. Our list is disjointed with the published Initial List and different from other bounty hunters' Sybil lists.  
Octan is an onchain data analytics firm, building an onchain reputation ranking system.
Contact us via TG @paven86 or Twitter @OctanNetwork.  
Our website: https://octan.network/ 

# Reasoning
Sybil wallets are generated with a sole intention to optimize potential airdrops in the future, without a faithful orientation to continue using the protocol after airdrop. Sybils can apply sophisticated strategies to avoid detection, e.g. transferring funds from CEX hot wallets to multiple EOAs, making it difficult to link those wallets to a single entity. Sybils may resemble real users, hence, detecting them is a big challenge. However, we can draw several common characteristics of Sybils within a social graph (considering a blockchain as a social & economical graph made of addresses and transactions) as below.  
-	Sybils usually have poor connections with real users.  
-	Sybil wallets usually form cliques, loosely connected clusters, which are small and separated from the giant components. Giant components are connected, essential structures of any social graph, containing vast numbers of users who are mostly non-Sybils.  
From the observation above, by probabilistic approach, we can use a good reputation ranking system to score Sybil wallets with very low values. Then, low reputation score is an important indicator to detect Sybils.

# Detailed Methodology & Walkthrough
Our scope is detecting Sybil wallets interacted with Layerzero protocol within Ethereum blockchain. We use Reputation Ranking (adaptive Pagerank) as a probabilistic approach to classify Sybil wallets on Ethereum. Intuition of [Octan Reputation Ranking](https://docs.octan.network/octan-docs-en/overview/octan-reputation-solutions/reputation-ranking-system), in general, is to qualify and quantify social relationship and interactions within a blockchain transaction graph. Octan Labs published 3 research papers (about onchain Reputation Ranking) on international scientific journals and conferences.  
-	Compute 1-year reputation scores for all addresses on Ethereum only up to May 1st, 2024.  
-	Remove contracts and CEX wallets.  
-	Excluding wallets with NO transaction/interaction related to Layerzero. After this, we obtain Layerzero’s user wallets.  
-	Plotting a histogram of Layerzero’s wallets: reputation scores against Sybils on Ethereum got from the published [initial list](https://github.com/LayerZero-Labs/sybil-report/blob/main/initialList.txt).
![image](https://github.com/Octan-Labs/Octan-Layer0-sybil-report/assets/45308207/519e3002-2f54-44d2-bfe6-84209ff5e973)
Observing that Sybils usually have low Reputation Score (RS). We can infer that wallets near-zero RS are more likely Sybils. We will reduce the size of Layerzero wallets by onchain statistical indicators, then using AUROC and extrapolation to infer Sybils outside the initial list.
-	Excluding the initial list published by LayerZero.  
-	Sybil list contains wallets with RS range [0, K], where K is selected nearly zero to cover mostly the initial list.  


# Reward Address (If Eligible)
