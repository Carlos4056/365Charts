<script>
    import Day001 from "$lib/components/days/Day001.svelte";
    import Day002 from "$lib/components/days/Day002.svelte";
</script>

<header>
  <div class="header-container">
    <h1>This is <span class="colored">365Charts!</span></h1>
      <div class="presentation">
        <p>
          Hi! I'm Carlos Albaladejo! I am a data journalist and web developer. I write code, maps, charts and stories:)
          My main goal before this year finishes is to be hired by one big media outlet. Let's get cracked!
        </p>
      </div>
      <div class="project">
        <p>
          So, what is 365Charts? Every day I will be publishing a map or chart here and on social media to catch a recruiter's eye.
          If you are an internet sailor, note that all the code used to create these charts is Open 
          Source, because journalism must be affordable and accessible to everyone. It can be used, 
          copied, reproduced, pasted at your convenience.
        </p>
      </div>
  </div>
</header>

<main class="gallery">
    <div class="map-card">
        <Day002 />
    </div>

    <div class="map-card">
        <Day001 />
    </div>
</main>

<style>
    header {
      position: relative;
      display:flex;
      flex-direction: column;
      margin: 6rem 0;
    }
    .header-container {
      margin: auto;
      padding:1rem;
      width: 100%;
      max-width: 1200px;
    }
    h1 {
      font-size: 4rem;
      font-weight: 700;
      color:#444;
      margin:1.5rem 0;
    }
    p {
      font-size: 1.5rem;
      line-height: 1.6;
      max-width: 75ch;
    }
    .presentation {
      font-weight: 500;
    }
  
    .project {
      margin: 1rem 0;
      font-weight: 300;
      color: #919191;
    }
    
    .gallery {
        position: relative;
        display: flex;
        flex-direction: column; /* Un sota l'altre */
        gap: 2rem; /* Espai entre mapes */
        align-items: center;

    }
    
    .map-card {
       margin: 0.3rem 0;
        
    }
    
    .colored {
      background-image: linear-gradient(
        45deg,
        #ff0000,
        #ff7300,
        #fffb00,
        #48ff00,
        #00ffd5,
        #002bff,
        #7a00ff,
        #ff00c8,
        #ff0000
      );
      
      background-size: 400%;
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      animation: rainbow-move 5s linear infinite;
    }

    @keyframes rainbow-move {
      0% {
        background-position: 0% 50%;
      }
      100% {
        background-position: 100% 50%;
      }
    }

    @media (max-width:768px) {
      h1 {
        line-height: 1.3;
      }
      p {
        margin-top: 2rem;
        font-size: 1.3rem;
        line-height: 1.6;
      }
      header {
        margin: 0;
      }
    }
</style>