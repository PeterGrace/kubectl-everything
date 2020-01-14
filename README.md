# kubectl-everything
Are you frustrated by 'kubectl get all' not actually returning all?  Well, I was, and it turns out that the `get all` command is planned to be deprecated eventually.  My annoyance has manifest into a kubectl plugin called `kubectl everything`, which is a simple bash script that outputs *everything* in the current namespace, a specified namespace, or all namespaces.  The script here is accessible as a kubectl plugin if you store it in your path as an executable bash file called `kubectl-everything`.

## Usage
  * `kubectl everything` -- Show all resources that are in your current namespace, as well as cluster-wide resources.
  * `kubectl everything -n foo` -- Show all resources in foo namespace, as well as cluster-wide resources.
  * `kubectl everything -a` -- show all resources in the entire cluster
