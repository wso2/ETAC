


<h1 align="center">The Role of Blockchain in Future Integrations
</center></h1>

<p align="center">
<i>
Version 0.8<br/>
</i>
</p>

# Abstract

_This paper critically evaluates blockchain-based integration use cases, their feasibility, and their timelines. The paper identifies 30-plus blockchain-based use cases for integration and four architecture patterns. Notably, each use case we identified can be implemented using one of the architecture patterns. Then the paper discusses how challenges posed by blockchains, such as performance limitations and risks such as immutability, and unpredictability, would affect above architecture patterns._  
 
_Based on the analysis, the paper concludes that the use cases around "Auditable History or Workspace" and "Identity and Access Management(IAM)" patterns are feasible and use cases around the "Registry and Marketplace" pattern are feasible for moderate-size deployments. Further, the paper concludes that the "Smart Contracts and Managed Things" pattern will need several breakthroughs before becoming feasible._

# Introduction 

The rise of Bitcoin digital currency kick-started blockchain. Beginning as a virtual currency, Bitcoin and blockchain were initially synonymous. The US government identified Bitcoin as property in 2011 and as a currency in 2013 [1]. Other governments soon followed suit (Hobbes [1]). Some major Internet companies started accepting Bitcoin (e.g., Zynga, Expedia, Dell, Microsoft). However, while the perceived value of cryptocurrencies as investments fueled blockchain’s popularity, blockchain technology also soon found other use cases. 

As early as 2013, it was observed that the impact of the blockchain algorithm, which underlies Bitcoin, extends beyond pure cryptocurrency. 
>Blockchain as defined here is a technology that creates and maintains a shared, decentralized, append-only immutable digital record that uses hash chains and operates according to a consensus algorithm<sup>[1](#proof)</sup>. 

The real value of blockchains is this shared, decentralized, and immutable ledger, which enables decentralized trust and other use cases. New blockchain implementations, such as Ethereum in 2015 and Hyperledger in 2016, soon followed blockchain. 

Although Bitcoin has drawn mixed responses from regulators and policy-makers, blockchain technology has been received favorably. For example, many US states have passed or are preparing legislation supporting blockchain [7]. Similarly, the Bank of England has explored the ideas around using blockchains for central bank digital currency [25].  

Blockchain has the potential to transform many fields, including enterprise integration, which is a subset of the wider challenge of distributed systems integration. Integration in this context is about connecting different systems, some of which may come from different trust domains. Most current integrations assume the trust between parties has been already established.  For example, this might happen through a contract between both parties facilitated by a lawyer. For example, this may happen by creating accounts for all parties participating in a transaction. Blockchain’s ability to broker ad-hoc trust among previously untrusted parties can help us to build flexible, more extensive integrations for a reduced cost by replacing previous mechanisms for establishing trust. 

This paper discusses the applications of blockchain within the systems integration domain. However, to ground this discussion, we first need to clearly define integration. 

>We define integration as _the use of technologies that enable typically diverse systems within or between organizations to work together in order to achieve common business goals_.  


Organizations share many functions, such as accounting, sales, and customer relationship management. Most of these organizations build their systems by combining specialized tools that can handle those functions. Initially, organizations depended on one vendor to support all those functions and make sure the tools worked together. This did not last. 

On one hand, systems have grown complex over time, making it impossible for a vendor to support all of the functions and tools required by an organization. As a result, different vendors have chosen to specialize in specific areas of functionality. However, functionally often overlaps, resulting in redundant data. On the other hand, enterprises in today’s connected economy have to communicate as a part of their operations. For example, flights may involve multiple airlines, and the airlines need to coordinate to effectively serve customers. For this reason, tools supporting the functions of an organization need to talk to each other, share data, and accept or delegate work. 

As the definition of integration explains, integration connects different systems within and outside the organization, and it builds an integrated system. Therefore, integration has evolved to become a necessary and crucial factor in organizations’ design and often a strong predictor of user productivity. 

Our main goal is to sort between the hype and the real potential of blockchain within the integration domain. With that in mind, we wanted to take a systematic approach to evaluate it. To do so, we have used the Emerging Technology Analysis Canvas (ETAC) [[27](https://github.com/wso2/ETAC/blob/master/ETAC.md)] framework, which takes a broad view of emerging technology by probing impact, feasibility, risks and future timelines.

We draw the following conclusions as a result of our analysis:
* There are integration use cases in both public and private blockchain.
* We identified four architecture pattern candidates that support those use cases: IAM, Auditable History or Workspace,  Registry or Marketplace, and Smart Contracts and Managed Things.
* We find that the IAM and Auditable History or Workspace patterns are feasible.
* We believe that use cases around the Registry and Marketplace pattern are feasible for moderate-size deployments. 
* We predict that the Smart Contracts and Managed Things pattern will need to see a number of breakthroughs before it is feasible for most use cases. 

The remainder of this document is organized as follows. We have identified 30+ integration use cases that involves blockchain. After examining those integration use cases, the paper identifies four blockchain architecture pattern candidates. Most aforementioned blockchain-based integration use cases can be supported using one or combination of those pattern candidates. The paper then follows the narrative structure defined by the Emerging Technology Analysis Framework (ETAC) [27], which takes a broad view of emerging technology by probing impact, feasibility, risks and future timelines. 

We first discuss the opportunity, including the initial trigger and the current status of blockchain adoption. Then under impact, we identify six motivations for organizations to deploy blockchain and examine the associated impacts at both macro and micro level. Next we review the feasibility of the four architecture pattern candidates, as well as the ecosystem required to support them. Finally, in evaluating the future, we discuss the risks and timelines for each of the four architectures and associated use cases. 

# Opportunity 
## Trigger 
Although Bitcoin kick-started blockchain, it has had a minimal impact on integration. For example, some organizations have accepted payment through blockchain, but adoption has been limited, and several have withdrawn support for Bitcoin due to legal uncertainties. Moreover, there are many proofs-of-concepts, but there is no widely successful single application that acts as a trigger for integration use cases that involves blockchain. Generic blockchain use cases mostly motivate current activities in the integration area. 
## Players	
Today, there is a significant blockchain ecosystem, which is active and includes developers, miners, and investors. There are ongoing investments in this ecosystem from IBM (HyperLedger), Google (e.g. [[8](https://www.bloomberg.com/news/articles/2018-03-21/google-is-said-to-work-on-its-own-blockchain-related-technology)]), Microsoft, financial institutions, banks, governments, and the United Nations, among many others. Gartner has listed [32 blockchain platforms](https://www.gartner.com/reviews/market/blockchain-platforms) in a report [9]. Blockchain has also received significant venture capital (VC) investments (e.g. [[10](https://www.coindesk.com/Bitcoin-venture-capital/), [11](https://www.investopedia.com/news/top-blockchain-startups-watch-2018/), [12](https://www.forbes.com/sites/haroldstark/2017/12/12/keep-an-eye-on-these-blockchain-startups-throughout-2018/#6e3efd0413e6
)]).  

Furthermore, many researchers are exploring new blockchain-based research ideas. Examples of that research are available from the [curated paper list on blockchain](https://github.com/decrypto-org/blockchain-papers)[13]. Unlike many other emerging technologies, large tech giants—such as Google, Facebook, Amazon, and Apple—have little influence on blockchain although some investments are underway. Moreover, although there are many players, the core technology is still under active development, and consequently, the playing field is still wide open.

In the area of blockchain-based integration, two key players are [Hyperledger](https://www.hyperledger.org/) and [Ethereum](https://www.ethereum.org/). Integration vendors are also exploring blockchain opportunities. 

## Drivers
Trust is the critical driver of the blockchain. Other drivers, such as decentralization and transparency, are also aspects of trust. For example, decentralization is required due to lack of trust on a single party and transparency is a mechanism to establish trust. 

On one hand, individuals and organizations need to interact with others who are not known, and establishing trust with those parties is a crucial requirement. Currently, trust is built through rules, professionals (e.g., lawyers), and brokers. This process is both slow and expensive. Blockchain could potentially establish trust faster and cheaper. 

On the other hand, centrally operated systems or services have gained deep mistrust. Examples of such systems include ecosystems, such as Facebook or a land registry operated by few. Blockchain enables us to decentralize those operations and limit the potential harm done by a few rogue individuals or organizations. 

Furthermore, in some cases, blockchain enables us to keep immutable records of everything that happens, which can be audited and verified as needed. The knowledge about immutability both reassures participants and deters potential attackers. 

In the case of integration, there are three key drivers of blockchain: 
* Historically improved communication, integration, and trust have improved efficiencies of systems. 
* An affordable trust mechanism lets more and more systems to be loosely coupled, reducing the effort required for changes. 
* Replacing current trust alternatives and associated frauds can lead to significant savings. 

The next section explores the impact of blockchain on integration.

# Impact
After brainstorming potential blockchain use cases, we identified 30-plus blockchain-based integration use cases, which are discussed in [Blockchain-based Integration Usecases](https://github.com/wso2/ETAC/blob/master/blockchain/blockchain-usecases.md)[31]. This section examines the common trends seen across those use cases, as well as specific use cases when relevant.  

## Macro Impact
At the macro level, it is important to understand the role of blockchain when used for integration, its network effects and interactions, and related disrupters. 

### The Role of Blockchain in Future Integrations
Integration enables different systems to work together. Since different systems cannot always trust each other, systems need to establish trust before taking part in an integration scenario. Currently, this trust establishment happens via out of bound means and implemented as credentials used in the communication. Outside of the blockchain world, most integrations are static and occur between parties that already have a trust relationship, since establishing this relationship is expensive. 

Blockchain improves efficiencies by supporting the seamless establishment of trust between participants (humans or systems) in an integration scenario and making participants accountable for their actions. 

The following discussion assumes a scenario in which blockchain-based identifiers, known as  Distributed Identifiers (DIDs) [[14](https://w3c-ccg.github.io/did-spec/)]) and verifiable claims[[15](https://www.w3.org/TR/verifiable-claims-data-model/)] defined by W3C specifications are widely adopted. The former enables everyone to have a DID to which their verifiable claims can be attached. Verifiable claims are proof of claims provided by authorities. For example, “Department of Motor Vehicles” (or DMV) may issue a verifiable claim confirming your name and address while the university you attended may issue a claim confirming your degree. 

For example, if blockchain is widely adopted, each actor will have an identifier (DID) and verifiable claims that will confirm this person’s attributes. When a party wants to interact with an unknown one, he can verify the unknown party securely and cheaply using verifiable claims. Before blockchain, this kind of transaction was handled by third parties or lawyers. Blockchain enables these transactions, instantly and without facilitators, bringing efficiency to trusted transactions. Furthermore, seamless trust establishment allows participants to assume less about each other, making them more loosely coupled while being even more integrated. 

Additionally, an immutable ledger can capture the activities of participants, which can be audited and cannot be refuted. This activity record creates strong incentives for participants to behave responsibly. For instance, if an internet service requires a verifiable claim asserting that a user’s identity needs to be issued by the country he lives in, it stops him from creating a new account if he was banned due to misconduct. 

Moreover, the wide adoption of blockchain establishes a higher bar of accountability. For example, many individuals or organizations would refuse to do business with entities that can't establish their trust via blockchain. Also, stakeholders will demand a higher level of visibility about activities from governments, organizations, and even individuals when they act in the public sphere. Donors want to track how their money is spent, and citizens will request details how their tax money is spent. More and more, those future transactions will be integrations and require high levels of accountability. 

## Network effects and Interactions
Let’s now examine the network effects and interactions associated with blockchain.

Network effects are often a strong predictor of success. We say a system has a “network effect” when its value to users increases as the number of users of the system increases. Systems with a network effect builds momentum as they grows, which is the reason for their strong correlation with success. However, it is worth noting that even systems with network effects fail if they fail to create a critical mass.

Following are some examples of use cases enabled by blockchain that have network effects. Primary advantage they offer over existing implementations are two fold where they are decentralized and one or few actors can’t control them. 

* With API marketplaces and dynamic API discovery and composition, as the number of users increases, more and more new APIs will come in, which will attract more users. 
* More users with verifiable claims make it more likely you can do ad-hoc transactions with a user you run into, which increases the value of verifiable claims, causing more users to obtain verifiable claims.   
* More people in a reputation system (e.g., consider a doctor ranking system) will increase the value of reputation, causing more users to ask for reputation as a part of background checks; in turn more people will join the reputation system. 

In looking at interactions between other technologies, the API economy can be affected significantly by a blockchain-based API marketplace and support for dynamic API composition. For instance, let’s assume you travel frequently. If there is a standard interface for accessing a wifi network, based on your location, your device can obtain a connection by finding a wifi provider from an API marketplace, negotiating the term, and carrying out the payment. (See [use cases "API marketplace" and "Support for dynamic API composition”](https://github.com/wso2/ETAC/blob/master/blockchain/blockchain-usecases.md)][31].)

## Disrupters 
The broad adoption of blockchain will significantly change established systems, products, and solutions. For example, if blockchain-based DIDs are widely adopted, most identity systems can simply lookup DIDs from the blockchain or keep a cache of DIDs and update them periodically.  Furthermore, since the identity systems no longer need to store passwords, complications associated with password management would be significantly reduced. 

In addition, verifiable claims can replace most authorization use cases, including the majority of security token use cases and access control lists. The implementations may periodically read the verifiable claims and keep a cache for performance reasons. Verifiable claims also can replace certification authorities and federation use cases. Importantly, blockchain reduces or removes several fraud scenarios, since with blockchain: 
* We have a robust alternative to traditional approaches for establishing trust, which are often weak points in security and used by attackers. 
* All transactions and data are protected by strong cryptography, which is very hard to break
* Changes happen following predefined protocol and all actions are auditable.

Consequently, blockchain will reduce exploitable parts in transactions and make them auditable, which likely to make current fraud detection and prevention solutions obsolete. In world with wide adoption of blockchain, the future fraud scenarios are likely to be of a very different nature. It also will make available a wide array of data about transactions, which will enable us to detect much more complicated forms of fraud. Consequently,  fraud detection and prevention solutions will have to adopt. 

Furthermore, blockchain will significantly simplify many auditing use cases, disrupting current auditing solutions. For example, it may be possible for an organization to record hashes of their financial records in a blockchain instead of doing a full audit, which enables regulators to verify records later if needed. 

Moreover, blockchain can simplify standards and regulations by removing intermediaries. For instance, consider a hotel, which is certified by various travel associations via periodic inspections. Instead, they may choose to ask employees and subcontractors to record their quality control activities in a blockchain instead of hiring inspectors. This enables the associations to verify the records directly as needed.  Similarly, blockchain may also replace some supply chain auditing and tracking as exemplified by the shipping logistic solution announced by IBM [16].  
 
Finally, blockchain may help consortiums to automate some of their processes through the use of a decentralized autonomous organization (DAO), which is a collection of smart contracts. For example, while establishing a consortium, founding members can agree with the rules of operations and implement them as smart contracts. This will make consortium cheeper to operate and impartial. 


# Micro Impact
At a micro level, blockchain provides organizations several benefits, most notably in terms of competitive advantage, financial performance, and supply chain efficiency. 

## Competitive Advantage
Competitive advantages provided by blockchain include the ability to collaborate more effectively, foster trust, avoid coercion, and enhance customer experiences. 

* **Collaborate More Effectively:** Blockchain allows better collaborations with partners, suppliers, and other parties. For example, we can use smart contracts to coordinate a project that involves multiple organizations. Furthermore, a blockchain-based, shared auditable workspace enables various parties to share information or work together.  

* **Foster Trust:** Some companies face higher hurdles for engendering trust due to the nature of their business. A case in point is a provider of organic foods that needs to validate it meets regulatory definitions of “organic.” These and other organizations often use a combination of certification and inspections to demonstrate quality. Blockchain provides a potentially more cost-effective alternative for establishing trust in those cases. 

* **Avoid Coercion:**. Some organizations face risks because they can be coerced into actions that harm them. For example a government agency may demand changes to software behavior for surveillance purposes. A good example of this is that a certificate authority (CA) can be coerced into creating false certificates [17]. By setting up the certificates in a blockchain, where parties outside the company must approve the changes, a company reduces the probability of coercion by giving up the ability to arbitrarily change behaviors.  

* **Enhance Customer Experiences:** In some cases, enterprises may choose to implement blockchain to bring new benefits to customers. For instance, we can use blockchain to digitally hande vehicle ownership and maintenance records, which may create a better secondary market for used automobiles. Another example is issuing verifiable claims based on a user’s interaction with the organization, which then can be used to establish trust. 

## Financial Benefits
The main financial benefits are derived from the use of Blockchain to enhance the efficiency of operations, thereby removing either the middleman or mechanisms currently required to enforce quality and integrity. Among examples are identity, access management (IAM) and auditing use cases, [tracking software lifecycles, managing copyrights via smart contracts, and control objects via smart contracts](https://github.com/wso2/ETAC/blob/master/usecases/blockchain-usecases.md)[31].  

## Supply Chain Efficiency 
As discussed earlier, blockchain allows more effective collaboration with partners, suppliers, and other parties by supporting mechanisms, such as smart contracts and auditable workspaces.

The six impacts described earlier become motivations for deploying blockchains. For more information, please refer to [Blockchain-based Integration Use Cases](https://github.com/wso2/ETAC/blob/master/usecases/blockchain-usecases.md), which describes the use cases under each motivation. 


# Feasibility 
To understand the feasibility of blockchain for integration, we need to understand “how to implement the use cases” and their Quality of Service (QoS) characteristics. After exploring the possible implementations of these use cases, we have identified four architecture patterns for blockchain-based systems. Most use cases can be implemented using one or combination of these architecture patterns. Let’s look at each of them in detail. 

## Four Architecture Patterns Candidates for Blockchain
Following describes patterns according to template described by Aleksandra Tešanovic [[6](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.123.1162&rep=rep1&type=pdf)]. 

### Architecture Pattern for IAM. 
**Context:** IAM environments include many users and service providers. IAM systems give each user an account and set of capabilities enabling users to go to service providers, demonstrate their ownership of accounts, and then receive services based on their capabilities.

**Forces:** Need to implement a decentralized IAM environment where a single rogue user or few users can’t significantly affect the system. 

**Solution:** Proposed pattern candidate uses World Wide Web Consortium (W3C) DID specification[14] and W3C Verifiable Claims [15] specification in the following manner. 

<p align="center">
<img src="https://github.com/wso2/ETAC/blob/master/images/blockchain4Integration/IAM-RefArch.png" alt="drawing" width="450" align="center"/></br>
<p align="center">Figure 1: Blockchain-based IAM Architecture Pattern</p>
</p>


Let’s assume Alice needs an identity (DID, which is a unique identifier). As shown by the figure for creating a new DID, Alice creates an entry in the blockchain, which includes a randomly generated identifier, a link to the repository with her profile data, and a hash of the profile data. The user profile contains a public key and a set of verifiable claims. The generated random identifier now becomes Alice’s DID because only she owns the private key corresponds to the public key. 

Verifiable claims are delegation tokens [18] signed by a competent authority. The creator also records them in a blockchain together with the hash of the claim in a manner similar to the DID. 

Alice obtains the verifiable claims in the first place by going to authorities. For example, the department of personal registration or equivalent is the proper authority for verifiable claims of name, address, and date of birth. Assuming authorities issue verifiable claims, Alice first   demonstrates her ownership of the DID using a challenge-response-protocol. Then she submits requests for verifiable claims for her attributes, which may, for example, include her name, address, degree, and date of birth. To update her profile data, Alice will add a new entry to the blockchain with a new hash of the profile. 

In the challenge-response-protocol, the validator generates a random seed, encrypts it using Alice’s public key, and then challenges Alice to demonstrate that she has the private key by decrypting the encrypted seed. Since Alice has the private key, she must be the owner of the DID. 

A different user or an organization (authenticator), Bob, who wants to identify Alice, first receives the DID from Alice, read all entries related to that DID from the blockchain, retrieve Alice’s profile data, and verify them. Bob can verify the identity of Alice (identification) again using challenge-response-protocol. Then Bob can confirm the verifiable claims and be assured that the claims about Alice are true. 

We can layer most IAM use cases on top of this architecture pattern. For example, we can achieve access control either by issuing verifiable claims for actions we want users to perform or by only accepting users who have certain properties (e.g. age, job description, group membership) in their verifiable claims. An implementation may choose to cache relevant subsets of the profile data in a database to improve performance.  

### Architecture Pattern for Auditable History or Workspace

**Context:** A two or more parties perform transactions or works together and their activities need to be recorded in an indisputable manner. 

**Forces:** Need to implement a decentralized audit log or a workspace where a single rogue user or few users can’t significantly affect the system. 

**Solution:** The proposed system records activities and creates entries in the blockchain for those records. The entry contains the hash of activity records, and therefore, the records can’t be disputed later. 


<p align="center">
<img src="https://github.com/wso2/ETAC/raw/master/images/blockchain4Integration/Auditable-Workspace-RefArch.png" alt="drawing" width="450" align="center"/></br>
<p align="center">Figure 2: Blockchain based Auditable History or Workspace Architecture Pattern</p>
</p>




For example, let’s assume Alice wants to pay a tax. Tax Server accepts the payment application, creates a digital receipt, records its hash in the blockchain, and sends the receipt to Alice. Alice can verify the receipt by calculating the hash and checking against the value stored in the blockchain. After this, Bob can’t deny the receipt because the receipt hash and time are recorded in the blockchain. 

If the activities are numerous, there may be a need to workaround blockchain performance limitations. Therefore, some implementations may record a hash of several activity records as a block instead of a single activity record. 


### Architecture Pattern for Registry or Marketplace
**Context:** A registry is a collection of data entries that can be searched and retrieved over the network. A market place is a registry that allows users to buy the services or products represented by data entries. For example, a registry may be a catalog of available APIs. 

**Forces:** Need to implement a decentralized environment where a single rogue user or few users can’t significantly affect the system. 

**Solution:** The proposed pattern works as follows. 

<p align="center">
<img src="https://github.com/wso2/ETAC/raw/master/images/blockchain4Integration/Registry-RefArch.png" alt="drawing" width="450" align="center"/></br>
<p align="center">Figure 3: Blockchain based Registry Architecture Pattern</p>
</p>



Let’s first consider a registry. With the proposed architecture, when a user issues a registry update (to add or modify an entry), the client records the change in the blockchain. If data in the update is large, the blockchain record may contain a link to the data and a hash value of the data. If data stored in the registry needs to be amended, the registry client adds a new record to the blockchain with amended information. 

In the diagram above, each user has a registry client running in the local machine (e.g. laptop or phone). Each registry client reads the update records from the blockchain, verifies the update data against the hash included in the records, and reconstructs the most current view of records from updates. For example, by reading blockchain records about APIs, their additions, amendments, and removals, the registry client can create a view that shows current APIs included in the registry. To avoid having to read and verify all records every time the registry is used, clients might store data in a database and index it. The client should periodically check the blockchain and update the registry. 

Blockchain works well as a "service marketplace," since the same service may be sold many times. However, due to performance limitations, blockchain-based marketplaces are not suitable for items that can be sold only once. 

To illustrate, the functionality of a blockchain-based registry, let’s look at when Alice wants to subscribe to "weather news service” in the blockchain marketplace. When she submits her request, the registry creates credentials for the service and shares it with Alice. The payment may happen in one of several ways: using Bitcoins, via a smart contract where payments are made on a time basis, or by some out-of-bound means. 


### Architecture Pattern for Smart Contracts and Managed Things

Under this pattern we consider two cases. First consider smart contracts and the second consider a common special case of smart contracts: “Managed Things”. 

#### Smart Contracts Pattern 

**Context:** Multiple users want to abide by a contract, described as an executable program. Contract undergoes state transitions as per conditions defined in the contract, and at a given time, everyone can agree on the current status of the contract.  

**Forces:** need to implement an environment where a single rogue user or few users can’t significantly affect the system. 

**Solution:** Smart contacts are part of blockchain technologies and supported by blockchain implementations, such as Ethereum. A contract is described using a smart contract language and distributed to all participants. As conditions defined in the contract changes, each participant executes the contract and records the current status in the blockchain using the consensus algorithm. 

#### Managed Things Pattern 

**Context:** We need to track the ownership of real world smart things. Here smart things are real world objects that are capable of running computing logic within them. Owner is allowed to control and perform actions on the real world things.  Also owner may transfer his ownership to someone else. 

**Forces:** need to implement an environment where a single rogue user or few users can’t significantly affect the system. 

**Solution:** Following describes the implementation of the pattern using Car as the managed thing as an example. 

<p align="center">
<img src="https://github.com/wso2/ETAC/raw/master/images/blockchain4Integration/ManagedThingsRefArch.png" alt="drawing" width="450" align="center"/></br>
<p align="center">Figure 4: Blockchain based Managed Things Architecture Pattern</p>
</p>




We can implement a blockchain for a managed thing, in this case a car, in two steps. First, the manufacturer records the DID and public key of the owner of the car. When ownership changes, the owner adds a new record in the blockchain specifying the new owner. Second, when checking for ownership, the car first retrieves all records in the blockchain and verifies that each record is added by the owner at that time. This is done by checking the public key of the user who wrote the record against the public key included in the previous ownership record. The last owner in this valid chain is the current owner. 

After determining the owner, the car logs in the current owner, Alice, by retrieving her public key and carrying out a challenge-response-protocol-based login with Alice’s phone, which has Alice’s private key.  

Such a system reduces the risks associated with remotely controlled artifacts.  For example, in a non-blockchain implementation, someone with access can change the ownership of your car. However, with the blockchain-based model, to remotely control the car, a would-be attacker must change the ownership record in the blockchain, which is very hard to achieve without being the owner. 

However, it is hard to stop someone who has access to the “thing” from physically changing the logic running inside (e.g., by replacing firmware of the car). One solution to this problem is to build some form of self-destruct that triggers when tampering into the artifact is detected.

For example, Alice buys the car from Bob using a smart contract that pays Bob and updates the ownership of the vehicle. After the transaction, Alice walks to the car, which reads Alice’s DID from the phone, retrieves her public key, authenticates her using a challenge-response-protocol by communicating with the phone that has Alice’s private key, verifies her ownership, and unlocks the car.  

# Technical Merit 

As discussed by the blockchain outlook [19], blockchain-based systems face four challenges: 
* Limited scalability and latency
* Limited privacy
* Storage constraints
* Unsustainable consensus

The following table explores the impact of the four challenges on the use cases described earlier. The columns represent the architecture pattern, challenges of public deployments, and challenges of private or consortium deployments.

|Architecture Pattern Candidate| Challenges of public deployments |Challenges of Private or Consortium deployments |
|---|---|---|
|IAM Use cases|Limited scalability, latency and unsustainable consensus (e.g. global ID use case). Otherwise, feasible for most cases. </br>Limited privacy - OK (data stored outside)</br> Storage constraints - OK (data is small)| Feasible because these use cases usually needs limited scale and performance. &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|Auditable History or Workspace|Limited scalability, latency, and unsustainable consensus. Otherwise, feasible for most use cases.  </br>Limited privacy is not a concern. (data stored outside) .</br>Storage constraints is not a concern. (data can be archived and retired time to time)|Feasible because these use cases usually needs limited scale and performance.|
|Registry, Market place|Limited scalability, latency, and unsustainable consensus. The global marketspace use case may be challenging. Limited privacy is not a concern. Private data can be stored outside and replaced with a hash of the data. Storage constraints is not a concern as data is small. |Feasible because these use cases usually needs limited scale and performance.|
|Smart contracts & Managed Things|N/A|Feasible because these use cases usually needs limited scale and performance.|

<p align="center">Table 1: Technical Challenges by the Architecture Pattern</p>

As the table depicts, most private or consortium use cases are not affected by the challenges. 

Also, most IAM use cases can work with the current performance limits of the blockchain. For example, IAM use cases update an entry only when a new account is added or when verifiable claims are updated, both of which are not frequent for an individual user. For the read access, the systems may keep a cache and update it by listening to blockchain updates. Write updates can be batched and entered into the blockchain as a single batch. This is acceptable because even current non-blockchain implementations often require few hours for the creation of a new account to take effect.

As the table indicates, auditable history and workspace can generate a significant amount of data for some use cases. We can handle this by batching data, and for each batch, we can store a single hash in the blockchain. Therefore, scalability is not a concern for most use cases. Workspace-based use cases will need smart contracts, but those use cases are most likely to take place in a private blockchain. Hence, each workspace would be independent, letting end users run many copies as needed. 

Among marketplace use cases, the ability to process subscriptions in a global marketplace may face scalability limits. One option may be to take subscriptions off the blockchain and charge the user by other means. 

Smart contracts are mostly private and do not need substantial deployments. "Managed things" use cases are also mostly private, and most of the workload reads from the blockchain (e.g., authenticate the user to a car), which can be supported via caches. 

As discussed in [the blockchain outlook](https://doi.org/10.7287/peerj.preprints.27529v1), notwithstanding significant challenges, there is hope. The best minds are working on these problems, and progress is being made. For example, Zamani [[20](https://blog.acolyer.org/2018/12/07/rapidchain-scaling-blockchain-via-full-sharding/)] presented a RapidChain algorithm that can perform 7,500 transactions/second. Furthermore, Kasireddy [[21](https://hackernoon.com/blockchains-dont-scale-not-today-at-least-but-there-s-hope-2cb43946551a)] discusses some of the approaches used to handle these problems, and the web page “[Curated Blockchain Papers](https://github.com/decrypto-org/blockchain-papers)[22]” cites many relevant publications that examine how to address some of the issues.

## Tools, Ecosystem, & Skills 

To date, developers with blockchain skills have been scarce. However, fueled by high demand, many developers are acquiring blockchain skills. We have observed students master key ideas within a few weeks, and many education materials are already available. Therefore, we believe skills will not be a significant obstacle. 

However, tooling support for blockchain at this point remains limited. Most use cases assume that they will be handled by highly technical users (Kasireddy [[24](https://tools.ietf.org/html/draft-ietf-oauth-use-cases-01)]). However, this can be fixed after the core technology has stabilized. 

Often integration use cases depend on middleware, where organizations run pre-built systems and make the necessary changes and configurations to suit their use cases. These decisions are driven by an analysis of the total cost of ownership. 

Currently, blockchain integration use cases are only possible for organizations that maintain a highly technical team to build and manage these systems. We might see middleware solutions for each of the four architecture patterns in the future, which will be available for most organizations to buy, extend and manage. 

However, the middleware approach does not always works. For example, the middleware approach has mostly failed in the case of Internet of Things (IoT) implementations where the required extensions are significant compared to the middleware, which only occupies a thin layer. In those use cases, organizations do better by outsourcing the development and management of the system to a systems integrator. The pros and cons of building blockchain integration solutions using middleware versus relying on a systems integrator are still evolving in this nascent market. 

Many public use cases such as ["decentralized API marketplace" and "improving supply chain visibility"](https://github.com/wso2/ETAC/blob/master/usecases/blockchain-usecases.md) require standards for governance and communication, since many parties are involved. This will ensure consistency, clarity and efficiency.

Among those standards, the most essential ones are related to identity and access management as they provide the fundamental underpinning for the rest of the use cases. W3C is already working on two IAM specifications: “DID” and “Verifiable Claims,” both of which are promising developments for blockchain adoption. 

Some other use cases only need an agreement between participating organizations. Examples of these include [information sharing across a group of companies; ecosystem-level, non-competitive critical services; multi-party projects or processes; multi-organization collaborations; and groups operating a consortium as a DAO](https://github.com/wso2/ETAC/blob/master/usecases/blockchain-usecases.md). These scenarios can work though defacto standards created by the two parties. However, that will create many competing standards that will be costly to reconcile. 

The absence of standards will continue to be a source of friction, particularly as organizations compete to create de-facto standards and build industry adoption around them. 

## Friction
In previously published [blockchain outllook](https://github.com/wso2/ETAC/blob/master/ETAC.md)[27], the authors have identified the following cases of friction: 
* An absence of methods for verifying and limiting risks
* A lack of governance around the blockchain code base (e.g., when and how it can be forked) 
* The complexity of many blockchain-based applications (e.g., smart contracts)
* A shortage of tools within current blockchain ecosystems to help users debug their applications

Most of the above risks stem from smart contracts ( see [blockchain outlook](https://github.com/wso2/ETAC/blob/master/ETAC.md) [27] for details). Among the four architecture patterns, the IAM and Auditable History or Workspace patterns does not use smart contracts. Therefore, none of the above risks apply. 

The subscription part of the "Registry or Marketplace" and "Smart Contracts and Managed Things" architecture patterns need custom smart contracts. Therefore, they are susceptible to all four frictions. 


# Future
## Risks


In previously published [blockchain outllook](https://github.com/wso2/ETAC/blob/master/ETAC.md)[27], the authors have identified several risks associated with blockchain: irrevocability, regulator absence, regulator response, unpredictability, and quantum cryptography. 

Among them, irrevocability is the risk induced by the immutability of blockchain: if a mistake is made, the transaction can’t be recalled. Most real-life scenarios support some form of “appeal,” and this is a concern for some use cases. 

Some of the use cases might significantly affect users and therefore come under the purview of government or industry regulators in the future, creating uncertainty. This is identified as “regulator response” in the table. 

Unpredictability refers to the lack of methods for verifying smart contracts and other complex blockchain-based interactions. 

Quantum cryptography refers to the impact of quantum computing—if widely available—where most current cryptographic techniques will become useless. However, those risks are no different than the risks on other systems already in operations. 

The following table explores the effects of the risks on blockchain use cases. The first column lists the architecture pattern; the second lists risks related to public blockchain deployments, and the third notes risks associated with private blockchain deployments. 


|Architecture pattern| Risks of Public deployments|Risks of Private or Consortium deployments| 
|---|---|---|
|Auditable History or Workspace|Regulator response (Use cases: Standards or Regulation Adherence, Information sharing across a group of companies)|Regulator response (Use cases: Standards or Regulation Adherence, Information sharing across a group of companies)|
|Smart contracts & Managed Things|N/A|Irrevocability|Unpredictability |</br>Regulator response ( [Use cases: Ecosystem-level non-competitive critical services, Global Reputation System)|
|IAM Use cases|Regulator response(due to privacy))|Regulator response (due to privacy)|
|Registry, Market place|Regulator response ([Use cases: Support health data kept in with a patient, Operating a Consortium as a DAO, Multi-party Projects or Processes](https://github.com/wso2/ETAC/blob/master/usecases/blockchain-usecases.md))|Regulator response ([Use cases: Support health data kept in with a patient, Operating a Consortium as a DAO, Multi-party Projects or Processes](https://github.com/wso2/ETAC/blob/master/blockchain/blockchain-usecases.md))|

<p align="center">Table 2: Risks by Architecture Patterns</p> 


Use cases other than Smart Contracts and Managed Things have well-defined behaviors and are not affected significantly by irrevocability. Any mistake may be corrected by adding a new entry to the blockchain. For example, any incorrect verifiable contract can be canceled by adding a new entry to the blockchain. 

However, as described in the outlook section, smart contract-based use cases—such as [consortium as a DAO, managing copyrights via smart contracts, and cloud-based transferable ownership](https://github.com/wso2/ETAC/blob/master/usecases/blockchain-usecases.md)—may be affected by irrevocability and unpredictability. For example, if a car’s ownership, which is implemented via the Managed Things pattern, is handed over to a third party by mistake, the transfer can only be revoked by the current owner. 

It is worth noting that only use cases affected by irrevocability and unpredictability are affected by the lack of a regulator. The table above lists the use cases that may require regulator involvement. 

# Timeline 
The following table summarizes observations and assesses the future of each architecture pattern and associated use cases. The columns list the architecture pattern, the challenges and risks for both public and private blockchain deployments, and the conclusion on where the patterns are best suited. In some instances, the conclusion will reference “EU-TRL,” which indicates the European Union Technology Readiness Level [[29](https://en.wikipedia.org/wiki/Technology_readiness_level)].


|Architecture Pattern|Public|Private or Consortium|Conclusion|
|---|---|---|---|
|IAM|**Risks:** Regulator response is possible due to privacy|Feasible<br/>**Risks:** Regulator response is possible due to privacy|Feasible for both public and private. Expected to take off within the next three years.<br/>EU-TRL 4-6|
|Auditable History or Workspace|Feasible<br/>**Risks:** Regulator response (e.g. Regulation Information sharing across companies)|Feasible for most use cases.<br/>**Risks:** Regulator response (e.g. Regulation Information sharing across companies)|Feasible for both public and private. Expected to take off within the next three years.<br/> EU-TRL 5-7|
|Registry or Markeplace|**Challenges:** Limited scalability and latency & Unsustainable consensus. <br/> **Risks:** Regulator response (e.g. [health data kept in with a patient,Multi-organizations Projects](https://github.com/wso2/ETAC/blob/master/usecases/blockchain-usecases.md))|Feasible<br/>**Risks:** Regulator response (e.g. [health data kept in with a patient, Multi-organizations Projects](https://github.com/wso2/ETAC/blob/master/usecases/blockchain-usecases.md))|Feasible for both public and private. <br/> EU-TRL 4-6<br/>Feasible for small deployments (e.g. throughput about 2-3 TPS).  Full support likely to take 5-10 years.| 
|Smart contracts & Managed Things|N/A|**Risks:** Irrevocability, Unpredictability, Regulator response| Mainly private<br/>|EU-TRL 2-4<br/>Breakthroughs needed on handling risks, which likely to take 5-10 years.|

<p align="center">Table 3: Future assesment of each Pattern</p>  


IAM and Auditable History or Workspace architecture patterns are feasible, and the only risk is regulator involvement. Among them, IAM shows the most promise due to the two W3C specifications handling DIDs and Verifiable Claims. We believe that we will start to see these applications within the next three years. 

Use of the Registry and Marketplace architecture pattern may face challenges related to performance, but it is feasible for moderate use cases. The Smart Contracts and Managed Things architecture pattern faces significant challenges due to the risks around irrevocability and unpredictability. 

# Blockchain for Integration ETAC
The following picture summarizes our assessment of blockchain for integration using the ETAC format.

<p align="center">
<img src="https://github.com/wso2/ETAC/blob/master/images/blockchain4Integration/ETAC-Blockchain-For-Integration-V2.png" alt="drawing"  align="center"/></br>
<p align="center">Figure 5: Blockchain for Integration ETAC</p>
</p>




# Conclusions
This paper evaluates blockchain-based integration use cases using the Emerging Technology Analysis Canvas (ETAC), a framework for critically analyzing emerging technologies. 

We first identified 30-plus blockchain-based use cases for integration by brainstorming with practitioners. By studying those use cases, we identified six motivations for an organization to deploy blockchain in the context of integration. Those motivations are better collaboration, ensuring trust, preventing coercion, providing new features for customers, improving efficiency, and optimizing supply chains. 

Further, while exploring the feasibility of blockchain for integration, we identified four architecture patterns. Notably, each use case we identified can be implemented using one of the architecture patterns. Then we discussed how challenges posed by blockchains, such as performance limitations and risks around immutability, and unpredictability, would affect the architecture patterns. 

We make the following conclusions as a result of our analysis:
* There are integration use cases in both public and private blockchain.
* We identified four architecture pattern candidates that support those use cases: IAM, Auditable History or Workspace,  Registry or Marketplace, and Smart Contracts and Managed Things.
* We find that the IAM and Auditable History or Workspace patterns are feasible.
* We believe that use cases around the Registry and Marketplace pattern are feasible for moderate-size deployments. 
* We predict that the Smart Contracts and Managed Things pattern will need to see a number of breakthroughs before it is feasible for most use cases. 


# References
1. Robert Hobbes' Zakon, Hobbes' Blockchain Timeline 0.1, https://www.zakon.org/robert/blockchain/timeline/
2. Melanie Swan, Blockchain: Blueprint for a New Economy, https://www.amazon.com/Blockchain-Blueprint-Economy-Melanie-Swan/dp/1491920491   
3. Anant Kadiyala, Nuances Between Permissionless and Permissioned Blockchains, https://medium.com/@akadiyala/nuances-between-permissionless-and-permissioned-blockchains-f5b566f5d483  
4. The Case for Permissioned Blockchains, https://blocksplain.com/2018/02/07/permissioned-blockchains 
5. Taylor Hatmaker, Senate Cryptocurrency Hearing strikes a cautiously Optimistic Tone, https://techcrunch.com/2018/02/06/virtual-currencies-oversight-hearing-sec-cftc-Bitcoin/
6. A Tešanovic, What is a Pattern?, http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.123.1162&rep=rep1&type=pdf, 2004 
7. Blockchain State Legislation, http://www.ncsl.org/research/financial-services-and-commerce/the-fundamentals-of-risk-management-and-insurance-viewed-through-the-lens-of-emerging-technology-webinar.aspx  
8. Olga Kharif and Mark Bergen, Google Is Working on Its Own Blockchain-Related Technology, https://www.bloomberg.com/news/articles/2018-03-21/google-is-said-to-work-on-its-own-blockchain-related-technology
9. Reviews for Blockchain Platforms, https://www.gartner.com/reviews/market/blockchain-platforms 
10. Blockchain Venture Capital, https://www.coindesk.com/Bitcoin-venture-capital/
11. Nathan Reiff, Top Blockchain Startups to Watch in 2018, https://www.investopedia.com/news/top-blockchain-startups-watch-2018/
12. Harold Stark, Keep An Eye On These Blockchain Startups Throughout 2018, https://www.forbes.com/sites/haroldstark/2017/12/12/keep-an-eye-on-these-blockchain-startups-throughout-2018/#6e3efd0413e6
13. Blockchain Papers, https://github.com/decrypto-org/blockchain-papers
14. Reed, D. et al. (2017). Decentralized Identifiers (dids). W3C, Credentials Community Group., https://w3c-ccg.github.io/did-spec/
15. Burnett, D. C. et al. (2017). Verifiable Claims Data Model. Verifiable Claims Working Group, W3C Editor’s Draft, https://www.w3.org/TR/verifiable-claims-data-model/
16. Maersk and IBM Introduce TradeLens Blockchain Shipping Solution, https://newsroom.ibm.com/2018-08-09-Maersk-and-IBM-Introduce-TradeLens-Blockchain-Shipping-Solution
17. How feasible is it for a CA to be hacked? https://security.stackexchange.com/questions/2268/how-feasible-is-it-for-a-ca-to-be-hacked-which-default-trusted-root-certificate 
18. Gasser, Morrie, and Ellen McDermott. "An Architecture for Practical Delegation in a Distributed System." Proceedings. 1990 IEEE Computer Society Symposium on Research in Security and Privacy. IEEE, 1990.
19. S. Perera, F. Leymann, P. Fremantle. 2019. A Use Case centric Survey of Blockchain: Status quo and Future directions. PeerJ Preprints, https://doi.org/10.7287/peerj.preprints.27529v1 
20. Zamani et al, RapidChain: scaling blockchain via full sharding, https://blog.acolyer.org/2018/12/07/rapidchain-scaling-blockchain-via-full-sharding/
21. Kasireddy, Blockchains don’t scale. Not today, at least. But there’s hope, https://hackernoon.com/blockchains-dont-scale-not-today-at-least-but-there-s-hope-2cb43946551a
22. Blockchain Papers, https://github.com/decrypto-org/blockchain-papers
23. Jesse Yli-Huumo and others, Where Is Current Research on Blockchain Technology?—A Systematic Review,https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5047482/
24. G. Fletcher, T. Lodderstedt, Z. Zeltsan, Internet-Draft: OAuth Use Cases, 2013, https://tools.ietf.org/html/draft-ietf-oauth-use-cases-01 
25. Why might some Central Banks issue their own Digital Currency? https://www.bankofengland.co.uk/-/media/boe/files/research/cbdc.pdf 
26. Bitcoin P2P e-cash paper, https://www.mail-archive.com/cryptography@metzdowd.com/msg09997.html
27. Srinath Perera, Emerging technology analysis canvas (ETAC). https://github.com/wso2/ETAC/blob/master/ETAC.md, 2018. 
28. Challenge Response Protocol, https://en.wikipedia.org/wiki/Challenge%E2%80%93response_authentication 
29. Europen Union Technology Readiness Level. ”https://en.wikipedia.org/wiki/Technology_readiness_level”
30. Decentralized Data: “Why Blockchain is meaningless and Trustless is everything”, https://hackernoon.com/decentralized-data-why-blockchain-is-meaningless-and-trustless-is-everything-318fd14d3827
31. Blockchain-based Integration Use Cases, https://github.com/wso2/ETAC/blob/master/usecases/blockchain-usecases.md




# Footnotes
<a name="proof">1. </a> These are commonly known as “proof-of-” algorithms, such as proof-of-work, proof-of-stake, proof-of-storage, etc. Other consensus algorithms that are also Byzantine Fault Tolerant have also been used [26].



# Original Authors
Original authors are Srinath Perera (srinath@wso2.com), Paul Fremantle (paul@wso2.com), Frank Leymann (frank@wso2.com). 

# Acknowledgments
Many thanks to Nuwan Dias, Kasun Indrasiri, Parbath Siriwardana, Miyuru Dayarathne, and Malith Jayasinghe from WSO2 who have provided significant and useful feedback.

# Help us improve ETAC
We welcome and appreciate any feedback, changes, or contributions. Please send a pull request, create a github issue, or send a mail to srinath@wso2.com.

To receive updates to ETAC and ETAC-based emerging technology analysis, please subscribe to our [Global Technology Outlook Updates Newsletter](https://wso2.com/subscribe/global-technology-outlook-update).

# About WSO2 and Our Research

In 14 years in business, and as the #1 Open Source integration and API management vendor, WSO2 continually invests in areas beyond products. Our Research for Integration team regularly produces our Global Technology Outlook (GTO) — an effort to identify emerging technology trends, classify them based on their potential, and assess a relevant subset of technologies in detail. We do so using our Emerging Technology Analysis Canvas (ETAC). Our research is public in an effort to maintain our commitment to openness, quality, innovation, and integration leadership. 



