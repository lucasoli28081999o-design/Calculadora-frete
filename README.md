<!doctype html>
<html lang="pt-BR"><head><meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Calculadora de Frete</title>
<meta name="apple-mobile-web-app-title" content="Calc. Frete">
<meta name="theme-color" content="#14243B">
<link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;600;800&display=swap" rel="stylesheet">
<style>
:root{--navy:#14243B;--or:#F28C28;--gr:#159B69;--bg:#F4F6F8;--card:#fff;--tx:#14243B;--mu:#5b6b80;--bd:#dde3ea;--in:#fff;box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){--bg:#0d1726;--card:#14243B;--tx:#eef2f7;--mu:#9fb0c5;--bd:#2a3d58;--in:#0d1726;--gr:#2bc48d;color-scheme:dark}}
:root[data-theme="dark"]{--bg:#0d1726;--card:#14243B;--tx:#eef2f7;--mu:#9fb0c5;--bd:#2a3d58;--in:#0d1726;--gr:#2bc48d;color-scheme:dark}
*{box-sizing:border-box}html,body{margin:0}
body{background:var(--bg);color:var(--tx);font:16px/1.45 "Plus Jakarta Sans",system-ui,-apple-system,"Segoe UI",Roboto,sans-serif}
header{background:#14243B;color:#fff;padding:16px}
header b{display:block;font-size:19px;font-weight:800;letter-spacing:.5px}
header span{font-size:13px;color:#F28C28}
main{max-width:640px;margin:0 auto;padding:16px 16px 96px}
h2{font-size:21px;margin:4px 0 6px}h3{font-size:16px;margin:0 0 8px}
.mu{color:var(--mu);font-size:14px}
.card{background:var(--card);border:1px solid var(--bd);border-radius:10px;padding:14px;margin:12px 0}
label{display:block;font-size:14px;font-weight:600;margin:10px 0 0}
input,select,textarea{width:100%;margin-top:4px;padding:11px;border:1px solid var(--bd);border-radius:8px;background:var(--in);color:var(--tx);font:inherit}
textarea{min-height:68px}
.r2{display:grid;grid-template-columns:1fr 1fr;gap:10px;align-items:end}
button{font:inherit;cursor:pointer}
.b{display:block;width:100%;margin-top:14px;padding:13px;border:0;border-radius:8px;background:#F28C28;color:#14243B;font-weight:800}
.b:disabled{opacity:.45}
.b2{padding:8px 12px;border:1px solid var(--bd);border-radius:8px;background:transparent;color:var(--tx);font-size:14px}
.acts{display:flex;flex-wrap:wrap;gap:8px;margin-top:10px}
.sec{font-size:18px;margin:18px 0 8px}
details.hp{margin:8px 0 4px;border:1px dashed var(--bd);border-radius:8px;padding:10px 12px}details.hp summary{cursor:pointer;font-weight:600;font-size:14px}.hb{padding-top:4px}.strip{display:flex;justify-content:space-between;align-items:center;gap:10px}
.grid{display:grid;grid-template-columns:1fr 1fr;gap:12px;margin:8px 0 14px}
.tile{display:flex;flex-direction:column;align-items:flex-start;gap:3px;text-align:left;min-height:132px;padding:14px;background:var(--card);color:var(--tx);border:1px solid var(--bd);border-radius:14px;box-shadow:0 1px 3px rgba(20,36,59,.1)}
.tile:active{transform:scale(.98)}.tile i{width:50px;height:50px;border-radius:13px;background:#F28C28;color:#14243B;display:grid;place-items:center;margin-bottom:8px}
.tile:last-child:nth-child(odd){grid-column:1/-1;min-height:96px}.tile b{font-size:15px}.tile small{color:var(--mu);font-size:12.5px;line-height:1.3}
.big{font-size:34px;font-weight:800;color:var(--gr)}
.hero{background:#14243B;color:#fff;border-radius:10px;padding:18px;margin:12px 0}
.hero .pp{font-size:38px;font-weight:800;color:#F28C28}
.warn{border-left:4px solid #F28C28;background:var(--card);padding:12px;border-radius:6px;margin:12px 0;font-size:14px}
.ck{display:flex;gap:10px;align-items:flex-start;font-weight:400}.ck input{width:auto;margin-top:3px}
.ln{display:flex;justify-content:space-between;gap:10px;padding:5px 0;border-bottom:1px solid var(--bd)}
.ex{display:flex;gap:10px;align-items:center;justify-content:space-between;padding:6px 0}
.tabs{display:flex;gap:6px;overflow-x:auto;margin:8px 0}.tabs button{padding:8px 12px;border:1px solid var(--bd);border-radius:8px;background:var(--card);color:var(--tx);white-space:nowrap}
.tabs .on{background:#14243B;color:#fff;border-color:#14243B}
nav{position:fixed;left:0;right:0;bottom:0;display:grid;grid-template-columns:repeat(6,1fr);background:#14243B;padding-bottom:env(safe-area-inset-bottom,0px)}
nav button{background:none;border:0;color:#b9c6d8;padding:13px 2px;font-size:12px}
nav .on{color:#F28C28;font-weight:800}
#t{display:none;position:fixed;left:16px;right:16px;bottom:84px;background:#14243B;color:#fff;padding:12px;border-radius:8px;z-index:9;font-size:14px}
img.lg{max-height:64px;max-width:160px;display:block;margin:8px 0}
#ov{position:fixed;inset:0;z-index:20;background:rgba(10,20,35,.92);overflow:auto;padding:12px 12px 90px}
.sheet{max-width:600px;margin:0 auto;background:#fff;color:#14243B;border-radius:6px;overflow:hidden;font-size:14px}
.sh{background:#14243B;color:#fff;padding:14px;display:flex;gap:12px;align-items:center}.sh img{max-height:48px;max-width:90px}.sh small{color:#c9d4e3}
.st{display:flex;justify-content:space-between;align-items:baseline;gap:8px;padding:14px 14px 4px;flex-wrap:wrap}.st b{font-size:20px}
.pr{display:grid;grid-template-columns:96px 1fr;gap:8px;padding:6px 14px}.pr span{color:#5b6b80;font-size:12px;font-weight:600}
.pv{background:#14243B;color:#fff;margin:14px;padding:14px;border-radius:6px}.pv b{display:block;font-size:26px;color:#F28C28}
.sheet p,.sheet .ft{padding:0 14px 14px;margin:0;font-size:12px;color:#5b6b80}
.obar{position:fixed;left:0;right:0;bottom:0;display:flex;gap:10px;align-items:center;padding:10px 12px calc(10px + env(safe-area-inset-bottom,0px));background:#14243B;z-index:21}.obar .b{margin:0}.obar .b2{color:#fff;border-color:#4a5d78;white-space:nowrap}
</style></head>
<body>
<header><b>CALCULADORA DE FRETE</b><span>Calcule seus custos. Saiba quanto cobrar.</span></header>
<main id="v"></main><div id="t"></div>
<nav><button data-t="inicio" onclick="go('inicio')">Início</button><button data-t="custo" onclick="go('custo')">Custo/km</button><button data-t="frete" onclick="go('frete')">Frete</button><button data-t="docs" onclick="go('docs')">Docs</button><button data-t="hist" onclick="go('hist')">Histórico</button><button data-t="perfil" onclick="go('perfil')">Perfil</button></nav>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
<script>
const K='cdf_v1',$=s=>document.querySelector(s);
let S={perfil:{},vs:[],hist:[],n:{o:0,r:0}},tab='inicio',E=[],FR=null,FRid=null,draft={},dt_='o',ht='o',resId=null,KMD=null,tm;
try{const t=localStorage.getItem(K);if(t)S=Object.assign(S,JSON.parse(t))}catch(e){}
const save=()=>{try{localStorage.setItem(K,JSON.stringify(S));return true}catch(e){toast('Não foi possível salvar neste navegador.');return false}};
const esc=s=>String(s==null?'':s).replace(/[&<>"]/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;'}[c]));
const num=s=>{s=String(s==null?'':s).trim();if(!s)return NaN;if(s.includes(','))s=s.replace(/\./g,'').replace(',','.');else if(!/^\d+\.\d{1,2}$/.test(s))s=s.replace(/\./g,'');return /^\d*\.?\d+$/.test(s)?parseFloat(s):NaN};
const f=n=>new Intl.NumberFormat('pt-BR',{style:'currency',currency:'BRL'}).format(n);
const today=()=>{const d=new Date();return new Date(d-d.getTimezoneOffset()*6e4).toISOString().slice(0,10)};
const fd=s=>s?String(s).slice(0,10).split('-').reverse().join('/'):'';
const pad=n=>String(n).padStart(4,'0'),uid=()=>Date.now().toString(36)+Math.random().toString(36).slice(2,6);
const g=id=>$('#'+id).value.trim(),H=id=>S.hist.find(h=>h.id==id);
function toast(m){const t=$('#t');t.textContent=m;t.style.display='block';clearTimeout(tm);tm=setTimeout(()=>t.style.display='none',4500)}
// ---- cálculos centralizados (sem arredondar valores intermediários)
const C={
 mensal:(v,p)=>p=='a'?v/12:v,
 km(o){const comb=o.preco/o.cons,varMes=o.manut+o.pneus+o.oleo,varKm=comb+varMes/o.km;
  const fixMes=['seguro','ipva','lic','outras'].reduce((a,k)=>a+C.mensal(o[k],o[k+'P']),0),fixKm=fixMes/o.km;
  return{comb,varMes,varKm,fixMes,fixKm,total:varKm+fixKm}},
 preco:(ct,m,v)=>m=='f'?ct+v:m=='p'?ct*(1+v/100):ct/(1-v/100)
};
const inp=(id,l,v,t,x)=>`<label>${l}<input id="${id}" type="${t||'text'}" value="${esc(v)}" ${x||''}></label>`;
const mon=(id,l,v)=>inp(id,l,v===''||v==null?'':String(v).replace('.',','),'text','inputmode="decimal" autocomplete="off"');
const ta=(id,l,v)=>`<label>${l}<textarea id="${id}">${esc(v)}</textarea></label>`;
function go(t){tab=t;resId=null;if(t=='frete'){E=[];FR=null;FRid=null}render()}
function render(){document.querySelectorAll('nav button').forEach(b=>b.classList.toggle('on',b.dataset.t==tab));$('#v').innerHTML=V[tab]();window.scrollTo(0,0);if(tab=='frete'&&$('#ex'))drawEx()}
const V={};
const IC={frete:'<rect x="5" y="3" width="14" height="18" rx="2"/><path d="M8 7h8M8 12h2M12 12h2M8 16h2M12 16h4"/>',custo:'<path d="M4 17a8 8 0 1 1 16 0"/><path d="M12 17l4-5"/>',orc:'<path d="M7 3h7l4 4v14H7z"/><path d="M14 3v4h4M9.5 12h5M9.5 16h5"/>',rec:'<path d="M6 3h12v18l-3-2-3 2-3-2-3 2z"/><path d="M9 8h6M9 12h6"/>',hist:'<circle cx="12" cy="12" r="9"/><path d="M12 7v5l3 2"/>',veic:'<path d="M3 7h11v9H3zM14 10h4l3 3v3h-7"/><circle cx="7.5" cy="17.5" r="1.8"/><circle cx="17" cy="17.5" r="1.8"/>',perfil:'<circle cx="12" cy="8" r="4"/><path d="M4 21a8 8 0 0 1 16 0"/>'};
const TL=[['frete','Calcular frete','Descubra quanto cobrar',"go('frete')"],['custo','Custo por KM','Quanto custa rodar',"go('custo')"],['orc','Novo orçamento','PDF para o cliente',"dt_='o';draft={};go('docs')"],['rec','Novo recibo','Comprovante de pagamento',"dt_='r';draft={};go('docs')"],['hist','Histórico','Cálculos e documentos',"go('hist')"],['veic','Meus veículos','Veja seu custo por veículo',"go('veic')"],['perfil','Meu perfil','Empresa, contato e logo',"go('perfil')"]];
const TILES=()=>`<div class=grid>${TL.map(t=>`<button class=tile onclick="${t[3]}"><i><svg viewBox="0 0 24 24" width="28" height="28" fill="none" stroke="currentColor" stroke-width="1.9" stroke-linecap="round" stroke-linejoin="round">${IC[t[0]]}</svg></i><b>${t[1]}</b><small>${t[2]}</small></button>`).join('')}</div>`;
V.veic=()=>`<h2>Meus veículos</h2><p class=mu>O custo por km do veículo é a base dos seus cálculos de frete. Nesta versão o app trabalha com um veículo.</p>`+(S.vs.length?S.vs.map(v=>`<div class=card><b>${esc(v.nome)}</b><div class=big style="font-size:26px">${f(v.total)} <small class=mu>por km</small></div><div class=ln><span>Variável por km</span><b>${f(v.varKm)}</b></div><div class=ln><span>Fixo rateado por km</span><b>${f(v.fixKm)}</b></div><div class=ln><span>Km por mês</span><b>${v.km.toLocaleString('pt-BR')}</b></div><button class=b2 style="margin-top:10px" onclick="go('custo')">Editar custos</button></div>`).join(''):`<div class=warn>Nenhum veículo cadastrado ainda. <button class=b onclick="go('custo')">Cadastrar veículo e custo por km</button></div>`);
V.inicio=()=>{const p=S.perfil,v=S.vs[0],nm=p.resp||p.nome,u=S.hist.filter(h=>h.t=='o').slice(-3).reverse(),r=S.hist.filter(h=>h.t=='r').slice(-3).reverse();
 const li=a=>a.length?a.map(h=>`<div class=ln><span>Nº ${pad(h.num)} ${esc(h.t=='o'?h.d.cliente:h.d.pagador)}</span><b>${f(h.d.valor)}</b></div>`).join(''):'<p class=mu>Nada gerado ainda.</p>';
 return `<h2>Olá${nm?', '+esc(nm):''}!</h2>`+(v?`<div class="card strip"><div><div class=mu>Seu custo por km</div><div class=big style="font-size:28px">${f(v.total)}</div></div><button class=b2 onclick="go('custo')">Atualizar</button></div>`:`<div class=warn>Você ainda não cadastrou seu custo por km. Sem ele não dá para calcular o frete. <button class=b onclick="go('custo')">Configurar custo por km</button></div>`)+`<h3 class=sec>O que você deseja fazer?</h3>`+TILES()+
 `<div class=card><h3>Últimos orçamentos</h3>${li(u)}</div><div class=card><h3>Últimos recibos</h3>${li(r)}<button class=b2 onclick="go('hist')">Ver histórico</button></div>`};
// ---- ajudas do custo por km
const PD={seguro:'a',ipva:'a',lic:'a',outras:'m'};
const PH={seguro:'Informe o valor total do seguro no ano e deixe “Valor do ano”. Se você paga parcelas mensais, informe a parcela e escolha “Valor do mês”. Não tem seguro? Coloque 0.',ipva:'O IPVA é pago uma vez por ano. Informe o valor total do ano e deixe “Valor do ano (÷ 12)”: o app divide por 12 para achar o custo de cada mês. Isento ou não paga? Coloque 0.',lic:'É a taxa anual do licenciamento do veículo. Informe o valor do ano e deixe “Valor do ano (÷ 12)”.',outras:'Rastreador, garagem, taxas e outros gastos fixos que não entram nos itens acima. Informe o valor e escolha se é do mês ou do ano.'};
const HX={manut:'Exemplo: R$ 1.200,00 gastos em revisões e peças que se repetem a cada 6 meses dão R$ 200,00 por mês.',pneus:'Exemplo: se o jogo de pneus dura 8 meses e a troca custa R$ 800,00, você gasta R$ 100,00 por mês.',oleo:'Exemplo: a troca de óleo e filtros custa R$ 240,00 e é feita a cada 10.000 km. Escolha “km rodados”: o app usa os km por mês que você informou lá em cima.'};
const HT={manut:'Revisões, peças, mecânico e lavagem. Informe quanto isso dá em média por mês.',pneus:'Quanto você gasta com pneus em média por mês (troca, alinhamento e balanceamento).',oleo:'Troca de óleo, filtros e fluidos. Informe a média por mês.'};
const VF=(k,l,val)=>mon(k,l,val)+`<p class=mu>${HT[k]}</p><details class=hp><summary>Não sei: me ajude a calcular</summary><div class=hb><p class=mu>${HX[k]}</p>${mon(k+'_a','Valor gasto na troca ou serviço (R$)','')}<div class=r2>${mon(k+'_b','Dura quanto?','')}<label>Unidade<select id="${k}_u"><option value="m">meses</option><option value="k">km rodados</option></select></label></div><button class=b2 style="margin-top:10px" onclick="helpV('${k}')">Calcular e usar</button><p class=mu id="${k}_r"></p></div></details>`;
function helpV(k){const a=num(g(k+'_a')),b=num(g(k+'_b')),u=$('#'+k+'_u').value;if(!(a>0)||!(b>0))return toast('Preencha o valor gasto e quanto tempo (ou km) ele dura.');
 let r;if(u=='k'){const km=num(g('km'));if(!(km>0))return toast('Preencha antes os km rodados por mês, lá em cima.');r=a/b*km}else r=a/b;
 $('#'+k).value=(Math.round(r*100)/100).toFixed(2).replace('.',',');$('#'+k+'_r').textContent='Resultado: '+f(r)+' por mês. Já preenchido no campo acima.'}
// ---- custo por km
V.custo=()=>{const v=S.vs[0]||{};const P=(k,l)=>{const s=v[k+'P']||PD[k];return `<div class=r2>${mon(k,l,v[k])}<label>Esse valor é<select id="${k}P"><option value="m" ${s=='m'?'selected':''}>Valor do mês</option><option value="a" ${s=='a'?'selected':''}>Valor do ano (÷ 12)</option></select></label></div><p class=mu>${PH[k]}</p>`};
 return `<h2>Descubra quanto custa o km do seu veículo</h2><p class=mu>Use seus gastos reais. Despesas por ano viram média mensal e os custos fixos são divididos pelos km rodados no mês.</p>
 <div class=card><h3>Uso do veículo</h3>${inp('nm','Nome do veículo',v.nome||'')}${mon('km','Km rodados por mês',v.km)}<p class=mu>Todos os km que o veículo roda no mês, no trabalho e fora dele. Veja o hodômetro no começo e no fim do mês.</p>${mon('cons','Consumo médio (km por litro)',v.cons)}<p class=mu>Quantos km o veículo faz com 1 litro. Dica: encha o tanque, zere o hodômetro parcial e, no próximo abastecimento, divida os km rodados pelos litros colocados.</p>${mon('preco','Preço do combustível (R$ por litro)',v.preco)}<p class=mu>Quanto você paga em média por litro.</p></div>
 <div class=card><h3>Despesas variáveis (por mês)</h3>${VF('manut','Manutenção',v.manut)}${VF('pneus','Pneus',v.pneus)}${VF('oleo','Óleo e outros itens de manutenção',v.oleo)}<p class=mu>O combustível é calculado pelo consumo e pelo preço do litro.</p></div>
 <div class=card><h3>Despesas fixas</h3><p class=mu>São gastos que você tem rodando ou não. Muitos são pagos uma vez por ano: nesses casos informe o valor do ano e o app divide por 12.</p>${P('seguro','Seguro')}${P('ipva','IPVA')}${P('lic','Licenciamento')}${P('outras','Outras despesas fixas')}</div>
 <button class=b onclick="calcKm()">Calcular custo por km</button><div id=rk></div>`};
function readKm(){const o={nome:g('nm')||'Meu veículo'},bad=[];
 [['km','Km por mês',1],['cons','Consumo',1],['preco','Preço do combustível',1],['manut','Manutenção'],['pneus','Pneus'],['oleo','Óleo'],['seguro','Seguro'],['ipva','IPVA'],['lic','Licenciamento'],['outras','Outras despesas']].forEach(([k,l,req])=>{
  const raw=g(k);let n=raw===''?(req?NaN:0):num(raw);if(isNaN(n)||n<0||(req&&n<=0))bad.push(l);o[k]=n;const s=$('#'+k+'P');if(s)o[k+'P']=s.value});
 return bad.length?(toast('Confira estes campos: '+bad.join(', ')+'.'),null):o}
function calcKm(){const o=readKm();if(!o)return;KMD=o;const r=C.km(o);
 $('#rk').innerHTML=`<div class=hero><div>Custo total por km</div><div class=pp>${f(r.total)}</div></div>
 <div class=card><div class=ln><span>Custo variável por km</span><b>${f(r.varKm)}</b></div><div class=ln><span>Custo fixo rateado por km</span><b>${f(r.fixKm)}</b></div><div class=ln><span>Combustível por km (dentro do variável)</span><b>${f(r.comb)}</b></div><div class=ln><span>Variáveis no mês (sem combustível)</span><b>${f(r.varMes)}</b></div><div class=ln><span>Fixos no mês (média)</span><b>${f(r.fixMes)}</b></div><div class=ln><span>Km rodados no mês</span><b>${o.km.toLocaleString('pt-BR')}</b></div></div>
 <div class=warn>“Confira se todas as informações estão corretas. Este custo por quilômetro será utilizado como base nos cálculos dos seus próximos fretes. Informações incorretas podem gerar preços incorretos e fazer você cobrar menos do que precisa.”</div>
 <label class=ck><input type=checkbox id=ok onchange="$('#sv').disabled=!this.checked"> Conferi as informações e quero salvar este custo por km.</label><button id=sv class=b disabled onclick="saveKm()">Salvar custo por km</button>`;$('#sv').scrollIntoView({behavior:'smooth',block:'center'})}
function saveKm(){if(!KMD||!$('#ok').checked)return;const r=C.km(KMD),v=Object.assign({id:1},KMD,r);S.vs[0]=v;
 S.hist.push({id:uid(),t:'c',em:today(),nome:v.nome,km:v.km,total:r.total,varKm:r.varKm,fixKm:r.fixKm});if(save()){toast('Custo por km salvo.');go('inicio')}}
// ---- frete
V.frete=()=>{const v=S.vs[0];if(!v)return `<h2>Calcular frete</h2><div class=warn>Primeiro cadastre o custo por km do seu veículo. Ele é a base do cálculo. <button class=b onclick="go('custo')">Configurar custo por km</button></div>`;
 return `<h2>Calcular frete</h2><p class=mu>Custo por km em uso: <b>${f(v.total)}</b></p>
 <div class=card>${inp('cl','Nome do cliente')}${inp('or','Origem')}${inp('de','Destino')}${mon('kt','Km totais da operação')}<p class=mu>Some todos os km que você vai rodar: ida, retorno vazio e deslocamentos extras. Não é só o trajeto de ida.</p>${ta('ds','Descrição do serviço','')}${inp('tv','Tipo de veículo',v.nome)}${inp('dp','Data prevista',today(),'date')}</div>
 <div class=card><h3>Despesas adicionais</h3><p class=mu>Pedágio, ajudante, alimentação, estacionamento, carga e descarga. Não repita combustível, manutenção ou pneus: já estão no custo por km.</p><div id=ex></div>${inp('xd','Descrição')}${mon('xv','Valor (R$)')}<button class=b2 style="margin-top:10px" onclick="addEx()">Adicionar despesa</button></div>
 <div class=card><h3>Seu lucro</h3><label>Como definir<select id=lm><option value="f">Valor fixo em reais</option><option value="p">Percentual sobre o custo (markup)</option><option value="m">Margem percentual sobre o preço final</option></select></label>${mon('lv','Valor (R$ ou %)')}<p class=mu>Markup soma uma porcentagem ao custo. Margem é a parte do preço final que sobra de lucro. Não são a mesma coisa.</p></div>
 <button class=b onclick="calcFrete()">Calcular preço</button><div id=rf></div>`};
function drawEx(){$('#ex').innerHTML=E.map((e,i)=>`<div class=ex><span>${esc(e.d)}</span><b>${f(e.v)}</b><button class=b2 onclick="E.splice(${i},1);drawEx()">Remover</button></div>`).join('')||'<p class=mu>Nenhuma despesa adicional.</p>'}
function addEx(){const d=g('xd'),v=num(g('xv'));if(!d||isNaN(v)||v<=0)return toast('Informe a descrição e um valor maior que zero.');E.push({d,v});$('#xd').value=$('#xv').value='';drawEx()}
function calcFrete(){const v=S.vs[0],km=num(g('kt')),lv=num(g('lv')),m=$('#lm').value;
 if(isNaN(km)||km<=0)return toast('Informe os km totais da operação (maior que zero).');
 if(isNaN(lv)||lv<0)return toast('Informe o lucro desejado.');if(m=='m'&&lv>=100)return toast('A margem precisa ser menor que 100%.');
 const op=km*v.total,ex=E.reduce((a,e)=>a+e.v,0),ct=op+ex,preco=C.preco(ct,m,lv),lucro=preco-ct;
 if(!FRid)FRid=uid();FR={id:FRid,t:'f',em:today(),cliente:g('cl'),origem:g('or'),destino:g('de'),desc:g('ds'),tipo:g('tv'),data:g('dp'),km,ckm:v.total,op,extras:E.slice(),ex,ct,modo:m,lv,lucro,preco};
 const i=S.hist.findIndex(h=>h.id==FRid);if(i<0)S.hist.push(FR);else S.hist[i]=FR;save();
 $('#rf').innerHTML=`<div class=card><div class=ln><span>Custo operacional (${km.toLocaleString('pt-BR')} km × ${f(v.total)})</span><b>${f(op)}</b></div><div class=ln><span>Despesas adicionais</span><b>${f(ex)}</b></div><div class=ln><span>CUSTO TOTAL DA VIAGEM</span><b>${f(ct)}</b></div><div class=ln><span>LUCRO DESEJADO</span><b style="color:var(--gr)">${f(lucro)}</b></div><p class=mu>Equivale a ${(ct?lucro/ct*100:0).toFixed(1).replace('.',',')}% de markup e ${(preco?lucro/preco*100:0).toFixed(1).replace('.',',')}% de margem.</p></div>
 <div class=hero><div>PREÇO SUGERIDO PARA COBRAR</div><div class=pp>${f(preco)}</div></div><button class=b onclick="toOrc()">Gerar orçamento com este cálculo</button>`;$('#rf').scrollIntoView({behavior:'smooth'})}
function toOrc(){draft={cliente:FR.cliente,origem:FR.origem,destino:FR.destino,desc:FR.desc,tipo:FR.tipo,valor:FR.preco};tab='docs';dt_='o';resId=null;render()}
// ---- documentos
V.docs=()=>{if(resId){const r=H(resId);return `<div class="card"><h2>${r.t=='o'?'Orçamento':'Recibo'} Nº ${pad(r.num)} gerado</h2><p class=mu>Ele fica salvo no histórico com os valores de hoje.</p><div class=acts><button class=b onclick="vw('${r.id}')">Visualizar documento</button><button class=b2 onclick="dl('${r.id}')">Baixar PDF</button><button class=b2 onclick="shr('${r.id}')">Compartilhar documento</button></div><button class=b2 style="margin-top:14px" onclick="resId=null;draft={};render()">Novo documento</button></div>`}
 const p=S.perfil,d=draft,w=!p.nome?`<div class=warn>Cadastre os dados da sua empresa no Perfil para eles aparecerem no documento. <button class=b onclick="go('perfil')">Abrir Perfil</button></div>`:'';
 const tabs=`<div class=tabs><button class="${dt_=='o'?'on':''}" onclick="dt_='o';draft={};render()">Orçamento</button><button class="${dt_=='r'?'on':''}" onclick="dt_='r';draft={};render()">Recibo</button></div>`;
 if(dt_=='o')return `<h2>Orçamento em PDF</h2>${tabs}${w}<div class=card>${inp('cl','Nome do cliente',d.cliente||'')}${inp('or','Origem',d.origem||'')}${inp('de','Destino',d.destino||'')}${ta('ds','Descrição do serviço',d.desc||'')}${inp('tv','Tipo de veículo',d.tipo||'')}${mon('vl','Valor do serviço (R$)',d.valor!=null?Math.round(d.valor*100)/100:'')}${ta('pg','Condições de pagamento','')}${inp('vd','Validade (dias)','7','number','inputmode="numeric" min="1"')}${ta('ob','Observações adicionais','')}</div><button class=b onclick="genOrc()">Gerar orçamento</button>`;
 return `<h2>Recibo em PDF</h2>${tabs}${w}<div class=card>${inp('pa','Nome do pagador','')}${inp('rc','Nome do recebedor',p.resp||p.nome||'')}${inp('dc','CPF ou CNPJ (se quiser informar)',p.doc||'')}${mon('vl','Valor recebido (R$)','')}${inp('dp','Data do pagamento',today(),'date')}${inp('fp','Forma de pagamento','')}${ta('ds','Descrição do serviço','')}${ta('ob','Observações','')}</div><button class=b onclick="genRec()">Gerar recibo</button>`};
function miss(a){const m=a.filter(([id,l])=>!g(id)||(id=='vl'&&!(num(g(id))>0))).map(x=>x[1]);if(m.length){toast('Faltou preencher: '+m.join(', ')+'.');return true}if(!S.perfil.nome){toast('Cadastre o nome da sua empresa no Perfil.');return true}}
function emit(r){S.hist.push(r);if(!save())return;resId=r.id;draft={};render()}
function genOrc(){if(miss([['cl','nome do cliente'],['ds','descrição do serviço'],['vl','valor do serviço']]))return;
 emit({id:uid(),t:'o',num:++S.n.o,em:today(),p:Object.assign({},S.perfil),d:{cliente:g('cl'),origem:g('or'),destino:g('de'),desc:g('ds'),tipo:g('tv'),valor:num(g('vl')),pag:g('pg'),dias:Math.max(1,parseInt(g('vd'))||7),obs:g('ob')}})}
function genRec(){if(miss([['pa','nome do pagador'],['rc','nome do recebedor'],['vl','valor recebido'],['ds','descrição do serviço']]))return;
 emit({id:uid(),t:'r',num:++S.n.r,em:today(),p:Object.assign({},S.perfil),d:{pagador:g('pa'),recebedor:g('rc'),doc:g('dc'),valor:num(g('vl')),data:g('dp'),forma:g('fp'),desc:g('ds'),obs:g('ob')}})}
function pdf(r){if(!window.jspdf)throw new Error('pdf');const d=new window.jspdf.jsPDF({unit:'mm',format:'a4'}),p=r.p,x=r.d,W=210;
 d.setFillColor(20,36,59);d.rect(0,0,W,36,'F');let tx=14;
 if(p.logo){const h=22,w=Math.min(46,h*(p.lw/p.lh||1));try{d.addImage(p.logo,'PNG',14,7,w,h);tx=14+w+6}catch(e){}}
 d.setTextColor(255,255,255);d.setFont('helvetica','bold');d.setFontSize(15);d.text(d.splitTextToSize(p.nome||'',W-tx-14)[0],tx,16);
 d.setFont('helvetica','normal');d.setFontSize(9);
 [[p.resp,p.doc].filter(Boolean).join('  |  '),[p.tel&&'Tel '+p.tel,p.whats&&'WhatsApp '+p.whats,p.email].filter(Boolean).join('  |  '),p.end].filter(Boolean).forEach((l,i)=>d.text(d.splitTextToSize(l,W-tx-14)[0],tx,22+i*5));
 d.setTextColor(20,36,59);d.setFont('helvetica','bold');d.setFontSize(20);d.text(r.t=='o'?'ORÇAMENTO':'RECIBO',14,52);
 d.setFontSize(10);d.setFont('helvetica','normal');d.text('Nº '+pad(r.num)+'  |  Emissão: '+fd(r.em),W-14,52,{align:'right'});
 let y=64;const row=(k,v)=>{if(!v)return;d.setFont('helvetica','bold');d.setFontSize(9);d.setTextColor(90,107,128);d.text(k,14,y);d.setFont('helvetica','normal');d.setFontSize(11);d.setTextColor(20,36,59);const L=d.splitTextToSize(String(v),135);d.text(L,60,y);y+=Math.max(8,L.length*5.2+3)};
 if(r.t=='o'){const v=new Date(r.em+'T12:00');v.setDate(v.getDate()+x.dias);row('Cliente',x.cliente);row('Origem',x.origem);row('Destino',x.destino);row('Serviço',x.desc);row('Veículo',x.tipo);row('Pagamento',x.pag);row('Validade','até '+v.toLocaleDateString('pt-BR'));row('Observações',x.obs)}
 else{row('Pagador',x.pagador);row('Recebedor',x.recebedor);row('CPF/CNPJ',x.doc);row('Data',fd(x.data));row('Forma',x.forma);row('Referente a',x.desc);row('Observações',x.obs)}
 y+=4;if(y>235){d.addPage();y=20}
 d.setFillColor(20,36,59);d.roundedRect(14,y,W-28,24,2,2,'F');d.setTextColor(255,255,255);d.setFontSize(9);d.text(r.t=='o'?'VALOR DO SERVIÇO':'VALOR RECEBIDO',20,y+8);
 d.setTextColor(242,140,40);d.setFont('helvetica','bold');d.setFontSize(20);d.text(f(x.valor).replace(/\u00a0/g,' '),20,y+18);y+=36;
 if(r.t=='r'){d.setTextColor(20,36,59);d.setFont('helvetica','normal');d.setFontSize(11);const L=d.splitTextToSize('Recebi de '+x.pagador+' a quantia de '+f(x.valor).replace(/\u00a0/g,' ')+', referente a '+x.desc+'.',W-28);d.text(L,14,y);y+=L.length*5.5+22;d.line(60,y,150,y);d.setFontSize(9);d.text(x.recebedor,105,y+5,{align:'center'})}
 d.setFontSize(8);d.setTextColor(120,130,145);d.text(r.t=='o'?'Orçamento sujeito à confirmação das condições do serviço.':'Recibo de pagamento. Este documento não é nota fiscal.',14,288);return d}
const fn=r=>(r.t=='o'?'orcamento-':'recibo-')+pad(r.num)+'.pdf';
function vw(id){const r=H(id),p=r.p,x=r.d,R=(k,v)=>v?`<div class=pr><span>${k}</span><div>${esc(v)}</div></div>`:'';
 const v=new Date(r.em+'T12:00');if(r.t=='o')v.setDate(v.getDate()+x.dias);
 const body=r.t=='o'?R('Cliente',x.cliente)+R('Origem',x.origem)+R('Destino',x.destino)+R('Serviço',x.desc)+R('Veículo',x.tipo)+R('Pagamento',x.pag)+R('Validade','até '+v.toLocaleDateString('pt-BR'))+R('Observações',x.obs):R('Pagador',x.pagador)+R('Recebedor',x.recebedor)+R('CPF/CNPJ',x.doc)+R('Data',fd(x.data))+R('Forma',x.forma)+R('Referente a',x.desc)+R('Observações',x.obs);
 const o=document.createElement('div');o.id='ov';
 o.innerHTML=`<div class=sheet><div class=sh>${p.logo?`<img src="${p.logo}" alt="">`:''}<div><b>${esc(p.nome)}</b><br><small>${esc([p.resp,p.doc].filter(Boolean).join(' | '))}<br>${esc([p.tel&&'Tel '+p.tel,p.whats&&'WhatsApp '+p.whats,p.email].filter(Boolean).join(' | '))}</small></div></div><div class=st><b>${r.t=='o'?'ORÇAMENTO':'RECIBO'}</b><span>Nº ${pad(r.num)} | Emissão: ${fd(r.em)}</span></div>${body}<div class=pv><small>${r.t=='o'?'VALOR DO SERVIÇO':'VALOR RECEBIDO'}</small><b>${f(x.valor)}</b></div>${r.t=='r'?`<p>Recebi de ${esc(x.pagador)} a quantia de ${f(x.valor)}, referente a ${esc(x.desc)}.</p>`:''}<div class=ft>${r.t=='o'?'Orçamento sujeito à confirmação das condições do serviço.':'Recibo de pagamento. Este documento não é nota fiscal.'}</div></div><div class=obar><button class=b onclick="dl('${id}')">Baixar PDF</button><button class=b2 onclick="$('#ov').remove()">Fechar</button></div>`;
 document.body.appendChild(o)}
let DLc=null;try{if(window.claude&&claude.use)claude.use('downloads').then(x=>{DLc=x}).catch(()=>{})}catch(e){}
async function saveFile(d,name){if(DLc){try{await DLc.save({filename:name,data:d.output('blob')});return}catch(e){if(e&&e.code=='declined')return}}try{d.save(name)}catch(e){toast('Não consegui baixar o arquivo neste aparelho.')}}
async function dl(id){const r=H(id);let d;try{d=pdf(r)}catch(e){return toast('Não foi possível gerar o PDF agora. Verifique a conexão e tente de novo.')}await saveFile(d,fn(r))}
async function shr(id){const r=H(id);let d;try{d=pdf(r)}catch(e){return toast('Não foi possível gerar o PDF agora.')}
 const file=new File([d.output('blob')],fn(r),{type:'application/pdf'});
 if(navigator.canShare&&navigator.canShare({files:[file]})){try{await navigator.share({files:[file],title:fn(r)})}catch(e){if(!e||e.name!='AbortError'){await saveFile(d,fn(r));toast('Compartilhar não está disponível aqui. Salve o PDF e envie pelo WhatsApp manualmente.')}}}
 else{await saveFile(d,fn(r));toast('Este aparelho não compartilha arquivos direto. Salve o PDF e envie pelo WhatsApp manualmente.')}}
// ---- histórico
V.hist=()=>{const T={o:'Orçamentos',r:'Recibos',f:'Cálculos',c:'Custos por km'},L=S.hist.filter(h=>h.t==ht).reverse();
 return `<h2>Histórico</h2><div class=tabs>${Object.keys(T).map(k=>`<button class="${k==ht?'on':''}" onclick="ht='${k}';render()">${T[k]}</button>`).join('')}</div>`+(L.length?L.map(item).join(''):`<div class=card><p class=mu>Nada por aqui ainda. Calcule um frete ou gere um documento para ele aparecer.</p></div>`)+`<p class=mu>O histórico fica salvo só neste aparelho. Cada registro guarda os valores de quando foi gerado e não muda se você atualizar seu custo por km.</p>`};
function item(h){let a,b='';const n=x=>x.toLocaleString('pt-BR');
 if(h.t=='o'||h.t=='r'){a=`<b>Nº ${pad(h.num)}</b> ${esc(h.t=='o'?h.d.cliente:h.d.pagador)}<br>${f(h.d.valor)} em ${fd(h.em)}`;b=`<button class=b2 onclick="vw('${h.id}')">Ver</button><button class=b2 onclick="dl('${h.id}')">Baixar</button><button class=b2 onclick="shr('${h.id}')">Enviar</button>`}
 else if(h.t=='f')a=`<b>${esc(h.cliente||'Sem cliente')}</b> em ${fd(h.em)}<br>${n(h.km)} km a ${f(h.ckm)} por km<br>Custo total ${f(h.ct)}, lucro ${f(h.lucro)}<br>Preço sugerido <b>${f(h.preco)}</b>`;
 else a=`<b>${esc(h.nome)}</b> em ${fd(h.em)}<br>Total ${f(h.total)} por km (variável ${f(h.varKm)}, fixo ${f(h.fixKm)})<br>${n(h.km)} km por mês`;
 return `<div class=card>${a}<div class=acts>${b}<button class=b2 onclick="del('${h.id}')">Apagar</button></div></div>`}
function del(id){if(confirm('Apagar este registro do histórico?')){S.hist=S.hist.filter(h=>h.id!=id);save();render()}}
// ---- perfil
V.perfil=()=>{const p=S.perfil;return `<h2>Meu perfil</h2><p class=mu>Preencha uma vez. Os dados aparecem nos seus orçamentos e recibos.</p><div class=card>${inp('pn','Nome da empresa ou profissional',p.nome||'')}${inp('pr','Nome do responsável',p.resp||'')}${inp('pt','Telefone',p.tel||'','tel')}${inp('pw','WhatsApp',p.whats||'','tel')}${inp('pe','E-mail',p.email||'','email')}${inp('pa','Endereço (opcional)',p.end||'')}${inp('pd','CPF ou CNPJ (opcional)',p.doc||'')}
 <label>Logotipo<input type=file accept="image/*" onchange="onLogo(event)"></label>${p.logo?`<img class=lg src="${p.logo}" alt="Logotipo"><button class=b2 onclick="Object.assign(S.perfil,readP());delete S.perfil.logo;save();render()">Remover logotipo</button>`:''}</div>
 <button class=b onclick="saveP()">Salvar perfil</button>
 <div class=card style="margin-top:18px"><h3>Seus dados ficam neste aparelho</h3><p class=mu>Nada é enviado para servidor. Se você limpar os dados do navegador ou trocar de celular, os dados somem.</p><button class=b2 onclick="wipe()">Apagar todos os dados deste aparelho</button></div>`};
const readP=()=>({nome:g('pn'),resp:g('pr'),tel:g('pt'),whats:g('pw'),email:g('pe'),end:g('pa'),doc:g('pd')});
function saveP(){Object.assign(S.perfil,readP());if(save())toast('Perfil salvo.')}
function onLogo(e){const fl=e.target.files[0];if(!fl)return;const rd=new FileReader();rd.onload=()=>{const im=new Image();im.onload=()=>{const s=Math.min(1,240/Math.max(im.width,im.height)),c=document.createElement('canvas');c.width=Math.round(im.width*s);c.height=Math.round(im.height*s);c.getContext('2d').drawImage(im,0,0,c.width,c.height);Object.assign(S.perfil,readP(),{logo:c.toDataURL('image/png'),lw:c.width,lh:c.height});save();render()};im.onerror=()=>toast('Não consegui ler essa imagem. Tente um PNG ou JPG.');im.src=rd.result};rd.readAsDataURL(fl)}
function wipe(){if(confirm('Apagar perfil, custo por km e todo o histórico deste aparelho? Não dá para desfazer.')){try{localStorage.removeItem(K)}catch(e){}S={perfil:{},vs:[],hist:[],n:{o:0,r:0}};go('inicio')}}
// ---- ícone do app (para quem salva na tela inicial)
(function(){try{const mk=n=>{const c=document.createElement('canvas');c.width=c.height=n;const x=c.getContext('2d'),u=n/180;x.fillStyle='#14243B';x.fillRect(0,0,n,n);
 [[34,88,28,48],[76,64,28,72],[118,34,28,102]].forEach((b,i)=>{x.fillStyle=i==2?'#F28C28':'#FFFFFF';x.beginPath();if(x.roundRect)x.roundRect(b[0]*u,b[1]*u,b[2]*u,b[3]*u,6*u);else x.rect(b[0]*u,b[1]*u,b[2]*u,b[3]*u);x.fill()});
 x.fillStyle='#159B69';x.fillRect(26*u,142*u,128*u,6*u);return c.toDataURL('image/png')};
 const a=document.createElement('link');a.rel='apple-touch-icon';a.href=mk(180);document.head.appendChild(a);
 const b=document.createElement('link');b.rel='icon';b.type='image/png';b.href=mk(192);document.head.appendChild(b)}catch(e){}})();
render();
</script></body></html>
