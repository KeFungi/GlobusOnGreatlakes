# GlobusOnGreatlakes
## Fisrt time setup
### Download globus connect personal
```bash
wget https://downloads.globus.org/globus-connect-personal/linux/stable/globusconnectpersonal-latest.tgz
tar xzf globusconnectpersonal-latest.tgz
# replace `x.y.z` in the line below with the version number you see
cd globusconnectpersonal-x.y.z
```
### Setup account
Run the command below, copy the produced URL to a web browser, log in to your Globus account, set the name of the machine, and enter the authentification code to the command line prompt

```bash
./globusconnectpersonal -setup
```

### Edit accessible path 
Edit the file `~/.globusonline/lta/config-paths`, which controls the paths accessible to Globus

This file is a headerless CSV with fields defined as follows.
```
<path>,<sharing flag>,<R/W flag>
<path>,<sharing flag>,<R/W flag>
...
```

For example to download files to Turbo, add the line to the file
```
/nfs/turbo/lsa-tyjames/mycology/next_gen_seq_data,0,1
```

## Connect
Run the command below. While the command is hanging, it works as an accessible “Collection (Endpoint)” in Globus, so you can find the machine and execute file migration operations through Globus webpage

```bash
./globusconnectpersonal -start
```
