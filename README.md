# PracticeAWS
Hands-on AWS practice projects focused on developing and deploying machine learning solutions. Includes exercises on data processing, model training, and cloud-based ML workflows for aspiring Machine Learning Engineers.

---

Keywords para buscar roles:
- "MLOps Engineer"
- "Data Engineer (MLOps)"
- "ML Infrastructure Engineer"
- "DataOps Engineer"


---



## SECTION 1: INFRASTRUCTURE & DEPLOYMENT

P1: “How would you deploy an ML model to production?”

“In APIUX, I deployed an end-to-end facial verification pipeline, so I usually think in terms of the full lifecycle.

First, I serialize the model outputs — in this case, 512-dimensional InsightFace embeddings — and version them.

Then I expose inference through a FastAPI service with strict input validation to avoid malformed requests.

The service is containerized using Docker, including dependencies like OpenCV and InsightFace, to ensure reproducibility.

For deployment, we used AWS Lambda for serverless inference, targeting sub-100ms p95 latency. This worked well given our traffic patterns.

On the monitoring side, I track model metrics like precision and drift, system metrics like latency and error rate via CloudWatch, and set alerts if thresholds are breached.

For scaling, we rely on AWS auto-scaling based on CPU and memory usage.

Finally, everything is integrated into a CI/CD pipeline with automated tests before promoting changes from DEV to PROD.

If performance degradation is detected, I’d orchestrate automated retraining using Prefect, for example on a weekly cadence or triggered by drift signals.”

---

P2: “How do you handle model performance degradation in production?”

“I’ve dealt with this in a document duplicate detection system.

First, I separate data drift from model drift. I monitor input distributions — for example cosine similarity distributions of embeddings — and compare training vs. production.

If model metrics like precision drop below a defined threshold, I trigger an investigation.

Then I do root-cause analysis:
– New document types usually mean retraining with fresh data
– Changes in lighting or angles often require better data augmentation

Short-term mitigation includes A/B testing against the previous model and automated rollback if performance drops below the threshold.

Long-term, I rely on a retraining pipeline orchestrated with Prefect that pulls recent data, retrains the model, validates on a hold-out set, and deploys only if there’s a measurable improvement — typically above 2%.”

---

P3: “How would you design a data pipeline processing 1TB per day?”

“I’d design it as a scalable, observable pipeline.

For ingestion, I’ve used tools like Azure Data Factory to pull data daily from multiple APIs, with early validation for schema, nulls, and duplicates.

Orchestration would be handled with Prefect, where each step — extract, transform, feature engineering, and load — is explicitly monitored.

Transformations would be done using dbt models or Spark if volume exceeds what SQL can handle efficiently.

Data would be loaded into a warehouse like BigQuery or Snowflake, partitioned by date for efficient querying.

From a performance perspective, Spark would handle large parallel transformations, intermediate results would be cached, and I’d target a 2-hour end-to-end SLA.

Finally, I’d monitor pipeline duration, row counts, and data quality metrics, with alerts if execution exceeds expected time or validations fail.”

---

P4: “Experience with Docker or Kubernetes?”

“My hands-on experience is mainly with Docker and serverless architectures rather than Kubernetes.

I’ve containerized FastAPI applications for ML inference and deployed them using AWS Lambda and ECS. I also use Docker consistently in development to ensure reproducibility.

For orchestration, I’ve worked extensively with Prefect Cloud for managing workflows in production.

While I haven’t worked directly with Kubernetes in production yet, I understand core concepts like pods, services, deployments, and scaling strategies.

I’m very comfortable learning new infrastructure tools quickly — I’m self-taught in Prefect, FastAPI, and computer vision frameworks — so ramping up on EKS would be straightforward.”

---

## SECTION 2: DATA ENGINEERING & PIPELINES

P5: “Experience with Snowflake or data warehouse design?”

“I haven’t worked directly with Snowflake, but I have solid experience with SQL-based data modeling and performance optimization.

In previous roles, I optimized schemas, stored procedures, indexes, and partitions to support analytics and reporting.

In Snowflake, I’d design a layered architecture:
– A staging layer with raw data
– A warehouse layer using dbt models for facts and dimensions
– A mart layer optimized for reporting and ML use cases

I’d also leverage clustering keys aligned with query patterns and rely on Snowflake’s automatic partition pruning.

If Snowflake is core to the role, I’d be happy to pursue certification.”

---

P6: “Tell me about your experience with Apache Spark.”

“My Spark experience is intermediate.

I’ve used PySpark for scalable ETL in freelance projects, mainly DataFrame operations like joins, aggregations, and filtering, and basic performance tuning such as caching.

My strength is knowing when to use Spark versus SQL or Pandas. For large-scale transformations over hundreds of gigabytes, Spark is the right tool. For analytics, I often prefer SQL in the warehouse.

If Spark is critical for this role, I already have the foundation and can deepen my expertise quickly.”

---

## SECTION 3: CLOUD & DEVOPS

P7: “What’s your experience with AWS?”

“I’ve worked with AWS across multiple projects.

I’ve used Lambda for serverless ML inference, EC2 — including GPU instances — for training, S3 for datasets and model artifacts, DynamoDB and RDS for metadata storage, and CloudWatch for monitoring.

I’ve also had basic exposure to SageMaker for training and deployment.

Areas I’m still improving include Infrastructure as Code with Terraform and advanced networking concepts like VPC design.

I’m comfortable learning these quickly if they’re important for the role.”

---

P8: “How would you monitor an ML model in production?”

Improved answer (very strong):

“I monitor models across four layers.

First, model performance: precision, recall, F1, ROC-AUC, recalculated daily when labels are available.

Second, data drift: I compare feature and embedding distributions between training and recent production data, triggering alerts when statistical shifts exceed thresholds.

Third, prediction drift: changes in the ratio of positive vs. negative predictions over time.

Fourth, system metrics: API latency, throughput, error rates, and resource utilization via CloudWatch.

Alerts are automated — for example, if precision drops below 80% or p95 latency exceeds 100ms.

Dashboards summarize trends for stakeholders, and incidents trigger either rollback or retraining workflows.”

---

## SECTION 4: SQL & ANALYTICS

P9: “What’s your SQL level?”

“I’d say intermediate to advanced.

I’m comfortable with complex joins, window functions, CTEs, and query optimization using execution plans, indexes, and partitions.

In one case, I optimized a stored procedure from 12 seconds to under 500ms by eliminating a table scan and adding the right index and partitioning strategy.

My strength is integrating SQL with Python for analytics and ML pipelines.

I haven’t done very advanced tuning like optimizer hints or materialized views, but I understand the concepts.”

---

P10: “Design a feature engineering approach for fraud detection.”

“I usually think in terms of temporal, similarity, behavioral, and interaction features.

Temporal features capture recency and velocity.
Similarity features include cosine similarity between embeddings and string similarity against historical documents.
Behavioral features capture transaction frequency, device changes, and geographic variance.
Interaction features combine signals — for example, high similarity plus short time gaps indicating higher risk.

Features are encoded appropriately, scaled where necessary, and validated using historical fraud labels, optimizing for precision and recall.”

---

P11: “What if a Data Scientist wants to deploy without testing?”

“I’d start with empathy — urgency is real — but I’d explain the risk clearly.

I usually propose a compromise: a gradual rollout, starting with 5% of traffic, combined with minimal but critical tests.

These include performance comparison with the previous model, input validation, and failure handling.

I frame MLOps as a risk-reduction tool: one hour of testing can prevent days of production issues.

This approach worked in APIUX — we caught a JSON edge case that would have caused downtime.”

---

P12: “How do you prioritize when overwhelmed?”

“I prioritize based on impact and urgency.

Production issues affecting users come first, followed by work that prevents future incidents, then improvements.

I also communicate proactively with my manager: if everything seems urgent, I ask for alignment rather than guessing.

Transparency and prioritization prevent burnout and mistakes.”