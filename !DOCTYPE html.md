<!DOCTYPE html>

<html lang="en">

<head>

&nbsp; <meta charset="utf-8" />

&nbsp; <meta name="viewport" content="width=device-width, initial-scale=1" />

&nbsp; <title>Supercentenarian Wiki (Local • Offline • Infinite)</title>

&nbsp; <style>

&nbsp;   :root{

&nbsp;     --bg:#0b0f14; --panel:#121821; --muted:#1a2230; --text:#e7eef7; --soft:#b7c3d9; --accent:#7cc4ff; --accent-2:#b98cff; --danger:#ff7c9a; --ok:#80e5a0; --warn:#ffd27c;

&nbsp;     --radius:16px; --shadow:0 10px 30px rgba(0,0,0,.35);

&nbsp;   }

&nbsp;   html,body{height:100%}

&nbsp;   body{margin:0; font-family: ui-sans-serif,system-ui,-apple-system,Segoe UI,Roboto,Inter,Helvetica,Arial,"Apple Color Emoji","Segoe UI Emoji"; background:linear-gradient(180deg,#0b0f14,#0e141c); color:var(--text)}

&nbsp;   a{color:var(--accent)}

&nbsp;   .app{max-width:1100px;margin:0 auto;padding:20px}

&nbsp;   .nav{position:sticky;top:0;background:rgba(9,13,18,.75);backdrop-filter: blur(8px);display:flex;gap:12px;align-items:center;padding:14px;border-bottom:1px solid #1d2937;z-index:30}

&nbsp;   .badge{font-size:12px;padding:4px 8px;border:1px solid #283548;border-radius:999px;background:#0f1621;color:var(--soft)}

&nbsp;   .brand{display:flex;gap:10px;align-items:center;font-weight:800;letter-spacing:.2px}

&nbsp;   .brand .dot{width:10px;height:10px;border-radius:50%;background:linear-gradient(135deg,var(--accent),var(--accent-2))}

&nbsp;   .spacer{flex:1}

&nbsp;   .btn{appearance:none;border:0;border-radius:12px;padding:10px 14px;background:var(--muted);color:var(--text);cursor:pointer;transition:.15s box-shadow,.15s transform,.15s background}

&nbsp;   .btn:hover{box-shadow:0 6px 18px rgba(0,0,0,.25);transform:translateY(-1px)}

&nbsp;   .btn.primary{background:linear-gradient(135deg,var(--accent),var(--accent-2));color:#08121c;font-weight:700}

&nbsp;   .btn.ghost{background:transparent;border:1px solid #273140}

&nbsp;   .btn.warn{background:linear-gradient(135deg,#ff9a7c,#ffd27c);color:#26130a}

&nbsp;   .searchbox{position:relative;flex:1;max-width:520px}

&nbsp;   .searchbox input{width:100%;padding:12px 14px 12px 40px;border-radius:12px;border:1px solid #2b3a4f;background:#0f1621;color:var(--text)}

&nbsp;   .searchbox svg{position:absolute;left:12px;top:50%;transform:translateY(-50%);opacity:.7}

&nbsp;   .suggest{position:absolute;left:0;right:0;top:calc(100% + 6px);background:#0f1621;border:1px solid #2b3a4f;border-radius:12px;box-shadow:var(--shadow);max-height:280px;overflow:auto;display:none}

&nbsp;   .suggest.visible{display:block}

&nbsp;   .suggest div{padding:10px 12px;cursor:pointer;border-bottom:1px solid #203046}

&nbsp;   .suggest div:last-child{border-bottom:none}

&nbsp;   .suggest .cat{font-size:11px;color:#8ea6c8;text-transform:uppercase;letter-spacing:.08em;padding:8px 12px;background:#0b111a;position:sticky;top:0}

&nbsp;   .grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:16px}

&nbsp;   .card{background:linear-gradient(180deg,#101724,#0d1320);border:1px solid #1f2a3a;border-radius:var(--radius);box-shadow:var(--shadow);padding:16px}

&nbsp;   .card h3{margin:0 0 6px 0}

&nbsp;   .meta{font-size:13px;color:var(--soft)}

&nbsp;   .pill{display:inline-block;padding:6px 10px;border-radius:999px;background:#0f1828;border:1px solid #263247;font-size:12px;color:#9fb5d3;margin-right:6px}

&nbsp;   .section{margin:24px 0}

&nbsp;   .section h2{margin:0 0 12px 0}

&nbsp;   .form{display:grid;grid-template-columns:repeat(12,1fr);gap:12px}

&nbsp;   .field{grid-column:span 6}

&nbsp;   .field.full{grid-column:1/-1}

&nbsp;   .field label{display:block;font-size:12px;color:#9fb5d3;margin:4px 2px}

&nbsp;   .field input,.field textarea,.field select{width:100%;padding:10px 12px;border-radius:12px;border:1px solid #2b3a4f;background:#0f1621;color:var(--text)}

&nbsp;   .list{background:#0f1621;border:1px solid #263247;border-radius:12px}

&nbsp;   .list-row{display:flex;gap:8px;padding:10px;border-bottom:1px solid #1e2a3b}

&nbsp;   .list-row:last-child{border-bottom:none}

&nbsp;   .small{font-size:12px;color:#8ea6c8}

&nbsp;   .footer{opacity:.7;font-size:12px;margin-top:18px}

&nbsp;   .tabs{display:flex;gap:8px;margin-bottom:12px}

&nbsp;   .tab{padding:8px 10px;border-radius:10px;border:1px solid #2b3a4f;background:#0f1621;cursor:pointer}

&nbsp;   .tab.active{background:linear-gradient(135deg,#152233,#0f1621);border-color:#405173}

&nbsp;   .kbd{font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace; font-size:12px;padding:2px 6px;border-radius:6px;background:#0d1320;border:1px solid #313e55;color:#9fb5d3}

&nbsp;   .chip{display:inline-flex;align-items:center;gap:6px;padding:6px 10px;border:1px dashed #33445d;border-radius:999px}

&nbsp;   .empty{padding:20px;border:1px dashed #33445d;border-radius:12px;text-align:center;color:#9fb5d3}

&nbsp;   .hero{display:grid;grid-template-columns:1.6fr 1fr;gap:16px;align-items:center}

&nbsp;   @media (max-width: 900px){ .hero{grid-template-columns:1fr} .nav{flex-wrap:wrap} }

&nbsp; </style>

</head>

<body>

&nbsp; <div class="nav">

&nbsp;   <div class="brand"><span class="dot"></span> Supercentenarian Wiki <span class="badge">Local • Editable</span></div>

&nbsp;   <div class="spacer"></div>

&nbsp;   <div class="searchbox">

&nbsp;     <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="11" cy="11" r="8"></circle><line x1="21" y1="21" x2="16.65" y2="16.65"></line></svg>

&nbsp;     <input id="globalSearch" placeholder="Search names or countries (e.g., ‘Venezuelan’)…" />

&nbsp;     <div id="suggest" class="suggest"></div>

&nbsp;   </div>

&nbsp;   <button class="btn ghost" onclick="Router.go('#/home')">Home</button>

&nbsp;   <button class="btn ghost" onclick="Router.go('#/new')">Add</button>

&nbsp;   <button class="btn ghost" onclick="Router.go('#/browse')">Browse</button>

&nbsp;   <button class="btn primary" onclick="Backup.exportJSON()">Export</button>

&nbsp;   <label class="btn" for="importFile">Import</label>

&nbsp;   <input id="importFile" type="file" accept="application/json" style="display:none" />

&nbsp; </div>



&nbsp; <div class="app" id="app"></div>



&nbsp; <script>

&nbsp; // ===== UTILITIES ==========================================================

&nbsp; const $ = sel => document.querySelector(sel);

&nbsp; const $$ = sel => \[...document.querySelectorAll(sel)];

&nbsp; const fmt = n => new Intl.NumberFormat().format(n);

&nbsp; const todayISO = () => new Date().toISOString().slice(0,10);

&nbsp; const slugify = s => s.toLowerCase().trim().replace(/\[^a-z0-9]+/g,'-').replace(/(^-|-$)/g,'');

&nbsp; const yearsBetween = (a,b) => Math.max(0, Math.floor((b-a)/ (365.2425\*24\*3600\*1000)));

&nbsp; const parseDate = d => d ? new Date(d) : null;

&nbsp; const safe = v => v==null?'' : String(v);



&nbsp; // Country list (ISO-like, 249 entries inc. territories) — truncated display uses search, so long list is OK

&nbsp; const COUNTRIES = \[

&nbsp;   "Afghanistan","Åland Islands","Albania","Algeria","American Samoa","Andorra","Angola","Anguilla","Antarctica","Antigua and Barbuda","Argentina","Armenia","Aruba","Australia","Austria","Azerbaijan","Bahamas","Bahrain","Bangladesh","Barbados","Belarus","Belgium","Belize","Benin","Bermuda","Bhutan","Bolivia","Bonaire, Sint Eustatius and Saba","Bosnia and Herzegovina","Botswana","Bouvet Island","Brazil","British Indian Ocean Territory","Brunei Darussalam","Bulgaria","Burkina Faso","Burundi","Cabo Verde","Cambodia","Cameroon","Canada","Cayman Islands","Central African Republic","Chad","Chile","China","Christmas Island","Cocos (Keeling) Islands","Colombia","Comoros","Congo","Congo, Democratic Republic of the","Cook Islands","Costa Rica","Côte d’Ivoire","Croatia","Cuba","Curaçao","Cyprus","Czechia","Denmark","Djibouti","Dominica","Dominican Republic","Ecuador","Egypt","El Salvador","Equatorial Guinea","Eritrea","Estonia","Eswatini","Ethiopia","Falkland Islands (Malvinas)","Faroe Islands","Fiji","Finland","France","French Guiana","French Polynesia","French Southern Territories","Gabon","Gambia","Georgia","Germany","Ghana","Gibraltar","Greece","Greenland","Grenada","Guadeloupe","Guam","Guatemala","Guernsey","Guinea","Guinea-Bissau","Guyana","Haiti","Heard Island and McDonald Islands","Holy See","Honduras","Hong Kong","Hungary","Iceland","India","Indonesia","Iran","Iraq","Ireland","Isle of Man","Israel","Italy","Jamaica","Japan","Jersey","Jordan","Kazakhstan","Kenya","Kiribati","Korea (North)","Korea (South)","Kuwait","Kyrgyzstan","Lao People’s Democratic Republic","Latvia","Lebanon","Lesotho","Liberia","Libya","Liechtenstein","Lithuania","Luxembourg","Macao","Madagascar","Malawi","Malaysia","Maldives","Mali","Malta","Marshall Islands","Martinique","Mauritania","Mauritius","Mayotte","Mexico","Micronesia","Moldova","Monaco","Mongolia","Montenegro","Montserrat","Morocco","Mozambique","Myanmar","Namibia","Nauru","Nepal","Netherlands","New Caledonia","New Zealand","Nicaragua","Niger","Nigeria","Niue","Norfolk Island","North Macedonia","Northern Mariana Islands","Norway","Oman","Pakistan","Palau","Palestine, State of","Panama","Papua New Guinea","Paraguay","Peru","Philippines","Pitcairn","Poland","Portugal","Puerto Rico","Qatar","Réunion","Romania","Russian Federation","Rwanda","Saint Barthélemy","Saint Helena, Ascension and Tristan da Cunha","Saint Kitts and Nevis","Saint Lucia","Saint Martin","Saint Pierre and Miquelon","Saint Vincent and the Grenadines","Samoa","San Marino","Sao Tome and Principe","Saudi Arabia","Senegal","Serbia","Seychelles","Sierra Leone","Singapore","Sint Maarten","Slovakia","Slovenia","Solomon Islands","Somalia","South Africa","South Georgia and the South Sandwich Islands","South Sudan","Spain","Sri Lanka","Sudan","Suriname","Svalbard and Jan Mayen","Sweden","Switzerland","Syrian Arab Republic","Taiwan","Tajikistan","Tanzania","Thailand","Timor-Leste","Togo","Tokelau","Tonga","Trinidad and Tobago","Tunisia","Turkey","Turkmenistan","Turks and Caicos Islands","Tuvalu","Uganda","Ukraine","United Arab Emirates","United Kingdom","United States of America","United States Minor Outlying Islands","Uruguay","Uzbekistan","Vanuatu","Venezuela","Viet Nam","Virgin Islands (British)","Virgin Islands (U.S.)","Wallis and Futuna","Western Sahara","Yemen","Zambia","Zimbabwe"

&nbsp; ];



&nbsp; // ===== DATA LAYER (LocalStorage) =========================================

&nbsp; const DB\_KEY = 'sc\_wiki\_v1';

&nbsp; const DB = {

&nbsp;   load(){

&nbsp;     try{ return JSON.parse(localStorage.getItem(DB\_KEY)) || {people:\[], history:\[], lastId:0}; }

&nbsp;     catch(e){ return {people:\[], history:\[], lastId:0}; }

&nbsp;   },

&nbsp;   save(state){ localStorage.setItem(DB\_KEY, JSON.stringify(state)); },

&nbsp;   clear(){ localStorage.removeItem(DB\_KEY); },

&nbsp; };

&nbsp; let state = DB.load();



&nbsp; // ===== ROUTER =============================================================

&nbsp; const Router = {

&nbsp;   go(hash){ location.hash = hash; },

&nbsp;   on(){

&nbsp;     const route = location.hash.replace('#','') || '/home';

&nbsp;     if(route.startsWith('/p/')) return Views.person(route.split('/p/')\[1]);

&nbsp;     if(route.startsWith('/edit/')) return Views.edit(route.split('/edit/')\[1]);

&nbsp;     if(route.startsWith('/new')) return Views.edit('new');

&nbsp;     if(route.startsWith('/browse')) return Views.browse();

&nbsp;     if(route.startsWith('/countries')) return Views.countries();

&nbsp;     return Views.home();

&nbsp;   }

&nbsp; };

&nbsp; window.addEventListener('hashchange', Router.on);

&nbsp; window.addEventListener('load', Router.on);



&nbsp; // ===== BACKUP =============================================================

&nbsp; const Backup = {

&nbsp;   exportJSON(){

&nbsp;     const blob = new Blob(\[JSON.stringify(state,null,2)], {type:'application/json'});

&nbsp;     const url = URL.createObjectURL(blob);

&nbsp;     const a = document.createElement('a');

&nbsp;     a.href=url; a.download='supercentenarian\_wiki\_backup\_'+Date.now()+'.json';

&nbsp;     a.click(); URL.revokeObjectURL(url);

&nbsp;   },

&nbsp;   async importJSON(file){

&nbsp;     const text = await file.text();

&nbsp;     try{

&nbsp;       const data = JSON.parse(text);

&nbsp;       if(!data.people) throw new Error('Invalid file');

&nbsp;       state = data; DB.save(state); Router.on();

&nbsp;       toast('Import successful. '+fmt(state.people.length)+' profiles loaded.', 'ok');

&nbsp;     }catch(e){ toast('Import failed: '+e.message, 'danger'); }

&nbsp;   }

&nbsp; };

&nbsp; $('#importFile').addEventListener('change', e=>{

&nbsp;   const f=e.target.files\[0]; if(f) Backup.importJSON(f);

&nbsp; });



&nbsp; // ===== TOASTS =============================================================

&nbsp; function toast(msg, kind='info'){

&nbsp;   let t=document.createElement('div'); t.textContent=msg; t.style.cssText=`position:fixed;right:16px;bottom:16px;background:${kind==='danger'?'#3a1020':kind==='ok'?'#0f2a1c':'#101724'};color:var(--text);border:1px solid #2b3a4f;border-left:4px solid ${kind==='danger'?'#ff7c9a':kind==='ok'?'#80e5a0':'#7cc4ff'};padding:12px 14px;border-radius:12px;box-shadow:var(--shadow);z-index:50`;

&nbsp;   document.body.appendChild(t); setTimeout(()=>t.remove(), 2800);

&nbsp; }



&nbsp; // ===== SEARCH / SUGGEST ===================================================

&nbsp; const Search = {

&nbsp;   index(){

&nbsp;     const names = state.people.map(p=>({type:'person', key: p.name, slug:p.slug}));

&nbsp;     const countries = \[...new Set(state.people.map(p=>p.birthCountry))].map(c=>({type:'country', key:c}));

&nbsp;     const allCountries = COUNTRIES.map(c=>({type:'country', key:c}));

&nbsp;     return \[...names, ...countries, ...allCountries];

&nbsp;   },

&nbsp;   run(q){

&nbsp;     q=q.toLowerCase();

&nbsp;     const pool = this.index();

&nbsp;     return pool.filter(x=>x.key \&\& x.key.toLowerCase().includes(q)).slice(0,50);

&nbsp;   }

&nbsp; };



&nbsp; const searchInput = $('#globalSearch');

&nbsp; const suggest = $('#suggest');

&nbsp; searchInput.addEventListener('input', ()=>{

&nbsp;   const q=searchInput.value.trim();

&nbsp;   if(!q){ suggest.classList.remove('visible'); suggest.innerHTML=''; return; }

&nbsp;   const results = Search.run(q);

&nbsp;   const person = results.filter(r=>r.type==='person');

&nbsp;   const country = results.filter(r=>r.type==='country');

&nbsp;   const html = \[

&nbsp;     person.length?'<div class="cat">People</div>'+person.map(r=>`<div data-kind="person" data-slug="${r.slug}">👤 ${r.key}</div>`).join(''):'' ,

&nbsp;     country.length?'<div class="cat">Countries</div>'+country.map(r=>`<div data-kind="country" data-name="${r.key}">🌍 ${r.key}</div>`).join(''):''

&nbsp;   ].join('');

&nbsp;   suggest.innerHTML = html || '<div class="empty">No matches</div>';

&nbsp;   suggest.classList.add('visible');

&nbsp; });

&nbsp; suggest.addEventListener('click', e=>{

&nbsp;   const row = e.target.closest('div\[data-kind]'); if(!row) return;

&nbsp;   suggest.classList.remove('visible');

&nbsp;   if(row.dataset.kind==='person') Router.go('#/p/'+row.dataset.slug);

&nbsp;   if(row.dataset.kind==='country') Router.go('#/browse?country='+encodeURIComponent(row.dataset.name));

&nbsp; });

&nbsp; document.addEventListener('click', (e)=>{

&nbsp;   if(!suggest.contains(e.target) \&\& e.target!==searchInput) suggest.classList.remove('visible');

&nbsp; });



&nbsp; // ===== VIEWS ==============================================================

&nbsp; const Views = {

&nbsp;   appEl: $('#app'),

&nbsp;   render(html){ this.appEl.innerHTML = html; },



&nbsp;   home(){

&nbsp;     const latest = \[...state.people].sort((a,b)=> (b.updatedAt||b.createdAt) - (a.updatedAt||a.createdAt)).slice(0,12);

&nbsp;     const total = state.people.length;

&nbsp;     this.render(`

&nbsp;       <div class="hero">

&nbsp;         <div class="card">

&nbsp;           <h2>Welcome</h2>

&nbsp;           <p>Build an infinite, local wiki of fictional supercentenarians. Everything saves to your browser (no server needed). Create pages, edit biographies, search by name or any of <span class="kbd">${COUNTRIES.length}</span> countries/territories, and export/import as JSON.</p>

&nbsp;           <div class="section">

&nbsp;             <div class="tabs">

&nbsp;               <span class="chip">Total profiles: <b>${fmt(total)}</b></span>

&nbsp;               <span class="chip">Last backup: <b>${safe(state.lastBackup||'—')}</b></span>

&nbsp;             </div>

&nbsp;             <button class="btn primary" onclick="Router.go('#/new')">+ Add Supercentenarian</button>

&nbsp;             <button class="btn" onclick="Router.go('#/browse')">Browse All</button>

&nbsp;             <button class="btn" onclick="Router.go('#/countries')">Browse by Country</button>

&nbsp;           </div>

&nbsp;           <div class="footer small">Tip: Press <span class="kbd">Ctrl/Cmd + K</span> to focus Search. Use <span class="kbd">Export</span> regularly to back up.</div>

&nbsp;         </div>

&nbsp;         <div class="card">

&nbsp;           <h3>Quick Stats</h3>

&nbsp;           <div class="list">

&nbsp;             <div class="list-row"><div class="spacer">Profiles</div><div><b>${fmt(total)}</b></div></div>

&nbsp;             <div class="list-row"><div class="spacer">Countries represented</div><div><b>${fmt(new Set(state.people.map(p=>p.birthCountry)).size)}</b></div></div>

&nbsp;             <div class="list-row"><div class="spacer">With awards</div><div><b>${fmt(state.people.filter(p=>safe(p.awards).trim()).length)}</b></div></div>

&nbsp;           </div>

&nbsp;         </div>

&nbsp;       </div>

&nbsp;       <div class="section">

&nbsp;         <h2>Latest</h2>

&nbsp;         ${latest.length?`<div class="grid">${latest.map(Cards.personCard).join('')}</div>`:`<div class="empty">No profiles yet. Be the first! Click <b>Add</b> above.</div>`}

&nbsp;       </div>

&nbsp;     `);

&nbsp;   },



&nbsp;   browse(){

&nbsp;     const url = new URL(location.href);

&nbsp;     const countryFilter = url.hash.includes('?country=') ? decodeURIComponent(url.hash.split('?country=')\[1]) : '';

&nbsp;     const q = url.hash.includes('?q=') ? decodeURIComponent(url.hash.split('?q=')\[1]) : '';

&nbsp;     let list = \[...state.people];

&nbsp;     if(countryFilter) list = list.filter(p=>p.birthCountry===countryFilter || p.deathCountry===countryFilter);

&nbsp;     if(q) list = list.filter(p=> p.name.toLowerCase().includes(q.toLowerCase()));

&nbsp;     list.sort((a,b)=> (b.updatedAt||b.createdAt) - (a.updatedAt||a.createdAt));



&nbsp;     const perPage = 18;

&nbsp;     const page = parseInt(url.searchParams?.get('page')||'1',10) || 1; // fallback for future

&nbsp;     const totalPages = Math.max(1, Math.ceil(list.length/perPage));

&nbsp;     const subset = list.slice((page-1)\*perPage, page\*perPage);



&nbsp;     this.render(`

&nbsp;       <div class="section">

&nbsp;         <h2>Browse ${countryFilter?`— <span class='pill'>${countryFilter}</span>`:''}</h2>

&nbsp;         <div class="form" style="margin-bottom:10px">

&nbsp;           <div class="field"><input id="browseName" placeholder="Filter by name…" value="${q}" /></div>

&nbsp;           <div class="field"><select id="browseCountry"><option value="">All countries…</option>${COUNTRIES.map(c=>`<option ${c===countryFilter?'selected':''}>${c}</option>`).join('')}</select></div>

&nbsp;           <div class="field"><button class="btn" id="browseApply">Apply</button></div>

&nbsp;         </div>

&nbsp;         ${subset.length?`<div class="grid">${subset.map(Cards.personCard).join('')}</div>`:`<div class="empty">No results.</div>`}

&nbsp;         <div class="section small">Page ${page} of ${totalPages}</div>

&nbsp;       </div>

&nbsp;     `);

&nbsp;     $('#browseApply').onclick = ()=>{

&nbsp;       const name = $('#browseName').value.trim();

&nbsp;       const c = $('#browseCountry').value;

&nbsp;       let h = '#/browse';

&nbsp;       const qs=\[]; if(c) qs.push('country='+encodeURIComponent(c)); if(name) qs.push('q='+encodeURIComponent(name));

&nbsp;       if(qs.length) h += '?'+qs.join('\&');

&nbsp;       Router.go(h);

&nbsp;     };

&nbsp;   },



&nbsp;   countries(){

&nbsp;     const counts = {};

&nbsp;     for(const p of state.people){ counts\[p.birthCountry] = (counts\[p.birthCountry]||0)+1; }

&nbsp;     const rows = COUNTRIES.map(c=>({c, n: counts\[c]||0})).sort((a,b)=> b.n-a.n || a.c.localeCompare(b.c));

&nbsp;     this.render(`

&nbsp;       <div class="section">

&nbsp;         <h2>Countries \& Territories <span class="small">(${COUNTRIES.length})</span></h2>

&nbsp;         <div class="grid">

&nbsp;           ${rows.map(r=>`<div class="card" style="display:flex;justify-content:space-between;align-items:center"><div>${r.c}</div><div class="pill">${r.n}</div><button class="btn" onclick="Router.go('#/browse?country=${encodeURIComponent(r.c)}')">View</button></div>`).join('')}

&nbsp;         </div>

&nbsp;       </div>

&nbsp;     `);

&nbsp;   },



&nbsp;   person(slug){

&nbsp;     const p = state.people.find(x=>x.slug===slug);

&nbsp;     if(!p){ this.render(`<div class='section'><div class='empty'>Profile not found.</div></div>`); return; }

&nbsp;     const age = (p.birth \&\& p.death)? yearsBetween(parseDate(p.birth), parseDate(p.death)) : (p.birth? yearsBetween(parseDate(p.birth), new Date()) : '—');

&nbsp;     this.render(`

&nbsp;       <div class="section">

&nbsp;         <div class="card">

&nbsp;           <div style="display:flex;gap:16px;align-items:center;flex-wrap:wrap">

&nbsp;             <div style="flex:1"><h2>${p.name}</h2>

&nbsp;               <div class="meta">${p.birthCountry||'—'} • born <b>${safe(p.birth)||'—'}</b> — died in ${p.deathCountry||'—'} <b>${safe(p.death)||'—'}</b> • Age ${age||'—'}</div>

&nbsp;               <div class="meta">Parents: ${safe(p.parents||'—')}</div>

&nbsp;               <div class="meta">Last updated: ${new Date(p.updatedAt||p.createdAt).toLocaleString()}</div>

&nbsp;             </div>

&nbsp;             <div style="display:flex;gap:8px">

&nbsp;               <button class="btn" onclick="Router.go('#/edit/${p.slug}')">Edit</button>

&nbsp;               <button class="btn warn" onclick="Actions.duplicate('${p.slug}')">Duplicate</button>

&nbsp;               <button class="btn" onclick="Actions.delete('${p.slug}')">Delete</button>

&nbsp;             </div>

&nbsp;           </div>

&nbsp;         </div>



&nbsp;         <div class="grid" style="margin-top:12px">

&nbsp;           <div class="card">

&nbsp;             <h3>Biography</h3>

&nbsp;             <div id="bio" contenteditable="true" class="list" style="padding:12px;min-height:120px">${safe(p.bio)||'<em class=small>Click to edit…</em>'}</div>

&nbsp;             <div style="margin-top:10px;display:flex;gap:8px"><button class="btn primary" onclick="Actions.saveBio('${p.slug}')">Save Bio</button><span class="small">Rich text allowed. Use paragraphs, lists, etc.</span></div>

&nbsp;           </div>

&nbsp;           <div class="card">

&nbsp;             <h3>Family</h3>

&nbsp;             <div class="small">Spouse(s)</div>

&nbsp;             ${(p.spouses||\[]).length? p.spouses.map(s=>`<div class='list-row'>💍 <b>${s.name}</b> (${safe(s.birth)||'?' } – ${safe(s.death)||'?'})</div>`).join(''): '<div class="empty">None</div>'}

&nbsp;             <div class="small" style="margin-top:8px">Children</div>

&nbsp;             ${(p.children||\[]).length? p.children.map(c=>`<div class='list-row'>👶 <b>${c.name}</b> (${safe(c.birth)||'?' } – ${safe(c.death)||'?'})</div>`).join(''): '<div class="empty">None</div>'}

&nbsp;           </div>

&nbsp;           <div class="card">

&nbsp;             <h3>Awards \& Achievements</h3>

&nbsp;             <div class="list" id="awards" contenteditable="true" style="padding:12px;min-height:90px">${safe(p.awards)||'<em class=small>Click to add awards…</em>'}</div>

&nbsp;             <div style="margin-top:10px"><button class="btn" onclick="Actions.saveAwards('${p.slug}')">Save Awards</button></div>

&nbsp;           </div>

&nbsp;         </div>

&nbsp;       </div>

&nbsp;     `);

&nbsp;   },



&nbsp;   edit(slug){

&nbsp;     const editing = slug!=='new';

&nbsp;     const p = editing ? state.people.find(x=>x.slug===slug) : {name:'', birth:'', death:'', birthCountry:'', deathCountry:'', parents:'', spouses:\[], children:\[], awards:'', bio:''};

&nbsp;     if(editing \&\& !p){ this.render(`<div class='section'><div class='empty'>Profile not found.</div></div>`); return; }

&nbsp;     this.render(`

&nbsp;       <div class="section">

&nbsp;         <h2>${editing?'Edit':'Create'} Supercentenarian</h2>

&nbsp;         <div class="form">

&nbsp;           <div class="field full"><label>Name</label><input id="f\_name" value="${safe(p.name)}" placeholder="Full name" /></div>

&nbsp;           <div class="field"><label>Date of Birth (YYYY-MM-DD)</label><input id="f\_birth" value="${safe(p.birth)}" placeholder="1873-05-01" /></div>

&nbsp;           <div class="field"><label>Date of Death (YYYY-MM-DD)</label><input id="f\_death" value="${safe(p.death)}" placeholder="1989-02-14" /></div>

&nbsp;           <div class="field"><label>Born in (Country)</label><select id="f\_birthC"><option value="">Select country…</option>${COUNTRIES.map(c=>`<option ${c===p.birthCountry?'selected':''}>${c}</option>`).join('')}</select></div>

&nbsp;           <div class="field"><label>Died in (Country)</label><select id="f\_deathC"><option value="">Select country…</option>${COUNTRIES.map(c=>`<option ${c===p.deathCountry?'selected':''}>${c}</option>`).join('')}</select></div>

&nbsp;           <div class="field full"><label>Parents (names and birth/death)</label><input id="f\_parents" value="${safe(p.parents)}" placeholder="e.g., Maria (1870–1950) \& Jose (1868–1942)" /></div>

&nbsp;           <div class="field full"><label>Biography</label><textarea id="f\_bio" rows="6" placeholder="Short life story…">${safe(p.bio)}</textarea></div>



&nbsp;           <div class="field full">

&nbsp;             <label>Spouse(s)</label>

&nbsp;             <div id="spouses" class="list"></div>

&nbsp;             <button class="btn" onclick="Forms.addRow('spouses')">+ Add spouse</button>

&nbsp;           </div>



&nbsp;           <div class="field full">

&nbsp;             <label>Children</label>

&nbsp;             <div id="children" class="list"></div>

&nbsp;             <button class="btn" onclick="Forms.addRow('children')">+ Add child</button>

&nbsp;           </div>



&nbsp;           <div class="field full"><label>Awards \& Achievements (rich text allowed later on profile)</label><textarea id="f\_awards" rows="4">${safe(p.awards)}</textarea></div>



&nbsp;           <div class="field full" style="display:flex;gap:8px;align-items:center">

&nbsp;             <button class="btn primary" id="saveBtn">${editing?'Save Changes':'Create Profile'}</button>

&nbsp;             ${editing?`<button class="btn" onclick="Router.go('#/p/${p.slug}')">Cancel</button>`:''}

&nbsp;           </div>

&nbsp;         </div>

&nbsp;       </div>

&nbsp;     `);



&nbsp;     // populate dynamic lists

&nbsp;     Forms.mount('spouses', p.spouses||\[]);

&nbsp;     Forms.mount('children', p.children||\[]);



&nbsp;     $('#saveBtn').onclick = ()=>{

&nbsp;       const next = {

&nbsp;         name: $('#f\_name').value.trim(),

&nbsp;         slug: editing? p.slug : slugify($('#f\_name').value.trim()||('person-'+(state.lastId+1))),

&nbsp;         birth: $('#f\_birth').value.trim(),

&nbsp;         death: $('#f\_death').value.trim(),

&nbsp;         birthCountry: $('#f\_birthC').value,

&nbsp;         deathCountry: $('#f\_deathC').value,

&nbsp;         parents: $('#f\_parents').value.trim(),

&nbsp;         bio: $('#f\_bio').value.trim(),

&nbsp;         spouses: Forms.collect('spouses'),

&nbsp;         children: Forms.collect('children'),

&nbsp;         awards: $('#f\_awards').value.trim(),

&nbsp;       };

&nbsp;       if(!next.name){ toast('Name is required', 'danger'); return; }

&nbsp;       if(editing){ Object.assign(p, next); p.updatedAt = Date.now(); }

&nbsp;       else{ next.createdAt = Date.now(); next.updatedAt = Date.now(); state.lastId++; state.people.push(next); }

&nbsp;       DB.save(state); Router.go('#/p/'+(editing?p.slug:next.slug));

&nbsp;     };

&nbsp;   },

&nbsp; };



&nbsp; // ===== FORMS (dynamic spouse/child rows) ==================================

&nbsp; const Forms = {

&nbsp;   mount(id, rows){

&nbsp;     const el = document.getElementById(id);

&nbsp;     el.innerHTML = rows.length? rows.map((r,i)=>this.rowHTML(id,i,r)).join('') : '<div class="empty">No entries yet.</div>';

&nbsp;   },

&nbsp;   rowHTML(kind, i, r){

&nbsp;     return `<div class="list-row" data-i="${i}">

&nbsp;       <input placeholder="Name" value="${safe(r.name)}" style="flex:2" />

&nbsp;       <input placeholder="Birth (YYYY-MM-DD)" value="${safe(r.birth)}" style="flex:1" />

&nbsp;       <input placeholder="Death (YYYY-MM-DD)" value="${safe(r.death)}" style="flex:1" />

&nbsp;       <button class="btn" onclick="Forms.remove('${kind}', ${i})">Remove</button>

&nbsp;     </div>`;

&nbsp;   },

&nbsp;   addRow(id){

&nbsp;     const el = document.getElementById(id);

&nbsp;     if(el.querySelector('.empty')) el.innerHTML='';

&nbsp;     const i = el.children.length;

&nbsp;     el.insertAdjacentHTML('beforeend', this.rowHTML(id, i, {name:'',birth:'',death:''}));

&nbsp;   },

&nbsp;   remove(id, index){

&nbsp;     const el = document.getElementById(id);

&nbsp;     const row = \[...el.children]\[index]; if(row) row.remove();

&nbsp;     if(!el.children.length) el.innerHTML='<div class="empty">No entries yet.</div>';

&nbsp;   },

&nbsp;   collect(id){

&nbsp;     const el = document.getElementById(id);

&nbsp;     return \[...el.querySelectorAll('.list-row')].map(r=>{

&nbsp;       const \[name,birth,death] = \[...r.querySelectorAll('input')].map(i=>i.value.trim());

&nbsp;       return {name,birth,death};

&nbsp;     }).filter(x=>x.name);

&nbsp;   }

&nbsp; };



&nbsp; // ===== CARDS ==============================================================

&nbsp; const Cards = {

&nbsp;   personCard(p){

&nbsp;     const age = (p.birth \&\& p.death)? yearsBetween(parseDate(p.birth), parseDate(p.death)) : '—';

&nbsp;     return `<div class="card">

&nbsp;       <h3>${p.name}</h3>

&nbsp;       <div class="meta">${p.birthCountry||'—'} → ${p.deathCountry||'—'}</div>

&nbsp;       <div class="meta">${safe(p.birth)||'—'} – ${safe(p.death)||'—'} • Age ${age}</div>

&nbsp;       <div style="margin-top:10px;display:flex;gap:8px;flex-wrap:wrap">

&nbsp;         <span class="pill">Spouses: ${(p.spouses||\[]).length}</span>

&nbsp;         <span class="pill">Children: ${(p.children||\[]).length}</span>

&nbsp;       </div>

&nbsp;       <div style="margin-top:10px"><button class="btn" onclick="Router.go('#/p/${p.slug}')">Open Page</button></div>

&nbsp;     </div>`;

&nbsp;   }

&nbsp; };



&nbsp; // ===== INLINE ACTIONS =====================================================

&nbsp; const Actions = {

&nbsp;   saveBio(slug){

&nbsp;     const p = state.people.find(x=>x.slug===slug); if(!p) return;

&nbsp;     p.bio = $('#bio').innerHTML; p.updatedAt = Date.now(); DB.save(state); toast('Biography saved','ok');

&nbsp;   },

&nbsp;   saveAwards(slug){

&nbsp;     const p = state.people.find(x=>x.slug===slug); if(!p) return;

&nbsp;     $('#awards').querySelectorAll('script').forEach(s=>s.remove()); // safety

&nbsp;     p.awards = $('#awards').innerHTML; p.updatedAt = Date.now(); DB.save(state); toast('Awards saved','ok');

&nbsp;   },

&nbsp;   duplicate(slug){

&nbsp;     const p = state.people.find(x=>x.slug===slug); if(!p) return;

&nbsp;     const copy = JSON.parse(JSON.stringify(p));

&nbsp;     copy.name = p.name + ' (Copy)'; copy.slug = slugify(copy.name + '-' + (state.lastId+1)); copy.createdAt = Date.now(); copy.updatedAt = Date.now();

&nbsp;     state.lastId++; state.people.push(copy); DB.save(state); Router.go('#/edit/'+copy.slug);

&nbsp;   },

&nbsp;   delete(slug){

&nbsp;     if(!confirm('Delete this profile? This cannot be undone.')) return;

&nbsp;     state.people = state.people.filter(x=>x.slug!==slug); DB.save(state); toast('Deleted','danger'); Router.go('#/browse');

&nbsp;   }

&nbsp; };



&nbsp; // ===== SHORTCUTS ==========================================================

&nbsp; document.addEventListener('keydown', (e)=>{

&nbsp;   if((e.ctrlKey||e.metaKey) \&\& e.key.toLowerCase()==='k'){

&nbsp;     e.preventDefault(); searchInput.focus(); searchInput.select();

&nbsp;   }

&nbsp; });



&nbsp; // ===== SAMPLE DATA (optional bootstrap if empty) ==========================

&nbsp; if(!state.people.length){

&nbsp;   const sample = {

&nbsp;     name:'Luciana Rivera de Ávila',

&nbsp;     slug:'luciana-rivera-de-avila',

&nbsp;     birth:'1889-03-14', death:'2003-07-09',

&nbsp;     birthCountry:'Venezuela', deathCountry:'Spain',

&nbsp;     parents:'Carmen Rivera (1860–1930) \& Julio Ávila (1857–1932)',

&nbsp;     spouses:\[{name:'Esteban Flores',birth:'1886-06-01',death:'1958-11-12'}],

&nbsp;     children:\[{name:'Isabel Flores',birth:'1910-01-05',death:'1992-04-20'},{name:'Rafael Flores',birth:'1913-09-12',death:'2001-01-30'}],

&nbsp;     awards:'<ul><li>Order of Cultural Merit (1962)</li><li>City of Valencia Centennial Medal (1989)</li></ul>',

&nbsp;     bio:'<p>Luciana was a weaver, educator, and community archivist whose notebooks preserved the oral histories of three towns through the 20th century. She migrated to Valencia, Spain in 1956.</p>',

&nbsp;     createdAt: Date.now(), updatedAt: Date.now()

&nbsp;   };

&nbsp;   state.people.push(sample); state.lastId=1; DB.save(state);

&nbsp; }



&nbsp; </script>

</body>

</html>



