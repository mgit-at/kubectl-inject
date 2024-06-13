# kubectl-inject

Make every debugging way that is possible, easy to use!

This project should also serve as a stark reminder of the complexity of kubernetes security mechanism, because this tool will use every method to reach it's goal even if it's a results of missunderstood or hard to use kubernetes security configs.

And will hopefully one day provided via a simple install with [krew - kubectl plugin manager](https://krew.sigs.k8s.io/) 

## GOALs

working tooling for debgging container in k8s in environments that don't have an "allow all" config or where the debugging person is NOT cluster-admin

1. working `kubectl cp` without `tar` inside container
2. working `kubectl debug` that injects intself INTO the running container (thus all processes and all files and PVs are there)
3. Having a simple editor like `vi` ready to just change some config files on an in use PV

## TODOs

- method to `kubectl cp` without requiring `tar` in the container
- usable `kubectl debug` to connect INTO a running container in a pod and debug running daemons
  - like interacting with files and PVs (this does not work with `kubectl debug` and makes it practically useless for most of our usecases)
  - seeing processes (granted that works with `kubectl debug --target`)
 
## Mentions

[kubectl-superdebug](https://github.com/JonMerlevede/kubectl-superdebug) - really nice tool, though mostly lacking permissions to patch pods
