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
    name="Kotlin"
    icon="mobile/kotlin.svg"
    repository="JetBrains/kotlin"
  />

  <Technology
    moreClass="absolute"
    position="top-right"
    active={false}
    name="Swift"
    icon="mobile/swift.svg"
    repository="apple/swift"
  />

  <Technology
    moreClass="absolute"
    position="right"
    active={false}
    name="Java"
    icon="mobile/java.svg"
  />

  <Technology
    moreClass="absolute"
    position="bottom-right"
    active={false}
    name="Objective-C"
    icon="mobile/objective-c.png"
  />

  <Technology
    moreClass="absolute"
    position="bottom"
    active={false}
    name="Flutter"
    icon="mobile/flutter.svg"
    repository="flutter/flutter"
  />

  <Technology
    moreClass="absolute"
    position="bottom-left"
    active={false}
    name="React Native"
    icon="mobile/react-native.svg"
    repository="facebook/react-native"
  />

  <Technology
    moreClass="absolute"
    position="left"
    active={false}
    name="Ionic"
    icon="mobile/ionic.svg"
    repository="ionic-team/ionic-framework"
  />

  <Technology
    moreClass="absolute"
    position="top-left"
    active={false}
    name="Xamarin"
    icon="mobile/xamarin.svg"
  />
</Group>