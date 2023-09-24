<script lang="ts">
  import { navigate } from "svelte-native";
  import Home from "./Home.svelte";
  import Cars from "./Cars.svelte";
  import History from "./History.svelte";
</script>

<page>
  <actionBar title="Profile" />

  <flexboxLayout flexDirection="column">
    <flexboxLayout flexGrow={1} flexDirection="column">
      <flexboxLayout padding="24">
        <image
          margin="0"
          width="120"
          height="120"
          borderRadius="100%"
          src="~/assets/eduard.jpg"
        />
        <flexboxLayout flexDirection="column" paddingLeft="16">
          <label text="Eduard Bardají Puig" fontSize="20" />
          <label text="CTO Glowosh" fontSize="18" color="gray" />
        </flexboxLayout>
      </flexboxLayout>
      <button text="Invite a friend, get a free wash!" />
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
        on:tap={() => navigate({ page: History })}
        class="nav-item"
      />
      <button
        text="Profile"
        on:tap={() => {
          // do nothing
        }}
        class="nav-item"
      />
    </flexboxLayout>
  </flexboxLayout>
</page>
