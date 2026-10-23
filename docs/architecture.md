# Bruxus architecture (first sketch)

This is a starting point for discussion, not a final design.

## Layers

```
Digital world (email, chat, files, web, code, systems, feeds)
        |
   [ Perception ]   connectors that observe and normalise signals into events
        |
   [ Memory ]       event log + structured knowledge + searchable index
        |
   [ Interpretation ]  classify, summarise, link, prioritise, detect change
        |
   [ Interface ]    briefings, alerts, answers to questions, requested actions
        |
      Human
```

## Layer responsibilities

- **Perception**: each connector turns an external source into a common event shape (source, time, content, metadata). Connectors are read-only by default.
- **Memory**: an append-only event log as the source of truth, plus derived structures (entities, relationships, summaries) and a search index. Derived data can always be rebuilt from the log.
- **Interpretation**: models and rules that decide what an event means for this person: relevance, urgency, relationships to people, projects and earlier events.
- **Interface**: how the human receives interpretation (daily briefing, real-time alerts, ask-anything queries). Any action on the person's behalf requires explicit permission.

## Principles

- The human stays in control: Bruxus informs first and acts only when authorised.
- Privacy by design: personal data stays under the person's control, with clear limits on what is stored and shared.
- Explainable: every interpretation points back to the signals it came from.

## Open questions

- Which digital surfaces should Bruxus perceive first?
- What is the first capability that would make it useful day to day?
- Where does it run (local, cloud, hybrid) and which languages and frameworks does it use?
- How is the binary stream in `docs/stream.md` meant to be used by the project?
