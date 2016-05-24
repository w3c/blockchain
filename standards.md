# Standards Criteria

In the context of this workshop, the following general criteria are relevant to identify when something is suitable for standardization (which is a particular approach to the larger goal of interoperability):

## Standardization Value and Readiness 

1. __Problem Statement__: Is there a clear problem statement that this would solve, for a significant number of people?
2. __Starting Point__: Is there a good starting point, such as a clear solution, or a set of competing solutions?
3. __Stakeholder Commitment__: Do we have the right stakeholders ready to commit to the work, including implementers who would deploy the feature, and individuals willing to write, review, and test the specification?

## W3C Focus and Fit 

For standardization at W3C specifically, the focus is on the Web, in three main areas:

* **Client-side** (browser-based) features, like markup languages, JavaScript APIs, or user-facing features
  * this is W3C's main focus
* **Data and formats**, such as interchange formats, vocabularies/ontologies, and languages to manipulate data
  * _note that this area is usually treated with some skepticism by browser makers_
* **Communication protocols** 
  * W3C does this much more rarely, typically only when there's a corresponding client-side API, and usually in partnership with IETF

#  Starting Points

## Joe Roets - Disney Notes on Blockchain Standardization

1. __What features could DLT add to the Web Platform?__
  * Secure distribution of data, i.e. Moving data to the edge/web service (lower latency and downtime)
  * Lightweight verification of data quality or information assurance at the endpoint
  * Ability to independently verify local data (e.g. authN/Z, configuration) with controlled risk (enterprise + trusted partner + external blockchain [Hyperledger or Bitcoin])
  * Real-time enterprise governance capabilities (e.g. in transactional information, configuration items, key management activities)
  * Micro-payment web service request applications
  
2. __What would we need to add to the Web Platform to enable DLT?__
  * For distributed data use cases, locally available network node or blockchain data (likely operated parallel)
  * For micro-payment applications, use of web service request components (e.g. 21.co marketplace headers HTTP_BITCOIN_MICROPAYMENT_SERVER and HTTP_RETURN_WALLET_ADDRESS)
  * Access to respective blockchain library(s)
  
3. __Some aspects are nearing the point where standardization would be warranted – such as:__
  * Proof/verification algorithms (e.g. PoW [SHA-256 v Scrypt v x11], PoS, proof of identity/trust, other proofs)
  * Abstraction of cryptographic libraries
  * Block verification structures
  * Consensus algorithm

IRT #3 above, it would be possible to create a foundation which defined pluggable component interfaces allowing the creation of custom blockchains with known best practice implementations to fit a given need. Most of these interfaces could theoretically be loosely defined today, and multiple implementations could readily be made available.

## Running List of Potential Candidates Areas for Standard Interoperation

The following list of potential candidate areas needing or greatly benefiting from standard interoperability was adapted and annotated by Dazza Greenwood from proposed workshop lightning talk topics proposed ([Issue #3](https://github.com/w3c/blockchain/issues/3) by Dan Buchner:


**Core technical components of blockchains and their overlap with the Web, such as:**

* Blockchain APIs, such as JavaScript or REST APIs **Perfect, as is**
* Blockchain primitives such as
  -  transaction initiation" **Maybe something like [IBM Event Ledger](https://www.ibm.com/developerworks/community/wikis/home?lang=en#!/wiki/W0e2f07da6e3a_404f_9eee_07686ea89ced) could be configured and applied to initiate transactions**
  - key signing, **Perfect** and 
  - wallet management **Sure, in principle, especially in contexts like web-based digital wallet transaction processing or status checking that requires some Blockchain read, prove or write but really depends on what wallet functions and what sorts of "management**"
* Ledger interchange formats and protocols **Perfect**
* Smart contracts and conditional execution contexts  **This item seems to become less relevant to the workshop the deeper one ventures into domain specific contexts ... which is where one must delve to distinguish whether a condition has been met by an event (or lack of one). For this item, the sweet spot may be standard messaging interfaces and/or standard message formats but not business processes, logic or rules.  

**Application areas, such as:**

* Identity, including:
  - privacy, 
  - security, and 
  - confidentiality factors  **To focus on areas relevant to the workshop, maybe one approach would be worth tracking to specific Blockchain enabled identity-related functional requirements from Fair Information Practices (eg as codified under EU law or US FERPA, HIPAA, FCRA, etc) and NSTIC/IDESG "Trust Framework" certification and assessment criteria**
* Rights expression and licensing **This would be a great target for standardization.  Especially with respect to title ownership rights to so-called "intangible property" and other digital assets**
* Decentralized processing, computing, and storage infrastructure" **Applications and data existing across distributed systems require standard interoperation...the three items are very broad**
* Voting systems **This is a good one"
