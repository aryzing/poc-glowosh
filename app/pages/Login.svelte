<script lang="ts">
  import { navigate } from "svelte-native";
  import Home from "./Home.svelte";

  let username;
  let password;

  function onLoginButtonTap() {
    navigate({
      page: Home,
    });
  }
</script>

<page>
  <actionBar title="Login" />

  <flexboxLayout flexDirection="column" justifyContent="center">
    <textField bind:text={username} hint="Username" />
    <textField bind:text={password} secure="true" hint="Password" />
    <button text="Log in" on:tap={onLoginButtonTap} />
  </flexboxLayout>
</page>
