# Testing Gatekeeper policies

* Install Gatekeeper operator via OLM
* Apply policies from `Policies/Gatekeeper`: '% oc apply -k AdmissionPolicies/Policies/Gatekeeper'
* Deploy demos
  * 'oc apply -k AdmissionPolicies/Policy-tests/Gatekeeper/[low|medium|high]'
* Check results

