---
name: export-profit-quote
description: Dynamic B2B export quotation, hidden-cost audit, and anti-discounting negotiation assistant for Chinese exporters and SOHO traders. Use whenever the user asks to calculate export quotes (EXW, FOB, CIF, DDP), check exchange rate buffers or hidden port/bank fees, build tiered MOQ pricing, check destination tariffs or shipping surcharges, or draft bilingual B2B quotation and counter-bargaining emails.
allowed-tools: google google_finance
---

# export-profit-quote

A practical B2B export pricing and negotiation skill designed for Chinese export salespeople and SOHO traders. It audits hidden costs, fetches live FX and trade policy context, builds tiered MOQ pricing matrices, and drafts ready-to-send buyer emails with counter-bargaining scripts.

## When to Use

* User asks to calculate or double-check an export quotation under EXW, FOB, CIF, or DDP.
* User wants to know how much margin is left after tax rebates, bank fees, port charges, and FX fluctuations.
* User needs a tiered pricing strategy (trial order vs. full container vs. volume contract) to avoid pure price comparison.
* User asks to write an English quotation email or needs help responding to a buyer who says the price is too high.

## Steps

### 1. Intake & Triage

Check what inputs the user provided:

* Product cost (RMB, clarify whether VAT-inclusive or ex-tax) and export tax rebate rate (if applicable).
* Packing specs (units per carton, carton dimensions/CBM, gross weight) for container or LCL allocation.
* Target Incoterm (EXW, FOB, CIF, DDP), loading port, destination country/port, and target currency (USD, EUR, AUD, etc.).
* Desired profit rate and MOQ tiers. Clarify explicitly whether the target is **Net Margin on Sales** (`Price = Cost / (1 - Margin%)`) or **Cost-Plus Markup** (`Price = Cost * (1 + Markup%)`); default to Net Margin unless the user specifies Markup, and state the chosen formula clearly.

If core inputs like unit cost or destination/Incoterm are missing, ask 2 to 4 concise questions before calculating. If only secondary details (such as exact port THC or insurance rate) are missing, state standard industry assumptions clearly and proceed.

### 2. Live FX & Policy Verification

* Fetch the current spot exchange rate using finance or web search tools. For Chinese exporters receiving foreign currency, apply a conservative FX safety buffer by **lowering** the quoting FX rate (typically 1.5% to 3.0% below the bank telegraphic buying rate, e.g. `Spot Buying Rate * 0.98`) so quote validity does not erode RMB margin. Show both the spot rate and the buffered quoting rate.
* Check container capacity conservatively: use realistic usable volume (e.g., 25.5 to 26.5 CBM for a 20'GP floor-loaded, 54 to 58 CBM for a 40'GP, 65 to 68 CBM for a 40'HQ) rather than theoretical maximums, and note whether volume or weight caps out first.
* When quoting CIF or DDP, or when shipping to markets with specific biosecurity/tariff rules (e.g., Australia ISPM 15 / BMSB season, US/EU tariff or de minimis shifts), run a quick web search so the pricing and loading advice reflect real market conditions.

### 3. Hidden-Cost Audit (Margin Protection)

Before outputting any quote, audit and itemize potential margin leaks in a clear Chinese internal breakdown:

* Tax rebate formula (when VAT invoice is available): `Net Cost = (VAT-Inclusive Cost / (1 + VAT Rate)) * (1 + VAT Rate - Rebate Rate)`. Note the working-capital tie-up for the VAT refund period.
* Domestic export expenses: inland trucking or feeder barge (especially for secondary/inland ports like Nantong or Foshan routing via Shanghai/Shenzhen - never silently switch the user's FOB port without flagging the hub-port option and cost difference), port THC/ORC, customs brokerage, inspection/fumigation, and document fees.
* Financial friction: bank wire/intermediary fees, FX conversion spread, and capital tie-up cost if offering O/A or long payment terms.
* CIF/DDP extras: marine insurance (typically 110% of CIF value), destination port handling, customs clearance, and import duty/VAT exposure.

Flag high-risk blind spots and list exact items to verify with the freight forwarder before sending the quote as a binding price.

### 4. Tiered Pricing Matrix

Avoid giving a single flat unit price that invites pure price-shopping. Present a comparison table covering the requested tiers (typically Trial/LCL, Standard FCL 20'GP/40'HQ, and optionally Volume/Annual Commitment):

* Show quantity (cartons and pcs), CBM and gross weight, unit quote price, **per-carton price**, total order value, estimated net profit (RMB at both buffered and spot FX rates), and net margin (%).
* If the unit price gap between LCL and FCL is small (because factory cost is fixed and FCL only dilutes local export handling), explain this explicitly in both the internal audit and the buyer email so the buyer understands the pricing logic.

### 5. Buyer-Facing Email & Anti-Discounting Playbook

Output two ready-to-use communication assets:

1. **Ready-to-Send English Quotation Email**: Lead with value anchors (packing specs, loading efficiency, biosecurity/compliance readiness), present the tiered options cleanly (including per-carton and total values), include a firm quote validity window (e.g., 7 to 14 days tied to FX/factory stability) and payment terms, and mark `[Product Name]` / `[HS Code]` placeholders clearly for the user to fill in before sending.
2. **Counter-Bargaining Playbook (Bilingual EN + CN)**: Provide 6 scenario-based tactical replies covering common buyer pushbacks:

   * **Too expensive**: Anchor on spec consistency, QC, export-ready packing, and FX stability (never reveal RMB factory cost or VAT rebate).
   * **Temu / 1688 comparison**: Contrast single-piece retail/stock platforms against custom B2B export packing, QC, and compliance.
   * **Competitor quoted lower**: Prompt an apples-to-apples check (same specs, packing, FOB vs. EXW, QC included).
   * **Demands 20% to 30% cut**: Hold the floor, point to the FCL tier, or trade small adjustments only for higher deposit / faster payment.
   * **Free sample + free courier**: Charge sample and courier upfront, with a clear deduction credit against the first trial order.
   * **Closing without burning bridges**: Propose starting with the trial order to verify quality, then unlocking volume pricing on repeat orders.

## Gotchas

* Never adjust the FX buffer in the wrong direction: for a Chinese exporter converting USD/foreign currency back to RMB, a *lower* USD/CNY quoting rate is safer; a *higher* rate underprices the quote and loses money.
* Never leak internal RMB costs, VAT rebate rates, or net profit margins into the English buyer-facing email or counter-bargaining scripts. Keep all cost breakdowns strictly in the internal Chinese analysis section.
* Never fabricate live HS duty rates or exact freight quotes; label forwarder local charges clearly as working estimates to confirm before binding commitment.
* Always include a quote validity period and an FX/freight fluctuation clause in the buyer email.
