# Leakage surface checklist

Four surfaces. Check all four — "the model didn't say anything wrong" only covers one of them.

## 🔍 Retrieval

- [ ] Is the search index scoped so a query can only return documents the requesting user/context
      should actually see?
- [ ] Could a document from a different permission boundary (internal notes, another tenant's data,
      an unrelated system) ever score as relevant and get pulled in?

## 📋 Logs

- [ ] Do stored transcripts include the full retrieved context, not just the final answer?
- [ ] Who — internally, or at any third-party vendor — has access to those logs?
- [ ] Is there a redaction step before logs leave the system that generated them?

## 🪟 Context windows

- [ ] Is session state properly isolated per user/conversation, with no shared caching that could
      leak one session's content into another's?
- [ ] Within a single long session, could information retrieved for one purpose resurface later in
      an answer to an unrelated question?

## 🛠️ Tool outputs

- [ ] Does every tool return only the fields a task actually needs, or does it pass through a full
      internal record because that's what the underlying API happens to return?
- [ ] Is there a filtering layer between a tool's raw response and what enters the model's context?

## Before finalizing

- [ ] Checked all four surfaces, not just whether the final answer looked wrong
- [ ] Named which surface(s) are actually exposed in the system under review
- [ ] Distinguished failures that need an attacker (injection) from failures that don't (most tool-
      output and context-window leaks require no attacker at all)
