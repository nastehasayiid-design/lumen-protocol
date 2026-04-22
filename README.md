<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>Lumen · Human Intelligence for Startups</title>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,300;0,9..144,700;0,9..144,900;1,9..144,300;1,9..144,700&family=DM+Sans:ital,wght@0,300;0,400;0,500;0,600;1,400&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
<style>
*{margin:0;padding:0;box-sizing:border-box;-webkit-tap-highlight-color:transparent;}
:root{
  --black:#070604;
  --dark:#0e0b07;
  --dark2:#1a1508;
  --gold:#c8952a;
  --gold2:#e8b84b;
  --gold3:#f5d07a;
  --cream:#f7f3ec;
  --cream2:#ede6d6;
  --cream3:#ddd0b6;
  --tan:#9a7b52;
  --tan2:#6b5034;
  --white:#fdfaf5;
  --green:#2a5c3a;
  --green2:#dff0e6;
  --red:#8b1f1f;
  --r:14px;--r2:9px;--pill:999px;
  --sh:0 2px 16px rgba(7,6,4,0.08);
  --sh2:0 8px 28px rgba(7,6,4,0.13);
  --sh3:0 20px 50px rgba(7,6,4,0.2);
}
html,body{width:100%;height:100%;overflow-x:hidden;}
body{font-family:'DM Sans',sans-serif;background:var(--cream);color:var(--dark);overscroll-behavior:none;}

/* ─── SCREENS ─── */
.screen{display:none;width:100%;min-height:100vh;min-height:100svh;flex-direction:column;position:relative;}
.screen.active{display:flex;animation:fadeIn 0.35s ease both;}
@keyframes fadeIn{from{opacity:0;transform:translateY(8px);}to{opacity:1;transform:translateY(0);}}

/* ─── LANDING ─── */
#s-land{background:var(--black);overflow:hidden;}
.land-canvas{position:absolute;inset:0;pointer-events:none;}
.land-grid{position:absolute;inset:0;background-image:linear-gradient(rgba(200,149,42,0.04) 1px,transparent 1px),linear-gradient(90deg,rgba(200,149,42,0.04) 1px,transparent 1px);background-size:56px 56px;}
.land-g1{position:absolute;width:700px;height:700px;background:radial-gradient(circle,rgba(200,149,42,0.16) 0%,transparent 65%);top:-200px;left:-180px;animation:breathe 9s ease-in-out infinite;}
.land-g2{position:absolute;width:450px;height:450px;background:radial-gradient(circle,rgba(200,149,42,0.1) 0%,transparent 65%);bottom:-100px;right:-100px;animation:breathe 7s ease-in-out infinite reverse;}
.land-g3{position:absolute;width:280px;height:280px;background:radial-gradient(circle,rgba(200,149,42,0.06) 0%,transparent 65%);top:55%;left:58%;animation:breathe 11s ease-in-out infinite 2s;}
@keyframes breathe{0%,100%{transform:scale(1);}50%{transform:scale(1.18);}}
.land-scan{position:absolute;height:1px;width:100%;background:linear-gradient(90deg,transparent,rgba(200,149,42,0.12),transparent);animation:scan 6s linear infinite;}
.land-scan:nth-child(2){top:22%;animation-delay:0s;}
.land-scan:nth-child(3){top:48%;animation-delay:2.5s;}
.land-scan:nth-child(4){top:74%;animation-delay:5s;}
@keyframes scan{0%{transform:translateX(-100%);}100%{transform:translateX(100%);}}

.land-inner{position:relative;z-index:2;display:flex;flex-direction:column;align-items:center;justify-content:center;min-height:100vh;min-height:100svh;padding:2.5rem 1.5rem;text-align:center;}
.land-pill{display:inline-flex;align-items:center;gap:0.55rem;border:1px solid rgba(200,149,42,0.32);border-radius:var(--pill);padding:0.42rem 1.2rem;font-size:0.7rem;font-weight:700;color:var(--gold2);letter-spacing:0.17em;text-transform:uppercase;margin-bottom:2.2rem;animation:ri 0.9s ease both;position:relative;overflow:hidden;}
.land-pill::after{content:'';position:absolute;inset:0;background:linear-gradient(90deg,transparent,rgba(200,149,42,0.1),transparent);animation:shim 3.5s linear infinite;}
@keyframes shim{0%{transform:translateX(-120%);}100%{transform:translateX(120%);}}
.pill-dot{width:5px;height:5px;background:var(--gold2);border-radius:50%;animation:blink 2s ease infinite;}
@keyframes blink{0%,100%{opacity:1;}50%{opacity:0.25;}}
.land-h{font-family:'Fraunces',serif;font-size:clamp(3.8rem,12vw,8rem);font-weight:900;line-height:0.9;letter-spacing:-0.045em;color:#fff;margin-bottom:0.15em;animation:ri 0.9s ease 0.1s both;}
.land-h .gd{color:var(--gold);font-style:italic;}
.land-h .out{-webkit-text-stroke:1.5px rgba(255,255,255,0.22);color:transparent;}
.land-tag{font-family:'Fraunces',serif;font-style:italic;font-size:clamp(0.95rem,2.8vw,1.45rem);color:rgba(255,255,255,0.32);margin-bottom:1.3rem;animation:ri 0.9s ease 0.2s both;font-weight:300;}
.land-desc{font-size:clamp(0.87rem,1.8vw,1rem);color:rgba(255,255,255,0.42);line-height:1.8;max-width:540px;margin:0 auto 2.8rem;animation:ri 0.9s ease 0.3s both;}
.land-desc strong{color:rgba(255,255,255,0.72);font-weight:500;}
.land-btns{display:flex;gap:0.75rem;justify-content:center;flex-wrap:wrap;margin-bottom:1.6rem;animation:ri 0.9s ease 0.4s both;}
.btn-gl{background:var(--gold);color:var(--black);font-family:'DM Sans',sans-serif;font-weight:700;font-size:0.95rem;border:none;border-radius:var(--pill);padding:1rem 2.5rem;cursor:pointer;transition:all 0.22s;display:inline-flex;align-items:center;gap:0.5rem;position:relative;overflow:hidden;}
.btn-gl:hover{background:var(--gold2);transform:translateY(-2px);box-shadow:0 10px 28px rgba(200,149,42,0.38);}
.btn-gh{background:transparent;color:rgba(255,255,255,0.55);font-family:'DM Sans',sans-serif;font-weight:500;font-size:0.95rem;border:1px solid rgba(255,255,255,0.14);border-radius:var(--pill);padding:1rem 1.9rem;cursor:pointer;transition:all 0.22s;display:inline-flex;align-items:center;gap:0.5rem;}
.btn-gh:hover{border-color:rgba(200,149,42,0.5);color:var(--gold2);}
.land-proof{display:flex;gap:2rem;justify-content:center;flex-wrap:wrap;animation:ri 0.9s ease 0.5s both;}
.proof-i{display:flex;align-items:center;gap:0.4rem;color:rgba(255,255,255,0.26);font-size:0.76rem;}
.proof-i i{color:var(--gold);font-size:0.7rem;}
.land-demo-label{position:absolute;bottom:1.6rem;left:50%;transform:translateX(-50%);color:rgba(255,255,255,0.2);font-size:0.68rem;letter-spacing:0.14em;text-transform:uppercase;animation:ri 1s ease 0.7s both;}
@keyframes ri{from{opacity:0;transform:translateY(20px);}to{opacity:1;transform:translateY(0);}}

/* ─── DEMO SELECTOR ─── */
#s-demo{background:var(--cream);align-items:center;justify-content:center;padding:2rem 1rem;}
.demo-card{background:var(--white);border:1px solid var(--cream3);border-radius:var(--r);box-shadow:var(--sh);max-width:680px;width:100%;padding:2.5rem;}
.demo-ew{font-size:0.67rem;font-weight:700;text-transform:uppercase;letter-spacing:0.17em;color:var(--tan);margin-bottom:0.5rem;}
.demo-title{font-family:'Fraunces',serif;font-size:1.85rem;font-weight:700;color:var(--dark);line-height:1.15;margin-bottom:0.45rem;}
.demo-sub{font-size:0.88rem;color:var(--tan);line-height:1.65;margin-bottom:2rem;}
.demo-grid{display:grid;grid-template-columns:1fr 1fr;gap:1rem;margin-bottom:1.5rem;}
@media(max-width:480px){.demo-grid{grid-template-columns:1fr;}}
.demo-choice{border:2px solid var(--cream3);border-radius:var(--r);padding:1.7rem 1.3rem;cursor:pointer;transition:all 0.22s;background:var(--cream);position:relative;}
.demo-choice:hover{border-color:rgba(200,149,42,0.5);transform:translateY(-3px);box-shadow:var(--sh2);}
.demo-choice.sel{border-color:var(--gold);background:linear-gradient(135deg,#fffdf5,#fef8e5);box-shadow:0 0 0 3px rgba(200,149,42,0.1);}
.dc-check{position:absolute;top:0.85rem;right:0.85rem;width:21px;height:21px;background:var(--gold);border-radius:50%;display:flex;align-items:center;justify-content:center;color:#fff;font-size:0.58rem;opacity:0;transform:scale(0) rotate(-60deg);transition:0.22s;}
.demo-choice.sel .dc-check{opacity:1;transform:scale(1) rotate(0deg);}
.dc-ico{width:46px;height:46px;border-radius:var(--r2);display:flex;align-items:center;justify-content:center;font-size:1.2rem;margin-bottom:0.9rem;}
.dc-ico.gold{background:linear-gradient(135deg,#fef3d0,#fde9a0);color:var(--gold);}
.dc-ico.slate{background:linear-gradient(135deg,#e8edf5,#d4dce8);color:#3a4a6b;}
.dc-h{font-family:'Fraunces',serif;font-weight:700;font-size:1rem;color:var(--dark);margin-bottom:0.3rem;}
.dc-p{font-size:0.8rem;color:var(--tan);line-height:1.5;}
.btn-cta{background:var(--dark);color:var(--cream);font-family:'DM Sans',sans-serif;font-weight:600;font-size:0.95rem;border:none;border-radius:var(--r2);padding:0.95rem 2rem;width:100%;cursor:pointer;transition:all 0.2s;display:flex;align-items:center;justify-content:center;gap:0.5rem;letter-spacing:0.01em;}
.btn-cta:hover{background:var(--dark2);transform:translateY(-1px);box-shadow:var(--sh);}
.btn-cta:disabled{opacity:0.45;pointer-events:none;}
.btn-cta.hidden{display:none;}

/* ─── NAV ─── */
.top-nav{background:rgba(247,243,236,0.96);backdrop-filter:blur(14px);border-bottom:1px solid var(--cream3);padding:0 1.5rem;height:62px;display:flex;align-items:center;justify-content:space-between;position:sticky;top:0;z-index:500;flex-shrink:0;}
.nav-logo{font-family:'Fraunces',serif;font-weight:900;font-size:1.55rem;color:var(--dark);letter-spacing:-0.03em;}
.nav-logo em{color:var(--gold);font-style:italic;}
.nav-right{display:flex;align-items:center;gap:0.8rem;}
.nav-step{font-size:0.7rem;font-weight:700;color:var(--tan);text-transform:uppercase;letter-spacing:0.1em;}
.prog-wrap{height:2px;background:var(--cream3);position:sticky;top:62px;z-index:499;flex-shrink:0;}
.prog-bar{height:100%;background:linear-gradient(90deg,var(--gold),var(--gold2));transition:width 0.55s cubic-bezier(0.4,0,0.2,1);position:relative;}
.prog-bar::after{content:'';position:absolute;right:-1px;top:50%;transform:translateY(-50%);width:6px;height:6px;background:var(--gold2);border-radius:50%;box-shadow:0 0 6px var(--gold2);}

/* ─── CARD WRAPPER ─── */
.pw{flex:1;display:flex;align-items:center;justify-content:center;padding:2rem 1rem;min-height:0;}
.pw-top{align-items:flex-start;padding-top:2rem;}
.card{background:var(--white);border:1px solid var(--cream3);border-radius:var(--r);box-shadow:var(--sh);}
.c-sm{max-width:460px;width:100%;padding:2.2rem 1.8rem;}
.c-md{max-width:560px;width:100%;padding:2.2rem 1.8rem;}
.c-lg{max-width:700px;width:100%;padding:2.2rem 1.8rem;}
.ew{font-size:0.66rem;font-weight:700;text-transform:uppercase;letter-spacing:0.18em;color:var(--tan);margin-bottom:0.4rem;}
.ct{font-family:'Fraunces',serif;font-size:1.85rem;font-weight:700;color:var(--dark);line-height:1.12;margin-bottom:0.4rem;}
.cs{font-size:0.88rem;color:var(--tan);line-height:1.65;margin-bottom:1.8rem;}
.back-btn{display:inline-flex;align-items:center;gap:0.4rem;font-size:0.82rem;color:var(--tan);cursor:pointer;background:none;border:none;font-family:'DM Sans',sans-serif;margin-bottom:1.3rem;transition:0.18s;}
.back-btn:hover{color:var(--gold);}

/* ─── FORM ─── */
.field{margin-bottom:1rem;}
.field label{display:block;font-size:0.68rem;font-weight:700;text-transform:uppercase;letter-spacing:0.1em;color:var(--dark);margin-bottom:0.35rem;opacity:0.65;}
.field input,.field select,.field textarea{width:100%;padding:0.82rem 1rem;border:1.5px solid var(--cream3);border-radius:var(--r2);font-size:0.92rem;font-family:'DM Sans',sans-serif;background:var(--cream);color:var(--dark);outline:none;transition:0.2s;-webkit-appearance:none;}
.field input:focus,.field select:focus,.field textarea:focus{border-color:var(--gold);background:var(--white);box-shadow:0 0 0 3px rgba(200,149,42,0.08);}
.field textarea{resize:vertical;min-height:80px;line-height:1.6;}
.frow{display:grid;grid-template-columns:1fr 1fr;gap:0.8rem;}
@media(max-width:440px){.frow{grid-template-columns:1fr;}}
.form-err{background:#fff2f2;border:1px solid #fecaca;border-radius:var(--r2);padding:0.72rem 1rem;font-size:0.82rem;color:var(--red);margin-bottom:1rem;display:none;}
.form-err.show{display:block;}
.btn-outline{background:transparent;color:var(--tan2);border:1.5px solid var(--cream3);border-radius:var(--r2);padding:0.85rem 1.5rem;width:100%;cursor:pointer;transition:all 0.2s;display:flex;align-items:center;justify-content:center;gap:0.5rem;font-family:'DM Sans',sans-serif;font-weight:600;font-size:0.92rem;margin-top:0.5rem;}
.btn-outline:hover{border-color:var(--gold);color:var(--gold);}

/* ─── ROLE CHOOSER ─── */
.role-grid{display:grid;grid-template-columns:1fr 1fr;gap:1rem;margin-bottom:1.8rem;}
@media(max-width:460px){.role-grid{grid-template-columns:1fr;}}
.rc{border:2px solid var(--cream3);border-radius:var(--r);padding:1.7rem 1.3rem;cursor:pointer;transition:all 0.22s;background:var(--cream);position:relative;}
.rc:hover{border-color:rgba(200,149,42,0.5);transform:translateY(-3px);box-shadow:var(--sh2);}
.rc.sel{border-color:var(--gold);background:linear-gradient(135deg,#fffdf5,#fef8e5);box-shadow:0 0 0 3px rgba(200,149,42,0.1);}
.rc-check{position:absolute;top:0.85rem;right:0.85rem;width:21px;height:21px;background:var(--gold);border-radius:50%;display:flex;align-items:center;justify-content:center;color:#fff;font-size:0.58rem;opacity:0;transform:scale(0);transition:0.22s;}
.rc.sel .rc-check{opacity:1;transform:scale(1);}
.rc-ico{width:44px;height:44px;border-radius:var(--r2);display:flex;align-items:center;justify-content:center;font-size:1.15rem;margin-bottom:0.85rem;}
.ico-gold{background:linear-gradient(135deg,#fef3d0,#fde9a0);color:var(--gold);}
.ico-dark{background:linear-gradient(135deg,#e8edf5,#d4dce8);color:#3a4a6b;}
.rc-h{font-family:'Fraunces',serif;font-weight:700;font-size:0.98rem;color:var(--dark);margin-bottom:0.3rem;}
.rc-p{font-size:0.79rem;color:var(--tan);line-height:1.5;}

/* ─── CLASS INPUT ─── */
.class-area{background:var(--cream);border:1.5px solid var(--cream3);border-radius:var(--r);padding:1.3rem;margin-bottom:1.2rem;}
.class-row{display:flex;gap:0.6rem;margin-bottom:0.85rem;}
.class-row input{flex:1;padding:0.72rem 0.9rem;border:1.5px solid var(--cream3);border-radius:var(--r2);font-family:'DM Sans',sans-serif;font-size:0.88rem;background:var(--white);outline:none;transition:0.2s;min-width:0;}
.class-row input:focus{border-color:var(--gold);box-shadow:0 0 0 3px rgba(200,149,42,0.08);}
.add-btn{background:var(--dark);color:var(--cream);border:none;border-radius:var(--r2);padding:0.72rem 1.1rem;font-size:0.8rem;font-weight:600;cursor:pointer;white-space:nowrap;font-family:'DM Sans',sans-serif;transition:0.2s;display:flex;align-items:center;gap:0.35rem;flex-shrink:0;}
.add-btn:hover{background:var(--gold);color:var(--dark);}
.tags-wrap{display:flex;flex-wrap:wrap;gap:0.4rem;min-height:30px;}
.ctag{display:inline-flex;align-items:center;gap:0.35rem;background:var(--white);border:1px solid var(--cream3);border-radius:var(--pill);padding:0.27rem 0.8rem;font-size:0.76rem;font-weight:500;color:var(--dark2);animation:pop 0.2s cubic-bezier(0.34,1.56,0.64,1) both;}
@keyframes pop{from{opacity:0;transform:scale(0.7);}to{opacity:1;transform:scale(1);}}
.ctag button{background:none;border:none;cursor:pointer;color:var(--tan);font-size:0.6rem;line-height:1;}
.class-hint{font-size:0.72rem;color:var(--tan);margin-top:0.45rem;font-style:italic;}
.ins-box{background:linear-gradient(135deg,var(--dark) 0%,#1a1306 100%);border-radius:var(--r);padding:1.4rem;margin-bottom:1.3rem;border:1px solid rgba(200,149,42,0.15);}
.ins-hdr{font-size:0.66rem;font-weight:700;text-transform:uppercase;letter-spacing:0.14em;color:var(--gold2);margin-bottom:0.85rem;display:flex;align-items:center;gap:0.45rem;}
.ins-chips{display:flex;flex-wrap:wrap;gap:0.45rem;}
.ins-chip{background:rgba(200,149,42,0.1);border:1px solid rgba(200,149,42,0.2);border-radius:var(--pill);padding:0.25rem 0.75rem;font-size:0.72rem;color:var(--gold2);font-weight:500;display:flex;align-items:center;gap:0.3rem;animation:pop 0.3s cubic-bezier(0.34,1.56,0.64,1) both;}
.ins-empty{font-size:0.79rem;color:rgba(255,255,255,0.2);font-style:italic;}

/* ─── VALUES ─── */
.vgrid{display:grid;grid-template-columns:repeat(3,1fr);gap:0.65rem;margin-bottom:1.2rem;}
@media(max-width:420px){.vgrid{grid-template-columns:repeat(2,1fr);}}
.vchip{border:1.5px solid var(--cream3);border-radius:var(--r2);padding:0.9rem 0.5rem;text-align:center;cursor:pointer;transition:all 0.18s;background:var(--cream);}
.vchip:hover{border-color:rgba(200,149,42,0.5);}
.vchip.sel{background:var(--dark);border-color:var(--dark);color:var(--gold2);}
.vi{font-size:1.35rem;margin-bottom:0.22rem;display:block;}
.vn{font-size:0.7rem;font-weight:600;}
.vcbar{display:flex;align-items:center;justify-content:space-between;margin-bottom:1rem;}
.vctxt{font-size:0.79rem;color:var(--tan);}
.vctxt strong{color:var(--gold);}
.vdots{display:flex;gap:0.35rem;}
.vdot{width:7px;height:7px;border-radius:50%;background:var(--cream3);transition:all 0.28s;}
.vdot.on{background:var(--gold);box-shadow:0 0 5px rgba(200,149,42,0.5);}

/* ─── DASHBOARD ─── */
#s-dash{background:var(--cream);min-height:100vh;min-height:100svh;}
.dash-nav{background:var(--white);border-bottom:1px solid var(--cream3);padding:0 1.3rem;height:60px;display:flex;align-items:center;justify-content:space-between;position:sticky;top:0;z-index:200;box-shadow:var(--sh);flex-shrink:0;}
.dash-logo{font-family:'Fraunces',serif;font-weight:900;font-size:1.45rem;color:var(--dark);}
.dash-logo em{color:var(--gold);font-style:italic;}
.dash-user{display:flex;align-items:center;gap:0.7rem;cursor:pointer;}
.dash-uname{font-size:0.82rem;font-weight:600;color:var(--dark2);}
.ava{width:35px;height:35px;border-radius:50%;background:linear-gradient(135deg,var(--gold),var(--gold2));display:flex;align-items:center;justify-content:center;font-weight:700;color:var(--black);font-size:0.82rem;font-family:'Fraunces',serif;flex-shrink:0;}
.dash-wrap{display:grid;grid-template-columns:240px 1fr;min-height:calc(100vh - 60px);min-height:calc(100svh - 60px);}
@media(max-width:768px){.dash-wrap{grid-template-columns:1fr;}.dash-side{display:none!important;}.mobile-nav{display:flex!important;}}
.dash-side{background:var(--white);border-right:1px solid var(--cream3);padding:1.5rem 0.85rem;display:flex;flex-direction:column;gap:1.2rem;}
.side-lbl{font-size:0.62rem;font-weight:700;text-transform:uppercase;letter-spacing:0.17em;color:var(--tan);padding:0 0.6rem;margin-bottom:0.4rem;}
.si{display:flex;align-items:center;gap:0.6rem;padding:0.55rem 0.75rem;border-radius:var(--r2);font-size:0.84rem;font-weight:500;color:var(--tan2);cursor:pointer;transition:0.14s;position:relative;}
.si i{width:15px;text-align:center;font-size:0.8rem;}
.si:hover{background:var(--cream);color:var(--dark);}
.si.active{background:var(--dark);color:var(--gold2);}
.si .badge{margin-left:auto;background:var(--gold);color:var(--black);border-radius:var(--pill);font-size:0.6rem;font-weight:700;padding:0.1rem 0.45rem;min-width:16px;text-align:center;}
.vet-card{background:linear-gradient(135deg,var(--dark),#1a1306);border-radius:var(--r);padding:1.2rem;border:1px solid rgba(200,149,42,0.15);}
.vet-lbl{font-size:0.62rem;font-weight:700;text-transform:uppercase;letter-spacing:0.12em;color:rgba(255,255,255,0.3);margin-bottom:0.6rem;}
.vet-badge{display:inline-flex;align-items:center;gap:0.38rem;background:rgba(200,149,42,0.12);border:1px solid rgba(200,149,42,0.24);border-radius:var(--pill);padding:0.2rem 0.7rem;font-size:0.7rem;color:var(--gold2);font-weight:600;margin-bottom:0.85rem;}
.vet-dot{width:5px;height:5px;background:var(--gold2);border-radius:50%;animation:blink 1.5s ease infinite;}
.vet-steps{list-style:none;display:flex;flex-direction:column;gap:0.42rem;}
.vs{display:flex;align-items:center;gap:0.5rem;font-size:0.75rem;color:rgba(255,255,255,0.35);}
.vs.done{color:#6ee87a;}
.vs.cur{color:var(--gold2);}
.vs i{font-size:0.62rem;width:12px;}
.logout-btn{display:flex;align-items:center;gap:0.6rem;padding:0.55rem 0.75rem;border-radius:var(--r2);font-size:0.82rem;font-weight:500;color:var(--tan);cursor:pointer;transition:0.15s;background:none;border:none;font-family:'DM Sans',sans-serif;width:100%;margin-top:auto;}
.logout-btn:hover{background:var(--cream);color:var(--red);}
.dash-main{padding:1.8rem 2rem;overflow-y:auto;}
@media(max-width:640px){.dash-main{padding:1.3rem 1rem 6rem;}}

/* ─── PANELS ─── */
.panel{display:none;}
.panel.active{display:block;animation:fadeIn 0.3s ease both;}
.welcome-bar{margin-bottom:1.7rem;}
.welcome-bar h1{font-family:'Fraunces',serif;font-size:1.85rem;font-weight:700;color:var(--dark);margin-bottom:0.2rem;}
.welcome-bar p{color:var(--tan);font-size:0.87rem;}
.val-banner{background:linear-gradient(135deg,var(--dark) 0%,#251a06 100%);border-radius:var(--r);padding:1.6rem;margin-bottom:1.7rem;display:flex;gap:1.5rem;align-items:flex-start;flex-wrap:wrap;border:1px solid rgba(200,149,42,0.15);position:relative;overflow:hidden;}
.val-banner::before{content:'';position:absolute;top:-60%;right:-8%;width:260px;height:260px;background:radial-gradient(circle,rgba(200,149,42,0.07),transparent 70%);border-radius:50%;pointer-events:none;}
.vb-left{flex:1;min-width:160px;position:relative;}
.vb-lbl{font-size:0.64rem;font-weight:700;text-transform:uppercase;letter-spacing:0.13em;color:var(--gold2);margin-bottom:0.45rem;display:flex;align-items:center;gap:0.4rem;}
.vb-title{font-family:'Fraunces',serif;font-size:1rem;color:var(--white);margin-bottom:0.7rem;}
.vb-skills{display:flex;flex-wrap:wrap;gap:0.35rem;}
.vb-skill{background:rgba(200,149,42,0.1);border:1px solid rgba(200,149,42,0.2);border-radius:var(--pill);padding:0.22rem 0.68rem;font-size:0.7rem;color:var(--gold2);font-weight:500;display:flex;align-items:center;gap:0.28rem;}
.vb-right{text-align:right;flex-shrink:0;}
.vb-score{font-family:'Fraunces',serif;font-size:2.9rem;font-weight:900;color:var(--gold);line-height:1;}
.vb-score-lbl{font-size:0.69rem;color:rgba(255,255,255,0.3);margin-top:0.1rem;}
.stats-row{display:grid;grid-template-columns:repeat(3,1fr);gap:0.75rem;margin-bottom:1.7rem;}
@media(max-width:500px){.stats-row{grid-template-columns:1fr 1fr;}}
.stat-box{background:var(--white);border:1px solid var(--cream3);border-radius:var(--r);padding:1.15rem;}
.stat-box .s-lbl{font-size:0.64rem;font-weight:700;text-transform:uppercase;letter-spacing:0.09em;color:var(--tan);margin-bottom:0.32rem;}
.stat-box .s-val{font-family:'Fraunces',serif;font-size:2.1rem;font-weight:700;color:var(--dark);line-height:1;}
.stat-box .s-sub{font-size:0.72rem;color:var(--green);margin-top:0.18rem;}
.sec-hdr{display:flex;align-items:center;justify-content:space-between;margin-bottom:0.85rem;}
.sec-hdr h2{font-family:'Fraunces',serif;font-size:1.2rem;font-weight:700;color:var(--dark);}
.sec-hdr button{background:none;border:none;font-size:0.78rem;color:var(--gold);font-weight:600;cursor:pointer;font-family:'DM Sans',sans-serif;}

/* ─── STARTUP CARDS ─── */
.startup-list{display:flex;flex-direction:column;gap:0.85rem;}
.sup-card{background:var(--white);border:1px solid var(--cream3);border-radius:var(--r);padding:1.3rem;display:flex;gap:1.1rem;align-items:flex-start;transition:all 0.2s;}
.sup-card:hover{box-shadow:var(--sh2);border-color:rgba(200,149,42,0.25);transform:translateY(-1px);}
.sup-logo{width:50px;height:50px;border-radius:var(--r2);display:flex;align-items:center;justify-content:center;font-size:1.35rem;flex-shrink:0;}
.sup-info{flex:1;min-width:0;}
.sup-top{display:flex;align-items:center;gap:0.6rem;margin-bottom:0.18rem;flex-wrap:wrap;}
.sup-name{font-family:'Fraunces',serif;font-weight:700;font-size:0.97rem;color:var(--dark);}
.sup-pct{background:var(--green2);color:var(--green);border-radius:var(--pill);padding:0.13rem 0.55rem;font-size:0.67rem;font-weight:700;}
.sup-meta{font-size:0.74rem;color:var(--tan);margin-bottom:0.45rem;}
.sup-role{font-size:0.75rem;color:var(--dark2);font-weight:500;margin-bottom:0.55rem;}
.sup-role i{color:var(--gold);margin-right:3px;}
.sup-tags{display:flex;gap:0.3rem;flex-wrap:wrap;margin-bottom:0.6rem;}
.tag{background:var(--cream2);color:var(--tan2);border-radius:var(--pill);padding:0.13rem 0.52rem;font-size:0.65rem;font-weight:600;}
.tag.m{background:var(--green2);color:var(--green);}
.sup-why{font-size:0.73rem;color:var(--tan);font-style:italic;margin-bottom:0.65rem;line-height:1.5;}
.sup-acts{display:flex;gap:0.42rem;flex-wrap:wrap;}
.btn-sp{background:var(--dark);color:var(--cream);border:none;border-radius:var(--pill);padding:0.4rem 1rem;font-size:0.72rem;font-weight:600;cursor:pointer;font-family:'DM Sans',sans-serif;transition:0.18s;}
.btn-sp:hover{background:var(--gold);color:var(--dark);}
.btn-so{background:transparent;color:var(--tan2);border:1.5px solid var(--cream3);border-radius:var(--pill);padding:0.4rem 1rem;font-size:0.72rem;font-weight:600;cursor:pointer;font-family:'DM Sans',sans-serif;transition:0.18s;}
.btn-so:hover{border-color:var(--gold);color:var(--gold);}
.btn-sc{background:var(--gold);color:var(--dark);border:none;border-radius:var(--pill);padding:0.4rem 1rem;font-size:0.72rem;font-weight:700;cursor:pointer;font-family:'DM Sans',sans-serif;transition:0.18s;}
.btn-sc:hover{background:var(--gold2);}
.btn-sc.connected{background:var(--green2);color:var(--green);cursor:default;}

/* ─── MATCH FILTERS ─── */
.match-filters{display:flex;gap:0.42rem;flex-wrap:wrap;margin-bottom:1.2rem;}
.mf-btn{background:var(--cream2);color:var(--tan2);border:1px solid var(--cream3);border-radius:var(--pill);padding:0.36rem 0.9rem;font-size:0.74rem;font-weight:600;cursor:pointer;font-family:'DM Sans',sans-serif;transition:0.18s;}
.mf-btn.active{background:var(--dark);color:var(--gold2);border-color:var(--dark);}

/* ─── CANDIDATE CARDS (startup view) ─── */
.cand-list{display:flex;flex-direction:column;gap:0.85rem;}
.cand-card{background:var(--white);border:1px solid var(--cream3);border-radius:var(--r);padding:1.3rem;display:flex;gap:1rem;align-items:flex-start;transition:all 0.2s;}
.cand-card:hover{box-shadow:var(--sh2);transform:translateY(-1px);}
.cand-ava{width:48px;height:48px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-family:'Fraunces',serif;font-size:1.3rem;font-weight:900;color:var(--black);flex-shrink:0;}
.cand-info{flex:1;min-width:0;}
.cand-top{display:flex;align-items:center;gap:0.6rem;margin-bottom:0.18rem;flex-wrap:wrap;}
.cand-name{font-family:'Fraunces',serif;font-weight:700;font-size:0.97rem;color:var(--dark);}
.cand-pct{background:var(--green2);color:var(--green);border-radius:var(--pill);padding:0.13rem 0.55rem;font-size:0.67rem;font-weight:700;}
.cand-meta{font-size:0.74rem;color:var(--tan);margin-bottom:0.45rem;}
.cand-skills{display:flex;gap:0.3rem;flex-wrap:wrap;margin-bottom:0.6rem;}
.cand-skill{background:var(--cream2);color:var(--tan2);border-radius:var(--pill);padding:0.13rem 0.52rem;font-size:0.65rem;font-weight:600;}
.cand-skill.m{background:linear-gradient(135deg,#fef3d0,#fde9a0);color:var(--gold);}
.cand-why{font-size:0.73rem;color:var(--tan);font-style:italic;margin-bottom:0.65rem;line-height:1.5;}
.cand-acts{display:flex;gap:0.42rem;flex-wrap:wrap;}

/* ─── MESSAGES ─── */
.msg-layout{border:1px solid var(--cream3);border-radius:var(--r);overflow:hidden;background:var(--white);}
@media(min-width:600px){.msg-layout{display:grid;grid-template-columns:230px 1fr;height:480px;}}
.msg-sidebar{border-right:1px solid var(--cream3);overflow-y:auto;}
@media(max-width:599px){.msg-sidebar{max-height:180px;border-right:none;border-bottom:1px solid var(--cream3);}}
.msg-sidebar-hdr{padding:0.85rem 1.1rem;border-bottom:1px solid var(--cream3);font-family:'Fraunces',serif;font-weight:700;font-size:0.9rem;color:var(--dark);}
.msg-thread{display:flex;align-items:center;gap:0.6rem;padding:0.82rem 1.1rem;cursor:pointer;transition:0.14s;border-bottom:1px solid var(--cream3);}
.msg-thread:hover{background:var(--cream);}
.msg-thread.active{background:var(--cream2);}
.msg-thread-ico{width:34px;height:34px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:0.95rem;flex-shrink:0;}
.msg-thread-info{flex:1;min-width:0;}
.msg-thread-name{font-weight:600;font-size:0.81rem;color:var(--dark);}
.msg-thread-preview{font-size:0.72rem;color:var(--tan);white-space:nowrap;overflow:hidden;text-overflow:ellipsis;}
.msg-thread-time{font-size:0.64rem;color:var(--tan);flex-shrink:0;}
.msg-main{display:flex;flex-direction:column;}
.msg-header{padding:0.85rem 1.2rem;border-bottom:1px solid var(--cream3);display:flex;align-items:center;gap:0.7rem;}
.msg-header-ico{width:32px;height:32px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:0.9rem;}
.msg-header-name{font-weight:700;font-size:0.88rem;color:var(--dark);}
.msg-header-sub{font-size:0.7rem;color:var(--tan);}
.msg-body{flex:1;overflow-y:auto;padding:1rem 1.2rem;display:flex;flex-direction:column;gap:0.65rem;min-height:120px;}
.msg-bubble{max-width:78%;padding:0.62rem 0.9rem;border-radius:14px;font-size:0.83rem;line-height:1.55;}
.msg-bubble.them{background:var(--cream2);color:var(--dark2);border-bottom-left-radius:3px;align-self:flex-start;}
.msg-bubble.me{background:var(--dark);color:var(--cream);border-bottom-right-radius:3px;align-self:flex-end;}
.msg-input-row{padding:0.85rem 1.2rem;border-top:1px solid var(--cream3);display:flex;gap:0.55rem;}
.msg-input{flex:1;padding:0.62rem 0.9rem;border:1.5px solid var(--cream3);border-radius:var(--pill);font-size:0.85rem;font-family:'DM Sans',sans-serif;outline:none;transition:0.2s;background:var(--cream);min-width:0;}
.msg-input:focus{border-color:var(--gold);background:var(--white);}
.msg-send{background:var(--dark);color:var(--cream);border:none;border-radius:50%;width:34px;height:34px;display:flex;align-items:center;justify-content:center;cursor:pointer;transition:0.18s;flex-shrink:0;}
.msg-send:hover{background:var(--gold);color:var(--dark);}
.msg-empty{display:flex;flex-direction:column;align-items:center;justify-content:center;flex:1;color:var(--tan);text-align:center;padding:2rem;}
.msg-empty i{font-size:1.8rem;margin-bottom:0.7rem;color:var(--cream3);}
.msg-empty p{font-size:0.8rem;}

/* ─── PROFILE PANEL ─── */
.profile-card{background:var(--white);border:1px solid var(--cream3);border-radius:var(--r);padding:1.7rem;margin-bottom:1rem;}
.profile-grid{display:grid;grid-template-columns:1fr 1fr;gap:0.9rem;margin-top:0.8rem;}
@media(max-width:400px){.profile-grid{grid-template-columns:1fr;}}
.pf-lbl{font-size:0.64rem;font-weight:700;text-transform:uppercase;letter-spacing:0.09em;color:var(--tan);margin-bottom:0.22rem;}
.pf-val{font-weight:600;font-size:0.9rem;color:var(--dark);}
.modal-pills{display:flex;flex-wrap:wrap;gap:0.35rem;}
.modal-pill{background:var(--cream2);color:var(--tan2);border-radius:var(--pill);padding:0.22rem 0.65rem;font-size:0.73rem;font-weight:600;}
.modal-pill.gold{background:linear-gradient(135deg,#fef3d0,#fde9a0);color:var(--gold);}

/* ─── STARTUP DASH ─── */
#s-startup-dash{background:var(--cream);}
.startup-dash-header{background:linear-gradient(135deg,var(--dark),#2a1a05);padding:2rem;border-radius:var(--r);margin-bottom:1.5rem;border:1px solid rgba(200,149,42,0.15);position:relative;overflow:hidden;}
.startup-dash-header::before{content:'';position:absolute;top:-40%;right:-5%;width:240px;height:240px;background:radial-gradient(circle,rgba(200,149,42,0.08),transparent 70%);border-radius:50%;}
.sdh-label{font-size:0.64rem;font-weight:700;text-transform:uppercase;letter-spacing:0.14em;color:var(--gold2);margin-bottom:0.5rem;}
.sdh-title{font-family:'Fraunces',serif;font-size:1.4rem;color:#fff;margin-bottom:0.35rem;}
.sdh-sub{font-size:0.83rem;color:rgba(255,255,255,0.45);}
.sdh-stats{display:flex;gap:1.5rem;margin-top:1.2rem;flex-wrap:wrap;}
.sdh-stat .n{font-family:'Fraunces',serif;font-size:2rem;font-weight:900;color:var(--gold);line-height:1;}
.sdh-stat .l{font-size:0.69rem;color:rgba(255,255,255,0.3);margin-top:0.1rem;}

/* ─── MODAL ─── */
.modal-overlay{position:fixed;inset:0;background:rgba(7,6,4,0.68);z-index:1000;display:flex;align-items:flex-end;justify-content:center;backdrop-filter:blur(4px);}
@media(min-width:600px){.modal-overlay{align-items:center;padding:2rem;}}
.modal-overlay.hidden{display:none!important;}
.modal-box{background:var(--white);border-radius:var(--r) var(--r) 0 0;width:100%;max-height:88vh;overflow-y:auto;box-shadow:var(--sh3);animation:slideUp 0.3s cubic-bezier(0.34,1.1,0.64,1) both;}
@media(min-width:600px){.modal-box{max-width:600px;border-radius:var(--r);animation:modalIn 0.3s cubic-bezier(0.34,1.1,0.64,1) both;}}
@keyframes slideUp{from{transform:translateY(100%);}to{transform:translateY(0);}}
@keyframes modalIn{from{opacity:0;transform:scale(0.94) translateY(14px);}to{opacity:1;transform:scale(1) translateY(0);}}
.modal-handle{width:34px;height:4px;background:var(--cream3);border-radius:var(--pill);margin:0.85rem auto 0;}
@media(min-width:600px){.modal-handle{display:none;}}
.modal-header{padding:1.4rem 1.5rem 0.9rem;border-bottom:1px solid var(--cream3);display:flex;align-items:flex-start;justify-content:space-between;gap:1rem;}
.modal-close{background:var(--cream2);border:none;width:28px;height:28px;border-radius:50%;cursor:pointer;display:flex;align-items:center;justify-content:center;font-size:0.78rem;color:var(--tan2);transition:0.18s;flex-shrink:0;}
.modal-close:hover{background:var(--dark);color:var(--cream);}
.modal-body{padding:1.2rem 1.5rem 1.5rem;}
.modal-section{margin-bottom:1.2rem;}
.modal-sec-title{font-family:'Fraunces',serif;font-size:0.9rem;font-weight:700;color:var(--dark);margin-bottom:0.55rem;display:flex;align-items:center;gap:0.38rem;}
.modal-sec-title i{color:var(--gold);font-size:0.8rem;}
.modal-text{font-size:0.85rem;color:var(--tan2);line-height:1.65;}
.modal-footer{padding:0.9rem 1.5rem 1.2rem;border-top:1px solid var(--cream3);display:flex;gap:0.55rem;flex-wrap:wrap;}
.btn-modal-primary{background:var(--dark);color:var(--cream);border:none;border-radius:var(--r2);padding:0.7rem 1.5rem;font-size:0.85rem;font-weight:600;cursor:pointer;font-family:'DM Sans',sans-serif;transition:0.18s;}
.btn-modal-primary:hover{background:var(--gold);color:var(--dark);}
.btn-modal-outline{background:transparent;color:var(--tan2);border:1.5px solid var(--cream3);border-radius:var(--r2);padding:0.7rem 1.3rem;font-size:0.85rem;font-weight:600;cursor:pointer;font-family:'DM Sans',sans-serif;transition:0.18s;}
.btn-modal-outline:hover{border-color:var(--gold);color:var(--gold);}

/* ─── PENDING SCREEN ─── */
#s-pending{background:var(--dark);align-items:center;justify-content:center;text-align:center;padding:2rem;}
.pend-wrap{max-width:500px;width:100%;}
.pend-ico{width:80px;height:80px;background:rgba(200,149,42,0.1);border:1.5px solid rgba(200,149,42,0.28);border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:2rem;color:var(--gold);margin:0 auto 1.5rem;animation:pulseGlow 2s ease infinite;}
@keyframes pulseGlow{0%,100%{box-shadow:0 0 0 0 rgba(200,149,42,0.28);}50%{box-shadow:0 0 0 16px rgba(200,149,42,0);}}
.pend-wrap h2{font-family:'Fraunces',serif;font-size:2.3rem;color:var(--white);margin-bottom:0.55rem;}
.pend-wrap>p{color:rgba(255,255,255,0.38);font-size:0.89rem;line-height:1.72;margin-bottom:1.7rem;}
.pend-steps{background:rgba(255,255,255,0.04);border:1px solid rgba(255,255,255,0.06);border-radius:var(--r);overflow:hidden;margin-bottom:1.7rem;text-align:left;}
.pstep{display:flex;align-items:flex-start;gap:0.9rem;padding:1.05rem 1.3rem;border-bottom:1px solid rgba(255,255,255,0.04);}
.pstep:last-child{border-bottom:none;}
.pstep-n{width:25px;height:25px;background:var(--gold);border-radius:50%;color:var(--dark);font-size:0.68rem;font-weight:700;display:flex;align-items:center;justify-content:center;flex-shrink:0;margin-top:2px;}
.pstep-t strong{color:var(--white);display:block;font-size:0.85rem;margin-bottom:0.1rem;}
.pstep-t p{color:rgba(255,255,255,0.34);font-size:0.77rem;line-height:1.5;}

/* ─── MOBILE NAV ─── */
.mobile-nav{display:none;position:fixed;bottom:0;left:0;right:0;background:var(--white);border-top:1px solid var(--cream3);z-index:300;padding:0.5rem 0 max(0.5rem,env(safe-area-inset-bottom));box-shadow:0 -3px 16px rgba(7,6,4,0.07);}
.mobile-nav-inner{display:flex;justify-content:space-around;}
.mn-item{display:flex;flex-direction:column;align-items:center;gap:0.22rem;padding:0.38rem 1rem;cursor:pointer;position:relative;background:none;border:none;font-family:'DM Sans',sans-serif;}
.mn-item i{font-size:1.05rem;color:var(--tan);transition:0.14s;}
.mn-item span{font-size:0.58rem;font-weight:600;color:var(--tan);text-transform:uppercase;letter-spacing:0.06em;transition:0.14s;}
.mn-item.active i,.mn-item.active span{color:var(--gold);}
.mn-badge{position:absolute;top:0.18rem;right:0.55rem;background:var(--gold);color:var(--black);border-radius:var(--pill);font-size:0.52rem;font-weight:700;padding:0.08rem 0.34rem;min-width:14px;text-align:center;display:none;}

/* ─── EMPTY STATES ─── */
.empty-state{background:var(--white);border:1.5px dashed var(--cream3);border-radius:var(--r);padding:2.8rem 2rem;text-align:center;}
.empty-state .ei{font-size:2.4rem;margin-bottom:0.9rem;display:block;}
.empty-state h3{font-family:'Fraunces',serif;font-size:1.15rem;font-weight:700;color:var(--dark);margin-bottom:0.45rem;}
.empty-state p{font-size:0.84rem;color:var(--tan);line-height:1.65;max-width:360px;margin:0 auto 1.3rem;}
.coming-box{background:linear-gradient(135deg,var(--dark),#251a06);border-radius:var(--r);padding:1.3rem;border:1px solid rgba(200,149,42,0.18);text-align:center;margin-top:1.1rem;}
.coming-chip{display:inline-flex;align-items:center;gap:0.38rem;background:rgba(200,149,42,0.1);border:1px solid rgba(200,149,42,0.24);border-radius:var(--pill);padding:0.28rem 0.85rem;font-size:0.7rem;color:var(--gold2);font-weight:600;margin-bottom:0.8rem;}
.coming-box p{font-size:0.8rem;color:rgba(255,255,255,0.38);line-height:1.65;}
.coming-box strong{color:var(--gold2);}

/* ─── LOADING ─── */
.loading-overlay{position:fixed;inset:0;background:var(--cream);z-index:9998;display:flex;align-items:center;justify-content:center;flex-direction:column;gap:1.1rem;}
.loading-overlay.hidden{display:none;}
.loading-logo{font-family:'Fraunces',serif;font-weight:900;font-size:2.8rem;color:var(--dark);}
.loading-logo em{color:var(--gold);font-style:italic;}
.loading-spinner{width:32px;height:32px;border:2.5px solid var(--cream3);border-top-color:var(--gold);border-radius:50%;animation:spin 0.7s linear infinite;}
@keyframes spin{to{transform:rotate(360deg);}}

/* ─── TOAST ─── */
.toast{position:fixed;bottom:1.8rem;left:50%;transform:translateX(-50%) translateY(80px);background:var(--dark);color:var(--gold2);border:1px solid rgba(200,149,42,0.28);padding:0.77rem 1.5rem;border-radius:var(--pill);font-size:0.82rem;font-weight:500;z-index:9999;transition:transform 0.38s cubic-bezier(0.34,1.4,0.64,1);white-space:nowrap;pointer-events:none;box-shadow:var(--sh3);}
.toast.show{transform:translateX(-50%) translateY(0);}
@media(max-width:600px){.toast{bottom:5.5rem;max-width:calc(100vw - 2.5rem);white-space:normal;text-align:center;}}

/* ─── UTILS ─── */
.hidden{display:none!important;}
hr.div{border:none;border-top:1px solid var(--cream3);margin:1.2rem 0;}
.text-link{color:var(--gold);font-weight:600;cursor:pointer;background:none;border:none;font-family:'DM Sans',sans-serif;font-size:inherit;padding:0;text-decoration:underline;}

/* ─── DEMO BANNER ─── */
.demo-banner{background:linear-gradient(90deg,var(--dark),#251a06);border-bottom:1px solid rgba(200,149,42,0.2);padding:0.55rem 1.2rem;display:flex;align-items:center;justify-content:space-between;gap:0.8rem;flex-shrink:0;}
.demo-banner-txt{font-size:0.72rem;color:rgba(255,255,255,0.55);display:flex;align-items:center;gap:0.5rem;}
.demo-banner-txt strong{color:var(--gold2);}
.demo-banner-switch{font-size:0.7rem;font-weight:600;color:var(--gold2);cursor:pointer;background:rgba(200,149,42,0.12);border:1px solid rgba(200,149,42,0.24);border-radius:var(--pill);padding:0.22rem 0.75rem;white-space:nowrap;transition:0.18s;}
.demo-banner-switch:hover{background:rgba(200,149,42,0.2);}

/* ─── INTERVIEW PANEL ─── */
.int-card{background:var(--white);border:1px solid var(--cream3);border-radius:var(--r);padding:1.5rem;margin-bottom:0.85rem;}
.int-header{display:flex;align-items:center;gap:0.9rem;margin-bottom:1rem;}
.int-icon{width:44px;height:44px;border-radius:var(--r2);display:flex;align-items:center;justify-content:center;font-size:1.1rem;flex-shrink:0;}
.int-info h3{font-family:'Fraunces',serif;font-weight:700;font-size:0.97rem;color:var(--dark);}
.int-info p{font-size:0.75rem;color:var(--tan);}
.int-status{display:inline-flex;align-items:center;gap:0.35rem;border-radius:var(--pill);padding:0.22rem 0.65rem;font-size:0.68rem;font-weight:700;margin-left:auto;}
.int-status.upcoming{background:var(--green2);color:var(--green);}
.int-status.pending{background:#fef3d0;color:var(--gold);}
.int-details{display:grid;grid-template-columns:1fr 1fr;gap:0.65rem;margin-bottom:1rem;}
.int-detail .label{font-size:0.64rem;font-weight:700;text-transform:uppercase;letter-spacing:0.09em;color:var(--tan);margin-bottom:0.18rem;}
.int-detail .value{font-size:0.84rem;font-weight:600;color:var(--dark);}
.int-actions{display:flex;gap:0.42rem;flex-wrap:wrap;}
</style>
</head>
<body>

<div class="loading-overlay" id="loading">
  <div class="loading-logo">Lum<em>en</em></div>
  <div class="loading-spinner"></div>
</div>

<!-- ══ LANDING ══ -->
<div id="s-land" class="screen">
  <div class="land-canvas">
    <div class="land-grid"></div>
    <div class="land-g1"></div>
    <div class="land-g2"></div>
    <div class="land-g3"></div>
    <div class="land-scan"></div>
    <div class="land-scan"></div>
    <div class="land-scan"></div>
  </div>
  <div class="land-inner">
    <div class="land-pill"><div class="pill-dot"></div> Human-first hiring platform</div>
    <div class="land-h"><span class="gd">Lum</span><span class="out">en</span></div>
    <div class="land-tag">Where your degree becomes your advantage</div>
    <p class="land-desc">Startups are failing because they hire for <strong>code</strong> and forget about <strong>people.</strong> Lumen matches humanities thinkers with the tech teams that need them most.</p>
    <div class="land-btns">
      <button class="btn-gl" onclick="goTo('s-demo')">Try the Demo <i class="fas fa-arrow-right"></i></button>
      <button class="btn-gh" onclick="goTo('s-login')"><i class="fas fa-sign-in-alt"></i> Sign In</button>
    </div>
    <div class="land-proof">
      <div class="proof-i"><i class="fas fa-lock"></i> Human-vetted only</div>
      <div class="proof-i"><i class="fas fa-bolt"></i> Skills-based matching</div>
      <div class="proof-i"><i class="fas fa-shield-halved"></i> Private &amp; secure</div>
      <div class="proof-i"><i class="fas fa-fire"></i> Limited spots open</div>
    </div>
    <div class="land-demo-label">Interactive demo available — no signup required</div>
  </div>
</div>

<!-- ══ DEMO SELECTOR ══ -->
<div id="s-demo" class="screen" style="align-items:center;justify-content:center;padding:2rem 1rem;background:var(--cream);">
  <div class="demo-card">
    <div class="demo-ew">Interactive Demo</div>
    <h2 class="demo-title">Experience Lumen as...</h2>
    <p class="demo-sub">Choose a perspective and walk through the full product. No signup needed — see exactly how Lumen works before creating an account.</p>
    <div class="demo-grid">
      <div class="demo-choice" id="dc-hum" onclick="pickDemo('hum')">
        <div class="dc-check"><i class="fas fa-check"></i></div>
        <div class="dc-ico gold"><i class="fas fa-graduation-cap"></i></div>
        <div class="dc-h">Humanities Major</div>
        <div class="dc-p">See how Lumen reveals the hidden startup value in your education and matches you with aligned companies.</div>
      </div>
      <div class="demo-choice" id="dc-startup" onclick="pickDemo('startup')">
        <div class="dc-check"><i class="fas fa-check"></i></div>
        <div class="dc-ico slate"><i class="fas fa-rocket"></i></div>
        <div class="dc-h">Tech Startup</div>
        <div class="dc-p">See how Lumen finds human-centered candidates whose values align with your culture — pre-vetted and ready.</div>
      </div>
    </div>
    <button class="btn-cta hidden" id="demo-btn" onclick="startDemo()">Start Demo <i class="fas fa-play"></i></button>
    <hr class="div" style="margin:1rem 0;">
    <p style="text-align:center;font-size:0.83rem;color:var(--tan);">Have an account? <button class="text-link" onclick="goTo('s-login')">Sign in instead</button></p>
  </div>
</div>

<!-- ══ LOGIN ══ -->
<div id="s-login" class="screen">
  <nav class="top-nav">
    <div class="nav-logo">Lum<em>en</em></div>
    <button class="btn-gh" style="font-size:0.82rem;padding:0.6rem 1.2rem;" onclick="goTo('s-land')"><i class="fas fa-arrow-left"></i> Back</button>
  </nav>
  <div class="pw">
    <div class="card c-sm">
      <div class="ew">Welcome Back</div>
      <h2 class="ct">Sign in</h2>
      <p class="cs">Your profile, matches, and messages are waiting.</p>
      <div class="form-err" id="login-err"></div>
      <div class="field"><label>Email</label><input type="email" id="li-em" placeholder="you@email.com" autocomplete="email"></div>
      <div class="field"><label>Password</label><input type="password" id="li-pw" placeholder="Your password" autocomplete="current-password" onkeydown="if(event.key==='Enter')doLogin()"></div>
      <button class="btn-cta" onclick="doLogin()" id="login-btn" style="margin-top:0.3rem;">Sign In <i class="fas fa-arrow-right"></i></button>
      <hr class="div">
      <p style="text-align:center;font-size:0.84rem;color:var(--tan);">No account? <button class="text-link" onclick="goTo('s-demo')">Try the demo</button></p>
    </div>
  </div>
</div>

<!-- ══ ONBOARDING: ROLE ══ -->
<div id="s-choose" class="screen">
  <nav class="top-nav">
    <div class="nav-logo">Lum<em>en</em></div>
    <div class="nav-right"><span class="nav-step">Step 1 of 4</span></div>
  </nav>
  <div class="prog-wrap"><div class="prog-bar" style="width:25%"></div></div>
  <div class="pw">
    <div class="card c-lg">
      <button class="back-btn" onclick="goTo('s-land')"><i class="fas fa-arrow-left"></i> Back</button>
      <div class="ew">Join Lumen</div>
      <h2 class="ct">Who are you here as?</h2>
      <p class="cs">Your path shapes everything. Both sides of Lumen are equally powerful.</p>
      <div class="role-grid">
        <div class="rc" id="rc-hum" onclick="pickRole('hum')">
          <div class="rc-check"><i class="fas fa-check"></i></div>
          <div class="rc-ico ico-gold"><i class="fas fa-graduation-cap"></i></div>
          <div class="rc-h">Humanities Major</div>
          <div class="rc-p">Psychology, Sociology, English, History, Philosophy & more. Your education holds startup value no one is measuring — yet.</div>
        </div>
        <div class="rc" id="rc-startup" onclick="pickRole('startup')">
          <div class="rc-check"><i class="fas fa-check"></i></div>
          <div class="rc-ico ico-dark"><i class="fas fa-rocket"></i></div>
          <div class="rc-h">Tech Startup</div>
          <div class="rc-p">Stop losing investors, clients, and team members because no one on your team knows how to connect with humans.</div>
        </div>
      </div>
      <button class="btn-cta hidden" id="btn-role-next" onclick="nextRole()">Continue <i class="fas fa-arrow-right"></i></button>
      <hr class="div">
      <p style="text-align:center;font-size:0.83rem;color:var(--tan);">Already have an account? <button class="text-link" onclick="goTo('s-login')">Sign in</button></p>
    </div>
  </div>
</div>

<!-- ══ ONBOARDING: ACCOUNT ══ -->
<div id="s-account" class="screen">
  <nav class="top-nav">
    <div class="nav-logo">Lum<em>en</em></div>
    <div class="nav-right"><span class="nav-step" id="acct-step">Step 2 of 4</span></div>
  </nav>
  <div class="prog-wrap"><div class="prog-bar" style="width:50%"></div></div>
  <div class="pw">
    <div class="card c-md">
      <button class="back-btn" onclick="goTo('s-choose')"><i class="fas fa-arrow-left"></i> Back</button>
      <!-- HUMANITIES FORM -->
      <div id="f-hum">
        <div class="ew">Humanities Major</div>
        <h2 class="ct">Create your account</h2>
        <p class="cs">60 seconds to unlock your value profile. No resume needed.</p>
        <div class="form-err" id="hum-err"></div>
        <div class="frow">
          <div class="field"><label>First Name</label><input type="text" id="h-fn" placeholder="Maya" autocomplete="given-name"></div>
          <div class="field"><label>Last Name</label><input type="text" id="h-ln" placeholder="Chen" autocomplete="family-name"></div>
        </div>
        <div class="field"><label>Email</label><input type="email" id="h-em" placeholder="you@school.edu" autocomplete="email"></div>
        <div class="field"><label>Password</label><input type="password" id="h-pw" placeholder="Min 8 characters" autocomplete="new-password"></div>
        <div class="frow">
          <div class="field"><label>Major</label>
            <select id="h-mj">
              <option value="">Select...</option>
              <option>Psychology</option><option>Sociology</option><option>English / Literature</option>
              <option>History</option><option>Philosophy</option><option>Political Science</option>
              <option>Communications</option><option>Anthropology</option><option>Linguistics</option>
              <option>Gender Studies</option><option>Cultural Studies</option><option>Other Humanities</option>
            </select>
          </div>
          <div class="field"><label>School</label><input type="text" id="h-sc" placeholder="Howard, NYU..."></div>
        </div>
        <div class="field"><label>Graduation Year</label>
          <select id="h-yr">
            <option value="">Select...</option>
            <option>2024</option><option>2025</option><option>2026</option><option>2027</option><option>2028</option><option>Already Graduated</option>
          </select>
        </div>
        <button class="btn-cta" id="btn-hum" onclick="submitHum()">Create Account <i class="fas fa-arrow-right"></i></button>
      </div>
      <!-- STARTUP FORM -->
      <div id="f-startup" class="hidden">
        <div class="ew">Tech Startup</div>
        <h2 class="ct">Create your account</h2>
        <p class="cs">Tell us about your company so we can find the right humans for your team.</p>
        <div class="form-err" id="startup-err"></div>
        <div class="field"><label>Your Full Name</label><input type="text" id="s-fn" placeholder="Alex Rivera" autocomplete="name"></div>
        <div class="field"><label>Startup Name</label><input type="text" id="s-sn" placeholder="Cortex Health"></div>
        <div class="field"><label>Email</label><input type="email" id="s-em" placeholder="you@startup.com" autocomplete="email"></div>
        <div class="field"><label>Password</label><input type="password" id="s-pw" placeholder="Min 8 characters" autocomplete="new-password"></div>
        <div class="frow">
          <div class="field"><label>Industry</label>
            <select id="s-ind">
              <option value="">Select...</option>
              <option>HealthTech</option><option>FinTech</option><option>EdTech</option><option>B2B SaaS</option>
              <option>B2B2C</option><option>Gaming</option><option>E-commerce</option><option>AI / ML</option><option>Other</option>
            </select>
          </div>
          <div class="field"><label>Location</label><input type="text" id="s-loc" placeholder="San Francisco, CA"></div>
        </div>
        <div class="frow">
          <div class="field"><label>Team Size</label>
            <select id="s-sz">
              <option value="">Select...</option>
              <option>1–5 (Pre-seed)</option><option>6–15 (Seed)</option><option>16–50 (Series A)</option><option>50+</option>
            </select>
          </div>
          <div class="field"><label>Role You're Hiring For</label><input type="text" id="s-ro" placeholder="Client Success..."></div>
        </div>
        <div class="field"><label>Brief description</label><textarea id="s-desc" placeholder="What you build and who you serve..."></textarea></div>
        <button class="btn-cta" id="btn-startup" onclick="submitStartup()">Create Account <i class="fas fa-arrow-right"></i></button>
      </div>
    </div>
  </div>
</div>

<!-- ══ ONBOARDING: CLASSES (humanities) ══ -->
<div id="s-classes" class="screen">
  <nav class="top-nav">
    <div class="nav-logo">Lum<em>en</em></div>
    <div class="nav-right"><span class="nav-step">Step 3 of 4</span></div>
  </nav>
  <div class="prog-wrap"><div class="prog-bar" style="width:75%"></div></div>
  <div class="pw pw-top">
    <div class="card c-lg">
      <button class="back-btn" onclick="goTo('s-account')"><i class="fas fa-arrow-left"></i> Back</button>
      <div class="ew">Step 3 — Your Education</div>
      <h2 class="ct">Enter your classes</h2>
      <p class="cs">Every class you've taken carries startup value. Add them and watch the engine reveal the skills hiding inside your humanities education.</p>
      <div class="class-area">
        <div class="class-row">
          <input type="text" id="c-inp" placeholder="e.g. Organizational Behavior, Social Psychology..." onkeydown="if(event.key==='Enter'){event.preventDefault();addCls();}">
          <button class="add-btn" onclick="addCls()"><i class="fas fa-plus"></i> Add</button>
        </div>
        <div class="tags-wrap" id="c-tags"><span style="font-size:0.76rem;color:var(--tan);font-style:italic;">Your classes appear here...</span></div>
        <div class="class-hint">💡 Hit Enter or tap Add · Remove by tapping ×</div>
      </div>
      <div class="ins-box">
        <div class="ins-hdr"><i class="fas fa-wand-magic-sparkles"></i> Hidden Startup Skills Detected</div>
        <div class="ins-chips" id="c-chips"><span class="ins-empty">Add classes above to reveal your hidden value...</span></div>
      </div>
      <button class="btn-cta" id="btn-cls" disabled onclick="toValues()">Continue to Values <i class="fas fa-arrow-right"></i></button>
    </div>
  </div>
</div>

<!-- ══ ONBOARDING: VALUES ══ -->
<div id="s-values" class="screen">
  <nav class="top-nav">
    <div class="nav-logo">Lum<em>en</em></div>
    <div class="nav-right"><span class="nav-step">Step 4 of 4</span></div>
  </nav>
  <div class="prog-wrap"><div class="prog-bar" style="width:100%"></div></div>
  <div class="pw">
    <div class="card c-lg">
      <button class="back-btn" onclick="goTo('s-classes')"><i class="fas fa-arrow-left"></i> Back</button>
      <div class="ew">Step 4 — Your Identity</div>
      <h2 class="ct">Choose your core values</h2>
      <p class="cs">Pick up to <strong>4 values</strong> that are genuinely you. These power every match we make.</p>
      <div class="vcbar">
        <div class="vctxt">Selected: <strong id="v-cnt">0</strong> / 4</div>
        <div class="vdots"><div class="vdot" id="vd0"></div><div class="vdot" id="vd1"></div><div class="vdot" id="vd2"></div><div class="vdot" id="vd3"></div></div>
      </div>
      <div class="vgrid" id="v-grid"></div>
      <button class="btn-cta" onclick="submitValues()" id="btn-vals" disabled>See My Dashboard <i class="fas fa-arrow-right"></i></button>
    </div>
  </div>
</div>

<!-- ══ STARTUP VALUES ══ -->
<div id="s-startup-values" class="screen">
  <nav class="top-nav">
    <div class="nav-logo">Lum<em>en</em></div>
    <div class="nav-right"><span class="nav-step">Step 3 of 3</span></div>
  </nav>
  <div class="prog-wrap"><div class="prog-bar" style="width:100%"></div></div>
  <div class="pw">
    <div class="card c-lg">
      <div class="ew">Step 3 — Team Culture</div>
      <h2 class="ct">What values define your ideal hire?</h2>
      <p class="cs">Pick up to <strong>4 values</strong> your ideal candidate must have. We filter every humanities applicant against these.</p>
      <div class="vcbar">
        <div class="vctxt">Selected: <strong id="sv-cnt">0</strong> / 4</div>
        <div class="vdots"><div class="vdot" id="svd0"></div><div class="vdot" id="svd1"></div><div class="vdot" id="svd2"></div><div class="vdot" id="svd3"></div></div>
      </div>
      <div class="vgrid" id="sv-grid"></div>
      <button class="btn-cta" onclick="submitStartupValues()" id="btn-sv" disabled>View My Candidates <i class="fas fa-arrow-right"></i></button>
    </div>
  </div>
</div>

<!-- ══ HUMANITIES DASHBOARD ══ -->
<div id="s-dash" class="screen">
  <div class="demo-banner" id="hum-demo-banner">
    <div class="demo-banner-txt"><i class="fas fa-play-circle"></i> Demo mode: <strong>Humanities Major</strong> perspective</div>
    <div class="demo-banner-switch" onclick="switchDemo()"><i class="fas fa-sync-alt"></i> Switch to Startup view</div>
  </div>
  <nav class="dash-nav">
    <div class="dash-logo">Lum<em>en</em></div>
    <div class="dash-user" onclick="switchPanel('profile',null)">
      <span class="dash-uname" id="d-uname">—</span>
      <div class="ava" id="d-ava">?</div>
    </div>
  </nav>
  <div class="dash-wrap">
    <aside class="dash-side">
      <div>
        <div class="side-lbl">Main</div>
        <div class="si active" onclick="switchPanel('home',this)"><i class="fas fa-home"></i> Dashboard</div>
        <div class="si" onclick="switchPanel('matches',this)"><i class="fas fa-heart"></i> My Matches <span class="badge" id="match-badge">0</span></div>
        <div class="si" onclick="switchPanel('interviews',this)"><i class="fas fa-calendar-check"></i> Interviews <span class="badge" id="int-badge">2</span></div>
        <div class="si" onclick="switchPanel('messages',this)"><i class="fas fa-comment-dots"></i> Messages <span class="badge" id="msg-badge">0</span></div>
        <div class="si" onclick="switchPanel('profile',this)"><i class="fas fa-user"></i> My Profile</div>
      </div>
      <div>
        <div class="side-lbl">Vetting Status</div>
        <div class="vet-card">
          <div class="vet-lbl">Your status</div>
          <div class="vet-badge"><div class="vet-dot"></div> Under Review</div>
          <ul class="vet-steps">
            <li class="vs done"><i class="fas fa-check-circle"></i> Account created</li>
            <li class="vs done"><i class="fas fa-check-circle"></i> Classes submitted</li>
            <li class="vs done"><i class="fas fa-check-circle"></i> Values selected</li>
            <li class="vs cur"><i class="fas fa-clock"></i> Lumen interview</li>
            <li class="vs"><i class="fas fa-lock"></i> Final approval</li>
          </ul>
        </div>
      </div>
      <button class="logout-btn" onclick="doLogout()"><i class="fas fa-sign-out-alt"></i> Sign Out</button>
    </aside>
    <main class="dash-main">
      <!-- HOME -->
      <div class="panel active" id="panel-home">
        <div class="welcome-bar">
          <h1>Welcome, <span id="d-fname">there</span> 👋</h1>
          <p>Your personalized startup feed — powered by your classes and values.</p>
        </div>
        <div class="val-banner">
          <div class="vb-left">
            <div class="vb-lbl"><i class="fas fa-wand-magic-sparkles"></i> Hidden Value Profile</div>
            <div class="vb-title">Skills from your education</div>
            <div class="vb-skills" id="d-skills"></div>
          </div>
          <div class="vb-right">
            <div class="vb-score" id="d-score">—</div>
            <div class="vb-score-lbl">profile score</div>
          </div>
        </div>
        <div class="stats-row">
          <div class="stat-box"><div class="s-lbl">Active Matches</div><div class="s-val" id="d-mc">4</div><div class="s-sub">↑ Updated daily</div></div>
          <div class="stat-box"><div class="s-lbl">Values</div><div class="s-val" id="d-vc">—</div><div class="s-sub">Identity locked in</div></div>
          <div class="stat-box"><div class="s-lbl">Classes</div><div class="s-val" id="d-cc">—</div><div class="s-sub">Skills analyzed</div></div>
        </div>
        <div class="sec-hdr"><h2>Matched Startups</h2><button onclick="switchPanel('matches',null)">See all →</button></div>
        <div id="d-feed"></div>
      </div>
      <!-- MATCHES -->
      <div class="panel" id="panel-matches">
        <div class="welcome-bar"><h1>My Matches</h1><p>Startups aligned with your values and skills.</p></div>
        <div class="match-filters">
          <button class="mf-btn active" onclick="filterMatches('all',this)">All</button>
          <button class="mf-btn" onclick="filterMatches('pending',this)">Pending</button>
          <button class="mf-btn" onclick="filterMatches('connected',this)">Connected</button>
        </div>
        <div id="m-feed"></div>
      </div>
      <!-- INTERVIEWS -->
      <div class="panel" id="panel-interviews">
        <div class="welcome-bar"><h1>Interviews</h1><p>Your scheduled and pending interview requests.</p></div>
        <div id="int-list"></div>
      </div>
      <!-- MESSAGES -->
      <div class="panel" id="panel-messages">
        <div class="welcome-bar"><h1>Messages</h1><p>Chat with startups you've connected with.</p></div>
        <div class="msg-layout">
          <div class="msg-sidebar">
            <div class="msg-sidebar-hdr">Conversations</div>
            <div id="msg-threads"></div>
          </div>
          <div class="msg-main" id="msg-main">
            <div class="msg-empty"><i class="fas fa-comment-dots"></i><p>Select a conversation to start chatting</p></div>
          </div>
        </div>
      </div>
      <!-- PROFILE -->
      <div class="panel" id="panel-profile">
        <div class="welcome-bar"><h1>My Profile</h1><p>Your Lumen identity — visible to matched startups.</p></div>
        <div class="profile-card">
          <div class="ew">Personal Info</div>
          <div class="profile-grid">
            <div><div class="pf-lbl">Full Name</div><div class="pf-val" id="p-name">—</div></div>
            <div><div class="pf-lbl">Email</div><div class="pf-val" id="p-email">—</div></div>
            <div><div class="pf-lbl">Major</div><div class="pf-val" id="p-major">—</div></div>
            <div><div class="pf-lbl">School</div><div class="pf-val" id="p-school">—</div></div>
          </div>
        </div>
        <div class="profile-card">
          <div class="ew">Your Values</div>
          <div class="modal-pills" style="margin-top:0.7rem;" id="p-vals"></div>
        </div>
        <div class="profile-card">
          <div class="ew">Hidden Skills</div>
          <div class="vb-skills" style="margin-top:0.7rem;" id="p-skills"></div>
        </div>
        <div style="text-align:center;padding:1rem 0;">
          <button class="btn-outline" style="max-width:200px;margin:0 auto;" onclick="doLogout()"><i class="fas fa-sign-out-alt"></i> Sign Out</button>
        </div>
      </div>
    </main>
  </div>
  <!-- Mobile nav -->
  <nav class="mobile-nav" id="hum-mobile-nav">
    <div class="mobile-nav-inner">
      <button class="mn-item active" id="mn-home" onclick="switchPanelM('home',0)"><i class="fas fa-home"></i><span>Home</span></button>
      <button class="mn-item" id="mn-matches" onclick="switchPanelM('matches',1)"><i class="fas fa-heart"></i><span>Matches</span><span class="mn-badge" id="mn-badge">0</span></button>
      <button class="mn-item" id="mn-interviews" onclick="switchPanelM('interviews',2)"><i class="fas fa-calendar-check"></i><span>Interviews</span><span class="mn-badge" style="display:flex;">2</span></button>
      <button class="mn-item" id="mn-messages" onclick="switchPanelM('messages',3)"><i class="fas fa-comment-dots"></i><span>Messages</span><span class="mn-badge" id="mn-msg-badge">0</span></button>
      <button class="mn-item" id="mn-profile" onclick="switchPanelM('profile',4)"><i class="fas fa-user"></i><span>Profile</span></button>
    </div>
  </nav>
</div>

<!-- ══ STARTUP DASHBOARD ══ -->
<div id="s-startup-dash" class="screen">
  <div class="demo-banner">
    <div class="demo-banner-txt"><i class="fas fa-play-circle"></i> Demo mode: <strong>Tech Startup</strong> perspective</div>
    <div class="demo-banner-switch" onclick="switchDemo()"><i class="fas fa-sync-alt"></i> Switch to Major view</div>
  </div>
  <nav class="dash-nav">
    <div class="dash-logo">Lum<em>en</em></div>
    <div class="dash-user">
      <span class="dash-uname" id="sd-uname">—</span>
      <div class="ava" id="sd-ava">?</div>
    </div>
  </nav>
  <div class="dash-wrap" style="grid-template-columns:240px 1fr;">
    <aside class="dash-side" id="startup-sidebar">
      <div>
        <div class="side-lbl">Main</div>
        <div class="si active" onclick="switchStartupPanel('shome',this)"><i class="fas fa-home"></i> Dashboard</div>
        <div class="si" onclick="switchStartupPanel('scands',this)"><i class="fas fa-users"></i> Candidates <span class="badge">8</span></div>
        <div class="si" onclick="switchStartupPanel('sinterviews',this)"><i class="fas fa-calendar-check"></i> Interviews <span class="badge">3</span></div>
        <div class="si" onclick="switchStartupPanel('smessages',this)"><i class="fas fa-comment-dots"></i> Messages <span class="badge" id="s-msg-badge">0</span></div>
        <div class="si" onclick="switchStartupPanel('sprofile',this)"><i class="fas fa-building"></i> Company Profile</div>
      </div>
      <div>
        <div class="side-lbl">Account Status</div>
        <div class="vet-card">
          <div class="vet-lbl">Subscription</div>
          <div class="vet-badge"><div class="vet-dot"></div> Active · Starter Plan</div>
          <ul class="vet-steps">
            <li class="vs done"><i class="fas fa-check-circle"></i> Profile approved</li>
            <li class="vs done"><i class="fas fa-check-circle"></i> Values set</li>
            <li class="vs done"><i class="fas fa-check-circle"></i> Matching live</li>
            <li class="vs cur"><i class="fas fa-star"></i> 8 candidates ready</li>
          </ul>
        </div>
      </div>
      <button class="logout-btn" onclick="doLogout()"><i class="fas fa-sign-out-alt"></i> Sign Out</button>
    </aside>
    <main class="dash-main">
      <!-- STARTUP HOME -->
      <div class="panel active" id="panel-shome">
        <div class="welcome-bar">
          <h1>Welcome, <span id="sd-fname">there</span> 👋</h1>
          <p>Your matched candidates — filtered by values, ranked by fit.</p>
        </div>
        <div class="startup-dash-header">
          <div class="sdh-label"><i class="fas fa-wand-magic-sparkles"></i> Live Matching Engine</div>
          <div class="sdh-title" id="sd-company">Your Startup</div>
          <div class="sdh-sub" id="sd-role-txt">Hiring for open role</div>
          <div class="sdh-stats">
            <div class="sdh-stat"><div class="n">8</div><div class="l">Matched candidates</div></div>
            <div class="sdh-stat"><div class="n">3</div><div class="l">Interviews scheduled</div></div>
            <div class="sdh-stat"><div class="n">94%</div><div class="l">Avg. value alignment</div></div>
          </div>
        </div>
        <div class="sec-hdr"><h2>Top Candidates</h2><button onclick="switchStartupPanel('scands',null)">See all 8 →</button></div>
        <div id="sd-feed"></div>
      </div>
      <!-- CANDIDATES -->
      <div class="panel" id="panel-scands">
        <div class="welcome-bar"><h1>Candidates</h1><p>All matched humanities majors, ranked by value alignment with your culture.</p></div>
        <div class="match-filters">
          <button class="mf-btn active" onclick="filterCands('all',this)">All (8)</button>
          <button class="mf-btn" onclick="filterCands('new',this)">New</button>
          <button class="mf-btn" onclick="filterCands('shortlisted',this)">Shortlisted</button>
          <button class="mf-btn" onclick="filterCands('interviewed',this)">Interviewed</button>
        </div>
        <div id="cands-feed"></div>
      </div>
      <!-- STARTUP INTERVIEWS -->
      <div class="panel" id="panel-sinterviews">
        <div class="welcome-bar"><h1>Interviews</h1><p>Scheduled and pending interviews with your matched candidates.</p></div>
        <div id="s-int-list"></div>
      </div>
      <!-- STARTUP MESSAGES -->
      <div class="panel" id="panel-smessages">
        <div class="welcome-bar"><h1>Messages</h1><p>Chat with candidates you've connected with.</p></div>
        <div class="msg-layout">
          <div class="msg-sidebar">
            <div class="msg-sidebar-hdr">Conversations</div>
            <div id="s-msg-threads"></div>
          </div>
          <div class="msg-main" id="s-msg-main">
            <div class="msg-empty"><i class="fas fa-comment-dots"></i><p>Select a conversation to start chatting</p></div>
          </div>
        </div>
      </div>
      <!-- STARTUP PROFILE -->
      <div class="panel" id="panel-sprofile">
        <div class="welcome-bar"><h1>Company Profile</h1><p>Your Lumen company listing — shown to matched candidates.</p></div>
        <div class="profile-card">
          <div class="ew">Company Info</div>
          <div class="profile-grid">
            <div><div class="pf-lbl">Company</div><div class="pf-val" id="sp-company">—</div></div>
            <div><div class="pf-lbl">Industry</div><div class="pf-val" id="sp-industry">—</div></div>
            <div><div class="pf-lbl">Hiring For</div><div class="pf-val" id="sp-role">—</div></div>
            <div><div class="pf-lbl">Location</div><div class="pf-val" id="sp-location">—</div></div>
          </div>
        </div>
        <div class="profile-card">
          <div class="ew">Culture Values</div>
          <div class="modal-pills" style="margin-top:0.7rem;" id="sp-vals"></div>
        </div>
        <div style="text-align:center;padding:1rem 0;">
          <button class="btn-outline" style="max-width:200px;margin:0 auto;" onclick="doLogout()"><i class="fas fa-sign-out-alt"></i> Sign Out</button>
        </div>
      </div>
    </main>
  </div>
  <nav class="mobile-nav" id="startup-mobile-nav" style="display:none;">
    <div class="mobile-nav-inner">
      <button class="mn-item active" onclick="switchStartupPanelM('shome',0)"><i class="fas fa-home"></i><span>Home</span></button>
      <button class="mn-item" onclick="switchStartupPanelM('scands',1)"><i class="fas fa-users"></i><span>Candidates</span><span class="mn-badge" style="display:flex;">8</span></button>
      <button class="mn-item" onclick="switchStartupPanelM('sinterviews',2)"><i class="fas fa-calendar-check"></i><span>Interviews</span></button>
      <button class="mn-item" onclick="switchStartupPanelM('smessages',3)"><i class="fas fa-comment-dots"></i><span>Messages</span></button>
      <button class="mn-item" onclick="switchStartupPanelM('sprofile',4)"><i class="fas fa-building"></i><span>Profile</span></button>
    </div>
  </nav>
</div>

<!-- ══ PENDING ══ -->
<div id="s-pending" class="screen">
  <div class="pw" style="background:var(--dark);flex:1;">
    <div class="pend-wrap">
      <div class="pend-ico"><i class="fas fa-check"></i></div>
      <h2>You're in.</h2>
      <p>Your startup profile is submitted. We review every application personally and will reach out within 24 hours.</p>
      <div class="pend-steps">
        <div class="pstep"><div class="pstep-n">1</div><div class="pstep-t"><strong>Lumen Onboarding Call</strong><p>We walk you through the platform and understand your exact hiring needs.</p></div></div>
        <div class="pstep"><div class="pstep-n">2</div><div class="pstep-t"><strong>Upload Your Company Video</strong><p>A short culture video so candidates can see your team before applying.</p></div></div>
        <div class="pstep"><div class="pstep-n">3</div><div class="pstep-t"><strong>Get Matched &amp; Hire</strong><p>We filter every humanities candidate against your values. You only see ideal fits.</p></div></div>
      </div>
      <button class="btn-gl" onclick="goTo('s-startup-dash')" style="width:100%;justify-content:center;border-radius:var(--r2);"><i class="fas fa-tachometer-alt"></i> Go to Dashboard</button>
    </div>
  </div>
</div>

<!-- ══ PROFILE MODAL ══ -->
<div class="modal-overlay hidden" id="profile-modal">
  <div class="modal-box">
    <div class="modal-handle"></div>
    <div class="modal-header">
      <div style="display:flex;align-items:center;gap:0.9rem;">
        <div class="sup-logo" id="m-logo" style="width:48px;height:48px;font-size:1.4rem;border-radius:10px;flex-shrink:0;"></div>
        <div>
          <div style="font-family:'Fraunces',serif;font-weight:700;font-size:1.1rem;" id="m-name"></div>
          <div style="font-size:0.76rem;color:var(--tan);" id="m-meta"></div>
        </div>
      </div>
      <button class="modal-close" onclick="closeModal()"><i class="fas fa-times"></i></button>
    </div>
    <div class="modal-body">
      <div class="modal-section">
        <div class="modal-sec-title"><i class="fas fa-bullseye"></i> About</div>
        <div class="modal-text" id="m-about"></div>
      </div>
      <div class="modal-section">
        <div class="modal-sec-title"><i class="fas fa-briefcase"></i> Open Role</div>
        <div class="modal-text" id="m-role-detail"></div>
      </div>
      <div class="modal-section">
        <div class="modal-sec-title"><i class="fas fa-star"></i> Company Values</div>
        <div class="modal-pills" id="m-vals"></div>
      </div>
      <div class="modal-section">
        <div class="modal-sec-title"><i class="fas fa-lightbulb"></i> Why You're a Match</div>
        <div class="modal-text" id="m-why"></div>
      </div>
    </div>
    <div class="modal-footer">
      <button class="btn-modal-primary" id="m-connect-btn" onclick="connectFromModal()">Connect <i class="fas fa-arrow-right"></i></button>
      <button class="btn-modal-outline" onclick="closeModal()">Close</button>
    </div>
  </div>
</div>

<!-- Candidate modal -->
<div class="modal-overlay hidden" id="cand-modal">
  <div class="modal-box">
    <div class="modal-handle"></div>
    <div class="modal-header">
      <div style="display:flex;align-items:center;gap:0.9rem;">
        <div class="cand-ava" id="cm-ava" style="width:48px;height:48px;font-size:1.4rem;border-radius:50%;flex-shrink:0;"></div>
        <div>
          <div style="font-family:'Fraunces',serif;font-weight:700;font-size:1.1rem;" id="cm-name"></div>
          <div style="font-size:0.76rem;color:var(--tan);" id="cm-meta"></div>
        </div>
      </div>
      <button class="modal-close" onclick="closeCandModal()"><i class="fas fa-times"></i></button>
    </div>
    <div class="modal-body">
      <div class="modal-section">
        <div class="modal-sec-title"><i class="fas fa-graduation-cap"></i> Education</div>
        <div class="modal-text" id="cm-edu"></div>
      </div>
      <div class="modal-section">
        <div class="modal-sec-title"><i class="fas fa-wand-magic-sparkles"></i> Hidden Skills</div>
        <div class="ins-chips" id="cm-skills" style="margin-top:0.5rem;"></div>
      </div>
      <div class="modal-section">
        <div class="modal-sec-title"><i class="fas fa-heart"></i> Core Values</div>
        <div class="modal-pills" id="cm-vals"></div>
      </div>
      <div class="modal-section">
        <div class="modal-sec-title"><i class="fas fa-lightbulb"></i> Why They're a Fit</div>
        <div class="modal-text" id="cm-why"></div>
      </div>
    </div>
    <div class="modal-footer">
      <button class="btn-modal-primary" id="cm-interview-btn" onclick="scheduleInterview()">Schedule Interview <i class="fas fa-calendar-plus"></i></button>
      <button class="btn-modal-outline" onclick="closeCandModal()">Close</button>
    </div>
  </div>
</div>

<div class="toast" id="tst"></div>

<script>
// ══════════════════════════════════════
// DATA
// ══════════════════════════════════════
const STARTUPS = [
  {id:'cortex',name:'Cortex Health',meta:'HealthTech · San Francisco · 12 people',icon:'🧠',bg:'#deeef5',role:'Patient Relations Lead',values:['Empathy','Ethics','Communication','Vision'],match:96,about:'Cortex Health builds AI-powered mental health tools for underserved communities. We believe technology should serve people, not replace them.',roleDetail:'The Patient Relations Lead serves as the human bridge between our AI platform and the real patients using it — onboarding, feedback, and community trust.',why:'Behavioral psychology and counseling coursework maps directly to patient-facing relationship work.'},
  {id:'luminary',name:'Luminary Learn',meta:'EdTech · Remote · 8 people',icon:'📚',bg:'#f5ede0',role:'Community & Curriculum Advisor',values:['Curiosity','Creativity','Collaboration','Enthusiasm'],match:91,about:'Luminary Learn creates personalized learning experiences for first-generation college students. Remote-first, mission-aligned, growing fast.',roleDetail:'Shape how our student communities are built and ensure course content resonates with diverse learners.',why:'Education and communications backgrounds translate directly to curriculum design and community management.'},
  {id:'anchor',name:'Anchor B2B',meta:'B2B SaaS · Austin, TX · 20 people',icon:'⚓',bg:'#e8f0e8',role:'Client Success Manager',values:['Integrity','Resilience','Leadership','Communication'],match:84,about:'Anchor B2B helps mid-market companies streamline vendor relationships through smart contract and workflow automation. Series A, scaling fast.',roleDetail:'Own the entire post-sale client relationship — onboarding, retention, expansion, and advocacy.',why:'Organizational behavior and negotiation training means thinking in systems, relationships, and outcomes.'},
  {id:'veritas',name:'Veritas Capital',meta:'FinTech · New York · 35 people',icon:'💎',bg:'#f0eaf8',role:'Investor Relations Associate',values:['Vision','Integrity','Communication','Ethics'],match:79,about:'Veritas Capital connects emerging market founders with institutional investors through a transparency-first platform.',roleDetail:'Manage our investor community, write quarterly updates, coordinate LP meetings, and ensure every stakeholder feels valued.',why:'Rhetoric, research, and policy thinking translates directly into clear, ethical financial communication.'},
];

const CANDIDATES = [
  {id:'c1',name:'Maya Chen',major:'Psychology',school:'Howard University',year:'2025',ava:'MC',bg:'linear-gradient(135deg,#deeef5,#b8d8e8)',skills:['Behavioral Insight','Active Listening','User Empathy','Community Building'],values:['Empathy','Ethics','Communication','Curiosity'],match:96,why:'Maya\'s clinical psychology background and research methods experience directly maps to what your team needs — someone who can translate user pain into product insight.'},
  {id:'c2',name:'Jordan Williams',major:'Communications',school:'NYU',year:'2024',ava:'JW',bg:'linear-gradient(135deg,#f5ede0,#e8d0b0)',skills:['Content Strategy','Public Speaking','Narrative Framing','Marketing Strategy'],values:['Creativity','Communication','Enthusiasm','Vision'],match:91,why:'Jordan\'s communications degree with a focus on digital media is a direct match for your content and community-facing role.'},
  {id:'c3',name:'Amara Osei',major:'Sociology',school:'Spelman College',year:'2025',ava:'AO',bg:'linear-gradient(135deg,#e8f0e8,#b8d8b8)',skills:['Community Building','Team Leadership','Global Perspective','Policy Thinking'],values:['Collaboration','Integrity','Empathy','Leadership'],match:88,why:'Amara\'s sociological lens and community organizing experience makes her exceptional at building relationships that scale.'},
  {id:'c4',name:'Diego Reyes',major:'Philosophy',school:'Georgetown',year:'2024',ava:'DR',bg:'linear-gradient(135deg,#f0eaf8,#d8b8e8)',skills:['Ethical Reasoning','Negotiation','Policy Thinking','Critical Thinking'],values:['Ethics','Integrity','Vision','Curiosity'],match:85,why:'Diego\'s philosophy background brings the kind of ethical framework and persuasive reasoning your investor relations and compliance work requires.'},
  {id:'c5',name:'Zoe Park',major:'English / Literature',school:'Yale',year:'2025',ava:'ZP',bg:'linear-gradient(135deg,#fdf4e3,#f5d8a0)',skills:['Storytelling','Content Strategy','Narrative Framing','Persuasion & Sales'],values:['Creativity','Communication','Empathy','Adaptability'],match:83,why:'Zoe\'s editorial instincts and storytelling ability is what your brand voice has been missing.'},
  {id:'c6',name:'Marcus Bell',major:'Political Science',school:'Morehouse College',year:'2024',ava:'MB',bg:'linear-gradient(135deg,#eaf5f0,#b0d8c8)',skills:['Policy Thinking','Negotiation','Team Leadership','Global Perspective'],values:['Leadership','Integrity','Resilience','Vision'],match:80,why:'Marcus brings the political acumen and strategic communication skills needed to represent your company to enterprise clients.'},
  {id:'c7',name:'Sofia Torres',major:'Anthropology',school:'UCLA',year:'2025',ava:'ST',bg:'linear-gradient(135deg,#fef0f0,#f8c8c8)',skills:['Global Perspective','User Empathy','Community Building','Behavioral Insight'],values:['Empathy','Curiosity','Collaboration','Adaptability'],match:77,why:'Sofia\'s cross-cultural research background makes her exceptional at understanding diverse user populations and advocating for underrepresented users.'},
  {id:'c8',name:'Kwame Davis',major:'History',school:'Howard University',year:'2024',ava:'KD',bg:'linear-gradient(135deg,#eef0fa,#c8c8f0)',skills:['Research & Analysis','Narrative Framing','Policy Thinking','Content Strategy'],values:['Curiosity','Integrity','Communication','Vision'],match:74,why:'Kwame\'s historical research skills — synthesizing complex information into clear narratives — is exactly what your investor communications and content strategy needs.'},
];

const SMAP = [
  {keys:['research','methods','quantitative','qualitative','data','analysis','survey','experiment','empirical'],skill:'Data Analysis',ico:'fa-chart-bar'},
  {keys:['economics','econom','finance','fiscal','budget','accounting','market analysis'],skill:'Financial Literacy',ico:'fa-dollar-sign'},
  {keys:['statistics','statistical','regression','modeling','measurement'],skill:'Statistical Reasoning',ico:'fa-calculator'},
  {keys:['psychology','behavior','cognitive','neuroscience','perception','mental','behavioral'],skill:'Behavioral Insight',ico:'fa-brain'},
  {keys:['social','sociology','community','group','collective','culture','society'],skill:'Community Building',ico:'fa-people-group'},
  {keys:['organizational','org','management','leadership','teams','administration'],skill:'Team Leadership',ico:'fa-sitemap'},
  {keys:['counseling','therapy','clinical','intervention','helping','support'],skill:'Active Listening',ico:'fa-ear-listen'},
  {keys:['development','developmental','child','adolescent','lifespan','human growth'],skill:'User Empathy',ico:'fa-heart-pulse'},
  {keys:['writing','composition','rhetoric','argument','essay','journalism','editorial'],skill:'Content Strategy',ico:'fa-pen-nib'},
  {keys:['communication','speech','public speaking','presentation','media','broadcasting'],skill:'Public Speaking',ico:'fa-microphone'},
  {keys:['language','linguistic','semiotics','discourse','narrative','translation'],skill:'Narrative Framing',ico:'fa-book-open'},
  {keys:['creative writing','fiction','storytelling','script','narrative craft'],skill:'Storytelling',ico:'fa-feather'},
  {keys:['marketing','advertising','branding','consumer','market','pr'],skill:'Marketing Strategy',ico:'fa-bullhorn'},
  {keys:['business','entrepreneurship','startup','venture','innovation','strategy'],skill:'Business Acumen',ico:'fa-briefcase'},
  {keys:['negotiation','conflict','mediation','diplomacy','resolution'],skill:'Negotiation',ico:'fa-handshake'},
  {keys:['policy','governance','law','legal','politics','political','regulation'],skill:'Policy Thinking',ico:'fa-scale-balanced'},
  {keys:['ethics','moral','philosophy','critical thinking','logic','reasoning'],skill:'Ethical Reasoning',ico:'fa-balance-scale'},
  {keys:['global','international','cross-cultural','intercultural','world','diversity'],skill:'Global Perspective',ico:'fa-globe'},
  {keys:['persuasion','influence','attitude','motivation','social influence'],skill:'Persuasion & Sales',ico:'fa-chart-line'},
  {keys:['human resources','hr','recruiting','talent','workforce','people management'],skill:'Talent Acquisition',ico:'fa-users'},
  {keys:['education','teaching','pedagogy','curriculum','instruction','tutoring'],skill:'Training & Coaching',ico:'fa-chalkboard-teacher'},
  {keys:['design','visual','ux','user experience','interface','art','graphic'],skill:'Design Thinking',ico:'fa-palette'},
];
const icoMap = {};
SMAP.forEach(m => icoMap[m.skill] = m.ico);

const VALS = [
  {n:'Empathy',i:'🤝'},{n:'Curiosity',i:'🔍'},{n:'Integrity',i:'⚖️'},{n:'Enthusiasm',i:'✨'},
  {n:'Resilience',i:'💪'},{n:'Creativity',i:'🎨'},{n:'Communication',i:'💬'},{n:'Adaptability',i:'🌱'},
  {n:'Leadership',i:'🧭'},{n:'Collaboration',i:'🤲'},{n:'Ethics',i:'🌟'},{n:'Vision',i:'🔭'}
];

// ── STATE ──
let S = {
  role: null, demoRole: null,
  firstName:'', lastName:'', email:'', major:'', school:'', gradYear:'',
  startupName:'', industry:'', location:'', teamSize:'', roleHiring:'', desc:'',
  classes:[], skills:[], values:[],
  matches:[], connectedStartups:[], activeChat:null,
  startupValues:[], activeCandChat:null,
  scheduledInterviews:[], scheduledCandInterviews:[]
};
const CHATS = {};
const CAND_CHATS = {};

// ── NAV ──
function goTo(id) {
  document.querySelectorAll('.screen').forEach(s=>s.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  window.scrollTo(0,0);
}

// ── DEMO ──
let demoRole = null;
function pickDemo(r) {
  demoRole = r;
  document.getElementById('dc-hum').classList.toggle('sel', r==='hum');
  document.getElementById('dc-startup').classList.toggle('sel', r==='startup');
  document.getElementById('demo-btn').classList.remove('hidden');
}
function startDemo() {
  if (!demoRole) return;
  if (demoRole === 'hum') launchHumDemo();
  else launchStartupDemo();
}
function launchHumDemo() {
  S.firstName='Maya'; S.lastName='Chen'; S.email='maya@howard.edu';
  S.major='Psychology'; S.school='Howard University'; S.gradYear='2025';
  S.classes=['Social Psychology','Research Methods','Counseling Techniques','Organizational Behavior','Developmental Psychology'];
  S.skills=extractSkills(S.classes);
  S.values=['Empathy','Ethics','Communication','Curiosity'];
  S.connectedStartups=['cortex','luminary'];
  CHATS['cortex']=[{sender:'them',text:'Hi Maya! 👋 We saw your profile on Lumen and we\'re really impressed. Your psychology background is exactly what our patient relations role needs. Are you available for a 30-min call this week?',time:'9:02'},{sender:'me',text:'Hi! Yes, absolutely — I\'d love to learn more about the role. I\'m free Thursday afternoon or Friday morning.',time:'9:45'},{sender:'them',text:'Perfect! Thursday 2pm PST works great. I\'ll send a calendar invite. Looking forward to connecting! 🙌',time:'10:12'}];
  CHATS['luminary']=[{sender:'them',text:'Maya, your profile is incredible. The combination of Developmental Psychology and Research Methods is rare — and exactly what our curriculum design needs.',time:'11:30'},{sender:'me',text:'Thank you! Luminary\'s mission really resonates with me — I wrote my thesis on learning disparities in first-gen students.',time:'12:05'}];
  S.scheduledInterviews=[
    {company:'Cortex Health',role:'Patient Relations Lead',date:'Thursday, Apr 24',time:'2:00 PM PST',format:'Video call · 30 min',icon:'🧠',bg:'#deeef5',status:'upcoming'},
    {company:'Luminary Learn',role:'Community & Curriculum Advisor',date:'Friday, Apr 25',time:'11:00 AM PST',format:'Video call · 45 min',icon:'📚',bg:'#f5ede0',status:'upcoming'}
  ];
  buildHumDash(); goTo('s-dash');
}
function launchStartupDemo() {
  S.firstName='Alex'; S.lastName='Rivera'; S.email='alex@cortexhealth.io';
  S.startupName='Cortex Health'; S.industry='HealthTech'; S.location='San Francisco, CA';
  S.teamSize='6–15 (Seed)'; S.roleHiring='Patient Relations Lead'; S.desc='AI-powered mental health tools for underserved communities.';
  S.startupValues=['Empathy','Ethics','Communication','Vision'];
  CAND_CHATS['c1']=[{sender:'me',text:'Hi Maya! We saw your profile on Lumen and we\'re really impressed. Your psychology background is exactly what our patient relations role needs.',time:'9:02'},{sender:'them',text:'Hi Alex! Yes, I\'d love to learn more. I\'m especially drawn to Cortex\'s mission — mental health access is something I care deeply about.',time:'9:45'},{sender:'me',text:'That means a lot. Would you be available Thursday at 2pm PST for a call?',time:'10:00'},{sender:'them',text:'Thursday 2pm works perfectly! Looking forward to it.',time:'10:12'}];
  CAND_CHATS['c2']=[{sender:'me',text:'Jordan, your communications background caught our eye. We think you could add a lot to our community outreach.',time:'14:00'},{sender:'them',text:'Thanks Alex! I\'ve been following Cortex — really admire what you\'re building.',time:'14:30'}];
  S.scheduledCandInterviews=[
    {name:'Maya Chen',major:'Psychology',date:'Thursday, Apr 24',time:'2:00 PM PST',format:'Video call · 30 min',ava:'MC',bg:'linear-gradient(135deg,#deeef5,#b8d8e8)',status:'upcoming',match:96},
    {name:'Jordan Williams',major:'Communications',date:'Friday, Apr 25',time:'11:00 AM PST',format:'Video call · 45 min',ava:'JW',bg:'linear-gradient(135deg,#f5ede0,#e8d0b0)',status:'upcoming',match:91},
    {name:'Amara Osei',major:'Sociology',date:'Monday, Apr 28',time:'3:00 PM PST',format:'Video call · 30 min',ava:'AO',bg:'linear-gradient(135deg,#e8f0e8,#b8d8b8)',status:'pending',match:88}
  ];
  buildStartupDash(); goTo('s-startup-dash');
}
function switchDemo() {
  if (document.getElementById('s-dash').classList.contains('active')) launchStartupDemo();
  else launchHumDemo();
}

// ── ROLE ──
function pickRole(r) {
  S.role = r;
  document.getElementById('rc-hum').classList.toggle('sel', r==='hum');
  document.getElementById('rc-startup').classList.toggle('sel', r==='startup');
  const btn = document.getElementById('btn-role-next');
  btn.classList.remove('hidden');
}
function nextRole() {
  if (!S.role) { showToast('Please choose a role first.'); return; }
  if (S.role === 'hum') {
    document.getElementById('f-hum').classList.remove('hidden');
    document.getElementById('f-startup').classList.add('hidden');
    document.getElementById('acct-step').textContent = 'Step 2 of 4';
  } else {
    document.getElementById('f-startup').classList.remove('hidden');
    document.getElementById('f-hum').classList.add('hidden');
    document.getElementById('acct-step').textContent = 'Step 2 of 3';
  }
  goTo('s-account');
}

// ── ACCOUNT SUBMIT ──
function v(id) { return document.getElementById(id)?.value?.trim() || ''; }
async function submitHum() {
  const fn=v('h-fn'),ln=v('h-ln'),em=v('h-em'),pw=v('h-pw'),mj=v('h-mj'),sc=v('h-sc'),yr=v('h-yr');
  const err=document.getElementById('hum-err'); err.classList.remove('show');
  if(!fn||!ln||!em||!pw||!mj||!sc||!yr){showErr(err,'Please fill in all fields.');return;}
  if(pw.length<8){showErr(err,'Password must be at least 8 characters.');return;}
  S.firstName=fn;S.lastName=ln;S.email=em;S.major=mj;S.school=sc;S.gradYear=yr;
  const btn=document.getElementById('btn-hum');btn.disabled=true;btn.innerHTML='Creating... <i class="fas fa-spinner fa-spin"></i>';
  await new Promise(r=>setTimeout(r,800));
  btn.disabled=false;btn.innerHTML='Create Account <i class="fas fa-arrow-right"></i>';
  showToast('✅ Account created!');
  setTimeout(()=>goTo('s-classes'),500);
}
async function submitStartup() {
  const fn=v('s-fn'),sn=v('s-sn'),em=v('s-em'),pw=v('s-pw'),ind=v('s-ind'),loc=v('s-loc'),sz=v('s-sz'),ro=v('s-ro');
  const err=document.getElementById('startup-err');err.classList.remove('show');
  if(!fn||!sn||!em||!pw||!ind||!loc||!sz||!ro){showErr(err,'Please fill in all fields.');return;}
  if(pw.length<8){showErr(err,'Password must be at least 8 characters.');return;}
  S.firstName=fn.split(' ')[0];S.email=em;S.startupName=sn;S.industry=ind;S.location=loc;S.teamSize=sz;S.roleHiring=ro;S.desc=v('s-desc');
  const btn=document.getElementById('btn-startup');btn.disabled=true;btn.innerHTML='Creating... <i class="fas fa-spinner fa-spin"></i>';
  await new Promise(r=>setTimeout(r,800));
  btn.disabled=false;btn.innerHTML='Create Account <i class="fas fa-arrow-right"></i>';
  showToast('✅ Account created!');
  setTimeout(()=>{buildSVGrid();goTo('s-startup-values');},500);
}
function showErr(el,msg){el.innerHTML=msg;el.classList.add('show');}

// ── CLASSES ──
function addCls() {
  const inp=document.getElementById('c-inp'),val=inp.value.trim();
  if(!val)return;
  if(S.classes.includes(val)){showToast('Already added!');return;}
  S.classes.push(val);inp.value='';inp.focus();
  renderCls();updateChips();
}
function removeCls(n) {
  S.classes=S.classes.filter(c=>c!==n);renderCls();updateChips();
}
function renderCls() {
  const el=document.getElementById('c-tags');
  if(!S.classes.length){el.innerHTML='<span style="font-size:0.76rem;color:var(--tan);font-style:italic;">Your classes appear here...</span>';return;}
  el.innerHTML=S.classes.map(c=>`<div class="ctag">${escHtml(c)}<button onclick="removeCls(${JSON.stringify(c)})"><i class="fas fa-times"></i></button></div>`).join('');
}
function updateChips() {
  S.skills=extractSkills(S.classes);
  const el=document.getElementById('c-chips'),btn=document.getElementById('btn-cls');
  if(!S.skills.length){el.innerHTML='<span class="ins-empty">Add classes above to reveal your hidden value...</span>';btn.disabled=true;return;}
  el.innerHTML=S.skills.map(s=>`<div class="ins-chip"><i class="fas ${icoMap[s]||'fa-star'}"></i> ${s}</div>`).join('');
  btn.disabled=false;
}
function extractSkills(classes) {
  const found=new Set(),low=classes.map(c=>c.toLowerCase());
  SMAP.forEach(({keys,skill})=>{if(low.some(c=>keys.some(k=>c.includes(k))))found.add(skill);});
  if(classes.length>0&&!found.size)['Critical Thinking','Research & Analysis','Written Communication'].forEach(s=>found.add(s));
  return[...found];
}
function toValues() {
  if(!S.classes.length){showToast('Add at least one class first.');return;}
  buildVGrid();goTo('s-values');
}

// ── VALUES ──
function buildVGrid() {
  document.getElementById('v-grid').innerHTML=VALS.map((v,i)=>`<div class="vchip" id="vc${i}" onclick="togVal(${i},'${v.n}')"><span class="vi">${v.i}</span><span class="vn">${v.n}</span></div>`).join('');
}
function togVal(i,n) {
  const c=document.getElementById('vc'+i);
  if(S.values.includes(n)){S.values=S.values.filter(x=>x!==n);c.classList.remove('sel');}
  else{if(S.values.length>=4){showToast('Max 4 values — deselect one first!');return;}S.values.push(n);c.classList.add('sel');}
  for(let d=0;d<4;d++)document.getElementById('vd'+d).classList.toggle('on',d<S.values.length);
  document.getElementById('v-cnt').textContent=S.values.length;
  document.getElementById('btn-vals').disabled=!S.values.length;
}
async function submitValues() {
  if(!S.values.length){showToast('Pick at least 1 value.');return;}
  const btn=document.getElementById('btn-vals');btn.disabled=true;btn.innerHTML='Saving... <i class="fas fa-spinner fa-spin"></i>';
  await new Promise(r=>setTimeout(r,600));
  btn.disabled=false;btn.innerHTML='See My Dashboard <i class="fas fa-arrow-right"></i>';
  buildHumDash();goTo('s-dash');showToast('🎉 Welcome to Lumen!');
}

// ── STARTUP VALUES ──
function buildSVGrid() {
  S.startupValues=[];
  document.getElementById('sv-grid').innerHTML=VALS.map((v,i)=>`<div class="vchip" id="svc${i}" onclick="togSVal(${i},'${v.n}')"><span class="vi">${v.i}</span><span class="vn">${v.n}</span></div>`).join('');
  document.getElementById('sv-cnt').textContent=0;
  for(let d=0;d<4;d++)document.getElementById('svd'+d).classList.remove('on');
  document.getElementById('btn-sv').disabled=true;
}
function togSVal(i,n) {
  const c=document.getElementById('svc'+i);
  if(S.startupValues.includes(n)){S.startupValues=S.startupValues.filter(x=>x!==n);c.classList.remove('sel');}
  else{if(S.startupValues.length>=4){showToast('Max 4 values.');return;}S.startupValues.push(n);c.classList.add('sel');}
  for(let d=0;d<4;d++)document.getElementById('svd'+d).classList.toggle('on',d<S.startupValues.length);
  document.getElementById('sv-cnt').textContent=S.startupValues.length;
  document.getElementById('btn-sv').disabled=!S.startupValues.length;
}
async function submitStartupValues() {
  if(!S.startupValues.length)return;
  const btn=document.getElementById('btn-sv');btn.disabled=true;btn.innerHTML='Submitting... <i class="fas fa-spinner fa-spin"></i>';
  S.values=S.startupValues;
  await new Promise(r=>setTimeout(r,700));
  btn.disabled=false;btn.innerHTML='View My Candidates <i class="fas fa-arrow-right"></i>';
  buildStartupDash();goTo('s-pending');
}

// ── HUM DASHBOARD ──
function buildHumDash() {
  const n=S.firstName||'there';
  document.getElementById('d-uname').textContent=n+(S.lastName?' '+S.lastName:'');
  document.getElementById('d-ava').textContent=(n[0]||'U').toUpperCase();
  document.getElementById('d-fname').textContent=n;
  const score=Math.min(99,50+(S.skills.length*3)+(S.values.length*4));
  document.getElementById('d-score').textContent=score+'%';
  document.getElementById('d-skills').innerHTML=S.skills.slice(0,6).map(s=>`<span class="vb-skill"><i class="fas ${icoMap[s]||'fa-star'}"></i> ${s}</span>`).join('')||'<span style="color:rgba(255,255,255,0.3);font-size:0.8rem;">Add classes to see your skills</span>';
  document.getElementById('d-vc').textContent=S.values.length;
  document.getElementById('d-cc').textContent=S.classes.length;
  document.getElementById('d-mc').textContent=STARTUPS.length;
  document.getElementById('p-name').textContent=n+(S.lastName?' '+S.lastName:'');
  document.getElementById('p-email').textContent=S.email;
  document.getElementById('p-major').textContent=S.major||'—';
  document.getElementById('p-school').textContent=S.school||'—';
  document.getElementById('p-vals').innerHTML=S.values.map(v=>`<span class="modal-pill gold">${v}</span>`).join('');
  document.getElementById('p-skills').innerHTML=S.skills.map(s=>`<span class="vb-skill"><i class="fas ${icoMap[s]||'fa-star'}"></i> ${s}</span>`).join('');
  renderFeed();renderMatchPanel();renderMsgThreads();renderInterviews();updateBadges();
}
function updateBadges() {
  const cc=S.connectedStartups.length;
  document.getElementById('match-badge').textContent=cc;
  document.getElementById('mn-badge').textContent=cc;
  if(cc>0){document.getElementById('mn-badge').style.display='flex';}
  const msgCount=Object.values(CHATS).flat().filter(m=>m.sender==='them').length;
  document.getElementById('msg-badge').textContent=msgCount;
  document.getElementById('mn-msg-badge').textContent=msgCount;
  if(msgCount>0)document.getElementById('mn-msg-badge').style.display='flex';
}
function renderFeed() {
  const el=document.getElementById('d-feed');
  el.innerHTML='<div class="startup-list">'+STARTUPS.slice(0,3).map(s=>supCard(s)).join('')+'</div>';
}
function supCard(s) {
  const ov=(s.values||[]).filter(v=>S.values.includes(v));
  const isConn=S.connectedStartups.includes(s.id);
  return `<div class="sup-card">
    <div class="sup-logo" style="background:${s.bg}">${s.icon}</div>
    <div class="sup-info">
      <div class="sup-top"><div class="sup-name">${escHtml(s.name)}</div><div class="sup-pct">${s.match}% match</div></div>
      <div class="sup-meta">${escHtml(s.meta)}</div>
      <div class="sup-role"><i class="fas fa-briefcase"></i> ${escHtml(s.role)}</div>
      <div class="sup-tags">${s.values.map(v=>`<span class="tag ${ov.includes(v)?'m':''}">${ov.includes(v)?'✓ ':''}${escHtml(v)}</span>`).join('')}</div>
      <div class="sup-why">💡 ${escHtml(s.why)}</div>
      <div class="sup-acts">
        <button class="btn-sp" onclick='openProfile(${JSON.stringify(s.id)})'><i class="fas fa-eye"></i> View Profile</button>
        ${isConn
          ?`<button class="btn-sc connected" disabled><i class="fas fa-check"></i> Connected</button><button class="btn-so" onclick='openChat(${JSON.stringify(s.id)})'><i class="fas fa-comment"></i> Message</button>`
          :`<button class="btn-sc" onclick='connectStartup(${JSON.stringify(s.id)})'><i class="fas fa-link"></i> Connect</button>`}
      </div>
    </div>
  </div>`;
}
function renderMatchPanel() {
  const el=document.getElementById('m-feed');
  el.innerHTML='<div class="startup-list">'+STARTUPS.map(s=>supCard(s)).join('')+'</div>';
}
function filterMatches(f,btn) {
  document.querySelectorAll('.mf-btn').forEach(b=>b.classList.remove('active'));
  btn.classList.add('active');
  const el=document.getElementById('m-feed');
  const items=f==='all'?STARTUPS:f==='connected'?STARTUPS.filter(s=>S.connectedStartups.includes(s.id)):STARTUPS.filter(s=>!S.connectedStartups.includes(s.id));
  el.innerHTML=items.length?'<div class="startup-list">'+items.map(s=>supCard(s)).join('')+'</div>':`<div class="empty-state"><span class="ei">🔍</span><h3>No ${f} matches</h3><p>Nothing here yet.</p></div>`;
}
function renderInterviews() {
  const el=document.getElementById('int-list');
  if(!S.scheduledInterviews||!S.scheduledInterviews.length){el.innerHTML=`<div class="empty-state"><span class="ei">📅</span><h3>No interviews yet</h3><p>Connect with startups to get interview invitations.</p></div>`;return;}
  el.innerHTML=S.scheduledInterviews.map(int=>`<div class="int-card">
    <div class="int-header">
      <div class="int-icon" style="background:${int.bg}">${int.icon}</div>
      <div class="int-info"><h3>${escHtml(int.company)}</h3><p>${escHtml(int.role)}</p></div>
      <div class="int-status ${int.status}">${int.status==='upcoming'?'<i class="fas fa-check"></i> Confirmed':'<i class="fas fa-clock"></i> Pending'}</div>
    </div>
    <div class="int-details">
      <div class="int-detail"><div class="label">Date</div><div class="value">${escHtml(int.date)}</div></div>
      <div class="int-detail"><div class="label">Time</div><div class="value">${escHtml(int.time)}</div></div>
      <div class="int-detail"><div class="label">Format</div><div class="value">${escHtml(int.format)}</div></div>
      <div class="int-detail"><div class="label">Status</div><div class="value" style="color:var(--green);">${int.status==='upcoming'?'Confirmed':'Awaiting confirmation'}</div></div>
    </div>
    <div class="int-actions">
      <button class="btn-sp"><i class="fas fa-video"></i> Join Call</button>
      <button class="btn-so">Reschedule</button>
    </div>
  </div>`).join('');
}

// ── CONNECT ──
function connectStartup(sid) {
  if(S.connectedStartups.includes(sid)){showToast('Already connected!');return;}
  S.connectedStartups.push(sid);
  const s=STARTUPS.find(x=>x.id===sid);
  if(!CHATS[sid])CHATS[sid]=[];
  renderFeed();renderMatchPanel();updateBadges();
  showToast(`✅ Connected with ${s.name}!`);
  setTimeout(()=>{
    const msg=`Hi ${S.firstName}! 👋 We saw your profile on Lumen and are really impressed. Your background looks like a great fit for our ${s.role} role. Would love to chat — when are you available?`;
    CHATS[sid].push({sender:'them',text:msg,time:now()});
    updateBadges();renderMsgThreads();
    if(S.activeChat===sid)renderChatMessages(sid);
  },1800);
}

// ── PROFILE MODAL ──
let currentModalId=null;
function openProfile(sid) {
  const s=STARTUPS.find(x=>x.id===sid);if(!s)return;
  currentModalId=sid;
  const ov=(s.values||[]).filter(v=>S.values.includes(v));
  document.getElementById('m-logo').textContent=s.icon;
  document.getElementById('m-logo').style.background=s.bg;
  document.getElementById('m-name').textContent=s.name;
  document.getElementById('m-meta').textContent=s.meta;
  document.getElementById('m-about').textContent=s.about;
  document.getElementById('m-role-detail').textContent=`Looking for a ${s.role} — someone who can bridge the human side of their product and team.`;
  document.getElementById('m-vals').innerHTML=s.values.map(v=>`<span class="modal-pill ${ov.includes(v)?'gold':''}">${escHtml(v)}</span>`).join('');
  document.getElementById('m-why').textContent=s.why;
  const isConn=S.connectedStartups.includes(sid);
  document.getElementById('m-connect-btn').innerHTML=isConn?'<i class="fas fa-comment"></i> Open Chat':'Connect <i class="fas fa-arrow-right"></i>';
  document.getElementById('profile-modal').classList.remove('hidden');
}
function closeModal(){document.getElementById('profile-modal').classList.add('hidden');}
function connectFromModal() {
  if(S.connectedStartups.includes(currentModalId)){closeModal();openChat(currentModalId);switchPanel('messages',null);}
  else{connectStartup(currentModalId);closeModal();}
}

// ── MESSAGES ──
function renderMsgThreads() {
  const wrap=document.getElementById('msg-threads');
  const connected=STARTUPS.filter(s=>S.connectedStartups.includes(s.id));
  if(!connected.length){wrap.innerHTML=`<div style="padding:1.2rem;text-align:center;color:var(--tan);font-size:0.79rem;font-style:italic;">Connect with startups to start chatting</div>`;return;}
  wrap.innerHTML=connected.map(s=>{
    const msgs=CHATS[s.id]||[];
    const last=msgs[msgs.length-1];
    return `<div class="msg-thread ${S.activeChat===s.id?'active':''}" onclick="openChat('${s.id}')">
      <div class="msg-thread-ico" style="background:${s.bg}">${s.icon}</div>
      <div class="msg-thread-info">
        <div class="msg-thread-name">${escHtml(s.name)}</div>
        <div class="msg-thread-preview">${last?escHtml(last.text):'No messages yet'}</div>
      </div>
      <div class="msg-thread-time">${last?last.time:''}</div>
    </div>`;
  }).join('');
}
function openChat(sid) {
  S.activeChat=sid;
  const s=STARTUPS.find(x=>x.id===sid);if(!s)return;
  renderMsgThreads();
  document.getElementById('msg-main').innerHTML=`
    <div class="msg-header">
      <div class="msg-header-ico" style="background:${s.bg}">${s.icon}</div>
      <div><div class="msg-header-name">${escHtml(s.name)}</div><div class="msg-header-sub">${escHtml(s.role)}</div></div>
    </div>
    <div class="msg-body" id="chat-body"></div>
    <div class="msg-input-row">
      <input class="msg-input" id="msg-inp" placeholder="Type a message..." onkeydown="if(event.key==='Enter')sendMsg('${sid}')">
      <button class="msg-send" onclick="sendMsg('${sid}')"><i class="fas fa-paper-plane"></i></button>
    </div>`;
  renderChatMessages(sid);
}
function renderChatMessages(sid) {
  const body=document.getElementById('chat-body');if(!body)return;
  const msgs=CHATS[sid]||[];
  if(!msgs.length){body.innerHTML=`<div style="text-align:center;color:var(--tan);font-size:0.78rem;font-style:italic;padding:1.8rem;">Start the conversation 👋</div>`;return;}
  body.innerHTML=msgs.map(m=>`<div class="msg-bubble ${m.sender==='me'?'me':'them'}">${escHtml(m.text)}</div>`).join('');
  body.scrollTop=body.scrollHeight;
}
async function sendMsg(sid) {
  const inp=document.getElementById('msg-inp'),text=inp.value.trim();if(!text)return;
  if(!CHATS[sid])CHATS[sid]=[];
  CHATS[sid].push({sender:'me',text,time:now()});
  inp.value='';renderChatMessages(sid);renderMsgThreads();
}
function now(){const d=new Date();return d.getHours()+':'+String(d.getMinutes()).padStart(2,'0');}

// ── STARTUP DASHBOARD ──
function buildStartupDash() {
  const n=S.firstName||'there';
  document.getElementById('sd-uname').textContent=n;
  document.getElementById('sd-ava').textContent=(n[0]||'S').toUpperCase();
  document.getElementById('sd-fname').textContent=n;
  document.getElementById('sd-company').textContent=S.startupName||'Your Company';
  document.getElementById('sd-role-txt').textContent=`Hiring for ${S.roleHiring||'open role'} · ${S.industry||'Tech'} · ${S.location||''}`;
  document.getElementById('sp-company').textContent=S.startupName||'—';
  document.getElementById('sp-industry').textContent=S.industry||'—';
  document.getElementById('sp-role').textContent=S.roleHiring||'—';
  document.getElementById('sp-location').textContent=S.location||'—';
  document.getElementById('sp-vals').innerHTML=(S.values.length?S.values:S.startupValues).map(v=>`<span class="modal-pill gold">${v}</span>`).join('');
  renderCandFeed();renderStartupInterviews();renderStartupMsgThreads();
  // mobile nav
  document.getElementById('startup-mobile-nav').style.display='flex';
  document.getElementById('startup-sidebar').style.display='flex';
}
function renderCandFeed() {
  const el=document.getElementById('sd-feed');
  el.innerHTML='<div class="cand-list">'+CANDIDATES.slice(0,4).map(c=>candCard(c)).join('')+'</div>';
  document.getElementById('cands-feed').innerHTML='<div class="cand-list">'+CANDIDATES.map(c=>candCard(c)).join('')+'</div>';
}
function candCard(c) {
  const valOverlap=c.values.filter(v=>(S.values.length?S.values:S.startupValues).includes(v));
  const hasChat=CAND_CHATS[c.id]&&CAND_CHATS[c.id].length>0;
  return `<div class="cand-card">
    <div class="cand-ava" style="background:${c.bg}">${c.ava}</div>
    <div class="cand-info">
      <div class="cand-top"><div class="cand-name">${escHtml(c.name)}</div><div class="cand-pct">${c.match}% match</div></div>
      <div class="cand-meta">${escHtml(c.major)} · ${escHtml(c.school)} · ${c.year}</div>
      <div class="cand-skills">${c.skills.slice(0,4).map(s=>`<span class="cand-skill ${(S.values.length?S.values:S.startupValues).some(v=>s.toLowerCase().includes(v.toLowerCase()))?'m':''}">${escHtml(s)}</span>`).join('')}</div>
      <div class="cand-why">💡 ${escHtml(c.why.substring(0,100))}...</div>
      <div class="cand-acts">
        <button class="btn-sp" onclick='openCandProfile(${JSON.stringify(c.id)})'><i class="fas fa-eye"></i> View Profile</button>
        ${hasChat?`<button class="btn-so" onclick='openStartupChat(${JSON.stringify(c.id)})'><i class="fas fa-comment"></i> Message</button>`:`<button class="btn-sc" onclick='msgCandidate(${JSON.stringify(c.id)})'><i class="fas fa-paper-plane"></i> Message</button>`}
        <button class="btn-so" onclick='openCandProfile(${JSON.stringify(c.id)})'><i class="fas fa-calendar-plus"></i> Interview</button>
      </div>
    </div>
  </div>`;
}
function filterCands(f,btn){
  document.querySelectorAll('.mf-btn').forEach(b=>b.classList.remove('active'));btn.classList.add('active');
  const el=document.getElementById('cands-feed');
  const items=f==='all'?CANDIDATES:f==='new'?CANDIDATES.filter((_,i)=>i>=4):f==='shortlisted'?CANDIDATES.slice(0,3):CANDIDATES.slice(0,2);
  el.innerHTML=items.length?'<div class="cand-list">'+items.map(c=>candCard(c)).join('')+'</div>':`<div class="empty-state"><span class="ei">🔍</span><h3>No ${f} candidates</h3></div>`;
}

// ── CAND MODAL ──
let currentCandId=null;
function openCandProfile(cid) {
  const c=CANDIDATES.find(x=>x.id===cid);if(!c)return;
  currentCandId=cid;
  document.getElementById('cm-ava').textContent=c.ava;
  document.getElementById('cm-ava').style.background=c.bg;
  document.getElementById('cm-name').textContent=c.name;
  document.getElementById('cm-meta').textContent=`${c.major} · ${c.school} · Class of ${c.year}`;
  document.getElementById('cm-edu').textContent=`${c.major} degree from ${c.school}. Graduating ${c.year}. Strong academic background in human behavior, research methods, and applied social science.`;
  document.getElementById('cm-skills').innerHTML=c.skills.map(s=>`<div class="ins-chip"><i class="fas ${icoMap[s]||'fa-star'}"></i> ${s}</div>`).join('');
  document.getElementById('cm-vals').innerHTML=c.values.map(v=>`<span class="modal-pill gold">${v}</span>`).join('');
  document.getElementById('cm-why').textContent=c.why;
  document.getElementById('cand-modal').classList.remove('hidden');
}
function closeCandModal(){document.getElementById('cand-modal').classList.add('hidden');}
function scheduleInterview() {
  const c=CANDIDATES.find(x=>x.id===currentCandId);if(!c)return;
  closeCandModal();
  showToast(`📅 Interview request sent to ${c.name}!`);
}
function msgCandidate(cid) {
  const c=CANDIDATES.find(x=>x.id===cid);if(!c)return;
  if(!CAND_CHATS[cid])CAND_CHATS[cid]=[];
  CAND_CHATS[cid].push({sender:'me',text:`Hi ${c.name.split(' ')[0]}! We came across your profile on Lumen and are really impressed. Your background in ${c.major} is a great fit for our ${S.roleHiring||'open'} role. Would you be open to a quick call?`,time:now()});
  renderCandFeed();renderStartupMsgThreads();
  switchStartupPanel('smessages',null);
  showToast(`✅ Message sent to ${c.name}!`);
  setTimeout(()=>{
    if(!CAND_CHATS[cid])return;
    CAND_CHATS[cid].push({sender:'them',text:`Hi! Yes, I'd love to learn more. ${S.startupName||'Your company'}'s mission really resonates with me.`,time:now()});
    renderStartupMsgThreads();
    if(S.activeCandChat===cid)renderStartupChatMessages(cid);
  },2000);
}

// ── STARTUP INTERVIEWS ──
function renderStartupInterviews() {
  const el=document.getElementById('s-int-list');
  if(!S.scheduledCandInterviews||!S.scheduledCandInterviews.length){el.innerHTML=`<div class="empty-state"><span class="ei">📅</span><h3>No interviews yet</h3><p>Message candidates to schedule interviews.</p></div>`;return;}
  el.innerHTML=S.scheduledCandInterviews.map(int=>`<div class="int-card">
    <div class="int-header">
      <div class="cand-ava" style="background:${int.bg};width:44px;height:44px;font-size:1.1rem;">${int.ava}</div>
      <div class="int-info"><h3>${escHtml(int.name)}</h3><p>${escHtml(int.major)} · ${int.match}% match</p></div>
      <div class="int-status ${int.status}">${int.status==='upcoming'?'<i class="fas fa-check"></i> Confirmed':'<i class="fas fa-clock"></i> Pending'}</div>
    </div>
    <div class="int-details">
      <div class="int-detail"><div class="label">Date</div><div class="value">${escHtml(int.date)}</div></div>
      <div class="int-detail"><div class="label">Time</div><div class="value">${escHtml(int.time)}</div></div>
      <div class="int-detail"><div class="label">Format</div><div class="value">${escHtml(int.format)}</div></div>
    </div>
    <div class="int-actions">
      <button class="btn-sp"><i class="fas fa-video"></i> Join Call</button>
      <button class="btn-so">Reschedule</button>
    </div>
  </div>`).join('');
}

// ── STARTUP MESSAGES ──
function renderStartupMsgThreads() {
  const wrap=document.getElementById('s-msg-threads');
  const hasMsgs=Object.keys(CAND_CHATS).filter(k=>CAND_CHATS[k].length>0);
  if(!hasMsgs.length){wrap.innerHTML=`<div style="padding:1.2rem;text-align:center;color:var(--tan);font-size:0.79rem;font-style:italic;">Message candidates to start chatting</div>`;return;}
  wrap.innerHTML=hasMsgs.map(cid=>{
    const c=CANDIDATES.find(x=>x.id===cid);if(!c)return'';
    const msgs=CAND_CHATS[cid];
    const last=msgs[msgs.length-1];
    return `<div class="msg-thread ${S.activeCandChat===cid?'active':''}" onclick="openStartupChat('${cid}')">
      <div class="msg-thread-ico" style="background:${c.bg}">${c.ava}</div>
      <div class="msg-thread-info">
        <div class="msg-thread-name">${escHtml(c.name)}</div>
        <div class="msg-thread-preview">${last?escHtml(last.text):''}</div>
      </div>
      <div class="msg-thread-time">${last?last.time:''}</div>
    </div>`;
  }).join('');
  document.getElementById('s-msg-badge').textContent=hasMsgs.length;
}
function openStartupChat(cid) {
  S.activeCandChat=cid;
  const c=CANDIDATES.find(x=>x.id===cid);if(!c)return;
  renderStartupMsgThreads();
  document.getElementById('s-msg-main').innerHTML=`
    <div class="msg-header">
      <div class="msg-header-ico" style="background:${c.bg}">${c.ava}</div>
      <div><div class="msg-header-name">${escHtml(c.name)}</div><div class="msg-header-sub">${escHtml(c.major)}</div></div>
    </div>
    <div class="msg-body" id="s-chat-body"></div>
    <div class="msg-input-row">
      <input class="msg-input" id="s-msg-inp" placeholder="Type a message..." onkeydown="if(event.key==='Enter')sendStartupMsg('${cid}')">
      <button class="msg-send" onclick="sendStartupMsg('${cid}')"><i class="fas fa-paper-plane"></i></button>
    </div>`;
  renderStartupChatMessages(cid);
}
function renderStartupChatMessages(cid) {
  const body=document.getElementById('s-chat-body');if(!body)return;
  const msgs=CAND_CHATS[cid]||[];
  body.innerHTML=msgs.map(m=>`<div class="msg-bubble ${m.sender==='me'?'me':'them'}">${escHtml(m.text)}</div>`).join('');
  body.scrollTop=body.scrollHeight;
}
function sendStartupMsg(cid) {
  const inp=document.getElementById('s-msg-inp'),text=inp.value.trim();if(!text)return;
  if(!CAND_CHATS[cid])CAND_CHATS[cid]=[];
  CAND_CHATS[cid].push({sender:'me',text,time:now()});
  inp.value='';renderStartupChatMessages(cid);renderStartupMsgThreads();
}

// ── PANEL SWITCHERS ──
function switchPanel(name,el) {
  document.querySelectorAll('#s-dash .panel').forEach(p=>p.classList.remove('active'));
  document.getElementById('panel-'+name).classList.add('active');
  if(el){document.querySelectorAll('#s-dash .si').forEach(s=>s.classList.remove('active'));el.classList.add('active');}
}
function switchPanelM(name,idx) {
  switchPanel(name,null);
  document.querySelectorAll('#hum-mobile-nav .mn-item').forEach((b,i)=>b.classList.toggle('active',i===idx));
}
function switchStartupPanel(name,el) {
  document.querySelectorAll('#s-startup-dash .panel').forEach(p=>p.classList.remove('active'));
  document.getElementById('panel-'+name).classList.add('active');
  if(el){document.querySelectorAll('#startup-sidebar .si').forEach(s=>s.classList.remove('active'));el.classList.add('active');}
}
function switchStartupPanelM(name,idx) {
  switchStartupPanel(name,null);
  document.querySelectorAll('#startup-mobile-nav .mn-item').forEach((b,i)=>b.classList.toggle('active',i===idx));
}

// ── AUTH ──
function doLogin() {
  const em=document.getElementById('li-em').value.trim();
  const pw=document.getElementById('li-pw').value.trim();
  const err=document.getElementById('login-err');err.classList.remove('show');
  if(!em||!pw){showErr(err,'Please enter your email and password.');return;}
  showErr(err,'Demo mode: use the demo instead. <a onclick="goTo(\'s-demo\')" style="cursor:pointer;color:var(--gold);text-decoration:underline;">Try the demo →</a>');
  err.classList.add('show');
}
function doLogout() {
  S={role:null,demoRole:null,firstName:'',lastName:'',email:'',major:'',school:'',gradYear:'',startupName:'',industry:'',location:'',teamSize:'',roleHiring:'',desc:'',classes:[],skills:[],values:[],matches:[],connectedStartups:[],activeChat:null,startupValues:[],activeCandChat:null,scheduledInterviews:[],scheduledCandInterviews:[]};
  Object.keys(CHATS).forEach(k=>delete CHATS[k]);
  Object.keys(CAND_CHATS).forEach(k=>delete CAND_CHATS[k]);
  goTo('s-land');showToast('Signed out.');
}

// ── UTILS ──
function escHtml(str){return String(str||'').replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;');}
let _tt;
function showToast(m){const e=document.getElementById('tst');e.textContent=m;e.classList.add('show');clearTimeout(_tt);_tt=setTimeout(()=>e.classList.remove('show'),3200);}

// ── INIT ──
function init() {
  buildVGrid();
  // demo responsive: on mobile show both mobile navs correctly
  const isMobile=window.innerWidth<768;
  if(isMobile){
    document.getElementById('startup-sidebar').style.setProperty('display','none','important');
  }
  document.getElementById('loading').classList.add('hidden');
  document.getElementById('s-land').classList.add('active');
}

// close modals on overlay click
document.getElementById('profile-modal').addEventListener('click',function(e){if(e.target===this)closeModal();});
document.getElementById('cand-modal').addEventListener('click',function(e){if(e.target===this)closeCandModal();});

window.addEventListener('load',init);
</script>
</body>
</html>
