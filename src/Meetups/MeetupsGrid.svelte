<script>
  import MeetupItem from './MeetupItem.svelte';

  export let meetups;
</script>

<section class="meetups">
  {#each meetups as meetup (meetup.id)}
    <MeetupItem {...meetup}/>
  {/each}
</section>

<style>

  .meetups {
      width: 100%;
      display: grid;
      grid-template-columns: 1fr;
      grid-gap: 1rem;
  }

  @media (min-width: 768px) {
      .meetups {
          grid-template-columns: repeat(2, 1fr);
      }
  }

</style>
