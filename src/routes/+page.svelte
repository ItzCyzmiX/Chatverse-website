<svelte:head>
    <title>ChatVerse - Create and Chat with AI Bots</title>
</svelte:head>

<div class="min-h-screen flex flex-col text-white bg-black relative overflow-hidden">
    <!-- Grid background -->
    <div class="absolute inset-0 bg-[linear-gradient(rgba(255,255,255,0.03)_1px,transparent_1px),linear-gradient(90deg,rgba(255,255,255,0.03)_1px,transparent_1px)] bg-[size:50px_50px] [mask-image:radial-gradient(ellipse_at_center,black_40%,transparent_100%)]"></div>
    
    <!-- Radial gradient overlay -->
    <div class="absolute inset-0 bg-[radial-gradient(circle_at_50%_50%,transparent_0%,rgba(0,0,0,0.7)_100%)]"></div>
    
    <!-- Header with glass effect -->
    <header class="fixed w-full top-0 p-6 backdrop-blur-sm bg-black/30 z-50 border-b border-white/5">
        <nav class="max-w-7xl mx-auto flex justify-between items-center">
            <h1 class="text-4xl font-bold bg-gradient-to-r from-white to-gray-200 bg-clip-text text-transparent">ChatVerse</h1>
        </nav>
    </header>

    <main class="flex-grow flex flex-col lg:flex-row items-center justify-center gap-12 px-4 py-16 relative mt-6">
        <!-- Left side content -->
        <div class="text-center lg:text-left lg:w-1/2 z-10">
            <h2 class="text-6xl md:text-7xl font-bold mb-6 bg-gradient-to-r from-white via-gray-100 to-white bg-clip-text text-transparent">
                Discover a Universe of <span class="">AI Chatbots</span>
            </h2>
            <p class="text-2xl mb-12 text-gray-300">
                Create, explore, and chat with unique AI personalities crafted by the community.
            </p>
            <a class="group relative px-8 py-4 bg-white text-black font-bold rounded-full hover:scale-105 transition-all duration-300 shadow-[0_0_15px_rgba(255,255,255,0.1)] hover:shadow-[0_0_30px_rgba(255,255,255,0.2)]">
                Get the App
                <span class="absolute inset-0 rounded-full bg-white/30 blur-md group-hover:blur-xl transition-all duration-300 -z-10"></span>
            </a>
        </div>

        <!-- Right side app preview -->
        <div class="relative lg:w-1/2 max-w-sm w-full z-10 ">
            <!-- Phone frame -->
            <div class="relative mx-auto w-[22.5rem] aspect-[9/17] bg-black rounded-[3rem] border-4 border-white/10 overflow-hidden shadow-2xl shadow-white/10 ">
                <!-- App screenshot -->
                <div class="absolute inset-0 bg-black">
            
                    <img class=" w-full h-full" src="preveiw.jpeg" alt="preveiw app" />
                   
                </div>
            </div>
            
            <!-- Decorative glow -->
            <div class="absolute -inset-1 bg-gradient-to-r from-white/0 via-white/10 to-white/0 blur-xl opacity-50 -z-10"></div>
        </div>
    </main>

    <!-- Features Section -->
    <section class="py-24 relative bg-transparent">
        <div class="max-w-7xl mx-auto px-4 bg-transparent">
            <h2 class="text-4xl font-bold text-center mb-16 bg-transparent">
                Key Features
            </h2>
            
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                {#each features as feature}
                <div class="group p-8 rounded-2xl bg-white/[0.02] backdrop-blur-sm border border-white/10 hover:border-white/20 transition-all duration-300 hover:-translate-y-1 hover:bg-white/[0.04]">
                    <div class="flex flex-col h-full">
                        <h3 class="text-2xl font-semibold mb-4 text-white transition-all">
                            {feature.title}
                        </h3>
                        <p class="text-gray-400 transition-colors">
                            {feature.description}
                        </p>
                    </div>
                </div>
                {/each}
            </div>
        </div>
    </section>
    

    <section class="py-24 relative bg-transparent">
        <div class="max-w-7xl mx-auto px-4 bg-transparent">
          <h2 class="text-4xl font-bold text-center mb-16 bg-transparent">
            Chatbot Examples
          </h2>
      
          <div class="relative">
            <button
              class="absolute top-1/2 -translate-y-1/2 -left-4 z-10 px-4 py-2 rounded-full bg-white/10 hover:bg-white/20 backdrop-blur-sm transition-all"
              onclick={prevSlide}
              aria-label="slider"
            >
              <svg
                class="w-6 h-6"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M15 19l-7-7 7-7"
                />
              </svg>
            </button>
      
            <div class="flex overflow-x-auto snap-x snap-mandatory -mx-4 p-6 pb-32 overflow-y-hidden">
              {#each chatbotExamples as example, i}
                <div
                  class="flex-shrink-0 w-full h-96 md:w-1/2 lg:w-1/4 px-4 snap-always snap-center transition-all"
                  class:opacity-50={i !== currentIndex}
                  
                  class:scale-105={i == currentIndex}
                >
                  <div class="bg-white/[0.02] backdrop-blur-sm border border-white/10 rounded-2xl p-8 transition-all {i === currentIndex ? `shadow-white/30` : ""}"
                  class:shadow-md={i == currentIndex}
                  
                  >
                    <img
                      src={example.image}
                      alt={example.title}
                      class="w-full h-[20rem] object-cover rounded-t-2xl"
                    />
                    <h3 class="text-2xl font-semibold mt-4 text-white">{example.title}</h3>
                    <p class="text-gray-400 mt-2">{example.description}</p>
                  </div>
                </div>
              {/each}
            </div>
      
            <button
              class="absolute top-1/2 -translate-y-1/2 -right-2 z-10 px-4 py-2 rounded-full bg-white/10 hover:bg-white/20 backdrop-blur-sm transition-all"
              onclick={nextSlide}
              aria-label="slider"
            >
              <svg
                class="w-6 h-6"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M9 5l7 7-7 7"
                />
              </svg>
            </button>
          </div>
        </div>
        <h1 class="text-2xl font-bold text-center mt-4">And More On The<a class="ml-2 underline hover:-translate-y-1 transition-all" href="/download"> App!</a></h1>
      </section>
    <!-- Footer -->
    <footer class="border-t border-white/5 backdrop-blur-sm bg-black/30">
        <div class="max-w-7xl mx-auto px-4 py-8">
            <p class="text-center text-gray-400">
                &copy; {new Date().getFullYear()} ChatVerse. All rights reserved.
            </p>
        </div>
    </footer>
</div>
<script>

const features = [
    {
        title: "Custom Chatbot Creation",
        description: "Easily design and customize your AI chatbot with unique personalities and skills."
    },
    {
        title: "Explore Community Creations",
        description: "Discover and interact with a vast library of chatbots created by other users."
    },
    {
        title: "Chat History and Memory",
        description: "Your conversations are saved, allowing the AI to remember context and provide more relevant responses."
    },
    {
        title: "Completely Free to Use",
        description: "Enjoy all the features of ChatVerse without any cost. Start creating and chatting today!"
    }
];


const chatbotExamples = [
    {
        title: "Makima",
        description: "Yes she will accept your barks",
        image: "https://rukminim2.flixcart.com/image/416/416/kt4ozgw0/poster/c/b/g/medium-guchico-digital-art-illustration-makima-chainsaw-man-original-imag6jdgutruuf4r.jpeg",
    },
    {
        title: "Skibidi Toilet",
        description: "just dont let bite your ahh",
        image: "https://m.media-amazon.com/images/M/MV5BMzgzMzY2MmMtMWNkNy00ZjVkLWIxOWUtZDJjODNmY2IyOWFiXkEyXkFqcGc@._V1_.jpg"
    },
    {
        title: "Girlfriend",
        description: "freaky",
        image: "https://img.freepik.com/premium-photo/cute-chibi-lofi-anime-manga-girl-valentines-day-hearts-background_877869-45157.jpg"
    },
    {
        title: "Sigma",
        description: "Those who know",
        image: "https://i1.sndcdn.com/artworks-96JSClFLpAx79Njf-Zzf0dA-t500x500.jpg"
    }
];
let currentIndex = $state(0);
function prevSlide() {
    currentIndex = (currentIndex - 1 + chatbotExamples.length) % chatbotExamples.length;
  }

  function nextSlide() {
    currentIndex = (currentIndex + 1) % chatbotExamples.length;
  }

</script>