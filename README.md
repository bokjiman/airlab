<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AIR Lab — ACEs-Informed Recovery Lab @ CBNU</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Barlow:ital,wght@0,200;0,300;0,400;0,500;0,600;1,200;1,300;1,400&family=Barlow+Condensed:ital,wght@0,200;0,300;0,400;0,500;0,600;1,200;1,300;1,400&display=swap');

:root {
  --white:    #ffffff;
  --off:      #f7f6f3;
  --black:    #0e0e0e;
  --mid:      #4a4a4a;
  --light:    #999999;
  --xlight:   #cccccc;
  --rule:     #dedede;
  --red:      #b52b1e;
  --navy:     #162038;
  --hover-bg: #f4f3f0;
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; }
body {
  background: var(--white);
  color: var(--black);
  font-family: 'Barlow', 'Helvetica Neue', Helvetica, Arial, sans-serif;
  font-weight: 300;
  line-height: 1.65;
  -webkit-font-smoothing: antialiased;
}

/* ── STRIPE ── */
.stripe { display: flex; height: 4px; width: 100%; }
.stripe span { flex: 1; }
.stripe .s1 { background: var(--navy); }
.stripe .s2 { background: var(--red); }
.stripe .s3 { background: #ddd; }
.stripe .s4 { background: var(--red); }
.stripe .s5 { background: var(--navy); }

/* ── NAV ── */
nav {
  position: fixed; top: 0; left: 0; right: 0; z-index: 200;
  background: var(--white); border-bottom: 1px solid var(--rule);
}
.nav-inner {
  display: flex; align-items: center; justify-content: space-between;
  padding: 0 3.5rem; height: 56px;
  max-width: 1400px; margin: 0 auto;
}
.nav-logo {
  font-family: 'Barlow Condensed', sans-serif;
  font-weight: 500; font-size: 0.95rem;
  letter-spacing: 0.3em; text-transform: uppercase;
  color: var(--black); text-decoration: none;
  display: flex; align-items: center; gap: 0.9rem;
}
.nav-logo-dot {
  display: flex; gap: 2px; align-items: center;
}
.nav-logo-dot span {
  display: block; width: 5px; height: 5px; border-radius: 50%;
}
.nav-logo-dot .d1 { background: var(--navy); }
.nav-logo-dot .d2 { background: var(--red); }
.nav-logo-dot .d3 { background: var(--navy); }

.nav-links { display: flex; gap: 2.5rem; list-style: none; }
.nav-links a {
  font-size: 0.67rem; letter-spacing: 0.2em; text-transform: uppercase;
  color: var(--light); text-decoration: none; font-weight: 400;
  transition: color 0.15s;
}
.nav-links a:hover { color: var(--black); }

/* ── TICKER ── */
.ticker-wrap {
  margin-top: 60px; background: var(--navy);
  display: flex; align-items: stretch; overflow: hidden;
}
.ticker-label {
  background: var(--red); padding: 0 1.6rem;
  font-family: 'Barlow Condensed', sans-serif;
  font-size: 0.58rem; letter-spacing: 0.35em; text-transform: uppercase;
  font-weight: 600; color: #fff;
  display: flex; align-items: center; flex-shrink: 0;
}
.ticker-scroll { overflow: hidden; flex: 1; display: flex; align-items: center; }
.ticker-track { display: flex; animation: ticker 55s linear infinite; white-space: nowrap; }
.ticker-track:hover { animation-play-state: paused; }
.ticker-item {
  padding: 0.75rem 3rem; font-size: 0.72rem; letter-spacing: 0.05em;
  color: rgba(255,255,255,0.72); border-right: 1px solid rgba(255,255,255,0.08);
}
.ticker-item strong { color: #fff; font-weight: 500; }
@keyframes ticker { 0% { transform:translateX(0); } 100% { transform:translateX(-50%); } }

/* ── HERO ── */
#hero {
  max-width: 1400px; margin: 0 auto;
  padding: 0 3.5rem;
  border-bottom: 1px solid var(--rule);
}

/* Identity block — full-width top */
.hero-identity {
  padding: 4rem 0 3rem;
  border-bottom: 1px solid var(--rule);
  display: flex;
  align-items: flex-end;
  justify-content: space-between;
  gap: 3rem;
}

.hero-lab-name {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.hero-acronym {
  font-family: 'Barlow Condensed', sans-serif;
  font-weight: 600;
  font-size: clamp(5rem, 10vw, 11rem);
  line-height: 0.88;
  letter-spacing: -0.02em;
  color: var(--black);
  display: flex;
  align-items: baseline;
  gap: 0.15em;
}

.hero-acronym .letter-a { color: var(--navy); }
.hero-acronym .letter-i { color: var(--red); font-style: italic; }
.hero-acronym .letter-r { color: var(--navy); }
.hero-acronym .lab-suffix {
  font-size: 0.3em;
  font-weight: 300;
  letter-spacing: 0.15em;
  color: var(--light);
  text-transform: uppercase;
  padding-left: 0.4em;
  align-self: flex-end;
  padding-bottom: 0.15em;
  font-style: normal;
}

.hero-fullname {
  font-family: 'Barlow Condensed', sans-serif;
  font-weight: 300;
  font-size: clamp(0.9rem, 1.5vw, 1.15rem);
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--mid);
}

.hero-fullname strong {
  font-weight: 500;
  color: var(--black);
}

.hero-right-block {
  text-align: right;
  flex-shrink: 0;
}

.hero-institution {
  font-size: 0.72rem;
  letter-spacing: 0.14em;
  text-transform: uppercase;
  color: var(--light);
  line-height: 2;
}

.hero-institution strong {
  color: var(--mid);
  font-weight: 400;
}

/* Two-col content below identity */
.hero-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 0;
  padding: 3.5rem 0;
}

.hero-pi {
  padding-right: 5rem;
  border-right: 1px solid var(--rule);
  display: flex;
  gap: 2.2rem;
  align-items: flex-start;
}

.pi-photo {
  width: 110px; height: 145px;
  object-fit: cover; object-position: top;
  filter: grayscale(8%); flex-shrink: 0;
}

.pi-text {}
.pi-name {
  font-family: 'Barlow Condensed', sans-serif;
  font-size: 1.5rem; font-weight: 500;
  letter-spacing: 0.08em; text-transform: uppercase;
  color: var(--black); margin-bottom: 0.1rem;
}
.pi-name-ko {
  font-size: 0.8rem; color: var(--light);
  letter-spacing: 0.06em; margin-bottom: 0.1rem;
  font-weight: 300;
}
.pi-role {
  font-size: 0.68rem; color: var(--red);
  letter-spacing: 0.14em; text-transform: uppercase;
  font-weight: 500; margin-bottom: 1.4rem;
}

.contacts { display: flex; flex-direction: column; gap: 0.42rem; }
.cr { display: flex; gap: 0.8rem; font-size: 0.77rem; color: var(--mid); align-items: baseline; }
.cr .lbl {
  font-size: 0.58rem; letter-spacing: 0.16em; text-transform: uppercase;
  color: var(--xlight); width: 3.5rem; flex-shrink: 0; font-weight: 400;
}
.cr a { color: var(--mid); text-decoration: none; transition: color 0.15s; }
.cr a:hover { color: var(--black); }

.hero-research {
  padding-left: 5rem;
  display: flex; flex-direction: column; gap: 2.5rem;
}

.hero-desc {
  font-size: 0.92rem; color: var(--mid); line-height: 1.85;
  max-width: 46ch; font-weight: 300;
  border-left: 2px solid var(--rule);
  padding-left: 1.5rem;
}

.blk-lbl {
  font-size: 0.58rem; letter-spacing: 0.24em; text-transform: uppercase;
  color: var(--light); margin-bottom: 0.9rem;
  display: flex; align-items: center; gap: 0.8rem;
}
.blk-lbl::after { content: ''; flex: 1; height: 1px; background: var(--rule); }

.tags { display: flex; flex-wrap: wrap; gap: 0.38rem; }
.tag {
  font-size: 0.63rem; letter-spacing: 0.1em; text-transform: uppercase;
  padding: 0.3rem 0.8rem; border: 1px solid var(--rule); color: var(--light);
  transition: all 0.15s; cursor: default;
}
.tag:hover { border-color: var(--navy); color: var(--navy); }

/* ── SECTION ── */
.sw { max-width: 1400px; margin: 0 auto; padding: 5rem 3.5rem; border-bottom: 1px solid var(--rule); }

.sh {
  display: grid; grid-template-columns: 13rem 1fr;
  gap: 4rem; margin-bottom: 3.5rem; align-items: baseline;
}
.sn { font-size: 0.58rem; letter-spacing: 0.28em; text-transform: uppercase; color: var(--xlight); }
.st {
  font-family: 'Barlow Condensed', sans-serif;
  font-size: clamp(1.8rem, 2.8vw, 2.6rem); font-weight: 400;
  text-transform: uppercase; letter-spacing: 0.05em; line-height: 1;
  color: var(--black);
}

/* ── NEWS ── */
.news-cards { display: flex; flex-direction: column; }
.nc {
  display: grid; grid-template-columns: 13rem 1fr auto;
  gap: 4rem; padding: 1.7rem 0;
  border-bottom: 1px solid var(--rule); align-items: start;
}
.nc:first-child { border-top: 1px solid var(--rule); }
.nc-date {
  font-family: 'Barlow Condensed', sans-serif;
  font-size: 0.68rem; letter-spacing: 0.1em; color: var(--xlight);
  text-transform: uppercase; padding-top: 0.1rem;
}
.nc-text { font-size: 0.88rem; color: var(--black); line-height: 1.7; font-weight: 300; }
.nc-text strong { font-weight: 500; }
.nc-text em { font-style: normal; color: var(--light); font-size: 0.8rem; display: block; margin-top: 0.3rem; }
.badge { font-size: 0.56rem; letter-spacing: 0.16em; text-transform: uppercase; padding: 0.26rem 0.65rem; font-weight: 600; align-self: start; }
.badge-award  { background: #fdf3e3; color: #9a5c10; border: 1px solid #e8c880; }
.badge-recruit{ background: #eaf0fa; color: #1a3a7a; border: 1px solid #a0bbdf; }
.badge-paper  { background: #f0f0f0; color: #444; border: 1px solid #d4d4d4; }

/* ── ABOUT ── */
.about-grid { display: grid; grid-template-columns: 13rem 1fr; gap: 4rem; }
.about-body p { font-size: 0.91rem; color: var(--mid); line-height: 1.9; max-width: 64ch; margin-bottom: 1.5rem; font-weight: 300; }
.about-body p:last-child { margin-bottom: 0; }

/* ── PUBLICATIONS ── */
.pub-ctrl {
  display: grid; grid-template-columns: 13rem 1fr;
  gap: 4rem; margin-bottom: 0; align-items: center;
}
.pfilt { display: flex; }
.pfilt button {
  padding: 0.5rem 1.4rem; font-size: 0.62rem; letter-spacing: 0.18em;
  text-transform: uppercase; border: 1px solid var(--rule); border-right: none;
  background: transparent; color: var(--light); cursor: pointer;
  font-family: 'Barlow', sans-serif; font-weight: 400; transition: all 0.15s;
}
.pfilt button:last-child { border-right: 1px solid var(--rule); }
.pfilt button.active { background: var(--navy); color: var(--white); border-color: var(--navy); }
.pfilt button:hover:not(.active) { color: var(--black); border-color: #999; }

.pub-list { margin-top: 2rem; }

/* Pub Row */
.pr { border-bottom: 1px solid var(--rule); cursor: pointer; transition: background 0.12s; }
.pr:first-child { border-top: 1px solid var(--rule); }
.pr:hover { background: var(--hover-bg); }

.pr-head {
  display: grid; grid-template-columns: 13rem 1fr 6rem;
  gap: 4rem; padding: 1.5rem 0.6rem; align-items: start;
}

.pr-yr {
  font-family: 'Barlow Condensed', sans-serif;
  font-size: 0.7rem; letter-spacing: 0.08em; color: var(--xlight); padding-top: 0.1rem;
}

.pr-title-text {
  font-size: 0.89rem; color: var(--black); line-height: 1.55;
  font-weight: 400; margin-bottom: 0.35rem;
}
.pr-authors-preview {
  font-size: 0.74rem; color: var(--light); font-weight: 300;
}
.pr-authors-preview em { font-style: italic; }

.pr-badges { display: flex; flex-direction: column; align-items: flex-end; gap: 0.3rem; }
.pb {
  font-size: 0.57rem; letter-spacing: 0.13em; text-transform: uppercase;
  padding: 0.27rem 0.65rem; font-weight: 600; text-align: center;
}
.pb-intl { background: var(--navy); color: #fff; }
.pb-kci  { background: #f0f0f0; color: #555; border: 1px solid #d4d4d4; }
.pb-new  { background: var(--red); color: #fff; }

/* Detail panel */
.pr-detail { display: none; padding: 0 0.6rem 1.8rem; padding-left: calc(13rem + 4rem + 0.6rem); }
.pr-detail.open { display: block; animation: expandIn 0.18s ease; }
@keyframes expandIn { from { opacity:0; transform:translateY(-4px); } to { opacity:1; transform:translateY(0); } }

.detail-inner {
  border-top: 1px solid var(--rule); padding-top: 1.3rem;
  display: grid; grid-template-columns: 1fr auto; gap: 2rem; align-items: start;
}
.detail-block { display: flex; flex-direction: column; gap: 0.9rem; }
.detail-row {}
.detail-key {
  font-size: 0.56rem; letter-spacing: 0.22em; text-transform: uppercase;
  color: var(--xlight); margin-bottom: 0.3rem; font-weight: 400;
}
.detail-val {
  font-size: 0.8rem; color: var(--mid); line-height: 1.75; font-weight: 300;
}
.detail-val.citation { font-style: italic; }
.detail-val.authors { font-style: normal; color: var(--black); font-weight: 400; }

.detail-link {
  display: inline-flex; align-items: center; gap: 0.5rem;
  font-size: 0.65rem; letter-spacing: 0.16em; text-transform: uppercase;
  color: var(--navy); text-decoration: none;
  border: 1.5px solid var(--navy); padding: 0.5rem 1.1rem;
  transition: all 0.15s; white-space: nowrap; font-weight: 500; align-self: end;
}
.detail-link:hover { background: var(--navy); color: #fff; }
.detail-link.disabled { color: var(--xlight); border-color: var(--rule); pointer-events: none; }

.see-more {
  display: inline-flex; align-items: center; gap: 0.6rem; margin-top: 2rem;
  font-size: 0.67rem; letter-spacing: 0.18em; text-transform: uppercase;
  color: var(--mid); text-decoration: none;
  padding: 0 0.6rem; transition: gap 0.2s, color 0.15s;
}
.see-more:hover { color: var(--black); gap: 1.1rem; }

/* ── TIMELINE ── */
.tl { display: flex; flex-direction: column; }
.tr {
  display: grid; grid-template-columns: 13rem 1fr;
  gap: 4rem; padding: 1.9rem 0; border-bottom: 1px solid var(--rule);
}
.tr:first-child { border-top: 1px solid var(--rule); }
.tr-period {
  font-family: 'Barlow Condensed', sans-serif;
  font-size: 0.68rem; letter-spacing: 0.08em; color: var(--xlight);
  line-height: 1.5; padding-top: 0.1rem; font-weight: 300;
}
.tr-role { font-size: 0.91rem; font-weight: 500; color: var(--black); margin-bottom: 0.2rem; }
.tr-org { font-size: 0.77rem; color: var(--red); margin-bottom: 0.45rem; font-weight: 300; }
.tr-desc { font-size: 0.77rem; color: var(--light); line-height: 1.65; font-weight: 300; }

/* ── FOOTER ── */
.footer-wrap { border-top: 1px solid var(--rule); background: var(--off); }
footer {
  max-width: 1400px; margin: 0 auto; padding: 2.5rem 3.5rem;
  display: grid; grid-template-columns: 1fr auto 1fr; gap: 2rem; align-items: center;
}
.f-logo {
  font-family: 'Barlow Condensed', sans-serif;
  font-size: 0.9rem; letter-spacing: 0.28em; text-transform: uppercase; font-weight: 500;
  display: flex; align-items: center; gap: 0.7rem;
}
.f-center { display: flex; flex-direction: column; align-items: center; gap: 0.6rem; }
.f-stripe { display: flex; gap: 3px; }
.f-stripe span { display: block; width: 16px; height: 2.5px; }
.f-stripe .fs1,.f-stripe .fs5 { background: var(--navy); }
.f-stripe .fs2,.f-stripe .fs4 { background: var(--red); }
.f-stripe .fs3 { background: #ccc; }
.f-copy { font-size: 0.6rem; letter-spacing: 0.14em; text-transform: uppercase; color: var(--light); }
.f-right { text-align: right; font-size: 0.71rem; color: var(--light); line-height: 1.9; }

/* ── ANIMATE ── */
@keyframes fadeUp { from { opacity:0; transform:translateY(16px); } to { opacity:1; transform:translateY(0); } }
.hero-identity { animation: fadeUp 0.6s ease 0.05s both; }
.hero-content  { animation: fadeUp 0.6s ease 0.2s both; }

/* ── RESPONSIVE ── */
@media (max-width: 1024px) {
  .nav-inner { padding: 0 2rem; }
  .nav-links { gap: 1.8rem; }
  #hero { padding: 0 2rem; }
  .sw { padding: 4rem 2rem; }
  .hero-identity { flex-direction: column; align-items: flex-start; gap: 1.5rem; }
  .hero-right-block { text-align: left; }
  .hero-content { grid-template-columns: 1fr; gap: 3rem; }
  .hero-pi { padding-right: 0; border-right: none; border-bottom: 1px solid var(--rule); padding-bottom: 3rem; }
  .hero-research { padding-left: 0; }
  .sh, .about-grid, .pub-ctrl, .nc, .pr-head, .tr { grid-template-columns: 1fr; gap: 1rem; }
  .pr-detail { padding-left: 0.6rem; }
  .detail-inner { grid-template-columns: 1fr; }
  footer { grid-template-columns: 1fr; }
  .f-center, .f-right { text-align: left; }
  .f-center { align-items: flex-start; }
}
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="stripe"><span class="s1"></span><span class="s2"></span><span class="s3"></span><span class="s4"></span><span class="s5"></span></div>
  <div class="nav-inner">
    <a class="nav-logo" href="#hero">
      <span class="nav-logo-dot"><span class="d1"></span><span class="d2"></span><span class="d3"></span></span>
      AIR Lab
    </a>
    <ul class="nav-links">
      <li><a href="#news">News</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#publications">Publications</a></li>
      <li><a href="#experience">Experience</a></li>
      <li><a href="#education">Education</a></li>
    </ul>
  </div>
</nav>

<!-- TICKER -->
<div class="ticker-wrap">
  <div class="ticker-label">Latest</div>
  <div class="ticker-scroll">
    <div class="ticker-track" id="tickerTrack"></div>
  </div>
</div>

<!-- HERO -->
<div id="hero">

  <!-- Identity: AIR LAB big -->
  <div class="hero-identity">
    <div class="hero-lab-name">
      <div class="hero-acronym">
        <span class="letter-a">A</span><span class="letter-i">I</span><span class="letter-r">R</span>
        <span class="lab-suffix">Lab</span>
      </div>
      <div class="hero-fullname">
        <strong>ACEs-Informed</strong> Recovery Lab
      </div>
    </div>
    <div class="hero-right-block">
      <div class="hero-institution">
        <strong>Department of Child Welfare</strong><br>
        Chungbuk National University<br>
        Cheongju, Republic of Korea
      </div>
    </div>
  </div>

  <!-- PI + Research -->
  <div class="hero-content">
    <div class="hero-pi">
      <img class="pi-photo"
        src="https://bokjiman.notion.site/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F3c5dfe23-ae09-465d-aba2-4eddbc13f571%2Fef5d7a71-9a12-42da-8a2e-ec4ec09d9f74%2FKakaoTalk_Photo_2025-02-28-12-01-42.jpeg?table=block&id=1a9c0b4d-1505-8042-8e9f-e91b9b1f02a6&width=460&userId=&cache=v2"
        alt="Kim Joonbeom" onerror="this.style.background='#ebebeb'">
      <div class="pi-text">
        <div class="pi-name">Kim, Joonbeom</div>
        <div class="pi-name-ko">김준범</div>
        <div class="pi-role">Principal Investigator</div>
        <div class="contacts">
          <div class="cr"><span class="lbl">Email</span><a href="mailto:jayb.kim@cbnu.ac.kr">jayb.kim@cbnu.ac.kr</a></div>
          <div class="cr"><span class="lbl">Tel</span><span>+82 10-9539-1025</span></div>
          <div class="cr"><span class="lbl">Office</span><span>CBNU N20-1, Rm. 104</span></div>
          <div class="cr"><span class="lbl">Scholar</span><a href="https://scholar.google.com" target="_blank">Google Scholar ↗</a></div>
        </div>
      </div>
    </div>

    <div class="hero-research">
      <div class="hero-desc">
        Advancing empirical understanding of adverse childhood experiences, trauma, and youth mental health through rigorous mixed-method and quantitative research. The AIR Lab is committed to translating research into evidence-based social work policy and practice.
      </div>
      <div>
        <div class="blk-lbl">Research Interests</div>
        <div class="tags">
          <span class="tag">Adverse Childhood Experiences</span>
          <span class="tag">Trauma &amp; Recovery</span>
          <span class="tag">Youth Mental Health</span>
          <span class="tag">Suicide / PTSD</span>
          <span class="tag">Vulnerable Youth</span>
          <span class="tag">Family Violence</span>
          <span class="tag">ADHD</span>
          <span class="tag">Social Work Practice</span>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- NEWS -->
<div id="news" class="sw">
  <div class="sh"><div class="sn">01 · News &amp; Notice</div><h2 class="st">Latest Updates</h2></div>
  <div class="news-cards" id="newsCards"></div>
</div>

<!-- ABOUT -->
<div id="about" class="sw">
  <div class="sh"><div class="sn">02 · About</div><h2 class="st">Research Focus</h2></div>
  <div class="about-grid">
    <div></div>
    <div class="about-body">
      <p>I am an assistant professor in the Department of Child Welfare at Chungbuk National University. My research focuses on youth welfare and mental health, with an emphasis on empirical investigations of violence, trauma, depression, and suicide risk.</p>
      <p>I have examined topics such as Adverse Childhood Experiences (ACEs), family violence, school violence, ADHD, and post-traumatic recovery using diverse statistical approaches and mixed-method designs.</p>
      <p>I am also deeply interested in advancing social work practice and policy by integrating clinical and psychiatric perspectives, and I have led multiple community-based studies and NRF-funded research projects.</p>
      <p>As an educator, I value relationship-based teaching that prioritizes students' growth, experience, and active engagement.</p>
    </div>
  </div>
</div>

<!-- PUBLICATIONS -->
<div id="publications" class="sw">
  <div class="sh"><div class="sn">03 · Publications</div><h2 class="st">Selected Works</h2></div>
  <div class="pub-ctrl">
    <div></div>
    <div style="display:flex; align-items:center; gap:1.2rem; flex-wrap:wrap;">
      <div class="pfilt">
        <button class="active" onclick="fp('all',this)">All</button>
        <button onclick="fp('intl',this)">SSCI / SCIE</button>
        <button onclick="fp('kci',this)">KCI</button>
      </div>
      <span style="font-size:0.63rem;letter-spacing:0.14em;color:var(--xlight);" id="pubCount"></span>
    </div>
  </div>
  <div class="pub-list" id="pubList"></div>
</div>

<!-- EXPERIENCE -->
<div id="experience" class="sw">
  <div class="sh"><div class="sn">04 · Experience</div><h2 class="st">Professional</h2></div>
  <div class="tl">
    <div class="tr"><div class="tr-period">March 2025 – Present</div><div><div class="tr-role">Assistant Professor</div><div class="tr-org">Department of Child Welfare, Chungbuk National University</div><div class="tr-desc">Specialization in Youth Welfare and Mental Health</div></div></div>
    <div class="tr"><div class="tr-period">Nov 2021 – Feb 2025</div><div><div class="tr-role">Postdoctoral Researcher</div><div class="tr-org">Institute of Behavioral Science in Medicine, Yonsei University College of Medicine</div><div class="tr-desc">OJU Lab, Gangnam Severance Hospital — geriatric psychiatry, delirium in ICU, panic disorder, DTx, HRV</div></div></div>
    <div class="tr"><div class="tr-period">Jan 2019 – Oct 2021</div><div><div class="tr-role">Researcher</div><div class="tr-org">Suicide and School Mental Health Research Institute, Hallym University College of Medicine</div><div class="tr-desc">Policy Research Team — Ministry of Education Designated Policy Research Institute</div></div></div>
    <div class="tr"><div class="tr-period">Feb 2017 – Dec 2017</div><div><div class="tr-role">Research Intern</div><div class="tr-org">Korean Institute of Criminology and Justice (KICJ)</div><div class="tr-desc">General Crime Research Division</div></div></div>
    <div class="tr"><div class="tr-period">Additional</div><div><div class="tr-role">Clinical &amp; Counseling Practice</div><div class="tr-org">Gwangjin-gu Youth Counseling Center · Siheung City Youth Shelter · Seoul Yongsan Emergency Youth Shelter</div><div class="tr-desc">Youth Companion (YC) · Counselor (Professional Volunteer) · TSL Family Therapy — Certified Professional Counselor</div></div></div>
  </div>
</div>

<!-- EDUCATION -->
<div id="education" class="sw">
  <div class="sh"><div class="sn">05 · Education</div><h2 class="st">Academic Training</h2></div>
  <div class="tl">
    <div class="tr"><div class="tr-period">Mar 2018 – Aug 2024</div><div><div class="tr-role">Ph.D. in Social Welfare — Family and Youth Welfare</div><div class="tr-org">Interdisciplinary Program in Social Welfare Policy, Yonsei University</div><div class="tr-desc">"Effectiveness of an individual TSL treatment program to improve family functioning and mental health in runaway youth: Focusing on the recovery process after running away"</div></div></div>
  </div>
</div>

<div class="footer-wrap">
  <footer>
    <div class="f-logo">
      <span class="nav-logo-dot"><span class="d1"></span><span class="d2"></span><span class="d3"></span></span>
      AIR Lab @ CBNU
    </div>
    <div class="f-center">
      <div class="f-stripe"><span class="fs1"></span><span class="fs2"></span><span class="fs3"></span><span class="fs4"></span><span class="fs5"></span></div>
      <div class="f-copy">ACEs-Informed Recovery Lab</div>
    </div>
    <div class="f-right">Dept. of Child Welfare<br>Chungbuk National University<br>N20-1, Rm. 104 · Cheongju, Korea</div>
  </footer>
</div>

<script>
const NEWS_DATA = [
  { date:"2026.03.04", type:"award",   title:"우수논문 선정", body:"청소년상담연구 (한국청소년상담복지개발원) 2025년 게재 논문 중 우수논문 선정", sub:"가정 밖 청소년의 가족관계 변화와 회복 과정에 대한 질적 연구: 상담 개입 경험을 중심으로" },
  { date:"2026",       type:"paper",   title:"New Publication (SSCI)", body:"Mapping the Structures of Adverse Childhood Experiences: A Network Analysis and a Sex-Differentiated Structural Framework for Prevention and Intervention", sub:"Journal of Interpersonal Violence" },
  { date:"2026",       type:"paper",   title:"New Publication (SSCI)", body:"Do Adverse Childhood Experiences Intensify the Impact of Hazardous Drinking on Depression? Application of Quantile Regression Analysis", sub:"Child Abuse & Neglect" },
  { date:"상시",       type:"recruit", title:"Recruiting", body:"아동청소년복지 및 정신건강, 지역사회 기반 실천 연구에 관심 있는 대학원생·학부생을 상시 모집합니다.", sub:"문의: jayb.kim@cbnu.ac.kr" }
];

const PUB_DATA = [
  { no:71, year:2026, type:"KCI",  isNew:true,  title:"ADHD는 학교적응력을 떨어뜨리는가?: 청소년 ADHD 증상 정도와 학교적응의 관계에서 제곱항을 이용한 비선형관계 검증", journal:"미래청소년학회지", authors:"전진호, 김나영, 강주연, 김준범, 한승희", citation:"전진호, 김나영, 강주연, 김준범, 한승희. (2026). ADHD는 학교적응력을 떨어뜨리는가?: 청소년 ADHD 증상 정도와 학교적응의 관계에서 제곱항을 이용한 비선형관계 검증. 미래청소년학회지, 23(1), 91-116.", doi:"https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003317209" },
  { no:70, year:2026, type:"SSCI", isNew:true,  title:"Patterns of Intimate Partner Sexual Violence: Latent Classes and Sex-Specific Associations with Suicidal Ideation", journal:"Journal of Family Violence", authors:"Im, J., & Kim, J.", citation:"Im, J., & Kim, J. (2026). Patterns of Intimate Partner Sexual Violence: Latent Classes and Sex-Specific Associations with Suicidal Ideation. Journal of Family Violence, 1-16.", doi:"https://link.springer.com/article/10.1007/s10896-026-01099-w" },
  { no:69, year:2026, type:"SSCI", isNew:true,  title:"Do Adverse Childhood Experiences Intensify the Impact of Hazardous Drinking on Depression? Application of Quantile Regression Analysis", journal:"Child Abuse & Neglect", authors:"Lee, M. S., & Kim, J.", citation:"Lee, M. S., & Kim, J. (2026). Do adverse childhood experiences intensify the impact of hazardous drinking on depression? Child Abuse & Neglect, 174, 107976.", doi:"https://www.sciencedirect.com/science/article/pii/S0145213426000955" },
  { no:68, year:2026, type:"SSCI", isNew:true,  title:"Mapping the Structures of Adverse Childhood Experiences: A Network Analysis and a Sex-Differentiated Structural Framework for Prevention and Intervention", journal:"Journal of Interpersonal Violence", authors:"Kim, J., & Son, S.", citation:"Kim, J., & Son, S. Mapping the Structures of Adverse Childhood Experiences: A Network Analysis and a Sex-Differentiated Structural Framework for Prevention and Intervention. Journal of Interpersonal Violence, 08862605261426592.", doi:"https://journals.sagepub.com/doi/10.1177/08862605261426592" },
  { no:67, year:2025, type:"KCI",  isNew:false, title:"초등학교 고학년 아동의 ADHD 증상과 정신건강 서비스 인식에 따른 자살 위험의 비교 연구", journal:"학교사회복지", authors:"이재은, 김준범, 박연주", citation:"이재은, 김준범, 박연주. (2025). 초등학교 고학년 아동의 ADHD 증상과 정신건강 서비스 인식에 따른 자살 위험의 비교 연구. 학교사회복지, (72), 1-25.", doi:"https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003281759" },
  { no:66, year:2025, type:"KCI",  isNew:false, title:"사회복지사의 일·생활 균형 인식과 조직 분위기의 잠재유형별 이직의도 차이", journal:"한국사회복지행정학", authors:"장은주, 김준범, 신우철", citation:"장은주, 김준범, 신우철. (2025). 사회복지사의 일·생활 균형 인식과 조직 분위기의 잠재유형별 이직의도 차이. 한국사회복지행정학, 27(4), 111-142.", doi:"https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003267939" },
  { no:65, year:2025, type:"KCI",  isNew:false, title:"가정 밖 청소년의 가족관계 변화와 회복 과정에 대한 질적 연구: 상담 개입 경험을 중심으로", journal:"청소년상담연구", authors:"김준범, 손수민", citation:"김준범, 손수민. (2025). 가정 밖 청소년의 가족관계 변화와 회복 과정에 대한 질적 연구. 청소년상담연구, 33(2), 53-84.", doi:"https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003266176" },
  { no:64, year:2025, type:"SSCI", isNew:false, title:"ADHD and Sex Differences in School Bullying Victimization and Perpetration Based on Inverse Probability Treatment Weighting", journal:"Child Psychiatry & Human Development", authors:"Kim, D., Choi, Y. H., & Kim, J.", citation:"Kim, D., Choi, Y. H., & Kim, J. (2025). ADHD and Sex Differences in School Bullying Victimization and Perpetration Based on Inverse Probability Treatment Weighting. Child Psychiatry & Human Development, 1-13.", doi:"https://link.springer.com/article/10.1007/s10578-025-01930-3" },
  { no:63, year:2025, type:"KCI",  isNew:false, title:"초등학생 ADHD 증상 수준별 양육태도 및 학교적응의 영향 분석: 분위회귀분석의 적용", journal:"학교사회복지", authors:"장대연, 김준범, 김사라", citation:"장대연, 김준범, 김사라. (2025). 초등학생 ADHD 증상 수준별 양육태도 및 학교적응의 영향 분석. 학교사회복지, (71), 49-76.", doi:"https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003246608" },
  { no:62, year:2025, type:"SSCI", isNew:false, title:"Assessing the Effectiveness of TSL Program for Runaway and Homeless Youth", journal:"Research on Social Work Practice", authors:"Kim, J., Kim, J. Y., & Lee, J.", citation:"Kim, J., Kim, J. Y., & Lee, J. (2025). Assessing the Effectiveness of TSL Program for Runaway and Homeless Youth. Research on Social Work Practice.", doi:"https://journals.sagepub.com/doi/full/10.1177/10497315251335239" },
  { no:61, year:2025, type:"KCI",  isNew:false, title:"배우자 폭력 피해에서 발생하는 강압적 통제에 관한 연구: 외현적 폭력과 내현적 폭력 간의 관계를 중심으로", journal:"한국범죄심리연구", authors:"이진석, 김준범", citation:"이진석, 김준범. (2025). 배우자 폭력 피해에서 발생하는 강압적 통제에 관한 연구. 한국범죄심리연구, 21(1), 209-224.", doi:"https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003194662" },
  { no:60, year:2025, type:"KCI",  isNew:false, title:"북한이탈주민의 PTSD, 불안, 우울의 증상 네트워크가 자살경향성에 미치는 영향", journal:"정신건강과 사회복지", authors:"김준범, 손수민", citation:"김준범, 손수민. (2025). 북한이탈주민의 PTSD, 불안, 우울의 증상 네트워크가 자살경향성에 미치는 영향. 정신건강과 사회복지, 53(1), 31-58.", doi:"https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003187123" },
  { no:59, year:2025, type:"SCIE", isNew:false, title:"A Comparison of Symptom Structure between Panic Disorder with and without Comorbid Agoraphobia Using Network Analysis", journal:"Yonsei Medical Journal", authors:"Kim, J., Seo, Y., Lee, S., Lee, G., Seok, J. H., Kim, H. E., & Oh, J.", citation:"Kim, J. et al. (2025). A Comparison of Symptom Structure between Panic Disorder with and without Comorbid Agoraphobia Using Network Analysis. Yonsei Medical Journal, 66(5), 277.", doi:"https://eymj.org/DOIx.php?id=10.3349/ymj.2024.0177" },
  { no:58, year:2024, type:"KCI",  isNew:false, title:"사회복지사의 직장 폭력 피해 유형과 도움요청 행위에 따른 우울 수준 비교 연구", journal:"정신건강과 사회복지", authors:"김준범, 장대연", citation:"김준범, 장대연. (2024). 사회복지사의 직장 폭력 피해 유형과 도움요청 행위에 따른 우울 수준 비교 연구. 정신건강과 사회복지, 52(4), 57-84.", doi:"https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003154686" },
  { no:57, year:2024, type:"SCIE", isNew:false, title:"A propensity score-adjusted HRV analysis of social avoidance and distress in patients with panic disorders", journal:"Psychophysiology", authors:"Kim, J., Ham, J., & Oh, J.", citation:"Kim, J., Ham, J., & Oh, J. (2025). A propensity score-adjusted HRV analysis of social avoidance and distress in patients with panic disorders. Psychophysiology, 62(2), e14746.", doi:"https://onlinelibrary.wiley.com/doi/10.1111/psyp.14746" },
  { no:56, year:2024, type:"KCI",  isNew:false, title:"사회복지사의 직무만족도 수준에 따른 금전적 보상 수준, 분배공정성 인식, 보상 체계 인식의 차이", journal:"한국사회복지행정학", authors:"김준범, 장은주, 신우철", citation:"김준범, 장은주, 신우철. (2024). 사회복지사의 직무만족도 수준에 따른 금전적 보상 수준, 분배공정성 인식, 보상 체계 인식의 차이. 한국사회복지행정학, 26(4), 91-116.", doi:"https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003140536" },
  { no:55, year:2024, type:"KCI",  isNew:false, title:"아동기 역경경험이 성인기 가정폭력과 아동학대의 중복가해에 미치는 영향", journal:"한국사회복지학", authors:"이진석, 김준범", citation:"이진석, 김준범. (2024). 아동기 역경경험이 성인기 가정폭력과 아동학대의 중복가해에 미치는 영향. 한국사회복지학, 76(3), 179-199.", doi:"https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003111607" },
  { no:54, year:2024, type:"KCI",  isNew:false, title:"부모의 아동기 역경경험이 성인기 아동학대 가해에 미치는 영향: 인과효과 추정을 위한 역확률가중치의 적용", journal:"한국범죄심리연구", authors:"이진석, 김준범", citation:"이진석, 김준범. (2024). 부모의 아동기 역경경험이 성인기 아동학대 가해에 미치는 영향. 한국범죄심리연구, 20(2), 73-88.", doi:"https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003102274" },
  { no:53, year:2023, type:"KCI",  isNew:false, title:"신체 증상 장애 환자의 심박변이도와 증상 심각도의 연관성", journal:"정신신체의학", authors:"김은환, 김희선, 함진실, 김준범, 오주영", citation:"김은환, 김희선, 함진실, 김준범, 오주영. (2023). 신체 증상 장애 환자의 심박변이도와 증상 심각도의 연관성. 정신신체의학, 31(2), 108-117.", doi:"https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003039676" },
  { no:52, year:2023, type:"SCIE", isNew:false, title:"Association and interaction between clinician-rated measures of depression and anxiety with heart rate variability in elderly patients with psychiatric disorders", journal:"Heliyon", authors:"Kim, J., Kim, J. J., Seok, J. H., Kim, E., Park, J. Y., Kim, H. E., & Oh, J.", citation:"Kim, J. et al. (2023). Association and interaction between clinician-rated measures of depression and anxiety with HRV in elderly patients with psychiatric disorders. Heliyon, 9(10).", doi:"https://www.sciencedirect.com/science/article/pii/S2405844023079483" },
  { no:51, year:2023, type:"KCI",  isNew:false, title:"고령장애인의 우울, 신체적 기능, 그리고 사회적 유대감이 자살위험에 미치는 영향", journal:"한국장애인복지학", authors:"이병화, 김준범", citation:"이병화, 김준범. (2023). 고령장애인의 우울, 신체적 기능, 그리고 사회적 유대감이 자살위험에 미치는 영향. 한국장애인복지학, 127-149.", doi:"https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003000398" },
  { no:50, year:2023, type:"KCI",  isNew:false, title:"아동기 역경경험과 성인기 우울의 관계에 대한 연구", journal:"학교사회복지", authors:"손수민, 김준범", citation:"손수민, 김준범. (2023). 아동기 역경경험과 성인기 우울의 관계에 대한 연구. 학교사회복지, 62, 27-51.", doi:"https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART002970125" },
  { no:49, year:2023, type:"KCI",  isNew:false, title:"재난 피해자의 트라우마 수준이 PTSD 증상에 미치는 영향에서 초기 증상 정도와 문제음주의 조절효과", journal:"정신건강과 사회복지", authors:"김준범, 임지혜", citation:"김준범, 임지혜. (2023). 재난 피해자의 트라우마 수준이 PTSD 증상에 미치는 영향에서 초기 증상 정도와 문제음주의 조절효과. 정신건강과 사회복지, 51(2), 29-52.", doi:"https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART002969492" },
  { no:48, year:2023, type:"SCIE", isNew:false, title:"Can We Notice the Suicidal Warning Signs of Adolescents With Different Psychometric Profiles Before Their Death?: Analysis of Teachers' Reports", journal:"Journal of Korean Medical Science", authors:"Lee, M. S., Kim, J., Hong, H. J., & Bhang, S. Y.", citation:"Lee, M. S., Kim, J., Hong, H. J., & Bhang, S. Y. (2023). Can we notice the suicidal warning signs of adolescents with different psychometric profiles before their death? J Korean Med Sci, 38(25), e194.", doi:"https://pubmed.ncbi.nlm.nih.gov/37365728/" },
  { no:47, year:2023, type:"SSCI", isNew:false, title:"Depression, Alcohol Misuse, and Suicide Attempt Among North Korean Refugee Women Exposed to Gender-Based Violence", journal:"Journal of Interpersonal Violence", authors:"Nam, B., Kim, J., Kim, J. Y., & Lee, Y.", citation:"Nam, B., Kim, J., Kim, J. Y., & Lee, Y. (2023). Depression, alcohol misuse, and suicide attempt among North Korean refugee women exposed to gender-based violence. Journal of interpersonal violence, 38(15-16), 8878-8897.", doi:"https://journals.sagepub.com/doi/10.1177/08862605231161290" },
  { no:46, year:2022, type:"KCI",  isNew:false, title:"고령장애인의 우울과 분노가 자살시도에 미치는 영향: 장애인 쉼터 이용 만족도의 조절효과", journal:"보건과 복지", authors:"이병화, 김준범", citation:"이병화, 김준범. (2022). 고령장애인의 우울과 분노가 자살시도에 미치는 영향. 보건과 복지, 7-33.", doi:"https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART002915089" },
  { no:45, year:2022, type:"KCI",  isNew:false, title:"아동기 역경경험의 잠재유형과 가정폭력 가해의 관계: 위험음주의 가중효과를 중심으로", journal:"한국사회복지학", authors:"김준범, 최선아", citation:"김준범, 최선아. (2022). 아동기 역경경험의 잠재유형과 가정폭력 가해의 관계. 한국사회복지학, 74(4), 219-240.", doi:"https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART002900204" },
  { no:44, year:2022, type:"KCI",  isNew:false, title:"청소년 다중피해 발생 양상에 관한 성별 비교 연구: 네트워크 분석을 통한 맥락중심적 접근", journal:"학교사회복지", authors:"김준범", citation:"김준범. (2022). 청소년 다중피해 발생 양상에 관한 성별 비교 연구. 학교사회복지, 59, 57-86.", doi:"https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART002885175" },
  { no:39, year:2021, type:"SSCI", isNew:false, title:"Perceived social stigma, self-concealment, and suicide risk among North Korean refugee women exposed to traumatic events", journal:"Suicide and Life-Threatening Behavior", authors:"Nam, B., Kim, J., Ryu, W., Kim, D. I., Frey, J. J., & DeVylder, J.", citation:"Nam, B., Kim, J., Ryu, W., Kim, D. I., Frey, J. J., & DeVylder, J. (2021). Perceived social stigma, self-concealment, and suicide risk among North Korean refugee women. Suicide and Life-Threatening Behavior, 51(6), 1235-1246.", doi:"https://pubmed.ncbi.nlm.nih.gov/34585437/" },
  { no:37, year:2021, type:"SSCI", isNew:false, title:"Workplace victimization and alcohol misuse among junior military personnel: Mediating the role of anger", journal:"Journal of Affective Disorders", authors:"Kim, J. Y., Kim, J., Park, S., & Fear, N.", citation:"Kim, J. Y., Kim, J., Park, S., & Fear, N. (2021). Workplace victimization and alcohol misuse among junior military personnel. Journal of affective disorders, 294, 638-644.", doi:"https://www.sciencedirect.com/science/article/pii/S0165032721006893" },
  { no:35, year:2021, type:"SSCI", isNew:false, title:"Suicidal Ideation and Attempt among North Korean Refugee Women in South Korea: Factors that Distinguish Suicide Attempt from Suicidal Ideation", journal:"Suicide and Life-Threatening Behavior", authors:"Nam, B., Kim, J. Y., DeVylder, J., & Kim, J.", citation:"Nam, B., Kim, J. Y., DeVylder, J., & Kim, J. (2021). Suicidal ideation and attempt among North Korean refugee women in South Korea. Suicide and Life-Threatening Behavior, 51(3), 564-571.", doi:"https://pubmed.ncbi.nlm.nih.gov/33890688/" },
  { no:14, year:2019, type:"SSCI", isNew:false, title:"Military hazing and suicidal ideation among active duty military personnel: Serial mediation effects of anger and depressive symptoms", journal:"Journal of Affective Disorders", authors:"Kim, J., Kim, J., & Park, S.", citation:"Kim, J., Kim, J., & Park, S. (2019). Military hazing and suicidal ideation among active duty military personnel. Journal of affective disorders, 256, 79-85.", doi:"" }
];

function isIntl(t) { return t === 'SSCI' || t === 'SCIE'; }

function renderTicker() {
  const items = NEWS_DATA.map(n =>
    `<div class="ticker-item"><strong>[${n.title}]</strong> ${n.body}</div>`
  ).join('');
  document.getElementById('tickerTrack').innerHTML = items + items;
}

function renderNews() {
  const bm = { award:'badge-award', recruit:'badge-recruit', paper:'badge-paper' };
  const lm = { award:'Award', recruit:'Recruit', paper:'Paper' };
  document.getElementById('newsCards').innerHTML = NEWS_DATA.map(n => `
    <div class="nc">
      <div class="nc-date">${n.date}</div>
      <div class="nc-text"><strong>${n.title}</strong> — ${n.body}<em>${n.sub}</em></div>
      <span class="badge ${bm[n.type]}">${lm[n.type]}</span>
    </div>`).join('');
}

function renderPubs(filter) {
  const filtered = PUB_DATA.filter(p => {
    if (filter === 'all')  return true;
    if (filter === 'intl') return isIntl(p.type);
    if (filter === 'kci')  return p.type === 'KCI';
    return true;
  });

  document.getElementById('pubCount').textContent = `${filtered.length} papers`;

  const rows = filtered.map(p => {
    const cls  = isIntl(p.type) ? 'pb-intl' : 'pb-kci';
    const lbl  = isIntl(p.type) ? p.type : 'KCI';
    const newB = p.isNew ? `<span class="pb pb-new">New</span>` : '';
    const doiB = p.doi
      ? `<a class="detail-link" href="${p.doi}" target="_blank" onclick="event.stopPropagation()">View Paper ↗</a>`
      : `<span class="detail-link disabled">No link</span>`;
    return `
      <div class="pr" onclick="toggleDetail(this)">
        <div class="pr-head">
          <div class="pr-yr">${p.year}</div>
          <div>
            <div class="pr-title-text">${p.title}</div>
            <div class="pr-authors-preview">${p.authors} · <em>${p.journal}</em></div>
          </div>
          <div class="pr-badges">${newB}<span class="pb ${cls}">${lbl}</span></div>
        </div>
        <div class="pr-detail">
          <div class="detail-inner">
            <div class="detail-block">
              <div class="detail-row">
                <div class="detail-key">Authors</div>
                <div class="detail-val authors">${p.authors}</div>
              </div>
              <div class="detail-row">
                <div class="detail-key">Citation (APA)</div>
                <div class="detail-val citation">${p.citation}</div>
              </div>
            </div>
            ${doiB}
          </div>
        </div>
      </div>`;
  }).join('');

  document.getElementById('pubList').innerHTML = rows +
    `<a href="https://scholar.google.com" target="_blank" class="see-more">View full publication list on Google Scholar →</a>`;

  document.querySelectorAll('.pr').forEach((el, i) => {
    el.style.opacity = '0'; el.style.transform = 'translateY(8px)';
    el.style.transition = `opacity 0.32s ease ${i * 0.022}s, transform 0.32s ease ${i * 0.022}s`;
    setTimeout(() => { el.style.opacity = '1'; el.style.transform = 'none'; }, 10);
  });
}

function toggleDetail(el) {
  const d = el.querySelector('.pr-detail');
  const open = d.classList.contains('open');
  document.querySelectorAll('.pr-detail.open').forEach(x => x.classList.remove('open'));
  if (!open) d.classList.add('open');
}

function fp(type, btn) {
  document.querySelectorAll('.pfilt button').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  renderPubs(type);
}

renderTicker();
renderNews();
renderPubs('all');

const io = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (e.isIntersecting) { e.target.style.opacity='1'; e.target.style.transform='none'; io.unobserve(e.target); }
  });
}, { threshold: 0.05 });
document.querySelectorAll('.tr, .nc').forEach((el, i) => {
  el.style.opacity = '0'; el.style.transform = 'translateY(10px)';
  el.style.transition = `opacity 0.38s ease ${i*0.04}s, transform 0.38s ease ${i*0.04}s`;
  io.observe(el);
});
</script>
</body>
</html>
