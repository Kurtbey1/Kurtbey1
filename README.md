<svg viewBox="0 0 900 460" width="900" height="460" fill="none" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" role="img" aria-label="Abd Elrahman Alqudah, Backend Engineer, DevSecOps">
  <style>
    .base { font-family: -apple-system, 'Segoe UI', Roboto, Ubuntu, Helvetica, Arial, sans-serif; }
    .mono { font-family: ui-monospace, 'SF Mono', 'Cascadia Code', 'Fira Code', Consolas, monospace; }
    .serif { font-family: Georgia, 'Times New Roman', serif; }

    @keyframes rise { from { opacity:0; transform: translateY(12px) } to { opacity:1; transform: translateY(0) } }
    @keyframes lineSweep {
      0%   { opacity:0; transform: translateX(0) }
      8%   { opacity:1 }
      70%  { opacity:1 }
      85%  { opacity:0; transform: translateX(196px) }
      100% { opacity:0; transform: translateX(196px) }
    }
    @keyframes chipSweep {
      0%   { transform: skewX(-20deg) translateX(0) }
      55%  { transform: skewX(-20deg) translateX(780px) }
      100% { transform: skewX(-20deg) translateX(780px) }
    }
    @keyframes glow { 0%,100% { opacity:.55 } 50% { opacity:1 } }
    @keyframes ring { 0%,100% { opacity:.3; r:26 } 50% { opacity:.8; r:31 } }
    @keyframes blink { 0%,49% { opacity:1 } 50%,100% { opacity:0 } }
    @keyframes scan {
      0%   { transform: translateY(-190px); opacity:0 }
      6%   { opacity:.9 }
      48%  { opacity:.9 }
      54%  { opacity:0 }
      100% { transform: translateY(190px); opacity:0 }
    }
    @keyframes flicker { 0%,100% { opacity:.7 } 45% { opacity:1 } 55% { opacity:.4 } }

    .rise   { animation: rise .9s ease both }
    .lsweep { animation: lineSweep 3.4s ease-in-out infinite; animation-delay: 1s }
    .csweep { animation: chipSweep 5.5s ease-in-out infinite; animation-delay: 1.6s }
    .glowPulse { animation: glow 3.2s ease-in-out infinite }
    .ringPulse { animation: ring 3.2s ease-in-out infinite; transform-box: fill-box; transform-origin: center }
    .cursor { animation: blink 1s step-end infinite }
    .scanline { animation: scan 6.5s ease-in-out infinite }
    .flick { animation: flicker 2.6s ease-in-out infinite }

    .r1 { animation-delay: .15s } .r2 { animation-delay: .3s } .r3 { animation-delay: .45s }
    .r4 { animation-delay: .6s } .r5 { animation-delay: .75s } .r6 { animation-delay: .9s }

    /* hovering the rules gate reveals what it's actually doing (only when the SVG
       is opened as a document — img-tag embeds never receive hover) */
    .gateWrap { transition: opacity .6s ease }
    .gateNote { opacity: 0; transition: opacity .6s ease; }
    .diagram:hover .gateNote { opacity: 1; }
    .diagram:hover .gateHint { opacity: 0; }

    @media (prefers-reduced-motion: reduce) {
      * { animation: none !important; }
      .scanline, .lsweep { opacity: 0 !important; }
    }
  </style>

  <defs>
    <linearGradient id="bg" x1="0" y1="0" x2="900" y2="460" gradientUnits="userSpaceOnUse">
      <stop offset="0" stop-color="#060B18"/>
      <stop offset=".55" stop-color="#0E2340"/>
      <stop offset="1" stop-color="#050B14"/>
    </linearGradient>
    <linearGradient id="border" x1="0" y1="0" x2="900" y2="460" gradientUnits="userSpaceOnUse">
      <stop offset="0" stop-color="#2E6FD9"/>
      <stop offset=".5" stop-color="#123A66"/>
      <stop offset="1" stop-color="#C9A227"/>
    </linearGradient>

    <linearGradient id="nameGrad" gradientUnits="userSpaceOnUse" x1="0" y1="0" x2="220" y2="220" spreadMethod="repeat">
      <stop offset="0"   stop-color="#123A66"/>
      <stop offset=".28" stop-color="#2E6FD9"/>
      <stop offset=".55" stop-color="#F3D7C4"/>
      <stop offset=".78" stop-color="#C9A227"/>
      <stop offset="1"   stop-color="#123A66"/>
      <animateTransform attributeName="gradientTransform" type="translate" from="0 0" to="220 220" dur="7s" repeatCount="indefinite"/>
    </linearGradient>

    <linearGradient id="line" x1="64" y1="0" x2="330" y2="0" gradientUnits="userSpaceOnUse">
      <stop offset="0" stop-color="#2E6FD9"/>
      <stop offset="1" stop-color="#2E6FD9" stop-opacity="0"/>
    </linearGradient>
    <linearGradient id="lineSpark" x1="0" y1="0" x2="1" y2="0">
      <stop offset="0" stop-color="#C9A227" stop-opacity="0"/>
      <stop offset=".5" stop-color="#F9E8B8"/>
      <stop offset="1" stop-color="#C9A227" stop-opacity="0"/>
    </linearGradient>
    <linearGradient id="silver" x1="0" y1="0" x2="1" y2="0">
      <stop offset="0" stop-color="#FFFFFF" stop-opacity="0"/>
      <stop offset=".5" stop-color="#F3D7C4" stop-opacity=".22"/>
      <stop offset="1" stop-color="#FFFFFF" stop-opacity="0"/>
    </linearGradient>
    <linearGradient id="scanGrad" x1="0" y1="0" x2="0" y2="1">
      <stop offset="0" stop-color="#2E6FD9" stop-opacity="0"/>
      <stop offset=".5" stop-color="#4FA3FF" stop-opacity=".8"/>
      <stop offset="1" stop-color="#2E6FD9" stop-opacity="0"/>
    </linearGradient>
    <radialGradient id="nodeGlow" cx=".5" cy=".5" r=".5">
      <stop offset="0" stop-color="#4FA3FF" stop-opacity=".9"/>
      <stop offset="1" stop-color="#4FA3FF" stop-opacity="0"/>
    </radialGradient>
    <radialGradient id="goldGlow" cx=".5" cy=".5" r=".5">
      <stop offset="0" stop-color="#F9E8B8" stop-opacity=".95"/>
      <stop offset="1" stop-color="#C9A227" stop-opacity="0"/>
    </radialGradient>
    <radialGradient id="vignette" cx=".5" cy=".5" r=".72">
      <stop offset=".55" stop-color="#000000" stop-opacity="0"/>
      <stop offset="1" stop-color="#000000" stop-opacity=".4"/>
    </radialGradient>

    <pattern id="blueprint" width="34" height="34" patternUnits="userSpaceOnUse">
      <path d="M34,0 L0,0 L0,34" fill="none" stroke="#2E6FD9" stroke-opacity=".08" stroke-width="1"/>
    </pattern>

    <filter id="soft" x="-60%" y="-60%" width="220%" height="220%"><feGaussianBlur stdDeviation="1.4"/></filter>
    <filter id="mist" x="-80%" y="-80%" width="260%" height="260%"><feGaussianBlur stdDeviation="8"/></filter>

    <clipPath id="chipsClip">
      <rect x="64"  y="272" width="88"  height="26" rx="13"/>
      <rect x="159" y="272" width="64"  height="26" rx="13"/>
      <rect x="230" y="272" width="70"  height="26" rx="13"/>
      <rect x="307" y="272" width="100" height="26" rx="13"/>
      <rect x="64"  y="308" width="58" height="26" rx="13"/>
      <rect x="129" y="308" width="42" height="26" rx="13"/>
      <rect x="178" y="308" width="46" height="26" rx="13"/>
      <rect x="231" y="308" width="52" height="26" rx="13"/>
      <rect x="290" y="308" width="64" height="26" rx="13"/>
      <rect x="361" y="308" width="46" height="26" rx="13"/>
    </clipPath>

    <clipPath id="diagramClip">
      <rect x="470" y="60" width="380" height="340" rx="12"/>
    </clipPath>
  </defs>

  <rect x="1.5" y="1.5" width="897" height="457" rx="22" fill="url(#bg)" stroke="url(#border)" stroke-width="1.5"/>
  <rect x="470" y="60" width="380" height="340" rx="12" fill="url(#blueprint)"/>
  <ellipse cx="700" cy="180" rx="260" ry="180" fill="#123A66" opacity=".14" filter="url(#mist)"/>

  <g class="base">

    <!-- left: identity block -->
    <g class="rise">
      <text x="64" y="70" font-size="13" font-weight="700" fill="#C9A227" letter-spacing="4" class="mono">SYSTEMS &#183; SECURITY &#183; BACKEND</text>
      <text x="64" y="118" font-size="34" font-weight="700" fill="url(#nameGrad)" letter-spacing=".2" class="serif">Abd Elrahman Alqudah</text>
      <text x="64" y="148" font-size="15" font-weight="600" fill="#4FA3FF" letter-spacing="3" class="mono">BACKEND ENGINEER &#183; DEVSECOPS</text>
      <rect x="64" y="167.5" width="266" height="2" rx="1" fill="url(#line)" opacity=".6"/>
      <rect class="lsweep" x="64" y="166.8" width="70" height="3.4" rx="1.7" fill="url(#lineSpark)"/>
    </g>

    <g class="rise r2 mono" font-size="12.5" fill="#A9B8D9">
      <text x="64" y="200">I build backend systems where security is</text>
      <text x="64" y="220">part of the architecture &#8212; schemas, queues,</text>
      <text x="64" y="240">access rules, and the infra behind them.</text>
    </g>

    <g class="rise r3">
      <g fill="#0B1A30" stroke="#123A66" stroke-width="1">
        <rect x="64"  y="272" width="88"  height="26" rx="13"/>
        <rect x="159" y="272" width="64"  height="26" rx="13"/>
        <rect x="230" y="272" width="70"  height="26" rx="13"/>
        <rect x="307" y="272" width="100" height="26" rx="13"/>
        <rect x="64"  y="308" width="58" height="26" rx="13"/>
        <rect x="129" y="308" width="42" height="26" rx="13"/>
        <rect x="178" y="308" width="46" height="26" rx="13"/>
        <rect x="231" y="308" width="52" height="26" rx="13"/>
        <rect x="290" y="308" width="64" height="26" rx="13"/>
        <rect x="361" y="308" width="46" height="26" rx="13"/>
      </g>
      <g font-size="10" font-weight="600" fill="#F3D7C4" text-anchor="middle" class="mono">
        <text x="108" y="288">ASP.NET Core</text>
        <text x="191" y="288">Postgres</text>
        <text x="265" y="288">Cloud Run</text>
        <text x="357" y="288">GitHub Actions</text>
        <text x="93"  y="324">Laravel</text>
        <text x="150" y="324">Go</text>
        <text x="201" y="324">Redis</text>
        <text x="257" y="324">Docker</text>
        <text x="322" y="324">Firebase</text>
        <text x="384" y="324">Vault</text>
      </g>
      <g clip-path="url(#chipsClip)">
        <rect class="csweep" x="-160" y="264" width="110" height="80" fill="url(#silver)"/>
      </g>
    </g>

    <g class="rise r4">
      <rect x="64" y="356" width="9" height="9" rx="2" fill="#2E6FD9" class="glowPulse"/>
      <text x="82" y="365" font-size="14" font-style="italic" fill="#F3D7C4" class="mono">Systems that fail predictably.</text>
    </g>

    <g class="rise r5 mono" font-size="13" fill="#8FA3C9">
      <circle cx="69" cy="401" r="2.5" fill="#2E6FD9"/>
      <text x="82" y="406">abdelrahmanalqudah.dev</text>
      <circle cx="69" cy="421" r="2.5" fill="#C9A227"/>
      <text x="82" y="426">linkedin.com/in/abd-elarhman</text>
    </g>

  </g>

  <!-- right: a small piece of the actual architecture -->
  <g class="diagram" clip-path="url(#diagramClip)">
    <rect class="scanline" x="470" y="60" width="380" height="6" fill="url(#scanGrad)"/>

    <!-- connectors, drawn first so nodes sit on top -->
    <g stroke="#2E6FD9" stroke-opacity=".55" stroke-width="1.6" fill="none">
      <path id="p1" d="M520,140 L600,140"/>
      <path id="p2" d="M660,140 L740,140"/>
      <path id="p3" d="M740,140 L740,220"/>
      <path id="p4" d="M740,220 L660,220"/>
      <path id="p5" d="M600,220 L600,280"/>
      <path id="p6" d="M660,140 L660,80" stroke-dasharray="3 4"/>
    </g>

    <!-- packets riding the connectors -->
    <circle r="3.4" fill="url(#nodeGlow)"><animateMotion dur="2.6s" repeatCount="indefinite" begin="0s"><mpath xlink:href="#p1"/></animateMotion></circle>
    <circle r="3.4" fill="url(#nodeGlow)"><animateMotion dur="2.6s" repeatCount="indefinite" begin=".6s"><mpath xlink:href="#p2"/></animateMotion></circle>
    <circle r="3.4" fill="url(#nodeGlow)"><animateMotion dur="2.2s" repeatCount="indefinite" begin="1.1s"><mpath xlink:href="#p3"/></animateMotion></circle>
    <circle r="3.4" fill="url(#nodeGlow)"><animateMotion dur="2.6s" repeatCount="indefinite" begin="1.5s"><mpath xlink:href="#p4"/></animateMotion></circle>
    <circle r="3.4" fill="url(#nodeGlow)"><animateMotion dur="2.2s" repeatCount="indefinite" begin="2s"><mpath xlink:href="#p5"/></animateMotion></circle>
    <circle r="2.6" fill="url(#goldGlow)"><animateMotion dur="1.8s" repeatCount="indefinite" begin=".3s"><mpath xlink:href="#p6"/></animateMotion></circle>

    <!-- security gate, sitting above the API node -->
    <g class="gateWrap">
      <circle class="ringPulse" cx="660" cy="80" r="26" fill="none" stroke="#C9A227" stroke-opacity=".5" stroke-width="1.2"/>
      <circle cx="660" cy="80" r="15" fill="url(#goldGlow)" class="flick"/>
      <rect x="653" y="76" width="14" height="11" rx="2.5" fill="#F9E8B8"/>
      <path d="M656,76 L656,71.5 C656,68 664,68 664,71.5 L664,76" stroke="#F9E8B8" stroke-width="2" fill="none"/>
      <text x="660" y="105" font-size="9.5" font-weight="700" fill="#C9A227" text-anchor="middle" class="mono gateHint">RULES</text>
      <text x="660" y="105" font-size="8" font-weight="600" fill="#F3D7C4" text-anchor="middle" class="mono gateNote">Cloud Armor + auth</text>
    </g>

    <!-- nodes -->
    <g font-size="10.5" font-weight="700" text-anchor="middle" class="mono">
      <g>
        <rect x="480" y="126" width="40" height="28" rx="6" fill="#0B1A30" stroke="#123A66"/>
        <text x="500" y="143" fill="#F3D7C4">API</text>
      </g>
      <g>
        <rect x="600" y="126" width="60" height="28" rx="6" fill="#0B1A30" stroke="#2E6FD9"/>
        <text x="630" y="143" fill="#F3D7C4">QUEUE</text>
      </g>
      <g>
        <rect x="700" y="126" width="60" height="28" rx="6" fill="#0B1A30" stroke="#2E6FD9"/>
        <text x="730" y="143" fill="#F3D7C4">WORKER</text>
      </g>
      <g>
        <rect x="700" y="206" width="60" height="28" rx="6" fill="#0B1A30" stroke="#123A66"/>
        <text x="730" y="223" fill="#F3D7C4">GEMINI</text>
      </g>
      <g>
        <rect x="570" y="206" width="60" height="28" rx="6" fill="#0B1A30" stroke="#123A66"/>
        <text x="600" y="223" fill="#F3D7C4">CONSUMER</text>
      </g>
      <g>
        <rect x="570" y="280" width="60" height="30" rx="6" fill="#0B1A30" stroke="#C9A227"/>
        <text x="600" y="298" fill="#F9E8B8">FIRESTORE</text>
      </g>
    </g>

    <text x="660" y="375" font-size="10.5" fill="#5E7699" text-anchor="middle" class="mono">async pipeline &#183; queue &#8594; consumer &#183; gated at the edge</text>
  </g>

  <rect x="1.5" y="1.5" width="897" height="457" rx="22" fill="url(#vignette)"/>
</svg>
