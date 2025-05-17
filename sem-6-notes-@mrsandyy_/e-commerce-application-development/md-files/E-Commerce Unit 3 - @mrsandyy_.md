# UNIT 2: E-Commerce Models and Strategies

---

## 3.1 Electronic Data Interchange (EDI)

### 3.1.1 Definition

Electronic Data Interchange (EDI) is the **computer-to-computer exchange** of structured business documentss in a standardized electronic format, eliminating paper, faxes, and manual intervention.

### 3.1.2 Types of EDI

1. **Point-to-Point (Direct EDI)**
   
   - **Architecture:** Secure, dedicated link between two trading partners
   
   - **Pros:** High security, predictable performance
   
   - **Cons:** High setup and maintenance cost; one-to-one only

2. **EDI via Value-Added Network (VAN)**
   
   - **Architecture:** Third-party mailbox/translator service
   
   - **Pros:** Simplifies connectivity (many-to-many), built-in auditing
   
   - **Cons:** Per-message fees; possible latency

3. **Web-EDI**
   
   - **Architecture:** Browser-based portal; no local translation software
   
   - **Pros:** Low cost of entry; easy for low-volume partners
   
   - **Cons:** Manual entry overhead; limited integration

4. **Mobile EDI**
   
   - **Architecture:** Uses mobile devices (smartphones, tablets) with EDI apps
   
   - **Pros:** On-the-go access, real-time notifications
   
   - **Cons:** Smaller screens limit complexity; security of device

---

### 3.1.3 EDI Standards

- **ANSI ASC X12 (North America):**
  
  - > 300 transaction sets (e.g., 810 = Invoice, 850 = Purchase Order)

- **UN/EDIFACT (International):**
  
  - Multi-sector, multilingual; segments like UNH…UNT envelopes

- **TRADACOMS (UK Retail):**
  
  - Early retail-sector standard; largely superseded by EDIFACT

- **ODETTE (Automotive Europe):**
  
  - Messages for supply-chain (e.g., DELFOR = Delivery Forecast)

- **XML-Based (ebXML, cXML):**
  
  - Human-readable, integrates with web services; uses namespaces

---

### 3.1.4 EDI Security and Privacy Issues

1. **Authentication & Non-Repudiation**
   
   - Digital signatures with PKI ensure sender identity and message origin cannot be denied.

2. **Confidentiality**
   
   - Payload encryption (PGP, S/MIME, SSL/TLS) to protect content from eavesdropping.

3. **Integrity**
   
   - Hashing (SHA-256) plus signature to detect tampering.

4. **Access Control**
   
   - Role-based permissions on VAN mailboxes or AS2 endpoints.

5. **Audit & Logging**
   
   - Transaction logging, acknowledgement (997/999) tracking for non-repudiation.

6. **Data Privacy**
   
   - Field-level masking/encryption for PII (customer data, pricing).

---

### 3.1.5 EDI Implementation Steps

1. **Partner & Document Definition**
   
   - Identify trading partners, document types (e.g., ORDERS, INVOIC), and transaction volumes.

2. **Choose Standards & Protocol**
   
   - Select ANSI X12 vs. EDIFACT; communication protocol (AS2, FTP-SSL, VAN).

3. **Data Mapping & Translation**
   
   - Map internal fields → EDI segment.element (e.g., N1.01 = “BY” for buyer).
   
   - Use translation tools or middleware (Gentran, BizTalk).

4. **Connectivity Setup**
   
   - Establish network links, configure AS2 certificates or VAN mailboxes.

5. **Testing & Certification**
   
   - Syntax tests (TA1), functional/business-rules tests, end-to-end partner validation.

6. **Production & Monitoring**
   
   - Go-live; monitor transmissions, exceptions, acknowledgements.

7. **Maintenance**
   
   - Update mappings for new partner requirements or document versions.

---

### 3.1.6 EDI Document Structure

```
ISA|00|          |00|          |ZZ|SENDERID      |ZZ|RECEIVERID    |210517|1200|U|00401|000000905|0|P|>
GS|PO|SENDERID|RECEIVERID|20210517|1200|1|X|004010
ST|850|0001
BEG|00|NE|PO12345||20210517
N1|BY|BUYER NAME|92|123
N1|SE|SELLER NAME|92|456
PO1|1|10|EA|15.00||VN|ABC123||IN|ITEMDESC
CTT|1
SE|8|0001
GE|1|1
IEA|1|000000905
```

- **Interchange Envelope (ISA…IEA)**

- **Functional Group (GS…GE)**

- **Transaction Set (ST…SE)**

- **Segments & Data Elements** with separators (|, ~)

---

## 3.2 Electronic Catalogs & Digital Libraries

### 3.2.1 Electronic Catalogs

- **Definition:** Digitally-accessible product/service listings with rich metadata, pricing, images, and ordering.

- **Key Components:**
  
  - **Product Attributes:** SKUs, descriptions, technical specs
  
  - **Search & Navigation:** Faceted filters, full-text search, categories
  
  - **Pricing & Promotions:** Dynamic pricing, discount rules
  
  - **Order Integration:** “Add to Cart” APIs connecting to backend order management

**Example Flow:**

1. User searches “laptop” → filter by brand, price range.

2. Selects item → views detail page with image gallery, specs, availability.

3. Clicks “Add to Cart” → cart API updates session/cart DB.

---

### 3.2.2 Digital Libraries

- **Definition:** Networked repositories of digital content (documents, images, audio, video) with indexing, retrieval, and rights management.

- **Metadata Standards:**
  
  - **Dublin Core:** Title, Creator, Subject, Date
  
  - **MARC21:** Library cataloging format

- **Functionalities:**
  
  - **Full-Text Search & OCR:** Search within scanned documents
  
  - **Access Control:** Public vs. restricted collections; DRM for licensed content
  
  - **Digital Preservation:** Format migration, checksums for integrity

- **Use Cases:** Academic research, corporate knowledge management, archival.

---

## 3.3 E-Governance

### Definition

Use of ICT by governments to deliver services, share information, and engage citizens, with the goals of transparency, efficiency, and participation.

### Domains & Examples

1. **G2C (Government-to-Citizen):**
   
   - Online tax filing (e-filing portals)
   
   - e-Voting systems
   
   - Public grievance redressal (CPGRAMS)

2. **G2B (Government-to-Business):**
   
   - e-Procurement (GeM portal)
   
   - Licensing and compliance dashboards

3. **G2G (Government-to-Government):**
   
   - Inter-agency data sharing via secure APIs
   
   - Centralized ID systems (Aadhaar)

4. **G2E (Government-to-Employee):**
   
   - HR self-service portals
   
   - e-Learning and training platforms

---

## 3.4 E-Buying

### Definition

Procurement of goods/services electronically by organizations or individuals, encompassing requisition, approval, and purchase processes.

### Models

1. **B2C (Retail Buying):** Customer-facing online stores

2. **B2B (Corporate Buying):**
   
   - **Procurement Portals:** Punch-out catalogs integrated with ERP
   
   - **Reverse Auctions:** Suppliers bid to win contracts

3. **Group Buying:** Collective purchasing for volume discounts (Groupon)

### Workflow

1. **Requisition:** User selects items from electronic catalog → submits request.

2. **Approval:** Workflow routes to managers based on policies.

3. **Purchase Order:** Approved requisition converted to PO → sent via EDI/XML.

4. **Receipt & Invoice:** Goods received, invoices matched via 3-way match (PO, receipt, invoice).

5. **Payment:** Automated through e-payment systems (ACH, RTGS).

---

## 3.5 E-Selling

### Definition

Online marketing and sale of products/services through web storefronts, marketplaces, or social channels.

### Models & Channels

- **Direct-to-Consumer (D2C):** Brand’s own e-store

- **Marketplace:** Third-party platforms (Amazon, Flipkart)

- **Dropship:** Seller lists products but supplier ships directly

- **Social Commerce:** Shoppable posts/stories on Instagram, Facebook

### Key Components

- **Product Information Management (PIM):** Central repository for product data

- **Content Delivery Network (CDN):** Fast global access to images, videos

- **Shopping Cart & Checkout:** Secure sessions, cart persistence

- **Payment Gateway Integration:** PCI DSS compliance, multi-currency support

- **Order Management System (OMS):** Tracks orders, communicates with warehouse

---

## 3.6 E-Banking

### Definition

Delivery of banking products and services via digital channels (web, mobile apps).

### Core Services

- **Account Management:** Balance inquiry, statements, alerts

- **Funds Transfer:** NEFT, RTGS, IMPS, UPI

- **Bill Payments & Recharge:** Utility, credit card, mobile top-up

- **Investments & Loans:** Mutual funds, SIPs, loan applications

### Security Mechanisms

1. **User Authentication:**
   
   - Multi-factor (password + OTP/biometric)
   
   - Device fingerprinting

2. **Session Security:**
   
   - SSL/TLS encryption
   
   - Session timeouts, re-authentication for critical ops

3. **Transaction Monitoring:**
   
   - Real-time fraud detection (rule-based and ML-based)
   
   - Velocity checks, anomaly detection

4. **Regulatory Compliance:**
   
   - RBI guidelines, PCI DSS, KYC/AML checks

---

## 3.7 E-Retailing

### Definition

The sale of goods/services to end-consumers via the Internet, combining marketing, distribution, and customer service.

### Business Models

- **Pure-play e-tailers:** Online-only operations (e.g., Myntra)

- **Click-and-Mortar:** Online + physical stores (e.g., Big Bazaar)

- **Subscription-Based:** Recurring delivery (e.g., monthly product boxes)

### Value Chain Components

1. **Channel Integration:** Unified inventory across online and offline

2. **Logistics & Fulfillment:**
   
   - Warehousing strategy (centralized vs. hub-and-spoke)
   
   - Last-mile delivery partners, reverse logistics for returns

3. **Customer Experience:**
   
   - Personalization engines (recommendations)
   
   - Omnichannel support (chatbots, call centers, in-store pickup)

4. **Analytics & Optimization:**
   
   - A/B testing for UI/UX
   
   - Demand forecasting, dynamic pricing

---
