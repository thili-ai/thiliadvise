# The same checklist, different data

The reusable reference from Lesson 3. The six items don't change — where each one actually bites
does, by data type.

| Data type | Where it bites hardest |
|---|---|
| **Text** | Row count misleads (repetitive boilerplate); labels are often implicit; PII sits inline, sometimes inconsistently redacted; policies/prices under the text go stale; internal notes hide inside "clean" exports. |
| **Images** | Diversity matters more than count — 1,000 photos of one angle isn't 1,000 data points; specialised domains (e.g. medical) need expert annotators, not crowdworkers; PII is faces, plates, visible documents, and backgrounds; check who owns the copyright of the source photos. |
| **Audio** | Transcription quality gates everything built downstream of it; PII includes voiceprints (a biometric identifier under several regimes) and spoken PII, plus other people's voices caught in the background; two-party consent-to-record laws vary by jurisdiction. |
| **Video** | Combines image and audio PII simultaneously; storage cost compounds fast; bystanders appear in frame unintentionally, without ever having consented to anything. |
| **Time-series** | Ground truth often lives in a separate system (e.g. a fraud case only confirmed by a later investigation); re-identification risk exists even with no name attached, via the mosaic effect across enough data points; behavioural baselines drift over time. |

## Re-identification, briefly

A location trail or a health-monitoring sequence can identify a specific person with no name field
anywhere in the dataset — enough distinctive data points about one entity, cross-referenced against
public information, narrows to one person. This is why "we stripped the names" is not the same claim
as "this data is anonymous," especially for time-series and location data.
