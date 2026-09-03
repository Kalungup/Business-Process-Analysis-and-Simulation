# -Business-Process-Analysis-and-Simulation
Business process analysis and simulation project using BPMN, process modelling, performance analysis, and data-driven process improvement.
 ## Nordic Secure Bank – AS-IS Customer Onboarding Process

This project analyses and models the **AS-IS customer onboarding process** of Nordic Secure Bank using **Workflow Nets**. The process will subsequently be analysed and simulated to identify process behaviour, bottlenecks, resource utilisation, waiting times, and potential areas for improvement.

---

## 1. Business Case

Nordic Secure Bank is a fictitious bank with a customer onboarding process that was originally designed and configured by a consulting company.

The bank has requested a redesign and improvement of its customer onboarding processes. Before designing a future **TO-BE process**, this project focuses on understanding, modelling, and analysing the existing **AS-IS process**.

The AS-IS process consists of a normal customer onboarding scenario and a cancellation scenario.

---

## 2. AS-IS Scenario

### 2.1 The Normal Scenario

The bank has only one branch in central Stockholm, where **Anna**, a clerk, works.

Anna registers scanned customer requests by filling out a form in the system. This takes an average of **20 minutes per case**.

After registration, **Kim**, the credit investigator, checks the customer's credit using a website called **UC**. This takes approximately **25 minutes**.

Kim then records the credit check result in the system, which takes an additional **10 minutes**.

### Credit Check Decision

If the credit check result is **not OK**, which occurs in approximately **10% of cases**, **Elin**, the CRM officer, writes and sends a rejection letter through the system. The system then notifies the customer by email.

This task takes approximately **25 minutes**.

If the credit check result is **OK**, the process continues.

---

### Customer Profile and Transactions

Elin enables the customer to update their profile.

At the same time, **Linda**, an accounting assistant, enables incoming transactions.

These two activities are performed **in parallel** through the system:

- Enable customer profile update – **10 minutes**
- Enable incoming transactions – **10 minutes**

Once both activities are completed, Elin informs the customer that they can use the system by sending a separate email.

This takes approximately **25 minutes**.

---

### Fraud Investigation

After the customer has been informed, a **fraud investigator** reviews the case for potential fraud.

The bank currently employs two fraud investigators:

- **Peter**
- **Maria**

The fraud investigation is a very time-consuming activity because every case must be checked against several anti-money-laundering rules.

The investigation takes approximately **3 hours per case**.

In approximately **80% of cases**, no potential fraud is found.

---

### No Potential Fraud

When no potential fraud is identified:

1. Linda enables the customer to have full access.
2. Elin informs the customer by email.
3. The process ends.

The activities take:

- Enable full customer access – **10 minutes**
- Inform customer – **10 minutes**

---

### Potential Fraud Detected

If the fraud investigator identifies the case as a potential fraud case, the investigator submits a request for an **external fraud investigation** through a website.

Completing all required information takes approximately **30 minutes**.

In approximately **90% of these cases**, the bank receives the external investigation result within **1 day**.

If no result is received within **2 days**, the fraud investigator sends a reminder through the external website.

The reminder takes approximately **10 minutes**.

The reminder may be repeated until an external investigation result is received.

---

### External Investigation Result

Once the external investigation result arrives, the fraud investigator registers the result in the internal system.

This takes approximately **20 minutes**.

The result then determines how the process continues.

#### Result: No Fraud

In approximately **90% of external investigations**, the result indicates that there is no fraud.

In this situation:

1. Linda enables the customer to have full access.
2. Elin informs the customer by email.
3. The process ends.

---

#### Result: Fraud

If the external investigation result indicates fraud:

1. Elin disables the customer's ability to update their profile.
2. Linda disables incoming transactions for the customer's account.

These two activities are performed **in parallel** and each takes approximately **10 minutes**.

After both disabling activities are completed:

- Elin sends a rejection letter by email – **25 minutes**
- The fraud investigator reports the case to the police – **25 minutes**

These two activities can also be performed **in parallel**.

However, the rejection notification and police report **cannot be performed in parallel with the earlier disabling activities**.

This is because regulations require that the customer must not be able to take any action at the moment they are informed or the case is reported to the police.

---

## 3. Resources

The main resources involved in the AS-IS process are:

| Resource | Role |
|---|---|
| Anna | Clerk |
| Kim | Credit Investigator |
| Elin | CRM Officer |
| Paul | CRM Officer |
| Linda | Accounting Assistant |
| Peter | Fraud Investigator |
| Maria | Fraud Investigator |

The bank has recently hired **Paul**, another CRM officer who can assist Elin.

The reported time for each task includes a **5-minute setup time**.

---

## 4. Cancellation Scenario

The customer may cancel their request **at any time after registration and until the end of the process**.

When a customer requests cancellation, the CRM officer cancels the case.

There is one important exception.

If the bank receives the external fraud investigation result and the result indicates that the case is a **fraud case**, the remaining process steps must be completed because of regulatory requirements.

Therefore, the process must **not allow a cancellation request to be processed once an external fraud investigation has returned a positive fraud result**.

---

## 5. AS-IS Workflow Net

The AS-IS process will be represented using a **Workflow Net**.

The model will capture:

- Customer request registration
- Credit investigation
- Credit decision
- Customer rejection
- Parallel customer profile and transaction activities
- Customer notification
- Fraud investigation
- Fraud investigator resource allocation
- External fraud investigation
- External investigation waiting time
- Investigation reminders
- External investigation result
- Fraud/no-fraud decisions
- Customer access activation
- Fraud-related account restrictions
- Rejection and police reporting
- Customer cancellation
- Cancellation exception after a positive fraud result

The Workflow Net will be used as the foundation for subsequent process analysis and simulation.

---

## 6. Process Analysis

The AS-IS model will be analysed with particular attention to:

- Process execution time
- Waiting time
- Resource utilisation
- Parallelism
- Decision probabilities
- Bottlenecks
- Rework/repetition
- External waiting periods
- Cancellation behaviour
- Potential process inefficiencies

---

## 7. Simulation

After constructing and validating the AS-IS Workflow Net, the process will be simulated to investigate its behaviour under the conditions described in the business case.

The simulation will consider the stated:

- Processing times
- Probabilities
- Available resources
- Parallel activities
- External investigation delays
- Reminder behaviour
- Cancellation scenarios

Simulation results will be used to support the analysis of the existing process.

---

## 8. Project Objectives

The main objectives of this project are to:

1. Model the Nordic Secure Bank customer onboarding process as a **Workflow Net**.
2. Represent the AS-IS process faithfully according to the business case.
3. Capture the different process paths and decision probabilities.
4. Model parallel activities and resource constraints.
5. Analyse the behaviour and performance of the process.
6. Identify potential bottlenecks and inefficiencies.
7. Simulate the AS-IS process.
8. Use the analysis as a foundation for potential future process improvement and TO-BE design.

---

## 9. Project Structure

```text
Business-Process-Analysis-and-Simulation/
│
├── README.md
│
├── docs/
│   ├── business-case.md
│   ├── as-is-process.md
│   └── methodology.md
│
├── models/
│   ├── as-is-workflow-net/
│   └── diagrams/
│
├── simulation/
│   ├── model/
│   ├── data/
│   └── results/
│
├── analysis/
│   ├── performance-analysis.md
│   ├── bottlenecks.md
│   └── findings.md
│
└── images/
    ├── as-is-workflow-net.png
    └── simulation-results.png
