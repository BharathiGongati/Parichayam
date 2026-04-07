# Parichayam Visual Flow Diagrams

These diagrams are designed for admin and business-owner training.

## 1. End-to-End User Journey

```mermaid
flowchart LR
    A[Index Page] --> B[Auth Page]
    B --> C{Sign In or Register}
    C -->|Sign In| D[Member Dashboard]
    C -->|Register| E[Account Basics]
    E --> F[OTP Verification if Enabled]
    F --> G{Trial or Paid Plan}
    G -->|Trial| D
    G -->|Paid| H[Checkout]
    H --> I[Payment Verification]
    I --> D
    D --> J[Profile Completion]
    J --> K[Live Match Generation]
    K --> L[Matches Shown to User]
    L --> M[Interest or Shortlist]
    M --> N[Message / Upgrade / Matchmaker Support]
```

## 2. Matchmaking Engine Logic

```mermaid
flowchart TD
    A[Live Member Pool] --> B[Remove Self Profile]
    B --> C[Keep Only Opposite Gender]
    C --> D[Remove Hidden / Suspended / Invalid Profiles]
    D --> E{Same Gotra Hard Block?}
    E -->|Yes| F[Exclude Candidate]
    E -->|No| G[Score Candidate]
    G --> H[Age Fit]
    G --> I[Community Fit]
    G --> J[Location Fit]
    G --> K[Education Fit]
    G --> L[Income Fit]
    G --> M[Profile Completeness]
    G --> N[Activity and Trust]
    G --> O[Kundali Score if Entitled]
    O --> P[Add Limited Boost / Paid Bonus]
    P --> Q[Sort by Final Score]
    Q --> R[Show Ranked Matches]
```

## 3. Admin Controls and Business Impact

```mermaid
flowchart TD
    A[Admin Panel] --> B[Auth Settings]
    A --> C[Payment Settings]
    A --> D[Dashboard Builder]
    A --> E[Profile Form Builder]
    A --> F[Community Manager]
    A --> G[Gotra Manager]
    A --> H[Verification Queue]
    A --> I[User Access Control]
    A --> J[Agents and Franchise]
    B --> B1[Changes signup and login behavior]
    C --> C1[Changes checkout and activation]
    D --> D1[Changes what members can see]
    E --> E1[Changes data quality and required fields]
    F --> F1[Improves matching cleanliness]
    G --> G1[Controls same-gotra and traditional logic quality]
    H --> H1[Improves trust and response rate]
    I --> I1[Controls add-ons and restrictions]
    J --> J1[Controls referrals and payout operations]
```

## 4. Daily Operations Loop

```mermaid
flowchart LR
    A[Morning Check] --> B[New Registrations]
    B --> C[Verification Queue]
    C --> D[Trial Expiry Watchlist]
    D --> E[Payments and Activations]
    E --> F[Agent Applications and Payouts]
    F --> G[Midday Match Quality Spot Check]
    G --> H[Support Follow-Up]
    H --> I[Evening Revenue and Risk Review]
    I --> A
```

## 5. Verification Flow

```mermaid
flowchart TD
    A[Member Uploads Aadhaar or Income Proof] --> B[Verification Queue]
    B --> C[Admin Reviews Document]
    C --> D{Valid or Invalid}
    D -->|Valid| E[Approve Verification]
    D -->|Invalid| F[Reject and Request Better Proof]
    E --> G[Trust Score Improves]
    G --> H[Profile Ranks Better]
```

## 6. Agent Referral Flow

```mermaid
flowchart TD
    A[Agent Application] --> B[Admin Review]
    B -->|Approved| C[Agent Account Created]
    C --> D[Agent Refers Member]
    D --> E[Member Registers with Agent Reference]
    E --> F[Payment Converts to Paid Membership]
    F --> G[Commission Record Created]
    G --> H[Payout Request]
    H --> I[Admin Approves or Rejects]
```
