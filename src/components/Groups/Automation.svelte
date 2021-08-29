<script lang="ts">
  import Group from '../Group.svelte';
  import Technology from "../Technology.svelte";
  
  export let name: string = "";
  export let icon: string;
  export let links: boolean[] = [false, false, false, false];
  export let linkHeight: number = 9.37;
</script>

<Group {name} {icon} {links} {linkHeight}>
  <Technology
    moreClass="absolute"
    position="top"
    active={false}
    name="Kubernetes"
    icon="automation/kubernetes.svg"
    repository="kubernetes/kubernetes"
  />

  <Technology
    moreClass="absolute"
    position="top-right"
    active={true}
    name="Docker"
    icon="automation/docker.svg"
    repository="docker/compose"
  />

  <Technology
    moreClass="absolute"
    position="right"
    active={false}
    name="SaltStack"
    icon="automation/saltstack.svg"
  />

  <Technology
    moreClass="absolute"
    position="bottom-right"
    active={true}
    name="Ansible"
    icon="automation/ansible.svg"
    repository="ansible/ansible"
  />

  <Technology
    moreClass="absolute"
    position="bottom"
    active={false}
    name="Puppet"
    icon="automation/puppet.svg"
    repository="puppetlabs/puppet"
  />

  <Technology
    moreClass="absolute"
    position="bottom-left"
    active={true}
    name="Terraform"
    icon="automation/terraform.svg"
    repository="hashicorp/terraform"
  />

  <Technology
    moreClass="absolute"
    position="left"
    active={false}
    name="TravisCI"
    icon="automation/travisci.svg"
    repository="travis-ci/travis-ci"
  />

  <Technology
    moreClass="absolute"
    position="top-left"
    active={false}
    name="CircleCI"
    icon="automation/circleci.svg"
  />
</Group>