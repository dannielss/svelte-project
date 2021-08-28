<script>
  import Header from './UI/Header.svelte';
  import MeetupGrid from './Meetups/MeetupGrid.svelte';

  const meetups = [
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
</script>

<style>
  main {
    margin-top: 5rem;
    padding-bottom: 1rem;
  }
</style>

<Header />

<main>
  <MeetupGrid {meetups} />
</main>


