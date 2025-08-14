# Layered Architecture for Data Aggregation and Delivery

## **Layer 1 – Data Sources & Access Layer**

### **1a. Data Sources (Systems of Record)**
- **Description**: Authoritative systems that store or provide raw, unprocessed data.  
- **Examples**:  
  - Relational Databases (PostgreSQL, MySQL)  
  - External APIs & Third-Party Services (e.g., ratings providers, payment gateways)  
- **Purpose**: Maintain source-of-truth data in its native format.  

### **1b. Data Access Gateway**
- **Description**: A unified access layer (e.g., Hasura) that exposes data sources through a consistent GraphQL API.  
- **Responsibilities**:  
  - Abstract underlying databases & services  
  - Manage entity relationships across data sources  
  - Provide event triggers and scheduled tasks (cron jobs)  
- **Industry Analogy**: API Gateway + Data Access Layer.  

---

## **Layer 2 – Domain Aggregation Layer**

- **Description**: Composes complete domain entities by aggregating and enriching data from multiple upstream sources.  
- **Responsibilities**:  
  - Consolidate attributes from different systems  
  - Apply domain-level business logic and transformations  
- **Example** (*Hotel Entity*):  
  - Base hotel data → from GraphQL (Hasura)  
  - Ratings → from third-party ratings API  
  - Content & descriptions → from CMS  
- **Industry Analogy**: Backend-for-Frontend (BFF) for domain services or an **Aggregation Service Layer** in microservices architecture.  

---

## **Layer 3 – Product Delivery Layer**

- **Description**: Serves product-specific, optimized views of domain entities to client applications.  
- **Responsibilities**:  
  - Select only relevant fields required by the target frontend/app  
  - Format and structure data for optimal performance and user experience  
  - Minimize payload size and tailor responses for specific product needs  
- **Industry Analogy**: **Backend-for-Frontend (BFF)** or **Presentation API Layer**.  

---

## **Key Benefits of This Architecture**
- Clear separation of **data ownership**, **aggregation logic**, and **product-specific views**  
- Facilitates reuse of aggregation logic across multiple products  
- Enables independent scaling and evolution of each layer  
- Reduces coupling between frontends and raw data sources  
