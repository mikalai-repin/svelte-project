<script>
  import TextInput from './TextInput.svelte';
  import { controlTypes } from '../core/models/constants';
  import Button from './Button.svelte';

  let title = '';
  let description = '';
  let subtitle = '';
  let address = '';
  let imageURL = '';
  let email = '';

</script>


<form on:submit|preventDefault>
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
      label="Address"
      inputType="text"
      value="{imageURL}"
      on:input={event => imageURL = event.target.value}
  />
  <TextInput
      id="email"
      label="Email"
      inputType="email"
      value="{email}"
      on:input={event => email = event.target.value}
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
