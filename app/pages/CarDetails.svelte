<script lang="ts">
  import { Flick } from "../services/flick";
  export let carId: string;

  let cars = [
    {
      id: "opel-mokka",
      src: "~/assets/car-opel.jpg",
      name: "Opel Mokka",
      plate: "AA 83 K2",
      year: "2023",
      vin: "GXQAFGHT342",
    },
    {
      id: "tesla-model-3",
      src: "~/assets/car-tesla-model-3.jpg",
      name: "Tesla Model 3",
      plate: "6834 LBX",
      year: "2023",
      vin: "SDHH356SDVF",
    },
    {
      id: "mini-cooper",
      src: "~/assets/car-mini-cooper.jpg",
      name: "Mini Cooper",
      plate: "3857 JCN",
      year: "2023",
      vin: "GDSGHB74FGS",
    },
    {
      id: "rivian-r1t",
      src: "~/assets/car-rivian-r1t.jpg",
      name: "Rivian R1T",
      plate: "YT D8 50",
      year: "2023",
      vin: "84JETG346664",
    },
  ];

  let car = cars.find((car) => car.id === carId);
</script>

<page>
  {#if car}
    <actionBar title={car.name} />

    <stackLayout>
      <image height="200" margin="0" stretch="aspectFill" src={car.src} />
      <stackLayout padding="10 20">
        <flexboxLayout flexDirection="column">
          <flexboxLayout justifyContent="space-between">
            <label text="Plate" />
            <label text={car.plate} />
          </flexboxLayout>
          <flexboxLayout justifyContent="space-between">
            <label text="Year" />
            <label text={car.year} />
          </flexboxLayout>
          <flexboxLayout justifyContent="space-between">
            <label text="VIN" />
            <label text={car.vin} />
          </flexboxLayout>
          <flexboxLayout justifyContent="center" marginTop="50">
            <label text="✔️ Glowosh Insured" />
          </flexboxLayout>
        </flexboxLayout>
      </stackLayout>
    </stackLayout>
  {:else}
    <actionBar title="Car not found" />
  {/if}
</page>

<style>
  label {
    font-size: 20;
  }
</style>
