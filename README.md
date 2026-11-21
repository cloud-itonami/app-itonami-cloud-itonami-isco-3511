# cloud-itonami-isco-3511
Occupation reference: ISCO-08 (International Labour Organization, 2012), code 3511. This app is not produced, reviewed or endorsed by the ILO.
職業の参照: ISCO-08（国際労働機関 ILO、2012 年）のコード 3511。日本語の名称は当方の訳です。この app は ILO が作成・確認・推奨したものではありません。

Open Business Blueprint for **ISCO-08 3511**: ICT Operations Technicians — an ISCO
**Wave 0 (cognitive substrate)** occupation per the reverse-toposort
rollout plan (ADR-2607121000): pure-cognitive work, the LLM-first wave,
with **no robotics gate** — eligible for actor implementation now.

**Maturity: `:implemented`** — ICTOperationsTechniciansAdvisor ⊣
ICTOperationsTechniciansGovernor as a langgraph StateGraph
(`intake → advise → govern → decide → commit/hold`, human-approval
interrupt), modeled on cloud-itonami-isco-4311's bookkeeping actor.
13 tests / 27 assertions green.

The ops HARD invariants — arithmetic and set coverage, not a best
effort:

1. **SLA arithmetic** — the proposed response-time-minutes must not
   exceed the system's registered SLA ceiling.
2. **Certification coverage** — the responding technician's
   certifications must be a superset of the system's registered
   required-certifications set (no partial-coverage response).

Also HARD: unregistered/foreign system, unregistered organization,
non-`:propose` effect. Escalations (always human sign-off):
`:approve-emergency-override` (bypassing normal change control under
incident pressure), low confidence (< 0.6).

AGPL-3.0-or-later, forkable by any qualified operator. Part of the
[cloud-itonami](https://itonami.cloud) open business fleet
(labor-transition context: ADR-2607122100 — ISCO wave-0 agentization
is marketed through the 7810 labour-exchange lane).
