
<!doctype html>
<html lang="en" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Topgamerx Studios</title>
  <script src="/_sdk/element_sdk.js"></script>
  <script src="/_sdk/data_sdk.js"></script>
  <style>
    body {
      box-sizing: border-box;
    }
    
    * {
      box-sizing: border-box;
    }
    
    html, body {
      margin: 0;
      padding: 0;
      height: 100%;
      width: 100%;
      scroll-behavior: smooth;
    }
    
    body {
      font-family: 'Space Grotesk', 'Rajdhani', 'Orbitron', -apple-system, sans-serif;
      background: #0a0a12;
      color: #e0e0e0;
      overflow-x: hidden;
    }
    
    .main-wrapper {
      width: 100%;
      min-height: 100%;
      overflow-y: auto;
      background: linear-gradient(135deg, #0a0a12 0%, #1a1a2e 50%, #0a0a12 100%);
    }
    
    /* Header Styles */
    header {
      background: linear-gradient(135deg, #6366f1 0%, #8b5cf6 50%, #d946ef 100%);
      padding: 50px 20px;
      text-align: center;
      position: relative;
      overflow: hidden;
    }
    
    header::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background: url('data:image/svg+xml,<svg width="100" height="100" xmlns="http://www.w3.org/2000/svg"><rect width="2" height="2" fill="white" opacity="0.1"/></svg>');
      opacity: 0.3;
      animation: float 20s infinite linear;
    }
    
    @keyframes float {
      from { transform: translateY(0); }
      to { transform: translateY(-100px); }
    }
    
    header h1 {
      margin: 0;
      font-size: 3.5rem;
      font-weight: 900;
      text-shadow: 0 4px 20px rgba(0,0,0,0.5);
      position: relative;
      z-index: 1;
      animation: slideDown 0.8s ease-out;
    }
    
    header p {
      margin-top: 12px;
      font-style: italic;
      font-size: 1.3rem;
      opacity: 0.95;
      position: relative;
      z-index: 1;
      animation: slideDown 0.8s ease-out 0.2s both;
    }
    
    @keyframes slideDown {
      from {
        opacity: 0;
        transform: translateY(-30px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
    
    /* Navigation */
    nav {
      background: rgba(17, 24, 39, 0.95);
      backdrop-filter: blur(10px);
      display: flex;
      justify-content: center;
      gap: 40px;
      padding: 16px 0;
      position: sticky;
      top: 0;
      z-index: 100;
      box-shadow: 0 4px 20px rgba(0,0,0,0.3);
    }
    
    nav a {
      color: #e0e0e0;
      text-decoration: none;
      font-weight: bold;
      font-size: 1.1rem;
      padding: 8px 16px;
      border-radius: 8px;
      transition: all 0.3s ease;
      position: relative;
    }
    
    nav a::after {
      content: '';
      position: absolute;
      bottom: 0;
      left: 50%;
      width: 0;
      height: 2px;
      background: linear-gradient(90deg, #6366f1, #8b5cf6);
      transition: all 0.3s ease;
      transform: translateX(-50%);
    }
    
    nav a:hover {
      color: #a78bfa;
      transform: translateY(-2px);
    }
    
    nav a:hover::after {
      width: 80%;
    }
    
    /* Sections */
    section {
      padding: 60px 20px;
      max-width: 1200px;
      margin: 0 auto;
      opacity: 0;
      transform: translateY(30px);
      transition: all 0.8s ease-out;
    }
    
    section.visible {
      opacity: 1;
      transform: translateY(0);
    }
    
    .card {
      background: linear-gradient(135deg, #1f2937 0%, #111827 100%);
      padding: 30px;
      border-radius: 16px;
      margin-bottom: 30px;
      box-shadow: 0 8px 30px rgba(0,0,0,0.4);
      border: 1px solid rgba(139, 92, 246, 0.2);
      transition: all 0.4s ease;
      position: relative;
      overflow: hidden;
    }
    
    .card::before {
      content: '';
      position: absolute;
      top: 0;
      left: -100%;
      width: 100%;
      height: 100%;
      background: linear-gradient(90deg, transparent, rgba(139, 92, 246, 0.1), transparent);
      transition: left 0.6s ease;
    }
    
    .card:hover {
      transform: translateY(-5px);
      box-shadow: 0 12px 40px rgba(139, 92, 246, 0.3);
      border-color: rgba(139, 92, 246, 0.5);
    }
    
    .card:hover::before {
      left: 100%;
    }
    
    .card h2 {
      color: #a78bfa;
      margin-top: 0;
      font-size: 2rem;
      margin-bottom: 16px;
    }
    
    .card ul {
      list-style: none;
      padding: 0;
    }
    
    .card ul li {
      padding: 12px 0;
      font-size: 1.1rem;
      border-bottom: 1px solid rgba(255,255,255,0.1);
      transition: all 0.3s ease;
    }
    
    .card ul li:hover {
      padding-left: 10px;
      color: #a78bfa;
    }
    
    .card ul li:last-child {
      border-bottom: none;
    }
    
    /* Games Showcase */
    .games-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 25px;
      margin-top: 30px;
    }
    
    .game-item {
      background: linear-gradient(135deg, #312e81 0%, #1e1b4b 100%);
      padding: 25px;
      border-radius: 12px;
      text-align: center;
      transition: all 0.4s ease;
      border: 2px solid transparent;
      cursor: pointer;
      text-decoration: none;
      color: inherit;
      display: block;
    }
    
    .game-item:hover {
      transform: scale(1.05) rotate(1deg);
      border-color: #8b5cf6;
      box-shadow: 0 15px 40px rgba(139, 92, 246, 0.4);
    }
    
    .game-item:active {
      transform: scale(0.98);
    }
    
    .game-icon {
      font-size: 4rem;
      margin-bottom: 15px;
      display: block;
      animation: bounce 2s infinite;
    }
    
    @keyframes bounce {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
    }
    
    .game-item:hover .game-icon {
      animation: spin 0.6s ease;
    }
    
    @keyframes spin {
      from { transform: rotate(0deg); }
      to { transform: rotate(360deg); }
    }
    
    .game-item h3 {
      color: #e0e0e0;
      margin: 10px 0;
      font-size: 1.3rem;
    }
    
    .game-item p {
      color: #9ca3af;
      font-size: 0.95rem;
    }
    
    /* Contact Form */
    .contact-form {
      max-width: 600px;
      margin: 30px auto;
    }
    
    .form-group {
      margin-bottom: 20px;
    }
    
    .form-group label {
      display: block;
      margin-bottom: 8px;
      color: #a78bfa;
      font-weight: bold;
    }
    
    .form-group input,
    .form-group textarea {
      width: 100%;
      padding: 12px;
      background: rgba(31, 41, 55, 0.8);
      border: 2px solid rgba(139, 92, 246, 0.3);
      border-radius: 8px;
      color: #e0e0e0;
      font-size: 1rem;
      font-family: inherit;
      transition: all 0.3s ease;
    }
    
    .form-group input:focus,
    .form-group textarea:focus {
      outline: none;
      border-color: #8b5cf6;
      box-shadow: 0 0 20px rgba(139, 92, 246, 0.3);
    }
    
    .form-group textarea {
      min-height: 120px;
      resize: vertical;
    }
    
    .submit-btn {
      background: linear-gradient(135deg, #6366f1, #8b5cf6);
      color: white;
      border: none;
      padding: 14px 40px;
      border-radius: 8px;
      font-size: 1.1rem;
      font-weight: bold;
      cursor: pointer;
      transition: all 0.3s ease;
      box-shadow: 0 4px 15px rgba(139, 92, 246, 0.4);
      width: 100%;
    }
    
    .submit-btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 6px 25px rgba(139, 92, 246, 0.6);
    }
    
    .submit-btn:active {
      transform: translateY(0);
    }
    
    .submit-btn:disabled {
      opacity: 0.6;
      cursor: not-allowed;
      transform: none;
    }
    
    .form-message {
      margin-top: 20px;
      padding: 15px;
      border-radius: 8px;
      text-align: center;
      font-weight: bold;
      animation: slideDown 0.5s ease;
    }
    
    .form-message.success {
      background: rgba(34, 197, 94, 0.2);
      border: 2px solid #22c55e;
      color: #4ade80;
    }
    
    .form-message.error {
      background: rgba(239, 68, 68, 0.2);
      border: 2px solid #ef4444;
      color: #f87171;
    }
    
    .messages-list {
      margin-top: 40px;
    }
    
    .message-item {
      background: rgba(31, 41, 55, 0.6);
      padding: 20px;
      border-radius: 10px;
      margin-bottom: 15px;
      border-left: 4px solid #8b5cf6;
    }
    
    .message-item h4 {
      margin: 0 0 5px 0;
      color: #a78bfa;
    }
    
    .message-item .email {
      color: #9ca3af;
      font-size: 0.9rem;
      margin-bottom: 10px;
    }
    
    .message-item .content {
      color: #e0e0e0;
      line-height: 1.6;
    }
    
    .message-item .timestamp {
      color: #6b7280;
      font-size: 0.85rem;
      margin-top: 10px;
    }
    
    /* Footer */
    footer {
      background: #020617;
      text-align: center;
      padding: 30px 20px;
      font-size: 1rem;
      opacity: 0.9;
      border-top: 2px solid rgba(139, 92, 246, 0.3);
    }
    
    /* Loading Spinner */
    .spinner {
      display: inline-block;
      width: 16px;
      height: 16px;
      border: 2px solid rgba(255,255,255,0.3);
      border-top-color: white;
      border-radius: 50%;
      animation: spin-loader 0.8s linear infinite;
    }
    
    @keyframes spin-loader {
      to { transform: rotate(360deg); }
    }
    
    /* Responsive */
    @media (max-width: 768px) {
      header h1 {
        font-size: 2.5rem;
      }
      
      header p {
        font-size: 1.1rem;
      }
      
      nav {
        gap: 15px;
        flex-wrap: wrap;
        padding: 12px 10px;
      }
      
      nav a {
        font-size: 0.95rem;
        padding: 6px 12px;
      }
      
      section {
        padding: 40px 15px;
      }
      
      .games-grid {
        grid-template-columns: 1fr;
      }
    }
  </style>
  <style>@view-transition { navigation: auto; }</style>
  <script src="https://cdn.tailwindcss.com" type="text/javascript"></script>
 </head>
 <body class="h-full">
  <div class="main-wrapper" id="mainContent"><!-- HEADER -->
   <header>
    <div style="text-align: center; margin-bottom: 20px;"><img src="https://chatgpt.com/backend-api/estuary/content?id=file_00000000286c71f5a2c13e4efa094af0&amp;cp=pri&amp;ma=90000&amp;ts=20470&amp;p=igh&amp;cid=1&amp;sig=422c950ba22dd0b795008b33a80e24d2c537f07f04b3b895b1717ffa71afcb1a" alt="Topgamerx Studios Logo" loading="lazy" onerror="console.error('Logo failed to load'); this.style.display='none';" style="max-width: 250px; width: 100%; height: auto; display: inline-block; border-radius: 16px; box-shadow: 0 8px 30px rgba(139, 92, 246, 0.5); border: 3px solid rgba(255,255,255,0.2); animation: slideDown 0.8s ease-out; background: white; padding: 10px;">
    </div>
    <div style="text-align: center; margin-bottom: 20px;"><img src="https://chatgpt.com/backend-api/estuary/content?id=file_00000000fcc4722f8a4ecd501b41152f&amp;cp=pri&amp;ma=90000&amp;ts=20470&amp;p=igh&amp;cid=1&amp;sig=8adffbcf74750e46db9c2491aa2de4a50c738bc7b814ca6ba9adce1f734d0495" alt="Topgamerx Studios Banner" loading="lazy" onerror="console.error('Banner failed to load'); this.style.display='none';" style="max-width: 800px; width: 100%; height: auto; display: inline-block; border-radius: 12px; box-shadow: 0 6px 25px rgba(0,0,0,0.4); animation: slideDown 0.8s ease-out 0.2s both;">
    </div>
    <h1 id="studio-name">Topgamerx Studios</h1>
    <p id="tagline">Creativity Rules</p>
   </header><!-- NAVIGATION -->
   <nav><a href="#home">Home</a> <a href="#news">News</a> <a href="#games">Games</a> <a href="#collabs">Collabs</a> <a href="#motivation">Motivation</a> <a href="#signup">Sign Up</a> <a href="#htmlblox">htmlblox</a> <a href="#employee">Employee</a> <a href="#toptv">TopTV</a> <a href="#gamejoin">Game Join</a> <a href="#contact">Contact</a>
   </nav><!-- HOME PAGE -->
   <section id="home">
    <div class="card">
     <h2 id="welcome-title">Welcome to Topgamerx Studios</h2>
     <p id="welcome-text">Whenever you're looking for wacky, chaotic Poople sewer moments or unbelievably fun and creative Roblox games, Topgamerx Studios has it all. Founded by the gamer legend Topgamerx, we always put creativity before business.</p>
    </div>
   </section><!-- NEWS PAGE -->
   <section id="news">
    <div class="card">
     <h2>Latest News</h2>
     <ul>
      <li>🚽 New Poople project in development!</li>
      <li>🎮 Roblox game updates coming soon.</li>
      <li>🧱 New creative experiments and game ideas being tested.</li>
     </ul>
    </div>
   </section><!-- GAMES PAGE -->
   <section id="games">
    <div class="card">
     <h2>Our Games &amp; Apps</h2>
     <p>Explore the worlds and experiences created by Topgamerx Studios:</p>
     <div class="games-grid"><a href="https://poople-universe-navigator-4f470ef3.base44.app" target="_blank" rel="noopener noreferrer" class="game-item"> <span class="game-icon">💩</span> <h3>Poople Universe Navigator</h3><p>Navigate the chaotic Poople universe</p></a> <a href="https://topgamerx.my.canva.site/play-poople-com" target="_blank" rel="noopener noreferrer" class="game-item"> <span class="game-icon">🚽</span> <h3>Play Poople</h3><p>The official Poople gaming experience</p></a> <a href="https://gamer-x-nexus-46dbeaa1.base44.app" target="_blank" rel="noopener noreferrer" class="game-item"> <span class="game-icon">🎮</span> <h3>Gamer X Nexus</h3><p>Your ultimate gaming hub and community</p></a> <a href="https://calc-bot-adventure-09296d78.base44.app" target="_blank" rel="noopener noreferrer" class="game-item"> <span class="game-icon">����</span> <h3>Calc Bot Adventure</h3><p>Math meets adventure in this wild journey</p></a> <a href="https://calculator-clicker-49c38a50.base44.app" target="_blank" rel="noopener noreferrer" class="game-item"> <span class="game-icon">🔢</span> <h3>Calculator Clicker</h3><p>Click your way to calculation mastery</p></a> <a href="https://ai-forge-2351a779.base44.app" target="_blank" rel="noopener noreferrer" class="game-item"> <span class="game-icon">🤖</span> <h3>AI Forge</h3><p>Create and experiment with AI tools</p></a>
     </div>
    </div>
   </section><!-- COLLABS PAGE -->
   <section id="collabs">
    <div class="card">
     <h2>Our Collaborations</h2>
     <p>We're proud to partner with these amazing companies and studios:</p><!-- Roblox Studio Callout -->
     <div style="background: linear-gradient(135deg, #e91e63 0%, #9c27b0 100%); padding: 25px; border-radius: 12px; margin: 25px 0; text-align: center; border: 2px solid #ce93d8;">
      <h3 style="margin: 0 0 10px 0; font-size: 1.6rem;">🎮 Join Our Roblox Studio!</h3>
      <p style="margin: 10px 0; font-size: 1.1rem;">Want to build amazing experiences with us?</p><a href="https://www.roblox.com/communities/34259388/TOPGAMERX-STUDIOS#!/about" target="_blank" rel="noopener noreferrer" style="display: inline-block; background: white; color: #9c27b0; padding: 12px 30px; border-radius: 8px; text-decoration: none; font-weight: bold; margin: 10px 0; transition: all 0.3s ease; box-shadow: 0 4px 15px rgba(0,0,0,0.3);"> Visit TOPGAMERX STUDIOS on Roblox </a>
      <p style="margin: 10px 0 0 0; font-size: 0.95rem; opacity: 0.9;">💬 Interested in becoming a builder? Contact us to join the team!</p>
     </div>
     <div class="games-grid"><a href="https://www.roblox.com" target="_blank" rel="noopener noreferrer" class="game-item"> <span class="game-icon">🎮</span> <h3>Roblox Corp</h3><p>The ultimate platform for imagination</p></a> <a href="https://www.base44.com" target="_blank" rel="noopener noreferrer" class="game-item"> <span class="game-icon">🚀</span> <h3>Base44</h3><p>Innovation and technology partners</p></a> <a href="https://www.infinitygames.io" target="_blank" rel="noopener noreferrer" class="game-item"> <span class="game-icon">♾️</span> <h3>Infinity Games</h3><p>Endless gaming possibilities</p></a> <a href="https://zbonesstudios.com" target="_blank" rel="noopener noreferrer" class="game-item"> <span class="game-icon">💀</span> <h3>Zbones Studios</h3><p>Creative gaming experiences</p></a> <a href="https://www.tacobell.com" target="_blank" rel="noopener noreferrer" class="game-item"> <span class="game-icon">��</span> <h3>Taco Bell</h3><p>Live más in gaming</p></a> <a href="https://www.chick-fil-a.com" target="_blank" rel="noopener noreferrer" class="game-item"> <span class="game-icon">🐔</span> <h3>Chick-fil-A</h3><p>Eat mor gaming experiences</p></a> <a href="https://www.mcdonalds.com" target="_blank" rel="noopener noreferrer" class="game-item"> <span class="game-icon">🍔</span> <h3>McDonald's</h3><p>I'm lovin' it gaming</p></a> <a href="https://www.bk.com" target="_blank" rel="noopener noreferrer" class="game-item"> <span class="game-icon">👑</span> <h3>Burger King</h3><p>Have it your way in games</p></a> <a href="https://www.vilros.com" target="_blank" rel="noopener noreferrer" class="game-item"> <span class="game-icon">������</span> <h3>Vilros</h3><p>Tech and hardware innovation</p></a>
     </div>
    </div>
   </section><!-- MOTIVATION PAGE -->
   <section id="motivation">
    <div class="card">
     <h2>🎮 Gamer Motivation &amp; Jokes 🎮</h2>
     <p style="font-size: 1.2rem; text-align: center; margin: 20px 0; color: #a78bfa; font-weight: bold;">Remember: You are AWESOME! Everyone deserves a chance, no matter who you are. Never give up! 💪✨</p>
     <div style="background: rgba(139, 92, 246, 0.1); padding: 25px; border-radius: 12px; margin: 25px 0; border-left: 5px solid #8b5cf6;">
      <h3 style="color: #a78bfa; margin-top: 0;">💪 Words of Power</h3>
      <ul style="line-height: 2; font-size: 1.1rem;">
       <li>🌟 <strong>You've got unlimited respawns in life</strong> - Every setback is just a checkpoint, not game over!</li>
       <li>🎯 <strong>Level up every day</strong> - Small progress is still progress. You're gaining XP with every challenge!</li>
       <li>🏆 <strong>Your journey is YOUR game</strong> - Don't compare your Chapter 3 to someone else's Chapter 20!</li>
       <li>⚡ <strong>Lag happens to everyone</strong> - Tough times are just server issues. Keep playing!</li>
       <li>🎮 <strong>You're the main character</strong> - Your story matters. Your victories matter. YOU matter!</li>
       <li>��� <strong>No one starts as a pro</strong> - Every legend was once a noob. Keep grinding!</li>
       <li>🔥 <strong>Boss battles make you stronger</strong> - Hard times are just training you for the epic win ahead!</li>
       <li>🌈 <strong>Your squad believes in you</strong> - You're never playing solo. We're all rooting for you!</li>
      </ul>
     </div>
     <div style="background: linear-gradient(135deg, #312e81 0%, #1e1b4b 100%); padding: 25px; border-radius: 12px; margin: 25px 0;">
      <h3 style="color: #a78bfa; margin-top: 0;">😂 Gamer Jokes to Boost Your HP</h3>
      <div style="line-height: 2.2; font-size: 1.05rem;">
       <p>🎮 <strong>Why do gamers never get locked out?</strong><br>
        Because they always find the KEY to success! 🔑</p>
       <p>��� <strong>What's a gamer's favorite type of music?</strong><br>
        Anything with good CONTROLS! 🎵</p>
       <p>🏃 <strong>Why did the gamer cross the road?</strong><br>
        To render the other side! 😄</p>
       <p>🎯 <strong>How do gamers stay cool?</strong><br>
        They stand next to their fans! (Both kinds! 😅)</p>
       <p>🍕 <strong>Why did the gamer bring a ladder to the game?</strong><br>
        To reach the NEXT LEVEL! 🪜</p>
       <p>⌨️ <strong>What do you call a gamer who just broke up?</strong><br>
        Single-player mode! (But you're still multiplayer material! ��)</p>
       <p>🌟 <strong>Why are gamers the best friends?</strong><br>
        Because they never RAGE QUIT on you! 🤝</p>
       <p>🎨 <strong>What's a gamer's favorite subject?</strong><br>
        GRAPHICS design! 📊</p>
      </div>
     </div>
     <div style="text-align: center; background: linear-gradient(135deg, #e91e63 0%, #9c27b0 100%); padding: 30px; border-radius: 12px; margin: 25px 0;">
      <h3 style="margin-top: 0; font-size: 1.8rem;">🏆 Daily Power-Up 🏆</h3>
      <p style="font-size: 1.3rem; line-height: 1.8; margin: 20px 0;"><strong>Remember:</strong> Every pro was once a beginner.<br>
        Every expert was once a noob.<br>
        Every legend faced defeat.<br><span style="font-size: 1.5rem; color: #ffeb3b;">But they NEVER gave up! 🔥</span></p>
      <p style="font-size: 1.2rem; margin-top: 20px;">You're not just playing the game of life...<br><strong style="font-size: 1.4rem; color: #ffeb3b;">YOU'RE WINNING IT! 👑</strong></p>
     </div>
     <div style="text-align: center; margin: 30px 0; padding: 20px;">
      <p style="font-size: 1.3rem; color: #a78bfa;">💖 <em>Everyone deserves a chance. Everyone deserves respect. Everyone is worthy of greatness.</em> 💖</p>
      <p style="font-size: 1.5rem; font-weight: bold; color: #ffeb3b; margin-top: 20px;">And that includes YOU! 🌟</p>
     </div>
    </div>
   </section><!-- SIGN UP PAGE -->
   <section id="signup">
    <div class="card">
     <h2>🎮 Join Topgamerx Studios! 🎮</h2>
     <p style="text-align: center; font-size: 1.2rem; margin: 20px 0;">Sign up to become part of our amazing gaming community! Get exclusive updates, early access to games, and connect with fellow gamers! 🌟</p>
     <form class="contact-form" id="signupForm">
      <div class="form-group"><label for="signup-username">Username</label> <input type="text" id="signup-username" name="username" required placeholder="Choose your gamer tag">
      </div>
      <div class="form-group"><label for="signup-email">Email</label> <input type="email" id="signup-email" name="email" required placeholder="your.email@example.com">
      </div>
      <div class="form-group"><label for="signup-favorite-game">Favorite Game Type</label> <input type="text" id="signup-favorite-game" name="favorite_game" placeholder="Adventure, RPG, Puzzle, etc.">
      </div>
      <div class="form-group"><label for="signup-platform">Preferred Platform</label> <input type="text" id="signup-platform" name="platform" placeholder="Roblox, PC, Mobile, Console, etc.">
      </div><button type="submit" class="submit-btn" id="signupBtn"> Sign Up Now! 🚀 </button>
     </form>
     <div id="signupMessage"></div>
     <div class="messages-list" id="signupsList"></div>
    </div>
   </section><!-- HTMLBLOX GAMES CENTER -->
   <section id="htmlblox">
    <div class="card">
     <h2>������ htmlblox Games Center 🎮</h2><!-- Passcode Protection for htmlblox -->
     <div id="htmlbloxLock" style="text-align: center; padding: 40px 20px;">
      <p style="font-size: 1.3rem; color: #a78bfa; margin-bottom: 25px;">🔒 This section is protected</p>
      <div style="max-width: 400px; margin: 0 auto;"><input type="password" id="htmlbloxPasscodeInput" placeholder="Enter passcode" style="width: 100%; padding: 12px; font-size: 1.1rem; background: rgba(31, 41, 55, 0.8); border: 2px solid rgba(139, 92, 246, 0.3); border-radius: 8px; color: #e0e0e0; text-align: center; font-family: inherit; margin-bottom: 15px;"> <button id="htmlbloxSubmitPasscode" style="width: 100%; padding: 12px; font-size: 1.1rem; font-weight: bold; background: linear-gradient(135deg, #6366f1, #8b5cf6); color: white; border: none; border-radius: 8px; cursor: pointer; transition: all 0.3s ease; box-shadow: 0 4px 15px rgba(139, 92, 246, 0.4);"> Unlock 🔓 </button>
       <p id="htmlbloxPasscodeError" style="color: #ef4444; margin: 15px 0 0 0; font-weight: bold; display: none;">❌ Incorrect passcode</p>
      </div>
     </div><!-- Protected Content -->
     <div id="htmlbloxContent" style="display: none;">
      <p style="text-align: center; font-size: 1.2rem; margin: 20px 0;">Check out our collection of brainrot games! Pure chaos and fun! ��💥</p>
      <div class="games-grid"><a href="https://sites.google.com/wpsstudent.us/brainrotbgesonly/home" target="_blank" rel="noopener noreferrer" class="game-item"> <span class="game-icon">🧠</span> <h3>Brainrot BGE Games</h3><p>The ultimate brainrot gaming experience</p></a>
      </div>
     </div>
    </div>
   </section><!-- EMPLOYEE WORKSPACE -->
   <section id="employee">
    <div class="card">
     <h2>💼 Employee Workspace 🔧</h2><!-- Passcode Protection for Employee Area -->
     <div id="employeeLock" style="text-align: center; padding: 40px 20px;">
      <p style="font-size: 1.3rem; color: #a78bfa; margin-bottom: 15px;">🔒 Employees &amp; Build-a-thon Only</p>
      <p style="font-size: 1rem; color: #9ca3af; margin-bottom: 25px;">This section is restricted to authorized staff and build-a-thon participants</p>
      <div style="max-width: 400px; margin: 0 auto;"><input type="password" id="employeePasscodeInput" placeholder="Enter employee passcode" style="width: 100%; padding: 12px; font-size: 1.1rem; background: rgba(31, 41, 55, 0.8); border: 2px solid rgba(139, 92, 246, 0.3); border-radius: 8px; color: #e0e0e0; text-align: center; font-family: inherit; margin-bottom: 15px;"> <button id="employeeSubmitPasscode" style="width: 100%; padding: 12px; font-size: 1.1rem; font-weight: bold; background: linear-gradient(135deg, #6366f1, #8b5cf6); color: white; border: none; border-radius: 8px; cursor: pointer; transition: all 0.3s ease; box-shadow: 0 4px 15px rgba(139, 92, 246, 0.4);"> Access Workspace 🚀 </button>
       <p id="employeePasscodeError" style="color: #ef4444; margin: 15px 0 0 0; font-weight: bold; display: none;">❌ Access denied - Invalid passcode</p>
      </div>
     </div><!-- Protected Employee Content -->
     <div id="employeeContent" style="display: none;">
      <p style="text-align: center; font-size: 1.2rem; margin: 20px 0; color: #4ade80;">✅ Access Granted - Welcome to the team workspace! 💼</p>
      <div class="games-grid"><a href="https://tgxs-workspace-d53a8dd6.base44.app" target="_blank" rel="noopener noreferrer" class="game-item"> <span class="game-icon">💼</span> <h3>TGXS Workspace</h3><p>Main employee workspace and collaboration hub</p></a> <a href="https://poople-wiffleball-adventure-irl-34d1999e.base44.app" target="_blank" rel="noopener noreferrer" class="game-item"> <span class="game-icon">⚾</span> <h3>Poople Wiffleball Adventure IRL</h3><p>Build-a-thon project workspace</p></a>
      </div>
     </div>
    </div>
   </section><!-- TOPGAMERX GAMES JOINING -->
   <section id="gamejoin">
    <div class="card">
     <h2>🎮 Join TopGamerx Games 🏆</h2>
     <div style="text-align: center; margin-bottom: 30px;">
      <div style="background: linear-gradient(135deg, #312e81 0%, #1e1b4b 100%); padding: 25px; border-radius: 12px; margin: 20px auto; max-width: 500px; border: 2px solid #8b5cf6;">
       <h3 style="color: #a78bfa; margin-top: 0;">🔥 Game Registration Status</h3>
       <p style="font-size: 1.2rem; color: #e0e0e0; margin: 15px 0;">Available Spots:</p>
       <p id="availableSpots" style="font-size: 3rem; color: #4ade80; font-weight: bold; margin: 10px 0;">50 / 50</p>
       <div id="gameStatus" style="margin-top: 15px; padding: 10px; border-radius: 8px; font-weight: bold; font-size: 1.1rem;"></div>
      </div>
     </div><!-- Registration Form -->
     <div id="gameRegistrationForm">
      <p style="text-align: center; font-size: 1.2rem; margin: 20px 0;">Register now to secure your spot in the next TopGamerx Arena match! 🎯</p>
      <form class="contact-form" id="gameJoinForm">
       <div class="form-group"><label for="game-name">Player Name</label> <input type="text" id="game-name" name="name" required placeholder="Enter your gamer name">
       </div>
       <div class="form-group"><label for="game-email">Email Address</label> <input type="email" id="game-email" name="email" required placeholder="your.email@example.com">
       </div>
       <div class="form-group"><label for="game-username">Game Username (Optional)</label> <input type="text" id="game-username" name="username" placeholder="Your in-game username">
       </div><button type="submit" class="submit-btn" id="gameJoinBtn"> Register for Game 🚀 </button>
      </form>
      <div id="gameJoinMessage"></div>
     </div><!-- Access Game Section (for returning players) -->
     <div style="margin-top: 50px; padding-top: 30px; border-top: 2px solid rgba(139, 92, 246, 0.3);">
      <h3 style="color: #a78bfa; text-align: center; margin-bottom: 20px;">Already Registered? 🎮</h3>
      <p style="text-align: center; margin-bottom: 25px;">Enter your registration number and email to access the game:</p>
      <form class="contact-form" id="gameAccessForm" style="max-width: 500px;">
       <div class="form-group"><label for="access-number">Registration Number</label> <input type="text" id="access-number" name="number" required placeholder="e.g., #001">
       </div>
       <div class="form-group"><label for="access-email">Email Address</label> <input type="email" id="access-email" name="email" required placeholder="your.email@example.com">
       </div><button type="submit" class="submit-btn" id="gameAccessBtn"> Access Game 🎯 </button>
      </form>
      <div id="gameAccessMessage"></div>
     </div><!-- Registered Players List -->
     <div class="messages-list" id="gamePlayersList" style="margin-top: 40px;"></div>
    </div>
   </section><!-- TOPTV SUBSCRIPTION -->
   <section id="toptv">
    <div class="card">
     <h2>📺 TopTV Streaming 🎬</h2><!-- TopTV Subscription Area -->
     <div id="toptvSubscription">
      <div style="text-align: center; padding: 30px 20px;">
       <p style="font-size: 1.3rem; color: #a78bfa; margin-bottom: 15px;">Premium Streaming Content</p>
       <p style="font-size: 1.1rem; color: #e0e0e0; margin-bottom: 25px;">Subscribe now to access exclusive shows, movies, and live streams! 🌟</p>
       <div style="background: linear-gradient(135deg, #312e81 0%, #1e1b4b 100%); padding: 30px; border-radius: 12px; margin: 25px auto; max-width: 500px; border: 2px solid #8b5cf6;">
        <h3 style="color: #a78bfa; margin-top: 0;">Monthly Subscription</h3>
        <p style="font-size: 2rem; color: #4ade80; font-weight: bold; margin: 20px 0;">$9.99/month</p>
        <ul style="text-align: left; margin: 20px 0; line-height: 2;">
         <li>✅ Unlimited streaming</li>
         <li>✅ HD &amp; 4K quality</li>
         <li>✅ Exclusive TopGamerx content</li>
         <li>✅ No ads</li>
         <li>✅ Cancel anytime</li>
        </ul><button id="subscribeBtn" style="width: 100%; padding: 15px; font-size: 1.2rem; font-weight: bold; background: linear-gradient(135deg, #4ade80, #22c55e); color: white; border: none; border-radius: 10px; cursor: pointer; transition: all 0.3s ease; box-shadow: 0 4px 15px rgba(34, 197, 94, 0.4); margin-top: 10px;"> Pay with Poople Pay 💩💳 </button>
       </div>
      </div>
     </div><!-- Subscription Code Input (shown after payment) -->
     <div id="toptvCodeEntry" style="display: none;">
      <div style="text-align: center; padding: 30px 20px;">
       <p style="font-size: 1.3rem; color: #4ade80; margin-bottom: 15px;">✅ Payment Successful!</p>
       <p style="font-size: 1.1rem; color: #e0e0e0; margin-bottom: 25px;">Your subscription code has been generated. Save it to access TopTV!</p>
       <div style="background: rgba(74, 222, 128, 0.1); padding: 25px; border-radius: 12px; margin: 25px auto; max-width: 450px; border: 2px solid #4ade80;">
        <h3 style="color: #4ade80; margin-top: 0;">Your Subscription Code</h3>
        <p id="generatedCode" style="font-size: 2.5rem; color: #4ade80; font-weight: bold; letter-spacing: 3px; margin: 20px 0; font-family: monospace;"></p>
        <p style="font-size: 0.95rem; color: #9ca3af; margin: 15px 0;">Valid for 1 month from today</p><button id="copyCodeBtn" style="padding: 12px 30px; font-size: 1rem; font-weight: bold; background: linear-gradient(135deg, #6366f1, #8b5cf6); color: white; border: none; border-radius: 8px; cursor: pointer; transition: all 0.3s ease; margin: 10px 5px;"> 📋 Copy Code </button> <button id="accessToptvBtn" style="padding: 12px 30px; font-size: 1rem; font-weight: bold; background: linear-gradient(135deg, #4ade80, #22c55e); color: white; border: none; border-radius: 8px; cursor: pointer; transition: all 0.3s ease; margin: 10px 5px;"> 🎬 Access TopTV </button>
       </div>
       <p style="font-size: 0.9rem; color: #9ca3af; margin-top: 20px;">💡 Tip: Save your code! You'll need it to log into TopTV.</p>
      </div>
     </div>
    </div>
   </section><!-- CONTACT PAGE -->
   <section id="contact">
    <div class="card">
     <h2>Contact Us</h2>
     <p>Have questions or ideas? Send us a message!</p>
     <form class="contact-form" id="contactForm">
      <div class="form-group"><label for="name">Name</label> <input type="text" id="name" name="name" required>
      </div>
      <div class="form-group"><label for="email">Email</label> <input type="email" id="email" name="email" required>
      </div>
      <div class="form-group"><label for="message">Message</label> <textarea id="message" name="message" required></textarea>
      </div><button type="submit" class="submit-btn" id="submitBtn"> Send Message </button>
     </form>
     <div id="formMessage"></div>
     <div class="messages-list" id="messagesList"></div>
    </div>
   </section><!-- FOOTER -->
   <footer>
    <p id="footer-text">© 2026 Topgamerx Studios · Creativity Rules</p>
   </footer>
  </div>
  <script>
    // Passcode Protection for htmlblox section
    const htmlbloxCorrectPasscode = '67896790';
    const htmlbloxPasscodeInput = document.getElementById('htmlbloxPasscodeInput');
    const htmlbloxSubmitPasscode = document.getElementById('htmlbloxSubmitPasscode');
    const htmlbloxPasscodeError = document.getElementById('htmlbloxPasscodeError');
    const htmlbloxLock = document.getElementById('htmlbloxLock');
    const htmlbloxContent = document.getElementById('htmlbloxContent');

    function checkHtmlbloxPasscode() {
      if (htmlbloxPasscodeInput.value === htmlbloxCorrectPasscode) {
        htmlbloxLock.style.display = 'none';
        htmlbloxContent.style.display = 'block';
      } else {
        htmlbloxPasscodeError.style.display = 'block';
        htmlbloxPasscodeInput.value = '';
        htmlbloxPasscodeInput.style.borderColor = '#ef4444';
        setTimeout(() => {
          htmlbloxPasscodeInput.style.borderColor = 'rgba(139, 92, 246, 0.3)';
        }, 1000);
      }
    }

    htmlbloxSubmitPasscode.addEventListener('click', checkHtmlbloxPasscode);
    htmlbloxPasscodeInput.addEventListener('keypress', (e) => {
      if (e.key === 'Enter') {
        checkHtmlbloxPasscode();
      }
      htmlbloxPasscodeError.style.display = 'none';
    });

    // Passcode Protection for Employee section
    const employeeCorrectPasscode = '21042';
    const employeePasscodeInput = document.getElementById('employeePasscodeInput');
    const employeeSubmitPasscode = document.getElementById('employeeSubmitPasscode');
    const employeePasscodeError = document.getElementById('employeePasscodeError');
    const employeeLock = document.getElementById('employeeLock');
    const employeeContent = document.getElementById('employeeContent');

    function checkEmployeePasscode() {
      if (employeePasscodeInput.value === employeeCorrectPasscode) {
        employeeLock.style.display = 'none';
        employeeContent.style.display = 'block';
      } else {
        employeePasscodeError.style.display = 'block';
        employeePasscodeInput.value = '';
        employeePasscodeInput.style.borderColor = '#ef4444';
        setTimeout(() => {
          employeePasscodeInput.style.borderColor = 'rgba(139, 92, 246, 0.3)';
        }, 1000);
      }
    }

    employeeSubmitPasscode.addEventListener('click', checkEmployeePasscode);
    employeePasscodeInput.addEventListener('keypress', (e) => {
      if (e.key === 'Enter') {
        checkEmployeePasscode();
      }
      employeePasscodeError.style.display = 'none';
    });

    // TopTV Subscription System
    function generateRandomCode() {
      const chars = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789';
      let code = '';
      for (let i = 0; i < 8; i++) {
        code += chars.charAt(Math.floor(Math.random() * chars.length));
      }
      return code;
    }

    const subscribeBtn = document.getElementById('subscribeBtn');
    const toptvSubscription = document.getElementById('toptvSubscription');
    const toptvCodeEntry = document.getElementById('toptvCodeEntry');
    const generatedCode = document.getElementById('generatedCode');
    const copyCodeBtn = document.getElementById('copyCodeBtn');
    const accessToptvBtn = document.getElementById('accessToptvBtn');

    subscribeBtn.addEventListener('click', () => {
      // Generate random subscription code
      const subCode = generateRandomCode();
      generatedCode.textContent = subCode;
      
      // Show code entry screen
      toptvSubscription.style.display = 'none';
      toptvCodeEntry.style.display = 'block';
    });

    copyCodeBtn.addEventListener('click', () => {
      const code = generatedCode.textContent;
      navigator.clipboard.writeText(code).then(() => {
        const originalText = copyCodeBtn.textContent;
        copyCodeBtn.textContent = '✅ Copied!';
        setTimeout(() => {
          copyCodeBtn.textContent = originalText;
        }, 2000);
      });
    });

    accessToptvBtn.addEventListener('click', () => {
      window.open('https://app-toptv-027ec6a3-05d4-43d5-bcc9-8af17892753d.base44.app', '_blank', 'noopener,noreferrer');
    });

    // Default Configuration
    const defaultConfig = {
      studio_name: "Topgamerx Studios",
      tagline: "Creativity Rules",
      welcome_title: "Welcome to Topgamerx Studios",
      welcome_text: "Whenever you're looking for wacky, chaotic Poople sewer moments or unbelievably fun and creative Roblox games, Topgamerx Studios has it all. Founded by the gamer legend Topgamerx, we always put creativity before business.",
      footer_text: "© 2026 Topgamerx Studios · Creativity Rules",
      background_color: "#0a0a12",
      header_color: "#8b5cf6",
      card_color: "#1f2937",
      text_color: "#e0e0e0",
      accent_color: "#a78bfa",
      font_family: "Space Grotesk",
      font_size: 16
    };

    // Data handler for messages, signups, and game registrations
    let currentMessages = [];
    let currentSignups = [];
    let currentGamePlayers = [];
    let allData = [];
    const MAX_GAME_SPOTS = 50;
    
    const dataHandler = {
      onDataChanged(data) {
        allData = data;
        currentMessages = data.filter(item => item.type === 'message' || !item.type);
        currentSignups = data.filter(item => item.type === 'signup');
        currentGamePlayers = data.filter(item => item.type === 'game_registration');
        renderMessages(currentMessages);
        renderSignups(currentSignups);
        renderGamePlayers(currentGamePlayers);
        updateGameStatus(currentGamePlayers.length);
      }
    };

    // Initialize Data SDK
    (async () => {
      const initResult = await window.dataSdk.init(dataHandler);
      if (!initResult.isOk) {
        console.error("Failed to initialize data SDK");
      }
    })();

    // Update game registration status
    function updateGameStatus(playerCount) {
      const availableSpots = document.getElementById('availableSpots');
      const gameStatus = document.getElementById('gameStatus');
      const gameRegistrationForm = document.getElementById('gameRegistrationForm');
      
      const spotsLeft = MAX_GAME_SPOTS - playerCount;
      availableSpots.textContent = `${spotsLeft} / ${MAX_GAME_SPOTS}`;
      
      if (spotsLeft === 0) {
        availableSpots.style.color = '#ef4444';
        gameStatus.style.background = 'rgba(239, 68, 68, 0.2)';
        gameStatus.style.border = '2px solid #ef4444';
        gameStatus.style.color = '#f87171';
        gameStatus.textContent = '🔒 GAME FULL - Registration Closed';
        gameRegistrationForm.style.opacity = '0.5';
        gameRegistrationForm.style.pointerEvents = 'none';
      } else if (spotsLeft <= 5) {
        availableSpots.style.color = '#fbbf24';
        gameStatus.style.background = 'rgba(251, 191, 36, 0.2)';
        gameStatus.style.border = '2px solid #fbbf24';
        gameStatus.style.color = '#fcd34d';
        gameStatus.textContent = '⚠️ Almost Full - Register Now!';
      } else {
        availableSpots.style.color = '#4ade80';
        gameStatus.style.background = 'rgba(74, 222, 128, 0.2)';
        gameStatus.style.border = '2px solid #4ade80';
        gameStatus.style.color = '#4ade80';
        gameStatus.textContent = '✅ Open for Registration';
      }
    }

    // Render game players
    function renderGamePlayers(players) {
      const playersList = document.getElementById('gamePlayersList');
      
      if (players.length === 0) {
        playersList.innerHTML = '';
        return;
      }
      
      const sortedPlayers = [...players].sort((a, b) => 
        parseInt(a.player_number) - parseInt(b.player_number)
      );
      
      playersList.innerHTML = '<h3 style="color: #a78bfa; margin-bottom: 20px;">🎮 Registered Players</h3>';
      
      sortedPlayers.forEach(player => {
        const playerDiv = document.createElement('div');
        playerDiv.className = 'message-item';
        
        const date = new Date(player.timestamp);
        const formattedDate = date.toLocaleDateString() + ' ' + date.toLocaleTimeString();
        
        playerDiv.innerHTML = `
          <h4>🏆 ${player.name} - Registration #${player.player_number}</h4>
          <div class="email">${player.email}</div>
          <div class="content">
            ${player.username ? `<strong>Game Username:</strong> ${player.username}<br/>` : ''}
            <strong>Status:</strong> <span style="color: #4ade80;">✅ Registered & Ready</span>
          </div>
          <div class="timestamp">${formattedDate}</div>
        `;
        
        playersList.appendChild(playerDiv);
      });
    }

    // Render signups
    function renderSignups(signups) {
      const signupsList = document.getElementById('signupsList');
      
      if (signups.length === 0) {
        signupsList.innerHTML = '';
        return;
      }
      
      const sortedSignups = [...signups].sort((a, b) => 
        new Date(b.timestamp) - new Date(a.timestamp)
      );
      
      signupsList.innerHTML = '<h3 style="color: #a78bfa; margin-bottom: 20px;">Recent Sign-Ups 🎉</h3>';
      
      sortedSignups.forEach(signup => {
        const signupDiv = document.createElement('div');
        signupDiv.className = 'message-item';
        
        const date = new Date(signup.timestamp);
        const formattedDate = date.toLocaleDateString() + ' ' + date.toLocaleTimeString();
        
        signupDiv.innerHTML = `
          <h4>🎮 ${signup.username || signup.name}</h4>
          <div class="email">${signup.email}</div>
          <div class="content">
            <strong>Favorite Game:</strong> ${signup.favorite_game || 'Not specified'}<br/>
            <strong>Platform:</strong> ${signup.platform || 'Not specified'}
          </div>
          <div class="timestamp">${formattedDate}</div>
        `;
        
        signupsList.appendChild(signupDiv);
      });
    }

    // Render messages
    function renderMessages(messages) {
      const messagesList = document.getElementById('messagesList');
      
      if (messages.length === 0) {
        messagesList.innerHTML = '';
        return;
      }
      
      const sortedMessages = [...messages].sort((a, b) => 
        new Date(b.timestamp) - new Date(a.timestamp)
      );
      
      messagesList.innerHTML = '<h3 style="color: #a78bfa; margin-bottom: 20px;">Recent Messages</h3>';
      
      sortedMessages.forEach(msg => {
        const messageDiv = document.createElement('div');
        messageDiv.className = 'message-item';
        
        const date = new Date(msg.timestamp);
        const formattedDate = date.toLocaleDateString() + ' ' + date.toLocaleTimeString();
        
        messageDiv.innerHTML = `
          <h4>${msg.name}</h4>
          <div class="email">${msg.email}</div>
          <div class="content">${msg.message}</div>
          <div class="timestamp">${formattedDate}</div>
        `;
        
        messagesList.appendChild(messageDiv);
      });
    }

    // Handle game registration form submission
    document.getElementById('gameJoinForm').addEventListener('submit', async (e) => {
      e.preventDefault();
      
      const gameJoinBtn = document.getElementById('gameJoinBtn');
      const gameJoinMessage = document.getElementById('gameJoinMessage');
      const name = document.getElementById('game-name').value;
      const email = document.getElementById('game-email').value;
      const username = document.getElementById('game-username').value;
      
      // Check if game is full
      if (currentGamePlayers.length >= MAX_GAME_SPOTS) {
        gameJoinMessage.className = 'form-message error';
        gameJoinMessage.textContent = '🔒 Game is full! All 50 spots have been taken.';
        return;
      }
      
      // Check overall data limit
      if (allData.length >= 999) {
        gameJoinMessage.className = 'form-message error';
        gameJoinMessage.textContent = 'Maximum limit reached. Please try again later.';
        return;
      }
      
      // Check if email already registered
      const existingPlayer = currentGamePlayers.find(p => p.email.toLowerCase() === email.toLowerCase());
      if (existingPlayer) {
        gameJoinMessage.className = 'form-message error';
        gameJoinMessage.textContent = `This email is already registered as #${existingPlayer.player_number}`;
        return;
      }
      
      // Show loading state
      gameJoinBtn.disabled = true;
      gameJoinBtn.innerHTML = '<span class="spinner"></span> Registering...';
      gameJoinMessage.innerHTML = '';
      
      // Generate player number (pad with zeros)
      const playerNumber = String(currentGamePlayers.length + 1).padStart(3, '0');
      
      const newPlayer = {
        id: Date.now().toString(),
        name: name,
        email: email,
        username: username,
        player_number: playerNumber,
        type: 'game_registration',
        timestamp: new Date().toISOString()
      };
      
      const result = await window.dataSdk.create(newPlayer);
      
      if (result.isOk) {
        gameJoinMessage.className = 'form-message success';
        gameJoinMessage.innerHTML = `
          🎉 <strong>Registration Successful!</strong><br/>
          Your registration number is: <strong style="font-size: 1.5rem; color: #4ade80;">#${playerNumber}</strong><br/>
          <em style="font-size: 0.95rem;">Save this number! You'll need it with your email to access the game.</em>
        `;
        document.getElementById('gameJoinForm').reset();
      } else {
        gameJoinMessage.className = 'form-message error';
        gameJoinMessage.textContent = '❌ Registration failed. Please try again.';
      }
      
      gameJoinBtn.disabled = false;
      gameJoinBtn.innerHTML = 'Register for Game 🚀';
    });

    // Handle game access form submission
    document.getElementById('gameAccessForm').addEventListener('submit', async (e) => {
      e.preventDefault();
      
      const gameAccessBtn = document.getElementById('gameAccessBtn');
      const gameAccessMessage = document.getElementById('gameAccessMessage');
      const numberInput = document.getElementById('access-number').value.replace(/[^0-9]/g, '');
      const emailInput = document.getElementById('access-email').value;
      
      // Show loading state
      gameAccessBtn.disabled = true;
      gameAccessBtn.innerHTML = '<span class="spinner"></span> Verifying...';
      gameAccessMessage.innerHTML = '';
      
      // Find matching player
      const player = currentGamePlayers.find(p => 
        p.player_number === numberInput.padStart(3, '0') && 
        p.email.toLowerCase() === emailInput.toLowerCase()
      );
      
      if (player) {
        gameAccessMessage.className = 'form-message success';
        gameAccessMessage.innerHTML = `
          ✅ <strong>Verification Successful!</strong><br/>
          Welcome back, ${player.name}!<br/>
          <button onclick="window.open('https://top-arena-play.base44.app', '_blank', 'noopener,noreferrer')" style="margin-top: 15px; padding: 12px 30px; font-size: 1.1rem; font-weight: bold; background: linear-gradient(135deg, #4ade80, #22c55e); color: white; border: none; border-radius: 8px; cursor: pointer; transition: all 0.3s ease; box-shadow: 0 4px 15px rgba(34, 197, 94, 0.4);">
            🎮 Launch Game Now
          </button>
        `;
      } else {
        gameAccessMessage.className = 'form-message error';
        gameAccessMessage.textContent = '❌ Invalid registration number or email. Please check your details.';
      }
      
      gameAccessBtn.disabled = false;
      gameAccessBtn.innerHTML = 'Access Game 🎯';
    });

    // Handle signup form submission
    document.getElementById('signupForm').addEventListener('submit', async (e) => {
      e.preventDefault();
      
      const signupBtn = document.getElementById('signupBtn');
      const signupMessage = document.getElementById('signupMessage');
      const username = document.getElementById('signup-username').value;
      const email = document.getElementById('signup-email').value;
      const favoriteGame = document.getElementById('signup-favorite-game').value;
      const platform = document.getElementById('signup-platform').value;
      
      // Check limit
      if (allData.length >= 999) {
        signupMessage.className = 'form-message error';
        signupMessage.textContent = 'Maximum limit of 999 entries reached. Please try again later.';
        return;
      }
      
      // Show loading state
      signupBtn.disabled = true;
      signupBtn.innerHTML = '<span class="spinner"></span> Signing you up...';
      signupMessage.innerHTML = '';
      
      const newSignup = {
        id: Date.now().toString(),
        username: username,
        name: username,
        email: email,
        favorite_game: favoriteGame,
        platform: platform,
        type: 'signup',
        timestamp: new Date().toISOString()
      };
      
      const result = await window.dataSdk.create(newSignup);
      
      if (result.isOk) {
        signupMessage.className = 'form-message success';
        signupMessage.textContent = '🎉 Welcome to Topgamerx Studios! Check your email for exclusive updates!';
        document.getElementById('signupForm').reset();
      } else {
        signupMessage.className = 'form-message error';
        signupMessage.textContent = '�� Sign-up failed. Please try again.';
      }
      
      signupBtn.disabled = false;
      signupBtn.innerHTML = 'Sign Up Now! 🚀';
    });

    // Handle contact form submission
    document.getElementById('contactForm').addEventListener('submit', async (e) => {
      e.preventDefault();
      
      const submitBtn = document.getElementById('submitBtn');
      const formMessage = document.getElementById('formMessage');
      const name = document.getElementById('name').value;
      const email = document.getElementById('email').value;
      const message = document.getElementById('message').value;
      
      // Check limit
      if (allData.length >= 999) {
        formMessage.className = 'form-message error';
        formMessage.textContent = 'Maximum limit of 999 entries reached. Please contact us through another channel.';
        return;
      }
      
      // Show loading state
      submitBtn.disabled = true;
      submitBtn.innerHTML = '<span class="spinner"></span> Sending...';
      formMessage.innerHTML = '';
      
      const newMessage = {
        id: Date.now().toString(),
        name: name,
        email: email,
        message: message,
        type: 'message',
        timestamp: new Date().toISOString()
      };
      
      const result = await window.dataSdk.create(newMessage);
      
      if (result.isOk) {
        formMessage.className = 'form-message success';
        formMessage.textContent = '✓ Message sent successfully! We\'ll get back to you soon.';
        document.getElementById('contactForm').reset();
      } else {
        formMessage.className = 'form-message error';
        formMessage.textContent = '✗ Failed to send message. Please try again.';
      }
      
      submitBtn.disabled = false;
      submitBtn.textContent = 'Send Message';
    });

    // Scroll animations
    const observerOptions = {
      threshold: 0.1,
      rootMargin: '0px 0px -50px 0px'
    };

    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
        }
      });
    }, observerOptions);

    document.querySelectorAll('section').forEach(section => {
      observer.observe(section);
    });

    // Element SDK Implementation
    async function onConfigChange(config) {
      const studioName = config.studio_name || defaultConfig.studio_name;
      const tagline = config.tagline || defaultConfig.tagline;
      const welcomeTitle = config.welcome_title || defaultConfig.welcome_title;
      const welcomeText = config.welcome_text || defaultConfig.welcome_text;
      const footerText = config.footer_text || defaultConfig.footer_text;
      
      document.getElementById('studio-name').textContent = studioName;
      document.getElementById('tagline').textContent = tagline;
      document.getElementById('welcome-title').textContent = welcomeTitle;
      document.getElementById('welcome-text').textContent = welcomeText;
      document.getElementById('footer-text').textContent = footerText;
      
      // Apply colors
      const bgColor = config.background_color || defaultConfig.background_color;
      const headerColor = config.header_color || defaultConfig.header_color;
      const cardColor = config.card_color || defaultConfig.card_color;
      const textColor = config.text_color || defaultConfig.text_color;
      const accentColor = config.accent_color || defaultConfig.accent_color;
      
      document.body.style.background = bgColor;
      document.querySelector('.main-wrapper').style.background = `linear-gradient(135deg, ${bgColor} 0%, #1a1a2e 50%, ${bgColor} 100%)`;
      document.querySelector('header').style.background = `linear-gradient(135deg, #6366f1 0%, ${headerColor} 50%, #d946ef 100%)`;
      document.querySelectorAll('.card').forEach(card => {
        card.style.background = `linear-gradient(135deg, ${cardColor} 0%, #111827 100%)`;
      });
      document.body.style.color = textColor;
      document.querySelectorAll('.card h2').forEach(h2 => {
        h2.style.color = accentColor;
      });
      document.querySelectorAll('nav a:hover').forEach(link => {
        link.style.color = accentColor;
      });
      
      // Apply font
      const customFont = config.font_family || defaultConfig.font_family;
      const baseFontStack = '-apple-system, BlinkMacSystemFont, sans-serif';
      document.body.style.fontFamily = `${customFont}, ${baseFontStack}`;
      
      // Apply font size
      const baseSize = config.font_size || defaultConfig.font_size;
      document.querySelector('header h1').style.fontSize = `${baseSize * 2.2}px`;
      document.querySelector('header p').style.fontSize = `${baseSize * 1.1}px`;
      document.querySelectorAll('nav a').forEach(a => {
        a.style.fontSize = `${baseSize * 1.1}px`;
      });
      document.querySelectorAll('.card h2').forEach(h2 => {
        h2.style.fontSize = `${baseSize * 1.5}px`;
      });
      document.querySelectorAll('.card p, .card ul li').forEach(el => {
        el.style.fontSize = `${baseSize * 1.05}px`;
      });
      document.querySelectorAll('.game-item h3').forEach(h3 => {
        h3.style.fontSize = `${baseSize * 1.2}px`;
      });
      document.querySelectorAll('.game-item p').forEach(p => {
        p.style.fontSize = `${baseSize * 0.95}px`;
      });
      document.querySelectorAll('.form-group label').forEach(label => {
        label.style.fontSize = `${baseSize}px`;
      });
      document.querySelectorAll('input, textarea, .submit-btn').forEach(el => {
        el.style.fontSize = `${baseSize}px`;
      });
      document.querySelector('footer').style.fontSize = `${baseSize}px`;
    }

    function mapToCapabilities(config) {
      return {
        recolorables: [
          {
            get: () => config.background_color || defaultConfig.background_color,
            set: (value) => {
              if (window.elementSdk) {
                window.elementSdk.config.background_color = value;
                window.elementSdk.setConfig({ background_color: value });
              }
            }
          },
          {
            get: () => config.card_color || defaultConfig.card_color,
            set: (value) => {
              if (window.elementSdk) {
                window.elementSdk.config.card_color = value;
                window.elementSdk.setConfig({ card_color: value });
              }
            }
          },
          {
            get: () => config.text_color || defaultConfig.text_color,
            set: (value) => {
              if (window.elementSdk) {
                window.elementSdk.config.text_color = value;
                window.elementSdk.setConfig({ text_color: value });
              }
            }
          },
          {
            get: () => config.header_color || defaultConfig.header_color,
            set: (value) => {
              if (window.elementSdk) {
                window.elementSdk.config.header_color = value;
                window.elementSdk.setConfig({ header_color: value });
              }
            }
          },
          {
            get: () => config.accent_color || defaultConfig.accent_color,
            set: (value) => {
              if (window.elementSdk) {
                window.elementSdk.config.accent_color = value;
                window.elementSdk.setConfig({ accent_color: value });
              }
            }
          }
        ],
        borderables: [],
        fontEditable: {
          get: () => config.font_family || defaultConfig.font_family,
          set: (value) => {
            if (window.elementSdk) {
              window.elementSdk.config.font_family = value;
              window.elementSdk.setConfig({ font_family: value });
            }
          }
        },
        fontSizeable: {
          get: () => config.font_size || defaultConfig.font_size,
          set: (value) => {
            if (window.elementSdk) {
              window.elementSdk.config.font_size = value;
              window.elementSdk.setConfig({ font_size: value });
            }
          }
        }
      };
    }

    function mapToEditPanelValues(config) {
      return new Map([
        ["studio_name", config.studio_name || defaultConfig.studio_name],
        ["tagline", config.tagline || defaultConfig.tagline],
        ["welcome_title", config.welcome_title || defaultConfig.welcome_title],
        ["welcome_text", config.welcome_text || defaultConfig.welcome_text],
        ["footer_text", config.footer_text || defaultConfig.footer_text]
      ]);
    }

    // Initialize Element SDK
    if (window.elementSdk) {
      window.elementSdk.init({
        defaultConfig,
        onConfigChange,
        mapToCapabilities,
        mapToEditPanelValues
      });
    }
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9cd775b1607bf4bb',t:'MTc3MTAxODU3MC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>

<!-- 📞 TopGamerX Fun Call System (Safe & Harmless) -->
<div class="card" style="text-align:center; max-width:500px; margin:40px auto;">
  <h2>📞 Call TopGamerX Studios</h2>
  <p>Support line — please stay on the call</p>

  <button id="callBtn" style="
    background: linear-gradient(135deg,#22c55e,#16a34a);
    border:none;
    padding:15px 35px;
    border-radius:10px;
    font-size:1.2rem;
    color:white;
    cursor:pointer;
    box-shadow:0 4px 20px rgba(0,0,0,0.4);
  ">📞 Call Now</button>

  <button id="hangupBtn" style="
    display:none;
    margin-top:10px;
    background:#ef4444;
    border:none;
    padding:10px 25px;
    border-radius:8px;
    color:white;
    cursor:pointer;
  ">❌ Hang Up</button>

  <!-- Sounds -->
  <audio id="ringtone" loop>
    <source src="https://www.myinstants.com/media/sounds/italian-brainrot-ringtone.mp3" type="audio/mpeg">
  </audio>

  <audio id="transitionSfx">
    <source src="https://www.myinstants.com/instant/facetime-join-call-39775/embed/" type="audio/mpeg">
  </audio>

  <audio id="edmSfx" loop>
    <source src="https://www.myinstants.com/media/sounds/facetime-join-call-39775.mp3" type="audio/mpeg">
  </audio>

  <audio id="clickSfx">
    <source src="https://www.myinstants.com/media/sounds/phone-click.mp3" type="audio/mpeg">
  </audio>

  <audio id="dialtoneSfx" loop>
    <source src="https://www.myinstants.com/media/sounds/phone-dial-tone.mp3" type="audio/mpeg">
  </audio>
</div>

<!-- Call Popup -->
<div id="callPopup" style="
  display:none;
  position:fixed;
  top:50%; left:50%;
  transform:translate(-50%,-50%);
  background:#111827;
  border:2px solid #8b5cf6;
  border-radius:14px;
  padding:25px;
  width:340px;
  z-index:9999;
  box-shadow:0 0 40px rgba(139,92,246,0.5);
  text-align:center;
">
  <h3>📡 TopGamerX Studios Support</h3>
  <p id="callText">Connecting...</p>
</div>

<script>
(function(){
  const callBtn = document.getElementById("callBtn");
  const hangupBtn = document.getElementById("hangupBtn");
  const ringtone = document.getElementById("ringtone");
  const transitionSfx = document.getElementById("transitionSfx");
  const edmSfx = document.getElementById("edmSfx");
  const clickSfx = document.getElementById("clickSfx");
  const dialtoneSfx = document.getElementById("dialtoneSfx");
  const callPopup = document.getElementById("callPopup");
  const callText = document.getElementById("callText");

  if(!callBtn) return;

  let timer;

  const scriptLines = [
    "Support: Thank you for calling TopGamerX Studios Support...",
    "Support: Please stay on the line while we transfer you...",
    "Nova: YOOO! You're live with Max and Nova!",
    "Max: Checking caller stats...",
    "Max: THE STATS ARE GARBAGE! ZERO AURA!",
    "Nova: ITALIAN BRAINROT MODE ACTIVATED!",
    "TRALALERO TRALALA! BOMBARDIRO CROCODILO!",
    "CHIMPANZINI BANANINI! TUNG TUNG TUNG SAHUR!",
    "Nova: SELECTION DENIED! YOU'RE COOKED!",
    "Support: Yeah... sorry about that. Better luck next time. Goodbye."
  ];

  function runCall(){
    let i = 0;
    callText.textContent = scriptLines[0];

    timer = setInterval(()=>{
      i++;
      if(i === 2){
        ringtone.pause();
        transitionSfx.currentTime = 0;
        transitionSfx.play().catch(()=>{});
        edmSfx.currentTime = 0;
        edmSfx.play().catch(()=>{});
      }
      if(i === 8){
        edmSfx.pause();
        clickSfx.play().catch(()=>{});
      }
      if(i === scriptLines.length-1){
        dialtoneSfx.currentTime = 0;
        dialtoneSfx.play().catch(()=>{});
      }

      if(i < scriptLines.length){
        callText.textContent = scriptLines[i];
      } else {
        clearInterval(timer);
      }
    }, 2600);
  }

  callBtn.onclick = ()=>{
    callPopup.style.display = "block";
    hangupBtn.style.display = "inline-block";
    ringtone.currentTime = 0;
    ringtone.play().catch(()=>{});
    runCall();
  };

  hangupBtn.onclick = ()=>{
    clearInterval(timer);
    ringtone.pause();
    edmSfx.pause();
    dialtoneSfx.pause();
    callPopup.style.display = "none";
    hangupBtn.style.display = "none";
  };
})();
</script>
