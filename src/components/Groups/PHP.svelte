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
    name="CodeIgniter"
    icon="php/codeigniter.svg"
    repository="bcit-ci/CodeIgniter"
  />

  <Technology
    moreClass="absolute"
    position="top-right"
    active={true}
    name="Laravel"
    icon="php/laravel.svg"
    repository="laravel/laravel"
  />

  <Technology
    moreClass="absolute"
    position="right"
    active={false}
    name="Zend"
    icon="php/zend.svg"
    repository="zendframework/zendframework"
  />

  <Technology
    moreClass="absolute"
    position="bottom-right"
    active={false}
    name="CakePHP"
    icon="php/cakephp.svg"
    repository="cakephp/cakephp"
  />

  <Technology
    moreClass="absolute"
    position="bottom"
    active={true}
    name="Symfony"
    icon="php/symfony.svg"
    repository="symfony/symfony"
  />

  <Technology
    moreClass="absolute"
    position="bottom-left"
    active={false}
    name="Phalcon"
    icon="php/phalcon.png"
    repository="phalcon/cphalcon"
  />
</Group>