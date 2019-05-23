


<h1 align="center">A Survey of Serverless: Status Quo and Future Directions</center></h1>

<p align="center">
<i>
Version 0.8<br/>
</i>
</p>

# Abstract

_This paper presents an assessment of serverless technology. The assessment uses an approach called the **Emerging Technology Analysis Canvas (ETAC)** to evaluate the serverless movement and explore the potential success of serverless. The ETAC is a framework to critically analyze emerging technologies._

_In our assessment, we observe that serverless can significantly impact software development workflows and cloud runtimes. We observe that despite challenges, there are significant use cases for serverless. Also, we identify gaps in developer tooling, best practices, and available architectural patterns. Assuming those gaps can be addressed, we foresee significantly increased adoption of serverless in the next 2-5 years._ 



# Introduction

WSO2 is creating a Global Technology Outlook (GTO) — an effort to identify emerging technology trends, classify them based on their potential, and assess a relevant subset of technologies in detail. WSO2 has been in the middleware market for 13 years, has helped many Fortune 500 companies build their systems, and is currently the 7th largest open source company. The GTO is designed to share our thoughts about our industry, to get feedback from customers and the community, and to enable a wider discussion on emerging technologies. As part of the GTO effort, we evaluate a number of emerging technologies.

This document presents our assessment of serverless technology. It uses the [Emerging Technology Analysis Canvas (ETAC)](https://github.com/wso2/ETAC/blob/master/ETAC.md)[[18](https://github.com/wso2/ETAC/blob/master/ETAC.md)], which is a framework that was developed to critically analyze emerging technologies. ETAC includes questions that bring out different aspects of an emerging technology, a narrative that connects those questions to a coherent whole, and a visual representation of both. You can find more information about ETAC from [https://github.com/wso2/ETAC/](https://github.com/wso2/ETAC/). 

## Definition of Serverless

To understand what is serverless, let us consider some definitions from various organizations.

The Cloud Native Computing Foundation (CNCF) defines serverless as:
>“where applications, bundled as one or more functions, are uploaded to a platform and then executed, scaled, and billed in response to the exact demand needed at the moment.” [[20](https://github.com/cncf/wg-serverless/tree/master/whitepaper)]

This definition focuses on Function-as-a-Service (FaaS), which is further defined as:
>“... code with functions that are triggered by events or HTTP requests. Developers deploy small units of code to the FaaS, which are executed as needed as discrete actions, scaling without the need to manage servers or any other underlying infrastructure.”

In addition, the CNCF also includes Backend-as-a-Service (BaaS):
>“which are third-party API-based services that replace core subsets of functionality in an application. Because those APIs are provided as a service that auto-scales and operates transparently, this appears to the developer to be serverless.”

ThoughtWorks[[11](https://martinfowler.com/articles/serverless.html)], also defines serverless as the combination of FaaS and BaaS. These definitions can be considered to be operationally-focused — addressing the “how” of serverless.

Gartner, by contrast, defines serverless as:
>“Serverless computing is a model of IT service delivery in which the underlying enabling resources are used as an opaque, virtually unlimited, shared pool that is continuously available without advance provisioning (preprovisioning) and priced in the units of the consumed IT service”. [[21](https://www.gartner.com/document/3872956)]

This is a much more declarative definition that does not address the “how” but instead approaches it from outcomes. 

In other words, this is to say that any system that provides autoscaling and fine grain metering in an opaque manner is considered serverless. Or more formally, anything that provides **Resource Pooling**, **Rapid Elasticity**, and **Measured Service** as defined in NIST cloud computing definition [[22](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-145.pdf)]. The recently released project Knative [[16]( https://github.com/knative/)] also fits with this definition. 

Gartner also explicitly states that serverless is not just FaaS: the Gartner serverless guide [[21](https://www.gartner.com/document/3872956)] states “fPaaS<sup>[1](#fpaas)</sup> is not the only form of serverless platform services.”  

All three definitions of serverless that we have examined include BaaS. This is a natural position, because developers who are building any real-world applications are in need of capabilities such as identity, databases, messaging, and event sources. In general, server-side computing has long had a concept of **middleware**. Informally middleware can be defined as capabilities that are higher-level than the operating system, but that are not complete applications in themselves. More formally we define middleware as “pre-written software designed to offer re-usable services needed by application developers, especially for server-side applications”. This includes services such as Integration (ESB, APIs, Messaging, Workflows), Observability (Monitoring, Tracing and Log Management), Storage (RDBMS & NoSQL), Infrastructure (DevOps and Orchestration), Security (Firewalls, Identity and Access Management), and IoT (Device Management, Data Collection). In many ways, BaaS is the cloud/serverless incarnation of middleware, where traditional middleware services are offered as pay-per-use capabilities by a cloud provider.

Any serverless environment that does not offer access to such backend services is unlikely to be useful. When we discuss the impact, feasibility, and future of serverless we need to consider the full environment including such backend services.

Based on the above definitions, we take the position that serverless includes FaaS, resources (compute and storage) as well as a complete execution environment including platform services providing resource pooling, rapid elasticity, and measured service (as defined in the NIST cloud computing definition) in an opaque manner to the user. Furthermore, we state it as essential that these approaches must enable consumption-based business and operating models. 

## Potential Impact of Serverless

With a serverless platform, a programmer can write code and directly run it in the cloud without worrying about hardware, operating systems, or servers. They can write the business logic as code, and then run the code without needing to be aware of the deployment complexities. The benefit is that non-functional characteristics such as high availability (HA), scalability, and security (such as authentication and access control) are provided out-of-the-box. They can run their applications entirely in the cloud with minimal understanding of the underlying infrastructure. 

This developer-friendly approach to developing cloud applications is a significant productivity enabler, and as such is also seen to enable agility. As a result, this can be seen as one of the biggest advantages of serverless.

In addition, platform services such as databases, message brokers, security token services, and API management are provided, making it easier to build powerful applications in the cloud. The FaaS aspect of serverless also makes it relatively simple to reuse code segments in different parts of an application, or in other applications. 

Serverless can be used in many use cases. As pointed out by [[17](https://arxiv.org/pdf/1706.03178.pdf)] and Chandrasekaran [[21](https://www.gartner.com/document/3872956)], serverless platforms can be used with a wide variety of use cases such as running web and mobile backends (BaaS), event processing, integration, API composition and aggregation, serving machine learning models, and as an extension point for SaaS. Another example of a serverless platform is _Algorithmia_ that hosts algorithms and machine learning models contributed by the community and provides an environment to build applications using those algorithms and models. This highlights the potential for domain-specific serverless environments compared to the more domain agnostic approaches offered by Amazon, Google, and Microsoft.


Baldini [[17]( https://arxiv.org/pdf/1706.03178.pdf)] points out that infrequent but bursty workloads are better served by serverless. This is because the cost model of pay-per-use may be higher per transaction, but customers do not pay for quiet periods, compared to running a dedicated server. Roberts [[11](https://martinfowler.com/articles/serverless.html)] points out that serverless makes it easy to write glue code to connect other parts of a cloud application. 
 
These advantages of serverless could potentially move more and more applications into the cloud. This will have the effect of increasing the adoption of BaaS further tying up applications to the cloud. This is a potentially major shift in enterprise computing. 

Figure 1 presents our ETAC for serverless. The rest of the document follows the narrative structure introduced in the ETAC. We start with opportunity, then discuss the impact, followed by the technical feasibility, risks, and timeline. Finally, we present our assessments of the potential future for serverless. 

![Figure 1 - the Emerging Technology Analysis Canvas (ETAC)](https://github.com/wso2/ETAC/blob/master/images/etac-serverless-outlook-v4.png)

# Opportunity 
The trigger for serverless was Amazon Lambda [[7]( https://sdtimes.com/amazon/amazon-introduces-lambda-containers/)], launched in 2014. Lambda is a FaaS environment. It addresses a need to improve the developer experience and reduce the management overhead of creating applications running in the cloud. It also improves the granularity of billing. It was soon followed by competitive offerings from Google and Microsoft. In the intervening years, many more serverless services and frameworks have been launched including iron.io, Stackery, and Joyent's Lunchbadger.


Amazon, Google, and Microsoft clouds use FaaS to extend their cloud platforms. Before FaaS, to write code that connects different parts of an application, a developer has to provision computers, run servers, write non-application-specific code, and deploy and manage these components. The addition of FaaS capabilities has created serverless platforms where developers can write applications without worrying about running, scaling or managing infrastructure.

Serverless, propelled by the success of cloud computing, can move more and more applications into the cloud. In addition, there are several privately-deployable serverless (PDS) platforms such as OpenWhisk [[8]( https://openwhisk.apache.org/)] and Knative[[16]( https://github.com/knative/)] that organizations can run on-premise. Further serverless offerings are listed in the serverless resources page [[14](https://github.com/anaibol/awesome-serverless)] and CNCF list of serverless offerings [[19](https://docs.google.com/spreadsheets/d/10rSQ8rMhYDgf_ib3n6kfzwEuoE88qr0amUPRxKbwVCk/edit#gid=0)]. 

# Impact
At the macro level, serverless can have a twofold impact on the software and cloud industry.

Firstly, the Deloitte 2018 serverless outlook[[15]( https://www2.deloitte.com/content/dam/Deloitte/tr/Documents/technology-media-telecommunications/Serverless%20Computing.pdf)] argues that serverless platforms can complement the API economy. Together with APIs, serverless is a key driver of disaggregation of functionality across organizations. With serverless platforms, one can easily expose functionality as APIs, which can also be easily reused using serverless. Hence serverless can accelerate the API economy and function disaggregation [[9]( https://techcrunch.com/2016/05/21/the-rise-of-apis/)]. This creates a virtuous circle: serverless creates more APIs, more APIs make serverless more effective.


Second, more and more applications are built composing third-party APIs such as Twilio for communication, Salesforce for CRM, Stripe or PayPal for payments, and Amazon, Google, and Microsoft APIs for machine learning [[23]( https://hackernoon.com/lessons-learned-a-year-of-going-fully-serverless-in-production-3d7e0d72213f)]. These applications face a challenge due to latencies imposed by APIs reachable through the Internet. As Patterson[[26]( https://cacm.acm.org/magazines/2004/10/6401-latency-lags-bandwith/fulltext)] argues, although bandwidth has improved significantly (exponentially), over time latency of networks has not improved at the same rate. Even if we can improve latency more rapidly, there is a hard limit on latency due to the speed of light - both within chips and across networks. For example, the minimum possible US East Coast to West Coast round-trip time allowed by the speed of light is around 50ms. So while latency may become a focus area and improve significantly, eventually there is a limit to the possible improvements. Serverless can provide one solution to this problem. If serverless sees sizable adoption, more and more of these APIs, as well as applications, will be deployed in the cloud, in which case both APIs, as well as applications that use APIs as clients, will end up in the same high-speed networks provided by the cloud. This can be even more of a benefit if the serverless function can be moved “closer” (in latency terms) to the functions that it is orchestrating. Note however, that in some cases _tail latencies_<sup>[2](#tail_latencies)</sup> might increase due to on-demand provisioning in serverless.


Such a development could reduce the average latency overhead of using APIs. Availability of low latency APIs will drive other applications to come to the cloud. This also creates a virtuous circle based on co-location effects on latency. 

Let us explore how serverless interacts with different technology segments:
* As we discussed, serverless has a symbiotic relationship with _APIs_ where each helps the other in a virtuous cycle.

* Similarly, serverless has a symbiotic relationship with _containers_ and _microservices_. For example, serverless is positively affected by container technologies such as Docker and Kubernetes that are used by many serverless implementations. Moreover, microservices already have broken down monoliths into loosely coupled services. Systems that have adopted microservices architecture are well placed to move to serverless. Due to better virtualization of resources and an environment for reusing other's APIs, serverless is a good environment to build a microservices architecture. Hence serverless and microservices architecture have positive synergy.

* Serverless makes implementation of other technologies easier. For example, serverless provides a highly productive environment to run **machine learning models** and it also can make development of **IoT systems** more efficient.  

* Serverless can provide an extension point to many systems including **PaaS, identity clouds, and SaaS systems**: users can write extensions as serverless functions and register them with such systems to extend its behavior.

* **Blockchains** also include support for securely performing computations where the majority of participants can agree on the outcome, which has some resemblance for serverless functions. However, such computations execute in either every node or a significant proportion of nodes in the blockchain. As a result, the blockchain model of function execution is much more expensive and has significantly higher latency. One potential future is that part of the blockchain computation occurs within the blockchain while more compute intensive aspects are executed as serverless functions, with the blockchain containing a tamper-proof log of the serverless outcome. Therefore we see the potential synergy between blockchains and serverless.

At the micro level, serverless impact on an organization is fourfold. 

1. Increases agility: As discussed by Adzic [[4](https://blog.acolyer.org/2017/10/19/serverless-computing-economic-and-architectural-impact/)] and Sbarski [[6](https://www.youtube.com/watch?v=LAWjdZYrUgI)], serverless provides faster time to delivery because
    * It needs less coding and configuration
    * It replaces code that is often templated, such as security logic, with configuration
    * It replaces functionality with API calls
    * It focuses on business logic instead of plumbing
    * It provides HA, scalability, and DevOps out-of-the-box

    One could argue that if the developer works for a large organization, he or she might have an environment set up where most of the above advantages are already there. However, only a tiny percentage of developers have access to such environments, while serverless makes it available to all.

2. Lowers platform costs: It provides a true, pay-as-you-go model by eliminating idle time costs. As discussed by Adzic[[4](https://blog.acolyer.org/2017/10/19/serverless-computing-economic-and-architectural-impact/)], most applications have variable loads. The providers of serverless platforms can aggregate many workloads, and according to the _central limit theorem_<sup>[3](#central_limit_theorem)</sup>, this aggregated workload will have a predictable distribution curve even if the individual workloads are not easily predictable. Despite the additional cycles needed to load and unload serverless applications, automation of the platform can lead to a significant reduction in overall resource needs compared to on-premise deployments, which leads to reduced costs. As a result, serverless platforms can reap substantial savings through economies of scale achieved through large-scale operations.
3. Lowers development costs:As discussed by Zimine[[3](https://medium.freecodecamp.org/serverless-is-cheaper-not-simpler-a10c4fc30e49)] and Adzic[[4](https://blog.acolyer.org/2017/10/19/serverless-computing-economic-and-architectural-impact/)], , serverless lowers development costs by taking over DevOps and monitoring costs. Conceptually, by promoting an opinionated development paradigm, serverless simplifies the development and shifts the concerns from developers to the platform, which leads to cost savings. Developers are expensive! Cloud platforms are retaining some of those cost savings but are also passing on some of the savings to the end user, creating a win-win situation for both sides.
4. Cost insights: as noted by Roberts [[11](https://martinfowler.com/articles/serverless.html)], serverless is metered with very fine granularity, which provides greater insights into managing costs. 

# Technical Feasibility
The core technologies required to build serverless platforms are already in place and a number of use cases are already in production (e.g. [[23](https://hackernoon.com/lessons-learned-a-year-of-going-fully-serverless-in-production-3d7e0d72213f)), [24](https://dashbird.io/blog/companies-using-serverless-in-production/)].

Serverless has several technical advantages:
* As discussed by Sbarski [[6](https://www.youtube.com/watch?v=LAWjdZYrUgI)], applications get high availability and auto-scalability without additional effort from the developer. This can significantly reduce development time and consequently costs.
* As discussed by Vanderweide [[5](https://www.nextplatform.com/2017/09/25/serverless-revolution-will-make-us-developers/)], serverless platforms make citizen programming possible (low code) by removing the need for server management, scaling, HA, configurations, builds, and other details. Hence, serverless platforms significantly reduce the barrier to entry for programming complex backend systems.
* Polyglot architectures - As discussed by Heidloff [[10](http://heidloff.net/article/polyglot-serverless-applications)], serverless platforms enable polyglot architectures where multiple programming languages are used together.

Zimine, Jonas, Roberts, and others have also pointed out several disadvantages of serverless.

As pointed out by Zimine [[3](https://medium.freecodecamp.org/serverless-is-cheaper-not-simpler-a10c4fc30e49)], when the number of functions in the application grows, serverless adds friction. Firstly, different functions are often developed separately. Secondly, they can be hard to debug. Thirdly, integration logic may be pushed into DevOps scripts, which can obscure the overall architecture. 

Furthermore, serverless applications are often modeled as a collection of functions that are wired by an event-driven architecture (EDA). While designing serverless based solutions that go beyond simple use cases, architects have to think differently. EDA-based programming is not intuitive to traditional developers and is generally harder to debug. The resulting architecture is more complex and logical flow is harder to reason. Jonas[[2](https://blog.acolyer.org/2017/10/30/occupy-the-cloud-distributed-computing-for-the-99/)] also argues that such friction has a significant impact. This also applies to microservices architectures that often use EDA as well.

Consequently, Zimine argues that serverless need tools and Integrated Development Environments (IDEs) to simplify the experience for complex serverless applications. Such an IDE should enable users to create functions in one view, compose them, test the fully composed application in the IDE itself, debug, make sure everything works, and then a push a button to deploy it to a serverless platform. These IDEs don’t yet exist. In addition, the IDE should have a debugging experience that helps pinpoint problems. This requires local testing within developer machines. There is progress towards this: for example, Azure Functions already supports local debugging triggered by cloud events. We believe that IDEs that support the aforementioned capabilities will hasten the serverless adoption. 

Serverless, by design, is an opinionated solution. It is agile as long as the programmer is willing to conform to its model but becomes clumsy if the programmer resists the model. This is a disadvantage. It is true that the same can be said about programming languages as well, but training in programming language takes significant time and it is rare that people switch programming languages. Roberts[[11](https://martinfowler.com/articles/serverless.html)] also pointed out that this limits the server, OS, and hardware level configurations and tuning available to the end user application [[10](http://heidloff.net/article/polyglot-serverless-applications)]. This lack of flexibility may limit serverless adoption in some use cases.  

A concern with serverless is how to handle state using stateless functions. As discussed by Allamaraju[[1](https://www.slideshare.net/sallamar/are-we-ready-for-serverless?trk=v-feed)] and Mike[[11](https://martinfowler.com/articles/serverless.html)], the current architecture best practices are to store the state in platform services such as databases, shared file systems or messaging systems. This, however, increases vendor lock-in. Another related challenge is how to handle ephemeral states such as connection pools. Although they do not affect accuracy, they do affect performance. Serverless platforms need to support ephemeral states efficiently. This is likely to be supported by serverless platforms in the future. As of  October 2018, the Azure cloud has added support for stateful functions, including checkpoints and automatic recovery[[30](https://docs.microsoft.com/en-us/azure/azure-functions/durable-functions-overview)], which frees the developers having to write code to save and recover state. It is not yet clear if this approach will be adopted by other serverless platforms or if they will provide alternative approaches.

Serverless faces two kinds of latency challenges (see [[3]( https://medium.freecodecamp.org/serverless-is-cheaper-not-simpler-a10c4fc30e49), [4]( https://blog.acolyer.org/2017/10/19/serverless-computing-economic-and-architectural-impact/), [10](http://heidloff.net/article/polyglot-serverless-applications)]): cold-starts and high tail latencies. First, when the first user request arrives, the serverless platform needs to load the function, which is one of the causes of high tail-latencies (this can be in the order of seconds [[27](https://www.usenix.org/conference/atc18/presentation/wang-liang)]). Cold-starts are avoided by keeping one copy running, by forecasting when the first call happens, or by improving the startup time of the code. These approaches may incur additional costs - causing tension between the latency and the cost model. Sbarski[[6](https://www.youtube.com/watch?v=LAWjdZYrUgI)] points out that the cold-start model is already at the odd with the SaaS pricing model, where users can get a better bill by keeping the instance live via periodic bogus requests. Second, given an application will be composed of many functions, the latency for calling each function adds up, which also includes the network and serialization latencies due to network hops. As pointed out by Barroso[[12](http://highscalability.com/blog/2012/3/12/google-taming-the-long-latency-tail-when-more-machines-equal.html)] and Dean[[13](https://ai.google/research/pubs/pub40801)] as more functions are added, the tail latencies get worse. The above-mentioned two papers discuss methods that could be used to handle the tail latency challenges. However, currently serverless is mainly suitable only for use cases that can tolerate high tail latencies. This still leaves a large potential market. 

In summary, serverless has many technical advantages. Although there are challenges, there are significant use cases that are not hindered by those challenges. Hence we believe serverless is feasible. 

# Future
## Risks
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

To receive updates to ETAC and ETAC-based emerging technology analysis, please subscribe to our [Global Technology Outlook Updates Newsletter](https://wso2.com/subscribe/global-technology-outlook-update).

# About WSO2 and Our Research

In 14 years in business, and as the #1 Open Source integration and API management vendor, WSO2 continually invests in areas beyond products. Our Research for Integration team regularly produces our Global Technology Outlook (GTO) — an effort to identify emerging technology trends, classify them based on their potential, and assess a relevant subset of technologies in detail. We do so using our Emerging Technology Analysis Canvas (ETAC). Our research is public in an effort to maintain our commitment to openness, quality, innovation, and integration leadership. 



