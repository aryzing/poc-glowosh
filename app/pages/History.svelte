<script lang="ts">
  import { navigate } from "svelte-native";
  import Home from "./Home.svelte";
  import Cars from "./Cars.svelte";
  import Profile from "./Profile.svelte";
</script>

<page>
  <actionBar title="History" />

  <flexboxLayout flexDirection="column">
    <flexboxLayout flexGrow={1} flexDirection="column">
      <label
        text="Soon you'll be able to see your car wash history here."
        fontSize="18"
        padding="16"
        textWrap="true"
      />
    </flexboxLayout>

    <flexboxLayout>
      <button
        text="Home"
        on:tap={() => navigate({ page: Home })}
        class="nav-item"
      />
      <button
        text="Cars"
        on:tap={() => navigate({ page: Cars })}
        class="nav-item"
      />
      <button
        text="History"
        on:tap={() => {
          // navigate({ page: Home })
        }}
        class="nav-item"
      />
      <button
        text="Profile"
        on:tap={() => navigate({ page: Profile })}
        class="nav-item"
      />
    </flexboxLayout>
  </flexboxLayout>
</page>
