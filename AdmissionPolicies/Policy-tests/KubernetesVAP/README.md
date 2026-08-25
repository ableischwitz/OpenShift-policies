# Testing Validation Admission Policies

* VAP is already included in Kubernetes 1.30 (OpenShift 4.16)
* Apply policies from `Policies/KubernetesVAP`: '% oc apply -k AdmissionPolicies/Policies/KubernetesVAP'
* Deploy demos
  * 'oc apply -k AdmissionPolicies/Policy-tests/KubernetesVAP/[low|medium|high]'
* Check results
