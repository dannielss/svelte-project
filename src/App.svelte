<script>
  import Header from './UI/Header.svelte';
  import MeetupGrid from './Meetups/MeetupGrid.svelte';
  import TextInput from './UI/TextInput.svelte';

  let meetup = {
    title: '',
    subtitle: '',
    imageUrl: '',
    address: '',
    contactEmail: '',
    description: ''
  };

  let meetups = [
    {
      id: 'm1',
      title: 'Coding Bootcamp',
      subtitle: 'Learn to code in 2 hours',
      description: 'In this meetup, we will have some experts that teach you how to code',
      imageUrl: 'https://upload.wikimedia.org/wikipedia/commons/6/6b/Meetup_Logo.png',
      address: '27th Nerd Road, 32523 New York',
      contactEmail: 'code@test.com'
    },
    {
      id: 'm2',
      title: 'Swim Together',
      subtitle: 'Let\'s go for swimming',
      description: 'We will simply swim some rounds!',
      imageUrl: 'https://upload.wikimedia.org/wikipedia/commons/6/6b/Meetup_Logo.png',
      address: '27th Nerd Road, 32523 New York',
      contactEmail: 'swim@test.com'
    }
  ]

  const addMeetup = () => {
    if(Object.values(meetup).some(item => item.trim() !== '')) {
      const newMeetup = {
        id: Math.random().toString(),
        ...meetup
      }

      meetups = [...meetups, newMeetup]
    }
  }

</script>

<style>
  main {
    margin-top: 5rem;
    padding-bottom: 1rem;
  }

  form {
    width: 30rem;
    max-width: 90%;
    margin: 0 auto;
  }
</style>

<Header />

<main>
  <form on:submit|preventDefault={addMeetup}>
    <TextInput 
        id="title" 
        label="Title" 
        value={meetup.title} 
        on:input={(e) => meetup.title = e.target.value} 
        type="text" />
      <TextInput 
        id="subtitle" 
        label="Subtitle" 
        value={meetup.subtitle} 
        on:input={(e) => meetup.subtitle = e.target.value} 
        type="text" />
      <TextInput 
        id="address" 
        label="Address" 
        value={meetup.address} 
        on:input={(e) => meetup.address = e.target.value} 
        type="text" />
      <TextInput 
        id="imageUrl" 
        label="Image URL" 
        value={meetup.imageUrl} 
        on:input={(e) => meetup.imageUrl = e.target.value} 
        type="text" />
      <TextInput 
        id="email" 
        label="E-mail" 
        value={meetup.contactEmail} 
        on:input={(e) => meetup.contactEmail = e.target.value} 
        type="email" />
      <TextInput 
        id="description" 
        label="Description" 
        value={meetup.description} 
        on:input={(e) => meetup.description = e.target.value} 
        controlType="textarea"
        rows="3"
      />
    <button type="submit">Save</button>
  </form>

  <MeetupGrid {meetups} />
</main>


