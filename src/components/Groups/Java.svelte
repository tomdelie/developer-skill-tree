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
    active={false}
    name="Hibernate"
    icon="java/hibernate.svg"
  />

  <Technology
    moreClass="absolute"
    position="top-right"
    active={false}
    name="Spring"
    icon="java/spring.svg"
    repository="spring-projects/spring-framework"
  />

  <Technology
    moreClass="absolute"
    position="right"
    active={false}
    name="Hadoop"
    icon="java/hadoop.png"
    repository="apache/hadoop"
  />

  <Technology
    moreClass="absolute"
    position="bottom-right"
    active={false}
    name="Dropwizard"
    icon="java/dropwizard.png"
    repository="dropwizard/dropwizard"
  />

  <Technology
    moreClass="absolute"
    position="bottom"
    active={false}
    name="Spark"
    icon="java/spark.svg"
    repository="apache/spark"
  />
</Group>