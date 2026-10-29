# Question-led usability adaptation

Use during implementation and review of a user-facing web surface, especially responsive work. Create and answer the questions yourself from the brief, existing product and observable behavior. Do not turn internal design checks into a questionnaire for the user; ask only when missing information changes a material decision.

## Bounded loop

1. Identify the primary task, target screen sizes and input methods. Preserve product truth, brand and access contracts.
2. Generate 3–5 concrete friction questions for the actual journey. Prefer questions with observable answers over “does this look good?”.
3. Inspect the current UI with real content. For each material failure, record `question → observation → smallest structural change → verification`. Source inspection is evidence about implementation, not proof of real input behavior.
4. Change the structure when the context requires it: reorder, reflow, reduce disclosure, change navigation presentation or move primary actions within reach. A narrower desktop canvas, clipped content or smaller type is not mobile adaptation. Reuse components and one content model.
5. Verify the changed journey in one batched desktop/mobile pass, fix the failures together, then confirm the fixes. Distinguish viewport layout checks, synthesized input and physical-device evidence. Report any untested engine/device/gesture accurately.

## Useful questions

- Navigation: Does opening the menu obscure the task? Are frequent destinations available without opening it? Is an overlay, full-width menu screen, inline disclosure or bottom navigation best for this product? Preserve a predictable exit and keyboard focus; a drawer is not always wrong.
- Reading: Can the title, essential metadata and primary action be understood without horizontal page scrolling? Does the next partially visible item communicate an intentional carousel rather than clipping?
- Touch: Can controls be tapped with a 44px target? Do vertical swipes scroll naturally across horizontal controls? Are core actions available without hover?
- Media: Are images composed for the slot rather than cropped into unreadability? Does a preview preserve the detail-link contract, pause when hidden and explain loading without hiding useful content?
- Continuity: Who owns scroll and focus? Does closing a menu return to the same position? Do loading, back, reselect and cancellation produce distinct, predictable outcomes?
- Material: Does glass clarify a floating layer while keeping text readable over real content? Is there an opaque fallback for unsupported filters or reduced transparency? Avoid claiming CSS blur is native Liquid Glass.

For a new interactive UI, apply `dexter-hci` when available: map state, event, scroll/focus owners and iframe boundaries; load only the relevant topic. If unavailable, apply the same explicit interaction contracts locally and disclose that the skill could not be loaded. Brand tokens remain authoritative. Do not require a new library, bottom bar or glass effect for every project.
