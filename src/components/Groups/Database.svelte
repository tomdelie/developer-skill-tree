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
    name="MySQL"
    icon="database/mysql.svg"
    repository="mysql/mysql-server"
  />

  <Technology
    moreClass="absolute"
    position="top-right"
    active={true}
    name="MariaDB"
    icon="database/mariadb.svg"
    repository="MariaDB/server"
  />

  <Technology
    moreClass="absolute"
    position="right"
    active={false}
    name="Oracle"
    icon="database/oracle.svg"
  />

  <Technology
    moreClass="absolute"
    position="bottom-right"
    active={true}
    name="PostgreSQL"
    icon="database/postgresql.svg"
  />

  <Technology
    moreClass="absolute"
    position="bottom"
    active={true}
    name="MongoDB"
    icon="database/mongodb.svg"
    repository="mongodb/mongo"
  />

  <Technology
    moreClass="absolute"
    position="bottom-left"
    active={false}
    name="Couchbase"
    icon="database/couchbase.svg"
  />

  <Technology
    moreClass="absolute"
    position="left"
    active={false}
    name="RavenDB"
    icon="database/ravendb.png"
    repository="ravendb/ravendb"
  />

  <Technology
    moreClass="absolute"
    position="top-left"
    active={true}
    name="Redis"
    icon="database/redis.svg"
    repository="redis/redis"
  />
</Group>