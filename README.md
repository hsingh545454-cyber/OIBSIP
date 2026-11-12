<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Brinely – Fermentation kits for home kitchens</title>
<meta name="description" content="Brinely ships everything you need to make sauerkraut, kimchi and pickles at home.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:opsz,wght@12..96,500;12..96,700;12..96,800&family=Instrument+Sans:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --beet: #3F1637;
    --beet-soft: #6B4663;
    --brine: #E4EEC0;
    --leaf: #2E6B3C;
    --leaf-dark: #1F4D2A;
    --blush: #F2557E;
    --paper: #FBFDF3;

    --font-head: "Bricolage Grotesque", "Trebuchet MS", system-ui, sans-serif;
    --font-body: "Instrument Sans", system-ui, -apple-system, "Segoe UI", sans-serif;

    --fs-body: 1.0625rem;
    --fs-lead: clamp(1.125rem, 1rem + .6vw, 1.375rem);
    --fs-h1: clamp(2.5rem, 1.4rem + 5vw, 5rem);
    --fs-h2: clamp(1.875rem, 1.3rem + 2.4vw, 3rem);
    --fs-h3: 1.375rem;

    --space: clamp(1.25rem, 4vw, 2rem);
    --section-y: clamp(3.5rem, 9vw, 7rem);
    --radius: 1.25rem;
    --max: 72rem;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  html { scroll-behavior: smooth; scroll-padding-top: 5rem; }
  body {
    font-family: var(--font-body);
    font-size: var(--fs-body);
    line-height: 1.65;
    color: var(--beet);
    background: var(--brine);
    -webkit-font-smoothing: antialiased;
  }
  img, svg { display: block; max-width: 100%; }
  a { color: inherit; }
  :focus-visible { outline: 3px solid var(--blush); outline-offset: 3px; border-radius: 4px; }
  @media (prefers-reduced-motion: reduce) { html { scroll-behavior: auto; } * { transition: none !important; } }

  h1, h2, h3 { font-family: var(--font-head); line-height: 1.08; letter-spacing: -0.02em; }
  h1 { font-size: var(--fs-h1); font-weight: 800; }
  h2 { font-size: var(--fs-h2); font-weight: 700; }
  h3 { font-size: var(--fs-h3); font-weight: 700; line-height: 1.2; }

  .wrap { width: 100%; max-width: var(--max); margin-inline: auto; padding-inline: var(--space); }
  section { padding-block: var(--section-y); }

  .btn {
    display: inline-block;
    padding: .95rem 1.75rem;
    border-radius: 999px;
    background: var(--blush);
    color: #fff;
    font-weight: 600;
    text-decoration: none;
    border: 2px solid var(--blush);
    transition: background .2s, color .2s, transform .2s;
  }
  .btn:hover { background: var(--beet); border-color: var(--beet); }
  .btn.ghost { background: transparent; color: var(--beet); border-color: var(--beet); }
  .btn.ghost:hover { background: var(--beet); color: var(--brine); }

  /* Navigation */
  .nav {
    position: sticky; top: 0; z-index: 10;
    background: var(--paper);
    border-bottom: 2px solid var(--beet);
  }
  .nav .wrap {
    display: flex; flex-wrap: wrap; align-items: center; justify-content: space-between;
    gap: .5rem 1.5rem;
    padding-block: .85rem;
  }
  .logo { font-family: var(--font-head); font-weight: 800; font-size: 1.5rem; text-decoration: none; letter-spacing: -0.03em; }
  .logo span { color: var(--blush); }
  .nav ul { list-style: none; display: flex; flex-wrap: wrap; gap: .25rem 1.5rem; align-items: center; }
  .nav a.link { text-decoration: none; font-weight: 500; padding: .25rem 0; border-bottom: 2px solid transparent; }
  .nav a.link:hover { border-color: var(--blush); }
  .nav .btn { padding: .55rem 1.2rem; font-size: .95rem; }

  /* Hero */
  .hero { padding-block: clamp(3rem, 8vw, 6rem); }
  .hero .wrap { display: grid; gap: 3rem; align-items: center; grid-template-columns: 1.15fr .85fr; }
  .hero p.lead { font-size: var(--fs-lead); color: var(--beet-soft); max-width: 34rem; margin-block: 1.5rem 2rem; }
  .hero .actions { display: flex; flex-wrap: wrap; gap: 1rem; }
  .hero .note { margin-top: 1.25rem; font-size: .95rem; color: var(--beet-soft); }

  .jar-card {
    background: var(--leaf);
    border: 2px solid var(--beet);
    border-radius: 2rem;
    padding: 2.5rem 1.5rem 1.5rem;
    box-shadow: 8px 8px 0 var(--beet);
  }
  .jar-card svg { width: 100%; max-width: 20rem; margin-inline: auto; height: auto; }
  .jar-card figcaption { margin-top: 1rem; color: var(--paper); font-weight: 500; text-align: center; }

  /* Features */
  .section-head { max-width: 40rem; margin-bottom: 3rem; }
  .section-head p { margin-top: 1rem; color: var(--beet-soft); font-size: var(--fs-lead); }
  .features-grid { display: grid; gap: 1.5rem; grid-template-columns: repeat(auto-fit, minmax(15rem, 1fr)); }
  .feature {
    background: var(--paper);
    border: 2px solid var(--beet);
    border-radius: var(--radius);
    padding: 1.75rem;
  }
  .feature .icon {
    width: 3rem; height: 3rem; border-radius: 50%;
    display: grid; place-items: center;
    font-size: 1.4rem; margin-bottom: 1.25rem;
    background: var(--brine); border: 2px solid var(--beet);
  }
  .feature p { margin-top: .6rem; color: var(--beet-soft); }

  /* How it works */
  .steps-sec { background: var(--beet); color: var(--paper); }
  .steps-sec .section-head p { color: #D9C3D3; }
  .steps { list-style: none; counter-reset: step; display: grid; gap: 1.5rem; grid-template-columns: repeat(auto-fit, minmax(14rem, 1fr)); }
  .steps li { counter-increment: step; border-top: 3px solid var(--blush); padding-top: 1.25rem; }
  .steps li::before {
    content: "Day " counter(step, decimal);
    display: inline-block; margin-bottom: .75rem;
    font-family: var(--font-head); font-weight: 700; color: var(--brine);
  }
  .steps li:nth-child(2)::before { content: "Day 2–10"; }
  .steps li:nth-child(3)::before { content: "Day 11"; }
  .steps li:nth-child(4)::before { content: "Day 12+"; }
  .steps h3 { margin-bottom: .5rem; }
  .steps p { color: #D9C3D3; }

  /* Testimonials */
  .quotes { display: grid; gap: 1.5rem; grid-template-columns: repeat(auto-fit, minmax(17rem, 1fr)); }
  .quote {
    background: var(--paper); border: 2px solid var(--beet); border-radius: var(--radius);
    padding: 1.75rem; display: flex; flex-direction: column; justify-content: space-between; gap: 1.5rem;
  }
  .quote:nth-child(2) { background: var(--blush); color: #fff; }
  .quote:nth-child(2) .who span { color: #FFE3EA; }
  .quote blockquote { font-family: var(--font-head); font-size: 1.25rem; line-height: 1.35; font-weight: 500; }
  .who { font-weight: 600; }
  .who span { display: block; font-weight: 400; font-size: .95rem; color: var(--beet-soft); }

  /* Call to action */
  .cta { padding-top: 0; }
  .cta .box {
    background: var(--leaf); color: var(--paper);
    border: 2px solid var(--beet); border-radius: 2rem;
    padding: clamp(2rem, 6vw, 4rem);
    display: flex; flex-wrap: wrap; align-items: center; justify-content: space-between; gap: 1.5rem 3rem;
  }
  .cta h2 { max-width: 32rem; }
  .cta .btn { background: var(--paper); color: var(--beet); border-color: var(--paper); }
  .cta .btn:hover { background: var(--beet); color: var(--paper); border-color: var(--beet); }

  /* Footer */
  footer { background: var(--paper); border-top: 2px solid var(--beet); padding-block: 3rem 2rem; font-size: .975rem; }
  .foot-grid { display: grid; gap: 2rem; grid-template-columns: 1.5fr 1fr 1fr; }
  footer h3 { font-size: 1rem; margin-bottom: .75rem; }
  footer ul { list-style: none; display: grid; gap: .4rem; }
  footer a { text-decoration: none; color: var(--beet-soft); }
  footer a:hover { color: var(--blush); text-decoration: underline; }
  footer p { color: var(--beet-soft); max-width: 22rem; margin-top: .75rem; }
  .legal { margin-top: 2.5rem; padding-top: 1.25rem; border-top: 1px solid var(--beet-soft); color: var(--beet-soft); font-size: .9rem; }

  /* Responsive */
  @media (max-width: 52rem) {
    .hero .wrap { grid-template-columns: 1fr; }
    .jar-card { max-width: 24rem; }
    .foot-grid { grid-template-columns: 1fr 1fr; }
    .foot-grid > :first-child { grid-column: 1 / -1; }
  }
  @media (max-width: 34rem) {
    .nav .wrap { justify-content: center; }
    .nav ul { justify-content: center; gap: .25rem 1.1rem; }
    .btn { width: 100%; text-align: center; }
    .nav .btn { width: auto; }
    .foot-grid { grid-template-columns: 1fr; }
    .jar-card { box-shadow: 5px 5px 0 var(--beet); }
  }
</style>
</head>
<body>

<header class="nav">
  <div class="wrap">
    <a class="logo" href="#top">Brinely<span>.</span></a>
    <nav aria-label="Main">
      <ul>
        <li><a class="link" href="#features">Why Brinely</a></li>
        <li><a class="link" href="#how">How it works</a></li>
        <li><a class="link" href="#reviews">Reviews</a></li>
        <li><a class="btn" href="#start">Get a kit</a></li>
      </ul>
    </nav>
  </div>
</header>

<main id="top">

  <!-- Hero -->
  <section class="hero">
    <div class="wrap">
      <div>
        <h1>Make your own sauerkraut, kimchi and pickles.</h1>
        <p class="lead">Brinely kits include the jar, the weights, the salt and the instructions. You bring the cabbage.</p>
        <div class="actions">
          <a class="btn" href="#start">Order the starter kit</a>
          <a class="btn ghost" href="#how">See how it works</a>
        </div>
        <p class="note">Ships free over $40. 30-day money-back guarantee.</p>
      </div>

      <figure class="jar-card">
        <svg viewBox="0 0 200 240" role="img" aria-label="Illustration of a jar of fermenting vegetables">
          <rect x="62" y="14" width="76" height="26" rx="6" fill="#F2557E" stroke="#3F1637" stroke-width="4"/>
          <path d="M54 40h92v18c18 10 24 24 24 44v94a26 26 0 0 1-26 26H56a26 26 0 0 1-26-26v-94c0-20 6-34 24-44z" fill="#FBFDF3" stroke="#3F1637" stroke-width="4"/>
          <path d="M34 112h132v82a22 22 0 0 1-22 22H56a22 22 0 0 1-22-22z" fill="#E4EEC0"/>
          <circle cx="68" cy="140" r="14" fill="#F2557E" stroke="#3F1637" stroke-width="3"/>
          <circle cx="112" cy="156" r="16" fill="#2E6B3C" stroke="#3F1637" stroke-width="3"/>
          <circle cx="90" cy="190" r="12" fill="#F2557E" stroke="#3F1637" stroke-width="3"/>
          <circle cx="136" cy="196" r="10" fill="#2E6B3C" stroke="#3F1637" stroke-width="3"/>
          <circle cx="60" cy="184" r="6" fill="#FBFDF3" stroke="#3F1637" stroke-width="3"/>
          <circle cx="124" cy="126" r="5" fill="#FBFDF3" stroke="#3F1637" stroke-width="3"/>
          <path d="M34 112h132" stroke="#3F1637" stroke-width="4"/>
        </svg>
        <figcaption>Day 6: bubbling nicely.</figcaption>
      </figure>
    </div>
  </section>

  <!-- Features -->
  <section id="features">
    <div class="wrap">
      <div class="section-head">
        <h2>Everything you need, nothing you don't.</h2>
        <p>Fermenting is simple once the equipment is right. We sorted that part for you.</p>
      </div>
      <div class="features-grid">
        <article class="feature">
          <div class="icon" aria-hidden="true">🫙</div>
          <h3>Airlock lids</h3>
          <p>Gas escapes, air stays out. No daily burping and no mould.</p>
        </article>
        <article class="feature">
          <div class="icon" aria-hidden="true">⚖️</div>
          <h3>Glass weights</h3>
          <p>Keep vegetables under the brine, where they stay safe and crunchy.</p>
        </article>
        <article class="feature">
          <div class="icon" aria-hidden="true">🧂</div>
          <h3>Pre-measured salt</h3>
          <p>Packets sized for each recipe, so the ratio is right the first time.</p>
        </article>
        <article class="feature">
          <div class="icon" aria-hidden="true">📖</div>
          <h3>Twelve recipes</h3>
          <p>Printed cards from classic sauerkraut to spicy radish kimchi.</p>
        </article>
      </div>
    </div>
  </section>

  <!-- How it works -->
  <section class="steps-sec" id="how">
    <div class="wrap">
      <div class="section-head">
        <h2>From cabbage to jar in four steps.</h2>
        <p>Most of the work is waiting.</p>
      </div>
      <ol class="steps">
        <li>
          <h3>Chop and salt</h3>
          <p>Slice your vegetables, mix in a salt packet and massage until they release liquid.</p>
        </li>
        <li>
          <h3>Pack and seal</h3>
          <p>Press everything into the jar, add a weight and fit the airlock lid.</p>
        </li>
        <li>
          <h3>Taste</h3>
          <p>Around day 7 to 10, open it and try a forkful. Sour enough? Move to the fridge.</p>
        </li>
        <li>
          <h3>Enjoy</h3>
          <p>Eat it straight, pile it on sandwiches or stir it into soup. It keeps for months.</p>
        </li>
      </ol>
    </div>
  </section>

  <!-- Testimonials -->
  <section id="reviews">
    <div class="wrap">
      <div class="section-head">
        <h2>Home cooks are hooked.</h2>
      </div>
      <div class="quotes">
        <figure class="quote">
          <blockquote>“My first batch of kimchi was better than the jar I used to buy.”</blockquote>
          <figcaption class="who">Priya S.<span>Brinely customer since March</span></figcaption>
        </figure>
        <figure class="quote">
          <blockquote>“The weights alone are worth it. No more floating cabbage.”</blockquote>
          <figcaption class="who">Marcus T.<span>Home cook, Leeds</span></figcaption>
        </figure>
        <figure class="quote">
          <blockquote>“I gave one as a gift and my sister has already ordered a second.”</blockquote>
          <figcaption class="who">Hana L.<span>Brinely customer since June</span></figcaption>
        </figure>
      </div>
    </div>
  </section>

  <!-- CTA -->
  <section class="cta" id="start">
    <div class="wrap">
      <div class="box">
        <h2>Start your first batch this weekend.</h2>
        <a class="btn" href="#start">Order the starter kit</a>
      </div>
    </div>
  </section>
</main>

<footer>
  <div class="wrap">
    <div class="foot-grid">
      <div>
        <a class="logo" href="#top">Brinely<span>.</span></a>
        <p>Fermentation kits for home kitchens. Made in small batches.</p>
      </div>
      <div>
        <h3>Contact</h3>
        <ul>
          <li><a href="mailto:hello@brinely.example">hello@brinely.example</a></li>
          <li><a href="tel:+10000000000">+1 (000) 000-0000</a></li>
          <li>123 Placeholder Street</li>
        </ul>
      </div>
      <div>
        <h3>Follow</h3>
        <ul>
          <li><a href="#">Instagram</a></li>
          <li><a href="#">TikTok</a></li>
          <li><a href="#">YouTube</a></li>
        </ul>
      </div>
    </div>
    <p class="legal">© 2026 Brinely. All rights reserved. Placeholder brand for a design exercise.</p>
  </div>
</footer>

</body>
</html>
