# Istio Service Mesh

## Canary Deployment 

<details>
<summary>What are Canary Deployment and why do we need it?</summary></br>
A simple release method involves deploying the updated version to replace the existing one. Nevertheless, this deployment strategy promptly exposes all users to potential defects introduced by the new version.</br></br>
Canary releases solves this problem using a safe  approach where both versions of the application, the old and the new, run in parallel until the new version is completely validated and ready for all users. The new version, also called the canary, initially receives only a small amount of all application traffic. Therefore, if something goes wrong with this new version of the application, a minimal number of users are affected. As you gain confidence with how the canary works, you progressively route more traffic to it.
</details>

<details>
<summary>When do we use Canary Deployment?</summary></br>
* Your application handles high loads and you want to perform load or stress testing on a new.</br>
* Need a safe strategy to deploy a new critical version.</br>
* Analyze and Validate new version with reduced group of users to analyze how this affect your application.</br>
</details>

<details>
<summary>What K8s and Istio resources are needed to create Canary Deployment?</summary></br>
* Deployment</br>
* Service</br>
* Virtual Service</br>
* Destination Rule</br>
</details>
