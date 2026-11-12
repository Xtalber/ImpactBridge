# ImpactBridge

**AI-Assisted Fundraising Verification and Transparent Donation Platform**

ImpactBridge is an AI-powered crowdfunding platform designed to improve trust and transparency in online fundraising. It helps campaign creators submit supporting documents, enables reviewers to assess campaign information, and allows donors to track their contributions.

## Problem Statement

Online fundraising platforms face challenges such as fake campaigns, forged documents, limited verification, and a lack of transparency regarding donations. Donors often find it difficult to determine whether a campaign is genuine and how their contributions are being used.

ImpactBridge aims to address these challenges through AI-assisted document analysis, structured verification workflows, risk assessment, and transparent donation tracking.

## Key Features

### AI-Powered Document Analysis
- Upload hospital bills, medical estimates, and supporting documents.
- Extract important information using Google Gemini API.
- Identify missing information and potential inconsistencies.
- Present extracted information for human review.

### Campaign Verification
- Review submitted campaign documents.
- Check institution information against available verification evidence.
- Identify potential duplicate documents and suspicious patterns.
- Support campaign approval, rejection, and correction requests.

### Campaign Management
- Create and manage fundraising campaigns.
- Upload supporting documents.
- Track campaign verification status.
- View campaign submission history.

### Donor Dashboard
- Explore available fundraising campaigns.
- View campaign details and verification information.
- Donate through PayPal Checkout.
- Track personal donation history.

### Admin Dashboard
- Review submitted campaigns.
- Inspect extracted document information.
- View risk assessment results.
- Approve, reject, or request campaign corrections.
- Monitor donation and campaign activity.

### Transparent Impact Tracking
- Maintain donation records.
- Track confirmed contributions.
- Display campaign fundraising progress.
- Maintain an audit trail of important activities.

## Technology Stack

- Frontend: React.js, TypeScript, Tailwind CSS
- Backend: Node.js, Express.js
- Database: PostgreSQL
- AI Integration: Google Gemini API
- Payment Gateway: PayPal REST API and Orders API
- Development Tools: Git, GitHub, Postman

## Application Workflow

1. A campaign creator registers and submits a fundraising campaign.
2. The creator uploads supporting documents.
3. Gemini analyzes the uploaded documents and extracts relevant information.
4. The verification system checks available institution information and identifies inconsistencies.
5. A reviewer examines the submitted information.
6. Approved campaigns become available to donors.
7. Donors select a campaign and make contributions through PayPal Checkout.
8. Confirmed payments are recorded in the database.
9. Campaign progress and donor transaction history are updated.

## System Architecture

```text
                    IMPACTBRIDGE
                         |
             +-----------+-----------+
             |                       |
          FRONTEND                 BACKEND
             |                       |
       User Interface          Authentication
             |                       |
       Donor Dashboard        Campaign Management
             |                       |
     Creator Dashboard       Document Processing
             |                       |
       Admin Dashboard          Gemini API
             |                       |
             |                Verification Engine
             |                       |
             |                 Risk Assessment
             |                       |
             |                 Payment Service
             |                       |
             |                    PayPal
             |                       |
             +-----------+-----------+
                         |
                      DATABASE
                         |
               Donation and Audit Records
```

## Getting Started

### Prerequisites

- Node.js
- npm
- PostgreSQL
- Git
- Google Gemini API Key
- PayPal Developer Sandbox Account

### Clone the Repository

```bash
git clone YOUR_REPOSITORY_URL
cd ImpactBridge
```

### Install Dependencies

```bash
npm install
```

### Environment Configuration

Create a `.env` file in the backend directory.

```env
NODE_ENV=development
PORT=5000

DATABASE_URL=your_postgresql_connection_string

GEMINI_API_KEY=your_gemini_api_key

PAYPAL_CLIENT_ID=your_sandbox_client_id
PAYPAL_CLIENT_SECRET=your_sandbox_client_secret
PAYPAL_ENVIRONMENT=sandbox
PAYPAL_BASE_URL=https://api-m.sandbox.paypal.com
```

### Start the Application

```bash
npm run dev
```

## PayPal Integration

ImpactBridge integrates PayPal Checkout to process donation transactions in Sandbox mode.

### Payment Workflow

1. Donor selects a campaign and enters a donation amount.
2. Backend creates a PayPal order.
3. Donor approves the payment using a Sandbox Personal account.
4. Backend captures the approved order.
5. PayPal's capture response is validated.
6. Confirmed payment details are saved in the database.
7. Donor history and campaign fundraising progress are updated.

### Sandbox Testing

Two separate PayPal Sandbox accounts are used:

- Business Account: Merchant account used to receive payments.
- Personal Account: Buyer account used to test donations.

All API credentials are stored securely on the backend.

A donation is marked successful only after PayPal confirms a completed payment capture.

## Security

- Server-side API credential management.
- Secure document upload and storage.
- Role-based access control.
- Campaign ownership validation.
- Payment amount validation.
- PayPal webhook signature verification.
- Duplicate payment prevention.
- Audit logging for important actions.
- Human review for campaign verification decisions.

## Project Status

ImpactBridge is currently under development. Payment processing is being tested using PayPal Sandbox. Some verification and institutional checks may operate using prototype or simulated data.

Sandbox transactions do not represent real financial payments.

## Future Scope

- Advanced document fraud detection.
- Stronger institution verification.
- Improved payment reconciliation.
- Institution-level payment and settlement workflows.
- Enhanced donor transparency.
- Advanced risk assessment.
- Production-grade security and compliance.

## Disclaimer

ImpactBridge is designed to support transparent fundraising. AI-generated analysis does not independently prove document authenticity or guarantee campaign legitimacy. Payment processing and institutional disbursement depend on payment provider capabilities, account eligibility, and applicable regulations.

## License

This project is currently available for development and demonstration purposes.
