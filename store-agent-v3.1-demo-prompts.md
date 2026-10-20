# Zoho Store AI Agent v3.1 — Self-Service Demo Prompts (verified)

All 75 prompts were run through the prototype's own text router (the 15 added in Phase 7 were also run end to end). Each line shows the role to select and what you should see. When a prompt names the product (e.g. "Acme's Zoho CRM"), the agent goes straight to that license. For "Add / Remove N users" and "Upgrade … to <plan>", it opens the update form with the values already filled in. Only prompts without a product name (e.g. "Extend the license term for Globex") show a list to pick from.

**How to use:** open `zoho-store-agent-v3.1-spec-aligned.html`, select the role shown, type the prompt (or click the matching action button). Roles default to **Sales / AM**. Click **Reset demo** before a fresh run.

**Order matters for 3 prompts:** #38 needs #48 first, #54 needs #49 first, #56 needs the pre-seeded approval (present after Reset demo).

## Phase 1 — Customer Intelligence & Discovery

1. Show Customer 360 for Acme.
   *Sales · Acme profile, both licenses, "Needs attention" flag, action buttons.*
2. Show Customer 360 for Globex. **(changed)**
   *Sales · Globex licenses with price and renewal date, failed payment and open invoice flagged.*
3. Show subscription details for Globex's Zoho Desk license.
   *Sales · Opens Zoho Desk directly → plan, list price, 8% discount, net recurring, payment method.*
4. Show the complete transaction history for Acme.
   *Sales · Latest activity, then "Open complete history" for the full timeline with filters.*
5. Show allowed actions for Globex's Zoho Desk license.
   *Sales · Opens Zoho Desk directly → every action marked Allowed / No with the reason.*
6. Show allowed actions for Acme's Zoho One license.
   *Sales · Opens Zoho One directly → renew, upgrade, extend etc. blocked by the overdue invoice.*
7. Show allowed actions for Initech's Zoho Projects license.
   *Sales · Goes straight to the list (single license). Upgrade and modify blocked because it is paused.*
8. Show all customers under Northstar Solutions.
   *Any role · Partner portfolio with ARR and next renewal per customer.*
9. Show customers that need attention.
   *Any role · Portfolio insights: at-risk signals and suggested next actions.*

## Phase 2 — Simple Subscription Operations

10. Change the billing address for Acme.
    *Sales · Prefilled form. Change country to India or Germany to see the order-form link path.*
11. Add a new invoice notification recipient for Acme.
    *Sales · Set type to Invoice, enter name and email. Duplicates and bad emails are rejected.*
12. Change Evergreen's billing responsibility to the partner. **(changed)**
    *Sales · Set Bill to = Partner. Customer address fields hide.*
13. Pause Globex's Zoho Desk subscription.
    *Sales · Opens Zoho Desk directly → 7-day pause with auto-resume.*
14. Resume Initech's paused subscription.
    *Sales · Existing state shows Paused → Resume.*
15. Renew Globex's Zoho Desk subscription for two years.
    *Sales · Opens Zoho Desk directly; set term to 2 years. Creates a Draft renewal cart. The license is **not** renewed yet.*
16. Extend the license term for Globex.
    *Sales · Pick Zoho Desk, months or days plus a reason. Over 3 months needs approval.*
17. Show all trials for Globex.
    *Any role · Zoho CRM trial with Extend, Convert to purchase, Cancel trial.*
18. Extend Globex's Zoho CRM trial.
    *Any role · Same list → click Extend → new expiry date.*
19. Start a new trial for Acme.
    *Any role · "No trials" → click Start a new trial.*
20. Convert Globex's trial to a paid subscription.
    *Any role · Click Convert to purchase → in the form pick Zoho CRM as the product.*
21. Change the payment method for Globex.
    *Partner Store only · Pick Zoho Books → last 4 digits and expiry. Pays the outstanding $2,160 and clears the failed payment.*

## Phase 3 — Commercial & Licensing Operations

22. Purchase 10 Zoho Desk Professional licenses for Acme.
    *Sales · Form is prefilled with exactly this. Choose a route and confirm.*
23. Create an estimate for a new Zoho Projects subscription for Globex.
    *Sales · Purchase form. Pick Zoho Projects and keep the route "Create estimate".*
24. Purchase licenses using a purchase order for Globex.
    *Sales · Purchase form. Set route to "Proceed with purchase order": PO number, PO file, legal ack. Pick a product Globex doesn't own.*
25. Create a $0 evaluation license for Acme.
    *Sales · Purchase form. Set route to "Evaluation license", sales note required. Billed $0.*
26. Modify the Zoho One subscription for Evergreen Timber & Ply.
    *Sales · Existing data, usage gap suggestion, add-ons, sales note, apply now or at renewal.*
27. Upgrade Globex's Zoho Desk subscription to Enterprise.
    *Sales · Opens the update form with Plan already set to Enterprise (nothing to pick). Optional "Renew now". Review and click Update.*
28. Downgrade Globex's Zoho Desk subscription.
    *Sales · Opens the update form for Zoho Desk; change Plan to Standard. Shows a credit (negative amount).*
29. Show all estimates for Umbrella.
    *Any role · EST-4421 Awaiting E-Sign, EST-4425 with address-not-verified banner.*
30. Generate a quote for an Acme estimate.
    *Sales · Click Generate quote on EST-4402 (Draft). It becomes Pending Customer Approval.*
31. Attach a purchase order to Acme's accepted estimate and enable it. **(changed)**
    *Sales · Pick EST-4388. File `po.pdf`, PO total 2400 (any other total shows the mismatch error), legal ack.*
32. Show why Umbrella's estimate cannot be enabled.
    *Any role · EST-4425: address not yet verified, Enable disabled. EST-4421 waits for e-sign.*
33. Apply a 20% discount to Globex's Zoho Desk subscription.
    *Sales · Opens Zoho Desk directly; set 20. Above 15%, so it goes to approval and nothing changes yet.*
34. Apply a 10% discount to Initech. **(changed)**
    *Sales · Lowers 20% → 10%. Under the limit, so it applies directly.*
35. Generate a payment link for Globex's open invoice. **(changed)**
    *Sales · INV-21102, payment link generated.*
36. Create a one-time payment for Acme.
    *Sales · Online charge request or offline invoice. Amount is typed, sales note required.*
37. Extend Acme's payment due date by 15 days.
    *Sales · INV-20931, comment required, fixed +15 days.*
38. Revert the cancellation for Acme's Zoho CRM. **(changed, run #48 first)**
    *Admin · Opens Zoho CRM (Cancelling) directly → confirm address and recipients → Active, $0 due.*
39. Reassign an estimate to another customer.
    *Sales · Pick an Acme estimate, enter e.g. `admin@umbrella.example`.*

## Phase 4 — Proactive Intelligence & Portfolio Management

40. Show renewal opportunities for the next 30 days.
    *Any role · 4 licenses; overdue ones show "Resolve first".*
41. Show all failed payments.
    *Any role · Globex PAY-9921, with Send payment link.*
42. Show customers with overdue invoices.
    *Any role · Acme INV-20931, with Settle and Extend date.*
43. Show portfolio insights.
    *Any role · ARR, renewing ≤30d, at-risk, discount given.*
44. Show ARR and discount exposure.
    *Any role · Same insights view (ARR bars and discount given / yr).*
45. Show all pending approvals.
    *Sales sees "Your requests"; Admin sees the queue with Approve / Reject.*

## Phase 5 — Cancellation & Destructive Operations

46. Cancel Acme's Zoho One subscription and move to standalone products.
    *Sales · Opens Zoho One directly → path "Move to standalone", keep CRM, acknowledge. Sends for approval; Zoho One stays active.*
47. Cancel Initech's Zoho Projects subscription immediately. **(changed)**
    *Admin · Uncheck "Cancel at end of billing cycle", comment, type the license ID to confirm.*
48. Cancel Acme's Zoho CRM subscription. **(changed)**
    *Admin · "Cancel now" is not offered, so it is scheduled to 2027-02-14. Status becomes Cancelling.*
49. Cancel Acme's Zoho One subscription and show the invoice impact of a backdated cancellation. **(changed)**
    *Admin · Opens Zoho One directly → path "Continue to cancel" → set a past cancellation date, uncheck schedule. The raise-invoice amount recalculates.*
50. Cancel Globex's trial. **(changed)**
    *Any role · Click Cancel trial → confirm "customer loses access immediately".*
51. Delete an estimate for Acme.
    *Sales · Pick an estimate. A Draft deletes directly; a sent one goes to approval.*
52. Remove a recurring discount from Initech.
    *Sales · Typed confirmation of the license ID, then Store Admin approval.*
53. Remove an invoice notification recipient from Acme.
    *Sales · Confirm dialog. The last invoice recipient can't be removed.*
54. Reactivate Acme's Zoho One subscription. **(changed, run #49 first)**
    *Admin · Opens Zoho One (Cancelled) directly → creates a Draft reactivation estimate with a past-due row. The license stays cancelled until enabled.*

## Phase 6 — Approvals, Restrictions & Audit

55. Show all pending approval requests.
    *Admin · APR-1001 Globex discount 8% → 25%.*
56. Approve the pending discount request for Globex.
    *Admin · Click Approve → confirm. The 25% discount runs and is logged.*
57. Show the audit trail for Globex. **(changed)**
    *Admin · Latest activity → "Open complete history" → filter **Approval**.*
58. Renew Acme's Zoho One license. **(changed)**
    *Sales · Opens Zoho One directly → blocked: unpaid invoice INV-20931, with a Settle button.*
59. Upgrade Initech's Zoho Projects subscription. **(changed)**
    *Sales · Blocked: license is paused, with a Resume license button.*
60. Show the timeline of changes for Globex. **(changed)**
    *Sales · Latest activity → "Open complete history" → filter Change or Subscription.*


## Phase 7 — Role Boundaries, Commercial Rules & Complete Chains

61. Show Customer 360 for Umbrella.
    *Partner Store · Blocked: Umbrella is a direct customer, not in the partner's portfolio.*
62. Apply a 20% discount to Globex's Zoho Desk subscription.
    *Partner Store · "Discounts isn't available for Partner Store."*
63. Cancel Globex's Zoho Books subscription.
    *Partner Store · Not available; cancellations go through PAM or Sales.*
64. Show renewal opportunities for the next 30 days.
    *PAM · Lists only Northstar's customers (no Umbrella).*
65. Purchase licenses using a purchase order for Umbrella.
    *Sales · Set product Zoho Books, plan Premium, 20 users, route PO, PO number, PO file `po.pdf`, legal ack. $14,400 is over $10,000, so it goes to approval.*
66. Purchase Zoho Books Premium for Umbrella with annual commitment.
    *Sales · Set pay period "Annual commitment" and tick the acknowledgement. Due now is annual ÷ 12; route Estimate, tick the customer-approval box.*
67. Purchase Zoho Projects for Acme with annual commitment.
    *Sales · Blocked: annual commitment isn't offered for Canada (the spec example lists USD/GBP · USA/UK — rule to confirm).*
68. Change Acme's billing country to Germany.
    *Sales · Button becomes "Submit for verification" and an order-form link is generated. The address is not changed until the customer verifies.*
69. Renew Globex's Zoho Desk subscription.
    *Sales · Opens Zoho Desk directly; keep 1 year → Draft renewal cart (expiry still 2026-11-08). Then "Show estimates for Globex" → Generate quote → Demo: customer accepts → Renew license. Expiry becomes 2027-11-08 only now.*
70. Send a payment link for Globex's failed payment.
    *Sales · Failed-payments view → Send payment link → confirm. Status becomes "Link sent".*
71. Update the subscription for Evergreen to match active usage.
    *Sales · Shows the agent's suggestion (4 active vs 3 provisioned) with "Update only this".*
72. What can I do for Initech?
    *Sales · Casual phrasing → allowed / blocked actions with reasons.*
73. Add 15 users to Acme's Zoho CRM.
    *Sales · Opens the update form for Acme's Zoho CRM with Users already prefilled 45 → 60 (nothing to pick or type). Shows net recurring and the amount due now. Click Update.*
74. Reject the pending discount request for Globex.
    *Admin · Click Reject, enter a reason. The discount stays at 8%.*
75. Move Acme's Zoho One to the free plan.
    *Sales · Opens Zoho One directly → path "Move to free plan", acknowledge, comment, type the license ID to confirm. Goes to approval.*

---

**What to evaluate during the demo**

- Does the agent identify the correct customer and subscription?
- Does it display existing values before proposing changes?
- Does it clearly distinguish allowed and restricted actions?
- Does it prefill existing information and request only necessary inputs?
- Does it explain pricing, billing, and subscription impact?
- Does it request confirmation before executing changes?
- Does it route restricted operations for approval?
- Does it display the final outcome and updated subscription details?
- Does it maintain a complete customer transaction history?

**Note:** This is a mock-data prototype. Amounts are placeholders for the pricing tool. Some prompts demonstrate blocked operations, approval requirements or guided workflows rather than successful transactions. Text recognition is limited; use the action buttons if a prompt is not recognized.
