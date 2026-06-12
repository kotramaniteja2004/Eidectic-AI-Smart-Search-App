# 🧠 Eidectic: AI-Powered Smart Search Engine

**Eidectic** is a next-generation mobile utility application designed to act as a photographic memory system for your phone's media gallery. Built using a high-performance cross-platform mobile architecture and a scalable microservices machine learning backend, Eidectic replaces rigid, legacy text-string image matching with true **Semantic Vector Search**. 

With an always-on, native system overlay interface, users can execute context-aware visual query searches across their cloud-synchronized image index instantly from anywhere inside the operating system.

---

## 🚀 Core Architectural Pipelines

### 📥 1. The Gallery Synchronization Pipeline
When a synchronization cycle is initialized, assets are processed through a distributed ingestion pipeline to generate mathematical embeddings:
[Local Phone Gallery] ➡️ Local Scanner Engine
│
▼
[Flutter Client]      ➡️ Photo Byte Stream Upload (Multipart API)
│
▼
[Render API Gateway]  ➡️ Python Backend (FastAPI Wrapper)
│
├──> Uploads Binary File to [Supabase Cloud Storage]
│
└──> Dispatches Asset payload to [Google Gemini Vision API]
│
▼
[Gemini Engine] extracts Textual JSON Description
│
▼
[Gemini Embedding Model] translates Text to 768-Dim Coordinates
│
▼
[Supabase DB Engine]  ⬅️ Stores Dense Vector Coordinates & Account metadata

---

### 🔍 2. The Semantic Search & Extraction Pipeline
When a natural language concept query is executed from the floating background overlay bubble, the system processes the request via an instant matrix math lookup:

[Floating Search Bubble] ➡️ User Inputs Natural Language Query ("coffee bill from last Tuesday")
│
▼
[Render API Gateway]     ➡️ Passes query array payload to [Google Gemini text-embedding-004]
│
▼
[Math Vector Space]      ➡️ Generates corresponding 768-dimension floating-point array
│
▼
[Supabase pgvector]      ➡️ Executes Cosine Similarity matrix calculation (1 - (A <=> B))
│
▼
[Database Filtering]     ➡️ Isolates rows by active User_ID/Device_ID & filters proximity thresholds
│
▼
[Render API Gateway]     ➡️ Resolves matching unique Photo_IDs into secure public CDN asset URLs
│
▼
[Flutter UI Engine]      ➡️ Stops background Isolate loading state & displays the matching images

---

## 🛠️ The Technical Stack

* **Frontend Framework:** `Flutter` & `Dart` (Native OS overlay injection, isolated background threading)
* **Backend Framework:** `Python` (`FastAPI` asynchronous routing gateway hosted on `Render`)
* **Cloud Database Engine:** `Supabase` / `PostgreSQL` (Relational schema modeling with `pgvector` index clustering)
* **Object Storage CDN:** `Supabase Storage Buckets` (Private asset tokenization mapping)
* **Artificial Intelligence Interface:** `Google Gemini API` (`gemini-3.1-flash-lite` for vision description parsing & `text-embedding-004` for mathematical structural coordination)

---

## ⚡ Engineering Triumphs & Problem Solving

### 🪐 OS-Isolated Process Communication (The Floating Window)
**The Challenge:** A primary production goal was creating an unkillable floating search circle bubble capable of querying the server from anywhere inside the operating system. However, background overlay windows in Android run on completely isolated background threads (separate memory isolates), making them entirely blind to the foreground application state and `Supabase.auth` session memories.

**The Solution:** Engineered a custom data-persistence synchronization layer using native device disk access wrappers (`SharedPreferences`). When a user authenticates in the primary foreground dashboard, their unique encrypted token metadata profiles are securely written to the physical storage partition. The isolated background overlay entry-point (`@pragma("vm:entry-point")`) intercepts these shared disk variables on runtime, allowing the background bubble thread to flawlessly pass device metrics and query routes without launching the core application layout.

### 🛡️ Privacy-First Metadata Modeling
**The Challenge:** Users are naturally protective of their personal photos. Uploading, copying, or duplicating raw local image configurations across multiple global databases introduces heavy server load and significant privacy liabilities.

**The Solution:** Implemented a security-first abstract metadata pipeline. During sync tracking operations, images are strictly evaluated in memory arrays to generate text abstractions. Only the corresponding numerical vector coordinates, anonymized account tracking hashes (`user_id`), hardware identifiers (`device_id`), and text index scripts are committed to the cloud database rows. No raw photos are publicly cataloged or exposed, keeping individual galleries 100% private and protected.

### 📉 Scaling Beyond Free Tier API Threshold Limitations
**The Challenge:** High-throughput gallery sync processes can easily flood AI endpoints, crashing projects under restrictive free-tier Request-Per-Minute (RPM) boundaries.

**The Solution:** The backend server uses high-speed geometric similarity mapping. Instead of running continuous loop calls asking the AI model to analyze images line-by-line during a search, the database transforms query matching into a pure database-level mathematical vector equation. By offloading calculation operations onto Supabase's `pgvector` hardware layer via Cosine Distance queries, database search lookups finish executing in a few milliseconds—allowing the system to scale fluidly to thousands of assets while keeping overall cloud infrastructure costs incredibly low.

---

## 📋 Production Readiness & Deployment Architecture
* **Binary Packaging:** Compiled into optimized Android App Bundles (`.aab`) with asset-shrinking configurations (`minifyEnabled true`, `shrinkResources true`).
* **Code Obfuscation:** Flutter compilation parameters injected with obfuscation flags to prevent reverse engineering of proprietary endpoints or backend pipeline mappings.
* **Service Compliance:** Fully integrated with Android Foreground Service compliance properties (`specialUse` background management wrapper systems) to ensure runtime stability across multi-tasking windows.

---
*Note: The core operational source code for this repository is kept in a private development environment to protect proprietary API mappings, server endpoints, and infrastructure security keys.*

