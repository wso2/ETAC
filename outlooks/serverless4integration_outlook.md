


<h1 align="center">How Serverless can shape Enterprise Integration?</center></h1>

<p align="center">
<i>
Version 0.8<br/>
</i>
</p>

# Abstract

_This paper examines the impact of serverless computing on enterprise integration use cases. Within integration use cases, serverless computing can provide significant benefits,  such as lower costs, increased agility, and cost insights. At the same time, serverless computing faces challenges, most notably the lack of an integration language, minimal privacy safeguards, and vendor lock-in. Despite these challenges, there are significant serverless-based integration use cases. Consequently, assuming the need for an integration language can be addressed, we believe serverless computing can find significant adoption within integration use cases. Furthermore, although new applications are moving to the cloud, legacy applications continue to run in on-premise deployments. The need to integrate with those applications will create use cases for integrations both on-premise and the cloud._

# Introduction

Cloud computing has become a fundamental deployment choice for application systems. Despite concerns about privacy and vendor lock-in, even high-stakes services, such as those in governments, banks, and health, have adopted the cloud. In this backdrop, the introduction of Amazon Lambda in 2014, incepted the idea of serverless computing.  A programmer can write business logic based on a serverless platform and directly run it in the cloud without worrying about hardware, operating systems, or servers. Consequently, developers can focus on the business logic in their applications, which are running entirely in the cloud, with minimal understanding of the underlying infrastructure. 


In the last two years, serverless computing has received much attention. Therefore, in our earlier analysis, we explored serverless technology using the Emerging Technology Analysis Canvas (ETAC)[[1](https://github.com/wso2/ETAC/blob/master/ETAC.md)] framework. The analysis can be found in [[16](https://github.com/wso2/ETAC/blob/master/outlooks/serverless_outlook.md)]. In the rest of the document, we will refer to this analysis as the [“serverless outlook](https://github.com/wso2/ETAC/blob/master/outlooks/serverless_outlook.md).” 

This paper further extends the serverless outlook and discusses the applications of serverless computing within the systems integration domain and their impact. 

To ground this discussion, let us first define serverless computing and integration.


We define serverless computing as _including  function as a service (FaaS) resources (compute and storage), as well as a complete execution environment, including platform services that provide resource pooling, rapid elasticity, and measured service—as defined in the National Institute of Standards and Technology (NIST) cloud computing definition—in an opaque manner to the user_. 

We define integration as _the use of technologies that enable typically diverse systems within or between organizations to work together to achieve common business goals._

We implement integration by intercepting communications between mismatching apps, APIs, and services and shaping that information as messages, events, and files. Historically, integration is implemented using an enterprise service bus (ESB) that sits between information sources and sinks and coordinates activities as a single unit. With the advent of microservice architecture, newer systems tend to use integration logic running independently (e.g., as a microservice) instead of a centralized service bus.

Integration can be categorized as low-code integration and general integration. Wikipedia defines low-code development as _“software that provides an environment programmers use to create application software through graphical user interfaces and configuration instead of traditional computer programming.” [[2](https://en.wikipedia.org/wiki/Low-code_development_platform)]_. Hence low-code integration focuses on visual tooling based integration while general integration involves general programming and scripts. Given the shortage of programmers, the share of low code integration is expected to rise over time. Our discussion will consider both types of integration technologies. 

Our main goal is to sort between the hype and the real potential of serverless computing within the integration domain. With that in mind, we wanted to take a systematic approach to evaluate it. To do so, we have used the Emerging Technology Analysis Canvas (ETAC) [[1](https://github.com/wso2/ETAC/blob/master/ETAC.md)] framework, which takes a broad view of emerging technology by probing impact, feasibility, risks, and future timelines.

We have drawn the following conclusions as a result of our analysis:

1. Latency considerations, a lack of developers, and the rising complexity of systems coupled with standard cloud advantages are driving more and more apps to the cloud 
2. Since most applications use external APIs and services, building applications is becoming increasingly similar to integration use cases. 
3. Low-code integrations are already feasible, though iPaaS. The primary challenge faced by serverless computing within integration use cases is the lack of a language within the serverless environment that supports integration natively. However, several languages already have wide adoption among current integration use cases, and one or more of those languages can be adopted within serverless environments as well. 
4. There are significant serverless computing-based integration use cases despite the challenges. Therefore, serverless architectures can find significant adoption, even without standardization. The move to the cloud will drive these use cases.
5. A competition between Kubernetes running on the cloud (bringing portability) and serverless (providing usability) will decide the scale of serverless computing adoption.  
6. Since integration is the glue that connects legacy and new systems, integrations will continue to have use cases on-premise and in the cloud addressing integrations within and between these deployments. 


The remainder of this document is organized as follows. 

We first discuss the opportunity, including the initial trigger and the current status of serverless computing adoption in the integration domain. Then under the impact, we identify motivations for organizations to deploy a serverless architecture and examine the associated impacts at both macro and micro level. Next, we review the feasibility of the serverless integration, as well as the supporting ecosystem required. Finally, in evaluating future adoption, we discuss the risks and timelines for the associated use cases.


# Opportunity
## Trigger
There are no clear integration use cases that act as the trigger for serverless computing adoption. Our current interest is motivated by general serverless computing use cases. 

## Players
Amazon, Google, and Microsoft clouds have extended their cloud platforms with FaaS, thus creating serverless platforms. Amazon Step Functions [[3](https://docs.aws.amazon.com/step-functions/latest/dg/welcome.html)] is an integration solution for applications in the cloud, although it is much simpler compared to on-premises integration solutions [[4](https://www.forrester.com/report/The+Forrester+Wave+Strategic+iPaaS+And+Hybrid+Integration+Platforms+Q1+2019/-/E-RES141621)]. Integration platform as a service (iPaaS) solutions provide mature options for low-code integrations.

Other serverless offerings are listed in the serverless resources page [[7](https://github.com/anaibol/awesome-serverless)] and Cloud Native Computing Foundation (CNCF) list of serverless offerings [[8](https://docs.google.com/spreadsheets/d/10rSQ8rMhYDgf\_ib3n6kfzwEuoE88qr0amUPRxKbwVCk/edit#gid=0)]. 

Additionally, there are several privately-deployable serverless (PDS) platforms, such as OpenWhisk [[5](https://openwhisk.apache.org/)] and Knative [[6](https://github.com/knative/)] that organizations can run on-premise. 


## Drivers

The success of the cloud and its acceptance as an essential architectural choice has paved way to Serverless, which further raise cloud abstraction. There are several positive drivers, which fall under one of two categories: software trends and cloud trends. 


### Software Trends
We have identified Ten Governing Forces Shaping Technology [[26](https://hackernoon.com/catalysts-inhibitors-and-transformers-ten-governing-forces-shaping-technology-57a793bfbf0)]. Among them there are two major forces in the area of software development that are acting as positive drivers for serverless computing.


First, even as software is becoming a greater part of our lives [[9](https://a16z.com/2011/08/20/why-software-is-eating-the-world/)], we face a severe shortage of skilled developers, which will continue to get worse. Since by raising abstractions, serverless architectures lower the minimum bar required and broaden the developer pool, the shortage of developers  acts as a driver for adopting serverless computing. 

Second, a key goal of software architectures has been reducing complexity. Serverless computing is a significant step toward reducing complexity as it abstracts layers below the code, such as deployment, hardware, and configuration, lowering the knowledge  required from the developers and increasing their effectiveness. 


### Cloud Trends

At the same time, there have been three developments, in particular, that are accelerating the adoption of the cloud, which acts as a major positive driver for serverless. 

First, the wide adoption of APIs and associated latencies is driving applications to the cloud. For example, according to the "State of the Internet 2019" report by Akamai, APIs already account for 83% of HTML and JSON internet hits [[11](https://www.akamai.com/us/en/multimedia/documents/state-of-the-internet/state-of-the-internet-security-retail-attacks-and-api-traffic-report-2019.pdf)]. If this trend continues, most apps will use at least one API. The latency imposed by wide area networks (WAN) is up to 300 times higher than latencies within data centers [[13](https://gist.github.com/jboner/2841832)]. Such high latencies have a significantly greater effect on applications [[14](https://www.gigaspaces.com/blog/amazon-found-every-100ms-of-latency-cost-them-1-in-sales/)] that uses APIs. Consequently, if applications are composed of APIs, applications will be better placed in the cloud with APIs, which have low latency. This development will create incentives for both apps and APIs to move to the cloud. 

Second, for an application looking to implement MSA in the  cloud, using serverless environment is a natural candidate. Furthermore, MSA-based architectures can be easily moved to serverless platforms, since the functional decomposition already has been done. Furthermore, the cloud reduces the high cost of observability and DevOps associated with microservices due to its distributed nature. 

The third development, the complexity of systems, is rising with the adoption of Kubernetes, need for observability, and complex DevOps. Almost all cloud vendors have adopted Kubernetes, effectively converting it to a portability layer for cloud applications. Although it brings flexibility and efficiencies, Kubernetes deployment and management is complex [[15](https://medium.com/@betz.mark/is-kubernetes-too-complicated-1ffd8a3a6fb4)]. The same applies to other additions, such as service mesh, as well. Moreover, as the number of components in the systems increases, they become harder to deploy and manage. Therefore, these deployments  require observability and DevOps for managing the complexity. These developments push more and more systems to the cloud to offload management complexity there. 

The three developments above, coupled with standard cloud advantages, such as cost savings, agility, faster time to market, move most applications into the cloud. 

On the other hand, whether looking at software or the cloud, monopoly and vendor-lock-in  concerns act as negative drivers, which we will discuss later under “Risks.” Government policy and laws also act as a gating factors in serverless computing due to uncertainty over potential regulations. 

In the next section, we explore how serverless computing, together with the drivers examined in this section, will affect integration. 


# Impact

## Macro

There are several impacts at the macro level. 

Privately-deployable serverless (PDS) platforms are motivated by data and services that continue to run in on-premises data centers due to privacy and confidentiality concerns. For example, although there are cloud deployments within each country, concerns are much more involved. For example, in theory, a citizen of country A working in country B ‘s cloud provider can be forced by the country A government to get hold of data. 

Such use cases can be handled using serverless platforms such as KNative, which have added advantage of easy migrations to the cloud if needed. Another option is cloud provider platforms running locally (e.g. Amazon Outposts) or running a hybrid cloud using VPN based solutions (e.g. virtual private cloud (VPC)). Furthermore, if those systems consumes public APIs, they will face further pressure to move to the cloud to reduce latency. 

However, any of these scenarios leave little room for a separate market for  PDS platforms as free and open source KNative handles most of the use cases with minimal work to the end user. 


Second, in this backdrop, developers who want to write an app or an integration in the cloud have two choices. They can choose to run integration logic on top of Kubernetes using integration middleware, or they can choose to run integrations as serverless functions. In a nutshell, serverless computing provides usability versus Kubernetes provides portability. 

It is not clear which one will attract the most apps. Historically, usability has won. 
Kubernetes is trying to match the usability of serverless computing by building layers, such as KNative. One possible future is both matching a “serverless platform-like API”. However, Kubernetes has a lot of catching up to do in terms of a wide range of platform services, such as databases, message brokers, and identity services. Another possibility is that future integration tools can enable users to write integrations and directly produce serverless functions that can run on a serverless platform or Kubernetes. 

Third, the difference between building apps and building integrations is fast disappearing. This has been true for decades within enterprise, which is new becoming a global trend. The rise of the cloud, APIs, and serverless architectures are making app development much more like integration, effectively making integrations ubiquitous. Applications are composed of APIs, and the logic required to write those applications is similar to writing integrations. Consequently, the need for integration-like technology will be much more commonplace in future systems. This development will significantly widen the available market for integrations while driving existing program languages and platforms to provide first-class support for writing integrations.

We can program simple integrations using programming languages, such as Java, Go, and Python. However, complex integrations in serverless architectures also inherit most of the problems that occur in enterprise integration settings. For example, those integrations need to build systems by composing APIs from different vendors, which leads to timing, data format, and context mismatches. Writing such code using a programming language, such as Java, needs a lot of plumbing code. Furthermore, with the wide adoption for microservices and APIs, the number of services involved in an integration will likely rise, increasing the complexity of integrations and services, alike. ESB vendors, such as WSO2, Mulesoft, and IBM, have provided integration languages to handle such scenarios. It is likely that similar tools are required for integrations in the cloud as well. 

Serverless computing provides many middleware services as a part of the platform, thus nullifying the need for middleware in many use cases. In response, we are likely to see the rise of a new class of middleware that runs on top of a serverless platform. Most middleware is a collection of services, and most of those services can run directly on top of a serverless platform. Therefore, some middleware might be released as a serverless function. It is not clear whether cloud vendors would embrace serverless-based middleware or fight it. One could argue that, just like with the Apple App Store, having an ecosystem of middleware from which users can pick and choose would be a significant strength for a cloud provider. For example, in the case of the smart phones, the App Store ecosystem becomes a moat against the competition. 


## Micro
This section discusses the impact of serverless computing as experienced by individual organizations. In our earlier research, the serverless outlook [[16](https://github.com/wso2/ETAC/blob/master/outlooks/serverless_outlook.md)], we have identified several advantages. 

* Increases agility: As discussed by Adzic [[17](https://blog.acolyer.org/2017/10/19/serverless-computing-economic-and-architectural-impact/)] and Sbarski [[19](https://www.youtube.com/watch?v=LAWjdZYrUgI)], serverless computing provides faster time to delivery. 
* Lowers platform costs: It provides a true, pay-as-you-go model by eliminating idle time costs. 
* Lowers development costs: As discussed by Zimine [[18](https://medium.freecodecamp.org/serverless-is-cheaper-not-simpler-a10c4fc30e49)] and Adzic [[17](https://blog.acolyer.org/2017/10/19/serverless-computing-economic-and-architectural-impact/)], serverless computing lowers development costs by taking over DevOps and monitoring costs. 
* Cost insights: as noted by Roberts [[20](https://martinfowler.com/articles/serverless.html)], serverless platforms are metered with very fine granularity, which provides greater insights into managing costs.


These advantages will continue to be active for integration use cases using serverless architectures. 


# Feasibility
## Use cases
Before discussing the feasibility of integration use cases in serverless computing, it is useful to understand typical integration use cases and how they map into the serverless environment. 

Most apps built in the serverless environment are composed of four parts: 
1. the external APIs used
2. Microservices written as serverless functions
3. Integration logic connecting those services and APIs
4. Connections to data sources and sink functions. 

Apart from integration logic, all the other constructs are already available or connected to the serverless environment.  

The book, “Enterprise Integration Patterns(EIP)” [[21](https://www.enterpriseintegrationpatterns.com/patterns/messaging/)], identifies and classifies common integration patterns. Let’s have a look at how serverless can implement the scenarios identified in the book and the data integration use cases.


Collectively these include:

1. Matching data formats between participants: These patterns are categorized under “message transformations” in the EIP book.  
2. Resolving timing, aggregation, and disaggregation mismatches between participants or orchestrating the flow between participants: In the EIP book, corresponding patterns are categorized under “Message Routing,” “Message Channels,” and “Message Endpoints.” Among them, “Message Channels,” and “Message Endpoints” are mostly supported as platform services in the serverless environment (e.g., message broker). 
3. Data Integration use cases either combine multiple data sources or keep multiple data sources in sync with each other. They are usually implemented as a combination of event-driven programming (e.g. Kafka, RxJava, Akka), stream processing (e.g. Flink, Siddhi), and batch analytics processing ( e.g. Hadoop, Spark), with the latter two delivered as platform services.  

To support integration scenarios, a serverless environment needs to support the means to program these integration scenarios. 

In the next subsection, we discuss the technical feasibility and advantages of a serverless environment for implementing integration scenarios. 


## Technical merit
Under this section, we will discuss both positives and negatives of serverless applied to integration use cases. 

Considering positives, serverless computing continues to have the following advantages discussed in the serverless outlook. 
Applications get high availability and auto-scalability without additional effort from the developer. This can significantly reduce development time and consequently costs.
Serverless platforms make citizen programming [[23](https://readwrite.com/2013/07/15/the-rise-of-the-citizen-developer/)] possible by removing the need for server management, scaling, high availability (HA), configurations, builds, and other details. Hence, serverless platforms significantly reduce the barrier to entry.
Serverless platforms enable polyglot architectures where multiple programming languages and heterogeneous data stores are used together.
Serverless environments enable users to move their integration logic closer to data sources using a content delivery network (CDN) technology (e.g., Amazon Edge [[12](https://aws.amazon.com/lambda/edge/)]), which can provide significant performance improvements and save bandwidth. 

Considering these positives, some of the identified limitations of serverless computing are less prevalent with integration use cases. For example, integrations are predominantly stateless by design. To store a state, integrations use platform services, such as databases, shared file systems, or messaging systems. This reduces the state management challenges faced by serverless platforms. 

Among the negatives, as identified by the serverless outlook, are cold start and tail latencies, which continue to be a concern with integration use cases as well. However, with the wide adoption of Kubernetes, cold starts have also become part of on-premise systems. Furthermore, microservices architectures also lead to higher tail latencies. Consequently, neither is a negative differentiator for serverless environments compared to on-premise deployments. 

At the same time, integration use cases on serverless platforms face challenges due to the absence of integration-friendly language in the cloud. As discussed in the macro subsection, to support integration scenarios, a serverless environment needs to support the ability to program these integration scenarios. But, current choices for programming integration logic are limited:

1. iPaaS-based visual programming works for simple use cases (see [[25](http://mikehadlow.blogspot.com/2018/10/visual-programming-why-its-bad-idea.html)] for details).
2. Using one of the programming languages supported by the serverless platform (e.g., Java, Python) 
3. Amazon step functions are a potential alternative for integrations, yet they still have limited capabilities and are not a full language. For example, Amazon step functions can only model a set of states and transitions among them while most integration languages can be used to program any logic. Therefore, step functions are not suitable for complex logic.
   
If we look at the history of integration, the first integrations were written using classic programming languages, such as COBOL, C, Java and C#. However, most integration use cases involve communicating between services, APIs, data sinks, and data sources and then matching their inputs, outputs, timing, and control flow. Classic programming languages do not have first-class constructs for service invocations or dealing with data formats such as XML or JSON. Hence, developers need to re-implement the logic from first principles, which leads to code that is verbose, complicated to write, and hard to maintain. To address this challenge, on-premises integration vendors [[22](https://www.gartner.com/en/documents/3880132)] have supported domain-specific languages for programming integrations.  

Currently, serverless platform users rely on languages, such as Java, to implement their integration use cases as well. However, as more complex use cases move to serverless architectures, we are likely to rediscover the limitations we faced with those languages years back. Therefore, the lack of higher languages supporting integrations continues to be a challenge faced by serverless computing. 

This can be solved using several means: 
1. Users can run integration middleware within an infrastructure as a service (IaaS) solution and use it to integrate serverless applications. 
2. Cloud providers can support integration middleware as one of their platform as a service (PaaS) services. 
3. Cloud providers can support integration languages—e.g., Ballerina or domain-specific languages (DSLs)—as languages supported by FaaS. 
4. Solution providers can expand visual programming support for general integration.

This is an important consideration when moving integration use cases to the cloud. 

## Tools, Ecosystem and Skills

Our serverless outlook [[16](https://github.com/wso2/ETAC/blob/master/outlooks/serverless_outlook.md)] argues that serverless platforms need tools and integrated development environments (IDEs) to simplify the experience for complex serverless applications. For example, an IDE should enable users to create functions, compose them, test the fully composed application in the IDE itself, debug the app, and then push a button to deploy the app to a serverless platform.
 
In the case of low-code integration, user experiences already exist for integration in iPaaS tools, such as Worketo and Dell Boomi [[4](https://www.forrester.com/report/The+Forrester+Wave+Strategic+iPaaS+And+Hybrid+Integration+Platforms+Q1+2019/-/E-RES141621)]. These iPaaS solutions may act as an alternative to a language for programming interactions in a serverless environment. The visual programming supported by iPaaS tools works well for smaller use cases, but it faces challenges with complex programs [[24](https://www.outsystems.com/blog/visual-programming-is-unbelievable.html)]. Most complex integrations are done with textual languages, and similar tools do not yet exist for general integrations within serverless platforms. 


## Friction
Our serverless outlook observes that an event-driven architecture (EDA), which is central to the serverless model, is not intuitive to traditional developers and is generally harder to debug. However, integration use cases naturally follow an EDA model, and hence, EDA is not a significant concern to integration developers. 

Furthermore, the serverless outlook notes that serverless computing, by design, is an opinionated solution. It is agile as long as the developer is willing to conform to its model, but it becomes clumsy if the programmer resists the model. This continues to be a disadvantage. 

In summary, serverless computing has many technical advantages. Although there are challenges, there are significant use cases unhindered by those challenges. The main hurdle faced is the lack of a native integration language in the serverless environment, which we believe can be fixed. Hence we believe serverless computing is feasible within integration use cases.


# Future
## Risks
Our serverless outlook has identified the following two concerns: the lack of standards and vendor lock-in, which pose a significant risk to serverless architecture adoption. The real concern is not serverless functions, but the platform services required by those functions. It is hard to abstract those services effectively. These two concerns continue to be a negative consideration for integration use cases in serverless environments, although not a show stopper. 

## Timeline
We found that serverless platforms within integration use cases have a significant impact and have significant use cases that are feasible. Assuming that serverless platforms will support an integration language, we expect to see many new applications adopting serverless architectures in the next three years. Since these applications use APIs and interact with external systems, as applications move to the cloud, integration use cases will also be forced to move to the cloud. 

However, adoption of a serverless architecture would require significant parts of existing systems to be replaced. Hence, we believe initial adoption will be limited to new “greenfield” projects, and traditional deployments will continue to persist for a long time in the same way COBOL and mainframes are still around. The usual cycle is that eventually existing systems come up for replacement, and that can take years.

Integration is the glue that connects legacy and new systems. Consequently, integrations will continue to have on-premises deployments support legacy systems for years to come. Furthermore, there is likely to be demand for hybrid interactions between on-premise legacy deployments and new cloud infrastructures. 

Due to latency limitations, integrations will be often deployed close to the applications and systems they connect. Consequently, integrations will move to the cloud only after most APIs, services, and applications have migrated there. Despite this lag, we believe integration technologies will find significant use cases connecting new applications and services. Among exception would be hybrid cloud ( e.g. via VPC)  and apps that runs across multiple clouds. 

# Conclusion

As a result of our analysis, we have reached the following conclusions: 

1. Latency considerations, a lack of developers, and the rising complexity of systems coupled with standard cloud advantages are driving more and more apps to the cloud.  Since most applications use external APIs and services, building applications is becoming increasingly similar to integration use cases. 
2. Low-code integrations are already feasible, though iPaaS. The primary challenge faced by serverless computing within integration use cases is the lack of a language within the serverless environment that supports integration natively. However, several languages already have wide adoption among current integration use cases, and one or more of those languages can be adopted within serverless environments as well. 
3. There are significant serverless computing-based integration use cases despite the challenges. Therefore, serverless architectures can find significant adoption, even without standardization. The move to the cloud will drive these use cases.
4. A competition between Kubernetes running on the cloud (bringing portability) and serverless (providing usability) will decide the scale of serverless computing adoption.  
5. Since integration is the glue that connects legacy and new systems, integrations will continue to have use cases on-premise and in the cloud addressing integrations within and between these deployments. 


# References

1. Srinath Perera, “Emerging technology analysis canvas (ETAC)”, https://github.com/wso2/ETAC/blob/master/ETAC.md, 2018.
2. “Low-code development platform”, https://en.wikipedia.org/wiki/Low-code_development_platform
3. “Amazon Step Functions”, https://docs.aws.amazon.com/step-functions/latest/dg/welcome.html
4. “The Forrester Wave™: Strategic iPaaS and Hybrid Integration Platforms, Q1 2019”, https://www.forrester.com/report/The+Forrester+Wave+Strategic+iPaaS+And+Hybrid+Integration+Platforms+Q1+2019/-/E-RES141621
5. “Apache OpenWhisk”, https://openwhisk.apache.org/
6. “Google KNative”, https://github.com/knative/
7. “A curated list of awesome services, solutions, and resources for serverless”, https://github.com/anaibol/awesome-serverless
8. “CNCF WG serverless Landscape”, https://docs.google.com/spreadsheets/d/10rSQ8rMhYDgf\_ib3n6kfzwEuoE88qr0amUPRxKbwVCk/edit#gid=0
9. Marc Andreessen, "Why Software Is Eating the World", https://a16z.com/2011/08/20/why-software-is-eating-the-world/
10. “IDC FutureScape: Worldwide IT Industry 2019 Predictions”, https://www.idc.com/getdoc.jsp?containerId=US44403818
11. “State of the internet 2019”,  https://www.akamai.com/us/en/multimedia/documents/state-of-the-internet/state-of-the-internet-security-retail-attacks-and-api-traffic-report-2019.pdf
12. Amazon Edge, https://aws.amazon.com/lambda/edge/
13. “Latency Numbers Every Programmer Should Know”, https://gist.github.com/jboner/2841832
14. “Amazon Found Every 100ms of Latency Cost them 1% in Sales”,https://www.gigaspaces.com/blog/amazon-found-every-100ms-of-latency-cost-them-1-in-sales/
15. Mark Betz, “Is kubernetes too complicated?” https://medium.com/@betz.mark/is-kubernetes-too-complicated-1ffd8a3a6fb4
16. Srinath Perera et al, “A Survey of Serverless: Status Quo and Future Directions”, https://github.com/wso2/ETAC/blob/master/outlooks/serverless_outlook.md
17. Adzic et al., “Serverless computing: economic and architectural impact”, https://blog.acolyer.org/2017/10/19/serverless-computing-economic-and-architectural-impact/
18. Dmitri Zimine, “Serverless is cheaper, not simpler”, https://medium.freecodecamp.org/serverless-is-cheaper-not-simpler-a10c4fc30e49
19. Peter Sbarski, “Serverless: the Future of Software Architecture”, https://www.youtube.com/watch?v=LAWjdZYrUgI
20. Mike Roberts, “Serverless Architectures”, https://martinfowler.com/articles/serverless.html
21. Gregor Hohpe, Bobby Woolf. “Enterprise integration patterns: Designing, building, and deploying messaging solutions”. Addison-Wesley Professional, 2004.https://www.enterpriseintegrationpatterns.com/patterns/messaging/
22. “Market Guide for Application Integration Platforms”, https://www.gartner.com/en/documents/3880132
23. "Why Citizen Developers Are The Future Of Programming", https://readwrite.com/2013/07/15/the-rise-of-the-citizen-developer/
24. “Visual Programming Is Unbelievable: Here’s Why We Don't Believe In It”, https://www.outsystems.com/blog/visual-programming-is-unbelievable.html
25. “Visual Programming - Why it’s a Bad Idea”, http://mikehadlow.blogspot.com/2018/10/visual-programming-why-its-bad-idea.html
26. "Ten Governing Forces Shaping Technology", https://hackernoon.com/catalysts-inhibitors-and-transformers-ten-governing-forces-shaping-technology-57a793bfbf0


# Original Authors
Original authors are Srinath Perera (srinath@wso2.com), Paul Fremantle (paul@wso2.com), Frank Leymann (frank@wso2.com).

# Acknowledgments
Many thanks to Nuwan Dias, Kasun Indrasiri, Parbath Siriwardana, Miyuru Dayarathne, and Malith Jayasinghe from WSO2 who have provided significant and useful feedback.

# Help us improve ETAC
We welcome and appreciate any feedback, changes, or contributions. Please send a pull request, create a github issue, or send a mail to srinath@wso2.com.

To receive updates to ETAC and ETAC-based emerging technology analysis, please subscribe to our [Global Technology Outlook Updates Newsletter](https://wso2.com/subscribe/global-technology-outlook-update).

# About WSO2 and Our Research

In 14 years in business, and as the #1 Open Source integration and API management vendor, WSO2 continually invests in areas beyond products. Our Research for Integration team regularly produces our Global Technology Outlook (GTO) — an effort to identify emerging technology trends, classify them based on their potential, and assess a relevant subset of technologies in detail. We do so using our Emerging Technology Analysis Canvas (ETAC). Our research is public in an effort to maintain our commitment to openness, quality, innovation, and integration leadership.



