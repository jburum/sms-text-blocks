---
name: sms-text-blocks
description: Convert Grok chat output into very brief, concise SMS-ready text blocks optimized for Apple iPhone Messages. Trigger on sms, text message, iMessage, iPhone Messages, copy-paste text, SMS-friendly, text it, make this textable, phone-readable draft, or when the user wants a prior answer reformatted for pasting into Messages.
---

# SMS Text Blocks

## Overview

Rewrite any Grok answer or source text as short, copy-ready blocks for Apple iPhone Messages. Optimize for the Messages compose field and bubble width, not Android or other apps.

Match standing SMS draft style — short lines, extra blank lines between items, no dense paragraphs.

## When this skill is on

- User asks to text, SMS, iMessage, or make something phone-copyable.
- User points at a prior Grok reply and wants it paste-ready.
- Default deliverable is the SMS body itself, not a file, not markdown, not HTML.

## Output contract

1. Lead with the paste-ready block. No preamble, no "here is your text".
2. Wrap the block in a single fenced code block using the language tag `text` so the UI copy button copies the body only.
3. After the fence, one short line max if a note is required (e.g. split into 2 texts). Otherwise stop.
4. Do not add a second formatted version. One block unless the user asked for variants (short / even shorter).

## Rewrite rules (iPhone Messages)

- Plain text only. No markdown headings, bold, italics, tables, or raw markdown markers in the body.
- Simple leading dash is allowed. No `**`, no `#`, no backticks inside the SMS body.
- One idea per line. Hard wrap around 35–42 characters when a sentence would wrap mid-word in a bubble. Break at commas or natural pauses.
- Extra blank line between items, between a label and its value, and between distinct thoughts. Never stack more than two non-blank lines without a blank separator if they are separate facts.
- No walls of prose. If the source is a paragraph, explode it into labeled scraps.
- Numbers, times, addresses, names, and asks sit on their own lines.
- Questions to the recipient go last, each on its own line.
- Drop hedging, citations, "as of", source lists, and consultant framing unless the recipient needs them.

## Emoji (accent, never replace)

- Use a few well-placed Apple emoji as scan cues on section labels and key facts.
- Emoji sit next to words. Never swap a word for an emoji. The text must still make sense if every emoji is stripped.
- Typical placement — one emoji at the start of a section label or on the line that carries time, place, money, or the ask.
- Default budget is 3–6 emoji in a short text. Skip a line rather than decorate every line.
- Vendor / contractor texts stay lighter (0–3). Family / logistics can use the full budget.
- Prefer common iOS glyphs that render in Messages — calendar, clock, pin, car, ski, dog, house, bolt, money, box, key, check, question.
- No sticker spam, no emoji-only lines, no skin-tone sequences unless the user wrote them.
- Links on their own line. Prefer short URLs. Do not wrap a URL across lines.
- Phone numbers and addresses in the form iPhone will tap-target (digits with hyphens or spaces; full street on one line).
- Avoid special unicode dashes, smart quotes, and non-breaking spaces. Use ASCII hyphen and straight quotes.
- Do not start a line with a digit-period list if a dash or blank line works. iPhone sometimes auto-formats numbered lists oddly.

## Length

- Default target is one screen on an iPhone compose field (~400–700 characters, usually under 12 short lines plus blanks).
- If the source cannot be honest in that budget, split into labeled parts inside the same fence using Part 1/2 and Part 2/2 so each part can be sent as its own message.
- Never silently omit a date, time, place, dollar amount, name, or required ask. Cut color and repetition first.

## What to keep vs cut

Keep
- The action or decision
- Who / what / when / where / how much
- The question the recipient must answer
- Constraints that change the plan

Cut
- Background the recipient already knows
- Alternative options unless the user asked to present choices
- Process narration
- Legal or medical disclaimers unless the user is sending those on purpose

## Tone

Mirror the intended recipient.
- Family / casual — first names, short verbs, no corporate voice.
- Vendor / contractor — polite, specific, one ask.
- Do not add greetings or sign-offs unless the user included them or the recipient would find a bare dump rude. Default is no Hey and no name sign-off.

## If the source is missing

If there is no prior content to convert, ask in one line what to text and to whom. Do not invent a sample campaign.

## Examples

See `references/examples.md` for before/after patterns. Follow those line-break and blank-line rhythms exactly.
