


<h1 align="center">How Will AI shape Future Integrations?</center></h1>

<p align="center">
<i>
Version 0.8<br/>
</i>
</p>

# Abstract

_While critically evaluating how AI can affect the integration domain,  we identified 11 classes of use cases that can significantly affect integration outcomes. AI has significant developer community and rich set of tools. Many real-life AI use cases have demonstrated their effectiveness.  Despite the promise, there are obstacles. Risks such as bias, privacy concerns, and challenges such as shortage of skilled professionals and model interpretability are limiting the adoption of AI.  Paper discusses risks and challenges in detail and evaluate the feasibility of each use case and identifies four classes of use cases ready to be exploited._

# Introduction 

We can explain, precisely,  how to solve some tasks, but not others.  For example, we know how to sort an array of integers step by step and can write a program to perform it. On the other hand, we know how to drive but can’t explain it precisely. We can’t teach our children how to drive by writing it down. Instead, we have to give them examples and feedback to train their responses and their judgment. 

Artificial intelligence (AI) solves problems humans can do intuitively but can't explain. It does so by learning from examples  \to mimic our decisions.  

AI has received extensive attention as one of the world’s most impactful technologies to date—arguably as significant as the industrial revolution, which enabled us to automate human labor and ushered in the industrial age. Unsurprisingly, artificial intelligence has attracted many startups, venture investments, and academic research. 

Today, AI is comprised of a broad range of technologies: rule-based (e.g., Prolog), machine learning (pulling insights from data, e.g., random forest method, support vector machine (SVM), neural networks, Bayesian learning), ontology technologies (e.g. owl) ,and a sophisticated machine-learning technique called deep learning. 

This paper explores how AI will affect the integration domain over the next ten years. To ground this discussion, let us first review how we define AI and integration for our analysis.

We have chosen the Wikipedia definition of artificial intelligence as _“machines that mimic 'cognitive' functions that humans associate with other human minds, such as ‘learning’ and ‘problem-solving’."_

We define integration as _“the use of technologies that enable typically diverse systems within or between organizations to work together to achieve common business goals.” [23]._


We implement integration by intercepting communications between mismatched apps (e.g. APIs, services,...) and then shaping that information represented as messages, events, and files. Historically, integration is implemented using an enterprise service bus (ESB) that sits between information sources and coordinates activities as a single unit. With the advent of microservices architecture, newer systems tend to use integration logic running independently (e.g., as a microservice) instead of a centralized service bus.

Our main goal with this document is to separate the hype from the real potential of AI within the integration domain. With that in mind, we wanted to take a systematic approach to our evaluation. To do so, we have used the Emerging Technology Analysis Canvas (ETAC) [1] framework, which takes a broad view of emerging technology by probing impact, feasibility, risks, and future timelines.

We have drawn the following conclusions as a result of our analysis:
* Enabling AI in an enterprise involves collecting, cleaning up, and creating a single representation of data as well as enforcing decisions and exposing data outside, each of which leads to many integration use cases. Hence, AI indirectly creates demand for integration.
* A weakness in AI decisions is much more harmful than a weakness in a human decision for three reasons. First, AI is being integrated into our lives. Second, since the per-repeat cost is small, AI is used more frequently. Third, different people have different opinions, which provides oversight, but AI is often applied transparently without any supervision. Both integration and non integration use cases should carefully considers ramification of those challenges such as bias and false positives.  
* AI aligns well with many emerging technologies (e.g., big data, IoT, APIs, cloud), which already play significant roles within integration use cases.  
* AI needs data, which in some cases leads to significant competitive advantages. The need to collect data will drive vendors to offer most AI products in the cloud via APIs. 
* When applied to competitive fields, such as security or stock markets, where AI-based systems end up competing, AI might lead to worse-than-before situations. 
* Due to a lack of expertise and data, custom AI model building will be limited to large organizations. It is hard for small and medium size organization to build and maintain custom models. Many AI use cases will be solved as cloud APIs that let vendors concentrate data and expertise. Many integration use cases discussed will be solved in this manner. 
* There are significant AI-based integration use cases. Among them 
Security, Data Integration, Extracting useful information from humans, and AI support within existing data stores already have systems available and are likely find more adoption. 
* Increasing Usability, Self Driving Operations (DevOps and Regulatory Compliance), Automatic and Self-Service Integration do not face critical challenges but will need 5-10 years of development for wide adoption  
Business Automation will often be infeasible for SMEs if not already supported as a cloud API.
 
The remainder of this document is organized as follows. 

We first discuss the opportunity, including the initial triggers and the current status of AI adoption in the integration domain. Then under the impact section, we identify the motivations for organizations to deploy AI, and we examine the ramifications at both the macro and micro levels. Next, we review the feasibility of AI for integration, as well as the supporting ecosystem. Finally, in evaluating future adoption, we discuss the risks and timelines for the associated use cases.


# Use cases

To understand how artificial intelligence impacts the integration domain, we need to understand the applicable use cases. After a survey, we have identified the following eleven classes of AI use cases in the integration domain. 

1. Integrations required to enable AI—collecting data required for AI and carrying out actions suggested by AI creates many use cases 
2. Data Integration—use of AI to reconcile data from many data sources with different formats and semantics into meaningful records 
3. Extracting useful information from human Inputs—use of AI to extract meaningful data for inputs such as audio, video, and natural language 
4. Increasing Usability—use of AI to enhance the usability of systems 
5. AI support within existing data stores—supporting AI as turnkey solutions within existing data stores 
5. Algorithm Economy—combining algorithms from an algorithm marketplace to build systems  
6. Self Driving Operations (DevOps and Regulatory Compliance)—use of AI to reduce or eliminate the need for human intervention while managing systems 
7. Automatic and Self-Service Integration—use of AI to simplify the process of creating integrations 
7. Security—use of AI to detect potential attacks and fraud
8. Business Automation—use of AI to automate business operations 
9. API MarketPlace—use of AI to provide recommendations and ratings in API marketplaces
 
A detailed discussion about each use case is included in the [Use Cases of AI Within the Integration Domain](https://github.com/wso2/ETAC/blob/master/usecases/ai-integration-usecases.md). 

While there also are specific use cases of AI in other domains, like marketing and sales, as well as for creating new products and revenue streams, these are out of the scope of this discussion.


# Opportunity

# Trigger 
The history of artificial intelligence is nearly as old as computing. Computing pioneers, Alan Turing, and Von Neuman were fascinated with it, and Bernard Marr [2] discusses how AI improved through the last 50 years, in detail. 

The first widely known milestone of AI came in 1996 when IBM's Deep Blue defeated chess champion Garry Kasparov, who was recognized as one of the strongest players in the history of chess. Other high-profile examples include IBM Watson's win over world Jeopardy champion in 2012, and Google's AlphaGo's win over world Go champion in 2016, both of which were considered difficult problems for AI to solve. 

However, over the years, artificial intelligence also has demonstrated the ability to address day-to-day demands. For example, in problems such as face recognition and voice generation, AI has surpassed human accuracy [3]. And AI is a core enabler of autonomic vehicles.

As a result, the current interest in artificial intelligence is driven by the general interest in the potential of AI. There is no identified trigger within the integration domain for AI yet. 


# Players 
Many organizations and nations are active in AI. On the forefront are large internet companies, such as Google, Facebook, and Amazon, along with tech giants, such as Microsoft and IBM. Furthermore, there are many startups and academic research organizations. Most large enterprises have groups that use machine learning in some form. Since artificial intelligence is considered to be a transformational technology, many nations (e.g. Russia, China, France) have also entered the competition. 

Several integration vendors either already support AI, or they are exploring the possibilities.  As use cases discussed in the appendix, examples include data integration, automatic and self-service integration, and security. 


# Drivers

Artificial intelligence aligns with several forces that shape technology [4]. 

1. AI helps organizations to achieve cost savings, agility, and productivity.
2. AI enables automation to replace inefficient manual processes, such as using voice recognition to offer appropriate responses on customer calls or provide automatic lane assist to automobile drivers. 
3. AI can be used to auto-generate code or to assist developers by simplifying their task, thus reducing the expected skill levels from software developers and serving as a vital tool in handling the lack of software developers. 
4. In many cases, AI can take over complex decisions that otherwise consume significant time and attention. This includes surveillance, system configurations, and diagnosis. For example, in a case of root cause analysis, AI might be able to present the information in a manner that reduces the complexity, thus aiding humans in making decisions. 

Furthermore, the success of large internet companies has increased investments in artificial intelligence. Recent National level AI goals will be likely to further increase investments on AI [7,8]. 


At the same time, there are several forces that oppose AI. 

* First is complexity. Applying AI is complicated, and due to phenomena, such as bias, it can lead to unexpected situations. Further, AI has the potential to take us beyond our understanding, (e.g., killer robots [5] and super intelligence [6]). Those and other risks might compel the government to regulate or limit artificial intelligence. These concerns are mitigated by the fact that AI also plays a role in reducing complexity by creating models that predict complex behaviors. 
* AI interactions with governments and policies are complex. For example, standardizations help data collection, while laws mandating data release to the public domain after some years might increase data availability. However, if AI is deemed critical for national security, related export controls can slow down AI adoption. 
* AI increases our power of inference, which can have a significant effect on privacy. For example, it has been shown that often your speedometer data is enough to find where you live. Hence, privacy demands can negatively impact the use of artificial intelligence. 
* AI’s relationship with security has two sides. On one hand, it can be used to increase security by detecting anomalies. On the other, it can be a powerful tool in the hands of attackers. Moreover, the attacker just needs one scenario while the defender must consider all scenarios. Hence, the fact that it is often easier to attack than to defend might work against AI. 


# Impact
## Macro

This section discusses how AI interacts with other technologies. 

 **First**, AI interacts with several technologies that enable modern enterprise systems. 

* AI is significantly helped by big data and database technologies that came before, which created large datasets, identified use cases, and built data processing platforms.. 
* The Internet of Things (IoT) also helps AI by enabling new use cases and data, such as predictive maintenance based on data collected through IOT sensors. 
* AI  is facilitated by specialized hardware, particularly graphics processing unit (GPU) and tensor processing unit (TPU) processors. 
* APIs enable organizations to share insights, which they have derived from combining their data and AI, with customers and other participants of the supply chain. Consequently, AI-based APIs serve as a great use case for the API economy. 
* Applying AI creates incentives for organizations to collect data, clean it up, and to carry out recommended actions through an API call, creating a demand for integration technologies.  
* AI needs large computations. Hence AI and cloud technologies have a symbiotic relationship, and there is a strong incentive to operate AI-based offerings in the cloud as opposed to an on-premises deployment. Notably: 
    * AI increases the value of data, which in turn drives more everyone ( including vendors of software systems) to collect data, and it is easier for a vendor to collect AI-based data from applications in the cloud than doing so on-premises. Hence, more vendors are likely to deliver their apps as a cloud service. 
    * Cloud offerings enable vendors to consolidate data from all users as opposed to an on-premises deployment where that deployment have much smaller amounts of data.
    * It is easy to update the models with new data in the cloud. 
* AI based APIs can be a major enabler for the API economy by providing many concrete APIs for users to share with each other. 
* AI can be significantly helped by quantum computing, which uses AI use cases among its initial use cases. For example, Quantum support vector machines (SVMs) are already used in practice. 

**Second**, there is a clear connection between the availability of data and effectiveness, but the extent of the competitive advantage provided by more data has been debated. If most AI algorithms do better with larger datasets than smaller data sets, it could lead to a winner-takes-all behaviour. Companies who first get to market can collect more data, which in turn makes their models better, bringing in even more users. This behaviour is called data network effects. [9]. In this case, exclusive  access to data acts as a strong moat against competition. For example, if a vendor can build a self-service, AI-based, integration IDE and get adoption, new users will provide more data, which the vendor can use to further increase the quality of the offering, thus creating a moat. 

Others argue that data moats may only provide weak protection because the minimum viable datasets are easy to setup, and data has diminishing returns as they are collected. This is particularly true for less critical use cases, such as suggesting autofill in an integrated development environment (IDE), which benefits less from network effects. However, data can be a strong moat, for certain sophisticated processes, such as detecting suspicious activities; when a minimally viable product (MVP) data set is hard to create; or if a use case requires high accuracy (e.g. medical diagnosis). 

Several characteristics of AI provide an advantage to large companies as opposed to smaller ones. Because AI tools are widely and freely available, AI competition is likely to focus on data and AI expertise. For example, Google is a major force in enabling the wide availability of AI tools (e.g. Tensorflow). Google nevertheless differentiates itself through the availability of data and expertise. The need for data, expertise, and computing power provides a significant advantage to large organizations with extensive user bases if they can get to the market faster. Consequently, AI provides a significant opportunity for large companies in the telecom, credit card, and retail sectors who already have access to large and rich data sets. That said, it is not clear whether large companies can act fast enough to exploit the advantages. 

**Third**,  AI can reduce the skill required by integration developers. For example, when users have provided higher level steps, AI based tools can figure out the details and complete the code or propose different alternatives. In some cases, AI might be able to suggest integrations automatically. In many domains, similar use cases compete and phase out humans. Yet, given the shortage of developers, this is a welcome development as it enables many more use cases, and lower the skill levels are required from programmers. 


## Micro

At the organization level, AI related use cases offer several advantages: 

1. Cost Savings: 
    * Having humans perform tasks in organizational processes is expensive. If some of those tasks can be automated (e.g. taking video surveillance based integrations, replacing human based steps in integrations with AI), they can lead to significant savings. Having humans in the loop often leads to complex integrations because those interactions take time and because they are error prone. AI based solutions are faster and reliable. Furthermore, AI may help to simplify and improve integrations. 
    * AI-based tools can be used to reduce problems in systems by predicting and proactively generate alerts. Also, AI can be used to pinpoint problems, which enables us to fix them cheaply and faster. AI can improve scheduling, thus improving the overall results. Furthermore, AI can help make integration systems usable thus reducing user errors, which can also reduce costs. 
2. Competitive Advantage 
    * Applying AI makes tasks that have been infeasible before now feasible (e.g. image or video based inputs to integrations, personalized and targeted recommendations with marketplace). Furthermore, AI enables us to do tasks better and more frequently. (e.g. effective diagnoses and detecting anomalies in integration flows). 
    * Using AI can lead to better decisions and forecasts. This happens because AI makes better decisions or aids humans in understanding and exploring data. This could be useful on decision-based integrations. 
    * AI based solutions have predictable performance while human performance vary. For example, in the cases, such as quality control steps in integrations, AI-based solutions may provide consistently higher performance due to the predictability of their actions.  
3. New value and revenue: An organization may share insights derived though AI with other parties. For example, Walmart shares insights about products with its suppliers. Similarly, a telco may share discoveries about local trends with customers (e.g. sport events). This can be viewed as integrating value networks across companies. 


# Feasibility 

Artificial intelligence has reached a level where given enough data, an expert can use AI to solve most well-understood problems matching or exceeding human performance.However, large engineering projects are required to apply those technologies in the real world. Among examples of such projects are the self-driving car by Google and Healthcare efforts by IBM Watson. Same foundational AI technologies can be used within integration projects targeting the use cases discussed earlier. However, they require engineering projects to make them work in the real world. 

Building on big data and analytics, artificial intelligence has a large ecosystem of tools, but the demand for practitioners has outpaced the pool of professionals, making data scientists and machine-learning engineers two of the most sought after job titles. The good news is that, prospective developers are learning AI, machine learning, statistics, and related technologies. As they enter the job market, this will help to build hiring pipelines. Yet, we will face a severe shortage of professionals in the next five years. 

In terms of AI tools, there are many open source AI and machine-learning tools, such as Tensorflow, Theano, scikit-learn, which are freely available as are a wide collection of free data sets. These well-known datasets have enabled multiple practitioners to compare results and learn from each other, which has led to competition and breakthroughs. This process has been accelerated further by communities, such as Kaggle, Neural Information Processing Systems (NIPS) conference, and Knowledge Discovery and Data Mining (KDD), which are active, healthy, and have produced groundbreaking results. 

Specifications, such as Predictive Model Markup Language (PMML), have enabled models built with one tool to be exported and run within another tool. This enables integration technology, such as an enterprise service bus (ESB), to support machine-learning models easily as part of integrations. 

Many large organizations expose access to their AI models as APIs, which provides other organizations, specifically startups, with high-quality models. 

However, there are challenges. Initial success stories of AI implementations come from large organizations, such as Google, Apple, Facebook, and Amazon ( GAFA). However, deploying artificial intelligence at smaller places is much more complicated due to the complexity of incorporating models, the difficulty recruiting skilled professionals, and lack of access to large enough data sets. Let us consider each of them in detail. 

**Model Complexity:** Incorporating models into the real world is far from simple. Interpreting the results often means finding bugs, biases. Meanwhile, integrating a model with human processes, handling failures, and other processes are much less understood. For example, a model might recommend an action, but if the action has failed, any subsequent activity needs to consider this fact. 

Applying a model in the real world and handling risks, such as bias, need deep technical understanding, in-depth domain understanding, and deep thinking. Therefore, the people handling these projects need a unique mix of talents, including computer science, programming, math, statistics, and distributed systems. The subsuming job title is called “data scientist.” 

Moreover, each AI model needs fine-tuning in terms of features and hyperparameters with each kind of different data set. Therefore, it would be hard for a middleware company to build a turnkey AI pipeline that organizations can use with their own data. As a result, each project requires skilled data scientists on hand, who can handle data cleaning and the careful tuning of models. 

**Shortage of Skilled Professionals:** The challenge is that the  data scientists, programmers, and architects who can build systems based on complex AI models are in short supply. For example, the [stateof.ai](stateof.ai) website estimates that there are about 22,000 professionals worldwide with PhD.s and 5,000 researchers working on AI, where the US and China are hubs for AI talent. Google has the most talent [24] (which acts as a moat). A data scientist’s salary ranges from $300,000 to $500,000 per year [24]. So, it is hard for medium and smaller organizations to attract and hire enough skilled people.

**Lack of Large Enough Data Sets:** Furthermore, small and medium-sized organizations do not have enough data to get the required accuracy to beat human level cases. Most public data sets do not work when applying within a specific context. With the exception of a few fields, such as auto driving, the availabiity of labeled large-scale data sets are limited. There are three main approaches to addressing this problem. First is unsupervised learning from unlabeled data sets. Second is semi-supervised learning from a small amount of  labels and a much larger unlabeled data set. Third is transfer learning from a large data set in a different setting that we have obtained and used to build the model. (see [18]). 

Consequently, large organizations with significant resources can build their custom models, but to bring AI into individual organizations, better technologies, methodologies, best practices, and tools that hide complexity are needed. Several efforts may solve these challenges, most notably better tools and cloud AI building blocks. 

**Better Tools:** Newer tools guide users through the process of building models without the need to understand the fine details of artificial intelligence. There are four broad approaches. First is using wizards that guide users through the process of building a model. Second is mapping AI into a database such that the analysis can be performed simply by querying databases (e.g., BayesDB [25]). Third is mapping AI to a spreadsheet where users can build the model with spreadsheets functions. Fourth, algorithms known as automatic statisticians can accept data and automatically build models with minimum input from the user. However, they have only limited success, and they consume 100 times or more computing power than a model built by an expert (see [17]). Although progress is being made, currently available tools either handle only simple cases, or they require deep AI understanding from the user. 

**AI Building Blocks:** If data formats are well known (e.g. banking or healthcare data) and key performance indicators (KPIs) are well defined, then reusable models can be built for those use cases. Examples are disease detection in healthcare, marketing insights, spatiotemporal models, and analytics for specific sports. Some of those models may be shared through APIs creating an algorithm economy. For example, Cloud providers are building AI building blocks as APIs, which may have been trained using large amounts of data. Users can take advantage of the much-improved models. 

In addition to the challenges noted above, people often trust human judgment and are hesitant to relinquish control to artificial intelligence.  For example, we faced a situation where the user preferred to set the value himself even when the AI-driven app was capable of automatically accomplishing the task. 

Furthermore, AI models need to be carefully audited, and the provenance needs to be tracked. For instance, an attacker may introduce bias into an AI model by feeding carefully manipulated data into the model. Such attacks are hard to detect and difficult to trace back to the attacker even after detection. To date, little work has been done to address these challenges.


# Future 
## Risks

Let’s now focus on the risks associated with AI. 

Most of the risks already exist with human decision makers. Yet, within AI, the same weaknesses are much more dangerous due to three factors: broad integration, wide application, and invisible application without oversight. First, AI is highly integrated where it makes decisions in increasingly important aspects of our lives (e.g., selecting people for an interview, picking suspicious people for further investigation). Second, since the per unit cost of AI is small, it tends to be applied much more frequently than with humans. Third, people have divergent opinions, and when decisions are made transparently, the diversity helps us detect and fix problems. However, unlike cases with humans, decisions from machine-learning models will be applied automatically  without any oversight, which increases the risk of harm by many factors. 

Artificial intelligence faces several risks. 

The first immediate risk faced by AI is bias, where the AI learns the inherent bias in the data caused by human behavior, a risk discussed in the book “Weapons of Math Destruction” by Cathy O’Neil [25]. The impact of bias goes beyond human bias due to its broad integration, wide application, and transparent nature without oversight. The solution is nontrivial. It is not enough to remove fields that might create a bias (e.g., gender, race, age), since other seemingly innocent fields might act as a proxy for those fields. For example, an address in a certain neighborhood might act as a proxy for race; the name might act as a proxy for gender, or name of the degree might act as a proxy for age. (see [11]). Removing bias is an active research area. 

Second, AI increases our power of inference, which can have a significant effect on privacy. For example, your speedometer data often is enough to find where you live. On the other hand, AI creates incentives for organizations to collect data as much as possible. This is likely to spur a backlash against data collection and the use of AI. A case in point is San Francisco, which has banned the use of face recognition technology by authorities [18]. 

Third, most accurate models are complex. Interpreting the model and explaining the reason behind a specific decision is hard, which stops the application of AI in many use cases, such as credit scores or the justice system. For instance, with the General Data Protection Regulation (GDPR), the “right to explanation” may apply broadly for many use cases, and even those, such as job screening, might need model interpretability under fair opportunity laws. Because these concerns will limit AI use cases, the problem is being actively researched. Notably, [20] describes an effort to build a parallel explanation model with the AI model. 

Fourth, the potential for artificial intelligence to foster mass job replacement is well known. Therefore, the adaptation of AI in many cases will need negotiation with many parties, including trade unions and government agencies. 

Fifth, artificial intelligence is not perfect, and even when it makes a false detection (a.k.a. False-Positives), systems would act if as such failures were not possible.  For example, someone who matches demographics to obesity might be bombarded with fast food advertisements, or someone with a certain background may not be accepted into a university program, because his demographics suggest he is unlikely to finish earning a degree. In the US with 327 million people, even with a high accuracy of 99%, AI will be wrong in 1% of the time, which means 3.27 million people may be negatively affected by poor pattern matching. We have yet to explore these aspects broadly. 

Sixth is that when AI-based systems are pitched against each other in competitive fields, it can lead to unexpected situations—such as the time that online pricing algorithms set a book’s price $23 million due to a price war [21]. Following are a few more examples. We do not yet understand the best approaches for handling such use cases.  For example, within integration use cases involving AI based security, artificial intelligence can be used to defend as well as to attack. For example, it can be used to probe, create realistic phishing attacks, and even guess passwords. Just like SPAM, there is a risk of escalating AI battles in security without improving the situation and thereby forcing each side to be worse off than the start. 

These risks are not show stoppers. However, they can lead to problems, and AI practitioners need to pay careful attention to them when applying AI.
 
## Timeline
When thinking about an AI timeline within integration, there are two considerations. First, it is useful to classify use cases as critical and non-critical, since that decides the adoption velocity. Second, adoption by medium and small organizations (SME) is much more complex. 

Considering the first, Artificial intelligence is already widely used by tech-driven giants, such as Google, Amazon, IBM, and Facebook. AI-based features are a critical part of their offerings and their competitive advantage, and most of us unwittingly use AI daily by using their services. Furthermore, several larger organizations (e.g., Fortune 500) have had AI embedded within their products for a long time. For example, newer appliances (e.g., washing machines, air conditioners) include machine learning for automatic configurations and adaptive behavior. 

However, most initial use cases focus on non-critical decisions. For example, in a Google search or a movie recommendation, the cost of having a false positive—something that the system thinks relevant but is not—is minimal. There are some exceptions where false positives can have a serious impact. One area is autonomous driving cars. Google is working carefully to prove their reliability, and after many years of achieving impressive results, they have yet to be adopted widely. Other critical use cases, such as healthcare, will likely need the same careful process for adoption. 

Even among non-critical use cases, we are likely to find that seemingly innocent use cases can have a significant impact. One example is filter bubbles in social media. Although only showing news that confirms one’s belief may seem harmless in the short term, many have argued that filtering news can be harmful in the long run [22]. Another example is CV/resume screening for jobs. Wide use of AI and built-in bias may significantly affect candidate choices. And even with traffic use cases, mistakes can create costly traffic jams. Sooner or later, there will be well publicized incidents, and these scenarios will also face increased scrutiny. 

Adoption of AI within integrations will also be governed by the same considerations where the first adoption would be non-critical use cases, and the use of AI for critical use cases, such as within healthcare decision-related integrations, will take longer than envisioned. 

Considering the second, the future of AI use cases for medium and small organizations (SME) is more complex. As discussed under “Feasibility,” many use cases have complex aspects that are expensive to solve and maintain by an SME until we see rapid progress among tools, such as automatic statisticians. Instead, most SMEs are likely to start with the use of AI-based APIs, and they will prefer a domain-specific solution that only requires minimal work on their part. As they make progress, they will build their own models, and they might choose to build combined models.

The need among SMEs for solutions creates an opportunity for AI-based startups to build models and serve them through cloud APIs. Some of these models will recompose existing APIs but will go native as they build up. However, generic models will only work for particular domains. Therefore, it is likely that such startups will focus on specific domains, such as health and payments. 

More and more integrations and applications will add AI-based features by tapping into cloud APIs. Meanwhile, IDEs will facilitate inclusion of those AI models to day-to-day applications. 

Open source AI tools and communities will continue to thrive in education and prototyping, and some software as a service (SaaS) offerings will use them in the backend. However, due to the expertise needed and deployment complexities, custom AI models will be built relatively rare by SMEs. 

Let us explore use cases we identified in terms of technology readiness, criticality, and risks. 


|Use case| Criticality and risks| Technology Readiness|
|---|---|---|
|Integrations required to enable AI| N/A| Technology is ready and supported as a part of integration middleware; wider adoption is likely.| 
|Data Integration|No immediate critical outcomes. However, mistakes add up, and they might be hard to find and fix later. Therefore, a concise effort needs to be made to ensure the quality of data (e.g., human operators and agents scanning data for inconsistencies using exploratory analysis).|Initial work is done and available as functionality built into the data integration middleware. Further work is needed. Will take 3-5 years to mature. |
|Extracting useful information from human|No immediate critical outcomes. However, mistakes add up, and they might be hard to find and fix later. Therefore, concise effort needs to be made to ensure the quality of data (e.g., human operators and agents scanning data for inconsistencies using exploratory analysis).|Initial work is done and available as part of functionality built into the data integration middleware. Further work needed. Will take 3-5 years to mature.This is already hitting beyond human accuracy in some cases. Supported mostly as cloud APIs.|
 |Increasing usability of systems|Non-critical| Limited work has been done so far. Will be supported within other tools, such as IDEs. Often need custom models for each use case.| 
|AI support within existing data stores| Outcomes depend on the type of use case. |Already happening. Shipped as part of existing storage systems. Expected to find adoption within 3-5 years.| 
|Algorithm Economy| Market is not yet ready, but there is a promise. |Technology is ready.| 
|Self-driving Operations (DevOps and Regulatory Compliance)| OK with human oversight| Data collection and first level decisions are done. Further work needed. Supported as part of PaaS platforms or middleware offerings. |
|Automatic and Self-Service Integration| Needs the testing side to improve as well. Human oversight helps but does not cover all cases. Some form of sandboxes might be needed to be safe. |Shipped as a part of IDE for integration. Initial versions are available. Likely to take 5-10 years to mature. |
|Security| OK with human oversight| Supported as part of mature products or cloud APIs. Further refinements needed. Risk of an algorithm war exists.|  
|Business Automation| Depends on the use case. |Technology is ready. Feasibility is mostly decided by data availability. Custom development is needed|
|API Marketplace| Market is not yet ready. | Technology is ready and supported as part of an API marketplace. |

<p align="center">Table 1: Feasibility of Use Case Classes</p>

Among different use cases, security is the most well-developed segment of AI, with a multi-million market and mature products (e.g., Splunk, Securonix, RSA, and LogRythem) that either run on-premise or as an API. However, as we discussed in the “Risk” subsection, artificial intelligence can be used for attacks as well as for defense, which can degrade AI-based security to a never-ending tug-of-war from which neither side can leave. 

Artificial intelligence will create many Integration use cases. Furthermore, AI support within existing data stores has the potential for wide adoption as it needs little effort from organizations. 

In conclusion, we make the following observations 

* Enabling AI in an enterprise involves collecting, cleaning up, and creating a single representation of data as well as enforcing decisions and exposing data outside, each of which leads to many integration use cases. Hence, AI indirectly creates demand for integration.
* A weakness in AI decisions is much more harmful than a weakness in a human decision for three reasons. First, AI is being integrated into our lives. Second, since the per-repeat cost is small, AI is used more frequently. Third, different people have different opinions, which provides oversight, but AI is often applied transparently without any supervision. Both integration and non integration use cases should carefully considers ramification of those challenges such as bias and false positives.  
* AI aligns well with many emerging technologies (e.g., big data, IoT, APIs, cloud), which already play significant roles within integration use cases.  
* AI needs data, which in some cases leads to significant competitive advantages. The need to collect data will drive vendors to offer most AI products in the cloud via APIs. 
* When applied to competitive fields, such as security or stock markets, where AI-based systems end up competing, AI might lead to worse-than-before situations. 
* Due to a lack of expertise and data, custom AI model building will be limited to large organizations. It is hard for small and medium size organization to build and maintain custom models. Many AI use cases will be solved as cloud APIs that let vendors concentrate data and expertise. Many integration use cases discussed will be solved in this manner. 
* There are significant AI-based integration use cases. Among them 
    * Security, Data Integration, Extracting useful information from humans, and AI support within existing data stores already have systems available and are likely find more adoption. 
    * Increasing Usability, Self Driving Operations (DevOps and Regulatory Compliance), Automatic and  Self-Service Integration do not face critical challenges but will need 5-10 years of development for wide adoption  
    * Business Automation will often be infeasible for SMEs if not already supported as a cloud API. 

# References
1. Srinath Perera et al, "Emerging technology analysis canvas (ETAC)." https://github.com/wso2/ETAC/blob/master/ETAC.md, 2018.
2. Bernard Marr, A Short History of Machine Learning -- Every Manager Should Read, https://www.forbes.com/sites/bernardmarr/2016/02/19/a-short-history-of-machine-learning-every-manager-should-read/#45c6118a15e7, 2016
3. Is Artificial Intelligence surpassing human level accuracy? https://blog.wecognize.com/blog/2018/04/18/artificial-intelligence-surpassing-human-level-accuracy/, 2018
4. Srinath Perera, Catalysts, Inhibitors, and Transformers: Ten Governing Forces shaping Technology, 2018, https://hackernoon.com/catalysts-inhibitors-and-transformers-ten-governing-forces-shaping-technology-57a793bfbf0
5. Victor Tangermann, Scientists Call for a Ban on AI-Controlled Killer Robots, 2019, https://futurism.com/scientists-ban-ai-killer-robots
6. Maciej Ceglowski, Superintelligence: The Idea That Eats Smart People, https://www.youtube.com/watch?v=kErHiET5YPw, 2016 
7. James Vincent , China is about to overtake America in AI research, https://www.theverge.com/2019/3/14/18265230/china-is-about-to-overtake-america-in-ai-research, 2019
8. Pauline Bock, Meet the brain Macron tasked with turning France into an AI leader, 2019, https://www.wired.co.uk/article/cedric-villani-france-artificial-intelligence 
9. Peter Zhegin, Data network effects for an artificial intelligence startup, Towards Data Science, 2018, https://towardsdatascience.com/data-network-effects-for-an-artificial-intelligence-startup-7f6fab10ba85
10. Martin Casado and Peter Lauten,  The Empty Promise of Data Moats, https://a16z.com/2019/05/09/data-network-effects-moats/, 2019
11. Karen Hao, This is how AI bias really happens—and why it’s so hard to fix, MIT Technology Review, https://www.technologyreview.com/s/612876/this-is-how-ai-bias-really-happensand-why-its-so-hard-to-fix/ 2019
12. Attacking Machine Learning with Adversarial Examples, https://openai.com/blog/adversarial-example-research/
13. Attacks against machine learning — an overview, Elie BurszteinDate May 2018, https://elie.net/blog/ai/attacks-against-machine-learning-an-overview/
14. Dipanjan (DJ) Sarkar, A Comprehensive Hands-on Guide to Transfer Learning with Real-World Applications in Deep Learning, 2018, https://towardsdatascience.com/a-comprehensive-hands-on-guide-to-transfer-learning-with-real-world-applications-in-deep-learning-212bf3b2f27a 
15. D. Sculley, Gary Holt, Daniel Golovin, Eugene Davydov, Todd Phillips, Dietmar Ebner, Vinay Chaudhary, Michael Young, Machine Learning: The High Interest Credit Card of Technical Debt, SE4ML: Software Engineering for Machine Learning (NIPS 2014 Workshop), https://ai.google/research/pubs/pub43146
16. Roman Seyffarth, Machine learning: Moving from experiments to production, https://blog.codecentric.de/en/2019/03/machine-learning-experiments-production/, 2019
17. Anmol Rajpurohit, Automatic Statistician and the Profoundly Desired Automation for Data Science, https://www.kdnuggets.com/2015/02/automated-statistician-data-science.html
18. Alex Graves, Marc Aurelio Ranzato, Unsupervised Deep Learning - Google DeepMind & Facebook Artificial Intelligence NeurIPS 2018
19. Kate Conger, Richard Fausset and Serge F. Kovaleski, San Francisco Bans Facial Recognition Technology, https://www.nytimes.com/2019/05/14/us/facial-recognition-ban-san-francisco.html, 2019
20. LEMNA: explaining deep learning based security applications Guo et al., ACM Conference on Computer and Communications Security, 2018, https://blog.acolyer.org/2018/11/30/lemna-explaining-deep-learning-based-security-applications/ 
21. Chris Baraniuk, Bad Things that happen when algorithms run online shops, http://www.bbc.com/future/story/20150820-the-bad-things-that-happen-when-algorithms-run-online-shops  
22. Eli Pariser, Beware online "filter bubbles", https://www.ted.com/talks/eli_pariser_beware_online_filter_bubbles?language=en, 2011 
23. Srinath Perera, Paul Fremantle, Frank Leymann , The Role of Blockchain in Future Integrations, https://github.com/wso2/ETAC/blob/master/outlooks/blockchain4integration_outlook.md 
24. State of AI Report 2019, https://www.stateof.ai/
25. Cathy O’Neil, "Weapons of Math Destruction", https://www.goodreads.com/book/show/28186015-weapons-of-math-destruction


# Original Authors
Original authors are Srinath Perera (srinath@wso2.com), Paul Fremantle (paul@wso2.com), Frank Leymann (frank@wso2.com). 

# Acknowledgments
Many thanks to Nuwan Dias, Kasun Indrasiri from WSO2 who have provided significant and useful feedback.

# Help us improve 
We welcome and appreciate any feedback, changes, or contributions. Please send a pull request, create a github issue, or send a mail to srinath@wso2.com.

To receive updates to ETAC and ETAC-based emerging technology analysis, please subscribe to our [Global Technology Outlook Updates Newsletter](https://wso2.com/subscribe/global-technology-outlook-update).

# About WSO2 and Our Research

In 14 years in business, and as the #1 Open Source integration and API management vendor, WSO2 continually invests in areas beyond products. Our Research for Integration team regularly produces our Global Technology Outlook (GTO) — an effort to identify emerging technology trends, classify them based on their potential, and assess a relevant subset of technologies in detail. We do so using our Emerging Technology Analysis Canvas (ETAC). Our research is public in an effort to maintain our commitment to openness, quality, innovation, and integration leadership. 



