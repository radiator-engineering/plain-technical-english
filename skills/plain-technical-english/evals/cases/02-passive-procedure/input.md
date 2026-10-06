# Rotating the ingest worker

Before the rotation is attempted, it should be verified that the queue depth has been reduced to below 100 messages. The current depth can be checked by the operator via `nats stream info CLIPS --json | jq .state.messages`.

Once it has been confirmed that the depth is acceptable, the worker deployment is to be restarted. This is accomplished through the execution of `kubectl rollout restart deployment/ingest-worker -n ambience`. It is anticipated that the pods will be recreated within approximately two minutes, after which readiness should be confirmed by the operator through the running of `kubectl rollout status deployment/ingest-worker -n ambience`.

In the event that the rollout is observed to be stalled for a period exceeding five minutes, it is recommended that the on-call engineer be paged, and the rotation should not be re-attempted until the underlying cause has been identified and remediated.
