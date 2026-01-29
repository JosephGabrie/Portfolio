<script lang="ts">
  import { fade, fly } from "svelte/transition";
  import bgTagHk from "$lib/assets/bg_tag_hk.png";
  import whiteBox from "$lib/assets/whiteBox.png";
  let activePage = $state("home");

  function showPage(page: string) {
    activePage = page;
    if (typeof window !== "undefined") {
      window.scrollTo({ top: 0, behavior: "smooth" });
    }
  }
</script>

<div class="deadlock-wrapper animate-ripple">
  <nav>
    <ul>
      <li class="links">
        <button
          class:active={activePage === "home"}
          onclick={() => showPage("home")}>HOME</button
        >
        <button
          class:active={activePage === "about"}
          onclick={() => showPage("about")}>ABOUT</button
        >
        <button
          class:active={activePage === "blog"}
          onclick={() => showPage("blog")}>BLOG</button
        >
        <button
          class:active={activePage === "resume"}
          onclick={() => showPage("resume")}>RESUME</button
        >
      </li>
    </ul>
  </nav>

  <!-- HOME PAGE -->
  {#if activePage === "home"}
    <div id="home" class="page active">
      <section class="hero">
        <div
          class="hero-content"
          in:fly={{ y: 50, duration: 2000, delay: 2500 }}
        >
          <h1>Joseph Gabrie</h1>
          <p class="subtitle">Developer</p>
        </div>
      </section>

      <section class="projects" id="projects">
        <h2 class="section-title">Projects</h2>
        <div class="feature-grid">
          <div class="feature-card">
            <div class="feature-number">01</div>
            <h3>Arthas AI</h3>
            <p>
              Harness the power of artificial intelligence. Connect your
              research papers and get insight in topics beyond your
              understanding.
            </p>
          </div>
          <div class="feature-card">
            <div class="feature-number">02</div>
            <h3>Expo authkit convex template</h3>
            <p>
              Fight through the hassle of setting up your convex+workOS+expo
              project with this template.
            </p>
          </div>
          <div class="feature-card">
            <div class="feature-number">03</div>
            <h3>BVH for game engines</h3>
            <p>
              implementation of a binary self-balancing Bounding Volume
              Hierarchy (BVH) inspired by the tree rotations in Fast, Effective
              BVH Updates for Animated Scenes.
            </p>
          </div>
          <div class="feature-card">
            <div class="feature-number">04</div>
            <h3>Your Dialysis</h3>
            <p>
              Software for Dialysis clinic that manages statistics, patient, and
              administration work. The software is paired with a mobile app to
              easily upload the patient info into the database.
            </p>
          </div>
        </div>
      </section>

      <section class="showcase">
        <div class="showcase-content">
          <div class="showcase-text">
            <h2>Let's work together</h2>
            <p>
              Send me a message on discord (my tag is pendragon2099) or send me
              an email at josephgabriemolina@gmail.com. We can develop anything
              and everything.
            </p>
          </div>
          <div class="showcase-visual"></div>
        </div>
      </section>
    </div>
  {/if}

  <!-- ABOUT PAGE -->
  {#if activePage === "about"}
    <div id="about" class="page active">
      <div class="about-container">
        <div
          class="about-hero"
          style="background-image: url({whiteBox}); background-size: 100% 100%; background-color: #3874ae; border: none; color: #3874ae;"
        >
          <div
            class="hero-with-image flex flex-col md:flex-row gap-8 items-center"
          >
            <div class="flex-1">
              <h1>ABOUT</h1>
              <p>
                Architect of digital experiences. Builder of impossible things.
                Champion of bold design and unapologetic creativity.
              </p>
            </div>
          </div>
        </div>

        <div
          class="about-section"
          style="background-image: url({bgTagHk}); background-size: 100% 100%; background-color: #ffac11; border: none; color: #ffac11;"
        >
          <div class="block about">
            <div
              class="
        asset-container mt-4 w-xs h-xs
        grayscale hover:grayscale-0 transition-all duration-500
        bg-center bg-cover bg-no-repeat
        flex flex-col items-center justify-center text-center p-4
      "
              style="background-image: url({bgTagHk})"
            >
              <h2
                class="text-white text-4xl font-bold tracking-tighter drop-shadow-lg"
              ></h2>
            </div>
          </div>

          <h2>WHO I AM</h2>
          <p>
            I exist at the intersection of design and code, where brutalist
            aesthetics meet functional innovation. My work challenges
            conventions, embraces bold choices, and refuses to blend into the
            background.
          </p>
          <p>
            Every project is a statement. Every line of code carries intention.
            I don't create websites—I build experiences that demand attention
            and refuse to be ignored.
          </p>
        </div>
        <div
          class="about-section"
          style="background-color: #ffac11; color: black; padding:4rem 3rem;"
        >
          <h2>WHAT I DO</h2>
          <div class="skills-grid">
            <div
              class="skill-item"
              style="background-image: url({bgTagHk}); background-size: 100% 100%;"
            >
              FRONTEND DEV
            </div>

            <div
              class="skill-item"
              style="background-image: url({bgTagHk}); background-size: 100% 100%;"
            >
              UI/UX DESIGN
            </div>

            <div
              class="skill-item"
              style="background-image: url({bgTagHk}); background-size: 100% 100%;"
            >
              BACKEND DEV
            </div>

            <div
              class="skill-item"
              style="background-image: url({bgTagHk}); background-size: 100% 100%;"
            >
              XR DEV
            </div>

            <div
              class="skill-item"
              style="background-image: url({bgTagHk}); background-size: 100% 100%;"
            >
              EXPO DEV
            </div>
          </div>
        </div>
        <div
          class="about-section"
          style="background-color:#ffac11; color: black;"
        >
          <h2>MY PHILOSOPHY</h2>
          <div
            class=""
            style="background-image: url({bgTagHk}); background-size: 100% 100%; border: none; color: #ffac11; margin-left: -3rem; margin-right: -3rem; width: calc(100% + 6rem); padding: 5rem 4rem"
          >
            <p>
              Design should provoke. Code should perform. Every pixel has
              purpose, every interaction tells a story. I believe in pushing
              boundaries, challenging norms, and creating work that people
              remember long after they close the browser.
            </p>
          </div>
          <div
            class=""
            style="background-image: url({bgTagHk}); background-size: 100% 100%; border: none; color: #ffac11; margin-left: -3rem; margin-right: -3rem; width: calc(100% + 6rem); padding: 5rem 4rem"
          >
            <p>
              The web is a canvas for experimentation. Safe is boring.
              Conventional is forgettable. I choose impact over comfort, every
              single time.
            </p>
          </div>
        </div>
      </div>
    </div>
  {/if}

  <!-- BLOG PAGE -->
  {#if activePage === "blog"}
    <div id="blog" class="page active">
      <div class="blog-container">
        <div class="blog-header">
          <h1>Blog</h1>
        </div>

        <div class="blog-grid">
          <article class="blog-post">
            <div class="blog-post-header">
              <h2>THE DEATH OF MINIMALISM</h2>
              <div class="blog-meta">JANUARY 15, 2026 • DESIGN</div>
            </div>
            <div class="blog-post-content">
              <p>
                For years, we've been told that less is more. That clean white
                spaces and invisible interfaces are the pinnacle of design. But
                what if minimalism has become a crutch—an excuse for safe,
                uninspired work that's afraid to make a statement?
              </p>
              <p>
                True design courage means embracing maximalism when the moment
                demands it. It means bold colors, dramatic typography, and
                interfaces that don't apologize for existing. The web shouldn't
                whisper—sometimes it needs to scream.
              </p>
            </div>
          </article>
        </div>
      </div>
    </div>
  {/if}

  <!-- RESUME PAGE -->
  {#if activePage === "resume"}
    <div id="resume" class="page active">
      <div class="resume-container">
        <div class="resume-header">
          <h1>EXPERIENCE</h1>
          <p>DESIGNER • DEVELOPER • DISRUPTOR</p>
        </div>

        <div class="resume-section">
          <h2>PROFESSIONAL HISTORY</h2>

          <div class="experience-item">
            <h3>LEAD CREATIVE TECHNOLOGIST</h3>
            <div class="experience-meta">
              APEX DIGITAL STUDIO • 2023 - PRESENT
            </div>
            <ul>
              <li>
                Architected bold digital experiences for Fortune 500 clients
                willing to take risks
              </li>
              <li>
                Pioneered brutalist design approach that increased client
                engagement by 340%
              </li>
              <li>
                Led team of 8 designers and developers in creating award-winning
                web applications
              </li>
              <li>
                Developed proprietary animation framework used across all
                company projects
              </li>
            </ul>
          </div>

          <div class="experience-item">
            <h3>SENIOR FRONTEND DEVELOPER</h3>
            <div class="experience-meta">
              NOIR CREATIVE AGENCY • 2021 - 2023
            </div>
            <ul>
              <li>
                Built high-performance web applications with focus on
                experimental UI/UX
              </li>
              <li>
                Collaborated with design team to push boundaries of web
                capabilities
              </li>
              <li>
                Implemented complex animations and 3D graphics using Three.js
                and WebGL
              </li>
              <li>
                Mentored junior developers in modern JavaScript and creative
                coding techniques
              </li>
            </ul>
          </div>

          <div class="experience-item">
            <h3>FREELANCE DESIGNER & DEVELOPER</h3>
            <div class="experience-meta">INDEPENDENT • 2023 - 2026</div>
            <ul>
              <li>
                Created custom websites and branding for startups and
                established businesses
              </li>
              <li>
                Specialized in creating, bold and innovative healthcare software
              </li>
              <li>
                Built reputation for delivering projects that exceeded client
                expectations
              </li>
              <li>
                Developed skills in rapid prototyping and client communication
              </li>
            </ul>
          </div>
        </div>

        <div class="resume-section">
          <h2>IN PROGRESS</h2>

          <div class="education-item">
            <h3>BACHELOR OF Computer Science</h3>
            <div class="education-meta">
              Florida International University • 2022 - 2019
            </div>
          </div>
        </div>
      </div>
    </div>
  {/if}

  <footer>
    <div class="footer-content">
      <div class="footer-links">
        <a href="https://github.com/JosephGabrie">GITHUB</a>
        <a href="https://www.linkedin.com/in/jgabrie007/">LINKEDIN</a>
      </div>
    </div>
  </footer>
</div>

<style>
  /* Reset & Base Styles scoped to the wrapper */
  .deadlock-wrapper {
    font-family: "Courier New", monospace;
    background-color: #0a0e0d;
    color: #d4c5a0;
    height: 100vh;
    width: 100vw;
    position: fixed;
    top: 0;
    left: 0;
    z-index: 9999;
    overflow-y: auto;
    overflow-x: hidden;
  }

  @keyframes ripple {
    0% {
      clip-path: circle(0% at 50% 50%);
    }
    100% {
      clip-path: circle(150% at 50% 50%);
    }
  }

  .animate-ripple {
    animation: ripple 5s cubic-bezier(0.4, 0, 0.2, 1) forwards;
  }

  /* Since we're in Svelte, we don't need * selector if we apply box-sizing globally, 
       but to be safe for this component's children: */
  .deadlock-wrapper :global(*) {
    box-sizing: border-box;
  }

  /* Navigation */
  nav {
    position: fixed;
    top: 0;
    width: 100%;
    background: rgba(10, 14, 13, 0.95);
    backdrop-filter: blur(10px);
    border-bottom: 3px solid #2a4a3a;
    z-index: 1000;
    padding: 1.5rem 2rem;
  }

  nav ul {
    list-style: none;
    display: flex;
    justify-content: space-between;
    align-items: center;
    max-width: 1400px;
    margin: 0 auto;
    padding: 0;
  }

  nav .links {
    display: flex;
    gap: 3rem;
  }

  nav .links button {
    background: none;
    border: none;
    padding: 0;
    font-family: inherit;
    color: #d4c5a0;
    text-decoration: none;
    font-size: 0.9rem;
    letter-spacing: 2px;
    transition: all 0.3s;
    position: relative;
    cursor: pointer;
  }

  nav .links button:hover,
  nav .links button.active {
    color: #d4a574;
    text-shadow: 0 0 10px rgba(212, 165, 116, 0.5);
  }

  /* Page Container */
  .page {
    min-height: 100vh;
    padding-top: 80px;
    /* display: block; - handled by if blocks */
  }

  /* Hero Section */
  .hero {
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    background: linear-gradient(135deg, #0a0e0d 0%, #1a2e2a 100%);
    overflow: hidden;
    border-bottom: 5px solid #2a4a3a;
    margin-top: -80px;
  }

  .hero::before {
    content: "";
    position: absolute;
    width: 200%;
    height: 200%;
    background: repeating-linear-gradient(
      0deg,
      transparent,
      transparent 2px,
      rgba(42, 74, 58, 0.03) 2px,
      rgba(42, 74, 58, 0.03) 4px
    );
    animation: scan 8s linear infinite;
    pointer-events: none;
  }

  @keyframes scan {
    0% {
      transform: translateY(0);
    }
    100% {
      transform: translateY(50px);
    }
  }

  .hero-content {
    text-align: center;
    z-index: 10;
    padding: 2rem;
  }

  .hero h1 {
    font-size: 7rem;
    font-weight: 900;
    color: #d4a574;
    text-shadow:
      4px 4px 0 #2a4a3a,
      8px 8px 20px rgba(212, 165, 116, 0.3);
    letter-spacing: 1rem;
    margin-bottom: 1rem;
    line-height: 1;
    margin-top: 0;
  }

  .hero .subtitle {
    font-size: 1.5rem;
    color: #7a9a8a;
    letter-spacing: 0.5rem;
    margin-bottom: 3rem;
    font-weight: 300;
  }

  .section-title {
    font-size: 4rem;
    color: #d4a574;
    text-align: center;
    margin-bottom: 5rem;
    letter-spacing: 1rem;
    text-shadow: 3px 3px 0 #2a4a3a;
    margin-top: 0;
  }

  .feature-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
    gap: 0;
    max-width: 1400px;
    margin: 0 auto;
  }

  .feature-card {
    background: #151e1a;
    padding: 3rem;
    border: 2px solid #2a4a3a;
    position: relative;
    transition: all 0.3s;
    overflow: hidden;
  }

  .feature-card::before {
    content: "";
    position: absolute;
    top: -2px;
    left: -2px;
    right: -2px;
    bottom: -2px;
    background: linear-gradient(45deg, #d4a574, #2a4a3a);
    opacity: 0;
    transition: opacity 0.3s;
    z-index: 0;
  }

  .feature-card:hover::before {
    opacity: 1;
  }

  .feature-card > * {
    position: relative;
    z-index: 1;
  }

  .feature-card:hover {
    transform: translateY(-10px);
    background: #1a2e2a;
  }

  .feature-number {
    font-size: 4rem;
    color: #2a4a3a;
    font-weight: bold;
    line-height: 1;
    margin-bottom: 1rem;
  }

  .feature-card:hover .feature-number {
    color: #d4a574;
  }

  .feature-card h3 {
    font-size: 2rem;
    color: #d4a574;
    margin-bottom: 1rem;
    letter-spacing: 3px;
    margin-top: 0;
  }

  .feature-card p {
    color: #7a9a8a;
    line-height: 1.8;
    font-size: 1rem;
  }

  /* Showcase Section */
  .showcase {
    padding: 8rem 2rem;
    background: linear-gradient(135deg, #1a2e2a 0%, #0a0e0d 100%);
    border-top: 5px solid #2a4a3a;
    border-bottom: 5px solid #2a4a3a;
  }

  .showcase-content {
    max-width: 1400px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 5rem;
    align-items: center;
  }

  .showcase-text h2 {
    font-size: 3.5rem;
    color: #d4a574;
    margin-bottom: 2rem;
    letter-spacing: 5px;
    line-height: 1.2;
    margin-top: 0;
  }

  .showcase-text p {
    font-size: 1.2rem;
    color: #7a9a8a;
    line-height: 2;
    margin-bottom: 1.5rem;
  }

  .showcase-visual {
    aspect-ratio: 1;
    background: #0a0e0d;
    border: 3px solid #2a4a3a;
    position: relative;
    overflow: hidden;
  }

  .showcase-visual::before {
    content: "";
    position: absolute;
    width: 100%;
    height: 100%;
    background: linear-gradient(
        45deg,
        transparent 48%,
        #2a4a3a 48%,
        #2a4a3a 52%,
        transparent 52%
      ),
      linear-gradient(
        -45deg,
        transparent 48%,
        #2a4a3a 48%,
        #2a4a3a 52%,
        transparent 52%
      );
    background-size: 60px 60px;
    opacity: 0.3;
    animation: movePattern 20s linear infinite;
  }

  @keyframes movePattern {
    0% {
      transform: translate(0, 0);
    }
    100% {
      transform: translate(60px, 60px);
    }
  }

  .showcase-visual::after {
    content: "◈";
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    font-size: 10rem;
    color: #d4a574;
    opacity: 0.2;
  }

  /* About Page */
  .about-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 6rem 2rem;
  }

  .about-hero {
    background: #3874ae;
    color: #3874ae;
    padding: 5rem 3rem;
    margin-bottom: 4rem;
    position: relative;
    overflow: hidden;
  }

  .about-hero::before {
    content: "";
    position: absolute;
    top: 0;
    right: 0;
    width: 300px;
    height: 300px;
    background: #f4e03d;
    opacity: 0.1;
    clip-path: polygon(100% 0, 100% 100%, 0 0);
  }

  .about-hero h1 {
    font-size: 5rem;
    letter-spacing: 1rem;
    margin-bottom: 1.5rem;
    color: #3874ae;
    margin-top: 0;
  }

  .about-hero p {
    font-size: 1.3rem;
    line-height: 2;
    color: #3874ae;
  }

  .about-section {
    background: transparent;
    color: #ffac11;
    padding: 4rem 3rem;
    margin-bottom: 3rem;
  }

  .about-section h2 {
    font-size: 3rem;
    margin-bottom: 2rem;
    letter-spacing: 5px;
    margin-top: 0;
  }

  .about-section p {
    font-size: 1.1rem;
    line-height: 2;
    margin-bottom: 1.5rem;
  }

  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 2rem;
    margin-top: 2rem;
  }

  .skill-item {
    color: #ffac11;
    padding: 2rem;
    text-align: center;
    font-size: 1.2rem;
    font-weight: bold;
    letter-spacing: 2px;
  }

  /* Blog Page */
  .blog-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 6rem 2rem;
  }

  .blog-header {
    background: #1a3d5c;
    color: #ffffff;
    padding: 4rem 3rem;
    border: 5px solid #0d1f2d;
    margin-bottom: 4rem;
    text-align: center;
  }

  .blog-header h1 {
    font-size: 5rem;
    letter-spacing: 1rem;
    color: #ffffff;
    text-shadow: 3px 3px 0 #0d1f2d;
    margin: 0;
  }

  .blog-grid {
    display: grid;
    gap: 3rem;
  }

  .blog-post {
    background: #f4e03d;
    color: #000000;
    border: 5px solid #d4c030;
    overflow: hidden;
    transition: transform 0.3s;
  }

  .blog-post:hover {
    transform: translateX(10px);
  }

  .blog-post-header {
    background: #1a3d5c;
    color: #ffffff;
    padding: 2rem 3rem;
    border-bottom: 5px solid #0d1f2d;
  }

  .blog-post-header h2 {
    font-size: 2.5rem;
    margin-bottom: 1rem;
    letter-spacing: 3px;
    margin-top: 0;
  }

  .blog-meta {
    font-size: 0.9rem;
    color: #b8d4e8;
    letter-spacing: 2px;
  }

  .blog-post-content {
    padding: 3rem;
  }

  .blog-post-content p {
    font-size: 1.1rem;
    line-height: 1.8;
    margin-bottom: 1.5rem;
  }

  .read-more {
    display: inline-block;
    background: #000000;
    color: #f4e03d;
    padding: 1rem 2rem;
    border: 3px solid #000000;
    text-decoration: none;
    letter-spacing: 2px;
    font-weight: bold;
    transition: all 0.3s;
  }

  .read-more:hover {
    background: #1a3d5c;
    color: #ffffff;
    border-color: #1a3d5c;
  }

  /* Resume Page */
  .resume-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 6rem 2rem;
  }

  .resume-header {
    background: #f4e03d;
    color: #000000;
    padding: 4rem 3rem;
    border: 5px solid #d4c030;
    margin-bottom: 4rem;
    text-align: center;
  }

  .resume-header h1 {
    font-size: 5rem;
    letter-spacing: 1rem;
    margin-bottom: 1rem;
    margin-top: 0;
  }

  .resume-header p {
    font-size: 1.3rem;
    letter-spacing: 3px;
  }

  .resume-section {
    background: #1a3d5c;
    color: #ffffff;
    padding: 4rem 3rem;
    border: 5px solid #0d1f2d;
    margin-bottom: 3rem;
  }

  .resume-section h2 {
    font-size: 3rem;
    margin-bottom: 3rem;
    letter-spacing: 5px;
    border-bottom: 3px solid #f4e03d;
    padding-bottom: 1rem;
    margin-top: 0;
  }

  .experience-item,
  .education-item {
    margin-bottom: 3rem;
    padding-bottom: 3rem;
    border-bottom: 2px solid #2a5a7d;
  }

  .experience-item:last-child,
  .education-item:last-child {
    border-bottom: none;
    padding-bottom: 0;
  }

  .experience-item h3,
  .education-item h3 {
    font-size: 2rem;
    color: #f4e03d;
    margin-bottom: 0.5rem;
    letter-spacing: 2px;
    margin-top: 0;
  }

  .experience-meta,
  .education-meta {
    font-size: 1rem;
    color: #b8d4e8;
    margin-bottom: 1.5rem;
    letter-spacing: 2px;
  }

  .experience-item ul {
    list-style: none;
    padding-left: 0;
  }

  .experience-item li {
    padding-left: 2rem;
    margin-bottom: 1rem;
    position: relative;
    line-height: 1.8;
    font-size: 1.1rem;
  }

  .experience-item li::before {
    content: "▸";
    position: absolute;
    left: 0;
    color: #f4e03d;
    font-size: 1.5rem;
  }

  /* Footer */
  footer {
    background: #0a0e0d;
    border-top: 3px solid #2a4a3a;
    padding: 4rem 2rem 2rem;
    text-align: center;
  }

  .footer-content {
    max-width: 1400px;
    margin: 0 auto;
  }

  .footer-links {
    display: flex;
    justify-content: center;
    gap: 3rem;
    margin-bottom: 2rem;
    flex-wrap: wrap;
  }

  .footer-links a {
    color: #7a9a8a;
    text-decoration: none;
    letter-spacing: 2px;
    transition: all 0.3s;
  }

  .footer-links a:hover {
    color: #d4a574;
  }

  .copyright {
    color: #2a4a3a;
    font-size: 0.9rem;
    letter-spacing: 2px;
    margin-top: 2rem;
  }

  @media (max-width: 768px) {
    .hero h1 {
      font-size: 3rem;
      letter-spacing: 0.5rem;
    }

    .showcase-content {
      grid-template-columns: 1fr;
    }

    nav .links {
      gap: 1rem;
      font-size: 0.8rem;
    }

    .feature-grid {
      grid-template-columns: 1fr;
    }

    .about-hero h1,
    .blog-header h1,
    .resume-header h1 {
      font-size: 3rem;
      letter-spacing: 0.5rem;
    }

    .section-title {
      font-size: 2.5rem;
    }
  }
</style>

