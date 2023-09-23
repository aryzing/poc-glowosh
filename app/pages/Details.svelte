<script lang="ts">
  import { Flick } from "../services/flick";
  export let flickId;
  let flick = Flick.getInstance().getFlickById(flickId);
</script>

<page>
  {#if flick}
    <actionBar title={flick.title} />

    <scrollView>
      <stackLayout>
        <image margin="0" stretch="aspectFill" src={flick.image} />
        <stackLayout padding="10 20">
          {#each flick.details as details}
            <stackLayout>
              <label
                marginTop="15"
                fontSize="16"
                fontWeight="700"
                class="text-primary"
                textWrap="true"
                text={details.title}
              />
              <label
                fontSize="14"
                class="text-secondary"
                textWrap="true"
                text={details.body}
              />
            </stackLayout>
          {/each}
        </stackLayout>
      </stackLayout>
    </scrollView>
  {:else}
    <actionBar title="Movie not found" />
  {/if}
</page>
