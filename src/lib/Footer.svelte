<script>

  import HsLogo from "../assets/svg/hs-logo-white.svg";
  import LangIcon from "../assets/svg/language.svg";
  import BrazilFlag from "../assets/svg/brazil-flag.svg";
  import UsFlag from "../assets/svg/us-flag.svg";
  import GermanyFlag from "../assets/svg/germany-flag.svg";
  import SpainFlag from "../assets/svg/spain-flag.svg";
  import Fb from "../assets/svg/sm-fb.svg";
  import Ig from "../assets/svg/sm-ig.svg";
  import Tw from "../assets/svg/sm-tw.svg";
  import Yt from "../assets/svg/sm-yt.svg";

  const LinkCol = [
    {
      title: "Products",
      links: [
        { name: "Royalty Free Music", url: "#" },
        { name: "Sound Effects", url: "#" },
        { name: "Intros & Outros", url: "#" },
        { name: "AI Studio", url: "#" },
        { name: "ShortCap", url: "#" },
        { name: "Pricing", url: "#" }
      ]
    },
    {
      title: "For Business",
      links: [
        { name: "Business Contact Form", url: "#" },
        { name: "Custom Music", url: "#" },
        { name: "API Access", url: "#" },
        { name: "In-Store Music", url: "#" }
      ]
    },
    {
      title: "Resources",
      links: [
        { name: "Blog", url: "#" },
        { name: "Music for YouTube", url: "#" },
        { name: "Music for Streaming", url: "#" },
        { name: "Music for TikTok", url: "#" },
        { name: "Music for Podcasts", url: "#" },
        { name: "Music for Documentaries", url: "#" }
      ]
    },
    {
      title: "Plans & Programs",
      links: [
        { name: "Creator", url: "#" },
        { name: "Scale", url: "#" },
        { name: "Become an Affiliate", url: "#" },
        { name: "Education Program", url: "#" },
        { name: "Non-profit Program", url: "#" }
      ]
    },
    {
      title: "Legal & Support",
      links: [
        { name: "Business Contact", url: "#" },
        { name: "Custom Music", url: "#" },
        { name: "API Access", url: "#" },
        { name: "In-Store Music", url: "#" }
      ]
    },
  ];

  let open = new Set();
  function toggle(i) {
    if (open.has(i)) open.delete(i);
    else open.add(i);
    open = new Set(open);
  }
</script>


<footer class="flex flex-col bg-[#131313] text-neutral-200 w-screen justify-center ">
  <!-- top -->
  <div class="footer-top flex w-full max-w-[1360px] justify-between mx-auto py-[60px] px-[40px]">
    <!-- Left column -->
    <div class="left-col flex flex-col justify-between w-full max-w-[420px]">
      <!-- Logo and Description -->
      <div class="flex flex-col">
        <img src={HsLogo} alt="HookSounds logo" class="max-w-[315px]" />

      <p class="mt-[16px] text-sm leading-[24px] text-[#707070]">
        Original music. Worry-free licensing. Tools that speed you up. HookSounds gives you royalty-free tracks, SFX, and intros — made in-house — so you can tell better stories with sound, fast.
      </p>
      </div>

      <!-- Languages (desktop) -->
      <div class="lang-before mt-10">
        <div class=" flex gap-[4px] text-sm font-medium text-[#707070]"> <img src={LangIcon} alt="English" class="max-w-[20px] text-[#707070]" /> Languages</div>
        <ul class="mt-3 flex flex-wrap items-center gap-x-6 gap-y-2 text-sm text-neutral-400">
          <li>
            <a href="#" class="flex items-center gap-[8px] selected-lang pb-[4px]">
              <img src={UsFlag} alt="English" class="max-w-[16px]" />
              English
            </a>
          </li>
          <li>
            <a href="#" class="flex items-center gap-[8px] pb-[4px]">
              <img src={SpainFlag} alt="Espanol" class="max-w-[16px]" />
              Espanol
            </a>
          </li>
          <li>
            <a href="#" class="flex items-center gap-[8px] pb-[4px]">
              <img src={GermanyFlag} alt="Deutsch" class="max-w-[16px]" />
              Deutsch
            </a>
          </li>
          <li>
            <a href="#" class="flex items-center gap-[8px] pb-[4px]">
              <img src={BrazilFlag} alt="Português" class="max-w-[16px]" />
              Português
            </a>
          </li>
        </ul>
      </div>
    </div>


    <!-- Right Column - desktop -->
    <div class="footer-right right-desktop flex gap-[60px]">
       <div class="flex flex-col flex-wrap h-[440px] gap-y-[44px] gap-x-[60px]">
      {#each LinkCol as linkgroup}
        <div>
          <h4 class="text-sm font-semibold text-[#D6D6D6] text-left mb-[12px]">{linkgroup.title}</h4>
          <ul class="flex flex-col gap-[12px] text-sm text-neutral-400">
            {#each linkgroup.links as link}
              <li>
                <a class="whitespace-nowrap" href={link.url}>{link.name}</a>
              </li>
            {/each}
          </ul>
        </div>
      {/each}
    </div>

    </div>

    <!-- Right Column - mobile accordion -->
    <div class="right-mobile mt-4">
      {#each LinkCol as group, i}
        <div class="border-b border-[#222]">
          <button
            class="w-full flex items-center justify-between py-3 text-left"
            aria-expanded={open.has(i) ? 'true' : 'false'}
            on:click={() => toggle(i)}
          >
            <span class="text-sm font-semibold text-[#D6D6D6]">{group.title}</span>
            <svg
              class="size-4 transition-transform"
              style={`transform: rotate(${open.has(i) ? 180 : 0}deg);`}
              viewBox="0 0 20 20" fill="currentColor" aria-hidden="true"
            >
              <path d="M5.23 7.21a.75.75 0 011.06.02L10 10.2l3.71-2.97a.75.75 0 01.94 1.17l-4.24 3.4a.75.75 0 01-.94 0l-4.24-3.4a.75.75 0 01.02-1.19z"/>
            </svg>
          </button>
          {#if open.has(i)}
            <ul class="pb-2">
              {#each group.links as link}
                <li>
                  <a
                    href={link.url}
                    class="block whitespace-nowrap text-[14px] leading-[40px] text-[#707070] hover:text-white transition-colors"
                  >
                    {link.name}
                  </a>
                </li>
              {/each}
            </ul>
          {/if}
        </div>
      {/each}
    </div>

    <!-- Languages (after) shown under right column -->
    <div class="lang-after mt-6">
      <div class=" flex gap-[4px] text-sm font-medium text-[#707070]">
        <img src={LangIcon} alt="Languages" class="max-w-[20px] text-[#707070]" /> Languages
      </div>
      <ul class="mt-3 flex flex-wrap items-center gap-x-6 gap-y-2 text-sm text-neutral-400">
        <li>
          <a href="#" class="flex items-center gap-[8px] selected-lang pb-[4px]">
            <img src={UsFlag} alt="English" class="max-w-[16px]" />
            English
          </a>
        </li>
        <li>
          <a href="#" class="flex items-center gap-[8px] pb-[4px]">
            <img src={SpainFlag} alt="Espanol" class="max-w-[16px]" />
            Espanol
          </a>
        </li>
        <li>
          <a href="#" class="flex items-center gap-[8px] pb-[4px]">
            <img src={GermanyFlag} alt="Deutsch" class="max-w-[16px]" />
            Deutsch
          </a>
        </li>
        <li>
          <a href="#" class="flex items-center gap-[8px] pb-[4px]">
            <img src={BrazilFlag} alt="Português" class="max-w-[16px]" />
            Português
          </a>
        </li>
      </ul>
    </div>
  </div>

  <!-- bottom -->
  <div class=" bg-[#1A1A1A] w-full py-[12px]">
    <div class="bottom-panel flex justify-between max-w-[1360px] px-[40px] mx-auto items-center">
      <p class="text-xs text-[#707070]">Copyright © 2025 HookSounds - Royalty Free Music</p>
      <div class="flex items-center gap-4 text-neutral-400">
        <img src={Yt} alt="YouTube" class="text-[32px]" />
        <img src={Ig} alt="Instagram" class="text-[32px]" />
        <img src={Tw} alt="Twitter" class="text-[32px]" />
        <img src={Fb} alt="Facebook" class="text-[32px]" />
      </div>
    </div>
  </div>
</footer>

<style>
  li {
    font-size: 14px;
    line-height: 20px;
    text-align: left;
    color: #707070;
    transition: color 0.25s ease;
  }

  li:hover {
    color: #ffffff;
  }

  .selected-lang {
    color: white;
    border-bottom: 1px solid white;
  }

  .lang-after { display: none; }
  .right-mobile { display: none; }
  .right-desktop { display: block; }
  .lang-before { display: block; }

  /* Medium: 601px - 1024px */
  @media (min-width: 601px) and (max-width: 1024px) {
    /* Stack the top section, but keep normal link columns (no accordion) */
    .footer-top {
      flex-direction: column;
      gap: 32px;
      padding-left: 16px;
      padding-right: 16px;
    }
    .bottom-panel {
      padding-left: 16px;
      padding-right: 16px;
    }
    .footer-right {
      flex-direction: column;
      width: 100%;
      gap: 32px;
      padding-top: 24px;
    }
    /* Show desktop links, hide accordion; keep desktop languages */
    .right-desktop { display: block; }
    .right-mobile  { display: none; }
    .lang-before  { display: none; }
    .lang-after   { display: block; }
  }

  /* Small: ≤600px - accordion only */
  @media (max-width: 600px) {
    .footer-top {
      flex-direction: column;
      gap: 32px;
      padding-left: 16px;
      padding-right: 16px;
    }
    .bottom-panel {
      padding-left: 16px;
      padding-right: 16px;
    }
    .footer-right {
      flex-direction: column;
      width: 100%;
      gap: 32px;
      padding-top: 24px;
    }
    /* Hide desktop links, show accordion; move languages under right column */
    .right-desktop { display: none; }
    .right-mobile  { display: block;}
    .lang-before  { display: none; }
    .lang-after   { display: block;}
  }
</style>