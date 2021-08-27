<script lang="ts">
  import Group from '../Group.svelte';
  import Technology from "../Technology.svelte";
  
  export let name: string = "";
  export let icon: string;
</script>

<Group {name} {icon}>
  <Technology
    moreClass="absolute"
    position="top"
    active={true}
    name="GitHub"
    icon="control/git.svg"
  />
  <Technology
    moreClass="absolute"
    position="top-right"
    active={true}
    name="GitLab"
    icon="control/gitlab.svg"
  />
  <Technology
    moreClass="absolute"
    position="right"
    active={false}
    name="BitBucket"
    icon="control/bitbucket.svg"
  />
  <Technology
    moreClass="absolute"
    position="bottom-right"
    active={true}
    name="Azure DevOps"
    icon="control/azuredevops.svg"
  />
  <Technology
    moreClass="absolute"
    position="bottom"
    active={true}
    name="SubVersioN"
    icon="control/svn.svg"
  />
</Group>