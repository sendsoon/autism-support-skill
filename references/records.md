# Profile and problem log

Read this file before reading or writing records. Suggestions, safety limits, and the response shape still follow `SKILL.md`.

Store records in the **current workspace**, not in the skill install directory, and do not commit them.

```text
autism-support-records/
├── index.md
└── <nickname>/
    ├── profile.md
    └── logs/
        └── YYYY-MM-DD.md
```

Use the nickname the caregiver gave as the folder name. Replace spaces or characters the filesystem rejects with hyphens. If that folder already exists and you cannot tell whether it is the same child, ask. Do not overwrite it.

If the workspace is a Git repository, add `autism-support-records/` to `.gitignore`. Add only that line. Do not commit the records.

Write the whole profile, index, and every log in English. Translate what the caregiver said into English. Do not add facts while translating, and do not leave the original language in the file.

## When to read and write

1. Before answering about a child, read `index.md` and that child's `profile.md`. If recent logs exist, read the latest few so you do not ask again for facts already written down.
2. If someone is in immediate danger, give the safety step first, then ask and record.
3. If this child has no profile, ask for the nickname and current age together. Do not ask again for something already said. Before those two facts are known, you may explain a general principle, but do not write the plan as if you already know this child.
4. Write the files after the reply in that turn. Tell the caregiver which log entry you wrote. If the write fails, say that nothing was saved.
5. When the caregiver asks for a review, a comparison over time, or a change to a long-term goal, read that child's `profile.md` and all logs before you analyze.

## What to ask first

The first time, ask only for the nickname and age.

If other fields are empty, do not send them as a form. After you answer the current question, ask for one missing field, in this order:

1. Gender
2. Primary caregiver (mom, dad, grandparent, or another role; not a full name)
3. School or daycare (a short label, a grade, or "not in school yet")
4. Daily learning, self-care, and activities
5. Interests
6. Rehabilitation: which centers the child currently attends, and for each teacher the qualification and gender. One question may ask for both. Do not ask for the teacher's full name, the center's address, or a phone number.

If the caregiver already gave several of these, write them all. Do not ask again just to follow the order.

## Age

Store these fields in the `profile.md` front matter:

- `first_record_date`: the date the profile was first created, as `YYYY-MM-DD`. Never change it.
- `age_reported`: the caregiver's age statement, written in English, for example `4 years old`, `4 and a half`, `4 years 3 months`, or `born in 2019`.
- `age_reported_years` and `age_reported_months`: numbers parsed from that phrase. `4 and a half` is 4 years and 6 months. `4 years old` with no months is 4 years and 0 months.
- `age_precision`: `birthday`, `year_month`, or `year`.
- `birthday`: fill only if the caregiver offers it. Do not ask for a birth date.

Whenever you use the profile later, calculate age from the first record date. Do not keep treating `age_reported` as the current age.

- If there is a birth date, use completed years and months from that date to today.
- If years and months were both stated, add the full years and months from the first record date to today.
- If only a whole number of years was stated, add the elapsed years and months, and label the result as an estimate. "4 years old" on that day may already have included up to almost 12 months, so the true age may be somewhat higher or lower.

In suggestions and logs, write "about 4 years 6 months (estimated from '4 years old' recorded on 2026-11-18)". Do not also state a different age without saying where it came from.

If the caregiver later corrects the age or gives a birth date, do not change `first_record_date` or the original `age_reported`. Write the new fact into the current fields, and add the old value, the new value, and the date under "Profile changes".

## profile.md

Stable facts go here. Leave unknown fields blank. Do not write "typical", "unknown", or a guess.

The shape is in [examples/record-template.md](../examples/record-template.md).

When one of these changes, update the section and move the replaced sentence to "Profile changes". Do not delete it.

- Gender
- School or daycare
- Primary caregiver
- Daily learning, self-care, and activities
- Interests
- Rehabilitation: short center label, and each teacher's qualification and gender. No full name or address.
- Diagnosis and professional assessments (only what the caregiver or a written report actually said)
- Current support focus

## Problem log

One file per day: `logs/YYYY-MM-DD.md`. If several things happen the same day, append. Do not overwrite earlier entries.

Use a short title the caregiver would recognize. Include these fields. If the caregiver did not say, write "Not stated". Do not invent it.

- Estimated age at this entry
- Setting: home, school, a public place, or a social situation
- What the caregiver described: what the child did or said
- Frequency
- What was already tried, and what the caregiver saw
- Suggestion given this time
- Tell the rehab teacher: yes or no, and the one in-person skill to ask for if yes. Not stated if the caregiver has no rehab teacher.
- What to watch
- Still unverified
- Follows: if this continues an older problem, the path of that log

When the caregiver later says how a suggestion went, append a new entry. Point "Follows" at the old entry. Do not rewrite what the old entry said at the time.

## Review across logs

Review across logs only when the caregiver asks, or when a new question clearly depends on the history. Separate:

- Settings and needs that keep returning
- Steps the caregiver found helpful or unhelpful
- Changes in skills or interests
- Facts that are still missing
- One next support focus

Do not collapse several logs into a diagnosis. Do not treat one suggestion as a cause that has been confirmed.

## Privacy

Record the nickname. Do not record a legal name, identity number, address, phone number, full school name, school address, a therapist's full name, or a center's address. A short center label plus the teacher's qualification and gender is enough. If the caregiver already typed sensitive details into the chat, do not copy them into the profile.
