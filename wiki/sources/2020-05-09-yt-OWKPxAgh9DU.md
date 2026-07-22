---
type: youtube-video
source_date: 2020-05-09
url: https://www.youtube.com/watch?v=OWKPxAgh9DU
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [cloud-devops, networking]
tags: [ansible, network-automation, cisco, devnet, automation]
---

# get started with Ansible Network Automation (FREE cisco router lab)

## Summary

A hands-on tutorial where Chuck extends Ansible from server administration into
**network automation** — controlling Cisco routers and switches. It's a direct
follow-up to his prior Ansible video (which focused on Linux servers); here he
merges his two core domains: networking and automation. The pitch is that Ansible
is one of the more popular network-automation tools precisely *because* it requires
no programming knowledge — you don't need Python to start.

The workflow he demonstrates end to end:
1. **Install Ansible on CentOS** — `yum update`, install the EPEL release, then
   `yum install ansible`.
2. **Edit `ansible.cfg`** (in `/etc/ansible/`) to disable `host_key_checking` so it
   plays nicely with Cisco devices in a lab without SSH-key setup.
3. **Get free lab gear via Cisco DevNet** — use the always-on IOS XE sandbox routers
   that DevNet exposes freely, so viewers need no home lab. A free DevNet account is
   framed as effectively required for network automation.
4. **Define hosts + group vars** in the inventory/hosts file — group the routers and
   set the network-specific connection variables that differ from Linux boxes:
   `ansible_user`, `ansible_password`, `ansible_connection=network_cli`,
   `ansible_network_os=ios`, and `ansible_port=8181` (DevNet's non-default SSH port).
5. **Test connectivity** with the `ping` module, then run **ad-hoc IOS commands**
   with the `ios_command` module (e.g. `show ip interface brief`) against the whole
   group at once.
6. **Run a playbook** (`ansible-playbook devnet.yml`) with tasks using the
   `ios_banner` and `ios_interface` modules to set a login banner and add a loopback
   interface — then re-run it to demonstrate **idempotence**.
7. **Clean up** by flipping the task `state` from `present` to `absent`.

The recurring theme: idempotence beats copy-paste config. Ansible checks whether the
desired state already exists before changing anything; re-running the playbook does
nothing because the state is already present. Chuck closes by encouraging viewers to
try the lab themselves, and repeats his standing advice — you don't *have* to learn
programming to start, but you should still learn Python eventually.

## Key claims (dated — the concept + workflow)

All 2020-05-09, paraphrased unless quoted:

- Ansible can manage and configure hundreds of devices — Windows servers, Linux
  servers, and routers/switches — and is one of the more popular tools for network
  engineers because it requires no programming knowledge.
- Ansible for networking is attractive specifically because you don't need to know
  Python (or any programming) to start automating your network.
- Installing Ansible on CentOS: run `yum update`, install the EPEL release, then
  `yum install ansible`.
- You must disable `host_key_checking` (set it to `false`) in `ansible.cfg` so
  Ansible works with Cisco devices in a lab without uploading SSH keys.
- Cisco DevNet provides free, always-on sandbox routers (IOS XE), so viewers can do
  real network automation without owning any lab hardware.
- A free DevNet account is effectively required if you're getting into network
  automation.
- The key difference between managing Linux hosts and network devices is the
  connection variables: network devices need `ansible_connection=network_cli` and
  `ansible_network_os` (e.g. `ios`) so Ansible knows it's talking to a CLI-based
  network OS and which OS it is.
- `ansible_network_os` matters because the target could be Arista, IOS XR, etc. —
  Ansible has to be told what it's connecting to.
- DevNet's sandbox uses SSH port 8181 instead of the default 22, so
  `ansible_port=8181` must be set.
- The `ping` module confirms reachability (returns a "pong"); the `ios_command`
  module runs ad-hoc IOS commands like `show ip interface brief` across the whole
  group at once.
- Ad-hoc commands are fun but not the most powerful way to use Ansible — playbooks
  are. A playbook contains plays; a play targets a host group and runs tasks that use
  modules (small programs that apply configuration).
- The demo playbook uses the `ios_banner` module (to set the login banner) and the
  `ios_interface` module (to add loopback 21), each with a `state` of `present`.
- Ansible is idempotent: re-running the playbook changes nothing because it checks
  that the desired state is already present. This beats copy-pasting config, which
  re-applies every time without checking and can break some configurations.
- Setting a task's `state` to `absent` removes the configuration it previously added.
- Ansible's website lists all available modules; there are tons of examples, so you
  can truly start automating your network without learning programming — though you
  should still learn Python and the other tools (Puppet, Chef, SaltStack) over time.

## Notable verbatim quotes

> I love ansible it's by far one of my favorite IT automation tools we can use it to manage it configure hundreds of devices from Windows servers to Linux servers and even routers and switches.

> it's one of the more popular tools for networking engineers just because you don't need to know Python you don't need to know any of that.

> you don't need a lab in your own home there's stuff available for free thanks to Cisco dev net.

> if you're getting into Network automation this is almost required actually I'm gonna say it is required do it now.

> that sure beats copy and paste and config into a router because when you copy and paste it's gonna try and apply that config every time they won't check and see if it's there or not which could for some commands and some configurations really screw things up this is a lot cleaner a lot better.

> now you should learn Python you definitely need to you know how I feel about that but the point is you don't have to just start learning network automation now.

## Guest attribution

Solo — all statements attributable to Chuck Keith (the SUBJECT).
