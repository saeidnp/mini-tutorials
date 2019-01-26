# Remotely access a Jupyter Notebook
(Most of this mini-tutorial is taken from [here](https://coderwall.com/p/ohk6cg/remote-access-to-ipython-notebooks-via-ssh))

Basically, what we should do is:
1. Run Jupyter notebook on the remote machine on a specific port.
```
remote_user@remote_host$ jupyter notebook --no-browser --port=8889
```
2. ssh to remote machine and fo port forwarding.
```
local_user@local_host$ ssh -N -L localhost:<local-port>:localhost:<remote-port> remote_user@remote_host
```
    - A typical choice for `<local-port>` and `<remote-port>` is 8888 or 8889.
    - `-N` means no remote commands will be executed and can be used when you only want to do port forwarding.
    - You can add `-f` flag to the command above to ssh (and basically forward ports) in background. However, in that case for stopping port forwarding you need to find and kill its process manually.
    - If you saw `bind: Cannot assign requested address` error, it's probably the problem of IPv4 and IPv6 mismatch; add `-4` to ssh command to fix that.
3. You can access Jupyter Notebook remotely using the forwarded port, i.e. accessing `localhost:<local-port>` through your browser. It might ask for a key in this step. It's better to always insert the key in the address, i.e. using `localhost:<local-port>/?token=<JUPYTER_TOKEN>`.  `JUPYTER TOKEN` can be found in the url printed in the output of step 1. It has this format: `localhost:<remote-port>/?token=<JUPYTER_TOKEN>`

