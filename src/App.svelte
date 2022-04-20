<script>
  let belt = "Black";
  let first = "Jimi";
  let last = "Hendrix";

  let age = 12;

  const handleClick = () => {
    belt = "Orange";
  };

  const handleInput = (e) => {
    belt = e.target.value;
  };

  //   Reactive Value

  $: fullName = `${first} ${last}`;

  $: myage = age;

  //   Reactive Statements
</script>

<main>
  <!-- <h1>Hello {name}!</h1> -->
  <h2 style="color: {belt};">{fullName} {belt} Belt</h2>

  <p>{myage}</p>
  <!-- instead of doing this you can use bind -->
  <!-- <button on:click={handleClick}>Update Color</button> -->
  <!-- instead of doing this you can use bind -->

  <!-- <input
    type="text"
    name="Input Color"
    id=""
    on:input={handleInput}
    value={belt}
  /> -->

  <input type="text" name="Input Color" bind:value={belt} />
  <input type="text" name="Input First" bind:value={first} />
  <input type="text" name="Input First" bind:value={age} />

  <input type="text" name="Input Last" bind:value={last} />
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
