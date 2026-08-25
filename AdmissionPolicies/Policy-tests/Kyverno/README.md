# Testing Kyverno Policies

* Install Kyverno:
  * '% helm repo add kyverno https://kyverno.github.io/kyverno/'
  * '% kubectl create namespace kyverno'
  * '% helm install kyverno --namespace kyverno kyverno/kyverno' (adjust memory limits!)
* Apply policies from `Polies/Kyverno`: '% oc apply -k AdmissionPolicies/Policies/Kyverno/'
* Deploy `AdmissionPolicies/Policy-tests/Kyverno/deny_nodePort`: '% oc apply -k  AdmissionPolicies/Policy-tests/Kyverno/deny_nodePort'
  * This should be rejected due to the policy
* Deploy `AdmissionPolicies/Policy-tests/Kyverno/deny_pod_wo_limits_req`: '% oc apply -k AdmissionPolicies/Policy-tests/Kyverno/deny_pod_wo_limits_req'
  * This should succeed, but create a `PolicyReport` in the pod-namespace with 2 failures (limits and requests missing)
* Deploy `AdmissionPolicies/Policy-tests/Kyverno/allow_pod_w_limits_req`: '% oc apply -k AdmissionPolicies/Policy-tests/Kyverno/allow_pod_w_limits_req'
  * This should also succeed and create a positive report.
