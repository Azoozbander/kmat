<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<meta name="color-scheme" content="light">
<title>شطرنج هادئ</title>
<style>
:root{color-scheme:light;--bg:#fcfcf9;--ink:#3a4743;--sub:#85918c;--card:#ffffff;--dot:#5f8a7a;--sel:#f8e6b8;--last:#e8f0c4;--ck:#f4c8c2;box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
html{scroll-padding-top:env(safe-area-inset-top,0px)}
*{box-sizing:border-box}
body{margin:0;background:var(--bg);color:var(--ink);font-family:"Segoe UI",Tahoma,system-ui,sans-serif;min-height:100vh}
section{display:flex;flex-direction:column;align-items:center;gap:14px;padding:20px 14px 30px}
[hidden]{display:none!important}
h1{font-size:1.5rem;font-weight:600;margin:6px 0 0}
.sub{color:var(--sub);font-size:.9rem;text-align:center;margin:0}
.card{width:min(94vw,420px);background:var(--card);border-radius:18px;padding:16px;box-shadow:0 4px 18px rgba(58,71,67,.1);border:1px solid #eef0ea;display:flex;flex-direction:column;gap:10px}
.card h2{margin:0;font-size:1.05rem;display:flex;justify-content:space-between;align-items:center}
.tag{font-size:.72rem;padding:3px 10px;border-radius:999px;background:#eef4ec;border:1px solid #cfdccb;font-weight:400}
.row{display:flex;gap:8px;flex-wrap:wrap}
button,input{font:inherit;font-size:.95rem;border:0;border-radius:999px;padding:10px 16px;color:var(--ink)}
button{background:#fff;box-shadow:0 2px 8px rgba(58,71,67,.12);border:1px solid #eef0ea;cursor:pointer;transition:transform .12s,background .2s}
button:active{transform:scale(.95)}
.card button{background:#f3f6f1;box-shadow:none}
.card button:hover{background:#e6eee3}
.card button.on{outline:2px solid var(--dot);background:#e6eee3}
input{background:#f3f6f1;width:110px;text-align:center;direction:ltr;letter-spacing:2px;outline:none}
#st{min-height:1.5em;background:#fff;border:1px solid #eef0ea;padding:8px 20px;border-radius:999px;box-shadow:0 2px 8px rgba(58,71,67,.08);text-align:center;font-size:.95rem}
#bw{container-type:inline-size;width:min(94vw,540px);padding:10px;border-radius:20px;background:var(--fr,#e4ebe0);box-shadow:0 10px 28px rgba(58,71,67,.15)}
#bd{direction:ltr;position:relative;display:grid;grid-template-columns:repeat(8,minmax(0,1fr));grid-template-rows:repeat(8,minmax(0,1fr));aspect-ratio:1/1;border-radius:10px;overflow:hidden}
.q{display:flex;align-items:center;justify-content:center;position:relative;cursor:pointer;font-size:min(9.3cqw,52px);line-height:1;min-width:0;min-height:0;user-select:none;-webkit-tap-highlight-color:transparent;transition:background .25s}
.q.l{background:var(--l)}.q.d{background:var(--d)}
.q.last{background:var(--last)}.q.sel{background:var(--sel)}
.q.ck{background:var(--ck);animation:pl 1.2s ease-in-out infinite}
.q span{position:relative;z-index:2;display:block}
.q.sel span{animation:pop .25s ease-out forwards}
.co{position:absolute;font-size:.62rem;font-style:normal;opacity:.75;z-index:1;pointer-events:none;font-family:system-ui,sans-serif}
.co.f{bottom:2px;right:4px}.co.r{top:2px;left:4px}
.q.l .co{color:var(--d)}.q.d .co{color:#fff}
@keyframes pop{to{transform:translateY(-4px) scale(1.14)}}
@keyframes pl{50%{filter:brightness(1.06)}}
.q.mv::after{content:"";position:absolute;width:26%;height:26%;border-radius:50%;background:var(--dot);opacity:.55;animation:in .2s ease-out}
.q.mv.cap::after{width:84%;height:84%;background:none;border:3px solid var(--dot);opacity:.6}
@keyframes in{from{transform:scale(0)}}
/* color schemes */
.cs1{--wa:#ffffff;--wb:#ece9de;--ba:#46544f;--bb:#1f2a27;--ws:#7d8c85}
.cs2{--wa:#fbe6cc;--wb:#e5bd90;--ba:#4f8582;--bb:#2c5755;--ws:#b98a5c}
.cs3{--wa:#ffffff;--wb:#c9d4cd;--ba:#6a857d;--bb:#1a2522;--ws:#8a9a92}
.cs4{--wa:#fde4e7;--wb:#eeb0b9;--ba:#6a7aab;--bb:#38426b;--ws:#a8707a}
.cs5{--wa:#fff5cc;--wb:#d6ab4a;--ba:#4f9e86;--bb:#17402f;--ws:#9a7a2e}
.w{--a:var(--wa);--b:var(--wb)}.b{--a:var(--ba);--b:var(--bb)}
/* glyph shapes (1,2) */
.gl .w,.gl .b{background-image:linear-gradient(var(--a),var(--b));-webkit-background-clip:text;background-clip:text;color:transparent}
.gl .w{filter:drop-shadow(0 0 .6px var(--ws)) drop-shadow(0 0 .6px var(--ws)) drop-shadow(0 1px 1.5px rgba(0,0,0,.25))}
.gl .b{filter:drop-shadow(0 1px 1.5px rgba(0,0,0,.3))}
.gl.t .w{background-image:linear-gradient(var(--ba),var(--bb));filter:none}
/* disc shapes (3,4,5) */
.dc .w,.dc .b{display:flex;width:78%;aspect-ratio:1/1;align-items:center;justify-content:center;border-radius:50%;background:linear-gradient(var(--a),var(--b));font-size:.58em;font-weight:700;font-family:system-ui,"Segoe UI",Tahoma,sans-serif;color:var(--bb);box-shadow:0 2px 4px rgba(0,0,0,.25),inset 0 1px 2px rgba(255,255,255,.55)}
.dc .b{color:var(--wa)}
.dc.sq .w,.dc.sq .b{border-radius:28%}
.pv{font-weight:400;font-size:1.7rem;display:flex;gap:3px;height:1.9rem;align-items:center}
.pv.dc span{width:1.9rem!important}
.dc.pv .w,.dc.pv .b{font-size:.95rem}
.sv .w,.sv .b{display:block;width:98%;height:98%;filter:drop-shadow(0 3px 2px rgba(0,0,0,.28))}
.sv svg{display:block;width:100%;height:100%;overflow:visible}
.pv.sv span{width:1.95rem!important;height:1.95rem!important}
#cp{color:var(--sub);font-size:1.05rem;display:flex;gap:18px;flex-wrap:wrap;justify-content:center;min-height:1.4em}
.bar{display:flex;gap:8px;flex-wrap:wrap;justify-content:center;width:min(94vw,540px)}
.bar button{padding:9px 14px;font-size:.88rem}
.ovl{position:fixed;inset:0;background:rgba(58,71,67,.3);display:flex;align-items:center;justify-content:center;z-index:20;animation:in .25s}
.ovl .card{align-items:stretch;max-height:86vh;overflow:auto}
#ov .card{align-items:center;text-align:center}
#ot{font-size:1.3rem}
.g{display:grid;grid-template-columns:repeat(auto-fill,minmax(78px,1fr));gap:8px}
.tile{display:flex;flex-direction:column;align-items:center;gap:5px;border-radius:16px!important;padding:10px 6px!important}
.tile .sw{width:46px;height:28px;border-radius:8px;border:1px solid #0001}
.tile .two{display:flex;gap:4px;height:1.9rem;align-items:center}
.tile .two i{width:20px;height:20px;border-radius:50%;box-shadow:0 1px 3px rgba(0,0,0,.25)}
.tile small{font-size:.75rem;color:var(--ink)}
#ts{position:fixed;bottom:calc(20px + env(safe-area-inset-bottom,0px));left:50%;transform:translateX(-50%);background:var(--ink);color:#fff;padding:10px 18px;border-radius:999px;font-size:.9rem;z-index:30;max-width:90vw;text-align:center}
</style>
</head>
<body>
<section id="mn">
<h1>♞ شطرنج هادئ</h1>
<p class="sub">اختر طريقة اللعب</p>
<div class="card"><h2>ضد الكمبيوتر <span class="tag">بدون نت</span></h2>
<div class="row"><button data-l="0">سهل</button><button data-l="1">متوسط</button><button data-l="2">صعب</button></div></div>
<div class="card"><h2>مع خويك بنفس الجوال <span class="tag">بدون نت</span></h2>
<div class="row"><button id="lc">ابدأ</button></div></div>
<div class="card"><h2>لعب سريع مع لاعب عشوائي <span class="tag">أونلاين</span></h2>
<div class="row"><button id="qk">ابحث عن لاعب</button></div>
<p class="sub">يلقى لك أي لاعب فاتح الصفحة الحين. يشتغل مع اللي عندهم صلاحية يفتحون الصفحة وهم مسجلين دخول.</p></div>
<div class="card"><h2>أونلاين مع صديقك <span class="tag">يحتاج نت</span></h2>
<div class="row"><button id="mk">سوّ غرفة</button><input id="cd" placeholder="الكود" maxlength="8"><button id="jn">ادخل</button></div>
<p class="sub">سوّ غرفة وعطِ صديقك الكود. لازم تفتحون الصفحة وأنتم مسجلين دخول.</p></div>
<button id="op2">⚙ الإعدادات</button>
</section>
<section id="gm" hidden>
<div id="st"></div>
<div id="bw"><div id="bd"></div></div>
<div id="cp"></div>
<div class="bar">
<button id="bk">القائمة</button><button id="un">تراجع</button><button id="fp">قلب</button><button id="op">⚙ الإعدادات</button>
</div>
</section>
<div id="ov" class="ovl" hidden><div class="card"><div id="ot"></div><div class="row"><button id="ag">لعبة جديدة</button><button id="cl">إغلاق</button></div></div></div>
<div id="sk" class="ovl" hidden><div class="card" style="align-items:center;text-align:center"><div style="font-size:1.1rem">نبحث عن لاعب...</div><p class="sub">خلّ الصفحة مفتوحة</p><button id="skc">إلغاء</button></div></div>
<div id="set" class="ovl" hidden><div class="card" id="sc"></div></div>
<div id="ts" hidden></div>
<script>
const $=id=>document.getElementById(id);
const U={K:'♚',Q:'♛',R:'♜',B:'♝',N:'♞',P:'♟\uFE0E'};
const V={P:1,N:3,B:3,R:5,Q:9,K:0};
const K8=[[-1,-1],[-1,0],[-1,1],[0,-1],[0,1],[1,-1],[1,0],[1,1]];
const N8=[[-2,-1],[-2,1],[-1,-2],[-1,2],[1,-2],[1,2],[2,-1],[2,1]];
const LT={K:'K',Q:'Q',R:'R',B:'B',N:'N',P:'P'};
const SH=[
{n:'كلاسيك',c:'gl',w:U,b:U},
{n:'تقليدي',c:'gl t',w:{K:'♔',Q:'♕',R:'♖',B:'♗',N:'♘',P:'♙'},b:U},
{n:'حروف',c:'dc sq',w:LT,b:LT},
{n:'رموز',c:'dc',w:{K:'👑',Q:'👸',R:'🏰',B:'⛪',N:'🐴',P:'🪖'},b:{K:'👑',Q:'👸',R:'🏰',B:'⛪',N:'🐴',P:'🪖'}},
{n:'عربي',c:'dc',w:{K:'م',Q:'و',R:'ق',B:'ف',N:'ح',P:'ب'},b:{K:'م',Q:'و',R:'ق',B:'ف',N:'ح',P:'ب'}},
{n:'تماثيل',c:'sv',svg:1}];
const PL={
w:{robe:'#d3d8dc',rs:'#9ea8af',ped:'#8a6a3a',pd:'#5a421f',acc:'#3f5f9a',hair:'#8d8d93',qh:'#e9c258',qr:'#4f8f5a',horse:'#f4f3ee',mane:'#b9b6ac',stone:'#9aa0a5',ss:'#6e7479',met:'#dfe3e6',ms:'#9aa3aa',gold:'#d9ae43'},
b:{robe:'#a9783c',rs:'#7a5226',ped:'#cfd2d6',pd:'#8d9298',acc:'#b3382f',hair:'#d8d8d8',qh:'#b3622f',qr:'#7d3f86',horse:'#a05f32',mane:'#d3d3d3',stone:'#dcc48c',ss:'#a88f55',met:'#b98a45',ms:'#7a5226',gold:'#d9ae43'}};
function SVG(p){
  const c=PL[p[0]],t=p[1],sk='#ecc9a0',st=`stroke="${c.rs}" stroke-width="1.5"`;
  const ped=`<g fill="${c.ped}" stroke="${c.pd}" stroke-width="1.5"><path d="M36 90 L40 76 H60 L64 90Z"/><rect x="31" y="72" width="38" height="6" rx="2.5"/><rect x="27" y="89" width="46" height="7" rx="3"/></g>`;
  const sh=f=>`<path d="M27 74 Q27 55 50 53 Q73 55 73 74Z" fill="${f}" ${st}/>`;
  const pads=`<circle cx="33" cy="61" r="5" fill="${c.met}" stroke="${c.ms}"/><circle cx="67" cy="61" r="5" fill="${c.met}" stroke="${c.ms}"/>`;
  const eyes=`<circle cx="46" cy="38" r="1.2" fill="#333"/><circle cx="54" cy="38" r="1.2" fill="#333"/>`;
  const beard=`<path d="M40 40 Q50 68 60 40 Q57 50 50 50 Q43 50 40 40Z" fill="${c.hair}"/>`;
  let b,k=1;
  if(t=='K'){k=1;b=sh(c.robe)+pads+`<path d="M43 55 L50 66 L57 55Z" fill="${c.acc}"/><circle cx="50" cy="38" r="10" fill="${sk}"/>${beard}${eyes}<path d="M39 31 L39 20 L45 26 L50 17 L55 26 L61 20 L61 31Z" fill="${c.gold}" stroke="#a07f20"/>`}
  else if(t=='Q'){k=.97;b=`<path d="M37 36 Q34 62 40 68 H60 Q66 62 63 36 Q50 20 37 36Z" fill="${c.qh}"/>`+sh(c.qr)+`<path d="M42 55 L50 66 L58 55" fill="none" stroke="${c.gold}" stroke-width="1.6"/><circle cx="50" cy="39" r="9" fill="${sk}"/>${eyes.replace(/cy="38"/g,'cy="39"')}<path d="M41 31 L42 24 L46 28 L50 21 L54 28 L58 24 L59 31Z" fill="${c.gold}" stroke="#a07f20"/><circle cx="45" cy="57" r="1.2" fill="#fff"/><circle cx="50" cy="60" r="1.2" fill="#fff"/><circle cx="55" cy="57" r="1.2" fill="#fff"/>`}
  else if(t=='B'){k=.93;b=sh(c.qr)+`<path d="M50 55 V73 M44 62 H56" stroke="${c.gold}" stroke-width="1.6"/><circle cx="50" cy="38" r="10" fill="${sk}"/>${beard}${eyes}<path d="M40 31 L50 7 L60 31Z" fill="${c.acc}" stroke="${c.gold}"/><path d="M41 28 H59" stroke="${c.gold}" stroke-width="2"/><path d="M50 13 V23 M46 18 H54" stroke="${c.gold}" stroke-width="1.5"/>`}
  else if(t=='N'){k=.95;b=`<path d="M32 74 C30 58 34 44 44 34 L42 24 L50 29 C58 24 66 28 70 36 L76 42 C77 46 72 48 68 47 C66 52 62 55 58 56 C60 62 62 68 62 74Z" fill="${c.horse}" ${st}/><path d="M32 74 C30 58 34 44 44 34 L50 30 C45 42 43 56 45 74Z" fill="${c.mane}" ${st}/><circle cx="59" cy="36" r="1.7" fill="#2b2b2b"/><circle cx="72" cy="43" r="1" fill="#2b2b2b"/><path d="M58 33 L67 44" stroke="${c.acc}" stroke-width="1.6"/><path d="M28 74 Q30 64 40 62 L62 66 L66 74Z" fill="${c.acc}"/>`}
  else if(t=='R'){k=.9;b=`<path d="M38 72 L40 34 H60 L62 72Z" fill="${c.stone}" ${st}/><path d="M36 34 V22 H42 V27 H47 V22 H53 V27 H58 V22 H64 V34Z" fill="${c.stone}" ${st}/><path d="M39 50 H61 M39 62 H61 M45 34 V50 M55 50 V62" stroke="${c.ss}" stroke-width=".8" fill="none"/><path d="M47 72 V62 Q50 57 53 62 V72Z" fill="#3a2f26"/><rect x="48" y="40" width="4" height="8" rx="2" fill="#3a2f26"/>`}
  else{k=.8;b=sh(c.met)+pads+`<path d="M50 24 Q58 14 64 20 Q58 20 54 26Z" fill="${c.acc}"/><path d="M39 46 V38 Q39 24 50 24 Q61 24 61 38 V46 Q50 50 39 46Z" fill="${c.met}" stroke="${c.ms}" stroke-width="1.5"/><rect x="41" y="36" width="18" height="3" rx="1.5" fill="#2b2b2b"/><path d="M50 24 V46" stroke="${c.ms}"/>`}
  return `<svg viewBox="0 0 100 100" aria-hidden="true"><g transform="translate(50 96) scale(${k}) translate(-50 -96)">${ped}${b}</g></svg>`;
}
function setP(el,p,i=sh-1){const s=SH[i];if(s.svg)el.innerHTML=SVG(p);else el.textContent=s[p[0]][p[1]]}
const CN=['كلاسيك','رملي','مجسّم','وردي','ذهبي'],SPN=['سريع','عادي','بطيء'];
const PAL=[
{n:'مريمي',c:['#f4f6ee','#b4c9b6','#e4ebe0']},
{n:'بحري',c:['#f1f6f9','#b3cadb','#dfe9f0']},
{n:'رملي',c:['#f8f1e4','#d6bf9f','#eee3cf']},
{n:'لافندر',c:['#f3f0f8','#c4bbd9','#e6e0f0']},
{n:'رمادي',c:['#f1f2f2','#b4bdbf','#e3e6e7']}];
const G=p=>SH[sh-1][p[0]][p[1]];
let S,H=[],mode='',lv=1,me='w',fl=false,busy=false,ab=false,sel=null,mv=[],room=null,code='',shown=null;
let sh=1,cs=1,bt=1,spd=1,snd=1,hint=1;
try{const o=JSON.parse(localStorage.getItem('chs3')||'{}');sh=o.sh||1;cs=o.cs||1;bt=o.bt||1;spd=o.spd??1;snd=o.snd??1;hint=o.hint??1}catch(e){}
function save(){try{localStorage.setItem('chs3',JSON.stringify({sh,cs,bt,spd,snd,hint}))}catch(e){}}
const dur=()=>[220,400,650][spd];

function fresh(){
  const o='RNBQKBNR'.split('');
  const b=[o.map(x=>'b'+x),Array(8).fill('bP')];
  for(let i=0;i<4;i++)b.push(Array(8).fill(null));
  b.push(Array(8).fill('wP'),o.map(x=>'w'+x));
  return{b,t:'w',rt:{wK:1,wQ:1,bK:1,bQ:1},last:null,lc:null,res:null,chk:false,cap:{w:[],b:[]}};
}
function att(b,r,c,by){
  const g=(y,x)=>y>=0&&y<8&&x>=0&&x<8?b[y][x]:null;
  const d=by=='w'?1:-1;
  for(const x of[-1,1])if(g(r+d,c+x)==by+'P')return 1;
  for(const[y,x]of N8)if(g(r+y,c+x)==by+'N')return 1;
  for(const[y,x]of K8)if(g(r+y,c+x)==by+'K')return 1;
  for(const[y,x]of K8){
    let yy=r+y,xx=c+x;
    while(yy>=0&&yy<8&&xx>=0&&xx<8){
      const p=b[yy][xx];
      if(p){if(p[0]==by&&(p[1]=='Q'||p[1]==(y&&x?'B':'R')))return 1;break}
      yy+=y;xx+=x;
    }
  }
  return 0;
}
function findK(b,o){for(let r=0;r<8;r++)for(let c=0;c<8;c++)if(b[r][c]==o+'K')return[r,c]}
function chk(b,o){const k=findK(b,o);return k?att(b,k[0],k[1],o=='w'?'b':'w'):0}
function gen(b,r,c,rt){
  const p=b[r][c],o=p[0],t=p[1],en=o=='w'?'b':'w',m=[];
  const add=(y,x)=>{
    if(y<0||y>7||x<0||x>7)return 0;
    const q=b[y][x];
    if(!q){m.push([y,x]);return 1}
    if(q[0]==en)m.push([y,x]);
    return 0;
  };
  if(t=='P'){
    const d=o=='w'?-1:1;
    if(b[r+d]&&!b[r+d][c]){
      m.push([r+d,c]);
      if(r==(o=='w'?6:1)&&!b[r+2*d][c])m.push([r+2*d,c]);
    }
    for(const x of[-1,1]){const q=b[r+d]?.[c+x];if(q&&q[0]==en)m.push([r+d,c+x])}
  }else if(t=='N'){for(const[y,x]of N8)add(r+y,c+x)}
  else if(t=='K'){
    for(const[y,x]of K8)add(r+y,c+x);
    if(!att(b,r,c,en)){
      if(rt[o+'K']&&!b[r][5]&&!b[r][6]&&!att(b,r,5,en)&&!att(b,r,6,en))m.push([r,6]);
      if(rt[o+'Q']&&!b[r][1]&&!b[r][2]&&!b[r][3]&&!att(b,r,3,en)&&!att(b,r,2,en))m.push([r,2]);
    }
  }else{
    for(const[y,x]of K8){
      const dg=y&&x;
      if(t=='B'&&!dg||t=='R'&&dg)continue;
      let i=1;while(add(r+y*i,c+x*i))i++;
    }
  }
  return m;
}
function apply(b,rt,r,c,y,x){
  const nb=b.map(a=>a.slice()),p=nb[r][c],o=p[0];
  nb[y][x]=p;nb[r][c]=null;
  if(p[1]=='P'&&(y==0||y==7))nb[y][x]=o+'Q';
  if(p[1]=='K'&&Math.abs(x-c)==2){
    if(x==6){nb[y][5]=nb[y][7];nb[y][7]=null}else{nb[y][3]=nb[y][0];nb[y][0]=null}
  }
  const nr={...rt};
  if(p[1]=='K'){nr[o+'K']=0;nr[o+'Q']=0}
  for(const[s,k]of[[[7,0],'wQ'],[[7,7],'wK'],[[0,0],'bQ'],[[0,7],'bK']])
    if(s[0]==r&&s[1]==c||s[0]==y&&s[1]==x)nr[k]=0;
  return[nb,nr];
}
function legal(b,rt,r,c){
  const o=b[r][c][0];
  return gen(b,r,c,rt).filter(([y,x])=>!chk(apply(b,rt,r,c,y,x)[0],o));
}
function all(b,rt,o){
  const L=[];
  for(let r=0;r<8;r++)for(let c=0;c<8;c++)
    if(b[r][c]&&b[r][c][0]==o)for(const[y,x]of legal(b,rt,r,c))L.push([r,c,y,x]);
  return L;
}
function mat(b,o){let s=0;for(const a of b)for(const p of a)if(p)s+=(p[0]==o?1:-1)*V[p[1]];return s}
function srch(b,rt,d,o,al,be,root,j){
  if(!d)return mat(b,o);
  const L=all(b,rt,o);
  if(!L.length)return chk(b,o)?-1e4-d:0;
  let best=-1e9,bm=null;
  for(const m of L){
    const[nb,nr]=apply(b,rt,...m);
    let s=-srch(nb,nr,d-1,o=='w'?'b':'w',-be,-al,0,0);
    if(root)s+=Math.random()*j;
    if(s>best){best=s;bm=m}
    al=Math.max(al,s);if(al>=be)break;
  }
  return root?bm:best;
}

let AC;
function tn(f,t,d,v=.07){try{AC=AC||new(window.AudioContext||window.webkitAudioContext)();const o=AC.createOscillator(),g=AC.createGain(),n=AC.currentTime+t;o.type='sine';o.frequency.value=f;g.gain.setValueAtTime(v,n);g.gain.exponentialRampToValueAtTime(.0001,n+d);o.connect(g);g.connect(AC.destination);o.start(n);o.stop(n+d)}catch(e){}}
function sfx(k){if(!snd)return;({mv:()=>tn(520,0,.12),cap:()=>{tn(330,0,.1);tn(220,.07,.16)},chk:()=>{tn(660,0,.1);tn(880,.1,.18)},end:()=>[523,659,784,1047].forEach((f,i)=>tn(f,i*.12,.25))})[k]()}
let tt;function toast(s){const t=$('ts');t.textContent=s;t.hidden=false;clearTimeout(tt);tt=setTimeout(()=>t.hidden=true,2600)}

function start(m){
  mode=m;S=fresh();H=[];sel=null;mv=[];busy=false;ab=false;shown=null;
  $('mn').hidden=true;$('gm').hidden=false;$('ov').hidden=true;
  $('un').hidden=m=='online';$('fp').hidden=m=='online';
  draw();
}
function play(r,c,y,x){
  H.push(JSON.stringify(S));
  const t=S.b[y][x];
  if(t)S.cap[S.t].push(t[1]);
  S.lc=t||null;
  [S.b,S.rt]=apply(S.b,S.rt,r,c,y,x);
  S.t=S.t=='w'?'b':'w';S.last=[[r,c],[y,x]];
  const has=all(S.b,S.rt,S.t).length>0;
  S.chk=!!chk(S.b,S.t);
  if(!has)S.res=S.chk?'كش مات! فاز '+(S.t=='w'?'الأسود':'الأبيض'):'تعادل (ستيل مات)';
  sel=null;mv=[];
  return !!t;
}
function done(cap){
  sfx(S.res?'end':S.chk?'chk':cap?'cap':'mv');
  try{navigator.vibrate&&navigator.vibrate(cap?30:12)}catch(e){}
  draw(true);
  if(mode=='online'&&room)room.emit('st',{S}).catch(()=>{});
  if(mode=='ai'&&!S.res&&S.t=='b'){busy=true;$('st').textContent='الكمبيوتر يفكر...';setTimeout(think,dur()+120)}
}
function think(){
  const m=srch(S.b,S.rt,lv+1,'b',-1e9,1e9,1,lv==0?3:.3);
  busy=false;
  if(m&&mode=='ai'&&S.t=='b'&&!S.res)done(play(...m));else draw();
}
function click(r,c){
  if(S.res||busy||ab)return;
  if(mode=='ai'&&S.t!='w')return;
  if(mode=='online'&&S.t!=me)return;
  const p=S.b[r][c];
  if(sel&&mv.some(([y,x])=>y==r&&x==c)){done(play(sel[0],sel[1],r,c));return}
  if(p&&p[0]==S.t){sel=[r,c];mv=legal(S.b,S.rt,r,c)}else{sel=null;mv=[]}
  draw();
}
function draw(an){
  const bd=$('bd'),bw=$('bw'),P=PAL[bt-1].c;
  bd.innerHTML='';bd.className=SH[sh-1].c+' cs'+cs;
  bw.style.setProperty('--l',P[0]);bw.style.setProperty('--d',P[1]);bw.style.setProperty('--fr',P[2]);
  const kp=S.chk?findK(S.b,S.t):null,sq=(r,c)=>bd.querySelector(`[data-r="${r}"][data-c="${c}"]`);
  for(let i=0;i<64;i++){
    const r=fl?7-(i>>3):i>>3,c=fl?7-(i&7):i&7,p=S.b[r][c],d=document.createElement('div');
    let k='q '+((r+c)%2?'d':'l');
    if(S.last&&S.last.some(([y,x])=>y==r&&x==c))k+=' last';
    if(sel&&sel[0]==r&&sel[1]==c)k+=' sel';
    if(kp&&kp[0]==r&&kp[1]==c)k+=' ck';
    if(hint&&mv.some(([y,x])=>y==r&&x==c))k+=' mv'+(p?' cap':'');
    d.className=k;d.dataset.r=r;d.dataset.c=c;
    if(p){const s=document.createElement('span');s.className=p[0];setP(s,p);d.appendChild(s)}
    if(i>>3==7){const e=document.createElement('i');e.className='co f';e.textContent='abcdefgh'[c];d.appendChild(e)}
    if((i&7)==0){const e=document.createElement('i');e.className='co r';e.textContent=8-r;d.appendChild(e)}
    d.onclick=()=>click(r,c);
    bd.appendChild(d);
  }
  if(an&&S.last){
    const[[r,c],[y,x]]=S.last,D=dur();
    const fly=(a,b2,c2,d2,lift)=>{
      const f=sq(a,b2),t=sq(c2,d2),s=t&&t.querySelector('span');
      if(!f||!s)return;
      const A=f.getBoundingClientRect(),B=t.getBoundingClientRect(),dx=A.left-B.left,dy=A.top-B.top;
      s.style.zIndex=6;
      s.animate([{transform:`translate(${dx}px,${dy}px) scale(1)`},{transform:`translate(${dx/2}px,${dy/2}px) scale(${lift?1.22:1})`,offset:.5},{transform:'translate(0,0) scale(1)'}],{duration:D,easing:'cubic-bezier(.35,.6,.3,1)'});
    };
    fly(r,c,y,x,1);
    const pc=S.b[y][x];
    if(pc&&pc[1]=='K'&&Math.abs(x-c)==2)fly(y,x==6?7:0,y,x==6?5:3,0);
    if(S.lc){
      const g=document.createElement('span');
      g.className=S.lc[0];setP(g,S.lc);
      g.style.position='absolute';g.style.zIndex=1;
      sq(y,x).appendChild(g);
      g.animate([{opacity:1,transform:'scale(1)'},{opacity:0,transform:'scale(.3) rotate(14deg)'}],{duration:D*.7,delay:D*.45,fill:'both'});
    }
    ab=true;setTimeout(()=>ab=false,D+40);
  }
  let t=S.t=='w'?'دور الأبيض':'دور الأسود';
  if(mode=='ai')t=S.t=='w'?'دورك':'الكمبيوتر يفكر...';
  if(mode=='online'){const cc=code=='عشوائي'?'':' (الكود: '+code+')';t=room&&room.peers().length<2?'ننتظر اللاعب...'+cc:(S.t==me?'دورك':'دور خصمك')+cc}
  if(S.chk)t+=' ، كش!';
  $('st').textContent=S.res||t;
  $('cp').innerHTML='';
  for(const[k,n]of[['w','أكل الأبيض'],['b','أكل الأسود']]){const s=document.createElement('span');s.textContent=n+': '+S.cap[k].map(x=>U[x]).join(' ');$('cp').appendChild(s)}
  if(S.res&&shown!==S.res){shown=S.res;setTimeout(()=>{$('ot').textContent=S.res;$('ov').hidden=false},an?dur()+200:0)}
}
function okS(s){return s&&Array.isArray(s.b)&&s.b.length==8&&s.b.every(a=>Array.isArray(a)&&a.length==8&&a.every(p=>p===null||/^[wb][KQRBNP]$/.test(p)))&&(s.t=='w'||s.t=='b')&&s.rt&&s.cap&&Array.isArray(s.cap.w)&&Array.isArray(s.cap.b)&&(s.lc==null||/^[wb][KQRBNP]$/.test(s.lc))}
async function goOnline(create){
  const R=window.claude?await claude.use('room'):null;
  if(!R){toast('الأونلاين ما يشتغل هنا، افتح الصفحة وأنت مسجل دخول');return}
  const v=create?Math.random().toString(36).slice(2,6):$('cd').value.trim().toLowerCase().replace(/[^a-z0-9]/g,'');
  if(v.length<3){toast('اكتب كود الغرفة');return}
  openRoom(R,'chess-'+v,create,v);
}
async function openRoom(R,name,host,label){
  try{room=await R.join(name)}catch(e){toast('ما قدرت أدخل الغرفة');return false}
  code=label;me=host?'w':'b';fl=!host;start('online');
  room.on('hi',m=>{if(!m.isMe&&me=='w')room.emit('st',{S})});
  room.on('st',m=>{if(m.isMe||!okS(m.data&&m.data.S))return;S=m.data.S;sel=null;mv=[];sfx(S.chk?'chk':'mv');draw(true)});
  room.onPeers(()=>draw());
  if(!host)room.emit('hi',{});
  return true;
}
let skStop=null;
async function quick(){
  const R=window.claude?await claude.use('room'):null;
  if(!R){toast('الأونلاين ما يشتغل هنا، افتح الصفحة وأنت مسجل دخول');return}
  const id=Math.random().toString(36).slice(2,8),off=[];
  let timer;
  skStop=()=>{off.forEach(f=>f());clearInterval(timer);skStop=null;$('sk').hidden=true};
  $('sk').hidden=false;
  const seek=()=>R.emit('seek',{id}).catch(()=>{});
  off.push(R.on('seek',m=>{
    const d=m.data;
    if(m.isMe||!skStop||!d||typeof d.id!='string'||!/^[a-z0-9]{1,8}$/.test(d.id)||d.id==id)return;
    if(id<d.id){
      const name='q-'+id+d.id;
      skStop();
      R.emit('ok',{to:d.id,from:id,room:name}).catch(()=>{});
      openRoom(R,name,true,'عشوائي').then(ok=>{
        if(ok)setTimeout(()=>{if(room&&mode=='online'&&code=='عشوائي'&&room.peers().length<2){menu();toast('ما لقينا لاعب، جرب مرة ثانية')}},12000);
      });
    }
  }));
  off.push(R.on('ok',m=>{
    const d=m.data;
    if(m.isMe||!skStop||!d||d.to!=id||typeof d.room!='string'||!/^q-[a-z0-9]{2,16}$/.test(d.room))return;
    skStop();openRoom(R,d.room,false,'عشوائي');
  }));
  seek();timer=setInterval(seek,2500);
}
function menu(){if(room){room.leave().catch(()=>{});room=null}mode='';$('gm').hidden=true;$('ov').hidden=true;$('mn').hidden=false;fl=false}

function renderSet(){
  let h='<h2>الإعدادات</h2><p class="sub">شكل القطع</p><div class="g">';
  SH.forEach((s,i)=>h+=`<button class="tile${sh==i+1?' on':''}" data-k="sh" data-v="${i+1}"><b class="pv ${s.c} cs${cs}"><span class="w">${s.svg?SVG('wK'):s.w.K}</span><span class="b">${s.svg?SVG('bN'):s.b.N}</span></b><small>${s.n}</small></button>`);
  h+='</div><p class="sub">ألوان القطع (ما تنطبق على التماثيل)</p><div class="g">';
  CN.forEach((n,i)=>h+=`<button class="tile${cs==i+1?' on':''}" data-k="cs" data-v="${i+1}"><span class="two cs${i+1}"><i style="background:linear-gradient(var(--wa),var(--wb))"></i><i style="background:linear-gradient(var(--ba),var(--bb))"></i></span><small>${n}</small></button>`);
  h+='</div><p class="sub">لون الرقعة</p><div class="g">';
  PAL.forEach((p,i)=>h+=`<button class="tile${bt==i+1?' on':''}" data-k="bt" data-v="${i+1}"><b class="sw" style="background:linear-gradient(90deg,${p.c[0]} 50%,${p.c[1]} 50%)"></b><small>${p.n}</small></button>`);
  h+='</div><p class="sub">سرعة حركة القطع</p><div class="row">';
  SPN.forEach((n,i)=>h+=`<button class="${spd==i?'on':''}" data-k="sp" data-v="${i}">${n}</button>`);
  h+=`</div><div class="row"><button class="${hint?'on':''}" data-k="hint">مؤشرات الحركات: ${hint?'نعم':'لا'}</button><button class="${snd?'on':''}" data-k="snd">الصوت: ${snd?'شغال':'مقفل'}</button></div><button data-k="x">تم</button>`;
  $('sc').innerHTML=h;
}
function openSet(){renderSet();$('set').hidden=false}
$('sc').onclick=e=>{
  const b=e.target.closest('[data-k]');if(!b)return;
  const k=b.dataset.k,v=+b.dataset.v;
  if(k=='x'){$('set').hidden=true;return}
  if(k=='sh')sh=v;else if(k=='cs')cs=v;else if(k=='bt')bt=v;else if(k=='sp')spd=v;else if(k=='hint')hint=hint?0:1;else if(k=='snd'){snd=snd?0:1;sfx('mv')}
  save();renderSet();
  if(S&&!$('gm').hidden)draw();
};
$('set').onclick=e=>{if(e.target==$('set'))$('set').hidden=true};
document.querySelectorAll('[data-l]').forEach(b=>b.onclick=()=>{lv=+b.dataset.l;fl=false;me='w';start('ai')});
$('lc').onclick=()=>{fl=false;start('local')};
$('qk').onclick=quick;
$('skc').onclick=()=>skStop&&skStop();
$('mk').onclick=()=>goOnline(true);
$('jn').onclick=()=>goOnline(false);
$('bk').onclick=menu;
$('op').onclick=openSet;$('op2').onclick=openSet;
$('un').onclick=()=>{
  if(busy||ab||!H.length)return;
  do{S=JSON.parse(H.pop())}while(mode=='ai'&&S.t!='w'&&H.length);
  sel=null;mv=[];shown=null;$('ov').hidden=true;draw();
};
$('fp').onclick=()=>{fl=!fl;draw()};
$('ag').onclick=()=>{
  S=fresh();H=[];sel=null;mv=[];shown=null;$('ov').hidden=true;
  if(mode=='online'&&room)room.emit('st',{S}).catch(()=>{});
  draw();
};
$('cl').onclick=()=>$('ov').hidden=true;
</script>
</body>
</html>