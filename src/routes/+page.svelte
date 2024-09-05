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
    --four: hsl(251, 56%, 68%);

    --spacing-one: 0.8rem;
    --spacing-two: 0.4rem;
    --spacing-three: 1.2rem;
    --spacing-four: 0.2rem;

    --radius: 0.5rem;
  }

  main {
    display: grid;
    justify-content: center;
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
    padding: var(--spacing-four);
  }

  h3 {
    font-size: 1rem;
    font-weight: 600;
    padding-left: var(--spacing-three);
  }

  p {
    padding: var(--spacing-four);
  }

  img {
    background-color: var(--tertiary);
    padding: var(--spacing-four);
    border-radius: 2px;
    grid-column: 5/12;
    grid-row: 3/5;
    align-self: self-start;
    justify-self: center;
    z-index: 10;
  }

  section {
    grid-column: 2/12;
    justify-self: center;
    min-width: 16.5rem;
    max-width: 23rem;
    background-color: var(--primary);
    padding: var(--spacing-two);
    border-radius: 4px;
  }

  .about {
    grid-row: 2/4;
  }

  .skills {
    display: grid;
    flex-direction: column;
    grid-row: 4/8;
  }

  .bar {
    display: flex;
    align-self: center;
    justify-self: center;
    background-color: var(--secondary);
    width: 90%;
    height: 2.2rem;
    --radius: 10px;
    border-radius: var(--radius);
    --i: 0.2rem;
    --ii: 0.3rem;
    padding: var(--i) var(--ii);
    margin-top: -0.9rem;
  }

  .bar div {
    height: 1.5rem;
    align-self: center;
    background-color: var(--tertiary);
    border-radius: calc(var(--radius) - var(--i));
  }

  .bar .html {
    --w: 80%;
    width: var(--w);
  }

  .bar .css {
    --w: 70%;
    width: var(--w);
  }

  .bar .js {
    --w: 45%;
    width: var(--w);
  }

  .skills p {
    margin: var(--spacing-one) 0;
  }

  @media (prefers-reduced-motion: no-preference) {
    main {
      background: linear-gradient(323deg, var(--tertiary), var(--secondary));
      background-size: 400% 400%;
	  background-position: bottom;
      animation: bg 20s ease infinite;
    }

    @keyframes bg {
      0% {
        background-position: 51% 0%;
      }
      50% {
        background-position: 10% 100%;
      }
      100% {
        background-position: 51% 0%;
      }
    }

    .bar > * {
      opacity: 0;
    }

    .bar div {
      animation: load 0.75s ease-out 0.25s forwards;
    }

    @keyframes load {
      from {
        opacity: 0.5;
        width: 1%;
      }
      to {
        opacity: 1;
        width: var(--w);
      }
    }
  }

  @media (prefers-reduced-motion) {
    .bar > * {
      opacity: 1;
    }
  }
</style>
