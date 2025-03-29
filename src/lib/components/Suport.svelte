<script>
    let activeIndex = null;
  
    const faqs = [
      {
        question: "Cum se pot încărca rezultatele financiare anuale ale firmei?",
        answer: "Accesezi secțiunea de încărcare fișiere și urmezi pașii indicați pentru a adăuga fișierele contabile ale firmei."
      },
      {
        question: "Se pot descărca rezultatul analizei financiare?",
        answer: "Da, poți descărca un raport complet în format PDF, după ce analiza a fost generată."
      },
      {
        question: "Cui se adresează platforma și ce tip de utilizatori o pot folosi eficient?",
        answer: "Platforma este dedicată antreprenorilor, analiștilor financiari și consultanților care doresc să ia decizii bazate pe date clare și automate."
      },
      {
        question: "Care este procedura în cazul apariției unor erori în utilizarea platformei?",
        answer: "Poți contacta echipa noastră de suport sau accesa ghidurile din secțiunea de helpdesk."
      },
      {
        question: "Ce forme de suport tehnic și documentație sunt puse la dispoziția utilizatorilor?",
        answer: "Ai la dispoziție un centru de asistență, tutoriale video și suport live pentru orice întrebare."
      },
    ];
  
    function toggle(index) {
      activeIndex = activeIndex === index ? null : index;
    }
  </script>
  
  <section class=" py-28 px-4 my-[100px]">
    <h2 class="text-4xl text-center mb-16 font-semibold"> Întrebări </h2>
    <div class=" mx-auto bg-white rounded-2xl p-6 md:p-4 shadow-lg max-w-[75%]">
      {#each faqs as faq, index}
        <div class=" last:border-none text-lg">
          <button
            class={`w-full text-left py-8 px-8 rounded-xl transition-colors flex justify-between items-center ${
              activeIndex === index ? 'bg-gray-100 font-semibold' : 'hover:bg-gray-50'
            }`}
            on:click={() => toggle(index)}
          >
            {faq.question}
            <svg
              class="h-5 w-5 transition-transform"
              class:rotate-180={activeIndex === index}
              fill="none"
              stroke="currentColor"
              stroke-width="2"
              viewBox="0 0 24 24"
            >
              <path stroke-linecap="round" stroke-linejoin="round" d="M19 9l-7 7-7-7" />
            </svg>
          </button>
  
          {#if activeIndex === index}
            <div class="px-12 pb-4 pt-2 mt-[12.5px] text-base text-[#3b3b57]">
              {faq.answer}
            </div>
          {/if}
        </div>
      {/each}
    </div>
  </section>
  