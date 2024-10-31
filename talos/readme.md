# Talos setup

## Setup
Install Nix-shell and run `nix-shell` to get an environment where all the needed tools are installed.
Or install them manually.

## Generate Talos config
Make sure you're got the Sops Age private key. 
Inside the talos folder, generate the talos config using the command `talhelper genconfig -s secret.sops.yaml`

## Add a new machine to the cluster
`talosctl apply-config -i -f clusterconfig/talos-proxmox-cluster-XXX.yaml -n 192.168.100.XXX`

## Get the kubeconfig file
`talosctl kubeconfig -e 192.168.100.210 -n 192.168.100.210 --talosconfig=./clusterconfig/talosconfig`