# proposal-open-terrarium

- Feature Name: ceph-open-terrarium

https://github.com/MalloZup/ceph-open-terrarium

# Summary
[summary]: #summary

Ceph-open-terrarium deploy ceph cluster with terraform, provisioning with saltstack/ansible.

# Motivation
[motivation]: #motivation

This project claims to be a common/shared entrypoint for deploying CEPH.

The best places for this new repository would fit under the CEPH GitHub organisation upstream.

### Deployment:

The project use terraform-libvirt which i am co-maintaining and it is a SUSE opensource software. ( see https://github.com/dmacvicar/terraform-provider-libvirt).

The plugin itself it is already used by other project in SUSE internally (SUSE-Manager/Caasp teams) and by other DISTROs for their deployment (see openshift installer at GitHub)

Ceph-open-terrarium,  aims to deploy instance from upstream images (see supported systems) and  with minimal cloudinit modifications have a KVM instance. ( also using JEOS images)

This bring some advantages because we are not rebuilding custom images, but taking supported cloud images from free OS. 

The nature of the project is modular and generic:
  -  If we want to support the `openstack` backend we can support it easy in terraform. ( the same approach can be for other hypervisors.)
  
### Provisioning:

Since the project doesn't mix/couple  deployment and provisioning, there is space and freedom for community.

One could use saltstack or ansible.

With saltstack we prepare all vms for setting up the minion and salt-master for deepsea.

Ansible at moment is not implemented but community can implement it easy.
