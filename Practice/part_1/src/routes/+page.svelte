<script>
  let mainImageIndex = 0;
  let visiblePlatforms = [];

  let carouselItems = [
    { 
      image: "src/img/Diablo.png", 
      text: "The new part of the <br/>famous series will <br/>plunge you into <br/>the horrors of Sanctuary", 
      position: {
        top: '40%',
        left: '5%',
        classPos: 'xl:pt-32 xl:pl-[1px] lg:pt-[70px] lg:pl-[1px] md:pt-[90px] md:pl-[1px] sm:pt-[100px] sm:pl-[105px] xsm:pt-[100px] xsm:pl-[30px]',  
      },
      logo: { image: "src/img/Logo/DIABLO_LOGO_520x300 1.png", position: { top: '10%', left: '3%' }, sizeClasses: "w-[325px] h-[188px] xl:mt-[30px] xl:ml-[1px] lg:mt-[30px] lg:ml-[1px] md:mt-[60px] md:ml-[1px] sm:mt-[80px] sm:ml-[150px] xsm:mt-[80px] xsm:ml-[40px]" },
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
        
        classPos: 'xl:pt-[500px] xl:pl-[1px] lg:pt-[90px] lg:pl-[1px] md:pt-[90px] md:pl-1 sm:pt-[100px] sm:pl-[15px] xsm:pt-[150px] xsm:pl-[10px]',  
      },
      logo: { image: "src/img/Logo/Warcraft 1 logo 1.png", position: { top: '10%' }, sizeClasses: "w-[490px] h-[203px] xl:ml-[1px] lg:mt-[30px] lg:ml-[1px] md:mt-[20px] md:ml-[1px] sm:mt-[20px] sm:ml-[10px] xsm:mt-[20px] xsm:ml-[0px] " },
      platforms: [
        { main: "MacOs", additional: [] },
        { main: "Win", additional: ["Battle.net", "Epic Games Store", "gog.com","Steam","Humble Bundle"] },
      ],    
    },
    { 
      image: "src/img/Overwatch.png", 
      text: "A fresh take on <br/>co-op shooters expands <br/>the horizons of <br/>the genre", 
      position: {
        top: '35%',
        left: '5%',
        classPos: 'xl:pt-[400px] xl:pl-[1px] lg:pt-[90px] lg:pl-[1px] md:pt-[90px] md:pl-1 sm:pt-[130px] sm:pl-[15px] xsm:pt-[150px] xsm:pl-[10px]',  
      },
      logo: { image: "src/img/Logo/Overwatch-Logo 1.png", position: { top: '5%', left: '5%' }, sizeClasses: "w-[270px] h-[190px] xl:ml-[1px] lg:mt-[60px] lg:ml-[1px] md:mt-[40px] md:ml-[1px] sm:mt-[10px] sm:ml-[330px] xsm:mt-[80px] xsm:ml-[40px]" },
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
        top: '28%',
        
        classPos: 'xl:pt-[50px] xl:pl-[500px] lg:pt-[75px] lg:pl-[500px] md:pt-[90px] md:pl-1 sm:pt-[90px] sm:pl-[15px] xsm:pt-[100px] xsm:pl-[10px]',  
      },
      logo: { image: "src/img/Logo/HoMM-3-Logo 1.png", position: { top: '10%'  }, sizeClasses: "w-[524px] h-[188px] xl:ml-[480px]  lg:mt-[10px] lg:ml-[490px] md:mt-[10px] md:ml-[1px] sm:mt-[10px] sm:ml-[10px] xsm:mt-[10px] xsm:ml-[0px]" },  
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
        classPos: 'xl:pt-[100px] xl:pl-[10px] lg:pt-[75px] lg:pl-[10px] md:pt-[90px] md:pl-1 sm:pt-[90px] sm:pl-[160px] xsm:pt-[80px] xsm:pl-[90px]',  
      },
      logo: { image: "src/img/Logo/Warhammer-40k-logo 1.png", position: { top: '0%', left: '3%' }, sizeClasses: "w-[340px] h-[220px] xl:ml-[1px] xl:mt-[40px]  lg:mt-[40px] lg:ml-[1px] md:mt-[60px] md:ml-[1px] sm:mt-[40px] sm:ml-[130px] xsm:mt-[40px] xsm:ml-[20px]" },
      platforms: [
        { main: "Win", additional: ["Battle.net", "Epic Games Store", "gog.com","Steam","Humble Bundle"] },
      ],  
    },
    { 
      image: "src/img/Cyberpunk.png", 
      text: "A milestone in the <br/> contemporary art", 
      position: {
        top: '50%',
        
        classPos: 'xl:pt-[90px] xl:pl-[10px] lg:pt-[100px] lg:pl-[10px] md:pt-[90px] md:pl-[1px] sm:pt-[90px] sm:pl-[1px] xsm:pt-[5px] xsm:pl-[1px]',  
      },
      logo: { image: "src/img/Logo/Cyberpunk-2077-logo 2.png", position: { top: '15%' }, sizeClasses: "w-[450px] h-[293px] xl:ml-[800px] xl:mt-[40px]  lg:mt-[40px] lg:ml-[550px] md:mt-[60px] md:ml-[300px] sm:mt-[40px] sm:ml-[180px] xsm:mt-[0px] xsm:ml-[0px]" },
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


<div class="w-full h-50 bg-slate-700"></div>

<div class="w-full bg-zinc-300">
  <div class="w-full h-full absolute">
    <div class="w-full h-full absolute overflow-hidden">
      <img class="main-image w-full object-cover object-right" alt="" src={carouselItems[mainImageIndex].image} />
    </div>
    <div class="w-full h-full absolute flex flex-col items-center justify-end">
      {#each carouselItems as { text, position, logo, platforms }, index (text)}
        {#if index === mainImageIndex}
          <div style={`top: ${position.top}; left: ${position.left};`} class="text-white xl:text-5xl lg:text-4xl md:text-4xl sm:text-[32px] xsm:text-2xl font-extrabold leading-tight mb-8 absolute ${position.classPos}">
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

          <div class="w-[337px] h-[67px] p-2.5 opacity-95 rounded-[20px] flex items-center justify-center whitespace-nowrap mb-1">
            <div class="text-white text-[28px] font-normal font-['Inter'] leading-[23px] whitespace-nowrap">Buy it for</div>

            {#if visiblePlatforms.length > 0}
              {#each visiblePlatforms as platform (platform)}
                <div class="w-11 h-[47px] flex-col justify-center items-center gap-2.5 inline-flex group ml-3">
                  <div class="w-[47px] h-[47px] relative group ">
                    <img class="w-full h-full " src={`src/img/Platforms/${platform}.svg`} alt={platform} />
                    <div class="text-center text-white text-opacity-0 text-xs font-light font-['Inter'] leading-[23px] group-hover:text-opacity-100 transition-opacity duration-300 ease-in-out">{platform}</div>
                  </div>
                </div>
              {/each}
              <div 
                role="button"
                tabindex="0"
                class="w-11 h-[47px] flex-col justify-start items-center gap-2.5 inline-flex group ml-3"
                on:click={resetVisiblePlatforms}
              >
                <div class="w-[47px] h-[47px] relative group ">
                  <img class="w-full h-full " src={`src/img/Arrows/Back.svg`} alt="Arrow Back" />
                  <div class="text-center text-white text-opacity-0 text-xs font-light font-['Inter'] leading-[23px] group-hover:text-opacity-100 transition-opacity duration-300 ease-in-out ">Back</div>
                </div>
              </div>
            {:else}
              {#each carouselItems[mainImageIndex].platforms as platform (platform)}
                <div 
                  role="button"
                  tabindex="0"
                  class="w-11 h-[47px] text-center flex-col justify-start items-center gap-2.5 inline-flex group ml-3"
                  on:click={() => showAdditionalPlatforms(mainImageIndex, platform.main)}
                >
                  <div class="w-[47px] h-[47px] relative group ">
                    <img class="w-full h-full " src={`src/img/Platforms/${platform.main}.svg`} alt={platform.main} />
                    <div class="text-center text-white text-opacity-0 text-xs font-light font-['Inter'] leading-[23px] group-hover:text-opacity-100 transition-opacity duration-300 ease-in-out">{platform.main}</div>
                  </div>
                </div>
              {/each}
            {/if} 
          </div>
        {/if}
      {/each}

      <div class="w-350 h-10 relative ">
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
              class="{ 'w-[50px] h-[9px] mx-1 transition duration-300 ease-in-out cursor-pointer ' + (index === mainImageIndex ? 'bg-white rounded-sm' : 'bg-zinc-400 rounded-sm') }"
              on:click={() => goToSlide(index)}
              on:keydown={e => e.key === 'Enter' && goToSlide(index)}
            ></div>
          {/each}
        </div>
      </div>
      
      <button on:click={prevImage} class="arrow-button left pl-4">
        <img src="src/img/Arrows/bx-top-arrow.svg" alt="Left Arrow" />
      </button>
      <button on:click={nextImage} class="arrow-button right pr-4">
        <img src="src/img/Arrows/icon-arrow-right.svg" alt="Right Arrow" />
      </button>
    </div>
  </div>
</div>
