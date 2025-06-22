---
layout: center
highlighter: shiki
css: unocss
colorSchema: dark
transition: fade-out
mdc: true
glowSeed: 4
title: Yak Shaving
remoteAssets: true
description: Anthony's journey of open source development. The process of
  ideation and project development, as well as finding one's own position and
  direction in the open source community. Helping you better understand and
  participate in open source.
addons:
  - slidev-addon-graph
---

![](/af-logo-animated.svg){.w-30.mt--10.mb-5}

<!--
みなさん、こんにちは。また お会いできて 嬉しいです。

この素晴らしい イベントに <ruby>再<rt>ふたた</rt></ruby>び 招待して いただき、ありがとうございます。スタッフの皆さん、ここまで お疲れ様です。

ちなみに、僕は最近日本語を本気で勉強し始めました。また、よろしくお願いします。

Good to meet you again! Thank a lot for having me here.
-->

---
layout: intro
class: pl-30
glowSeed: 14
---

# Anthony Fu

<div class="[&>*]:important-leading-10 opacity-80">

Core team member of {Vue} {Vite} and {Nuxt}<br>
Creator of {Vitest} {Slidev} {UnoCSS} {Type Challenges} {Elk}<br>
Maintainer of {ESLint Stylistic} {Shiki} {Twoslash}<br>
Working at {NuxtLabs}<br>

</div>

<div my-10 w-min flex="~ gap-1" items-center justify-center>
  <div i-ri-user-3-line op50 ma text-xl />
  <div><a href="https://antfu.me" target="_blank" class="border-none! font-300">antfu.me</a></div>
  <div i-ri-github-line op50 ma text-xl ml4/>
  <div><a href="https://github.com/antfu" target="_blank" class="border-none! font-300">antfu</a></div>
  <div i-ri-mastodon-line op50 ma text-xl ml4 />
  <div><a href="https://m.webtoo.ls/@antfu" target="_blank" class="border-none! font-300">antfu@webtoo.ls</a></div>
  <div i-ri-twitter-x-line op50 ma text-xl ml4/>
  <div><a href="https://twitter.com/antfu7" target="_blank" class="border-none! font-300">antfu7</a></div>
</div>

<img src="/anthony-hi.png" v-click absolute top-36 right-35 w-40 />
<img src="/hi.png" v-after absolute top-30 right-26 w-8 rotate-10 delay-300 />

<!-- <img src="https://antfu.me/avatar.png" rounded-full absolute top-38 right-15 w-40 /> -->

<!--
Let me introduce myself quickly, my name is Anthony Fu. [click] Hi!

I am the core team member of Vue, Vite and Nuxt. Also the creator of Vitest, Slidev, UnoCSS, and a few other open-source projects. I am currently at NuxtLabs on the framework team. You can find me on social media with the links below.
-->

---
layout: cover
title: Anthony's Roads to Open Source
---

<h1 flex="~ col">
<div text-2xl origin-top-left transition duration-500 :class="$clicks <= 2 ? 'scale-150' : 'op50'">
  <span v-click>Anthony's Roads to </span>
  <span>Open Source </span>
  <sup v-click>3/n</sup>
</div>
<div mt1 forward:delay-300 v-click>Yak Shaving<span font-jp v-click="4">「ヤク剃り」</span></div>
</h1>

<div abs-br mx-10 mb-10 flex="~ col gap-4 items-end" text-left v-click="1">
  <img src="/vue-fes-japan.svg" w-40 />
  <div text-sm opacity-75 mt--4>Oct. 19th 2024</div>
</div>

<!--
Today, I'd like to talk about Open Source again [click] and my own journey with open source.

[click] Like I mentioned last year, Open Source is a very big topic. So I break it into a series of talks, today's topic is the 3rd one.

[click] It's called Yak Shaving.

[click] 少し難しいですが、とりあえず、「ヤク剃り」と呼びたいです。 I hope it make a bit sense :P
-->

---

<div grid="~ cols-2 gap-10" mt4>

<div>
<div op50 font-serif italic mb--1>Part I</div>
<h2><span op75>The Set Theory</span><br><span font-jp>「集合論」</span></h2>
<img src="/part1-the-set-theory.png" rounded-lg shadow-xl w-120 border="~ gray/25" mt-6 />
</div>

<div>
<div op50 font-serif italic mb--1>Part II</div>
<h2><span op75>The Progressive Path</span><br><span font-jp>「進歩の道」</span></h2>
<img src="/part2-progressive.png" rounded-lg shadow-xl w-120 border="~ gray/25" mt-6 />
</div>

</div>

<div mt-14 text-xl text-center v-click>

Recordings on [antfu.me](https://antfu.me)

</div>

<!--
This series about Open Source consists of multiple parts, part 1 is The Set Theory that I gave the last year. And the second one is called "The Progressive Path", maybe someday I can do it again here in Japan. In the meantime, [click] you can always find the slides and recordings of my previous talks on my website.
-->

---
class: flex justify-center items-center gap-20 px40 text-xl
glow: bottom
---

<div transition duration-500 :class="$clicks === 0 ? 'translate-x-26 translate-y-20' : ''">

# Yak{.important-text-3em}

<div v-click forward:delay-600>

<div font-serif op75 text-2xl mb2>/jak/</div>

<div op50 italic text-base>a type of cattle with <br>long hair and long horns</div>

<span font-jp>ヤク；旄牛、犛牛</span>

</div>
</div>

<div transition duration-500 :class="$clicks === 0 ? 'translate-x--10 translate-y-20' : ''">

# Shaving{.important-text-3em}

<div v-click>

<div font-serif op75 text-2xl mb2>/ˈʃeɪ.vɪŋ/</div>

<div op50 italic text-base>to remove hair from the body<br><span op0>.</span></div>

<span font-jp>剃毛；髭剃り</span>

</div>
</div>

<!--
Back to our topic today. So, what is yak shaving? It seems to be pretty random right?

Let's break it down and see how it explains.

[click] Yak is a type of cattle with long hair and long horns. I don't really know to to pronounce the kanji in Japanese.

[click] Shaving means removing hair from the body.

Combine the two together, they still don't explain much.
-->

---
layout: center
---

<figure>
  <img src="/yak-shaving-by-david-revoy.jpg" rounded-2xl w-180 />
  <figcaption mt-2 op50 text-sm>
    Yak Shaving - by <a href="https://en.wikipedia.org/wiki/en:David_Revoy" title="w:en:David Revoy"><span title="French illustrator and creator of the webcomic ''Pepper&amp;Carrot''">David Revoy</span></a>
  </figcaption>
</figure>

<!--
Here is an illustration by David Revoy to give you some impressions of Yak Shaving on literal.
-->

---
glow: left
---

# An Example of "Yak Shaving"

<div mt-4 />

<div grid="~ cols-[4fr_2fr] gap-2">

<div w-130>
<v-clicks>

- You plan to <span text-red>write a blog post</span> today.

- You feel that existing tools don't quite meet your needs, so you decide to create your own <span text-orange>static site generator</span>.
- After spending half a month, you realize that frameworks don't work well, you decide to invent a <span text-green>new framework</span>.
- Another month passes, and you realize that you now need: <span text-violet>routing</span>, <span text-yellow>state management</span>, <span text-blue>IDE plugins</span>, <span text-teal>DevTools</span>, and more.
- Two years later...
- You find yourself inexplicably doing <span text-fuchsia>shaving a yak</span> in Tibet...
- Wait, what about your blog?

</v-clicks>
</div>

<div>
</div>
</div>

<YakExample absolute top-0 right-0 bottom-0 w-100 />

<!--
Well, I hope I didn't make it more confusing for you.

Yak Shaving is actually a term we use to describe a phenomenon in the tech world or our daily lives. Let me give you the same example.

[click] Let's say today we wanted to write a blog, but after some searching,

[click] We found that the existing tools don't quite meet our needs, so we decided to create our own static site generator.

[click] After spending half a month building, we realized that the frameworks don't work well with our generator, so we decided to invent a new framework.

[click] Another month passed, and we realized that we now need routing, state management, IDE plugins, DevTools, and more.

[click] Two years later...

[click] You somehow find yourself inexplicably shaving a yak in Tibet...

[click] But wait, what about your blog?
-->

---
class: flex flex-col gap-4 items-center justify-center
---

<div text-center flex="~ col gap-2" mt--4>
  <div text-4xl font-serif>Yak Shaving</div>
  <div text-xl v-click>Task chains triggered in the process of solving a problem,</div>
  <div text-xl mt--1 v-after><span v-mark.orange="2"> which ultimately <b>deviates</b> from the original goal</span></div>
  <div v-click="3" op75>*Usually a negative term</div>

  <div text-4xl font-jp mt8>「ヤク剃り」</div>
  <div font-jp text-xl mt2 v-click="1">問題解決中に生じた作業が、<span v-mark.orange="2">最終的に目標から逸れること</span>。</div>
  <div font-jp text-sm op75 mt1 v-click="3">＊否定的な意味を持つことが多い</div>
</div>

<div text-center mt-6 v-click="4">
  <div op50>Or in another words:</div>
  <div flex="~ gap-2 items-center"><div i-lucide-rabbit/> Down to the Rabbit Hole</div>
  <div font-jp>「ウサギの穴に落ちて」</div>
</div>

<!--
Just like the example we mentioned earlier, the term "Yak Shaving" refers to [click] a series of task chains that are triggered in the process of solving a problem, resulting [click] in deviating from the original goal. [click] This term usually carries a negative connotation and is often used to educate people to stay focused on the goal and avoid getting lost in endless details.

[click] This term also has a similar saying, called "Down to the Rabbit Hole."

Although this term is often used in a derogatory sense, what if we consider it from another perspective? What if we were able to accomplish all the things we mentioned? Wouldn't we potentially come up with a completely new solution?

Of course, we know that these things have a considerable level of complexity, and it is impossible to complete them on our own in a short period of time. It is easy to get lost in this process and eventually give up.

This is where the charm of open source comes in. If the solution you provide is compelling enough, you may receive help from more people in the open source community, harnessing the power of the community to create a complete ecosystem. Transforming "Yak Shaving" into a positive and proactive process.
-->

---
glowSeed: 10
---

# Utilizing "Yak Shaving"

<div font-jp op75 mt--2 ml--2>「ヤク剃り」を活用する</div>

<div v-click op75 mt1 text-sm>It can be a great way to come up with ideas<br>and provide strong motivation</div>

<div flex="~ col gap-4" py6>

<span v-click>
  <div flex="~ inline" text-blue mr2 px2 rounded bg-blue:10>Demand 要件</div><br>
  <span text-blue2>Start from your own needs, with a deeper <br>understanding of the problem</span>
</span>
<span v-click>
  <div flex="~ inline" text-rose mr2 px2 rounded bg-rose:10>Motivation 動機</div><br>
  <span text-rose2>Solve your own problems, and maybe help others</span>
</span>
<span v-click>
  <div flex="~ inline" text-yellow mr2 px2 rounded bg-yellow:10>Validation 検証</div><br>
  <span text-yellow2>Your needs are likely to be others' needs,<br>validate your ideas through the community</span>
</span>
<span v-click>
  <div flex="~ inline" text-green mr2 px2 rounded bg-green:10>Iterating 繰り返す</div><br>
  <span text-green2>Refine the design with discussion and contributions from community</span>
</span>

</div>

<div absolute left-150 top-20>
  <div
    absolute w-50 h-50 left-0 top-28 border="~ blue rounded-full"
    bg-blue:20 text-xl text-blue flex="~ items-center justify-center"
    v-click="2"
  >
    <div :class="{pr15: $clicks>2, pt8: $clicks>3}" transition-all duration-400 text-center>Your<br>Strength</div>
  </div>
  <div
    absolute w-50 h-50 left-34 top-28 border="~ rose rounded-full"
    bg-rose:20 text-xl text-rose flex="~ items-center justify-center"
    v-click="3"
  >
    <div pl15 :class="{pt8: $clicks>3}" transition-all duration-400 text-center>Your<br>Passion</div>
  </div>
  <div
    absolute w-50 h-50 left-17 top-0 border="~ amber rounded-full"
    bg-amber:20 text-xl text-amber flex="~ items-center justify-center"
    v-click="4"
  >
    <div pb10 text-center>Community<br>Needs</div>
  </div>
  <Arrow v-click="5" x1="160" y1="340" x2="170" y2="175" color-green  />
  <div
    v-click="5"
    absolute top-85 left-10 ws-nowrap
    border="~ green rounded-12px" px3 py1
    bg-green:20 text-lg text-green text-center
  >Practical and Sustainable<br>Open Source Projects</div>
</div>

<!--
Here, let's analyze how we can effectively utilize "Yak Shaving" to come up with suitable ideas for open source projects.

[click] I would say that "Yak Shaving" can be a great way to generate ideas and provide strong motivation.

[click] From the perspective of needs, because our "yak hair" comes from the problems we encounter ourselves, starting from our own needs allows us to have a deeper understanding of the problem and potential solutions.

[click] And our motivation for "shaving this yak" comes from solving our own problems and the possibility of helping others.

[click] Furthermore, our needs are likely to be shared by others, and we can validate our ideas through the open source community.

[click] Finally, through community discussions and contributions, we can iterate on our designs and improve our solutions.

By following this approach, we can gather the essential elements for the continuous development of open source projects - what we are skilled at and enjoy, and what the community needs.

This approach is much more practical than trying to guess what kind of open source projects will be successful.
-->

---

# Examples in Business

<!-- https://x.com/mattwensing/status/1552136584224509954 -->
<!-- https://fortune.com/longform/amazon-web-services-ceo-adam-selipsky-cloud-computing/ -->

<div grid="~ cols-2 gap-6" pt3>

<div v-click="1" bg-lime:10 border="~ lime/50 rounded-lg">
  <div flex="~ items-center gap-2" bg-lime:10 px4 py2 rounded><div i-logos-shopify text-xl /> Shopify</div>

  <div ml2 p2 text-lime1>
  <v-clicks :at="2">

  - Sell snowboards
  - Made an online store to scale
  - Ended up building e-commerce platform

  </v-clicks>
  </div>
</div>

<div v-click="5" bg-gray:10 border="~ gray/50 rounded-lg">
  <div flex="~ items-center gap-2" bg-gray:10 px4 py2 rounded><div i-logos-unrealengine-icon text-xl invert-100 /> EpicGame</div>

  <div ml2 p2 text-gray1>
  <v-clicks :at="6">

  - Trying to make a 3D game
  - Found 3D was hard, made a game engine
  - Licensing the Unreal Engine

  </v-clicks>
  </div>
</div>

<div v-click="9" bg-orange:10 border="~ orange/50 rounded-lg">
  <div flex="~ items-center gap-2" bg-orange:10 px4 py2 rounded><div i-logos-aws invert-100 hue-rotate-180 text-xl /> Amazon</div>

  <div ml2 p2 text-orange1>
  <v-clicks :at="10">

  - E-commerce for Amazon Online Store
  - Performance couldn't keep up with growth, improved cloud service infrastructure
  - Renting cloud services
  - AWS is now Amazon's largest revenue source

  </v-clicks>
  </div>
</div>

<div v-click="14" bg-pink:10 border="~ pink/50 rounded-lg">
  <div flex="~ items-center gap-2" bg-pink:10 px4 py2 rounded><div i-logos-slack-icon text-xl /> Slack</div>

  <div ml2 p2 text-pink2>
  <v-clicks :at="15">

  - Started to make a game
  - Game failed, but made an internal chat tool
  - Pivoted to focus on the tool
  - Providing team communication tools for enterprises

  </v-clicks>
  </div>
</div>

</div>

<!--
Let's take some real examples of how this works [click] in the business world.

[click] So we know Shopify. At the very begining, they actually started by selling snowboards,
[click] At some point, they want to scale up their business, so they started to build an online store to sell more snowboards.
[click] While they build the store for themselves, they found out that this can also be a common need for other kind of stores - which they end up building the e-commerce store platform we know today.

[click] Then we have Epic Games.
[click] They first started by trying to make a 3D game,
[click] But they found out that making 3D games is hard, so they made a game engine to make things easier,
[click] The engine is now called Unreal Engine, where they are now licensing it to other game developers.

[click] Similarly, we have Amazon [click] that first started working on [click] the infrastructure for their store, and [click] end up have AWS, [click] which became Amazon's largest revenue source today.

[click] Then we have Slack, [click] first work on a game [click] that eventually failed, [click] but their internal communication app [click] now becomes their main bussiness and selling to enterprises.
-->

---
glow: right
---

# Idea Generation and Implementation Process

<div flex="~ col gap-1" py5>
  <div v-click flex="~ items-center gap-2"><div text-2xl i-ph-lightbulb-duotone text-yellow /> Understand the problem and consider possible solutions</div>
  <div v-click i-ph-arrow-down op25 ml-1 text-sm />
  <div v-after flex="~ items-center gap-2"><div text-2xl i-ph-magnifying-glass-duotone text-blue /> Search for existing libraries in the market</div>
  <div v-click absolute left-108 top-41 bg-blue:10 border="~ blue/50 rounded-lg" p2 py1>
    <div text-sm text-blue2>
      Contribute and provide suggestions
    </div>
  </div>
  <div v-click i-ph-arrow-down op25 ml-1 text-sm />
  <div flex="~ items-center gap-2">
    <div text-2xl i-ph-code-duotone text-green v-after />
    <span v-after>Implement MVP locally; validate solution feasibility;</span>
    <span v-click text-yellow font-bold flex="~ gap-1 items-center">Return to main task<div i-ph-arrow-square-out-duotone /></span>
  </div>
  <div v-click absolute left-175 top-32 bg-yellow:10 border="~ yellow/50 rounded-lg" p2 w-54>
    <div text-sm text-yellow2>
      Avoid "deep dive trap" and return to the main task after completing necessary functionality. Further details can be addressed later.
    </div>
  </div>
  <div v-click i-ph-arrow-down op25 ml-1 text-sm />
  <div v-after flex="~ items-center gap-2"><div text-2xl i-ph-books-duotone text-teal /> Extract implementation into a library; brief docs with motivation; open-source the repository</div>
  <div v-click i-ph-arrow-down op25 ml-1 text-sm />
  <div v-after flex="~ items-center gap-2"><div text-2xl i-ph-megaphone-duotone text-rose /> Promote appropriately; gather community feedback</div>
  <div v-click absolute left-132 top-77 bg-rose:10 border="~ rose/50 rounded-lg" p2 py1>
    <div text-sm text-rose2>
      Encourage summarizing as technical blog posts
    </div>
  </div>
  <div v-click i-ph-arrow-down op25 ml-1 text-sm />
  <div v-after flex="~ items-center gap-2"><div text-2xl i-ph-chats-circle-duotone text-violet /> Community validation</div>
    <div v-click flex="~ items-center gap-2" pl-4 mt4><div i-ph-arrow-elbow-down-right op25 ml-1 text-sm /><div text-2xl i-ph-seal-question-duotone text-gray /> No response: Solved your own problem, summarized the solution, still a good outcome</div>
    <div v-click flex="~ items-center gap-2" pl-4 mt4><div i-ph-arrow-elbow-down-right op25 ml-1 text-sm /><div text-2xl i-ph-treasure-chest-duotone text-orange /> Positive response: Engaged in community discussions, bug reporting, helped others and yourself</div>
</div>

<!--
So, let's get back to open source. Here, I would like to briefly outline what I personally consider as the process of generating open source tool ideas and their implementation using the concept of "Yak Shaving".

[click] When we encounter a problem, the first step is to take some time to understand the problem and consider possible solutions. Think about whether it could be a general solution that others might have encountered.

[click] Then, we can search if there are existing libraries in the market. Following the principle of "do less work if possible," it's best to reuse existing solutions. [click] At the same time, you can contribute to open source by providing feedback and suggestions to improve existing solutions.

If you can't find an existing tool that meets your expectations or if the existing tools don't fit your needs but could be a general solution, congratulations! You may have a viable idea. [click] At this point, you can start implementing your own tool by first creating an MVP (Minimum Viable Product) to validate the feasibility of your idea. When designing, keep in mind the idea of decoupling interfaces for future extensibility.

[click] The key to avoiding the yak-shaving trap is "to get back in time." [click] You don't need to make it perfect; it just needs to meet your current needs. The important thing is to return to your main task in a timely manner. You can refine the details of the tool later.

[click] Assuming we have completed our main task and have some extra time, if you are still interested in the tool, you can extract it into a separate library, write brief documentation explaining your motivation for creating the tool, and then open-source the repository.

[click] Once all of this is done, you can promote your repository appropriately. Share it with colleagues, post it on social media, and so on. This will help gather feedback from the community and understand the pros and cons of your solution.

[click] I highly encourage you to write a technical blog post summarizing your journey during this process. Share the problems you encountered, the solutions you proposed, and the lessons you learned. This not only for introducing your tool to others, but also serves as a valuable technical resource. Even people who don't directly use your tool can learn something from your exploration. Even in the worst case scenario, if our idea is ultimately proven to be unfeasible, this blog post can still be a valuable exploration. Just like in academic papers, the failure to validate a hypothesis is also an important contribution.

[click] In the end, we can use the open source community to validate the generality of our solution.

[click] If our project doesn't gain much attention in the end, that's okay. Lower our expectation, at least we solved our own problem, summarized the solution, and gained valuable experience.

[click] But if our tool is fortunate enough to be embraced by the community, we will naturally receive notifications from GitHub indicating that others are starting to contribute. At this point, we can start discussing with the community, accepting feedback, fixing bugs, adding new features, and so on. Throughout this process, you will find that your tool becomes more refined, and while helping others, the improved tool will also benefit you.

(Pause)
-->

---
layout: center
---

# Anthony's Road of Yak Shaving {.important-text-5xl}

<!--
That said, here I'd like to share some of my journey of Yak Shaving, for your reference and hope can bring you some inspiration.
-->

---
clicks: 46
zoom: 0.75
layout: none
class: flex h-full w-full
glow: topmost
glowSeed: 18
---

<RenderWhen context="visible">
  <YakMap />
</RenderWhen>

<div flex="~ items-center gap-3" fixed right-0 top-0 rounded-bl-2rem p5 backdrop-blur-md>
  <div text-5xl>
    🐃
  </div>
  <div flex="~ col">
    <a href="https://antfu.me" text-sm op50 hover:underline target="_blank">Anthony Fu's</a>
    <a text-2xl href="https://github.com/antfu/yak-shaving-map" target="_blank" hover:underline>
      Yak Map
    </a>
  </div>
</div>

<!--
My journey in open source started with a project built on Nuxt called BreadSplit around 5 years ago, an app for managing shared wallets. At that point, we wanted to internationalization, but I found that there were no good tools for managing the translations in VS Code, [click] so I made the extension called `i18n Ally` to improve the experience.

[click] From this project, I also extracted the composables we use internally out to become VueUse. At that time, the Vue 3 was not yet ready, and the community still hesitated about the new Composition API. I was trying to make VueUse work on both Vue 2 and Vue 3 to cover more users and make the transition easier (kinda like the "Set Theory" mindset we talked about last year). [click] I started to contribute to the  `@vue/composition-api` plugin to make sure the behavior aligns with Vue 3. [click] This project later got me into the Vue and also later came up with the library `vue-demi`.

[click] As I joined the Vue team, I started to dig deeper into the composition API and the reactivity system. [click] It got me to create Vue Reactivity experiments, and ReactiVue, which hook VUe's reactivity API into React.

[click] And then Vite came out; [click] I started trying the new build tool with Vue 3 and made the icon explorer `Icones`. It's my first app built on top of Vite. From that as the starting point, I found out that there are so many things missing in Vite because it was very young. Then I built [click] `vite-pwa`, and a bunch of plugins like [click] auto-imports, components, icons etc to enhance the developer experience of Vite.

[click] Since I worked a lot with icons, I started to involve with the Iconify project, [click] combining with my experience of VS Code extension when making `i18n ally`, [click] I made `Iconify IntelliSense` to display icons inside our code.

[click] From the work on Vite plugins, I made `vite-plugin-inspect` to see the internal of Vite's pipeline and help myself to debug.

[click] By combining all my exploration of the vite ecosystem, I extract them into the template called `Vitesse`, which somehow became quite popular. On top of that, I also made a variation [click] called `vitesse-webext` for browser extensions, and [click] a small library for it.

[click] With Vite becoming more and more mature, I started to migrate my blog site to Vite. Along the way, I made [click] a vite plugin for compiling markdown, and [click] `vite-ssg` for static site generator (what a coincidence to our previous examples :P)

[click] When it comes to styling, I found the project called Windi CSS, which was more like an on-demand version of Tailwind, and I started to contribute and build a plugin for it.

[click] At the same time, I have to prepare a talk about Vue. As a side product of my procrastination, I made Slidev, the slides maker that you are looking at right now. [click] from Slidev, I also made `drauu` for drawing on slides, and `broz` for taking beautiful screenshots.

[click] Then, with the experience I got with Windi CSS, I made UnoCSS, an atomic CSS engine that is highly extensible. [click] Combining with Iconify, I came up with the Pure CSS icons solution. Which I think is still the best approach for icons today.

[click] From my work on Vitesse, I got invited to work on Nuxt. [click] From my work at Nuxt [click], I made `unplugin` to allow plugins to support both Vite and webpack easily, and [click] `unimport` to unify auto-import usages.

To improve Nuxt' SSR experience in development, Pooya and I came up with the SSR runtime for Vite that [click] later became `vite-node`. Having the foundation of `vite-node`, it made [click] `Vitest` possible. When making Vitest, we need a way to communicate between worker threads and main threads. [click] I came up with the library `birpc` to handle remote procedure calls.

With the foundation work of `vite-plugin-inspect` and `birpc`, [click] I started to work on `Nuxt DevTools` to present you the internal of your Nuxt app and help you to understand it better. Then we have [click] `magicast` to write changes back to your config easier; We build [click] Elk the maston client with Nuxt. [click] Then the Nuxt Playground `learn.nuxt.com`.

Amount all these project, highlighting code becomes a tricky thing to do right, so [click] I started to work on improve Shiki, and end up completely rewriting it. From it I also made [click] `shiki-magic-move`, [click] `shiki/monaco`, [click] Twoslash integration, etc.

[click] Then I somehow get trapped into the ESLint ecosystem, [click] I started to take over the ESLint Stylistic project, I made the [click] config inspector which later become official, and a lot other small utilities. [click] All these experience I got working on them later be utilized to make the [click] Nuxt ESLint module possible.

Wooof. You can see I really down to the rabbit hole super deep. [click]

I hope my experience can inspire everyone. Each person has their own strengths and interests, and the birth of many projects has a certain timeliness and randomness. Everyone's journey of growth and yak shaving map will certainly be different. I am also very much looking forward to seeing your versions.
-->

---
layout: center
glow: center
---

<h1 important-text-5xl><span transition duration-700 inline-block :class="$clicks === 0 ? 'translate-x-40' : ''">Open Source</span> <span forward:delay-400 v-click>is about Giving</span></h1>

<div text-2xl op75 font-jp v-after forward:delay-800>オープンソースは与えることです</div>

<!--
Before we call it a day, I would like to reiterate the expectations on open source. While open source is a broad topic, different people may have different interpretations and expectations of open source. [click] However, I believe that Open Source is about Giving.
-->

---
glow: bottom
---

# Expections on Open Source

<div grid="~ cols-3 gap-2" py4>
  <div v-click flex="~ col gap-1" p4 rounded bg-violet:15 text-violet1>
    <div text-2xl i-ph-gift-duotone text-violet mb2 />
    <div>Open Source is a Gift</div>
    <div text-sm op60>オープンソースは贈り物です</div>
  </div>

  <div v-click flex="~ col gap-1" p4 rounded bg-orange:15 text-orange1>
    <div text-2xl i-ph-target-duotone text-orange mb2 />
    <div>Reciprocity is not the Goal</div>
    <div text-sm op60>返礼は目的ではない</div>
  </div>

  <div v-click flex="~ col gap-1" p4 rounded bg-rose:15 text-rose1>
    <div text-2xl i-ph-hand-heart-duotone text-rose mb2 />
    <div text-base>Enjoy Sharing and Collaboration</div>
    <div text-sm op60>共有と協力の過程を楽しむ</div>
  </div>

  <div v-click flex="~ col gap-1" p4 rounded bg-green:15 text-green1>
    <div text-2xl i-ph-hand-waving-duotone text-green mb2 />
    <div text-base>Open source is more than Code</div>
    <div text-sm op60>コード以上のものです</div>
  </div>

  <div v-click flex="~ col gap-1" p4 rounded bg-blue:15 text-blue1>
    <div text-2xl i-ph-users-three-duotone text-blue mb2 />
    <div text-base>Community is the Core</div>
    <div text-sm op60>核はコミュニティです</div>
  </div>
</div>

<div absolute bottom-10 v-click>
<div op75 mb1>Recommanded Articles</div>

- [Open-Source is a Gift](https://www.redotheweb.com/2011/11/13/open-source-is-a-gift.html)<span op50 text-sm> - François Zaninotto</span>
- [The open source gift exchange](https://world.hey.com/dhh/the-open-source-gift-exchange-2171e0f0)<span op50 text-sm> - David Heinemeier Hansson</span>
- [Mental Health in Open Source](https://antfu.me/posts/mental-health-oss)<span op50 text-sm> - Anthony Fu</span>

</div>

<!--
I think everyone has their own motivations and goals for participating in open source. It could be to improve their skills, to have better job opportunities, or simply to make the world a better place, among other reasons. Open source is a diverse community, and all these motivations are valid. However, different motivations may lead to different expectations of open source. Here, I want to talk about adjusting our expectations of open source, which could help us better integrate into the community and enjoy the benefits of open source.

[click] I like to think of open source projects as gifts. When we use someone else's open source project, it's like receiving a free lunch from a stranger. And when we contribute to open source, it's like giving a gift, a gesture from our hearts. [click] When you give a gift, you may often receive something in return, but reciprocity should not be the primary goal of giving. [click] For me, the process of open source itself is the goal. I enjoy sharing and working together with others to solve problems. When you stop focusing on the rewards, you will enjoy the process more, and in the long run, you may receive even more, just like how I am grateful for the opportunity to stand here today and share my thoughts with all of you, thanks to the opportunities provided by open source. [click] Open source is not just about code; it is a community, a culture, a spirit. [click] When you become part of this community, you will meet a group of generous and helpful people. They will appreciate your contributions, and you will also receive gratitude and assistance from many others. I believe this spirit of mutual support is at the core of open source.

[click] If you have a deeper interest in this topic, I recommend reading these articles. The PDF of the slides can be found on my website.
-->

---
layout: intro
class: text-center pb-5
glowX: 50
glowY: 120
---

# ハッピーハッキング！{.font-jp}

<div font-jp mt--2 text-2xl op75>ありがとうこざいます！</div>

<div pt-2 op50>

Slides on [antfu.me](https://antfu.me)

</div>

<!--
Finally, I hope everyone can find their own place in the open source community and enjoy the process. Wishing you all the best in your open source journey.

お疲れさまでした！ありがとうございました。アフターパーティーを お楽しみください。
-->
