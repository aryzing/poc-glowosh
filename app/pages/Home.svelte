<script lang="ts">
  import { navigate } from "svelte-native";
  import Cars from "./Cars.svelte";
  import History from "./History.svelte";
  import Profile from "./Profile.svelte";
</script>

<page>
  <actionBar title="Home" />

  <flexboxLayout flexDirection="column">
    <scrollView flexGrow={1}>
      <flexboxLayout class="container">
        <stackLayout class="card">
          <label text="Upcoming wash" class="title" />
          <label
            text="Tesla Model 3 on 2023-10-15 with Marco"
            class="message"
          />
          <flexboxLayout style="justify-content: space-between;">
            <button text="View" />
            <button text="Reschedule" />
          </flexboxLayout>
        </stackLayout>
        <stackLayout class="separator" />
        <stackLayout class="card">
          <label text="Upcoming wash" class="title" />
          <label text="Opel Mokka on 2023-10-20 with Jeni" class="message" />
          <flexboxLayout style="justify-content: space-between;">
            <button text="View" />
            <button text="Reschedule" />
          </flexboxLayout>
        </stackLayout>
        <stackLayout class="separator" />
        <button text="Invite a friend, get a free wash!" />
      </flexboxLayout>
    </scrollView>
    <flexboxLayout>
      <button
        text="Home"
        on:tap={() => {
          /* nothing */
        }}
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
        on:tap={() => navigate({ page: Profile })}
        class="nav-item"
      />
    </flexboxLayout>
  </flexboxLayout>
</page>

<style>
  .container {
    padding: 16;
    flex-direction: column;
  }
  .card {
    background-color: rgb(240, 240, 240);
    border-radius: 4;
    padding: 8;
  }
  .separator {
    height: 16;
  }
  .title {
    font-size: 20;
  }
  .message {
    font-size: 15;
  }
  .nav-item {
    flex-basis: 0;
    flex-grow: 1;
  }
</style>
