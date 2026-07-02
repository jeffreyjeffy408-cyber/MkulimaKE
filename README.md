<!-- MkulimaKe -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Zilla+Slab:wght@400;500;600;700&family=Inter:wght@400;500;600;700&family=IBM+Plex+Mono:wght@400;500;600&display=swap" rel="stylesheet">

<style>
  :root{
    --paper:#EFEAD9;
    --paper-dark:#E4DCC3;
    --card:#FBF9F1;
    --ink:#242F1F;
    --ink-soft:#5B6350;
    --ink-faint:#8C9280;
    --line:#CBC1A2;
    --line-soft:#DCD4B9;
    --rust:#4B7A3A;
    --rust-dark:#33541F;
    --rust-tint:#E1EAD0;
    --pine:#3E5C3A;
    --pine-dark:#2A4027;
    --pine-tint:#DCE4D4;
    --danger:#A13A2C;
    --danger-tint:#F1DAD3;

    --font-display:'Zilla Slab', Georgia, serif;
    --font-body:'Inter', -apple-system, sans-serif;
    --font-mono:'IBM Plex Mono', monospace;
  }

  *{box-sizing:border-box;}
  html,body{margin:0;padding:0;}
  #fh-root{
    background:var(--paper);
    color:var(--ink);
    font-family:var(--font-body);
    min-height:100vh;
    background-image:
      radial-gradient(circle at 1px 1px, var(--line-soft) 1px, transparent 1px);
    background-size:22px 22px;
    padding-bottom:60px;
  }
  #fh-root *{box-sizing:border-box;}
  #fh-root button{font-family:var(--font-body);cursor:pointer;}
  #fh-root input, #fh-root select, #fh-root textarea{font-family:var(--font-body);}

  /* ---------- Top bar ---------- */
  .fh-topbar{
    position:sticky; top:64px; z-index:40;
    background:var(--paper);
    border-bottom:2px solid var(--ink);
    padding:16px 24px;
    display:flex; align-items:center; justify-content:space-between; gap:16px;
    flex-wrap:wrap;
  }
  .fh-brand{display:flex; align-items:center; gap:12px;}
  .fh-brand-mark{width:38px;height:38px;flex-shrink:0;}
  .fh-brand-text h1{
    font-family:var(--font-display); font-weight:700; font-size:22px;
    margin:0; letter-spacing:0.2px; color:var(--ink);
  }
  .fh-brand-text p{
    margin:0; font-size:11px; letter-spacing:1.6px; text-transform:uppercase;
    color:var(--ink-faint); font-weight:600;
  }
  .fh-nav{display:flex; gap:4px; background:var(--paper-dark); padding:4px; border-radius:8px; border:1px solid var(--line);}
  .fh-nav-btn{
    border:none; background:transparent; padding:8px 14px; border-radius:6px;
    font-size:13px; font-weight:600; color:var(--ink-soft); letter-spacing:0.2px;
    transition:background .15s, color .15s;
  }
  .fh-nav-btn.active{background:var(--ink); color:var(--paper);}
  .fh-nav-btn:not(.active):hover{background:var(--card);}
  .fh-add-btn{
    background:var(--rust); color:#fff; border:none; padding:10px 18px;
    border-radius:7px; font-weight:700; font-size:13px; display:flex; align-items:center; gap:6px;
    box-shadow:0 2px 0 var(--rust-dark);
    transition:transform .1s;
  }
  .fh-add-btn:hover{transform:translateY(-1px);}
  .fh-add-btn:active{transform:translateY(1px); box-shadow:0 1px 0 var(--rust-dark);}

  .fh-main{max-width:1120px; margin:0 auto; padding:28px 24px;}

  /* ---------- Dashboard ---------- */
  .fh-stats{display:grid; grid-template-columns:repeat(4,1fr); gap:14px; margin-bottom:28px;}
  @media(max-width:800px){.fh-stats{grid-template-columns:repeat(2,1fr);}}
  .fh-stat{
    background:var(--card); border:1px solid var(--line); border-radius:10px;
    padding:16px 18px; position:relative; overflow:hidden;
  }
  .fh-stat::before{
    content:''; position:absolute; left:0; top:0; bottom:0; width:4px; background:var(--stat-color, var(--pine));
  }
  .fh-stat .fh-stat-num{font-family:var(--font-display); font-size:32px; font-weight:700; line-height:1;}
  .fh-stat .fh-stat-label{font-size:12px; color:var(--ink-soft); margin-top:6px; font-weight:600; letter-spacing:0.3px;}

  .fh-section-title{
    font-family:var(--font-display); font-size:15px; font-weight:700; text-transform:uppercase;
    letter-spacing:1.2px; color:var(--ink-soft); margin:32px 0 14px; display:flex; align-items:center; gap:10px;
  }
  .fh-section-title::after{content:''; flex:1; height:1px; background:var(--line);}

  .fh-empty{
    border:2px dashed var(--line); border-radius:12px; padding:40px 24px; text-align:center; color:var(--ink-soft);
    background:var(--paper-dark);
  }
  .fh-empty h3{font-family:var(--font-display); color:var(--ink); margin:10px 0 4px; font-size:18px;}
  .fh-empty p{margin:0 0 16px; font-size:13px;}

  .fh-activity{display:flex; flex-direction:column; gap:8px;}
  .fh-activity-row{
    display:flex; align-items:center; gap:12px; background:var(--card); border:1px solid var(--line-soft);
    border-radius:8px; padding:10px 14px; font-size:13px;
  }
  .fh-activity-dot{width:8px; height:8px; border-radius:50%; flex-shrink:0;}
  .fh-activity-meta{color:var(--ink-faint); margin-left:auto; font-family:var(--font-mono); font-size:11px;}

  /* ---------- Filter bar ---------- */
  .fh-filterbar{display:flex; gap:10px; flex-wrap:wrap; align-items:center; margin-bottom:20px;}
  .fh-search{
    flex:1; min-width:180px; background:var(--card); border:1px solid var(--line); border-radius:8px;
    padding:9px 12px; font-size:13px; color:var(--ink);
  }
  .fh-search:focus{outline:2px solid var(--pine); outline-offset:1px;}
  .fh-chip{
    border:1px solid var(--line); background:var(--card); padding:8px 13px; border-radius:20px;
    font-size:12px; font-weight:600; color:var(--ink-soft);
  }
  .fh-chip.active{background:var(--ink); color:var(--paper); border-color:var(--ink);}
  .fh-select{
    background:var(--card); border:1px solid var(--line); border-radius:8px; padding:9px 10px; font-size:13px; color:var(--ink);
  }

  /* ---------- Tag cards grid ---------- */
  .fh-grid{display:grid; grid-template-columns:repeat(auto-fill, minmax(230px,1fr)); gap:16px;}

  .fh-tagcard{
    background:var(--card); border:1px solid var(--line); border-radius:4px 14px 14px 4px;
    position:relative; padding:16px 16px 14px 22px; cursor:pointer;
    transition:transform .12s, box-shadow .12s;
    border-left:6px solid var(--cat-color, var(--pine));
  }
  .fh-tagcard:hover{transform:translateY(-2px); box-shadow:0 6px 14px -6px rgba(36,47,31,0.35);}
  .fh-tagcard-hole{
    position:absolute; left:-6px; top:16px; width:11px; height:11px; border-radius:50%;
    background:var(--paper); border:2px solid var(--cat-color, var(--pine));
  }
  .fh-tagcard-top{display:flex; justify-content:space-between; align-items:flex-start; gap:8px;}
  .fh-tagcard-id{font-family:var(--font-mono); font-size:11px; color:var(--ink-faint); font-weight:600; letter-spacing:0.5px;}
  .fh-tagcard-name{font-family:var(--font-display); font-size:18px; font-weight:700; margin:2px 0 4px;}
  .fh-tagcard-species{font-size:12px; color:var(--ink-soft); margin-bottom:10px;}
  .fh-badge{
    font-size:10px; font-weight:700; padding:3px 8px; border-radius:20px; text-transform:uppercase; letter-spacing:0.4px;
    white-space:nowrap;
  }
  .fh-badge.status-active{background:var(--pine-tint); color:var(--pine-dark);}
  .fh-badge.status-sold{background:#DDD3E8; color:#5A3A78;}
  .fh-badge.status-deceased{background:var(--danger-tint); color:var(--danger);}
  .fh-tagcard-meta{display:flex; gap:14px; font-size:11px; color:var(--ink-soft); border-top:1px dashed var(--line); padding-top:10px; margin-top:2px;}
  .fh-tagcard-meta div{display:flex; flex-direction:column; gap:2px;}
  .fh-tagcard-meta span{color:var(--ink-faint); font-size:9px; text-transform:uppercase; letter-spacing:0.5px; font-weight:700;}

  /* ---------- Modal ---------- */
  .fh-overlay{
    position:fixed; inset:0; background:rgba(36,47,31,0.45); z-index:100;
    display:flex; align-items:flex-start; justify-content:center; padding:40px 16px; overflow-y:auto;
  }
  .fh-modal{
    background:var(--paper); border-radius:14px; max-width:560px; width:100%;
    border:1px solid var(--line); box-shadow:0 20px 50px -10px rgba(0,0,0,0.35);
    animation:fh-pop .16s ease;
  }
  @keyframes fh-pop{from{opacity:0; transform:translateY(8px) scale(.98);} to{opacity:1; transform:none;}}
  .fh-modal-header{
    display:flex; justify-content:space-between; align-items:center; padding:18px 22px;
    border-bottom:2px solid var(--ink); background:var(--paper-dark); border-radius:14px 14px 0 0;
  }
  .fh-modal-header h2{font-family:var(--font-display); font-size:19px; margin:0;}
  .fh-modal-close{background:none; border:none; font-size:20px; color:var(--ink-soft); line-height:1; padding:4px;}
  .fh-modal-close:hover{color:var(--ink);}
  .fh-modal-body{padding:20px 22px;}

  .fh-field{margin-bottom:14px;}
  .fh-field label{display:block; font-size:11px; font-weight:700; text-transform:uppercase; letter-spacing:0.5px; color:var(--ink-soft); margin-bottom:5px;}
  .fh-field input, .fh-field select, .fh-field textarea{
    width:100%; border:1px solid var(--line); background:var(--card); border-radius:7px; padding:9px 11px;
    font-size:13px; color:var(--ink);
  }
  .fh-field input:focus, .fh-field select:focus, .fh-field textarea:focus{outline:2px solid var(--pine); outline-offset:1px;}
  .fh-row2{display:grid; grid-template-columns:1fr 1fr; gap:12px;}
  .fh-row3{display:grid; grid-template-columns:1fr 1fr 1fr; gap:12px;}
  @media(max-width:520px){.fh-row2,.fh-row3{grid-template-columns:1fr;}}

  .fh-cattype-toggle{display:flex; gap:8px; margin-bottom:16px;}
  .fh-cattype-opt{
    flex:1; border:1.5px solid var(--line); background:var(--card); border-radius:8px; padding:10px; text-align:center;
    font-size:13px; font-weight:700; color:var(--ink-soft);
  }
  .fh-cattype-opt.sel-livestock{border-color:var(--pine); background:var(--pine-tint); color:var(--pine-dark);}
  .fh-cattype-opt.sel-bird{border-color:var(--rust); background:var(--rust-tint); color:var(--rust-dark);}

  .fh-modal-footer{display:flex; justify-content:flex-end; gap:10px; padding:16px 22px 22px;}
  .fh-btn{border:none; border-radius:7px; padding:10px 18px; font-size:13px; font-weight:700;}
  .fh-btn-primary{background:var(--ink); color:var(--paper);}
  .fh-btn-primary:hover{background:var(--pine-dark);}
  .fh-btn-ghost{background:transparent; color:var(--ink-soft); border:1px solid var(--line);}
  .fh-btn-ghost:hover{background:var(--card);}
  .fh-btn-danger{background:var(--danger); color:#fff;}
  .fh-btn-danger:hover{background:#832E22;}

  /* ---------- Detail view ---------- */
  .fh-detail-head{display:flex; gap:16px; align-items:flex-start;}
  .fh-detail-tag{
    width:64px; height:64px; border-radius:12px; flex-shrink:0; display:flex; align-items:center; justify-content:center;
    font-family:var(--font-display); font-size:26px; font-weight:700; color:#fff;
  }
  .fh-detail-id{font-family:var(--font-mono); font-size:12px; color:var(--ink-faint); font-weight:600;}
  .fh-detail-name{font-family:var(--font-display); font-size:24px; font-weight:700; margin:2px 0 6px;}
  .fh-detail-facts{display:grid; grid-template-columns:repeat(3,1fr); gap:10px; margin:18px 0; }
  @media(max-width:520px){.fh-detail-facts{grid-template-columns:repeat(2,1fr);}}
  .fh-fact{background:var(--card); border:1px solid var(--line-soft); border-radius:8px; padding:9px 11px;}
  .fh-fact span{display:block; font-size:9px; text-transform:uppercase; letter-spacing:0.5px; color:var(--ink-faint); font-weight:700; margin-bottom:3px;}
  .fh-fact b{font-size:13px; font-weight:600;}
  .fh-notes-box{background:var(--card); border:1px solid var(--line-soft); border-radius:8px; padding:12px 14px; font-size:13px; color:var(--ink-soft); line-height:1.5;}

  .fh-timeline{margin-top:8px;}
  .fh-timeline-item{display:flex; gap:12px; position:relative; padding-bottom:16px;}
  .fh-timeline-item:not(:last-child)::before{
    content:''; position:absolute; left:15px; top:26px; bottom:0; width:1px; background:var(--line);
  }
  .fh-timeline-dot{
    width:31px; height:31px; border-radius:50%; background:var(--pine-tint); color:var(--pine-dark);
    display:flex; align-items:center; justify-content:center; flex-shrink:0; font-size:14px; z-index:1;
  }
  .fh-timeline-dot.type-treatment{background:var(--danger-tint); color:var(--danger);}
  .fh-timeline-dot.type-checkup{background:#DDE6F0; color:#2E5586;}
  .fh-timeline-dot.type-weight{background:#EEE3C8; color:#8A6A1B;}
  .fh-timeline-content{background:var(--card); border:1px solid var(--line-soft); border-radius:8px; padding:9px 12px; flex:1;}
  .fh-timeline-top{display:flex; justify-content:space-between; gap:8px; align-items:baseline;}
  .fh-timeline-type{font-size:12px; font-weight:700;}
  .fh-timeline-date{font-family:var(--font-mono); font-size:10px; color:var(--ink-faint);}
  .fh-timeline-note{font-size:12px; color:var(--ink-soft); margin-top:3px;}
  .fh-timeline-del{background:none; border:none; color:var(--ink-faint); font-size:12px; padding:0 2px;}
  .fh-timeline-del:hover{color:var(--danger);}

  .fh-addlog-form{display:flex; gap:8px; margin-top:12px; flex-wrap:wrap;}
  .fh-addlog-form select, .fh-addlog-form input{border:1px solid var(--line); background:var(--card); border-radius:7px; padding:8px 10px; font-size:12px;}
  .fh-addlog-form input[type=text]{flex:1; min-width:140px;}

  .fh-loading{display:flex; align-items:center; justify-content:center; gap:8px; padding:60px 0; color:var(--ink-soft); font-size:13px;}
  .fh-spinner{width:16px; height:16px; border:2px solid var(--line); border-top-color:var(--pine); border-radius:50%; animation:fh-spin .7s linear infinite;}
  @keyframes fh-spin{to{transform:rotate(360deg);}}

  .fh-toast{
    position:fixed; bottom:20px; left:50%; transform:translateX(-50%); background:var(--ink); color:var(--paper);
    padding:10px 20px; border-radius:8px; font-size:13px; font-weight:600; z-index:200; opacity:0; pointer-events:none;
    transition:opacity .2s, transform .2s;
  }
  .fh-toast.show{opacity:1; transform:translateX(-50%) translateY(-4px);}

  /* =====================================================
     MARKETING SITE (mk- prefix, sits above the app)
     ===================================================== */
  #mk-root{
    background:var(--paper); color:var(--ink); font-family:var(--font-body);
  }
  #mk-root *{box-sizing:border-box;}
  #mk-root a{color:inherit; text-decoration:none;}
  #mk-root button{font-family:var(--font-body); cursor:pointer;}
  #mk-root section{padding:88px 24px;}
  @media(max-width:760px){#mk-root section{padding:56px 20px;}}
  .mk-wrap{max-width:1120px; margin:0 auto;}
  .mk-eyebrow{
    font-family:var(--font-mono); font-size:11px; letter-spacing:2px; text-transform:uppercase;
    color:var(--rust-dark); font-weight:600; margin:0 0 10px;
  }
  .mk-h2{font-family:var(--font-display); font-size:clamp(26px,3.4vw,38px); font-weight:700; margin:0 0 14px; line-height:1.12;}
  .mk-lede{font-size:15px; color:var(--ink-soft); max-width:560px; line-height:1.6; margin:0;}

  /* ---- nav ---- */
  .mk-nav{
    position:sticky; top:0; z-index:60; height:64px; background:var(--paper);
    border-bottom:2px solid var(--ink); display:flex; align-items:center;
    padding:0 24px;
  }
  .mk-nav-inner{max-width:1120px; margin:0 auto; width:100%; display:flex; align-items:center; justify-content:space-between; gap:16px;}
  .mk-nav-brand{display:flex; align-items:center; gap:10px;}
  .mk-nav-brand svg{width:32px; height:32px; flex-shrink:0;}
  .mk-nav-brand span{font-family:var(--font-display); font-weight:700; font-size:19px;}
  .mk-nav-links{display:flex; gap:26px; align-items:center;}
  .mk-nav-links a{font-size:13px; font-weight:600; color:var(--ink-soft);}
  .mk-nav-links a:hover{color:var(--ink);}
  @media(max-width:760px){.mk-nav-links a:not(.mk-nav-cta){display:none;}}
  .mk-nav-cta{
    background:var(--ink); color:var(--paper) !important; padding:9px 16px; border-radius:7px;
    font-weight:700 !important; font-size:12px !important;
  }
  .mk-nav-cta:hover{background:var(--pine-dark);}

  /* ---- hero ---- */
  .mk-hero{padding-top:64px; padding-bottom:40px; position:relative; overflow:hidden;}
  .mk-hero-grid{display:grid; grid-template-columns:1.1fr 0.9fr; gap:40px; align-items:center;}
  @media(max-width:860px){.mk-hero-grid{grid-template-columns:1fr;}}
  .mk-hero h1{
    font-family:var(--font-display); font-weight:700; font-size:clamp(34px,5vw,54px);
    line-height:1.06; margin:0 0 18px; letter-spacing:-0.5px;
  }
  .mk-hero h1 em{font-style:normal; color:var(--pine); position:relative;}
  .mk-hero p.mk-sub{font-size:16px; color:var(--ink-soft); max-width:480px; line-height:1.6; margin:0 0 26px;}
  .mk-hero-ctas{display:flex; gap:12px; flex-wrap:wrap; margin-bottom:28px;}
  .mk-btn{border:none; border-radius:8px; padding:13px 22px; font-size:14px; font-weight:700; display:inline-flex; align-items:center; gap:8px;}
  .mk-btn-primary{background:var(--rust); color:#fff; box-shadow:0 3px 0 var(--rust-dark);}
  .mk-btn-primary:hover{transform:translateY(-1px);}
  .mk-btn-ghost{background:transparent; color:var(--ink); border:1.5px solid var(--ink);}
  .mk-btn-ghost:hover{background:var(--card);}
  .mk-hero-tags{display:flex; gap:10px; flex-wrap:wrap;}
  .mk-hero-tag{
    font-family:var(--font-mono); font-size:11px; background:var(--card); border:1px solid var(--line);
    padding:6px 11px; border-radius:20px; color:var(--ink-soft);
  }
  .mk-hero-visual{position:relative; height:360px;}
  .mk-hv-card{
    position:absolute; width:190px; background:var(--card); border:1px solid var(--line); border-radius:4px 12px 12px 4px;
    padding:14px 14px 12px 20px; box-shadow:0 14px 30px -12px rgba(36,47,31,0.35);
  }
  .mk-hv-card::before{content:''; position:absolute; left:-6px; top:14px; width:10px; height:10px; border-radius:50%; background:var(--paper); border:2px solid var(--tag,var(--pine));}
  .mk-hv-card{border-left:5px solid var(--tag,var(--pine));}
  .mk-hv-1{top:0; left:6%; transform:rotate(-6deg); --tag:var(--pine);}
  .mk-hv-2{top:120px; left:34%; transform:rotate(4deg); --tag:var(--rust); z-index:2;}
  .mk-hv-3{top:230px; left:4%; transform:rotate(-3deg); --tag:var(--pine);}
  .mk-hv-id{font-family:var(--font-mono); font-size:10px; color:var(--ink-faint); font-weight:600;}
  .mk-hv-name{font-family:var(--font-display); font-weight:700; font-size:15px; margin:2px 0 6px;}
  .mk-hv-meta{font-size:10px; color:var(--ink-soft); display:flex; gap:8px;}
  @media(max-width:860px){.mk-hero-visual{display:none;}}

  /* ---- logo strip ---- */
  .mk-strip{border-top:1px solid var(--line); border-bottom:1px solid var(--line); background:var(--paper-dark); padding:20px 24px;}
  .mk-strip-inner{max-width:1120px; margin:0 auto; display:flex; gap:34px; flex-wrap:wrap; align-items:center; justify-content:space-between;}
  .mk-strip-item{font-size:12px; font-weight:700; color:var(--ink-soft); display:flex; align-items:center; gap:8px; letter-spacing:0.2px;}
  .mk-strip-item b{color:var(--pine-dark); font-family:var(--font-display); font-size:18px;}

  /* ---- features ---- */
  .mk-feat-head{display:flex; justify-content:space-between; align-items:flex-end; gap:24px; margin-bottom:38px; flex-wrap:wrap;}
  .mk-feat-grid{display:grid; grid-template-columns:repeat(3,1fr); gap:16px;}
  @media(max-width:860px){.mk-feat-grid{grid-template-columns:repeat(2,1fr);}}
  @media(max-width:560px){.mk-feat-grid{grid-template-columns:1fr;}}
  .mk-feat-card{
    background:var(--card); border:1px solid var(--line); border-radius:12px; padding:22px 20px;
    transition:transform .12s, box-shadow .12s;
  }
  .mk-feat-card:hover{transform:translateY(-3px); box-shadow:0 10px 24px -12px rgba(36,47,31,0.3);}
  .mk-feat-icon{
    width:38px; height:38px; border-radius:9px; display:flex; align-items:center; justify-content:center;
    font-size:18px; margin-bottom:14px; background:var(--pine-tint);
  }
  .mk-feat-card:nth-child(3n-1) .mk-feat-icon{background:var(--rust-tint);}
  .mk-feat-card h3{font-family:var(--font-display); font-size:16px; font-weight:700; margin:0 0 6px;}
  .mk-feat-card p{font-size:13px; color:var(--ink-soft); line-height:1.55; margin:0;}

  /* ---- how it works ---- */
  .mk-how{background:var(--paper-dark);}
  .mk-steps{position:relative; display:grid; grid-template-columns:repeat(3,1fr); gap:24px; margin-top:40px;}
  @media(max-width:760px){.mk-steps{grid-template-columns:1fr;}}
  .mk-steps::before{
    content:''; position:absolute; top:22px; left:8%; right:8%; height:0;
    border-top:2px dashed var(--line); z-index:0;
  }
  @media(max-width:760px){.mk-steps::before{display:none;}}
  .mk-step{position:relative; z-index:1;}
  .mk-step-num{
    width:44px; height:44px; border-radius:50%; background:var(--ink); color:var(--paper);
    display:flex; align-items:center; justify-content:center; font-family:var(--font-display); font-weight:700; font-size:17px;
    margin-bottom:16px; border:3px solid var(--paper-dark);
  }
  .mk-step h3{font-family:var(--font-display); font-size:16px; margin:0 0 6px;}
  .mk-step p{font-size:13px; color:var(--ink-soft); line-height:1.55; margin:0;}

  /* ---- testimonials ---- */
  .mk-testi-grid{display:grid; grid-template-columns:repeat(3,1fr); gap:16px; margin-top:36px;}
  @media(max-width:860px){.mk-testi-grid{grid-template-columns:1fr;}}
  .mk-testi-card{background:var(--card); border:1px solid var(--line); border-radius:12px; padding:22px;}
  .mk-testi-quote{font-size:13.5px; color:var(--ink); line-height:1.65; margin:0 0 16px;}
  .mk-testi-who{display:flex; align-items:center; gap:10px;}
  .mk-testi-avatar{
    width:34px; height:34px; border-radius:50%; display:flex; align-items:center; justify-content:center;
    font-family:var(--font-display); font-weight:700; color:#fff; font-size:13px; flex-shrink:0;
  }
  .mk-testi-name{font-size:12.5px; font-weight:700;}
  .mk-testi-role{font-size:11px; color:var(--ink-faint);}

  /* ---- CTA banner ---- */
  .mk-cta{
    background:var(--ink); color:var(--paper); border-radius:16px; padding:48px 40px;
    display:flex; justify-content:space-between; align-items:center; gap:24px; flex-wrap:wrap;
    max-width:1120px; margin:0 auto;
  }
  .mk-cta h2{font-family:var(--font-display); font-size:26px; margin:0 0 6px; color:var(--paper);}
  .mk-cta p{margin:0; color:#C9D2C2; font-size:13px;}
  .mk-cta .mk-btn-primary{box-shadow:0 3px 0 var(--rust-dark);}

  /* ---- app section intro ---- */
  .mk-app-intro{max-width:1120px; margin:0 auto 0; padding:64px 24px 0; text-align:center;}
  .mk-app-intro .mk-eyebrow{justify-content:center;}
  .mk-app-intro .mk-h2{margin-left:auto; margin-right:auto;}
  .mk-app-intro p{max-width:520px; margin:0 auto; font-size:14px; color:var(--ink-soft);}

  /* ---- footer ---- */
  .mk-footer{background:var(--paper-dark); border-top:2px solid var(--ink); padding:52px 24px 26px; margin-top:24px;}
  .mk-footer-grid{max-width:1120px; margin:0 auto; display:grid; grid-template-columns:1.4fr repeat(3,1fr); gap:28px;}
  @media(max-width:700px){.mk-footer-grid{grid-template-columns:repeat(2,1fr);}}
  .mk-footer-brand{display:flex; align-items:center; gap:10px; margin-bottom:10px;}
  .mk-footer-brand svg{width:28px; height:28px;}
  .mk-footer-brand span{font-family:var(--font-display); font-weight:700; font-size:17px;}
  .mk-footer p.mk-footer-tag{font-size:12.5px; color:var(--ink-soft); max-width:240px; line-height:1.5;}
  .mk-footer-col h4{font-size:11px; text-transform:uppercase; letter-spacing:1px; color:var(--ink-faint); margin:0 0 12px;}
  .mk-footer-col a{display:block; font-size:13px; color:var(--ink-soft); margin-bottom:9px;}
  .mk-footer-col a:hover{color:var(--ink);}
  .mk-footer-bottom{max-width:1120px; margin:34px auto 0; padding-top:18px; border-top:1px solid var(--line); font-size:11.5px; color:var(--ink-faint); display:flex; justify-content:space-between; flex-wrap:wrap; gap:8px;}

  /* ---------- Auth (signup / login) ---------- */
  #fh-auth{
    min-height:100vh; display:flex; align-items:center; justify-content:center; padding:40px 20px;
    background:var(--paper);
    background-image: radial-gradient(circle at 1px 1px, var(--line-soft) 1px, transparent 1px);
    background-size:22px 22px;
  }
  .fh-auth-card{
    width:100%; max-width:420px; background:var(--card); border:1px solid var(--line); border-radius:16px;
    padding:32px 30px; box-shadow:0 20px 50px -18px rgba(30,45,25,0.35);
  }
  .fh-auth-logo{display:flex; align-items:center; gap:10px; margin-bottom:22px;}
  .fh-auth-logo svg{width:36px; height:36px;}
  .fh-auth-logo span{font-family:var(--font-display); font-weight:700; font-size:19px;}
  .fh-auth-card h2{font-family:var(--font-display); font-size:22px; margin:0 0 6px;}
  .fh-auth-card > p.fh-auth-sub{font-size:13px; color:var(--ink-soft); margin:0 0 22px; line-height:1.5;}
  .fh-auth-error{
    background:var(--danger-tint); color:var(--danger); border-radius:8px; padding:9px 12px; font-size:12.5px;
    font-weight:600; margin-bottom:14px;
  }
  .fh-auth-switch{text-align:center; font-size:12.5px; color:var(--ink-soft); margin-top:18px;}
  .fh-auth-switch button{background:none; border:none; color:var(--pine-dark); font-weight:700; font-size:12.5px; padding:0; text-decoration:underline; cursor:pointer;}
  .fh-auth-note{font-size:11px; color:var(--ink-faint); text-align:center; margin-top:16px; line-height:1.5;}
</style>

<div id="mk-root">
  <nav class="mk-nav">
    <div class="mk-nav-inner">
      <div class="mk-nav-brand">
        <svg viewBox="0 0 44 44" fill="none">
          <circle cx="22" cy="22" r="21" fill="#2E4A29" stroke="#1B2B17" stroke-width="1"/>
          <path d="M30 8 C 34 10 35 15 32 18 C 29 20 25 19 24 15 C 23 11 26 7 30 8 Z" fill="#6E9B4A"/>
          <path d="M24 15 C 27 13.5 30 11.5 32 9" stroke="#EFEAD9" stroke-width="1" stroke-linecap="round" opacity="0.7"/>
          <path d="M4 28 C 12 22, 18 30, 26 24 C 32 20, 38 25, 41 22 L41 22 C 41 33 32.5 41.5 22 41.5 C 11.5 41.5 3 33 3 22.5 Z" fill="#22331D"/>
          <path d="M2 31 C 10 25, 17 33, 25 27 C 31 23, 38 27.5, 42 25" stroke="#EFEAD9" stroke-width="1.6" stroke-linecap="round" fill="none" opacity="0.85"/>
          <circle cx="22" cy="22" r="21" fill="none" stroke="#EFEAD9" stroke-width="1.3" opacity="0.9"/>
        </svg>
        <span>MkulimaKe</span>
      </div>
      <div class="mk-nav-links">
        <a href="#features">Features</a>
        <a href="#how">How it works</a>
        <a href="#stories">Stories</a>
        <a href="#app" class="mk-nav-cta">Open the app</a>
      </div>
    </div>
  </nav>

  <section class="mk-hero">
    <div class="mk-wrap mk-hero-grid">
      <div>
        <p class="mk-eyebrow">Farm record keeping</p>
        <h1>Every animal on your farm, <em>one record away.</em></h1>
        <p class="mk-sub">MkulimaKe is a simple home for your livestock and poultry records — tag numbers, health logs, weights, and breeding history, kept in one handbook instead of scattered notebooks.</p>
        <div class="mk-hero-ctas">
          <a href="#app" class="mk-btn mk-btn-primary">Open the app →</a>
          <a href="#features" class="mk-btn mk-btn-ghost">See what it does</a>
        </div>
        <div class="mk-hero-tags">
          <span class="mk-hero-tag">🐄 Livestock</span>
          <span class="mk-hero-tag">🐔 Poultry</span>
          <span class="mk-hero-tag">✚ Health logs</span>
          <span class="mk-hero-tag">⚖ Weight tracking</span>
        </div>
      </div>
      <div class="mk-hero-visual" aria-hidden="true">
        <div class="mk-hv-card mk-hv-1">
          <div class="mk-hv-id">#LS-014</div>
          <div class="mk-hv-name">Kesi</div>
          <div class="mk-hv-meta"><span>Friesian</span><span>·</span><span>2 yr</span></div>
        </div>
        <div class="mk-hv-card mk-hv-2">
          <div class="mk-hv-id">#BD-102</div>
          <div class="mk-hv-name">Kienyeji flock</div>
          <div class="mk-hv-meta"><span>Chicken</span><span>·</span><span>40 birds</span></div>
        </div>
        <div class="mk-hv-card mk-hv-3">
          <div class="mk-hv-id">#LS-021</div>
          <div class="mk-hv-name">Tumbo</div>
          <div class="mk-hv-meta"><span>Boer goat</span><span>·</span><span>8 mo</span></div>
        </div>
      </div>
    </div>
  </section>

  <div class="mk-strip">
    <div class="mk-strip-inner">
      <div class="mk-strip-item"><b>2</b>&nbsp;record types — livestock &amp; poultry</div>
      <div class="mk-strip-item"><b>∞</b>&nbsp;animals, no per-head fees</div>
      <div class="mk-strip-item"><b>0</b>&nbsp;paperwork left in the barn</div>
      <div class="mk-strip-item"><b>1</b>&nbsp;handbook for the whole farm</div>
    </div>
  </div>

  <section id="features">
    <div class="mk-wrap">
      <div class="mk-feat-head">
        <div>
          <p class="mk-eyebrow">What's inside</p>
          <h2 class="mk-h2">Built only for animal records —<br>nothing you don't need.</h2>
        </div>
        <p class="mk-lede">No crop planning, no equipment schedules, no invoicing. Just a clean, fast way to keep track of every animal you raise.</p>
      </div>
      <div class="mk-feat-grid">
        <div class="mk-feat-card"><div class="mk-feat-icon">🏷️</div><h3>Animal profiles</h3><p>Tag ID, name, breed, sex, date of birth, and status for every head of livestock or poultry you keep.</p></div>
        <div class="mk-feat-card"><div class="mk-feat-icon">✚</div><h3>Health &amp; vaccination log</h3><p>Timestamp checkups, vaccinations, and treatments against each animal, in a running timeline.</p></div>
        <div class="mk-feat-card"><div class="mk-feat-icon">⚖️</div><h3>Weight tracking</h3><p>Log weight checks over time to keep an eye on growth and condition.</p></div>
        <div class="mk-feat-card"><div class="mk-feat-icon">🔍</div><h3>Search &amp; filter</h3><p>Find any animal instantly by tag number, name, breed, species, or status.</p></div>
        <div class="mk-feat-card"><div class="mk-feat-icon">📋</div><h3>Farm dashboard</h3><p>See your totals, recent activity, and newest additions at a glance the moment you open the app.</p></div>
        <div class="mk-feat-card"><div class="mk-feat-icon">🔒</div><h3>Private by default</h3><p>Your records are tied to your account only — nobody else sees your farm's data.</p></div>
      </div>
    </div>
  </section>

  <section id="how" class="mk-how">
    <div class="mk-wrap">
      <p class="mk-eyebrow">How it works</p>
      <h2 class="mk-h2">From new arrival to full history, in three steps.</h2>
      <div class="mk-steps">
        <div class="mk-step">
          <div class="mk-step-num">1</div>
          <h3>Add the animal</h3>
          <p>Tag it as livestock or poultry, give it an ID, and fill in the basics — species, breed, sex, birth date.</p>
        </div>
        <div class="mk-step">
          <div class="mk-step-num">2</div>
          <h3>Log what happens</h3>
          <p>Every checkup, vaccination, treatment, or weight check gets added to that animal's own timeline.</p>
        </div>
        <div class="mk-step">
          <div class="mk-step-num">3</div>
          <h3>Track from the dashboard</h3>
          <p>Search, filter, and see farm-wide totals and recent activity whenever you check in.</p>
        </div>
      </div>
    </div>
  </section>

  <section id="stories">
    <div class="mk-wrap">
      <p class="mk-eyebrow">From the field</p>
      <h2 class="mk-h2">Why small farms keep it simple.</h2>
      <div class="mk-testi-grid">
        <div class="mk-testi-card">
          <p class="mk-testi-quote">"I used to keep vaccination dates on a wall calendar. Now every goat has its own record and I can check it in seconds."</p>
          <div class="mk-testi-who">
            <div class="mk-testi-avatar" style="background:var(--pine)">A</div>
            <div><div class="mk-testi-name">Amina</div><div class="mk-testi-role">Dairy &amp; goat farmer</div></div>
          </div>
        </div>
        <div class="mk-testi-card">
          <p class="mk-testi-quote">"With 200 layers, I needed something faster than a notebook. I log the flock as one record and note anything unusual."</p>
          <div class="mk-testi-who">
            <div class="mk-testi-avatar" style="background:var(--rust)">D</div>
            <div><div class="mk-testi-name">Daniel</div><div class="mk-testi-role">Poultry keeper</div></div>
          </div>
        </div>
        <div class="mk-testi-card">
          <p class="mk-testi-quote">"It's just animal records, nothing else to learn. That's exactly what I wanted for the farm."</p>
          <div class="mk-testi-who">
            <div class="mk-testi-avatar" style="background:var(--pine)">W</div>
            <div><div class="mk-testi-name">Wanjiru</div><div class="mk-testi-role">Mixed livestock farmer</div></div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section>
    <div class="mk-cta">
      <div>
        <h2>Start your farm's handbook today.</h2>
        <p>Free to use — add your first animal in under a minute.</p>
      </div>
      <a href="#app" class="mk-btn mk-btn-primary">Open the app →</a>
    </div>
  </section>

  <div class="mk-app-intro">
    <p class="mk-eyebrow">The app</p>
    <h2 class="mk-h2">Your farm records, live below.</h2>
    <p>Add livestock and poultry, log health activity, and keep an eye on the whole farm from this dashboard.</p>
  </div>
</div>

<div id="fh-root">
  <div id="app"></div>
  <div id="fh-auth"></div>
  <div id="fh-app-shell" style="display:none">
  <div class="fh-topbar">
    <div class="fh-brand">
      <svg class="fh-brand-mark" viewBox="0 0 44 44" fill="none">
        <circle cx="22" cy="22" r="21" fill="#2E4A29" stroke="#1B2B17" stroke-width="1"/>
        <circle cx="22" cy="22" r="21" fill="url(#fh-logo-sheen)"/>
        <path d="M30 8 C 34 10 35 15 32 18 C 29 20 25 19 24 15 C 23 11 26 7 30 8 Z" fill="#6E9B4A"/>
        <path d="M24 15 C 27 13.5 30 11.5 32 9" stroke="#EFEAD9" stroke-width="1" stroke-linecap="round" opacity="0.7"/>
        <path d="M4 28 C 12 22, 18 30, 26 24 C 32 20, 38 25, 41 22 L41 22 C 41 33 32.5 41.5 22 41.5 C 11.5 41.5 3 33 3 22.5 Z" fill="#22331D"/>
        <path d="M2 31 C 10 25, 17 33, 25 27 C 31 23, 38 27.5, 42 25" stroke="#EFEAD9" stroke-width="1.6" stroke-linecap="round" fill="none" opacity="0.85"/>
        <path d="M1 35.5 C 9 30, 16.5 37, 24.5 31.5 C 30.5 27.5, 37.5 31.5, 41.5 29.5" stroke="#EFEAD9" stroke-width="1.6" stroke-linecap="round" fill="none" opacity="0.55"/>
        <circle cx="22" cy="22" r="21" fill="none" stroke="#EFEAD9" stroke-width="1.3" opacity="0.9"/>
        <defs>
          <radialGradient id="fh-logo-sheen" cx="30%" cy="20%" r="80%">
            <stop offset="0%" stop-color="#4C7A3E" stop-opacity="0.9"/>
            <stop offset="60%" stop-color="#2E4A29" stop-opacity="0"/>
          </radialGradient>
        </defs>
      </svg>
      <div class="fh-brand-text">
        <h1 id="fh-brand-name">MkulimaKe</h1>
        <p id="fh-brand-tag">Livestock &amp; Poultry Records</p>
      </div>
    </div>
    <div class="fh-nav" id="fh-nav"></div>
    <div style="display:flex; gap:8px; align-items:center;">
      <button class="fh-add-btn" id="fh-add-open">+ Add animal</button>
      <button class="fh-btn fh-btn-ghost" id="fh-logout-btn" style="padding:10px 14px; font-size:12px;">Log out</button>
    </div>
  </div>

  <div class="fh-main" id="fh-main">
    <div class="fh-loading"><div class="fh-spinner"></div> Loading your farm records…</div>
  </div>
  </div>
</div>

<div id="fh-toast" class="fh-toast"></div>

<script>
(function(){
  const STORE_KEY = 'animals';
  const ACCOUNT_KEY = 'account';
  let animals = [];
  let ready = false;
  let account = null;       // {farmName, ownerName, email, password, createdAt}
  let loggedIn = false;     // session flag (in-memory)
  let authView = 'signup';  // 'signup' | 'login'
  let authError = '';
  let view = 'dashboard'; // dashboard | list
  let listFilter = 'all'; // all | livestock | bird
  let searchTerm = '';
  let speciesFilter = 'all';
  let openDetailId = null;
  let modalMode = null; // 'add' | 'edit' | null
  let editingId = null;

  const SPECIES_LIVESTOCK = ['Cattle','Goat','Sheep','Pig','Rabbit','Donkey','Horse','Other'];
  const SPECIES_BIRD = ['Chicken','Duck','Turkey','Quail','Goose','Guinea Fowl','Other'];

  function uid(){ return Math.random().toString(36).slice(2,10) + Date.now().toString(36).slice(-4); }

  async function loadData(){
    try{
      const res = await window.storage.get(STORE_KEY, false);
      animals = res && res.value ? JSON.parse(res.value) : [];
    }catch(e){
      animals = [];
    }
    try{
      const acc = await window.storage.get(ACCOUNT_KEY, false);
      account = acc && acc.value ? JSON.parse(acc.value) : null;
    }catch(e){
      account = null;
    }
    authView = account ? 'login' : 'signup';
    ready = true;
    render();
  }

  async function saveAccount(){
    try{
      await window.storage.set(ACCOUNT_KEY, JSON.stringify(account), false);
    }catch(e){
      toast('Could not save your account — try again');
    }
  }

  async function saveData(){
    try{
      await window.storage.set(STORE_KEY, JSON.stringify(animals), false);
    }catch(e){
      toast('Could not save — try again');
    }
  }

  function toast(msg){
    const t = document.getElementById('fh-toast');
    t.textContent = msg;
    t.classList.add('show');
    clearTimeout(window.__fhToastTimer);
    window.__fhToastTimer = setTimeout(()=>t.classList.remove('show'), 2200);
  }

  function esc(s){
    return String(s==null?'':s).replace(/[&<>"']/g, c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));
  }

  function ageString(dob){
    if(!dob) return '—';
    const d = new Date(dob);
    if(isNaN(d)) return '—';
    const now = new Date();
    let months = (now.getFullYear()-d.getFullYear())*12 + (now.getMonth()-d.getMonth());
    if(months < 1) return 'Under 1 mo';
    if(months < 24) return months + ' mo';
    return Math.floor(months/12) + ' yr';
  }

  function catColor(cat){ return cat === 'bird' ? 'var(--rust)' : 'var(--pine)'; }
  function catLabel(cat){ return cat === 'bird' ? 'Poultry' : 'Livestock'; }

  function speciesList(cat){ return cat === 'bird' ? SPECIES_BIRD : SPECIES_LIVESTOCK; }

  // -------- Render root --------
  function render(){
    const authHost = document.getElementById('fh-auth');
    const shell = document.getElementById('fh-app-shell');

    if(!ready){
      authHost.innerHTML = '';
      shell.style.display = 'none';
      return;
    }

    if(!account || !loggedIn){
      shell.style.display = 'none';
      authHost.innerHTML = authHtml();
      bindAuth();
      return;
    }

    authHost.innerHTML = '';
    shell.style.display = '';

    document.getElementById('fh-brand-tag').textContent = account.farmName;

    const main = document.getElementById('fh-main');
    document.getElementById('fh-nav').innerHTML = navHtml();
    if(view === 'dashboard') main.innerHTML = dashboardHtml();
    else main.innerHTML = listHtml();

    bindNav();
    bindDashboardOrList();
    renderModals();

    const logoutBtn = document.getElementById('fh-logout-btn');
    if(logoutBtn) logoutBtn.onclick = ()=>{ loggedIn = false; authView='login'; authError=''; render(); };
  }

  function authLogoSvg(){
    return `<svg viewBox="0 0 44 44" fill="none">
      <circle cx="22" cy="22" r="21" fill="#2E4A29" stroke="#1B2B17" stroke-width="1"/>
      <path d="M30 8 C 34 10 35 15 32 18 C 29 20 25 19 24 15 C 23 11 26 7 30 8 Z" fill="#6E9B4A"/>
      <path d="M4 28 C 12 22, 18 30, 26 24 C 32 20, 38 25, 41 22 L41 22 C 41 33 32.5 41.5 22 41.5 C 11.5 41.5 3 33 3 22.5 Z" fill="#22331D"/>
      <circle cx="22" cy="22" r="21" fill="none" stroke="#EFEAD9" stroke-width="1.3" opacity="0.9"/>
    </svg>`;
  }

  function authHtml(){
    if(authView === 'signup' && !account){
      return `
        <div class="fh-auth-card">
          <div class="fh-auth-logo">${authLogoSvg()}<span>MkulimaKe</span></div>
          <h2>Create your farm account</h2>
          <p class="fh-auth-sub">Set up MkulimaKe for your farm to start keeping livestock and poultry records.</p>
          ${authError ? `<div class="fh-auth-error">${esc(authError)}</div>` : ''}
          <div class="fh-field"><label>Farm name</label><input id="au-farm" type="text" placeholder="e.g. Green Ridge Farm"></div>
          <div class="fh-field"><label>Your name</label><input id="au-name" type="text" placeholder="e.g. Amina Wanjala"></div>
          <div class="fh-field"><label>Email</label><input id="au-email" type="email" placeholder="you@example.com"></div>
          <div class="fh-field"><label>Password</label><input id="au-pass" type="password" placeholder="Choose a password"></div>
          <button class="fh-btn fh-btn-primary" id="au-signup-btn" style="width:100%; padding:12px; margin-top:6px;">Create account</button>
          <div class="fh-auth-switch">Already set up MkulimaKe here? <button id="au-goto-login">Log in</button></div>
          <p class="fh-auth-note">Your account is stored privately and only you can see your farm's records.</p>
        </div>
      `;
    }
    return `
      <div class="fh-auth-card">
        <div class="fh-auth-logo">${authLogoSvg()}<span>MkulimaKe</span></div>
        <h2>Welcome back${account ? ', ' + esc(account.farmName) : ''}</h2>
        <p class="fh-auth-sub">Log in to view your farm's livestock and poultry records.</p>
        ${authError ? `<div class="fh-auth-error">${esc(authError)}</div>` : ''}
        <div class="fh-field"><label>Email</label><input id="au-login-email" type="email" placeholder="you@example.com"></div>
        <div class="fh-field"><label>Password</label><input id="au-login-pass" type="password" placeholder="Your password"></div>
        <button class="fh-btn fh-btn-primary" id="au-login-btn" style="width:100%; padding:12px; margin-top:6px;">Log in</button>
        <div class="fh-auth-switch">
          New to this farm? <button id="au-goto-signup">Set up a different account</button>
        </div>
        <p class="fh-auth-note">Setting up a different account replaces this browser's saved farm — its animal records go with it.</p>
      </div>
    `;
  }

  function bindAuth(){
    const goSignup = document.getElementById('au-goto-signup');
    if(goSignup) goSignup.onclick = ()=>{
      if(confirm('Setting up a new farm account will remove the current one and its saved animal records from this browser. Continue?')){
        account = null; animals = []; authError=''; authView='signup'; render();
      }
    };
    const goLogin = document.getElementById('au-goto-login');
    if(goLogin) goLogin.onclick = ()=>{ authView='login'; authError=''; render(); };

    const signupBtn = document.getElementById('au-signup-btn');
    if(signupBtn){
      signupBtn.onclick = async ()=>{
        const farmName = document.getElementById('au-farm').value.trim();
        const ownerName = document.getElementById('au-name').value.trim();
        const email = document.getElementById('au-email').value.trim().toLowerCase();
        const password = document.getElementById('au-pass').value;
        if(!farmName || !email || !password){ authError='Farm name, email, and password are required.'; render(); return; }
        account = {farmName, ownerName, email, password, createdAt:Date.now()};
        await saveAccount();
        loggedIn = true; authError='';
        toast(`Welcome to MkulimaKe, ${farmName}!`);
        render();
      };
    }
    const loginBtn = document.getElementById('au-login-btn');
    if(loginBtn){
      loginBtn.onclick = ()=>{
        const email = document.getElementById('au-login-email').value.trim().toLowerCase();
        const password = document.getElementById('au-login-pass').value;
        if(account && email === account.email.toLowerCase() && password === account.password){
          loggedIn = true; authError='';
          render();
        }else{
          authError = 'Email or password is incorrect.';
          render();
        }
      };
    }
    document.querySelectorAll('#fh-auth input').forEach(inp=>{
      inp.onkeydown = (e)=>{
        if(e.key === 'Enter'){
          const btn = document.getElementById('au-signup-btn') || document.getElementById('au-login-btn');
          if(btn) btn.click();
        }
      };
    });
  }

  function navHtml(){
    const tabs = [['dashboard','Dashboard'],['list','All Animals']];
    return tabs.map(([id,label])=>
      `<button class="fh-nav-btn ${view===id?'active':''}" data-nav="${id}">${label}</button>`
    ).join('');
  }

  function bindNav(){
    document.querySelectorAll('[data-nav]').forEach(btn=>{
      btn.onclick = ()=>{ view = btn.dataset.nav; render(); };
    });
    document.getElementById('fh-add-open').onclick = ()=>{ modalMode='add'; editingId=null; render(); };
  }

  // -------- Dashboard --------
  function dashboardHtml(){
    const total = animals.length;
    const livestock = animals.filter(a=>a.category==='livestock').length;
    const birds = animals.filter(a=>a.category==='bird').length;
    const monthAgo = Date.now() - 30*24*3600*1000;
    let logCount = 0;
    animals.forEach(a=> (a.healthLog||[]).forEach(l=>{ if(new Date(l.date).getTime() >= monthAgo) logCount++; }));

    if(total === 0){
      return `
        <div class="fh-stats">
          ${statCard(0,'Total animals','var(--pine)')}
          ${statCard(0,'Livestock','var(--pine)')}
          ${statCard(0,'Poultry','var(--rust)')}
          ${statCard(0,'Log entries (30d)','var(--ink)')}
        </div>
        <div class="fh-empty">
          <h3>Your farm records are empty</h3>
          <p>Add your first animal to start keeping records — health checks, weights, and treatments all live here.</p>
          <button class="fh-btn fh-btn-primary" onclick="document.getElementById('fh-add-open').click()">+ Add your first animal</button>
        </div>
      `;
    }

    // recent activity: last 6 log entries across all animals, plus recent additions
    let events = [];
    animals.forEach(a=>{
      (a.healthLog||[]).forEach(l=> events.push({date:l.date, text:`${l.type} — ${a.name || a.tagId}`, cat:a.category, kind:l.type}));
    });
    events.sort((a,b)=> new Date(b.date) - new Date(a.date));
    events = events.slice(0,6);

    return `
      <div class="fh-stats">
        ${statCard(total,'Total animals','var(--ink)')}
        ${statCard(livestock,'Livestock','var(--pine)')}
        ${statCard(birds,'Poultry','var(--rust)')}
        ${statCard(logCount,'Log entries (30d)','#5A3A78')}
      </div>
      <div class="fh-section-title">Recent activity</div>
      ${events.length ? `<div class="fh-activity">${events.map(e=>`
        <div class="fh-activity-row">
          <span class="fh-activity-dot" style="background:${catColor(e.cat)}"></span>
          <span>${esc(e.text)}</span>
          <span class="fh-activity-meta">${esc(e.date)}</span>
        </div>
      `).join('')}</div>` : `<div class="fh-empty"><p style="margin:0">No log entries yet — open an animal's record to add a health note, treatment, or weight check.</p></div>`}
      <div class="fh-section-title">Recently added</div>
      <div class="fh-grid">
        ${animals.slice().sort((a,b)=> (b.createdAt||0)-(a.createdAt||0)).slice(0,3).map(tagCardHtml).join('')}
      </div>
    `;
  }

  function statCard(num,label,color){
    return `<div class="fh-stat" style="--stat-color:${color}"><div class="fh-stat-num">${num}</div><div class="fh-stat-label">${label}</div></div>`;
  }

  // -------- List view --------
  function listHtml(){
    const speciesOptions = Array.from(new Set(animals.map(a=>a.species))).sort();
    let filtered = animals.filter(a=>{
      if(listFilter !== 'all' && a.category !== listFilter) return false;
      if(speciesFilter !== 'all' && a.species !== speciesFilter) return false;
      if(searchTerm){
        const s = searchTerm.toLowerCase();
        if(!(`${a.name} ${a.tagId} ${a.breed} ${a.species}`.toLowerCase().includes(s))) return false;
      }
      return true;
    });
    filtered.sort((a,b)=> (b.createdAt||0)-(a.createdAt||0));

    return `
      <div class="fh-filterbar">
        <input class="fh-search" id="fh-search" placeholder="Search by name, tag ID, or breed…" value="${esc(searchTerm)}">
        <button class="fh-chip ${listFilter==='all'?'active':''}" data-filter="all">All</button>
        <button class="fh-chip ${listFilter==='livestock'?'active':''}" data-filter="livestock">Livestock</button>
        <button class="fh-chip ${listFilter==='bird'?'active':''}" data-filter="bird">Poultry</button>
        <select class="fh-select" id="fh-species-filter">
          <option value="all">All species</option>
          ${speciesOptions.map(s=>`<option value="${esc(s)}" ${speciesFilter===s?'selected':''}>${esc(s)}</option>`).join('')}
        </select>
      </div>
      ${filtered.length ? `<div class="fh-grid">${filtered.map(tagCardHtml).join('')}</div>` :
        `<div class="fh-empty"><h3>No matches</h3><p>Try a different search or filter.</p></div>`}
    `;
  }

  function tagCardHtml(a){
    const badgeClass = 'status-' + (a.status || 'active');
    return `
      <div class="fh-tagcard" style="--cat-color:${catColor(a.category)}" data-open="${a.id}">
        <div class="fh-tagcard-hole"></div>
        <div class="fh-tagcard-top">
          <div>
            <div class="fh-tagcard-id">#${esc(a.tagId||'—')}</div>
            <div class="fh-tagcard-name">${esc(a.name || a.species)}</div>
          </div>
          <span class="fh-badge ${badgeClass}">${esc(a.status||'active')}</span>
        </div>
        <div class="fh-tagcard-species">${esc(a.species)}${a.breed ? ' · ' + esc(a.breed) : ''}</div>
        <div class="fh-tagcard-meta">
          <div><span>Sex</span>${esc(a.sex||'—')}</div>
          <div><span>Age</span>${ageString(a.dob)}</div>
          <div><span>Weight</span>${a.weight ? esc(a.weight)+' '+esc(a.weightUnit||'kg') : '—'}</div>
        </div>
      </div>
    `;
  }

  function bindDashboardOrList(){
    document.querySelectorAll('[data-open]').forEach(el=>{
      el.onclick = ()=>{ openDetailId = el.dataset.open; render(); };
    });
    const search = document.getElementById('fh-search');
    if(search){
      search.oninput = ()=>{ searchTerm = search.value; render(); search2focus(); };
    }
    document.querySelectorAll('[data-filter]').forEach(el=>{
      el.onclick = ()=>{ listFilter = el.dataset.filter; render(); };
    });
    const sf = document.getElementById('fh-species-filter');
    if(sf){ sf.onchange = ()=>{ speciesFilter = sf.value; render(); }; }
  }
  function search2focus(){
    const s = document.getElementById('fh-search');
    if(s){ s.focus(); s.selectionStart = s.selectionEnd = s.value.length; }
  }

  // -------- Modals: add/edit + detail --------
  function renderModals(){
    let host = document.getElementById('fh-modal-host');
    if(host) host.remove();
    if(!modalMode && !openDetailId) return;
    host = document.createElement('div');
    host.id = 'fh-modal-host';
    document.getElementById('fh-root').appendChild(host);

    if(modalMode === 'add' || modalMode === 'edit'){
      host.innerHTML = formModalHtml();
      bindFormModal();
    } else if(openDetailId){
      const a = animals.find(x=>x.id===openDetailId);
      if(!a){ openDetailId=null; return; }
      host.innerHTML = detailModalHtml(a);
      bindDetailModal(a);
    }
  }

  function formModalHtml(){
    const editing = modalMode === 'edit';
    const a = editing ? animals.find(x=>x.id===editingId) : {category:'livestock', status:'active'};
    return `
      <div class="fh-overlay" id="fh-form-overlay">
        <div class="fh-modal">
          <div class="fh-modal-header">
            <h2>${editing ? 'Edit animal' : 'Add animal'}</h2>
            <button class="fh-modal-close" id="fh-form-close">✕</button>
          </div>
          <div class="fh-modal-body">
            <div class="fh-cattype-toggle">
              <button type="button" class="fh-cattype-opt ${a.category==='livestock'?'sel-livestock':''}" data-cat="livestock">🐄 Livestock</button>
              <button type="button" class="fh-cattype-opt ${a.category==='bird'?'sel-bird':''}" data-cat="bird">🐔 Poultry</button>
            </div>
            <div class="fh-row2">
              <div class="fh-field">
                <label>Species</label>
                <select id="f-species">
                  ${speciesList(a.category||'livestock').map(s=>`<option value="${s}" ${a.species===s?'selected':''}>${s}</option>`).join('')}
                </select>
              </div>
              <div class="fh-field">
                <label>Tag / ID number</label>
                <input id="f-tagid" type="text" placeholder="e.g. LS-014" value="${esc(a.tagId||'')}">
              </div>
            </div>
            <div class="fh-row2">
              <div class="fh-field">
                <label>Name (optional)</label>
                <input id="f-name" type="text" placeholder="e.g. Kesi" value="${esc(a.name||'')}">
              </div>
              <div class="fh-field">
                <label>Breed</label>
                <input id="f-breed" type="text" placeholder="e.g. Friesian" value="${esc(a.breed||'')}">
              </div>
            </div>
            <div class="fh-row3">
              <div class="fh-field">
                <label>Sex</label>
                <select id="f-sex">
                  <option ${a.sex==='Female'?'selected':''}>Female</option>
                  <option ${a.sex==='Male'?'selected':''}>Male</option>
                  <option ${a.sex==='Unknown'||!a.sex?'selected':''}>Unknown</option>
                </select>
              </div>
              <div class="fh-field">
                <label>Date of birth</label>
                <input id="f-dob" type="date" value="${esc(a.dob||'')}">
              </div>
              <div class="fh-field">
                <label>Status</label>
                <select id="f-status">
                  <option value="active" ${a.status==='active'?'selected':''}>Active</option>
                  <option value="sold" ${a.status==='sold'?'selected':''}>Sold</option>
                  <option value="deceased" ${a.status==='deceased'?'selected':''}>Deceased</option>
                </select>
              </div>
            </div>
            <div class="fh-row2">
              <div class="fh-field">
                <label>Weight</label>
                <input id="f-weight" type="number" min="0" step="0.1" placeholder="e.g. 320" value="${a.weight!=null?esc(a.weight):''}">
              </div>
              <div class="fh-field">
                <label>Weight unit</label>
                <select id="f-weightunit">
                  <option value="kg" ${(!a.weightUnit||a.weightUnit==='kg')?'selected':''}>kg</option>
                  <option value="lb" ${a.weightUnit==='lb'?'selected':''}>lb</option>
                  <option value="g" ${a.weightUnit==='g'?'selected':''}>g</option>
                </select>
              </div>
            </div>
            <div class="fh-field">
              <label>Notes</label>
              <textarea id="f-notes" rows="3" placeholder="Distinguishing marks, temperament, parentage…">${esc(a.notes||'')}</textarea>
            </div>
          </div>
          <div class="fh-modal-footer">
            ${editing ? '<button class="fh-btn fh-btn-danger" id="fh-form-delete" style="margin-right:auto">Delete</button>' : ''}
            <button class="fh-btn fh-btn-ghost" id="fh-form-cancel">Cancel</button>
            <button class="fh-btn fh-btn-primary" id="fh-form-save">${editing ? 'Save changes' : 'Add animal'}</button>
          </div>
        </div>
      </div>
    `;
  }

  function bindFormModal(){
    const overlay = document.getElementById('fh-form-overlay');
    overlay.onclick = (e)=>{ if(e.target===overlay) closeForm(); };
    document.getElementById('fh-form-close').onclick = closeForm;
    document.getElementById('fh-form-cancel').onclick = closeForm;

    let currentCat = (modalMode==='edit' ? animals.find(x=>x.id===editingId).category : 'livestock') || 'livestock';
    document.querySelectorAll('[data-cat]').forEach(btn=>{
      btn.onclick = ()=>{
        currentCat = btn.dataset.cat;
        document.querySelectorAll('[data-cat]').forEach(b=>b.classList.remove('sel-livestock','sel-bird'));
        btn.classList.add(currentCat==='bird'?'sel-bird':'sel-livestock');
        const sp = document.getElementById('f-species');
        sp.innerHTML = speciesList(currentCat).map(s=>`<option value="${s}">${s}</option>`).join('');
      };
    });

    const del = document.getElementById('fh-form-delete');
    if(del){
      del.onclick = ()=>{
        animals = animals.filter(x=>x.id!==editingId);
        saveData();
        modalMode=null; editingId=null; openDetailId=null;
        toast('Animal record deleted');
        render();
      };
    }

    document.getElementById('fh-form-save').onclick = ()=>{
      const tagId = document.getElementById('f-tagid').value.trim();
      if(!tagId){ toast('Tag / ID number is required'); return; }
      const record = {
        id: modalMode==='edit' ? editingId : uid(),
        category: currentCat,
        species: document.getElementById('f-species').value,
        tagId,
        name: document.getElementById('f-name').value.trim(),
        breed: document.getElementById('f-breed').value.trim(),
        sex: document.getElementById('f-sex').value,
        dob: document.getElementById('f-dob').value,
        status: document.getElementById('f-status').value,
        weight: document.getElementById('f-weight').value ? Number(document.getElementById('f-weight').value) : null,
        weightUnit: document.getElementById('f-weightunit').value,
        notes: document.getElementById('f-notes').value.trim(),
        healthLog: modalMode==='edit' ? (animals.find(x=>x.id===editingId).healthLog||[]) : [],
        createdAt: modalMode==='edit' ? animals.find(x=>x.id===editingId).createdAt : Date.now()
      };
      if(modalMode==='edit'){
        animals = animals.map(x=> x.id===editingId ? record : x);
        toast('Changes saved');
      }else{
        animals.push(record);
        toast('Animal added to MkulimaKe');
      }
      saveData();
      modalMode=null; editingId=null;
      render();
    };
  }
  function closeForm(){ modalMode=null; editingId=null; render(); }

  function detailModalHtml(a){
    const logs = (a.healthLog||[]).slice().sort((x,y)=> new Date(y.date)-new Date(x.date));
    const icon = a.category==='bird' ? '🐔' : '🐄';
    return `
      <div class="fh-overlay" id="fh-detail-overlay">
        <div class="fh-modal" style="max-width:600px">
          <div class="fh-modal-header">
            <h2>Animal record</h2>
            <button class="fh-modal-close" id="fh-detail-close">✕</button>
          </div>
          <div class="fh-modal-body">
            <div class="fh-detail-head">
              <div class="fh-detail-tag" style="background:${catColor(a.category)}">${icon}</div>
              <div style="flex:1">
                <div class="fh-detail-id">#${esc(a.tagId)} · ${catLabel(a.category)}</div>
                <div class="fh-detail-name">${esc(a.name || a.species)}</div>
                <span class="fh-badge status-${esc(a.status||'active')}">${esc(a.status||'active')}</span>
              </div>
              <button class="fh-btn fh-btn-ghost" id="fh-detail-edit">Edit</button>
            </div>
            <div class="fh-detail-facts">
              <div class="fh-fact"><span>Species</span><b>${esc(a.species)}</b></div>
              <div class="fh-fact"><span>Breed</span><b>${esc(a.breed)||'—'}</b></div>
              <div class="fh-fact"><span>Sex</span><b>${esc(a.sex)||'—'}</b></div>
              <div class="fh-fact"><span>Date of birth</span><b>${esc(a.dob)||'—'}</b></div>
              <div class="fh-fact"><span>Age</span><b>${ageString(a.dob)}</b></div>
              <div class="fh-fact"><span>Weight</span><b>${a.weight?esc(a.weight)+' '+esc(a.weightUnit||'kg'):'—'}</b></div>
            </div>
            ${a.notes ? `<div class="fh-notes-box">${esc(a.notes)}</div>` : ''}

            <div class="fh-section-title" style="margin-top:24px">Health &amp; activity log</div>
            <div class="fh-addlog-form">
              <select id="log-type">
                <option value="Checkup">Checkup</option>
                <option value="Vaccination">Vaccination</option>
                <option value="Treatment">Treatment</option>
                <option value="Weight check">Weight check</option>
              </select>
              <input id="log-date" type="date" value="${new Date().toISOString().slice(0,10)}">
              <input id="log-note" type="text" placeholder="Note (e.g. dewormed, 2ml Ivomec)">
              <button class="fh-btn fh-btn-primary" id="log-add" style="padding:8px 14px; font-size:12px;">Add entry</button>
            </div>
            <div class="fh-timeline" style="margin-top:16px">
              ${logs.length ? logs.map(l=>logItemHtml(l)).join('') : '<p style="font-size:12px; color:var(--ink-faint); margin:4px 0 0">No entries yet — log a checkup, vaccination, or treatment above.</p>'}
            </div>
          </div>
        </div>
      </div>
    `;
  }

  function logItemHtml(l){
    const iconMap = {'Checkup':'✓','Vaccination':'✚','Treatment':'⚕','Weight check':'⚖'};
    const classMap = {'Checkup':'type-checkup','Vaccination':'','Treatment':'type-treatment','Weight check':'type-weight'};
    return `
      <div class="fh-timeline-item">
        <div class="fh-timeline-dot ${classMap[l.type]||''}">${iconMap[l.type]||'•'}</div>
        <div class="fh-timeline-content">
          <div class="fh-timeline-top">
            <span class="fh-timeline-type">${esc(l.type)}</span>
            <span class="fh-timeline-date">${esc(l.date)}</span>
          </div>
          ${l.note ? `<div class="fh-timeline-note">${esc(l.note)}</div>` : ''}
          <button class="fh-timeline-del" data-dellog="${l.id}">Remove</button>
        </div>
      </div>
    `;
  }

  function bindDetailModal(a){
    const overlay = document.getElementById('fh-detail-overlay');
    overlay.onclick = (e)=>{ if(e.target===overlay){ openDetailId=null; render(); } };
    document.getElementById('fh-detail-close').onclick = ()=>{ openDetailId=null; render(); };
    document.getElementById('fh-detail-edit').onclick = ()=>{
      modalMode='edit'; editingId=a.id; openDetailId=null; render();
    };
    document.getElementById('log-add').onclick = ()=>{
      const type = document.getElementById('log-type').value;
      const date = document.getElementById('log-date').value || new Date().toISOString().slice(0,10);
      const note = document.getElementById('log-note').value.trim();
      const entry = {id:uid(), type, date, note};
      animals = animals.map(x=> x.id===a.id ? {...x, healthLog:[...(x.healthLog||[]), entry]} : x);
      saveData();
      toast('Log entry added');
      render();
    };
    document.querySelectorAll('[data-dellog]').forEach(btn=>{
      btn.onclick = ()=>{
        animals = animals.map(x=> x.id===a.id ? {...x, healthLog:(x.healthLog||[]).filter(l=>l.id!==btn.dataset.dellog)} : x);
        saveData();
        render();
      };
    });
  }

  loadData();
})();
</script>

<footer class="mk-footer">
  <div class="mk-footer-grid">
    <div>
      <div class="mk-footer-brand">
        <svg viewBox="0 0 44 44" fill="none">
          <circle cx="22" cy="22" r="21" fill="#2E4A29" stroke="#1B2B17" stroke-width="1"/>
          <path d="M30 8 C 34 10 35 15 32 18 C 29 20 25 19 24 15 C 23 11 26 7 30 8 Z" fill="#6E9B4A"/>
          <path d="M4 28 C 12 22, 18 30, 26 24 C 32 20, 38 25, 41 22 L41 22 C 41 33 32.5 41.5 22 41.5 C 11.5 41.5 3 33 3 22.5 Z" fill="#22331D"/>
          <circle cx="22" cy="22" r="21" fill="none" stroke="#EFEAD9" stroke-width="1.3" opacity="0.9"/>
        </svg>
        <span>MkulimaKe</span>
      </div>
      <p class="mk-footer-tag">A simple handbook for livestock and poultry records — built for the daily reality of running a small farm.</p>
    </div>
    <div class="mk-footer-col">
      <h4>Product</h4>
      <a href="#features">Features</a>
      <a href="#how">How it works</a>
      <a href="#app">Open the app</a>
    </div>
    <div class="mk-footer-col">
      <h4>Records</h4>
      <a href="#app">Livestock</a>
      <a href="#app">Poultry</a>
      <a href="#app">Health logs</a>
    </div>
    <div class="mk-footer-col">
      <h4>Farm</h4>
      <a href="#stories">Stories</a>
      <a href="#features">About the app</a>
    </div>
  </div>
  <div class="mk-footer-bottom">
    <span>© 2026 MkulimaKe. Built for the farm, not the office.</span>
    <span>Livestock &amp; Poultry Records</span>
  </div>
</footer>
