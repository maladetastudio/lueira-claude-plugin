---
name: lueira-product-forms
description: Help a Lueira tenant build, review and change the forms customers fill in at checkout, check-in or per participant, and see which products use them.
---

Discover the available Lueira product form tools and read their schemas before choosing an operation. The public MCP exposes different tools according to the connected tenant's scopes, so a missing write tool means the connection can only read forms.

A form is an ordered list of reusable sections, and a section holds the questions. The admin calls the section library the "Collection". A section can be shared by several forms: editing it changes every form that uses it. A product can use a form in three slots: checkout (shown in the online store before the purchase is completed), check-in (collects information during check-in or before the activity starts) and participant (shown for each participant during online booking). Answer validity, in days, only matters for check-in forms: a participant's answer is reused until it expires, and a form without validity never expires.

To build a form, first read how questions are written with the question schema tool; do not guess question types or properties. Then read the existing forms and sections and reuse a section when it already matches the request. Create the new sections, create the form with the section IDs in display order, and attach it to a product with the update tool of that product type. Question rules in plain words: radio and select questions need options; a yes/no question can reveal nested questions, but nested questions cannot be yes/no questions or static text; copying an answer into a customer record is only possible from top-level questions and only to the listed fields; translations use the supported language codes. If the tool refuses a question, read the reason, fix that question and retry; do not drop the validation.

To edit a section, read it first, change the question list and send the complete list back: the questions replace the old ones. Before editing a shared section, list the forms that use it where possible and tell the user that all of them change.

Before deleting a form, or moving its products to another form, list the products that use it and show them to the user. Replacing a form's usages repoints every product slot at once and changes live checkouts; it needs explicit confirmation and cannot be undone automatically. Deleting a form is refused while products use it. Deleting a section does not check the forms that use it, so only delete a section the user knows is unused.

Make only the changes the user requested and respect the host's confirmation requirements. After a successful write, summarize the form or section, the returned IDs and the products affected.

Documents customers sign are separate from forms. A document template can be renamed or given a different signer (the buyer, each participant, or both) when document signing is enabled for the business; documents already generated keep their signer. Creating a template needs a PDF and cannot be done through this connection.

To make a participant fill a form in again, invalidate the submission shown for the order: it needs the sensitive personal-data write permission, which many connections do not have, and the business's sensitive tools enabled. Find the submission and order IDs from the participant's submission list, confirm with the user, and know that the answers themselves are never shown.

Limits: forms from before reusable sections (version v1) can be read but not created or edited here. Courses have no product tools in this MCP, so their form slot can only be changed by replacing a form's usages.
