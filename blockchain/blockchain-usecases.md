<h1 align="center">Blockchain-based Integration Use Cases
</center></h1>


We have identified following blockchain use cases based on the feedback from practitioners who designs integration systems. Each use case is accompanied by a breif description of how to implement them. For details about architecture patterns mentioned, please refer to the paper [The Role of Blockchain in Future Integrations](https://github.com/wso2/ETAC/blob/master/outlooks/blockchain4integration_outlook.md#proof).

If you know other blockchain based Integration use cases, please send a git pull request.

Usecases are grpoup by the motation to adopt them. For more details, please refer to the paper [The Role of Blockchain in Future Integrations](https://github.com/wso2/ETAC/blob/master/outlooks/blockchain4integration_outlook.md#proof).

# Motivation: Foster Trust 

## Standards or Regulation Adherence 
* **Use case:** Adhere to standards, safety checks, etc. exposed via a public or consortium blockchain (by choice or by government regulation). This has added the advantage of holding regulators responsible for their decisions.
* **Implementation:** See Auditable History or Workspace architecture pattern.

## Attract Contributors by giving up control
* **Use case:** Some initiatives draw fewer external contributions if they are controlled by a single organization. Conversely, an organization can attract contributors by giving up control (e.g. Certification Authority) or defining a specification. 
* **Implementation:** See Auditable History or Workspace architecture pattern.


## Providing Supply Chain Visibility 
* **Use cases:** Get suppliers to record transactions in a blockchain to provide visibility into the claims made by the company about how resources are sourced. 
* **Implementation:** See Auditable History or Workspace architecture pattern.

## A Global Reputation System
* **Use case:** Reputation can take many forms. One example would be professional reputations (e.g. doctors and lawyers). Ratings are signed by actual users together with their verifiable claims, and therefore, they are hard to fake. Authorities that issue verifiable claims should keep records and mention user’s other DIDs within there verifiable claims to stop user from creating new DIDs and switching. Another example is digital identity with social credibility. The more an individual is trustworthy (e.g., paying on time or being a good tenant), their social credit rises. People with high social credibility can get priority when it comes to loan applications, reduced rental fees, etc. 
* **Implementation:** See the Registry or Marketplace architecture pattern.

## Implementing Organization Promises as Smart Contracts 	
* **Use cases:** Companies put their promises in blockchains so that they can’t retract those promises. This use case can help establish trust, enforce penalties, or authorize returns based on the blockchain. 
* **Implementation:** See the Smart Contracts and Managed Things architecture pattern.



# Motivation: Avoid Coercion 
## Avoid Coercion as a Certification Authority  
* **Use cases:** A Certification Authority may put public certificate in a blockchain so that they can’t change it without others’ consent. This reduces the chance that they will be coerced into creating certificates for activities, such as intelligence. 
* **Implementation:** See the Registry or Marketplace architecture pattern.



# Motivation: To Improve Efficiency 

## Create an Ecosystem 
* **Use case:** An organization can create an ecosystem using blockchain. Examples include maintaining an API registry or providing odometer and maintenance tracking for cars. For example, an automotive company may create a better second-hand market by tracking the maintenance records of cars in a blockchain, which in turn may improve car sales. 
* **Implementation:** See Auditable History or Workspace architecture pattern. 

## Tracking Software Lifecycle
* **Use case:** An organization can improve its security by tracking aspects of the software lifecycle—such as what libraries are used, what version, and who built it for a given distribution—and verifying them before deploying the software. 
* **Implementation:** See Auditable History or Workspace architecture pattern.

## Decentralized Deals Registry  
* **Use case:** Establish a single, decentralized place for sharing offers and deals. 
* **Implementation:** See Auditable History or Workspace architecture pattern.


## Auditing: Track who did what inside an Organization.
* **Use case:** Track key operations—such as approvals, the creation or deletion of accounts, performance and accountability reporting (PAR), and employee interactions—as well as human resources (HR) use cases where company’s version may be disputed.
* **Implementation:** Use the architecture pattern for Auditable History or Workspace.

## Managing Copyrights via Smart contracts 
* **Use cases:** Manage content and copyrights, by using blockchain to track use, propagate credit, and collect royalty payments for content (e.g. music, articles, images), there is the potential to remove intermediaries. (e.g. Choon, Audius).
* **Implementation:** See the Smart Contracts and Managed Things architecture pattern.

## Token Revocation 
* **Idea:** Currently token or claim revocations are difficult. We can support revocations by recording all token issues and revocations in a ledger and getting Policy Enforcement Point (PEP) devices to periodically check the ledger for revocations. The sovereign ledger already includes this feature. 
* **Implementation:** Use the architecture pattern for Auditable History or Workspace.

## Replace IP-based decisions (e.g. geo restrictions, rate limiting etc) via Verifiable Claims
* **Idea:** Currently, most APIs implement geo restrictions and rate limiting using an IP address, which can be masqueraded. We can replace them with Verifiable Claims.  For an example, a Verifiable Claim can demonstrate that a user lives in the United Kingdom, which can be used to enforce geo restrictions. 
* **Use case:** Implement geo restrictions based on Verifiable Claims included in API calls. 
* **Implementation:** Ask users to include a Verifiable Claim in their request, which server will verify and use to apply control. 
* **Other use cases:** This can be applied to all API and OAuth use cases,  e.g. see IETF OAuth use cases. 

## Control Objects via Smart Contracts 
* **Use case:** If an auto loan is not paid, automatically lock the car.
* **Implementation:** See the Smart Contracts and Managed Things architecture pattern.

## Cloud-based transferable Ownership
* **Use case:** The idea is to support ownership control via a blockchain. Among the examples are an Airbnb special lock that you can control during your stay and bicycle ride sharing. The use of built-in e-vaults enables car owners to automatically pay for parking, electricity top-ups, highway tolls, etc. 
* **Implementation:** See the Smart Contracts and Managed Things architecture pattern.

## Manage IoT Devices using Blockchain
* **Use case:** Establish a decentralized network of IoT devices using a blockchain. This will remove the requirement of having a central location to handle communications. Devices can communicate directly, conduct device management, etc. without involving a central authority.
* **Implementation:** See the Smart Contracts and Managed Things architecture pattern.


# Motivation: Enhance Customer Experiences

## Supporting a Receipt 
* **Idea:** Provide a receipt of a message using blockchain. 
* **Use case:** Submit an application and receive a receipt for the payment of a tax, product, service, etc. 
* **Implementation:** The server records hashes of messages in a ledger. 
* **Other use cases: This can be used for all kinds of situations where there are receipts. 
 
## Issuing Customers Verifiable Claims 
* **Use case:** Issuing Verifiable Claims to customers might enable integration with other vendors, and it can become a feature for attracting customers. For example, your telco provider or water provider can confirm your address. 
* **Implementation:** See architecture pattern for IAM.

## Managing Global miles or loyalty points 
* **Use case:** A group of smaller companies can create a shared loyalty point system on top of the blockchain. This may enable a smaller organization to compete with bigger players. 
* **Implementation:** See the Registry or Marketplace architecture pattern.

## Give Users control over their Health Data 
* **Idea:** Store health data with the patient (e.g. on a mobile phone). 
* **Use case:** Let users keep their own health data and provide access as needed.
* **Implementation:** Users keep health data in the phone, which periodically encrypted using user’s key pair and backed up to the cloud. Using the IAM architecture pattern, the blockchain helps to exchange a key between the health provider and customer. After the key exchange, the customer encrypts requested data using the shared key and shares it with a provider. If Operating System supports this, we might be able to send the data with instructions to be deleted in 24 hours. 


## Dynamic API Discovery and Composition
* **Idea:** Enables dynamic API composition where applications operate by picking APIs from the marketplace at runtime. 
* **Use case:** Your mobile phone has policies governing wifi connections, such as cost, connection speed limits, etc. The phone discovers and picks a wifi provider based on the policies and connects automatically. 
* **Implementation:** See the Registry and Marketplace architecture pattern. 
* **Other use cases:** The same idea can be used with tourist services. For example, paying tolls on demand or getting traffic data about the area you are entering.  






# Motivation: Collaborate More Effectively

## Decentralized API Marketplace
* **Idea:** Global decentralized registry of APIs that includes reputations, reviews, etc. (needs service contract agreements for tasks)
* **Use case:** Find APIs that perform specific tasks and pay for their use. 
* **Implementation:** See the Registry and Marketplace architecture pattern.
* **Other use cases:** The same ideas apply for other service registries as well. 


## Audit a Business Process
* **Idea:** Have the ability to track the activities of each actor in a business process later.
* **Use case:** Handle a dispute after a failure or customer complaint. 
* **Implementation:** Each participant in the process record has hashes for incoming and outgoing messages, which they can’t deny and can prove they indeed sent specific messages. See the Auditable History or Workspace architecture pattern. For example, this technique can be used to track public or charity money. 

## Adding Blockchain Connectors
* **Idea:** Some use cases may need the integration logic to talk to blockchain. Typically, this kind of third party calls are done using “connectors”, a client to the API that provides a usable programming constructs. 
* **Use case:** Connect to blockchain from integration logic. 
* **Implementation:** This is a wrapper around blockchain clients that maps data that goes in and out to common formats (e.g. JSON). 

## Spam-free Global Communication Queue
* **Idea:** Establish a broadcast channel across untrusted systems. 
* **Use case:** Provide notifications of new security exploits or attacks. 
* **Implementation:** Use a message broker coupled with an architecture pattern for Auditable History or Workspace to record hashes of messages in a ledger. Hashes of the messages can be used to determine whether a particular email is spam. Anyone can say anything, but others can find out who said it. However, scalability will be limited and this would only work for lower message rates. 

## Ecosystem-level non-competitive Critical Services
* **Use case:** The idea is to implement non-competitive critical services that can be shared across organizations, such as KYC (know your customer) databases. 
* **Implementation:** Use the architecture pattern for Registry or Marketplace.

## Multi-party Projects or Processes 
* **Idea:** Setup the multiparty project flow as a smart contract, which will handle the coordination. 
* **Use case:** Scenarios include building a house, claims settlement, air ticket verification, and handling a travel disruption. The use case also applies for processes that need participation from multiple organizations. For example, this can be useful in automating many government processes or company-government processes. We can conduct multiparty aggregation of news feeds and transaction data, and because no one tries to hide data from each other, we establish a shared record of information.
* **Implementation:** See the Smart Contracts and Managed Things architecture pattern.

## Multi-organization Collaborations 
* **Use case:** An organization may choose to start a document (e.g. spec) in public on a blockchain to invite collaborations. Alternatively, two companies that decide to collaborate may do so in a blockchain to track who said what and who disclosed what information. One example is an instant payment network where money is issued to the blockchain as a token. We can also attach metadata to the transactions, such as scans of contracts.
* **Implementation:** See Auditable History or Workspace architecture pattern.

## Operating a consortium as a DAO
* **Use case:** A consortium coordinates activities across the participating organizations. The idea is to identify processes performed by the consortium and implement them as smart contracts.  
* **Implementation:** See the Smart Contracts and Managed Things architecture pattern.

## Create shared Data-pools 
* **Use case:** Enable patients who have the same disease to communicate (anonymously if required) or share data. 
* **Implementation:** This can be implemented as a combination of the IAM and Smart Contracts and Managed Things architecture patterns. 

## Data that auto deletes at a timeout 
* **Use cases:** Enable data to auto delete at a timeout. Identify data as a copy of something where the original owner is known, and record it in a blockchain. Also, record access writes in the blockchain. Use an app running on your phone to verify your credentials before downloading the data and automatically delete it after the timeout. 
* **Implementation:** See architecture pattern for IAM. 

## Valuables Tracking and Protection
* **Use case:** Protect against forgery. For example, we can fingerprint the inside of the diamonds. Those can be recorded in the blockchain. Later you can take the fingerprint of the diamond and match with the fingerprint located in the blockchain to ensure that it is the same gemstone it is claimed to be.
* **Implementation:** See the Smart Contracts and Managed Things architecture pattern.

## Decentralized Resource brokering 
* **Use case:** Micro electricity grids (solar, wind, etc.). Have the ability to produce power where it is required. Certain houses produce more power or have lower power requirements, while other houses do not produce power at all. Excess power can be transferred automatically to the locations where deficit exists. We can use crypto currency for buying and selling power. Producing power with economically viable approach is possible using blockchains.
* **Implementation:** See the Smart Contracts and Managed Things architecture pattern.

## Global decentralized Prediction Markets
* **Usecase:** Conduct research, consulting, analysis, and forecasting. Blockchains can be developed to place and monitor bets on anything from sports, to stocks and elections in a decentralized way (e.g., AUGUR).
* **Implementation:** See the Registry or Marketplace architecture pattern.

#Other 


## Remove the need for common STS
* **Idea:** A challenge in security use cases, such as identity federation, is finding an STS (Secure Token Service) that is trusted by both sides. Verifiable claims replace most of these use cases. However, one concern is that may end up with several competing blockchains.
  
## Use case: Implement Identity Federation.
* **Implementation:** Use the IAM architecture pattern.
* **Other use cases:** This can be applied to all API and OAuth use cases. 

# Help us improve
We welcome and appreciate any feedback, changes, or contributions. Please send a pull request, create a github issue, or send a mail to srinath@wso2.com.

To receive updates about similar work, please subscribe to our [Global Technology Outlook Updates Newsletter](https://wso2.com/subscribe/global-technology-outlook-update).  
