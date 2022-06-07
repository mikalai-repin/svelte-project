<script>
  import { createEventDispatcher } from 'svelte';
  import { controlTypes } from '../core/models/constants';
  import TextInput from './TextInput.svelte';
  import Button from './Button.svelte';

  const dispatch = createEventDispatcher();

  let title = '';
  let description = '';
  let subtitle = '';
  let address = '';
  let imageUrl = '';
  let contactEmail = '';

  function addMeetup() {
    dispatch('updateMeetups', {
      title,
      description,
      subtitle,
      address,
      imageUrl,
      contactEmail
    });
    updateValues();
  }

  function updateValues() {
    title = description = subtitle = address = imageUrl = contactEmail = '';
  }

</script>


<form on:submit|preventDefault={addMeetup}>
  <TextInput
      id="title"
      label="Title"
      inputType="text"
      value="{title}"
      on:input={event => title = event.target.value}
  />
  <TextInput
      id="subtitle"
      label="Subtitle"
      inputType="text"
      value="{subtitle}"
      on:input={event => subtitle = event.target.value}
  />
  <TextInput
      id="address"
      label="Address"
      inputType="text"
      value="{address}"
      on:input={event => address = event.target.value}
  />
  <TextInput
      id="imageURL"
      label="Image URL"
      inputType="text"
      value="{imageUrl}"
      on:input={event => imageUrl = event.target.value}
  />
  <TextInput
      id="email"
      label="Email"
      inputType="email"
      value="{contactEmail}"
      on:input={event => contactEmail = event.target.value}
  />
  <TextInput
      id="description"
      label="Description"
      controlType="{controlTypes.textarea}"
      value="{description}"
      rows="3"
      on:input={event => description = event.target.value}
  />
  <Button type="submit" action="Save"/>
</form>
