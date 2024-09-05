<script>
  /** @type {import('./$types').PageData} */
  export let data;
</script>

<main>
  <h1>{data.person.name}</h1>

  <img src={data.person.avatar} alt={data.person.name} width="145" />

  <section class="about">
    <h2>about</h2>
    <p>{data.person.bio}</p>
  </section>

  <section class="skills">
    <h2>skills</h2>
    <h3>HTML</h3>
    <div class="bar">
      <div class="html"></div>
    </div>

    <h3>CSS</h3>
    <div class="bar">
      <div class="css"></div>
    </div>

    <h3>JS</h3>
    <div class="bar">
      <div class="js"></div>
    </div>

    <p>
      I am currently improving my JS skills and learning to work with
      frameworks.
    </p>
  </section>
</main>

<style>
  :root {
    --primary: hsl(283, 20%, 93%);
    --secondary: hsl(0, 0%, 7%);
    --tertiary: hsl(283, 56%, 68%);

    --spacing-one: 0.8rem;
    --spacing-two: 0.4rem;
    --spacing-three: 1.2rem;
    --spacing-four: 0.2rem;

    --radius: 0.5rem;
  }

  main {
    display: grid;
    grid-template-columns: repeat(12, 1fr);
    grid-template-rows: repeat(8, 1fr);
    width: 100dvw;
    height: 100dvh;
    background-color: var(--secondary);
    gap: 1rem 0;
    padding-top: var(--spacing-three);
  }

  h1 {
    font-size: 3.5rem;
    font-family: "Editorial italic bold";
    letter-spacing: 0.45rem;
    color: var(--primary);
    grid-column: 1/13;
    grid-row: 1/2;
    align-self: flex-end;
    justify-self: center;
  }

  h2 {
    font-family: "Editorial italic";
    margin-bottom: var(--spacing-four);
  }

  h3 {
	font-size: 1rem;
	font-weight: 600;
	padding-left: var(--spacing-three);
  }

  p {
    width: 25ch;
	padding: 0 var(--spacing-one);
  }

  img {
    background-color: var(--tertiary);
    padding: var(--spacing-four);
    border-radius: 2px;
    grid-column: 6/12;
    grid-row: 3/5;
    align-self: self-start;
    justify-self: center;
    z-index: 10;
  }

  section {
    background-color: var(--primary);
    padding: var(--spacing-two);
    border-radius: 4px;
  }

  .about {
    grid-column: 2/12;
    grid-row: 2/4;
  }

  .skills {
	display: grid;
	flex-direction: column;
    grid-column: 2/12;
    grid-row: 4/7;
  }

  .bar {
    display: flex;
	justify-self: center;
    background-color: var(--secondary);
    width: 90%;
    height: 2.2rem;
    --radius: 10px;
    border-radius: var(--radius);
    --i: 0.2rem;
	--ii: 0.3rem;
    padding: var(--i) var(--ii);
  }

  .bar div {
    height: 1.5rem;
    align-self: center;
    background-color: var(--tertiary);
    border-radius: calc(var(--radius) - var(--i));
  }

  .bar .html {
    width: 85%;
  }

  .bar .css {
    width: 75%;
  }

  .bar .js {
    width: 45%;
  }

  .skills p {
    margin: var(--spacing-one) 0;
  }
</style>
