<script>

  // import Router from "svelte-spa-router"
  // import Esc from "./esc.svelte";
  // import Home from "./Home.svelte";

  // let routes = {
  //   "/": Home,
  //   "/esc": Esc,

  // };


  let mainImageIndex = 0;
  let visiblePlatforms = [];

  let carouselItems = [
    { 
      image: "src/img/Diablo.png", 
      text: "The new part of the <br/>famous series will <br/>plunge you into <br/>the horrors of Sanctuary", 
      position: {
        top: '25%',
        left: '5%',
        classPos: '8k:pt-[200px] 8k:pl-[0px] 2k:pt-[250px] 2k:pl-[0px] xl:pt-32 xl:pl-[1px] lg:pt-[130px] lg:pl-[1px] md:pt-[150px] md:pl-[1px] sm:pt-[160px] sm:pl-[105px] xsm:pt-[160px] xsm:pl-[30px]',  
      },
      logo: { image: "src/img/Logo/DIABLO_LOGO_520x300 1.png", position: { top: '10%', left: '3%' }, sizeClasses: "8k:w-[1424px] 8k:h-[950px] 4k:w-[924px] 4k:h-[550px] 2k:w-[524px] 2k:h-[280px] w-[325px] h-[188px] 8k:mb-[0px] xl:mt-[30px] xl:ml-[1px] lg:mt-[30px] lg:ml-[1px] md:mt-[60px] md:ml-[1px] sm:mt-[50px] sm:ml-[150px] xsm:mt-[30px] xsm:ml-[40px]" },
      platforms: [
        { main: "PS", additional: [] },
        { main: "Xbox", additional: [] },
        { main: "Win", additional: ["Battle.net", "Epic Games Store", "gog.com","Steam","Humble Bundle"] },
      ],  
    },
    { 
      image: "src/img/Warcraft.png", 
      text: "An eternal classic of war <br/>between the Horde and the<br/> people of Lordaeron", 
      position: {
        top: '35%',
        
        classPos: '8k:pt-[500px] 8k:pl-[1px] 2k:pt-[200px] 2k:pl-[0px] xl:pt-[100px] xl:pl-[1px] lg:pt-[90px] lg:pl-[1px] md:pt-[90px] md:pl-1 sm:pt-[100px] sm:pl-[15px] xsm:pt-[150px] xsm:pl-[10px]',  
      },
      logo: { image: "src/img/Logo/Warcraft 1 logo 1.png", position: { top: '10%' }, sizeClasses: "8k:w-[2224px] 8k:h-[890px] 4k:w-[1224px] 4k:h-[550px] 2k:w-[724px] 2k:h-[350px] xl:w-[490px] xl:h-[203px] lg:w-[490px] lg:h-[203px] sm:w-[490px] sm:h-[203px] xsm:w-[490px] xsm:h-[203px] xl:ml-[1px] lg:mt-[5px] lg:ml-[1px] md:mt-[20px] md:ml-[1px] sm:mt-[20px] sm:ml-[10px] xsm:mt-[20px] xsm:ml-[0px] " },
      platforms: [
        { main: "MacOs", additional: [] },
        { main: "Win", additional: ["Battle.net", "Epic Games Store", "gog.com","Steam","Humble Bundle"] },
      ],    
    },
    { 
      image: "src/img/Overwatch.png", 
      text: "A fresh take on <br/>co-op shooters expands <br/>the horizons of <br/>the genre", 
      position: {
        top: '45%',
        left: '5%',
        classPos: '8k:pt-[900px] 8k:pl-[1px] 2k:pt-[50px] 2k:pl-[1px] xl:pt-[0px] xl:pl-[1px] lg:pt-[40px] lg:pl-[1px] md:pt-[70px] md:pl-1 sm:pt-[90px] sm:pl-[15px] xsm:pt-[50px] xsm:pl-[40px]',  
      },
      logo: { image: "src/img/Logo/Overwatch-Logo 1.png", position: { top: '5%', left: '5%' }, sizeClasses: "8k:w-[1680px] 8k:h-[980px] 4k:w-[1124px] 4k:h-[550px] 2k:w-[450px] 2k:h-[250px] w-[270px] h-[190px] 2k:mt-[100px] 2k:ml-[1px] xl:ml-[1px] lg:mt-[60px] lg:ml-[1px] md:mt-[90px] md:ml-[1px] sm:mt-[10px] sm:ml-[330px] xsm:mt-[80px] xsm:ml-[40px]" },
      platforms: [
        { main: "Nintendo Switch", additional: [] },
        { main: "PS", additional: [] },
        { main: "Xbox", additional: [] },
        { main: "Win", additional: ["Battle.net", "Epic Games Store", "gog.com","Steam","Humble Bundle"] },
      ],     
    },
    { 
      image: "src/img/HoMM3.png", 
      text: "A modern version of <br/>the turn-based strategy <br/>genre immortal leader", 
      position: {
        top: '35%',
        
        classPos: '8k:pt-[400px] 8k:pl-[500px] xl:pt-[0px] xl:pl-[500px] lg:pt-[55px] lg:pl-[500px] md:pt-[70px] md:pl-1 sm:pt-[60px] sm:pl-[15px] xsm:pt-[70px] xsm:pl-[10px]',  
      },
      logo: { image: "src/img/Logo/HoMM-3-Logo 1.png", position: { top: '3%'  }, sizeClasses: "8k:w-[1900px] 8k:h-[980px] 4k:w-[1124px] 4k:h-[550px] 2k:w-[624px] 2k:h-[250px] w-[524px] h-[188px] 8k:mt-[0px] 8k:ml-[490px] xl:ml-[480px]  lg:mt-[10px] lg:ml-[490px] md:mt-[10px] md:ml-[1px] sm:mt-[10px] sm:ml-[10px] xsm:mt-[10px] xsm:ml-[0px]" },  
      platforms: [
        { main: "Android", additional: ["Google Play", "Netflix", "Amazon"] },
        { main: "iOS", additional: ["App Store", "Apple Arcade"] },
        { main: "macOS", additional: [] },
        { main: "Linux", additional: [] },
        { main: "Win", additional: ["Battle.net", "Epic Games Store", "gog.com","Steam","Humble Bundle"] },
      ],     
    },
    { 
      image: "src/img/Warhammer40k.png", 
      text: "Defy Chaos in a <br/>classic real-time <br/>strategy game", 
      position: {
        top: '35%',
        left: '5%',
        classPos: '8k:pt-[600px] 8k:pl-[] xl:pt-[100px] xl:pl-[10px] lg:pt-[75px] lg:pl-[10px] md:pt-[90px] md:pl-1 sm:pt-[90px] sm:pl-[160px] xsm:pt-[80px] xsm:pl-[90px]',  
      },
      logo: { image: "src/img/Logo/Warhammer-40k-logo 1.png", position: { top: '0%', left: '3%' }, sizeClasses: "8k:w-[1900px] 8k:h-[1220px] 4k:w-[1124px] 4k:h-[650px] 2k:w-[524px] 2k:h-[350px] w-[340px] h-[220px] xl:ml-[1px] xl:mt-[40px]  lg:mt-[40px] lg:ml-[1px] md:mt-[60px] md:ml-[1px] sm:mt-[40px] sm:ml-[130px] xsm:mt-[40px] xsm:ml-[20px]" },
      platforms: [
        { main: "Win", additional: ["Battle.net", "Epic Games Store", "gog.com","Steam","Humble Bundle"] },
      ],  
    },
    { 
      image: "src/img/Cyberpunk.png", 
      text: "A milestone in the <br/> contemporary art", 
      position: {
        top: '50%',
        
        classPos: '2k:pt-[60px] xl:pt-[90px] xl:pl-[10px] lg:pt-[100px] lg:pl-[10px] md:pt-[90px] md:pl-[1px] sm:pt-[90px] sm:pl-[1px] xsm:pt-[30px] xsm:pl-[1px]',  
      },
      logo: { image: "src/img/Logo/Cyberpunk-2077-logo 2.png", position: { top: '15%' }, sizeClasses: "8k:w-[1920px] 8k:h-[980px] 4k:w-[1124px] 4k:h-[550px] 2k:w-[624px] 2k:h-[350px] w-[450px] h-[293px] 8k:ml-[4900px] 4k:ml-[2400px] 2k:ml-[1200px] xl:ml-[800px] xl:mt-[40px]  lg:mt-[40px] lg:ml-[550px] md:mt-[5px] md:ml-[300px] sm:mt-[0px] sm:ml-[180px] xsm:mt-[0px] xsm:ml-[0px]" },
      platforms: [
        { main: "PS", additional: [] },
        { main: "Xbox", additional: [] },
        { main: "Win", additional: ["Battle.net", "Epic Games Store", "gog.com","Steam","Humble Bundle"] },
      ],   
    },
  ];


  function changeMainImage(index) {
    mainImageIndex = index;
    resetVisiblePlatforms();
  }

  function nextImage() {
    mainImageIndex = (mainImageIndex + 1) % carouselItems.length;
    resetVisiblePlatforms();
  }
 
  function prevImage() {
    mainImageIndex = (mainImageIndex - 1 + carouselItems.length) % carouselItems.length;
    resetVisiblePlatforms();
  }

  function resetVisiblePlatforms() {
    visiblePlatforms = [];
  }

  function shouldCenterText(index) {
    return index === 1 || index === 3;
  }

  function goToSlide(index) {
    mainImageIndex = index;
    resetVisiblePlatforms();
  }

  function handleKeyDown(event) {
    if (event.key === 'Enter' || event.key === ' ') {
      goToSlide(event.detail);
    }
  }

  function showAdditionalPlatforms(index, platform) {
    visiblePlatforms = carouselItems[index].platforms.find(p => p.main === platform)?.additional || [];
  }
</script>

<style>
  .main-image {
    width: 100%;
    height: 100%;
  }

  .arrow-button {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background-color: transparent;
    border: none;
    color: white;
    font-size: 2xl;
    cursor: pointer;
  }

  .arrow-button.left {
    left: 4px;
  }

  .arrow-button.right {
    right: 4px;
  }
</style>

<!-- <header title="Esc" class="w-full h-10">
  <a href="#/esc"><button class="border p-2 mx-auto rounded-xl hover:bg-gray-50">1</button>
</header> -->


<div class="w-full h-50 bg-slate-700"></div>

<div class="w-full bg-zinc-300">
  <div class="w-full h-full absolute">
    <div class="w-full h-full absolute overflow-hidden">
      <img class="main-image w-full object-cover object-right" alt="" src={carouselItems[mainImageIndex].image} />
    </div>
    <div class="w-full h-full absolute flex flex-col items-center justify-end">
      {#each carouselItems as { text, position, logo, platforms }, index (text)}
        {#if index === mainImageIndex}
          <div style={`top: ${position.top}; left: ${position.left};`} class="text-white 8k:text-[190px] 4k:text-[140px] 2k:text-6xl xl:text-5xl lg:text-4xl md:text-4xl sm:text-[32px] xsm:text-2xl font-extrabold leading-tight mb-8 absolute ${position.classPos}">
            {#if shouldCenterText(index)}
              <div class="text-center">
                {@html text.split('<br/>').join('<br />')}
              </div>
            {:else}
              {@html text.split('<br/>').join('<br />')}
            {/if}
          </div>

          {#if logo}
            <div style={`top: ${logo.position.top}; left: ${logo.position.left};`} class="absolute">
              <img src={logo.image} alt="Logo" class={logo.sizeClasses} />
            </div>
          {/if}

          <div class="w-[37px] h-[67px] p-2.5 opacity-95 rounded-[20px] flex items-center justify-center whitespace-nowrap mb-1 ">
            <div class="text-white text-[28px] 8k:text-[200px] 4k:text-[70px] font-normal font-['Inter'] leading-[23px] whitespace-nowrap 8k:mb-[420px] 4k:mb-[120px] 4k:pl-[100px] ">Buy it for</div>

            {#if visiblePlatforms.length > 0}
              {#each visiblePlatforms as platform (platform)}
                <div class="  w-11 h-[47px] flex-col justify-center items-center gap-2.5 inline-flex group ml-3 8k:ml-[290px] 8k:mb-[490px] 4k:ml-[110px] 4k:mb-[150px]">
                  <div class=" w-[47px] h-[47px] 8k:w-[300px] 8k:h-[300px] relative group 4k:w-[130px] 4k:h-[130px]">
                    <img class="w-full h-full object-fill" src={`src/img/Platforms/${platform}.svg`} alt={platform} />
                    <div class="text-center text-white text-opacity-0 text-xs 8k:text-[50px] 4k:text-[25px]  8k:mt-[30px] 4k:mt-[15px] font-light font-['Inter'] leading-[23px] group-hover:text-opacity-100 transition-opacity duration-300 ease-in-out">{platform}</div>
                  </div>
                </div>
              {/each}
              <div 
                role="button"
                tabindex="0"
                class="w-11 h-[47px] flex-col justify-start items-center gap-2.5 inline-flex group ml-3 8k:ml-[290px] 8k:mb-[720px] 4k:ml-[110px] 4k:mb-[220px]"
                on:click={resetVisiblePlatforms}
                on:keydown={e => e.key === 'Enter' && goToSlide()}
              >
                <div class="w-[47px] h-[47px] 8k:w-[300px] 8k:h-[300px] 4k:w-[130px] 4k:h-[130px] relative group ">
                  <img class="w-full h-full " src={`src/img/Arrows/Back.svg`} alt="Arrow Back" />
                  <div class="text-center text-white text-opacity-0 text-xs 4k:text-[25px] font-light font-['Inter'] leading-[23px] group-hover:text-opacity-100 transition-opacity duration-300 ease-in-out ">Back</div>
                </div>
              </div>
            {:else}
              {#each carouselItems[mainImageIndex].platforms as platform (platform)}
                <div 
                  role="button"
                  tabindex="0"
                  class="w-11 h-[47px] text-center flex-col justify-start items-center gap-2.5 inline-flex group ml-[20px] 8k:ml-[290px] 8k:mb-[720px] 4k:ml-[110px] 4k:mb-[220px]"
                  on:click={() => showAdditionalPlatforms(mainImageIndex, platform.main)}
                  on:keydown={e => e.key === 'Enter' && goToSlide()}
                >
                  <div class="w-[47px] h-[47px] 8k:w-[300px] 8k:h-[300px] 4k:w-[130px] 4k:h-[130px] relative group ">
                    <img class="w-full h-full object-fill" src={`src/img/Platforms/${platform.main}.svg`} alt={platform.main} />
                    <div class="text-center text-white text-opacity-0 text-xs 8k:text-[50px] 4k:text-[25px] font-light font-['Inter'] leading-[23px] group-hover:text-opacity-100 transition-opacity duration-300 ease-in-out 8k:mt-[30px]">{platform.main}</div>
                  </div>
                </div>
              {/each}
            {/if} 
          </div>
        {/if}
      {/each}

      <div class="w-350 h-10 relative 8k:mb-[50px] 4k:mb-[25px] 4k:pl-[110px]">
        <div 
          role="button"
          tabindex="0"
          class="w-full h-9 flex justify-center items-center"
          on:keydown={handleKeyDown}
        >
          {#each carouselItems as { image }, index (image)}
            <div 
              role="button"
              tabindex="0"
              class="{ 'w-[50px] h-[9px] 8k:w-[250px] 8k:h-[30px] 8k:mx-[20px] 4k:w-[100px] 4k:h-[15px] 4k:mx-[10px] mx-1 transition duration-300 ease-in-out cursor-pointer ' + (index === mainImageIndex ? 'bg-white rounded-sm' : 'bg-zinc-400 rounded-sm') }"
              on:click={() => goToSlide(index)}
              on:keydown={e => e.key === 'Enter' && goToSlide(index)}
            ></div>
          {/each}
        </div>
      </div>
      
      <button on:click={prevImage} class="arrow-button left pl-4">
        <img class="8k:w-[100px] 8k:h-[100px] 4k:w-[50px] 4k:h-[50px]" src="src/img/Arrows/bx-top-arrow.svg" alt="Left Arrow" />
      </button>
      <button on:click={nextImage} class="arrow-button right pr-4">
        <img class="8k:w-[100px] 8k:h-[100px] 4k:w-[50px] 4k:h-[50px]" src="src/img/Arrows/icon-arrow-right.svg" alt="Right Arrow" />
      </button>
    </div>
  </div>
</div>
