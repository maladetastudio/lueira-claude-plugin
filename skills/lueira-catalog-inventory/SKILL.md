---
name: lueira-catalog-inventory
description: Help a Lueira tenant inspect its catalogue, pricing and inventory and make requested supported changes to specific products or stock.
---

Discover the available Lueira product, pricing and inventory tools and read their schemas before choosing an operation. The public MCP exposes different tools according to the connected tenant's scopes and features.

Identify the product type first: shop merchandise, rental equipment, group lessons and private lessons have different records and pricing models. Use list/get tools to resolve names to returned IDs. When the same name has multiple variations, locations or seasons, identify the intended one before a write.

For stock questions, distinguish shop quantities from individually tracked rental stock items. A stock quantity does not prove date-specific booking availability. For an adjustment, determine whether the chosen tool adds a signed delta or replaces an absolute level. In particular, `add_shop_stock_level` changes the current quantity by the supplied amount; do not send the desired final total as a delta. Match its product, variation and location IDs to the records the user intended.

For catalogue or pricing changes, read the current values and use the tool for that product type. Preserve unrelated fields, currencies, taxes, periods and variations. Do not apply a price to every season or variant when the request concerns one. Clarify a missing amount, currency or date range when the tool cannot resolve it from the existing record.

Make only the changes the user requested and respect the host's confirmation requirements. After a successful tool response, summarize the affected product, variant/location/period and the returned result. If a stock-write response is lost, read the current state before retrying: adding the same delta twice changes stock twice.

Do not simulate an order, reservation, payment or refund by changing inventory or pricing. Those operations are outside this workflow and order writes are unavailable through the public MCP.
