
<h1 align="center">Use Cases of AI Within the Integration Domain
</center></h1>


# Integrations required to enabling AI 
Enabling AI in an enterprise involves collecting data, bringing data into a single data representation, cleaning it up, enforcing decisions of the models communicating with many systems, carrying out actions, and coordinating those actions. Often, organizations are composed of several data silos established between different departments or systems. Some data and resulting models need to be exposed outside the organization. 

Creating a labeled data set requires us to collect data from multiple stages of business processes and correlating them. Furthermore, actual outcomes for each prediction should be tracked and fed back into the model. It is often accepted that about 70-80% of the AI project’s time is spent on clearing and engineering features. However, when applying AI within an organization, most of these steps must be done across different systems, continuously. Each of the above is an integration problem. An AI project that deals with real-world data will create massive demand for integration.   

# Data Integration
An organization receives data from many sources kept in many systems. Cleaning, connecting, and resolving different data formats and correlating diverse data from many sources continuously is a major challenge. For example, Michel stonebreaker mentioned data integration as a major use case for AI. Further, some of this data is stored, indexed, and kept to be used later. Doing this manually is expensive and requires significant human effort. AI can improve this process by cleaning data, creating data catalogs, discovering index structures, and finding similar data types. For example, Informatica already supports some of the use cases, and Trifacta enables users to interact with the system and clean data, and the tool can generalize those actions and convert examples into rules, which can be later used to clean up the data within the AI pipeline. 

# Extracting useful information from humanEnhancing Inputs
While building enterprise systems and interfacing with users and the real world, both digesting data and outputting data is a challenge. Computers need a GUI, command lines, or programming language-based interfaces. These interfaces are complex and unnatural to humans. However, with AI, we can digest data in images, audio, video, and natural languages, which are more natural for users. Additionally, we can represent output also using similar forms. This enables our applications to accept more user friendly inputs and digest data from a range of sources. 

For example, now we can track and analyze a football match just through video without any sensors. Also, AI can now listen to natural language activities (tweets) and extract significant information. These developments have increased the amount of data available for analysis. While it is possible for end users to build their own custom models, prebuilt models (usually as APIs) are available.  

# AI-Based Security
As systems become more connected and distributed, security challenges are increasing daily. Integration technology connects internal and external systems, some of which live in different security domains. AI can help in detecting attacks on those systems.

* **Fraud detection**: The use of fraud detection to monitor activities for potential fraud and anomalies has been a topic of interest for many years. AI has widened the scope and accuracy of fraud detection systems. 
* **Adaptive authentication**: Multi-factor authentication, which verifies the user through multiple means, such as passwords, biometrics, SMS, has had increased adoption. Adaptive authentication takes this one step forward, by making the system change the authentication criteria based on perceived risks (e.g. ask to send a one-time password (OTP), if a user is coming from a new IP address). 
* **Context**: AI can aid in detection scenarios, such as detecting session hijacking or a suspicious authentication by looking at the context (time, IP, user agent, frequency);  learning API call sequences and using them to detect suspicious calls; and detecting anomalous event rates from the same user account.  
* **Detecting/masking data**: AI can aid in detecting sensitive data in requests, such as passwords, credit card numbers, social security numbers, etc. and either stop the request or automatically mask the data. This is useful for regulatory and security compliance in GDPR, PCI-DSS, and HIPPA. 
* **Continuous authentication:** The main idea is to authenticate based on activities while considering the whole context. This would make non-critical common cases easy and critical, uncommon cases hard. This is often adopted by companies that handle critical data, such as financial firms.  

# AI-Enabled IDE 
An AI-enabled IDE can increase the productivity of integration developers by providing better suggestions, code templates, auto generate code, and error detection. Following are some examples. 

* The IDE can suggest available APIs for the user based on the current context. 
* The IDE can warn the user when a new data type is too close to some other data type thus removing unnecessary data types (e.g. Informatica).
* When the developers have initialized the client for a new API, the IDE can offer to automatically do the required data transformations. For example, Dell Boomi proposes data transformation together with confidence ranking on each suggestion. 
* An editor can guide the user through the process of building some constructs. For example, Snaplogic uses AI to guide the user through the process of building data pipelines. 
* AI can be a powerful tool in data exploration and visualization. An AI tool can suggest visualizations and automatically adjust presentations of visualizations. For example, the AI tool can automatically pick color shades, resolve overlapping items in visualizations, or adjust scales. Furthermore, the tool can automatically generate visualizations based on requests issued through chat. 
* AI can help tracing and debugging programs. For example, adaptive monitoring can collect more data in a suspicious area, point out errors, and provide suggestions for fixes. 
* AI can help users build personalized and adaptable UIs and menus without the need to write additional code by incorporating such decisions into UI frameworks. For example, menus can change based on the current context users are viewing. 
* AI-based performance simulations can help developers in tuning the performance of applications, detecting anti-patterns, and keeping the developed program within a given performance target. For example, microservices and API-based programs are highly sensitive to network calls, and AI-based simulation can help keep the programs within given latency limits. 
* AI can generate test cases, inject failures, and predict scenarios that might break the system. 
* AI can help in generating documentation from code. 

# Self-Service Integrations for Non-Programmers
AI can enable non-programmers to build integrations. When users have provided higher-level steps, AI-based tools can figure out the details and complete the code or propose different alternatives. This is visual programing, which seldom worked. Why? After the user drags and drops elements and connects them in the canvas, he has to go through a dreaded set of forms to give details. By automatically generating mappings and gluing code with minimal user input,  AI can change this.

Another alternative approach is program using instructions provided through Natural language, e.g. from a chat bot. For example, Worketo enables its users to create integrations provided from the chat. 

# Replacing Humans in Processes
Humans’ decisions are expensive and take longer. Furthermore, the presence of humans converts the process to a long-running process, giving rise to new failure cases. AI lets us replace some of the tasks usually completed by humans in processes or workflows. For example, we can use AI to verify a user who signs up for a new account and only escalate complex cases. 

# Self-Driving Operations 
AI can be a powerful tool in automating DevOps by removing or reducing the need for human intervention while running systems. This applies for systems including those handling integration. Following are some use cases.
 
* **Auto tuning**: AI can be used to inspect the environment and auto tune a system, enabling it to run without tedious configurations by the user. AI can also continuously tune a system, responding to changing environments and workloads, for example tuning a thread pool and database connection pools. 
* **Predictive maintenance**: AI can help detect and predict potential failures by monitoring current activities and triggering alerts to proactively take corrective actions to avoid potential failures. 
* **System management**: By detecting anomalies, raising alerts, and finding potential root causes, AI can help the DevOps team in managing the system. Furthermore, AI-based monitoring systems can automatically change tracing levels when anomalies are detected, making detailed sensor data available at critical points. 
* **Chat-based querying and control of the systems**: For example, a chat-based system may allow control of the system based on preconfigured templates. 
* **Automatic compliance**: AI can be used to provide automatic compliance and quality of service (QOS) checks, as well as issue warnings 

# AI Co-located with Data 
Applying AI to a custom dataset requires a significant investment from organizations. However, enterprises that manage users’ data (e.g. databases, customer relationship management (CRM) systems, and enterprise resource planning (ERP) software) can build AI capabilities into their products providing AI scenarios out of the box. For example, AI companies are integrating data from CRM and ERP systems to support use cases, such as lead scoring, churn prediction, and customer ticket prioritization. 

# Algorithm Economy
In the algorithm economy, algorithms are exposed via APIs that can be integrated to build systems. This removes the need for organizations to build their own AI systems, thus making it useful for medium and small organizations to apply AI. Furthermore, this removes the challenges related to a lack of data. And, it creates an opportunity for organizations that already have data to monetize it; [algorithmia.com](algorithmia.com) is an example of this model. 

# Enhanced Usability
AI can be used to increase the usability of systems by providing better error messages to users,  inferring/fixing errors in messages, or providing suggestions, such as: Did you mean this? You might also like that.

# Marketplaces (e.g. API Marketplaces)  
AI can provide recommendations and ratings in an API marketplace. 

