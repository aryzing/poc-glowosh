<script lang="ts">
  import { Flick } from "../services/flick";
  import { Template } from "svelte-native/components";
  import { navigate } from "svelte-native";
  import Details from "./Details.svelte";
  import { type ItemEventData } from "@nativescript/core";
  let flicks = Flick.getInstance().getFlicks();

  function onFlickTap(e: ItemEventData) {
    navigate({
      page: Details,
      props: { flickId: flicks[e.index].id },
    });
  }
</script>

<page>
  <actionBar title="NativeFlix Returns" />

  <stackLayout height="100%">
    <listView
      height="100%"
      separatorColor="transparent"
      items={flicks}
      on:itemTap={onFlickTap}
    >
      <Template let:item>
        <gridLayout
          height="280"
          borderRadius="10"
          class="bg-secondary"
          rows="*, auto, auto"
          columns="*"
          margin="5 10"
          padding="0"
        >
          <image row="0" margin="0" stretch="aspectFill" src={item.image} />
          <label
            row="1"
            margin="10 10 0 10"
            fontWeight="700"
            class="text-primary"
            fontSize="18"
            text={item.title}
          />
          <label
            row="2"
            margin="0 10 10 10"
            class="text-secondary"
            fontSize="14"
            textWrap="true"
            text={item.description}
          />
        </gridLayout>
      </Template>
    </listView>
  </stackLayout>
</page>
