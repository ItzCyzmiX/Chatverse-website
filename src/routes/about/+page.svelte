<script>
    // Explore Page
    const explorePageData = {
      title: "Explore Page",
      description:
        "The Explore page allows users to browse through a wide range of chatbot examples and discover new and innovative conversational experiences.",
      image: "explore-page.jpg"
    };
  
    // Chat Interface
    const chatInterfaceData = {
      title: "Chat Interface",
      description:
        "The Chat Interface provides a seamless and intuitive conversation experience, enabling users to engage with chatbots in a natural and responsive manner.",
      image: "chat-interface.jpg"
    };
  
    // Creation Screen
    const creationScreenData = {
      title: "Creation Screen",
      description:
        "The Creation Screen empowers users to design and customize their own chatbots, allowing them to tailor the conversational experience to their specific needs.",
      image: "creation-screen.jpg"
    };
  </script>
  
  <section class="py-24">
    <div class="max-w-7xl mx-auto px-4">
      <h1 class="text-4xl font-bold mb-12 text-center">Chatbot UI Showcase</h1>
  
      <!-- Explore Page -->
      <div class="flex flex-col md:flex-row items-center mb-24">
        <div class="md:w-1/2 md:pr-12">
          <h2 class="text-3xl font-bold mb-4">{explorePageData.title}</h2>
          <p class="text-gray-400">{explorePageData.description}</p>
        </div>
        <div class="md:w-1/2 mt-8 md:mt-0">
          <img
            src={explorePageData.image}
            alt={explorePageData.title}
            class="w-full rounded-lg shadow-lg"
          />
        </div>
      </div>
  
      <!-- Chat Interface -->
      <div class="flex flex-col-reverse md:flex-row items-center mb-24">
        <div class="md:w-1/2 mt-8 md:mt-0">
          <img
            src={chatInterfaceData.image}
            alt={chatInterfaceData.title}
            class="w-full rounded-lg shadow-lg"
          />
        </div>
        <div class="md:w-1/2 md:pl-12">
          <h2 class="text-3xl font-bold mb-4">{chatInterfaceData.title}</h2>
          <p class="text-gray-400">{chatInterfaceData.description}</p>
        </div>
      </div>
  
      <!-- Creation Screen -->
      <div class="flex flex-col md:flex-row items-center">
        <div class="md:w-1/2 md:pr-12">
          <h2 class="text-3xl font-bold mb-4">{creationScreenData.title}</h2>
          <p class="text-gray-400">{creationScreenData.description}</p>
        </div>
        <div class="md:w-1/2 mt-8 md:mt-0">
          <img
            src={creationScreenData.image}
            alt={creationScreenData.title}
            class="w-full rounded-lg shadow-lg"
          />
        </div>
      </div>
    </div>
  </section>