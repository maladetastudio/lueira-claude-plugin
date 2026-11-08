---
name: lueira-business-report
description: Answer a Lueira tenant's questions about orders, bookings, rental stock and instructors using its connected MCP data.
---

Use the connected Lueira account's available tools to build a report grounded in returned records. Discover the current tool definitions; available tools depend on the tenant's permissions and enabled features.

- For customer-specific questions, find the customer first and use the returned ID to filter orders. Resolve ambiguous matches before attributing bookings or balances to someone.
- Distinguish orders created during a period from bookings starting during that period. Use the requested date field and the business's timezone. Clarify an unknown timezone when it changes which records belong in the report.
- `list_orders` supports customer, status, payment-status and date filters. Inspect its current schema for the exact argument names and enum values. Use `get_order` and `list_order_items` for the details of an identified order.
- Follow pagination until the requested range is covered. A first page is not a complete dataset. If limits prevent completion, state the covered range and do not present partial sums as business-wide totals.
- Keep currencies separate and preserve the amounts and units returned by the tools. Distinguish order value, amounts paid and outstanding balances; one cannot be inferred from another without supporting data.
- Use rental-product stock tools for equipment questions and instructor tools for staff lookups. Stock counts alone do not establish that equipment is available for a future booking, and an instructor record alone does not establish scheduling availability.
- Give the scope and period of the answer, supported totals or records, and any missing information. Include returned Lueira links when useful. An empty result is different from missing access or a failed request.

This workflow reads data. Order and booking creation, modification and cancellation, payment registration, and refunds are outside the public MCP's supported operations. Explain those limits when requested; do not claim a booking or payment was completed.
