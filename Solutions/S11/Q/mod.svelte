<svelte:head>
    <title>Solution To Questions Of Section 11</title>
</svelte:head>

<script>
    import Greeting from './Greeting.svelte';
    import CounterSummery from './CounterSummery.svelte';
    import UserInfo from './UserInfo.svelte';
    import Box from './Box.svelte';
    import Todo from './TodoList.svelte';
    import Card from './Card.svelte';
    import Tag from './Tag.svelte';
    import SourceImage from './ImageButton.svelte';

    const todos = ['Wake Up Before 8', 'Drink Coffee', 'Study Before 10'];
    const blogInfo = {
      title: 'How To Master Debate',
      subtitle: 'A Guide For Budding Serial Owners',
      author: 'Brad Chucker',
    }
</script>

<Greeting name={'Satyam'}></Greeting>
<CounterSummery count={12}></CounterSummery>
<UserInfo isAdmin={false}></UserInfo>
<Box color={'Blue'}></Box>
<Todo todos={todos}></Todo>
<Card title={blogInfo.title} subtitle={blogInfo.subtitle} author={blogInfo.author}></Card>
<Tag highlighted={true}></Tag>
<SourceImage imageSrc={'/home/ynx/code/newAtten/code/assets/djubo-cropped.png'}></SourceImage>
