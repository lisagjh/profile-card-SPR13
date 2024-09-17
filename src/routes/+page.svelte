<script>
  export let data;

  console.log(data.person.custom);
</script>

<main>
  <h1>{data.person.name}</h1>

  <picture>
    <source
      srcset="{data.person.avatar}?format=avif"
      type="image/avif"
      width="145"
    />
    <source
      srcset="{data.person.avatar}?format=webp"
      type="image/webp"
      width="145"
    />
    <img src={data.person.avatar} width="145" alt={data.person.name} />
  </picture>

  <section class="about">
    <h2>About</h2>
    <p>{data.person.bio}</p>
  </section>

  <section class="skills">
    <h2>Skills</h2>
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
    --four: hsl(284, 24%, 36%);

    --spacing-one: 0.8rem;
    --spacing-two: 0.4rem;
    --spacing-three: 1.2rem;
    --spacing-four: 0.2rem;

    --radius: 0.5rem;
  }

  main {
    background-image: url(/src/lib/gradient.svg);
    background-size: 500%;
    background-position: left bottom;
    background-repeat: no-repeat;
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
    font-family: "Editorial regular";
    font-size: 22px;
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

  picture {
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
    width: 100%;
    min-width: 16.5rem;
    max-width: 23rem;
    background-color: var(--primary);
    padding: var(--spacing-one);
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
    background-color: var(--four);
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

  /* ik gebruik hier "--w" om de width te zetten, zodat ik later bij de animatie een herbruikbare animatie kan gebruiken ipv voor 3 verschillende widths te moeten maken */
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
      animation: background 10s ease-in-out infinite alternate;
    }

    @keyframes background {
      0% {
        background-position: left bottom;
      }
      10% {
        background-position: right center;
      }
      50% {
        background-position: right top;
      }
      65% {
        background-position: left top;
      }
      80% {
        background-position: left center;
      }
      100% {
        background-position: left bottom;
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
