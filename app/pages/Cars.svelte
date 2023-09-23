<script lang="ts">
  import { navigate } from "svelte-native";
  import Home from "./Home.svelte";
  import { Template } from "svelte-native/components";
  import History from "./History.svelte";
  import Profile from "./Profile.svelte";
  import CarDetails from "./CarDetails.svelte";

  let cars = [
    { id: "opel-mokka", src: "", name: "Opel Mokka" },
    { id: "tesla-model-3", src: "", name: "Tesla Model 3" },
    { id: "mini-cooper", src: "", name: "Mini Cooper" },
    { id: "rivian-r1t", src: "", name: "Rivian R1T" },
  ];

  function onCarTap(e) {
    navigate({
      page: CarDetails,
      props: { carId: cars[e.index].id },
    });
  }
</script>

<page>
  <actionBar title="Cars" />

  <flexboxLayout flexDirection="column">
    <flexboxLayout flexGrow={1} flexDirection="column">
      <flexboxLayout flexDirection="column">
        <listView items={cars} on:itemTap={onCarTap}>
          <Template let:item>
            <label text={item.name} fontSize="16" />
          </Template>
        </listView>

        <button text="Add a car" />
      </flexboxLayout>
    </flexboxLayout>
    <flexboxLayout>
      <button
        text="Home"
        on:tap={() => navigate({ page: Home })}
        class="nav-item"
      />
      <button
        text="Cars"
        on:tap={() => {
          /* nothing */
        }}
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
  .nav-item {
    flex-basis: 0;
    flex-grow: 1;
  }
</style>
