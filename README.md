# copilot-procurement

## What it does

Procurement Assistant: quote comparison, BOM comparison, supplier assessment and reorder planning.

Part of the **department-copilots** suite: local-only copilots where the employee provides the input, Claude analyses it on the machine, and the employee decides what to do. No CRM, NMS, email or system integrations.

## Install

```bash
claude plugin marketplace add sara-hamza/department-copilots
```

```bash
claude plugin install procurement@department-copilots
```

Drop in the quotes, BOMs, supplier documents or stock figures and get back a normalised comparison table, the mismatches, a structured supplier assessment or a reorder plan with the arithmetic shown.

| Command | Use when |
|---|---|
| `/procurement:compare-quotes <quotes>` | Two or more quotes for the same scope: Criteria x Supplier table, recommendation basis, what is missing from each quote |
| `/procurement:compare-bom <BOM A + BOM B or quote>` | Design BOM vs contractor BOM, or BOM vs supplier quote: quantity, item and price mismatches |
| `/procurement:supplier-assess <supplier info>` | New or renewing supplier: capability, risk, compliance documents present/missing |
| `/procurement:reorder <stock + lead time + usage>` | What to order and when, from current stock, usage and lead times |

Requires `copilot-common` (its spreadsheet-reader profiler and document-reader do the file reading).

Reference knowledge lives in `skills/procurement-assistant/references/`. Safety stock, review periods and compliance document lists there are sensible defaults marked `CUSTOMISE`; tune them to the company's procurement policy.

The assistant compares and recommends a basis. It does not award, commit spend or sign anything.
