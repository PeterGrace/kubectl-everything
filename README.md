# kubectl-everything
Are you frustrated by 'kubectl get all' not actually returning all?  Well, I was, and it turns out that the `get all` command is planned to be deprecated eventually.  My annoyance has manifest into a kubectl plugin called `kubectl everything`, which is a simple bash script that outputs *everything* in the current namespace, a specified namespace, or all namespaces.  The script here is accessible as a kubectl plugin if you store it in your path as an executable bash file called `kubectl-everything`.

# kubectl-sadpods
This command will show you all pods that are not in Running or Completed status.

# kubectl-sadreplicas
This command will show you any replicasets that don't have the same number of "ready" pods as they've requested.

# kubectl-get_laq
This command will produce an Azure Log Analytics query suitable for finding container logs for a deployment or pod.

# kubectl-get_pod_priority
This command produces a list of pods and what priorityclass they're operating under.

# kubectl-get_psp
This command produces a list of pods and what Pod Security Policy they're operating under.

## Prerequisites
  * You'll need a recent kubectl binary.

## Installation
  1. Copy kubectl-\* into your path.
  1. Enjoy being able to find all the things in your namespaces.

## Usage (everything)
  * `kubectl everything` -- Show all resources that are in your current namespace, as well as cluster-wide resources.
  * `kubectl everything -n foo` -- Show all resources in foo namespace, as well as cluster-wide resources.
  * `kubectl everything -a` -- show all resources in the entire cluster
## Usage (sadpods)
  * `kubectl sadpods` -- Show all pods in this namespace which are not Running or Completed.
  * `kubectl sadpods -n foo` -- Show all pods in specified namespace which are not Running or Completed.
  * `kubectl sadpods -a` -- Show all pods in the whole cluster which are not Running or Completed.
## Usage (sadreplicas)
  * `kubectl sadreplicas` -- Show all replicasets in this namespace which do not have the same number of ready pods as requested.
  * `kubectl sadreplicas -n foo` -- Show all replicasets in specified namespace which do not have the same number of ready pods as requested.
  * `kubectl sadreplicas -a` -- Show all replicasets in the whole cluster which do not have the same number of ready pods as requested.
## Usage (get-laq)
  * `kubectl get-laq -p podname` -- Get a Log Analytics query for a particular pod id.  Can use -n to specify alternate namespace, or -a for all.
  * `kubectl get-laq -d deployment` -- Get a Log Analytics query for all containers deployed to a deployment specification. -n and -a as above work as expected
## Usage (get-pod-priority)
  * `kubectl get-pod-priority` -- Show all pods in this namespace and what priorityClass they're running under.
  * `kubectl get-pod-priority -n foo` -- Show all pods in specified namespace and what priorityClass they're running under.
  * `kubectl get-pod-priority -a` -- Show all pods in the whole cluster and what priorityClass they're running under.
## Usage (get-psp)
  * `kubectl get-psp` -- Show all pods in this namespace and what Pod Security Policy applies to them.
  * `kubectl get-psp -n foo` -- Show all pods in specified namespace and what Pod Security Policy applies to them.
  * `kubectl get-psp -a` -- Show all pods in the whole cluster and what Pod Security Policy applies to them.
