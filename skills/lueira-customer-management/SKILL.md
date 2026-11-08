---
name: lueira-customer-management
description: Find, create or update customer records in the connected Lueira business, resolving duplicates and ambiguous identities before writing.
---

Use Lueira's current customer-tool schemas and the tenant connection already selected by the user. Permissions come from that connection, not from a tenant ID supplied in conversation.

For an existing customer, search using the identifying information the user supplied, then fetch the matching record. Names may not be unique: use returned email, phone or other relevant details to distinguish candidates. Ask about an unresolved identity before making a change.

Before creating a customer, check for an existing matching email or other strong identifier. If the match is uncertain, explain it rather than silently creating a duplicate or modifying a different person. Use the user's supplied values; do not fabricate contact details, fiscal data, birth dates or marketing consent.

For updates, inspect the current record and current tool schema. Send the requested changes, preserving unrelated fields. Do not use empty strings as placeholders: an empty value may clear saved data. Treat a requested correction of an email address separately from newsletter or other consent.

For deletion, identify the exact customer and follow the host's applicable confirmation flow. Do not delete records as a way to resolve a search or permission error. Report only the effect confirmed by the tool; deletion does not establish that related bookings, invoices or legal records have also been removed.

After a successful write, report the returned customer ID and the actual changes. If the response is uncertain or times out, check the record before retrying a creation. Do not declare success on an error or repeat a write blindly. If the account lacks the required customer scope, explain the permission gap without changing the connection's permissions yourself.
