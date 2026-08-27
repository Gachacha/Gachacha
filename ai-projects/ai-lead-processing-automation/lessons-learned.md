# Lessons Learned

1. AI and automation are different layers: AI handles understanding/transformation; automation executes defined actions.
2. A trigger starts a workflow; conditions determine paths; actions change the business state or communicate an outcome.
3. Workflow state should describe what has actually happened, not predict what might happen.
4. Verification and qualification are separate states.
5. Recommendation sent does not mean customer accepted or booked.
6. State and action-completion checks help prevent duplicate actions.
7. Rule priority can override the normal linear workflow.
8. Sensitive cases must be routed before normal automated decisions when the approved hierarchy says so.
9. Customer preference must remain separate from system recommendation.
10. A reliable AI workflow has a defined boundary and a human fallback.
