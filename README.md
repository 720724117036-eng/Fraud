# FraudPulse Net 🛡️

## AI-Powered Fraud Spike Detection & Risk Operations

FraudPulse Net is a browser-based fraud-risk operations demo designed to
detect suspicious transaction patterns, explain the signals behind a
risk decision, and route high-risk transactions to a human reviewer.

**Detect → Explain → Review → Decide**

## Project Objective --- What Does It Solve?

FraudPulse Net helps identify potentially fraudulent transactions
quickly while keeping the decision process understandable to human
analysts.

It: - Automatically scores incoming transaction records. - Estimates a
fraud probability from transaction evidence. - Highlights risk signals
such as IP risk, device risk, failed attempts, transaction amount,
account age, and unusual transaction hours. - Routes high-risk
transactions to an incident queue. - Lets analysts inspect the evidence
behind a decision. - Provides manual transaction analysis. - Keeps the
human reviewer responsible for the final outcome.

**AI recommends. Humans decide.**

## Key Features

### Real-Time Transaction Stream

The command center continuously generates transaction-shaped demo
records and scores them automatically.

### Risk Scoring

Transactions receive a fraud probability and one of three decisions: -
**CLEARED** --- lower risk - **WATCH** --- medium risk - **FLAGGED** ---
high risk

### Explainable Signals

The application can show: - High/elevated IP risk - High/elevated device
risk - Multiple/repeated failed attempts - Unusually large transaction
value - Very new/relatively new account - Unusual transaction hour

### Incident Queue

Flagged transactions are routed to an incident queue for human review.

### Human Review

Analysts can record: - Confirmed Fraud - False Positive - Legitimate
Transaction - Unable to Determine

Reviewer notes can also be recorded.

### Manual Analysis

An analyst can enter transaction evidence and receive a probability,
decision, explanation, and contributing signals.

## How the Demo Scoring Works

The standalone browser version uses a fallback scoring function based on
IP risk, device risk, failed attempts, transaction amount, account age,
and transaction hour.

Decision thresholds: - **70% or higher:** FLAGGED - **40% to below
70%:** WATCH - **Below 40%:** CLEARED

The current standalone implementation identifies the model source as
**Demo scoring fallback**.

## Technology

-   HTML5
-   CSS3
-   JavaScript
-   Responsive web design
-   Browser-side transaction scoring
-   Browser-side incident/review workflow

The current project is implemented as a standalone HTML application.

## Project Structure

``` text
FraudPulse-Net/
├── index.html
└── README.md
```

Rename the application HTML file to `index.html` when deploying with
GitHub Pages.

## How to Run

1.  Clone or download the repository.
2.  Open `index.html` in a modern browser.
3.  Click **Admin** on the landing page to fill the demo credentials.
4.  Click **Enter Command Center**.
5.  Explore Command Center, Incidents, Manual Analysis, and Explanation.

## Demo Login

This is a demonstration application, not a production authentication
system.

``` text
Username: admin@fraudpulse.local
Password: Demo@1234
```

These credentials are intentionally present in the client-side demo
code. Do not use this authentication approach for a production security
system.

## GitHub Pages Deployment

1.  Create a public GitHub repository.
2.  Upload the application as `index.html`.
3.  Upload this `README.md`.
4.  Open **Settings → Pages**.
5.  Select **Deploy from a branch**.
6.  Select the `main` branch and `/ (root)`.
7.  Click **Save**.
8.  GitHub will provide the published Pages URL.

## Build Challenges & Technical Obstacles

### 1. Automatic Transaction Generation

The command center needs a continuous stream of transaction-shaped
records. The demo creates varied records from predefined risk profiles
with controlled randomness.

### 2. Risk Scoring Without a Backend

The standalone version needed to run directly in a browser. A JavaScript
fallback scoring function was used so the demo can work without a
server.

### 3. Explainability

A numerical score alone is difficult for an analyst to interpret. The
application maps observable transaction features to human-readable risk
signals.

### 4. Incident Routing

High-risk records must move from automatic detection into human review.
Flagged transactions are automatically added to the incident queue.

### 5. Human Review Workflow

The application separates AI recommendations from final human decisions.
Analysts can review evidence and record an outcome and notes.

### 6. Single-Page Navigation

Multiple operational views are combined into one HTML application.
Client-side hash routing switches between the landing page, command
center, incidents, manual analysis, transaction analysis, and
explanation views.

## Future Improvements

-   Secure backend API
-   Real authentication and authorization
-   Production ML model served from a backend
-   Database for transactions and incidents
-   Model monitoring and drift detection
-   Stronger audit logging
-   Licensed public fraud dataset for evaluation
-   Automated tests and CI/CD
-   Role-based permissions

## Project Pitch

> **FraudPulse Net detects suspicious transaction spikes, explains why
> they look risky, routes high-risk cases to analysts, and keeps humans
> responsible for the final decision.**

## Project Status

**Prototype / Hackathon Demo**

The current version demonstrates the fraud-risk workflow,
explainability, and human-in-the-loop review process. It is not intended
to be a production fraud-detection system.
