# Parichayam Matrimony Platform
## Admin & Business Owner Standard Operating Procedure (SOP)

### Canva Formatting Brief
Use a premium Indian matrimonial business-document style.

Recommended design direction:
- Colors: maroon `#7B1C2E`, deep maroon `#4A0E1A`, gold `#C9963A`, light gold `#E8C06A`, cream `#FDF6EC`, white `#FFFDF9`
- Headings: Playfair Display or Cormorant Garamond
- Body: DM Sans, Open Sans, or Lato
- Tone: professional, elegant, operational, launch-ready
- Use section dividers, checklists, warning boxes, example boxes, and process diagrams

---

## 1. System Overview

Parichayam is a matrimony platform designed to manage the full matchmaking journey from lead generation to paid membership, profile verification, suggestions, agent referrals, and business operations.

The system has five practical layers:
- Public website
- Authentication and onboarding
- Member dashboard
- Admin and operations panel
- Matchmaker and agent support flows

At a business level, the platform works like this:
- A user lands on the website and understands the value proposition
- The user signs up using mobile OTP, email/password, or hybrid auth flow
- The user starts with trial or paid access depending on plan selection
- The user completes profile details
- The platform stores profile, verification, preference, and account data in Firebase
- The system generates and ranks match suggestions
- The admin panel controls pricing, features, verification, dashboard behavior, fields, and staff workflows

The platform is built for Arya Vyshya matrimonial operations and includes community, gotra, kundali, premium features, agent-led acquisition, and verification-driven trust building.

---

## 2. End-to-End System Flow

### Public User Journey
1. User lands on the index page
2. User clicks sign up, login, or an enquiry action
3. User enters auth flow
4. User verifies identity through configured login method
5. User either starts on trial or chooses a paid plan
6. User enters dashboard
7. User completes personal, family, jathakam, and professional information
8. The system evaluates profile quality and eligibility
9. Match suggestions are generated from live candidate profiles
10. User can shortlist, express interest, unlock, message, or upgrade

### Business Operations Flow
1. Admin monitors new registrations
2. Admin reviews verification queue
3. Admin manages pricing, add-ons, and visibility rules
4. Admin or staff manages operational exceptions, quality control, and support
5. Agents and matchmakers support acquisition and human-assisted matchmaking

---

## 3. Page-Wise SOP

### Index Page

#### Business Purpose
The index page is the first conversion surface. Its job is to establish trust, communicate the brand promise, and move visitors into sign up, login, or enquiry actions.

#### What Happens When a User Lands
- User sees Parichayam branding, trust cues, service positioning, and entry points
- User is guided toward account creation or sign in
- In some cases, the page also supports routes into agent/franchise enquiries or admin access

#### Business Outcome
The index page should convert cold traffic into:
- New registrations
- Returning member logins
- Agent enquiries
- Paid intent

#### Admin Responsibility
- Keep brand text current
- Keep support contacts accurate
- Make sure signup and login links work
- Keep plan communication aligned with actual backend pricing

---

### Auth Page

#### Business Purpose
This page handles user creation, login, password recovery, and the commercial step where a user begins as trial or paid member.

#### Registration Flow
- User enters basic identity details
- User verifies mobile or uses configured email/password route
- User chooses membership path
- If user chooses trial, account starts on trial logic
- If user chooses paid, account is created and checkout starts

#### Login Flow
- Existing user signs in
- Password reset is available if email/password auth is enabled
- OTP may be required depending on admin auth configuration

#### Business Notes
- This is the key funnel for lead-to-member conversion
- Any misconfiguration here affects the entire business

#### Admin Responsibility
- Ensure OTP provider is working
- Ensure email/password sign-in is enabled if the business wants fallback
- Ensure payment routing works before promoting paid plans

---

### Dashboard Page

#### Business Purpose
The dashboard is the member’s working area. This is where engagement, upgrades, verification, and matchmaking actually happen.

#### What the Member Sees
- Home or overview
- Today’s Matches
- Search Partners
- Shortlisted profiles
- Interests
- Messages
- Notifications
- Edit Profile
- Kundali Match
- Psychology Profile
- Membership and settings
- Service-related modules

#### Business Meaning
This is the value-delivery area of the platform. If this page feels relevant, users trust the platform and upgrade. If this page feels weak, they stop engaging.

#### Key Operational Truth
Profile and match behavior are not on separate standalone pages in business terms. They are working sections inside the dashboard.

---

### Profile Section

#### Critical Fields
These fields matter most for quality matching and trust:
- Name
- Age or date of birth
- Gender
- City, state, country
- Community
- Gotra
- Education
- Profession
- Salary or business income
- Family details
- About me
- Photos
- Jathakam or horoscope details

#### Why Profile Completeness Matters
The live system favors profiles that are more complete and trustworthy. A half-filled profile can still exist, but it will usually rank lower and perform worse in response quality.

#### Verification Impact
Profiles with verified mobile, Aadhaar, or income signals are more trustworthy in ranking and business perception.

#### Admin Responsibility
- Encourage complete profiles
- Keep required fields realistic
- Do not make too many important fields optional

---

### Matches Section

#### Business Purpose
The matches area is where the platform proves value by showing relevant spouse suggestions.

#### Core Business Rule
Only opposite-gender profiles should appear in normal matchmaking.

#### Matching Inputs Used by the System
- Opposite gender
- Approval and visibility status
- Community compatibility
- Gotra policy
- Age compatibility
- Location fit
- Education similarity
- Income compatibility
- Profile quality
- Activity freshness
- Verification and trust
- Boost or premium visibility bonus

#### Ranking Approach
The system first removes invalid candidates, then scores the remaining candidates, then orders them from stronger fit to weaker fit.

#### Business Warning
Partner preferences exist in the product, but the current live logic is stronger on actual profile facts, admin policy, and core scoring than on deeply enforced saved preference rules. Admin should not overpromise strict preference-only matching unless that layer is expanded further.

---

### Admin Panel

#### Business Purpose
The admin panel is the operating system of the business. It controls membership economics, feature visibility, verification, data quality, staff operations, and user access.

#### Major Business Controls
- Profiles
- Bulk Profile Upload
- Pricing and Plans
- Add-Ons
- Advertisements
- Agents and Franchise
- Dashboard Builder
- Profile Form Builder
- Feature Toggles
- Field Lock Settings
- Custom Form Fields
- Gotra Manager
- Community Manager
- Ad Slides Manager
- User Access Control
- Verification Queue
- Service Partners
- Website Content
- Staff Access
- Reports

#### What These Controls Do
- Pricing and Plans: controls how the platform earns revenue
- Add-Ons: controls upsell products such as boost or advanced features
- Dashboard Builder: controls which dashboard modules members can access
- Profile Form Builder: controls field visibility and mandatory data
- Gotra and Community Managers: improve matching quality by standardizing data
- Verification Queue: builds trust in the member base
- User Access Control: activates feature entitlements
- Staff Access: creates controlled internal operations
- Agent and Franchise: supports referral-led business growth

---

### Matchmaker Page

#### Business Purpose
This page supports internal relationship managers or matchmakers who assist members manually.

#### Business Value
- Better service for premium members
- Higher conversion for serious families
- Human follow-up and coordination

---

### Agent Page

#### Business Purpose
The agent page supports partner acquisition, referrals, commission tracking, and payout workflows.

#### Business Value
- Growth through community referrals
- Scalable local lead generation
- Operational control of commission payouts

---

## 4. Matchmaking Logic

### Simple Business Explanation
The system gives boys suggestions of girls, and girls suggestions of boys, based on profile facts, trust signals, and business rules.

### Rule 1: Opposite Gender Only
- Male profiles should see female suggestions
- Female profiles should see male suggestions
- Same-gender profiles should not appear in normal matchmaking

### Rule 2: Invalid Profiles Are Removed First
The system removes:
- Hidden profiles
- Suspended profiles
- Blocked profiles
- Inactive or deactivated profiles
- Same person’s own profile
- Same-gotra profiles when hard blocking is enabled

### Rule 3: Age Compatibility Matters
The current live scoring favors a directional age-gap pattern where the groom is older.

#### Example
- Boy age: 30
- Girl age: 26
- Difference: groom older by 4 years
- This ranks high because the gap falls into the preferred range

#### Another Example
- Girl age: 27
- Boy age: 30
- Difference: groom older by 3 years
- This also ranks high

### Rule 4: Education Matters, But Is Usually Soft
The system prefers similar education groups. Exact degrees are not always required. Similar educational seriousness is usually enough to improve ranking.

### Rule 5: Income and Business Income Influence Ranking
Income acts as a compatibility input rather than a strict rejection rule in most practical cases.

Examples:
- Similar salary band: higher score
- Similar business income band: higher score
- Missing income: lower ranking, but not always complete rejection

### Rule 6: Location Priority
The ranking is stronger when location is closer.

Typical order:
- Same city
- Same district or same state
- Same country
- Different country

### Rule 7: Community, Gotra, and Kundali
- Same or close community increases ranking
- Same gotra may be fully blocked if hard rule is on
- Kundali affects ranking only when enabled and entitled

### Rule 8: Trust and Profile Quality Improve Results
Profiles with better photos, complete details, verification, and recent activity usually rank higher.

### Rule 9: Paid Boost Does Not Replace Compatibility
Boosted or paid profiles may receive extra visibility, but they should still pass suitability checks. Revenue should support visibility, not destroy trust.

### User Preference vs Admin Rule Priority
Current practical order:
1. System validity rules
2. Admin business rules
3. Core profile-fact matching
4. User preferences and soft ranking layers
5. Boost and paid visibility bonus

Business interpretation:
- Admin rules shape the platform’s allowed boundaries
- User preferences guide ranking and filtering
- The system should not violate core safety and validity rules just to satisfy a weak preference or a paid boost

---

## 5. Admin Control Guide

### A. Reviewing New Registrations
1. Check new signups daily
2. Verify profile quality
3. Ensure basic required data is present
4. Watch for duplicate or suspicious accounts

### B. Managing Verification Queue
1. Review Aadhaar submissions
2. Review income proofs if enabled
3. Approve only genuine documents
4. Reject incomplete or unclear submissions

### C. Managing Pricing and Plans
1. Review active plan structure
2. Confirm trial logic is still aligned with business goals
3. Ensure live pricing matches advertised pricing
4. Test any plan changes before public promotion

### D. Managing Add-Ons
Use add-ons to increase monetization without harming trust.

Examples:
- Profile boost
- Advanced compatibility tools
- Extra unlocks
- Premium visibility

### E. Managing Dashboard Builder
Use this to control what members can see or access in the dashboard.

Business advice:
- Do not expose too many unfinished modules
- Enable only features that are operationally ready

### F. Managing Profile Form Builder
Use this to decide:
- which fields are shown
- which are required
- which are optional

Business advice:
- Keep important trust and matching fields visible
- Avoid making critical quality fields optional

### G. Managing Community and Gotra
Keep values standardized and clean.

Business advice:
- Avoid multiple spellings of the same community
- Avoid broken gotra naming
- Clean data improves match quality dramatically

### H. Managing User Access Control
Use this to give or restrict:
- premium access
- add-ons
- special visibility
- operational flags

### I. Managing Agents and Payouts
1. Review agent applications
2. Approve serious partners only
3. Track referred members
4. Review payout requests
5. Approve payouts carefully and maintain records

### J. Managing Staff Access
Only authorized staff should get access to sensitive operations.

Business advice:
- Limit permissions
- Review access regularly
- Remove inactive staff access

### Admin Do's
- Review registrations daily
- Review verification queue quickly
- Standardize community and gotra data
- Keep plan and feature settings synchronized with real business policy
- Spot-check live match quality regularly

### Admin Don'ts
- Do not approve low-quality profiles only to increase count
- Do not make too many mandatory rules too strict on a small database
- Do not enable hard same-gotra block unless gotra data quality is clean
- Do not announce pricing changes before testing checkout
- Do not assume every visual save button equals safe live persistence without verification

### Common Admin Mistakes
- Over-filtering and causing "no matches"
- Forgetting to review verification backlog
- Leaving incomplete profile fields too open
- Using boost too aggressively and reducing trust
- Changing settings without testing in a fresh session

---

## 6. Risk and Edge Cases

### Missing User Data
If important fields are missing:
- profile may still exist
- ranking becomes weaker
- trust drops
- user satisfaction drops

### Incomplete Profiles
If users fill only minimal details:
- they may get poor suggestions
- their profile may appear weaker to others

### Wrong Admin Inputs
Examples:
- broken auth settings can disrupt login
- broken payment settings can disrupt checkout
- extreme form settings can reduce profile completion

### Too-Strict Filters
With a limited database, too many hard filters can create an empty result set. This makes the platform look weak even when there are profiles available.

### Same-Gotra Hard Block Risk
If gotra data quality is poor, hard blocking can hide many valid matches incorrectly.

### Verification Backlog
If verification is ignored:
- trust drops
- serious families lose confidence
- match quality perception suffers

### Over-Monetization Risk
If boosted profiles are shown above clearly better profiles too often:
- users lose trust
- paid visibility starts looking fake
- long-term revenue can drop

### Auth and Payment Risk
If OTP, email auth, or checkout settings are misconfigured, the acquisition funnel and revenue funnel both fail.

---

## 7. Daily Operations SOP

### Morning Checklist
- Review new registrations
- Review verification queue
- Review payment status
- Review trial expiry list
- Review support issues
- Review agent applications or payout requests

### Midday Review
- Spot-check 2 to 3 live member dashboards
- Spot-check match quality
- Review incomplete premium profiles
- Follow up on pending verification cases

### End-of-Day Review
- Review revenue from plans and add-ons
- Review staff actions
- Review suspicious users or support escalations
- Review whether major admin changes behaved correctly

### Weekly Owner Review
- Best-performing cities
- Trial-to-paid conversion
- Verification turnaround
- Match quality complaints
- Premium upsell performance
- Agent contribution
- Support pain points

---

## 8. Final Recommendations

### Improve Match Quality
- Keep hard filters minimal
- Use weighted scoring for softer criteria
- Strengthen saved partner preference enforcement gradually

### Improve Data Quality
- Encourage complete profiles
- Standardize community, gotra, city, and income data
- Use verification as a trust engine

### Improve Business Trust
- Do not allow revenue boost to overpower relevance
- Maintain visible authenticity in suggestions

### Improve Admin Operations
- Keep a disciplined daily routine
- Test major setting changes before business announcements
- Review live user experience regularly

### Launch Advice
Before calling the platform fully launch-ready, verify:
- signup and login
- OTP and password reset
- payment flow
- profile save behavior
- match quality sanity
- verification process
- staff and agent workflows

---

## 9. Admin Training Checklist

### Access and Readiness
- Admin can log in successfully
- Staff roles are assigned correctly
- Matchmaker access is verified
- Agent workflow access is verified

### Registration and Onboarding
- Signup tested
- Login tested
- OTP tested
- Password reset tested
- Trial start tested
- Paid checkout tested

### Profile and Verification
- Admin knows how to review profiles
- Admin knows how to handle verification queue
- Admin knows how to spot low-quality data

### Matchmaking
- Admin understands opposite-gender rule
- Admin understands age-gap logic
- Admin understands community and gotra impact
- Admin understands boost and premium visibility behavior

### Business Controls
- Admin understands pricing and plans
- Admin understands add-ons
- Admin understands dashboard builder
- Admin understands profile form builder
- Admin understands user access control

### Operations
- Admin knows morning checklist
- Admin knows end-of-day review
- Admin knows weekly owner review

---

## 10. Visual Flow Diagrams

### User Journey
Landing Page -> Auth Page -> Registration/Login -> Trial or Paid Start -> Dashboard -> Profile Completion -> Match Suggestions -> Shortlist / Interest / Message / Upgrade

### Matchmaking Logic
Active Opposite-Gender Pool -> Remove Invalid Profiles -> Apply Community/Gotra/Validity Rules -> Score by Age, Location, Education, Income, Completeness, Activity, Trust, Kundali -> Apply Controlled Boost Bonus -> Show Ranked Matches

### Admin Control Flow
Admin Panel -> Pricing / Features / Form Rules / Verification / Access Control -> Live System Behavior -> Member Experience -> Revenue and Trust Outcome

### Daily Operations Loop
Morning Review -> Midday Spot Checks -> End-of-Day Audit -> Weekly Owner Review -> Continuous Improvement

### Verification Flow
User Uploads Proof -> Admin Reviews -> Approve or Reject -> Trust Signal Updated -> Better Visibility and Conversion

### Agent Flow
Agent Application -> Admin Review -> Agent Approval -> Member Referrals -> Commission Tracking -> Payout Review

---

## 11. Export Notes

This document is designed to be pasted into Canva Docs or a similar design platform and converted into:
- PDF SOP
- Admin training handbook
- Presentation deck
- Visual process document

Recommended Canva structure:
- Cover page
- System overview
- User journey
- Page-wise SOP
- Matchmaking logic
- Admin controls
- Risks
- Daily operations
- Checklist
- Flow diagrams
- Final recommendations
