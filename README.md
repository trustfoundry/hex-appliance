# TrustFoundry test appliance

Downloads for the test appliance TrustFoundry uses for internal penetration
tests. Your TrustFoundry contact gives you an enrollment code; the appliance
uses it to connect to TrustFoundry, and nothing else needs configuring.

## Pick the download for your environment

The files are on the [Releases](../../releases) page.

| Your environment | Download | What to do |
|---|---|---|
| VMware ESXi, Workstation, Fusion, or VirtualBox | `.ova` | Import the OVA, attach it to the network being tested, start it, type the code at the console |
| Microsoft Hyper-V | `.vhdx.zip` | Unzip, create a Generation 1 VM using the VHDX, then as above |
| Proxmox, KVM, Nutanix | `.qcow2` | Import the disk into a new VM, then as above |
| A Linux host with Docker | the container image | `curl -fsSL https://github.com/trustfoundry/hex-appliance/releases/latest/download/install.sh \| sudo sh -s -- YOUR-CODE` |

The VM needs 2 CPUs, 4 GB of memory, and one network adapter on the network
being tested.

## What it does

- It only connects out: to TrustFoundry over HTTPS, and to our Tailscale
  network. Nothing on your network has to accept a connection from outside.
- It sends nothing to your hosts before the testing start date you agreed with
  us.
- When the engagement ends, TrustFoundry disconnects it and it says on the
  console that it can be deleted.

Each release lists SHA-256 checksums for its files.

Questions: ask your TrustFoundry project contact.
