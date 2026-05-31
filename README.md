# Subspace.money — Product Teardown

**Submitted for:** Product Intern Assignment  
**Company chosen:** Subspace.money  
**Date:** 31st May 2026  
**Submitted by:** Prateek Kumar

---

## Why Subspace?

I chose Subspace over Vocallabs because Subspace is:
- Bootstrapped & profitable (₹36.5 Cr ARR with zero funding)
- A two-sided marketplace with a trust problem — the most interesting product challenge
- Something I could actually use as a real customer and find real issues

---

## My Background

I come from a **cybersecurity background**. I approached this teardown the way I'd approach a penetration test — looking for broken trust boundaries, failure modes, and edge cases. I believe this lens helped me find problems most applicants would miss.

---

## How I Used the Product

1. Downloaded the app from Google Play Store
2. Signed up via phone number
3. Browsed subscription plans (Netflix, Prime Video, Hotstar, Spotify)
4. Explored public groups and admin profiles
5. Checked wallet flow and withdrawal process
6. Read user reviews on Play Store to validate my observations
7. Analyzed competitor (Fleek) for comparison

---

## The 5 Sharpest Feedbacks

---

### Feedback #1: The Admin Trust Gap
**Category:** GTM & ICPs | **Priority:** 🔴 Critical

**(a) Observed:**  
Any user can create a public group, collect money from strangers, and act as admin with zero verification. Multiple Play Store reviews report admins taking money and disappearing or removing members after payment.

**(b) Problem:**  
Subspace is built on trust between strangers, but provides no trust infrastructure. Users who get cheated leave 1-star reviews and never return. The whole marketplace model collapses if trust breaks.

**(c) Ship Instead:**  
Introduce a **"Verified Admin" tier** with a ₹99 refundable deposit held in escrow:
- Deposit acts as a performance bond — lost if admin cheats
- Verified admins get a blue checkmark badge
- Verified admins appear first in search results
- New users can only create private groups (with friends) until they complete 5 successful transactions

**Why this works:** It's not punitive — it's economic signaling. Only serious admins will pay ₹99. It filters fraudsters and builds user trust. This is common in marketplaces (Airbnb, Uber) but absent in Subspace.

---

### Feedback #2: The Wallet Trap
**Category:** Features / Services | **Priority:** 🔴 Critical

**(a) Observed:**  
Subspace requires users to add money to a wallet. Withdrawing money costs 1% fee + ₹50 flat charge. One user reports: *"When you try to withdraw ₹50, they only give you ₹43."* Some users say the app charges for each click.

**(b) Problem:**  
This creates negative trust. The company's promise is "save money" — but then charges users to access their own money. Users feel trapped, not valued.

**(c) Ship Instead:**  
- First withdrawal per month: **FREE**
- Subsequent withdrawals: flat ₹10 (not percentage)
- No "per click" charges — only charge on confirmed purchases
- Show a tooltip on every screen: *"This is your available balance. Free withdrawal once/month."*

**Why this works:** Transparency builds trust. Trust builds retention. Retention builds revenue from subscriptions — not from wallet friction.

---

### Feedback #3: No Automated Dispute Resolution
**Category:** UX | **Priority:** 🟠 High

**(a) Observed:**  
When a user faces an issue with an admin (wrong credentials, removed from group, no access), the only recourse is emailing `mailus@subspace.money`. Reviews say support is slow, refunds require Aadhaar/KYC, and the listed phone number doesn't work.

**(b) Problem:**  
Subspace outsourced customer support to untrained admins. When admins fail, users hit a slow manual support process. For a ₹90 transaction, the support cost exceeds the transaction value — so Subspace has no incentive to resolve small disputes well.

**(c) Ship Instead:**  
Build a **3-tier automated dispute system** (copying Swiggy/Zomato's model):
- **Tier 1 (Auto, 60 seconds):** Did admin share credentials? If not → auto-refund from deposit
- **Tier 2 (24 hours):** If Tier 1 fails → admin gets 24 hours to respond or auto-refund
- **Tier 3 (Human):** Only if both parties disagree — handles <5% of cases

**Why this works:** Most disputes are simple (admin never shared credentials). Automated resolution costs nothing and keeps users happy.

---

### Feedback #4: The Explore Tab is a Ghost Town
**Category:** Competitor Analysis | **Priority:** 🟠 High

**(a) Observed:**  
When I opened the Explore/Discover tab, I saw a flat grid of subscription cards. There is no way to filter by price or category, sort by admin rating or popularity, or search by subscription name. One Play Store review confirms: *"If you have a subscription to share, it will not be shown in the explore page. Only certain people's names are shown."*

Meanwhile, **Fleek** (Subspace's main competitor) has a much cleaner discovery flow with category-based browsing, price sorting, and plan recommendations. Subspace is falling behind here.

**(b) Problem:**  
Subspace is a marketplace, but the Explore tab works like a static catalog. A marketplace needs dynamic discovery — users should be able to find the best deal, the most trusted admin, or the fastest-filling group. Without this:
- Good admins' groups sit empty (supply unfilled)
- Users can't find what they want and leave (demand unserved)
- Cross-sell opportunities are lost (someone buying Netflix might also buy Spotify if shown)
- **Fleek pulls ahead** on user experience, making Subspace look outdated

**(c) Ship Instead:**  
Redesign the Explore tab with these additions:

Search bar with autocomplete
Category chips: [All] [OTT] [Music] [Productivity] [Gaming] [Student]

3 dynamic rows:
- 🔥 TRENDING NOW — Groups filling fastest in last 24 hours
- ⭐ TOP RATED — Highest admin ratings, best prices
- 🆕 FRESH GROUPS — Newly created

Each group card shows: Service logo | ₹163/mo | ⭐ 4.8 rating | ✅ spots left | [Join Now] button

Add a waitlist feature at the bottom: "Notify me when Spotify Premium has an available group"

**Why this works:** This doesn't require building new features — it's just re-sorting existing data. Low effort, high impact. The trending row creates FOMO, the top rated row rewards good admins, and the waitlist captures demand signals so Subspace knows what to expand. Most importantly, it **matches and beats Fleek** on discovery.

---

### Feedback #5: The Rentals Feature is Half-Built
**Category:** Potential Collaborations | **Priority:** 🟡 Medium

**(a) Observed:**  
Subspace's Play Store listing promotes: *"Rent gadgets, accessories and essentials with 10-minute delivery (select cities)."* The website forces a location selector on load — suggesting rentals are the primary focus. But:
- The rental catalog is thin (few products, select cities only)
- No clear partnership branding or logos from brands
- No blog posts or landing pages explaining the rental service
- The location-first homepage confuses users who came for subscriptions

**(b) Problem:**  
Subspace is trying to be two products at once:
1. Subscription marketplace (proven cash cow — ₹36.5 Cr ARR)
2. Instant rental platform (experimental — unproven)

The rental feature could be a huge differentiator — Fleek (competitor) doesn't do rentals at all. But right now it's underdeveloped, confusingly positioned, and lacks partnerships. The homepage confuses subscription users by asking for location before showing any plans.

**(c) Ship Instead:**  
**Pivot rentals into a "Student Essentials" partnership program** — don't build inventory, partner for it.

- **Target user:** College students (they already have student email deals)
- **Partner with:** Local electronics stores in Bangalore, brands like boAt/Noise/Realme
- **Product catalog:** Laptops (semester rental), earphones (monthly), power banks (daily), tablets (semester)
- **Student verification:** College email = zero-deposit rentals
- **Return tracking:** Automated reminders before due date

Create a separate microsite: rent.subspace.money with clear categories, partner logos, and rental terms.

**Fix the homepage:**
- Remove location selector from homepage
- Default homepage shows subscriptions first (the proven revenue driver)
- Add a "Rent" tab in navigation — only asks for location when clicked

**Why this works:** Subspace doesn't hold inventory — it connects renters with local stores (asset-light model). Student rentals have high repeat rates (every semester) = recurring revenue. Partnerships create a moat. Differentiates from Fleek which has no rentals.

---

## Priority Summary

**Ship order:** #2 → #4 → #1 → #3 → #5

| Order | Feedback | Category | Priority | Why This Order |
|---|---|---|---|---|
| 1st | #2 Wallet fix | Features / Services | 🔴 Critical | High impact, low effort — ship today |
| 2nd | #4 Explore redesign | Competitor Analysis | 🟠 High | High impact, low effort — ship this week |
| 3rd | #1 Admin deposit | GTM & ICPs | 🔴 Critical | Critical but needs some development |
| 4th | #3 Dispute system | UX | 🟠 High | Important but needs more engineering |
| 5th | #5 Rental pivot | Potential Collaborations | 🟡 Medium | Strategic — needs partnerships, takes time |

---

## Frameworks Used

| Framework | Where I Applied It |
|---|---|
| **SWOT** | Mapped Subspace's strengths (bootstrapped, India-first, profitable) and weaknesses (admin fraud, wallet friction, poor support) |
| **7Ps** | Analyzed Price (wallet fees), People (admin trust gap), Process (dispute resolution), Physical Evidence (no trust badges) |
| **Porter's Five Forces** | Identified high buyer power (users can leave to Fleek or WhatsApp easily) → trust infrastructure is the moat that keeps them |
| **Jobs-to-be-Done** | Users hire Subspace to save money WITHOUT hassle — wallet fees and admin fraud add hassle, so the job isn't done well |
| **Principal-Agent Theory** | Admin (agent) collects money from user (principal) with no consequence for cheating → ₹99 deposit aligns incentives |
| **Competitive Benchmarking** | Compared Subspace's Explore tab with Fleek's discovery flow to find where Subspace is falling behind |

---

## Why This Teardown is Different

| Generic Feedback (Most Applicants) | My Feedback (Specific & Actionable) |
|---|---|
| "Improve trust" | ✅ Add ₹99 admin deposit + blue badge (GTM & ICPs) |
| "Fix wallet" | ✅ First withdrawal free, flat ₹10 after (Features / Services) |
| "Better support" | ✅ 3-tier automated dispute system (UX) |
| "Better discovery" | ✅ Trending rows + filters to beat Fleek (Competitor Analysis) |
| "Add rentals" | ✅ Student Essentials partnership program (Potential Collaborations) |

Every feedback has:
- ✅ Observable evidence (I saw it in the app or found it in Play Store reviews)
- ✅ A real problem (why it matters for users or the business)
- ✅ A specific solution (what to build and how it would work)
- ✅ A unique category covering all 5 pillars from the assignment
- ✅ A framework backing it (SWOT, 7Ps, Porter's Five Forces, JTBD, Principal-Agent, Competitive Benchmarking)

---

## Category Coverage Map

| Pillar (from assignment) | Feedback # | Feedback Name |
|---|---|---|
| GTM & ICPs | #1 | Admin Trust Gap |
| Competitor Analysis | #4 | Explore Tab vs Fleek |
| Features / Services | #2 | Wallet Trap |
| UX | #3 | No Automated Dispute Resolution |
| Potential Collaborations | #5 | Rentals Feature Half-Built |

---

## Connect With Me

LinkedIn: https://www.linkedin.com/in/prateek-kumar02  
Email: prateek.cse23@bgsbu.ac.in
