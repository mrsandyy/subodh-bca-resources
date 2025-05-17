# **UNIT IV: E-Commerce Application Development**

---

## **4. E-Payment Systems**

---

### **4.1 Types of E-Payment Systems**

#### **4.1.1 Electronic Funds Transfer (EFT)**

**Definition:**  
EFT is the electronic transfer of money from one bank account to another without the use of paper documents.

**Process/Flow:**

1. **Initiation:** Customer instructs bank (online or at ATM) to transfer funds.

2. **Authorization:** Bank verifies credentials (PIN, OTP, digital signature).

3. **Clearing & Settlement:** Funds are debited from sender’s account and credited to beneficiary via interbank networks (e.g., SWIFT, NEFT, RTGS).

4. **Confirmation:** Both parties receive transaction confirmations.

**Features:**

- Real-time (RTGS) or batch processing (NEFT).

- Secure interbank messaging protocols.

- Automated reconciliation.

**Advantages:**

- Fast and reliable for large sums (RTGS).

- Minimal manual intervention.

**Disadvantages:**

- May incur fees per transaction.

- Depends on banking network availability.

---

#### **4.1.2 Electronic Cash (E-Cash)**

**Definition:**  
E-Cash is a digital equivalent of physical cash, enabling anonymous, peer-to-peer electronic payments.

**Process/Flow:**

1. **Withdrawal:** User obtains digital tokens from bank (blinded tokens ensuring anonymity).

2. **Payment:** User sends tokens to merchant; tokens cannot be traced back to user.

3. **Deposit:** Merchant deposits tokens at their bank, which verifies token validity.

**Features:**

- **Anonymity:** User identity hidden via cryptographic blinding.

- **Offline Capability:** Small transactions can occur without real-time bank contact.

**Advantages:**

- Privacy-preserving.

- Good for micropayments.

**Disadvantages:**

- Risk of double-spending if merchant’s bank isn’t online.

- Limited adoption and standardization.

---

#### **4.1.3 Electronic Cheque (E-Cheque)**

**Definition:**  
An E-Cheque is a digital version of a paper cheque, signed electronically and processed through banking networks.

**Process/Flow:**

1. **Issuance:** Payer creates an electronic cheque via bank’s website, digitally signs it.

2. **Transmission:** E-Cheque sent to payee by email or payment platform.

3. **Verification:** Payee’s bank verifies digital signature and payer’s account balance.

4. **Settlement:** Funds are transferred from payer’s to payee’s account.

**Features:**

- Legally equivalent to paper cheques under IT Act.

- Supports post-dated payments.

**Advantages:**

- Faster clearing than paper cheques.

- Reduced paper handling costs.

**Disadvantages:**

- Requires robust digital-signature infrastructure.

- Potential for fraud if signatures are compromised.

---

#### **4.1.4 Credit/Debit Card Payments**

**Definition:**  
Payments made by transferring funds from a debit card (directly from account) or credit card (loan extended by issuer) via POS terminals or online gateways.

**Process/Flow (Online):**

1. **Checkout:** Customer enters card details (number, expiry, CVV).

2. **Authorization Request:** Merchant sends data to payment gateway.

3. **Issuer Bank Verification:** Card network routes to issuing bank for authentication and fraud checks.

4. **Authorization Response:** Issuer approves or declines.

5. **Capture & Settlement:** Approved authorizations are captured and settled in batch to merchant’s account.

**Features:**

- Wide global acceptance.

- Various authentication methods (3D Secure, OTP).

- Credit risk managed by issuer.

**Advantages:**

- Convenient and familiar to consumers.

- Chargeback and dispute mechanisms protect cardholders.

**Disadvantages:**

- Transaction fees (interchange, gateway).

- Risk of data breaches if PCI-DSS not followed.

---

#### **4.1.5 Smart Card Payments**

**Definition:**  
Smart cards are plastic cards with embedded microprocessor chips that store and process data for secure transactions.

**Types:**

- **Contact Smart Cards:** Require insertion into a reader.

- **Contactless (RFID/NFC) Cards:** Tap-and-go transactions.

**Process/Flow:**

1. **Initialization:** Card issued by bank and loaded with credentials or value.

2. **Authentication:** Reader and card perform mutual challenge-response.

3. **Transaction:** Card’s chip securely debits stored value or initiates account debit.

4. **Update:** New balance written to card or bank ledger updated.

**Features:**

- On-card PIN verification (offline).

- Secure cryptographic processing on card.

**Advantages:**

- High security against skimming.

- Can store multiple applications (e-cash, loyalty).

**Disadvantages:**

- Higher card issuance cost.

- Requires specialized readers.

---

#### **4.1.6 Digital Tokens and Electronic Purses/Wallets**

**Definition:**  
Digital tokens and e-wallets store value or payment credentials electronically for use in various online and offline transactions.

**Types:**

- **Prepaid E-Wallets:** Loaded with funds in advance (e.g., Paytm, Google Pay balance).

- **Stored-Value Tokens:** Cryptographic tokens representing digital cash (e.g., blockchain tokens).

**Process/Flow (E-Wallet):**

1. **Top-Up:** User adds funds via bank transfer, card, or cash at agent.

2. **Payment:** User selects e-wallet, authenticates (PIN/biometric), and confirms payment.

3. **Settlement:** Wallet provider transfers funds to merchant or another wallet.

**Features:**

- Multi-channel access (app, web, POS).

- Often integrated with loyalty and rewards.

**Advantages:**

- Convenience of one-click payments.

- Supports micropayments and peer-to-peer transfers.

**Disadvantages:**

- Dependency on wallet provider’s uptime and security.

- Regulatory requirements for e-money issuers.

---

### **4.2 Payment Gateways**

#### **4.2.1 Definition**

A payment gateway is a service that **authorizes and processes** payment transactions by securely transmitting payment data between merchants, acquiring banks, and issuing banks.

#### **4.2.2 Components**

1. **Merchant Interface API/Plugin:** Integrates with e-commerce platforms.

2. **Transaction Server:** Receives and routes payment requests.

3. **Security Layer:** SSL/TLS encryption, tokenization, fraud detection.

4. **Settlement Engine:** Batches and forwards transactions to acquiring banks.

5. **Dashboard & Reporting:** Real-time transaction monitoring, reconciliation.

#### **4.2.3 Transaction Flow**

1. **Payment Initiation:** Customer selects “Pay” → enters payment details.

2. **Data Encryption:** Gateway encrypts data before transmission.

3. **Authorization Request:** Gateway forwards to acquiring bank/card network.

4. **Issuer Bank Processing:** Validates details, checks funds, fraud rules.

5. **Authorization Response:** Approval/decline sent back through gateway.

6. **Capture:** Merchant confirms capture (immediate or delayed).

7. **Settlement & Funding:** Gateway batches captures, sends to acquiring bank for settlement into merchant account.

#### **4.2.4 Key Features & Services**

- **Multi-Payment Method Support:** Cards, wallets, UPI, net-banking.

- **Fraud Management:** Rule engines, velocity checks, AVS, CVV verification.

- **PCI-DSS Compliance:** Ensures secure handling of cardholder data.

- **Recurring/Billing Profiles:** Automated recurring payments and subscriptions.

- **Global Transactions:** Multi-currency processing, local payment methods.

#### **4.2.5 Examples of Payment Gateways**

- **Stripe:** Developer-friendly API, global reach.

- **PayPal:** Widely recognized, buyer protection.

- **Razorpay / Paytm / CCAvenue (India):** Local bank integrations, UPI support.

- **Authorize.Net:** Established gateway with extensive features.

#### **4.2.6 Security & Privacy Considerations**

- **Tokenization:** Replaces card data with non-sensitive tokens.

- **SSL/TLS:** Encrypts data in transit.

- **3D Secure (3DS):** Adds authentication layer (e.g., OTP).

- **PCI-Compliant Vaulting:** Secure storage of payment credentials.

- **Fraud Analytics:** Machine-learning based risk scoring.

---
