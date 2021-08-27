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
    name="AWS"
    icon="provider/aws.svg"
  />

  <Technology
    moreClass="absolute"
    position="top-right"
    active={false}
    name="Google Cloud"
    icon="provider/googlecloud.svg"
  />

  <Technology
    moreClass="absolute"
    position="right"
    active={false}
    name="Azure"
    icon="provider/azure.svg"
  />

  <Technology
    moreClass="absolute"
    position="bottom-right"
    active={false}
    name="Oracle Cloud"
    icon="provider/oracle.svg"
  />

  <Technology
    moreClass="absolute"
    position="bottom"
    active={true}
    name="Digital Ocean"
    icon="provider/digitalocean.svg"
  />

  <Technology
    moreClass="absolute"
    position="bottom-left"
    active={false}
    name="Salesforce"
    icon="provider/salesforce.svg"
  />

  <Technology
    moreClass="absolute"
    position="left"
    active={false}
    name="OVH"
    icon="provider/ovh.svg"
  />
</Group>