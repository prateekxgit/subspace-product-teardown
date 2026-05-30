# Subspace.money — Product Teardown

**Submitted for:** Product Intern Assignment  
**Company chosen:** Subspace.money  
**Date:** 30th May 2026  
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

### Feedback #1: The Admin Trust Gap
**Category:** GTM & ICP | **Priority:** 🔴 Critical

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
