


<h1 align="center">Technology Outlook: Blockchain </center></h1>

<p align="center">
<i>
Version 0.8<br/>
</i>
</p>

# Abstract

_This paper presents an assessment of blockchain technology based on the **Emerging Technology Analysis Canvas (ETAC)** to evaluate the drivers and potential outcomes. The ETAC is a framework to critically analyze emerging technologies._

_The assessment finds that blockchain can transform the world fundamentally. It is ready for limited applications in use cases such as digital currency, lightweight financial systems, ledgers, provenance, and disintermediation._

_However, it faces significant technical gaps in other use cases and needs at least 5-10 years to Sustaining the current level of effort (e.g. startups, research) until breakthroughs occur is challenging. We also find that the need and merits of decentralization compared to centralized and semi-centralized alternatives is not clear. Given the risk involved and significant potential returns, we recommend a cautiously optimistic approach to blockchain with the focus on concrete use cases._ 




# Introduction

This document presents our assessment of Blockchain technology. It uses the Emerging Technology Analysis Canvas (ETAC) [19], which is a framework to critically analyze emerging technologies. ETAC includes questions that bring out different aspects of an emerging technology, a narrative that connects those questions to a coherent whole, and a visual representation of both. You can find more information about ETAC from [https://github.com/wso2/ETAC/](https://github.com/wso2/ETAC/). 

We define blockchain as _a technology that creates and maintains a shared, distributed, append-only immutable digital record that uses hash chains and operates according to a consensus algorithm_. 

Let's consider a land registry as an example of a digital record that can be transformed with blockchain. In a land registry, a single set of owners must own a plot of land at a given point of time, and only they may transfer it to a new set of owners and only once. Buyers need to be able to verify ownership; Owners need to be able to demonstrate their ownership. Currently, the land registry handles these requirements through complex and expensive documents and processes executed by professional lawyers doing rigorous background checks. However, availability of a permanent digital record that can’t be tampered with or disputed can replace these complex processes. The permanent and tamper-proof digital record will show the owners, and only they will be able to sell a land. 

In the above example, the consensus algorithm provides the agreement among participants and makes blockchain possible. Furthermore, often, blockchain based systems create incentives to attract participants to take part in the algorithm by offering coins (a token that can have value), which ensures the sustainability of the algorithm. Such participants are called miners. 

Blockchain creates such a digital record. Such a digital record supports many use cases such as electronic cash, ownership ledgers, lightweight financial systems, and a distributed internet. Frisby [6] provides an excellent introduction to blockchain and its use cases. 

Blockchain has received extensive attention, is often cited as one of the most impactful technologies, and has attracted many startups, venture investments, and academic research. 

Having analyzed blockchain using the ETAC methodology, we make the following assertions. 

* Blockchain’s potential impact is both real and transformative. 
* Blockchain is ready for limited applications in use cases such as digital currency, lightweight financial systems, ledgers (of identity, ownership, status, and authority), provenance (e.g. supply chains and other B2B scenarios) and disintermediation, which we believe will happen in the next three years. 
* However, blockchain faces significant challenges such as performance, irrevocability, need for regulation and lack of census mechanisms. These are hard problems and it will likely take at least 5-10 years to find answers to those problems. 
* It is not clear whether blockchain can sustain the current level of effort for an extended period of 5+ years until breakthroughs occur. There are many startups and they run the risk of running out of money before markets are ready. Failure of startups can inhibit further funding and investments.  
* Value and need of decentralization compared to centralized and semi-centralized alternatives is not clear, which confuses our approach to the blockchain.  
* Given the risk involved as well as the significant potential returns, we recommend a cautiously optimistic approach for blockchain with the focus on concrete use cases.  Investments must consider sustainability for 5-10 year horizon before significant returns. 

The rest of the document discusses the rationale for the above assertions. It follows the narrative structure introduced in the ETAC. We start with the opportunity, then discuss the impact of the blockchain, followed by its feasibility. Finally, we present our assessments of blockchain future.

Since blockchain is applicable across a wide range of use cases, to ground the discussion, we first identify ten classes of blockchain use cases. As we discuss the impact, feasibility, and future, we consider each of these use cases separately while highlighting crosscutting concepts. 

![Figure 1 - ETAC for Blockchain](https://github.com/wso2/ETAC/blob/master/images/etac-blockchain-v2.png)

# Opportunity
The rise of the most successful digital currency—Bitcoin—kick-started blockchain. Economic incentives resulting from the appreciating bitcoin price attracted many and created awareness. Ensuing news following the booms and bust of the Bitcoin price kept blockchain on top of the minds of many. The US government identified Bitcoin as property in 2011 and as a currency in 2013 [8]. Other governments soon followed suit (Hobbes [8]). One by one Internet companies started accepting Bitcoin (e.g. Zinga, Expedia, Dell, Microsoft).

By 2015-16, it was observed that the impact of Bitcoin extends beyond cryptocurrency. The real value of blockchain is its shared, distributed, and immutable ledger, which enables decentralization and other use cases. The Bitcoin is followed by new blockchain implementations such as Ethereum in 2015 and Hyperledger in 2016. 

In her book “Blockchain: Blueprint for a New Economy” [47], Melanie Swan identifies three generations of the blockchain.

1. The first generation deploys cryptocurrencies in applications related to cash (e.g., currency transfer, remittance, and digital payment systems). 
2. The second generation deploys contracts. They are economic, market, and financial applications of cryptocurrencies such as stocks, bonds, futures, loans, mortgages, titles, smart property, and smart contracts. 
3. Third generation deploys cryptocurrencies beyond currency, finance, and markets (e.g. government, health, science, literacy, culture, and art).

Initial blockchains were public where anyone can interact with the blockchain. Later other variations of private blockchains are introduced. Based on who can write to it and who can read from it, blockchain implementations can be categorized in four ways:

1. Public - Permissionless: Anyone can join the network and any node in the network can participate in the consensus algorithm (could validate transactions). Or in other words, anyone can read or write. (e.g. Bitcoin, Ethereum).
2. Private - Permissionless: Only a selected set of nodes can read but no restrictions on who can write to. (e.g. Hyperledger Sawtooth).
3. Public - Permissioned: Anyone can read from the Blockchain, but only a selected set of nodes are allowed to write. (e.g. Sovrin Ledger, IPDB). 
4. Private - Permissioned: Only a selected set of nodes can read or write. (e.g. Hyperledger Fabric, Hyperledger Iroha, R2 Corda, CU Ledger).

In addition to the above four models, in some cases, the private-permissioned model is extended into two more categories:

1. Consortium: Only a selected set of nodes can read or write. But anyone or a selected set of participants can submit transactions.
2. Private - Permissioned (enterprise): Only a selected set of nodes can read or write.

Often permissions blockchain are built to support enterprise use cases [33] and based on more relaxed consensus mechanisms.

Some argue that private blockchains, given their centralized nature, are useless. However, they do provide stronger guarantees than a centralized system. To commit fraud in a permissioned blockchain, the culprit needs help from several people, which is hard to come by in most practical cases. For example, in the case of a consortium of banks, to commit fraud, a bank would need a majority of other banks to cooperate [34], which is unlikely to happen. Hence permissioned blockchains are useful for at least some use cases. 

By 2018, a significant blockchain ecosystem is active, which includes developers, miners, black markets, and investors. There are ongoing investments from IBM (HyperLedger), Google (e.g. [13]), Microsoft, financial institutions, banks, governments, and the United Nation among many others. Gartner has listed 32 blockchain platforms in a report [52]. Blockchain has also received significant venture capital (VC) investments (e.g. [10, 11, 12]). A16z crypto fund [14] is an example. Furthermore, many researchers are exploring new blockchain based research ideas. Examples of that research are available from _the curated paper list on blockchain_ [9]. Unlike many other emerging technologies, large tech giants such as Google, Facebook, Amazon, and Apple have little influence on the blockchain although some investments are already underway. Although there are many players,  the core technology is still under active development, and consequently, the playing field is still wide open.

The need for decentralization, the need to establish trust, and the need for security are positive drivers for blockchain. Among these three, the need for trust is the major driver. Sometimes the same is described as _“trustless transactions”_, where “trustless” means that no preexisting trust is needed and trust is provided by the platform. 

Although Bitcoin has drawn mixed responses from regulators and policy-makers, blockchain technology has received a favorable response. In terms of bitcoins, as Hatmaker [15] reports, the US government has taken a cautiously optimistic stance. However, China, Russia, and some countries have either banned or imposed limitations on cryptocurrencies. As Hobbes [8] points out, some companies that accepted Bitcoins have reversed their position (e.g. Dell, Stripe). On the other hand, the government's response to blockchain has been positive. For example, many US states have passed or are preparing legislations supporting blockchain [48].  

# Impact

It is worth noting that the following impacts are not based on the current state of the technology but based on a future where core technologies required to deliver blockchains has been realized. 


## Blockchain use cases 
Potential impacts of blockchain are far-reaching and many. The following shows some classes of those use cases. 

**Ledgers (of identity, ownership, status, and authority)** - As Berg [1] points out, both, governments and organizations maintain ledgers of identity, ownership, status, and authority. Corresponding blockchain implementations can replace them. 

Following are some advantages of blockchain based replacements:
* It improves data integrity and security. It also builds security and privacy protocols into the ledger operations, which makes it harder to defraud the system.
* It can reduce operational and processing costs. For example, it can reduce the documentation required for government and corporate processing (e.g. loans) through tamper-proof record keeping. Among examples of records are education records, birth, and death certificates, and criminal records.
* It can improve visibility and accountability. For example, it can track public spending and aid money. 

In summary, these systems make fraud harder, which enables removing safeguards required to avoid fraud, both of which leads to reduced cost. Decentralization improves security further. Increased automation and accountability provided by blockchain also improve agility. 


**Digital currency & lightweight financial system** - As pointed out by Greenspan [2], Meola [3], and Tapscott [4], blockchain can build a lightweight financial system. In some cases, it removes some intermediaries, and in others, it makes current models efficient and secure. Some examples are Nexus Mutual, Stellar, Celsius, BABB, and Omisego. 

Following are some advantages:
* It provides better integrity and sharing and reduces or removes financial costs. Mortgages, loans, credit scoring, escrow crowdfunding, widely accepted gift cards, widely accepted loyalty points, and local currencies are among a few of the use cases.
* It can offer efficient and cheap micropayments.
* It can enable many who are currently disconnected from banking systems due to costs or loan criteria (e.g. micro-financing).
* It can disaggregate and enable many new business models. 

In summary, just like with the earlier use case, lightweight financial systems reduce costs by reducing fraud and safeguards required to avoid fraud. Decentralization improves security further. Increased automation and accountability provided by blockchain also improve agility. It is worth noting that the high value of cryptocurrencies poses challenges due to significant transaction costs of blockchain, which must be solved to enable this use case. 

**Smart contracts** - As pointed out by Berg [1], blockchain through smart contracts enables businesses or individuals that do not trust each other to create agreements, do transactions, and build value without intermediaries. For example, a smart contract can provide an escrow, a trusted third party that hold the funds while the transaction takes place to reduce risks. It can be triggered by actions such as timeout, acceptance of goods, or a stock tick. Another common example is that of a car lease whereupon a missed payment, the car automatically locks and returns the control to the lender. In these cases, the immutability of blockchain replaces the need for trust. Furthermore, due to the reduction of costs, smart contracts would enable complex financial instruments to a wider audience.  However, the assertion that smart contract can broadly replace legal instruments has been challenged due to lack of “court of appeal”. This use case is still evolving. 

These use cases provide high agility and, in some cases, reduced costs.  

**New internet** - As described by Meola [3] and Dixon [5], a new decentralized internet can be built using the decentralized nature of the blockchain. Such an internet is independent of governments and corporate entities. 

Following are some examples of its services. 
* A decentralized DNS services, routing, and other internet services
* A global identity that is safe and decentralized - users can own their identity and it can’t be tampered with by an outsider (e.g. Blockstack).
* A global reputation that is safe and decentralized - this will let someone take his reputation in one ecosystem to another. Also, this will create incentives for people to behave (e.g. DREP).Limit or control the anonymity of the Internet. If every node that gets connected need to be registered with the blockchain we can identify and trace every node. If we eliminate anonymity we can eliminate bad actors/fraud

Such a decentralized internet is motivated by many that are concerned about the growing arbitrary power of GAFA (Google, Apple, Facebook, Amazon) over the Internet and concerned about the interference by governments on the Internet. Among examples are recent algorithm changes by Facebook that significantly affect traffic patterns [16] and government surveillance bills [17]. There have been earlier isolated efforts [18, 19] to build a truly decentralized internet, and many believe that blockchain is a perfect path to make further progress. 

Another possibility is to use blockchains to move away from advertisement based internet economy. For example, today most free services (google, gmail, twitter etc etc.) provide their services through advertisement revenue. The consumer is their ultimate product. An alternative to this approach is enabling the end users to pay creators small amount of bitcoin or crypto coin instead of liking their content. Same is already happening some extent via patreon accounts, although this a decentralized implementation of the same model. 

These use cases provide privacy and decentralization. 

**Autonomous ecosystems** - Meola [3] points out that blockchains can create decentralized alternatives for ecosystems and marketplaces such as Amazon, eBay, and Uber. Such ecosystems and marketplaces will not have an organization that has arbitrary power over all participants. Furthermore, this can also replace many ranking systems and rating agencies (e.g. hotel ranking, college ranking, bank rating, sports ranking). 

Following are some of the potential use cases. 
* Social networks (e.g. Socialx)
* Ridesharing (e.g. Dylyver)
* Marketplaces, auctions, and reputation (e.g. LO3 Energy, Greeneum, Tracer)
* Stock exchange without an exchange 
* Prediction markets (e.g. Augur)
* Reputation verification and ranking (e.g. The World Table (Open Reputation) and ThanksCoin). 
* Decentralized Autonomous Organizations (DAO) (e.g. Dash, Bitshares) 

This use case increases decentralization. 

**Disintermediation** - As pointed out by Greenspan [2], blockchains enable many untrusted parties to safely share a single database without an intermediary. For example, this can be used to audit critical communication between parties in healthcare, legal domains, or negotiations (e.g. Legaler). For instance, a secure email system where all transactions are verified and hence cannot be denied. 

This use case provides better security and agility.  

**Provenance** - Provenance tracks the origin, history, or movement of anything and make those auditable. As pointed out by Greenspan [2] and Meola [3], capturing provenance of artifacts using blockchain will provide better security and simplify processing. 

Following are examples of some use cases. 

* Tracking high-value items such as luxury goods, pharmaceuticals, cosmetics, diamonds, art, and electronics through the supply chain to verify their authenticity and to make sure they are sourced or built the way they are advertised. (e.g. FarmaTrust)
* Tracking cars and other items, their ownership, their operations history, and their service history will enable a stable second-hand market for those items. 
* Creating new markets for special origin goods such as organic food making their supply chain auditable as described in the first use case (e.g. CargoX, ShipChain, Paket). 
* Tracking software lifecycle such as what libraries are used, what version, who build it for a given distribution to enforce security.  
* Tracking aid money to ensure transparency and accountability. 
* Avoiding double payments in insurance claim processing.
* Managing content and copyrights by using blockchain to track use, propagate credit, and collect royalty payments for content (e.g. music, articles, images) potentially removing intermediaries. (e.g. Choon, Audius)
* Tracking perishable items (e.g. produce, medicine) and their chain of custody 

This use case will provide reduced cost and agility. 

**Initial Coin Offerings (ICO)** - ICOs [35] provides a new way to raise money. Tapscott [4] also recognizes this as an important blockchain use case. They can be used to attract initial capital or to attract contributions. 

Another variation is that instead of raising money for a project, one can bootstrap a project by offering coins for contributions. For example, a software project may attract developers by offering coins for feature implementations, bug reports, and patches. If the project is successful, those coins may become valuable. Even now, many developers see contributions to the missing open source projects as investing their time in return for reputation and potential recognition. Blockchain-based coins formalize these informal interactions. For example, Nazarov and others [55] argue blockchain related technologies as the next evolution of open source. 

This use case can provide agility. However, as Partz [36] points out since ICOs sidestep current regulations, they increase the risks of fraud. Current US Security and Exchange Commission (SEC) has defined ICO tokens as securities [49], in which case it is less attractive as a funding mechanism. It may still be valuable as a way to track contributions done by different people to a project.

**Voting** - As Meola [3] points out, blockchain can be used to build secure and fast voting systems. Such a system reduces the cost of conducting elections, which enables us to use elections more frequently thus increasing people participation in governance. Among examples are the US state West Virginia [40] and Swiss City Zug [41]. In its logical conclusion, voting becomes easy and cheaper, if we choose, we might even be able to replace the representative democracy with direct democracy [4].  

It is worth noting that this is an evolving use case. For example, Dunietz [42] questions the readiness of blockchain for voting.

This use case provides reduced cost and agility.

**Healthcare** - As pointed out by Gens [7], Greenspan [2], and Meola [3], blockchain can be used to support many healthcare use cases such as handling medicine providers' supply chain, managing prescriptions, and health data sharing. 

The last use case warrants further analysis due to its impact. Efforts are underway to use blockchain to record health data securely in a manner that gives complete control over the data to its owners (patients) while enabling portability between providers. This use case might allow anonymous analytics that will provide better population health indicators as well as the ability to track the effect of medication on individuals as statistics. 

This use case provides reduced cost and agility. 

The following table explores each of the use cases in terms of their applicability in public and private settings. 


|  None     | Public| Private |
| ------ |------ | --------- |
|Ledgers   |Yes    |   Yes|
|Digital currency & lightweight financial system|Yes|Rare|
|Smart contracts |Rare|Yes| 
|New internet|Yes|Rare|
|Autonomous ecosystems|Yes|Rare|
|Disintermediation| No| Yes|
|Provenance| Yes| Yes|
|Initial Coin Offerings (ICO)| Yes| No|
|Voting |Yes| Rare|
|Healthcare| Yes| Yes|

**Table 1: Applicability of use cases in public and private settings**

The next section will look at the above use cases in terms of the ETAC. 

Let us start with the impact. 

## Macro Impact 
We use the term “network effects”  to describe a phenomenon where the value of a system to its users increases as size of the system increases [45]. Most of the above use cases benefit from network effects as more and more users join those systems, they become more and more effective. However, as discussed by Griffin [45], the success of those use cases depends on the ability to create a critical mass. 

Blockchain affects security and integration middleware segments. The blockchain is tightly bound with security middleware and the success of blockchain likely makes systems much more secure and extends their applications. At the same time, blockchain may disrupt or change some prevailing security solutions. The fraud subsegment of security will be significantly affected. Blockchain will reduce or remove some of the common fraud scenarios. It will also make available a wide array of data about transactions, which will enable us to detect much more complicated fraud. 

Blockchain based systems may replace systems built by current internet companies. Some examples are social networks like Facebook, and Twitter,  and marketplaces like Amazon, and eBay. They may also disrupt large public clouds replacing them with decentralized crowdsourced computation platforms. Furthermore, blockchains can significantly change many financial systems, trade, and government operations. 

## Micro Impact
Blockchain can affect an individual company in several ways. By integrating with blockchains, organizations that have requirements for ad-hoc transactions with untrusted parties can use blockchain to achieve a competitive advantage due to agility enabled by reduced friction for transactions and ad-hoc trust. Furthermore, organizations can reduce cost due to reduced fraud, better security, and reduced friction. Also, blockchains enable new business models hence enabling new products and services. 

Furthermore, blockchain can increase the efficiency of the supply chain due to reduced fraud, better security, and faster transaction term negotiations. It is likely that organizations will have to support demand from the rest of the supply chain for integration with blockchain. 

In summary, common themes of blockchain impact include better security, decentralization, reduced cost, and agility. The impact is both substantial and transformative. This yields our first assertion of the document.  

## Technical Feasibility

#Technical Merit 
The double spending problem, which is the need to stop the owner of digital cash from reusing the money he has used to pay a transaction, is a long-standing challenge while building digital cash. Blockchain provided a new decentralized solution to the problem,  created incentives to keep it going, and made it work in the real world. These are significant contributions to the state of art. 

However, blockchain has many limitations. 

Let us explore some of the technical challenges. 
1. Limited scalability and latency - As pointed out by Kasireddy [24] and Yli-Huumo [29], blockchain systems have limited scalability and high latency. At the time of writing, a bitcoin transaction takes about 8 minutes and can support only about 2-3 transactions per second (Chepurnoy [26]). Furthermore, Croman [54] argues that independently of consensus algorithms, this limit is about 50 seconds and 27 transactions per second. Most use cases that we discussed under impact are infeasible under these limits. For example, to handle global scale systems such as a decentralized internet, blockchain needs to handle tens of thousands of transactions per second. However, it is worth noting that it is decided by the choice of consensus algorithm. Private blockchain implementations have proposed faster algorithms although they provide lesser guarantees. 
2. Limited privacy - as pointed out by Kasireddy [24] and Yli-Huumo [29], although blockchain provides pseudo anonymizations, by analyzing the transaction graph and other related information, it is often possible to link users to transactions. Once one transaction is linked to a user, all his transactions become known. Since blockchain transaction data are public or shared across a larger group (in the case of permissioned-blockchain), this means blockchain is riskier than using a credit card in terms of privacy. Furthermore, since blockchain transactions are public information, user identification via analysis is not prohibited under privacy laws. 
3. Storage constraints - As pointed out by Kasireddy [24] and Yli-Huumo [29], with current algorithms, each node must store the full history of the blockchain. This leads to high transaction latencies. The need to store full history also forestalls lightweight nodes, such as IoT devices, from joining a blockchain network. As time passes, the history becomes larger aggravating the problem. 
4. Unsustainable consensus - As pointed out by Kasireddy [24], Yli-Huumo [29], Bitcoin website [27], and Ethereum website [28], the current consensus method is cumbersome and consumes a significant amount of energy. For example, as pointed out by [30], Bitcoin energy consumption, if considered as a country, would be 39th in the world and higher than Australia. 

Among other challenges are inadequate tooling pointed out by Kasireddy [24], and Sybil attack (where an attacker attempts to fill the network with clients that they control).  Furthermore, the Ethereum problems page [28] and the Bitcoin list of problems page [27] list other issues. 

These challenges affect the blockchain ecosystem. For example, in 2018, when the startup Coinprism [55] stopped operations, the founder quoted some of the aforementioned challenges. 

It is worth noting that most of the above challenges mainly affect public permissionless blockchains due to their deployment size, although even private large deployments may be affected. The following table depicts how blockchain use cases are affected by four main technical challenges.




|   |Public|Private|
|---|----|---|
|Ledgers of identity, ownership, status, and authority|Limited scalability and latency, Limited privacy, Storage constraints * Unsustainable consensus |OK for most use cases| 
|Digital currency & lightweight financial system |Limited scalability and latency, Limited privacy, Storage constraints, Unsustainable consensus ||
|Smart contracts without a central authority| N/A | OK for most use cases |
| New internet| Limited scalability and latency, Limited privacy, Storage constraints, Unsustainable consensus |N/A|
|Autonomous ecosystems/ marketplace|Limited scalability and latency,Limited privacy, Storage constraints, Unsustainable consensus| N/A|
|Disintermediation| N/A| OK for most use cases| 
|Provenance| OK for most use cases|| 
|Initial Coin Offerings (ICO)| OK for most use cases | N/A |
|Voting| OK for most use cases | N/A
|Healthcare | Limited scalability and latency, Limited privacy, Storage constraints, Unsustainable consensus | Limited privacy, Storage constraints, Unsustainable consensus| 
 
 **Table 2: Technical challenges by use case**

Notwithstanding significant challenges, there is hope. Best minds are working on these problems. Progress is being made. For example, Zamani [53] presented a RapidChain algorithm that can perform 7500 transactions/ second. Furthermore, Kasireddy [25] discuss some of the approaches used to handle these problems and the curated blockchain papers list [31] records many relevant publications addressing some of the problems.

Tools, Ecosystem, and Skills: Developers with Blockchain skills are scarce. However, fueled by high demand, many developers are acquiring blockchain skills. We have observed students master key ideas within a few weeks. Many education materials are already available. Therefore, we believe skills will not be a significant obstacle. 

Tooling support for blockchain is limited. Most use cases are currently geared for highly technical users (Kasireddy [24]). However, this can be fixed only after core technology has stabilize. 

Friction: Following are some of the technical challenges that lead to friction. 
* Lack of methods to verify and limit risks - As pointed out by Kasireddy [25], lack of such tools is a major inhibitor to the blockchain. Among approaches that have been considered are formal contract verification, testing and simulation environments, and means to undo operations or limit the associated risks (e.g. by specifying upper limits). Although most software development happens without formal verification, irrevocability and the automated nature of blockchain transactions (e.g. smart contracts) increase associated risks to a new level. Therefore, we believe this is significant friction. 

* Lack of governance and standards - As pointed out by Tapscott [4], there are no clear regulatory processes for public blockchains. Among open challenges are how to evolve the blockchain, when to fork, what is the process to accept a fork, and how to handle human errors. They pose significant security risks. Solutions themselves must be decentralized not to undermine the goals. Finding a technical solution or finding a process to solve the problem is a pressing need.

* Blockchain-based applications are often complex (e.g. smart contracts). Current blockchain ecosystems do not provide tools that help users to debug those applications. 

Hence, in its current state, technical limitations and friction can significantly reduce blockchain adoption. Progress mandates new and significant technological breakthroughs. 





# Future
## Risks

There are significant risks associated with blockchains. Blockchain’s high impact potential in replacing many critical systems such as financial systems, cash, land registries, voting, further exacerbates those risks. 

### Irrevocability 
As Stinchcombe [20] points out, the irrevocability of transactions is a significant risk. 

For use cases such as Bitcoin and land registry, a resource is passed from an owner to an owner and only the current owner has the capability to assign it to a new owner. Irrevocability can have devastating consequences. However, for most other use cases, this can be addressed via a recovery transaction that undoes the transaction. 

Following are example cases where irrevocability is problematic. 

* If a credit card is lost or bank account is hacked, money can often be traced, found, and returned. However, as pointed out in the Bitcoin projects problems page [27], no recourse is possible with blockchain. There is no possibility of appeal. A person or an organization can lose all the money because their account is hacked or because their hard disk has crashed. For example, Roberts [44] cites an incident where a user threw away a hard drive with keys to 7500 bitcoins. The same article approximates that about 25% of all Bitcoins are already lost.

* Most ecosystems and markets built with blockchains are complex systems. They have emergent behaviors. For example, consider a hypothetical ChainBook, a Facebook alternative built on top of the blockchain. ChainBook’s underlying algorithm will be designed to distribute traffic equitably, to manage accounts, and propagate updates to all users based on some criteria. Since ChainBook is a complex system, we do not have techniques to analyze or understand those algorithms fully. Instead, they are designed using heuristics and empirical experiments, just like current Facebook algorithms. It is possible for such algorithms to have loopholes, which enables an attacker to hijack some accounts or hijack traffic. Unlike with Facebook, which has central control and can undo the change, it is not clear how this can be handled in ChainBook.

* Vulnerabilities are already challenging. Coupled with irrevocability they are dangerous. Unlike with Facebook, we can’t fix the problem even when we know the problem as changes are irrevocable. The emergent behaviors are often hard to foresee fully. Ultimately, the outcome could be systems that no one understands. Anyone who would figure out a weakness in the decentralized algorithms would wield a vast amount of power. Risks are very high. We can lose control of our creation.

* Let’s now also consider smart contracts. Smart contracts bring in automation. Automation and irrevocability are a poisoned combination. A simple mistake in a smart contract can lead to disasters, and outcomes can’t be revoked. Mistakes and unexpected scenarios are bound to happen, and blockchain technology needs to handle how to detect, contain, and recover from those scenarios. 

Any hijacked accounts or a resource is irrevocable unless more than 50% of participants are willing to accept a fork to the code. For example, as described by Castillo [38], Ethereum returned funds lost due to an attack using a hard fork [33]. However, it is not clear what is the criteria to accept such a hard fork. Also, it is possible that the next attack can be hidden inside the hard fork. Also, as the blockchain adoption and hence transaction rates increases, it is as time passes, it becomes harder and harder to enforce a hard fork without affecting correct transactions.

Before broad adoption, blockchain needs algorithmic changes to handle problems or needs a way to contain the impact via some form of upper limits, sandboxes, or insurance. As an alternative, many private blockchains provide the organization or consortium the ability to do admin operations such as change rules, undo transactions, and modify balances. 

### Regulator Absence 
Another risk is regulator absence. A regulator plays a key role in some use cases. For example, in the case of a stock market or share offering, oversight makes sure that all parties are protected. Without a regulator, it might not be easy to detect and avoid schemes like pyramid schemes. Although not popular, regulators play a crucial role in many systems. 

Regulator role is also important to ecosystems. For example, decentralized social networks might do a bad job of controlling hate speech, bias, and targeted attacks than a centralized system. For example, if a fake news scenario developed with a decentralized social network, there is no one to hold accountable. Further, this may be a perfect medium for an attacker to introduce bias and other unexpected behaviors to the system via updates while hiding his tracks. 

Blockchain-based systems, in their current form, do not support a regulator.  Also given irrevocability, it can either be impossible or expensive to fill the missing regulator's role. 

At the same time, one could argue that the web does not have a regulator. For example, no one curates what goes on the web. Regardless, the web is one of the most successful systems humans have built. At the same time, with scenarios such as fake news and hate speech, we are seeing the limitations of the web.

Where a regulator is needed and where it is not needed is a debate that will continue. However, blockchain based decentralized systems make it hard to introduce a regulator if needed. 

### Misunderstood Side-effects 
Thirdly, the impact of blockchain extends beyond computer science. We need to understand the economics, social, and political side effects of the blockchain. For example, blockchain may enable chap voting, enabling us to even replace representative democracy with direct democracy but we do not know whether that will be a good thing or a bad thing. Another risk is macroeconomic impacts. For example, lack of inflation is often lauded as a significant feature in the blockchain. However, inflation is often used as a monetary instrument by countries: for example, to absorb the shock of a downturn [22]. Some theorists believe that inflation is necessary for growth [21]. Removing such instruments would be risky without understanding its repercussions. Economics, Marketplaces and Trust sections in Blockchain papers [31] lists some of the current work in this area. 

### Fluctuations in Bitcoin Prices
Another risk is fluctuations in bitcoin prices. However, many believe that this is because it is new and its intrinsic value is hard to judge and it will stabilize over time [23]. With high bitcoin values, transactions charges are also high, which would turn off many use cases such as micropayments. It seems that the deflationary nature of Bitcoin and broad transformative use cases are in conflict due to transaction costs. This problem will aggravate with time. This only affects Bitcoin and financial use cases but does not affect other use cases. 

### Quantum Cryptography
As pointed out by Kasireddy [24], one of the looming threats to cryptocurrency and cryptography is the issue of quantum computers. However, quantum resistant hash functions are known and in some case implemented and it is likely we can just switch hashing algorithms. Therefore, the effect on the blockchain by quantum computing is not different from the effect on other aspects of computing [50]. Aggarwal [46] discusses some techniques for protecting against quantum attacks. 

At the same time, such a shift to quantum blockchain will take time. Even at its initial stages, where only governments and large organizations have access to quantum computers, quantum computing undermine all benefits of decentralization, in which case, the problem is worse as governments or organizations can act algorithmically without detection as opposed to current centralized systems that are regulated through transparent processes.  

### Regulatory Response
Finally, as we discussed under impact, blockchain changes many things that are currently governed by regulation and law. Therefore, likely, there will be future regulations and the law governing blockchains and its use. The response of those institutions are not clear, and the associated uncertainty creates risks. However, blockchain carries significant first-mover advantages to countries if they can adapt it in a significant manner. Therefore, governments will be ready to give it a fair chance. 

Some of these challenges, such as irrevocability, regulation and lack of census mechanisms are not present in private blockchains. On the other hand, private blockchains provide less decentralization. Consequently, there is a tradeoff between those challenges and amount of decentralization. At the same time, private blockchains are intended to be used in closed environments and can’t be widely applied to public blockchain use cases. 

The following table explores the effect of the aforementioned risks on blockchain use cases. 

||Public|Private|
|---|---|---|
|Ledgers of identity, ownership, status, and authority||
|Digital currency & lightweight financial systems|Irrevocability, Unpredictability, Economical, social, and political side effects, Regulatory response| N/A|
|Smart contracts without a central authority| N/A |Irrevocability, Unpredictability| 
|New internet|Irrevocability, Unpredictability, Lack of a regulator Economical, social, and political side effects|N/A|
|Autonomous ecosystems/ marketplace|Irrevocability, Unpredictability 
Lack of a regulator, Economical, social, and political side effects|N/A|
|Disintermediation| N/A ||
|Provenance|||
|Initial Coin Offerings (ICO)||N/A|
Voting| Regulatory response| N/A |
|Healthcare|Regulatory response||

**Table 3: Risks by use cases**






As Adzic [[4](https://blog.acolyer.org/2017/10/19/serverless-computing-economic-and-architectural-impact/)] and Sbarski [[6](https://www.youtube.com/watch?v=LAWjdZYrUgI)] points out, lack of standards and concerns about vendor lock-in pose a significant risk to serverless adoption. The real concern is not serverless functions, but the platform services required by those functions. It is hard to abstract away those services effectively. 

The vendor lock-in also can make it hard to switch from one serverless platform to another. This platform specific approach reduces the size of the developer pool available for hire, as few developers will know all the available systems.

The impact of vendor lock-in and how it is different from current conditions is not clear. For example, it is interesting to explore how vendor lock-in due to serverless is different from current on-premise and cloud development. For example, if users stick to simply using virtual machine images, there is some clear portability between cloud providers. However, most developers end up using cloud services such as databases, messaging, API gateways and storage solutions that are platform-specific. As a result, they may already be locked in. Another approach that aims to improve portability is Kubernetes, with many cloud providers offering managed Kubernetes deployments (such as GKE, EKS, and AKS). However, there are differences between these  (e.g. some require containers that do not run as root, which can cause a complete rewrite), and hence the real-world portability is uncertain. As a result, many teams have decided to balance the concerns of vendor lock-in with the agility provided by serverless.

The concerns on vendor lock-in are definitely higher with serverless. The reason for this is that serverless functions rely significantly more on platform services than traditional cloud applications. For example, a cloud application might rely on Amazon SNS, but equally may deploy its own messaging backbone. In serverless, all applications rely on the platform services. The platform services offered by each cloud are not the same - either in terms of which services, but also the detailed capabilities of each service. Hence the challenge of moving from one cloud to another is increased.

## Timeline 
Up to this point, our aim has been to present observations that are supported by either citations or arguments. This last section weighs those observations and provides our opinions on evolution and future of serverless, based on those observations as well as our experiences in the field. 

Following discussion uses the term _mega-clouds_ to identify public clouds owned by companies such as Google, Amazon, and Microsoft.  

Considering Roger’s five factors on technology adoption [[28](https://www.amazon.com/Diffusion-Innovations-5th-Everett-Rogers/dp/0743222091)], serverless has a strong score on four of those: 
* Relative advantage (delta to existing technology),
* Complexity or Simplicity (ease of understanding and use)
* Trialability (ease of demonstration)
* Compatibility (ease of assimilation)

The only missing factor is observability (the ability for end-users to see serverless in use). However, even though serverless is not a visible technology to the end user, there is significant awareness which is compensating for this aspect.

Serverless falls under level 8 out of 9 levels in _EU technology readiness level_ [[29](https://en.wikipedia.org/wiki/Technology_readiness_level)]. 

Given these aspects and the analysis above, we see no unassailable blocks to serverless reaching significant adoption in the next 3-5 years. In summary, we make the following assessments.  

**Opinion 1:** Holistically, we do not see technical challenges blocking serverless platform adoption. Although the disadvantages and risks we discussed might reduce the adoption, we believe there are significant use cases that are not affected by those limitations. 

**Opinion 2:** As discussed in the section “Technical Feasibility”, the significant gap we see is the need for tooling and IDE support, best practices, and architecture blueprints. This gap must be filled before a wider adoption can take place. On the other hand, with proper tooling, it is possible to train existing enterprise developers to program for a serverless platform as the required skills are fundamentally similar to a subset of current enterprise development skills. Therefore, we do not anticipate challenges in finding developers to build serverless applications. 

**Opinion 3:** Privately-deployable serverless (PDS) platforms like Apache OpenWhisk are a significant development. Proponents of PDS platforms argue that by running a PDS platform without depending on mega-clouds, an organization can get most of the advantages of serverless, without lock-in. This is a strategic answer by middleware companies to combat the serverless threat faced by middleware. However, this is only effective if organizations can run a large enough serverless platform that can provide the economies of scale. It is hard for PDS platforms to compete by running on top of mega-clouds’ IaaS offerings because mega-clouds can do strategic pricing better and because mega-clouds serverless offering can better integrate with their own IaaS. However, even if the PDS platform can provide savings, they might still lack the underlying platform services such as identity, databases, different storage types, and message-oriented middleware (MOM), which significantly reduce their appeal. At the same time, when data, systems, applications, and APIs are predominantly deployed on-premise, PDS platforms become appealing. The choice to use PDS in such scenarios will be a trade-off between latency requirements and incurred operational costs.  

One other interesting possibility to explore is that multiple small organizations might be able to pool their resources into one serverless platform securely. 

As Microsoft has done with Azure Functions [[25](https://docs.microsoft.com/en-us/azure/azure-functions/functions-overview)], mega-clouds can counter the rise of PDS’ by open-sourcing their serverless platform enabling it to run on-premise, which reduces the vendor lock-in risks and provides flexibility. Effectively this strategy is to offer customers a choice of PDS or serverless cloud with the same semantic model.

Another intriguing player amongst PDS’ is Knative[[16](https://github.com/knative/)], which provides a layer on top of Kubernetes to support serverless. Since all mega-clouds support Kubernetes, Knative aspires to be a platform to build apps that are portable across all mega-clouds. However, it is not clear how that support can extend to platform services such as storage, queues, and identity. If those aspirations materialize, we believe Knative will be attractive as a way to avoid vendor lock-in, especially if it can be used to hide differences between mega-clouds support for Kubernetes.

In summary, we only see limited use cases for PDS platforms. Even those use cases are likely to choose solutions like Knative so that they can switch to cloud providers if needed. 


**Opinion 4:** Current serverless platform market leaders are resisting standardization. It is not clear what the mega-clouds should worry about more: other mega-clouds or antipathy to vendor lock-in by users. For example, if mega-clouds co-operate to make applications portable, it could expand the market to the extent so that everyone is better off. It will take time for those scenarios to play out. Another possibility is if standardization is enforced by governments or significant buyers or consortia. We believe, standardization, in any form, is net positive and will significantly hasten the adoption of serverless.

Finally, adoption of serverless would need significant parts of existing systems to be replaced. Hence, we believe possible adoption will initially be limited to new projects (“greenfield”), and non-serverless deployments will continue to be around for a long time in the same way COBOL and mainframes are still around. The usual cycle is that eventually existing systems come up for replacement, and that can take years.

# Conclusions 
We see serverless having a significant impact and believe it is feasible.  In conclusion, we make two observations. 
* First, although there are limitations such as tail latencies and cold starts, they are not deal breakers for adoption. As discussed in the introduction, there are significant use cases that can work with existing serverless technologies. 
* Second, the significant gap is the need for tooling and IDE support, best practices, and architecture blueprints. This gap must be filled before a wider adoption can take place. With proper tooling, it is possible to train existing enterprise developers to program with serverless. So there are no significant concerns of finding developers. If proper tools are forthcoming, we believe serverless can cross the chasm in 3-5 years.


# References
1. Subbu Allamaraju, “Are We Ready for Serverless?”, https://www.slideshare.net/sallamar/are-we-ready-for-serverless?trk=v-feed
2. Jonas et al., “Occupy the cloud: distributed computing for the 99%”, SoCC’17, https://blog.acolyer.org/2017/10/30/occupy-the-cloud-distributed-computing-for-the-99/ 
3. Dmitri Zimine, “Serverless is cheaper, not simpler”, https://medium.freecodecamp.org/serverless-is-cheaper-not-simpler-a10c4fc30e49 
4. Adzic et al., “Serverless computing: economic and architectural impact”, https://blog.acolyer.org/2017/10/19/serverless-computing-economic-and-architectural-impact/
5. Doug Vanderweide, “Serverless Platform will make us all developers”, https://www.nextplatform.com/2017/09/25/serverless-revolution-will-make-us-developers/ 
6. Peter Sbarski, “Serverless: the Future of Software Architecture”, https://www.youtube.com/watch?v=LAWjdZYrUgI
7. “Amazon introduces Lambda, Containers at AWS re:Invent”, https://sdtimes.com/amazon/amazon-introduces-lambda-containers/ 
8. “Apache OpenWhisk”, https://openwhisk.apache.org/
9. Matt Murphy, Steve SloaneMay, “The rise of APIs”, https://techcrunch.com/2016/05/21/the-rise-of-apis/ 
10. Niklas Heidloff, “Developing Polyglot Serverless Applications”, http://heidloff.net/article/polyglot-serverless-applications 
11. Mike Roberts, “Serverless Architectures”, https://martinfowler.com/articles/serverless.html
12. “Google: Taming The Long Latency Tail - When More Machines Equals Worse Results”, http://highscalability.com/blog/2012/3/12/google-taming-the-long-latency-tail-when-more-machines-equal.html 
13. Jeffrey Dean and Luiz André Barroso, “The Tail at Scale”, https://ai.google/research/pubs/pub40801 
14. “A curated list of awesome services, solutions, and resources for serverless”, https://github.com/anaibol/awesome-serverless 
15. “Serverless Computing: Architectural Considerations & Principles”, https://www2.deloitte.com/content/dam/Deloitte/tr/Documents/technology-media-telecommunications/Serverless%20Computing.pdf 
16. “Google Kantive”, https://github.com/knative/ 
17. Baldini and others, “Serverless Computing: Current Trends and Open Problems”, https://arxiv.org/pdf/1706.03178.pdf 
18. "Emerging Technology Analysis Canvas (ETAC)", https://github.com/wso2/ETAC/blob/master/ETAC.md
19. “CNCF WG Serverless Landscape”, https://docs.google.com/spreadsheets/d/10rSQ8rMhYDgf_ib3n6kfzwEuoE88qr0amUPRxKbwVCk/edit#gid=0
20. “CNCF Serverless Whitepaper v1.0”, https://github.com/cncf/wg-serverless/tree/master/whitepaper 
21. Arun Chandrasekaran, Craig Lowery, Gartner: An I&O Leader's Guide to Serverless Computing”, https://www.gartner.com/document/3872956, 26 April 2018
22. “The NIST Definition of Cloud Computing”, https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-145.pdf
23. “Lessons Learned — A Year Of Going 'Fully Serverless' In Production”, https://hackernoon.com/lessons-learned-a-year-of-going-fully-serverless-in-production-3d7e0d72213f
24. “Companies using serverless in production”, https://dashbird.io/blog/companies-using-serverless-in-production/
25. “An introduction to Azure Functions”, https://docs.microsoft.com/en-us/azure/azure-functions/functions-overview
26. David A. Patterson, “Latency Lags Bandwith”, https://cacm.acm.org/magazines/2004/10/6401-latency-lags-bandwith/fulltext
27. Liang Wang, “Peeking Behind the Curtains of Serverless Platforms”, https://www.usenix.org/conference/atc18/presentation/wang-liang
28. Everett M. Rogers, “Diffusion of Innovations”, https://www.amazon.com/Diffusion-Innovations-5th-Everett-Rogers/dp/0743222091 
29. “EU Technology Readiness Level”, https://en.wikipedia.org/wiki/Technology_readiness_level 
30. Microsoft Azure, Durable Functions overview, https://docs.microsoft.com/en-us/azure/azure-functions/durable-functions-overview 

# Footnotes
<a name="fpaas">1. </a>Function Platform-as-a-Service (fPaaS) - this is Gartner’s term for FaaS [21]

<a name="tail_latencies">2. </a>Tail latencies are the high percentiles - e.g. 99th percentile. A system with high tail latencies can serve the majority of requests with normal latency, but a small proportion of requests have much higher latency.

<a name="central_limit_theorem">3. </a>https://en.wikipedia.org/wiki/Central_limit_theorem 


# Original Authors
Original authors are Srinath Perera (srinath@wso2.com), Paul Fremantle (paul@wso2.com), Frank Leymann (frank@wso2.com), and Nuwan Bandara (nuwan@wso2.com). 

# Acknowledgments
Many thanks to Selvaratnam Uthaiyashankar from WSO2 who have provided significant and useful feedback.

# Help us improve ETAC
We welcome and appreciate any feedback, changes, or contributions. Please send a pull request, create a github issue, or send a mail to srinath@wso2.com.

Blockchain Outlook, an ETAC methodology based analysis of Serverless technology will be released soon. To receive updates to ETAC and ETAC based emerging technology analysis, please subscribe to our [Global Technology Outlook Updates Newsletter](https://wso2.com/subscribe/global-technology-outlook-update).  


