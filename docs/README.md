# INTRODUCTION

For years, applying Artificial Intelligence to business problems has been possible, but not practical for mainstream organizations. Over the last few years, access to cheap storage at massive scale, combined with nearly limitless on-demand compute, has changed that. The cloud has enabled an environment where Artificial Intelligence is accessible to nearly all organizations. It has made returns and the cost model compelling for not just the extremely high-value endeavors, but also for more common scenarios.

Still, many organizations struggle with where to start in AI: what scenarios are most accessible, and therefore the most appealing initial project candidates? Which are the most compelling and impactful to my business? And how will the specialized technologies required change the way we acquire and manage skills in our organization?

Predictive Maintenance is emerging as one of the most demanded applications of predictive analytics, for several reasons:
* First – and most importantly – preventing the unexpected failure of critical assets, and extending their useful life, has unambiguous cost reduction benefits in both equipment and personnel. Those benefits directly translate to increased profitability.  Further, as these assets are often directly related to the organization's value chain, more reliable use normally results in better customer service and therefore brand benefits. In the short term, service outages may only increase costs, but in the longer term, outages negatively impact an organization's reputation, making it costly to keep existing customers and add new ones.
* Second, predictive maintenance has nearly universal applicability: almost every industry possesses highly capitalized assets that make the returns on greater utilization material to the bottom line.  The applicability in discrete manufacturing is obvious, but process manufacturing, energy, transportation, oil and gas, consumer goods, health care, and many other industries utilize long term assets that daily affect their competitiveness.
* Third, unlike many other AI domains, the concepts, approaches and algorithms employed are more intuitive than many other emerging AI problems.  Detecting anomalies in equipment performance, predicting when failures may occur, identifying the cause of the failure, and estimating the remaining useful life are relatively clearly understood; answers can often be obtained using simple algorithms such as regression or classification, which are mature and widely utilized, relative to other cutting-edge data science approaches.

This solution describes the logical services that can be delivered to a customer – or leveraged if those logical services already exist – and then combined to deliver business impact through a production predictive maintenance deployment.  An important design goal is modularity: the service functions provide utility on their own, and can be re-used in different scenarios to solve many problems over time.  In the end, a more flexible and modular approach allows us to provide value faster, and to re-use existing services to solve other business problems at a lower incremental cost.

![](img/data_flow.png)

## Data Ingress and Storage

Solving any business problem with AI starts with data. The question you are trying to answer will affect what data you need, and in what format, quantities, and time horizons.  Most predictive maintenance problems are based on the desire to understand the behavior and operational health of distributed devices with embedded sensors. A message ingestion service supports ingesting real-time operational data from those sensors and saving it to long term (cold) cloud storage.  For most predictive maintenance scenarios, this message ingestion substrate also provides two-way communication back to remote devices to configure and manage those devices over time.

## AI Modeling Engine
The core AI engine supports the iterative training of a machine learning model on the data that has been ingested into cloud storage and prepared for processing. After that model – or models, if there are multiple unique business problems that the organization is trying to solve – has been created with sufficient quality to meet the business objective, the model(s) will be used in production to evaluate (or ‘score’) incoming operational data from the devices you wish to manage.  This AI training environment must reflect the size and complexity of the data it is based on, as well as the processing requirements of the algorithm being used.

## Online Featurization Engine

## Scoring Engine
The runtime AI system supports evaluating incoming real-time (more accurately, near-real-time) data, and calculating a relevant prediction based on the developed model. The result of this scoring needs to be persisted somewhere – like Azure Tables or CosmosDB – so that the prediction can be consumed by the appropriate business process that can act on the insight delivered by that prediction.

## Visualization and Action Components
The dashboard is used to present the near-real-time status of the business data (such as from distributed devices, in a remote monitoring scenario), as well as the predictions based on the incoming telemetry data, so that the appropriate personnel can act on that information based on a well-defined business process.  The visualization format, as well as tooling, will be affected by how the predictions will impact business processes, such as whether the event warrants a response in seconds, hours or days.

Ultimately, all the logical services listed above cumulatively represent a cloud AI platform that can support solving not just predictive maintenance business challenges, but other industry-specific or general business challenges.
Predictive maintenance has wide applicability in many industries, as most companies utilize long-term assets that are core to delivering on their business model. There are also many industry-specific ISV solutions that more narrowly target these challenges by industry.

---

Please refer to the [Solution Design](Solution-Design.md) document for an in-depth overview of the solution's architecture and technical trade-offs.
