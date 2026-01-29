<script lang="ts">
  import { DndContext } from "@dnd-kit-svelte/core";
  import Draggable from "$lib/components/draggable.svelte";
  import Droppable from "$lib/components/droppable.svelte";
  import DeadlockTheme from "$lib/components/DeadlockTheme.svelte";

  let isDropped = $state(false);
  let isActive = $state(false);

  function handleDragEnd(event: any) {
    const { over } = event;
    if (over && over.id === "droppable") {
      isDropped = true;
      isActive = !isActive;
    }
  }
</script>

{#if isDropped}
  <DeadlockTheme />
{:else}
  <div class="brutalist-portfolio">
    <div class="noise"></div>

    <!-- Grid Layout -->
    <div class="grid-layout">
      <!-- Header Section -->
      <header class="header-section">
        <h1 class="name">JOSEPH<br />GABRIE</h1>
        <h2 class="role">FULL STACK DEVELOPER</h2>
        <div class="status-indicator">
          <span class="blink">●</span> SYSTEM: UNSTABLE
        </div>
      </header>

      <!-- Main Content (Projects/About) -->
      <main class="content-section">
        <div class="block about">
          <h3><a href="/about" class="hover:underline">// ABOUT</a></h3>
          <p>
            Building scalable systems and immersive web experiences.
            Specializing in Svelte, React, and backend architecture.
          </p>
        </div>

        <div class="block projects">
          <h3>// PROJECTS</h3>
          <ul>
            <li>
              <a href="#https://github.com/JosephGabrie/ArthasAI">ArthasAI</a
              >ArthasAi
            </li>
            <li>MyDialisis</li>
          </ul>
        </div>

        <div class="block contact">
          <h3>// CONTACT</h3>
          <p>DEV@GABRIE.IO</p>
          <div class="socials">
            <a href="https://github.com/JosephGabrie">GITHUB</a>
            <a href="https://www.linkedin.com/in/jgabrie007/">LINKEDIN</a>
          </div>
        </div>
      </main>

      <!-- Interactive Zone -->
      <aside class="interaction-section">
        <div class="terminal-header">
          <span class="status-light"></span> TERMINAL_V1.0
        </div>

        <div class="instruction">
          <p>> SYSTEM STANDBY...</p>
          <p>> LOAD MODULE TO INITIALIZE.</p>
        </div>

        <DndContext onDragEnd={handleDragEnd}>
          <div class="game-board">
            <!-- The Draggable Modules -->
            <div class="modules-container">
              <Draggable class="sys-module">
                <span class="mod-icon">::</span>
                <span>DATA_STREAM.dat</span>
              </Draggable>
            </div>

            <!-- The Drop Zone -->
            <Droppable class="input-terminal">
              <div class="upload-slot">
                <span class="slot-label">[ INSERT MODULE ]</span>
              </div>
            </Droppable>
          </div>
        </DndContext>
      </aside>
    </div>

    <!-- Background Decorative Elements -->
    <div class="bg-deco">VOID</div>
  </div>
{/if}

<style lang="scss">
  :global(body) {
    margin: 0;
    overflow: hidden;
    background-color: #0a0a0a;
    color: #e0e0e0;
    font-family: "Courier New", monospace;
  }

  .brutalist-portfolio {
    position: relative;
    width: 100vw;
    height: 100vh;
    overflow: hidden;
    background-color: #0a0a0a;
  }

  .noise {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    opacity: 0.05;
    pointer-events: none;
    z-index: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noiseFilter'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.65' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noiseFilter)' opacity='1'/%3E%3C/svg%3E");
  }

  .grid-layout {
    position: relative;
    z-index: 10;
    display: grid;
    grid-template-columns: 1fr 1fr 350px;
    height: 100vh;
    border: 1px solid #222;
  }

  .header-section {
    padding: 3rem;
    border-right: 1px solid #333;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }

  .name {
    font-size: 6rem;
    line-height: 0.8;
    margin: 0;
    color: #fff;
  }

  .role {
    font-size: 1.2rem;
    letter-spacing: 2px;
    margin-top: 1rem;
    color: #666;
  }

  .status-indicator {
    margin-top: auto;
    font-size: 0.8rem;
    color: #ff3e3e;
    border: 1px solid #ff3e3e;
    padding: 0.5rem;
    display: inline-block;
    width: fit-content;
  }

  .blink {
    animation: blink 1s infinite;
  }

  @keyframes blink {
    50% {
      opacity: 0;
    }
  }

  .content-section {
    padding: 3rem;
    border-right: 1px solid #333;
    display: flex;
    flex-direction: column;
    gap: 4rem;
    overflow-y: auto;
  }

  .block h3 {
    font-size: 1.5rem;
    border-bottom: 2px solid #e0e0e0;
    padding-bottom: 0.5rem;
    margin-bottom: 1rem;
    display: inline-block;
  }

  .block ul {
    list-style: none;
    padding: 0;
  }

  .block li {
    margin-bottom: 0.5rem;
  }

  .block a {
    color: #888;
    text-decoration: none;
    transition: color 0.3s;
  }

  .block a:hover {
    color: #fff;
    text-decoration: underline;
  }

  .interaction-section {
    background: #0f0f0f;
    padding: 2rem;
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
    border-left: 1px solid #333;
  }

  .terminal-header {
    font-weight: bold;
    border-bottom: 1px solid #333;
    padding-bottom: 1rem;
    display: flex;
    align-items: center;
    gap: 0.5rem;
  }

  .status-light {
    width: 10px;
    height: 10px;
    background: #ff3e3e;
    border-radius: 50%;
    box-shadow: 0 0 5px #ff3e3e;
  }

  .instruction {
    font-size: 0.8rem;
    color: #00ff41; /* Terminal Green */
    background: #050505;
    border: 1px solid #333;
    padding: 1rem;
    font-family: "Courier New", monospace;
  }

  .instruction p {
    margin: 0;
    line-height: 1.5;
  }

  .game-board {
    flex-grow: 1;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
  }

  .modules-container {
    display: flex;
    flex-direction: column;
    gap: 0.8rem;
    width: 100%;
  }

  :global(.sys-module) {
    background: #1a1a1a;
    border: 1px solid #444;
    border-left: 4px solid #666;
    color: #ccc;
    padding: 0.8rem 1rem;
    cursor: grab;
    font-weight: bold;
    font-size: 0.9rem;
    display: flex;
    align-items: center;
    gap: 0.8rem;
    transition: all 0.2s;
    user-select: none;
  }

  :global(.sys-module:hover) {
    background: #222;
    border-color: #888;
    border-left-color: #e0e0e0;
    color: #fff;
    transform: translateX(5px);
  }

  .mod-icon {
    color: #666;
  }

  :global(.input-terminal) {
    width: 100%;
    height: 120px;
    border: 2px dashed #444;
    display: flex;
    justify-content: center;
    align-items: center;
    transition: all 0.3s;
    background: #0d0d0d;
    margin-top: 2rem;
  }

  :global(.input-terminal:hover),
  :global(.input-terminal.droppable-active) {
    border-color: #00ff41;
    background: #0a1a0a;
  }

  .upload-slot {
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }

  .slot-label {
    font-size: 0.8rem;
    color: #444;
    letter-spacing: 2px;
    animation: pulse-text 2s infinite;
  }

  @keyframes pulse-text {
    0%,
    100% {
      opacity: 0.5;
    }
    50% {
      opacity: 1;
    }
  }

  .bg-deco {
    position: absolute;
    bottom: -50px;
    left: 20px;
    font-size: 20rem;
    font-family: "UnifrakturMaguntia", cursive;
    color: #111;
    z-index: 1;
    pointer-events: none;
    opacity: 0.5;
  }

  @media (max-width: 1024px) {
    .grid-layout {
      grid-template-columns: 1fr;
      grid-template-rows: auto auto auto;
    }
    .header-section,
    .content-section,
    .interaction-section {
      border-right: none;
      border-bottom: 1px solid #333;
    }
    .name {
      font-size: 4rem;
    }
  }
</style>
