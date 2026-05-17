<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>richardweb.com</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Mono:wght@300;400;500&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg: #05070f;
            --surface: rgba(12,18,34,0.78);
            --surface2: rgba(20,28,50,0.5);
            --border: rgba(255,255,255,0.06);
            --border-accent: rgba(99,224,255,0.2);
            --text: #e8edf8;
            --muted: #5a6a8a;
            --dim: #3a4a6a;
            --accent: #1de9ff;
            --accent3: #34eba8;
            --danger: #ff6b9d;
            --glow: rgba(29,233,255,0.12);
        }
        * { box-sizing: border-box; margin: 0; padding: 0; }
        body, html {
            width: 100%; height: 100%;
            background: var(--bg);
            font-family: 'DM Mono', monospace;
            color: var(--text);
            display: flex; flex-direction: column;
            justify-content: center; align-items: center;
            overflow: hidden;
        }
        canvas#bg { position:fixed; inset:0; z-index:0; opacity:0.4; }
        body::before {
            content:''; position:fixed; inset:0;
            background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='1'/%3E%3C/svg%3E");
            opacity:0.025; z-index:0; pointer-events:none;
        }
        .glow-orb { position:fixed; border-radius:50%; filter:blur(120px); pointer-events:none; z-index:0; }
        .glow-orb.a { width:700px;height:700px;top:-200px;left:-200px;background:radial-gradient(circle,rgba(99,224,255,0.07),transparent 70%);animation:driftA 18s ease-in-out infinite alternate; }
        .glow-orb.b { width:500px;height:500px;bottom:-150px;right:-100px;background:radial-gradient(circle,rgba(167,139,250,0.09),transparent 70%);animation:driftB 14s ease-in-out infinite alternate; }
        @keyframes driftA { 0%{transform:translate(0,0)} 100%{transform:translate(80px,60px)} }
        @keyframes driftB { 0%{transform:translate(0,0)} 100%{transform:translate(-60px,-80px)} }

        /* ════ ALARM OVERLAY ════ */
        #alarm-overlay {
            position:fixed; inset:0; z-index:10000;
            background:rgba(2,5,14,0.85);
            backdrop-filter:blur(10px);
            display:flex; align-items:center; justify-content:center;
            opacity:0; pointer-events:none;
            transition:opacity 0.3s ease;
        }
        #alarm-overlay.active { opacity:1; pointer-events:all; }

        #alarm-box {
            background:rgba(6,12,26,0.98);
            border:1px solid rgba(29,233,255,0.28);
            border-radius:24px;
            padding:2rem 2.25rem;
            width:min(88vw,360px);
            text-align:center;
            display:flex; flex-direction:column; align-items:center; gap:1rem;
            box-shadow:
                0 0 0 1px rgba(29,233,255,0.05) inset,
                0 40px 80px rgba(0,0,0,0.85),
                0 0 80px -10px rgba(29,233,255,0.18);
            transform:scale(0.88) translateY(16px);
            transition:transform 0.4s cubic-bezier(0.16,1,0.3,1);
        }
        #alarm-overlay.active #alarm-box { transform:scale(1) translateY(0); }

        .alarm-icon-wrap {
            width:76px; height:76px; border-radius:50%;
            background:rgba(29,233,255,0.07);
            border:1.5px solid rgba(29,233,255,0.25);
            display:flex; align-items:center; justify-content:center;
            font-size:2.2rem;
            position:relative;
            animation:iconBob 1s ease-in-out infinite alternate;
        }
        @keyframes iconBob { 0%{transform:scale(1)} 100%{transform:scale(1.07)} }
        .alarm-icon-wrap::before, .alarm-icon-wrap::after {
            content:''; position:absolute; inset:-10px;
            border-radius:50%; border:1.5px solid rgba(29,233,255,0.15);
            animation:ripple 2s ease-out infinite;
        }
        .alarm-icon-wrap::after { animation-delay:1s; }
        @keyframes ripple {
            0%  { transform:scale(1); opacity:0.7; }
            100%{ transform:scale(1.9); opacity:0; }
        }

        .alarm-eyebrow {
            font-size:0.58rem; text-transform:uppercase; letter-spacing:0.2em;
            color:var(--accent); font-weight:600;
        }
        .alarm-title-text {
            font-family:'Syne',sans-serif; font-size:1.1rem; font-weight:800;
            color:var(--text); line-height:1.3; letter-spacing:-0.02em;
        }
        .alarm-due {
            font-size:0.68rem; color:var(--muted);
            background:rgba(255,255,255,0.03);
            border:1px solid var(--border);
            padding:0.28rem 0.85rem; border-radius:20px;
        }
        .alarm-btns { display:flex; gap:0.6rem; width:100%; margin-top:0.3rem; }
        .btn-snooze {
            flex:1; background:var(--surface2); border:1px solid var(--border);
            color:var(--muted); font-family:'Syne',sans-serif; font-size:0.7rem;
            font-weight:600; padding:0.6rem; border-radius:10px; cursor:pointer;
            transition:border-color 0.2s,color 0.2s;
        }
        .btn-snooze:hover { border-color:var(--border-accent); color:var(--text); }
        .btn-dismiss {
            flex:2; background:linear-gradient(135deg,var(--accent),#00c9e0);
            border:none; color:#050a14; font-family:'Syne',sans-serif;
            font-size:0.7rem; font-weight:700; padding:0.6rem;
            border-radius:10px; cursor:pointer; transition:opacity 0.2s;
        }
        .btn-dismiss:hover { opacity:0.85; }

        /* ════ TOAST ════ */
        #toast-container {
            position:fixed; top:16px; right:16px; z-index:9000;
            display:flex; flex-direction:column; gap:8px; pointer-events:none;
        }
        .toast {
            background:rgba(8,14,28,0.97);
            border:1px solid rgba(29,233,255,0.22);
            border-left:3px solid var(--accent);
            border-radius:12px; padding:0.8rem 1rem; width:275px;
            box-shadow:0 8px 24px rgba(0,0,0,0.5);
            pointer-events:all;
            animation:toastIn 0.35s cubic-bezier(0.16,1,0.3,1) both;
            display:flex; align-items:flex-start; gap:9px;
        }
        .toast.success { border-left-color:var(--accent3); border-color:rgba(52,235,168,0.22); }
        .toast.warn    { border-left-color:#fbbf24;         border-color:rgba(251,191,36,0.22); }
        @keyframes toastIn  { from{opacity:0;transform:translateX(22px)} to{opacity:1;transform:translateX(0)} }
        @keyframes toastOut { from{opacity:1;transform:translateX(0)}    to{opacity:0;transform:translateX(22px)} }
        .toast.removing { animation:toastOut 0.25s ease forwards; }
        .toast-icon  { font-size:1rem; flex-shrink:0; margin-top:1px; }
        .toast-body  { flex:1; min-width:0; }
        .toast-title { font-family:'Syne',sans-serif; font-size:0.74rem; font-weight:700; color:var(--text); margin-bottom:1px; }
        .toast-msg   { font-size:0.61rem; color:var(--muted); line-height:1.5; }
        .toast-close { background:none; border:none; color:var(--dim); cursor:pointer; font-size:0.85rem; padding:2px; transition:color 0.2s; flex-shrink:0; }
        .toast-close:hover { color:var(--text); }

        /* ════ CARD ════ */
        .card {
            position:relative; z-index:1;
            width:min(92vw,680px); max-height:92vh;
            background:var(--surface);
            backdrop-filter:blur(32px) saturate(1.4);
            border:1px solid var(--border); border-radius:28px;
            overflow:hidden; display:flex; flex-direction:column;
            box-shadow:0 0 0 1px rgba(255,255,255,0.03) inset,0 40px 80px -16px rgba(0,0,0,0.7),0 0 80px -20px var(--glow);
            animation:cardIn 0.7s cubic-bezier(0.16,1,0.3,1) both;
        }
        @keyframes cardIn { from{opacity:0;transform:translateY(24px) scale(0.97)} to{opacity:1;transform:translateY(0) scale(1)} }
        .card::after { content:'';position:absolute;inset:0;background:linear-gradient(180deg,transparent 0%,rgba(255,255,255,0.012) 50%,transparent 100%);background-size:100% 4px;pointer-events:none;z-index:99;opacity:0.5; }

        .header { display:flex;align-items:center;justify-content:space-between;padding:1.1rem 1.75rem;border-bottom:1px solid var(--border);background:rgba(8,12,24,0.5);gap:12px;flex-shrink:0; }
        .logo-group { display:flex;align-items:center;gap:10px; }
        .status-dot { width:7px;height:7px;border-radius:50%;background:var(--accent3);box-shadow:0 0 8px var(--accent3),0 0 18px rgba(52,235,168,0.4);animation:sdBlink 2.5s ease-in-out infinite;flex-shrink:0; }
        @keyframes sdBlink { 0%,100%{opacity:1} 50%{opacity:0.45} }
        .logo-text { font-family:'Syne',sans-serif;font-size:0.875rem;font-weight:700;color:var(--text);letter-spacing:-0.02em; }
        .tag { background:rgba(29,233,255,0.08);border:1px solid rgba(29,233,255,0.2);color:var(--accent);font-size:0.6rem;font-weight:500;padding:0.18rem 0.6rem;border-radius:20px;letter-spacing:0.08em;text-transform:uppercase;transition:all 0.3s; }
        .tag.ringing { background:rgba(255,107,157,0.12);border-color:rgba(255,107,157,0.35);color:var(--danger);animation:tagBlink 0.8s ease infinite; }
        @keyframes tagBlink { 0%,100%{opacity:1} 50%{opacity:0.5} }

        .datetime { display:flex;align-items:center;gap:10px;font-size:0.68rem;color:var(--muted);background:rgba(255,255,255,0.02);border:1px solid var(--border);padding:0.3rem 0.85rem;border-radius:20px; }
        .datetime .sep { width:1px;height:10px;background:var(--dim); }
        .datetime .t { color:var(--accent);font-weight:500; }

        .body { padding:1.5rem 1.75rem;display:flex;flex-direction:column;gap:1.1rem;overflow-y:auto;flex:1; }
        .body::-webkit-scrollbar { width:4px; }
        .body::-webkit-scrollbar-thumb { background:var(--dim);border-radius:4px; }

        .hero { text-align:center; }
        .hero h1 { font-family:'Syne',sans-serif;font-size:clamp(1.8rem,6vw,2.5rem);font-weight:800;letter-spacing:-0.04em;line-height:1;background:linear-gradient(135deg,#ffffff 10%,#a8d8ff 50%,var(--accent) 90%);-webkit-background-clip:text;-webkit-text-fill-color:transparent;margin-bottom:0.35rem; }
        .hero p { font-size:0.72rem;color:var(--muted);line-height:1.6; }

        .section-label { font-size:0.6rem;text-transform:uppercase;letter-spacing:0.15em;color:var(--dim);margin-bottom:0.6rem;display:flex;align-items:center;gap:8px; }
        .section-label::after { content:'';flex:1;height:1px;background:var(--border); }

        .tasks { display:flex;flex-direction:column;gap:0.5rem; }
        .task { display:flex;align-items:center;gap:12px;padding:0.7rem 1rem;background:var(--surface2);border:1px solid var(--border);border-radius:14px;transition:border-color 0.2s,box-shadow 0.2s,opacity 0.3s,transform 0.3s;animation:taskIn 0.35s cubic-bezier(0.16,1,0.3,1) both; }
        @keyframes taskIn { from{opacity:0;transform:translateY(8px) scale(0.98)} to{opacity:1;transform:translateY(0) scale(1)} }
        .task:hover { border-color:var(--border-accent);box-shadow:0 0 20px -4px rgba(29,233,255,0.1); }
        .task.removing { opacity:0;transform:translateX(20px) scale(0.95); }
        .task.firing { animation:taskFire 0.7s ease infinite; }
        @keyframes taskFire { 0%{box-shadow:0 0 0 0 rgba(255,107,157,0.5); border-color:var(--danger);} 70%{box-shadow:0 0 0 10px rgba(255,107,157,0); border-color:var(--danger);} 100%{box-shadow:none;} }

        .task-check { width:18px;height:18px;border-radius:5px;border:1.5px solid var(--dim);cursor:pointer;flex-shrink:0;display:flex;align-items:center;justify-content:center;transition:border-color 0.2s,background 0.2s;font-size:0.65rem; }
        .task-check:hover { border-color:var(--accent3); }
        .task-check.done { background:rgba(52,235,168,0.15);border-color:var(--accent3);color:var(--accent3); }
        .task-icon { width:30px;height:30px;border-radius:9px;display:flex;align-items:center;justify-content:center;font-size:0.8rem;flex-shrink:0; }
        .task-icon.blue   { background:rgba(99,102,241,0.15);border:1px solid rgba(99,102,241,0.25); }
        .task-icon.teal   { background:rgba(29,233,255,0.1); border:1px solid rgba(29,233,255,0.2); }
        .task-icon.purple { background:rgba(167,139,250,0.12);border:1px solid rgba(167,139,250,0.25); }
        .task-icon.green  { background:rgba(52,235,168,0.1); border:1px solid rgba(52,235,168,0.2); }
        .task-icon.pink   { background:rgba(255,107,157,0.1);border:1px solid rgba(255,107,157,0.2); }
        .task-info { flex:1;min-width:0;text-align:left; }
        .task-title { font-size:0.78rem;font-weight:500;color:var(--text);white-space:nowrap;overflow:hidden;text-overflow:ellipsis; }
        .task-title.done-text { text-decoration:line-through;color:var(--muted); }
        .task-meta { font-size:0.62rem;color:var(--muted);margin-top:2px; }
        .pill { font-size:0.57rem;font-weight:600;padding:0.2rem 0.6rem;border-radius:20px;white-space:nowrap;flex-shrink:0; }
        .pill.upcoming { background:rgba(29,233,255,0.1);color:var(--accent);border:1px solid rgba(29,233,255,0.25); }
        .pill.soon     { background:rgba(255,107,157,0.12);color:var(--danger);border:1px solid rgba(255,107,157,0.28); }
        .pill.overdue  { background:rgba(255,107,157,0.18);color:var(--danger);border:1px solid rgba(255,107,157,0.4);animation:pb 2s infinite; }
        .pill.now      { background:rgba(29,233,255,0.18);color:var(--accent);border:1px solid rgba(29,233,255,0.5);animation:pb 0.8s infinite; }
        .pill.done-pill{ background:rgba(52,235,168,0.1);color:var(--accent3);border:1px solid rgba(52,235,168,0.25); }
        @keyframes pb { 0%,100%{opacity:1} 50%{opacity:0.45} }
        .btn-delete { width:24px;height:24px;border-radius:7px;border:none;background:transparent;color:var(--dim);cursor:pointer;display:flex;align-items:center;justify-content:center;flex-shrink:0;transition:background 0.2s,color 0.2s; }
        .btn-delete:hover { background:rgba(255,107,157,0.12);color:var(--danger); }

        .btn-row { display:flex;gap:0.5rem;margin-top:0.2rem; }
        .btn-add-task {
            flex:1;display:flex;align-items:center;justify-content:center;gap:8px;
            padding:0.65rem;background:rgba(29,233,255,0.05);
            border:1px dashed rgba(29,233,255,0.2);border-radius:14px;
            color:var(--accent);font-family:'DM Mono',monospace;font-size:0.72rem;
            cursor:pointer;transition:background 0.2s,border-color 0.2s,transform 0.15s;
        }
        .btn-add-task:hover { background:rgba(29,233,255,0.09);border-color:rgba(29,233,255,0.4);transform:translateY(-1px); }
        .btn-test {
            display:flex;align-items:center;justify-content:center;gap:6px;
            padding:0.65rem 1rem;background:rgba(255,107,157,0.05);
            border:1px dashed rgba(255,107,157,0.22);border-radius:14px;
            color:var(--danger);font-family:'DM Mono',monospace;font-size:0.68rem;
            cursor:pointer;transition:background 0.2s,border-color 0.2s,transform 0.15s;
            white-space:nowrap;
        }
        .btn-test:hover { background:rgba(255,107,157,0.1);border-color:rgba(255,107,157,0.4);transform:translateY(-1px); }

        .url-bar { display:flex;background:rgba(4,8,18,0.8);border:1px solid var(--border);border-radius:14px;overflow:hidden;transition:border-color 0.2s,box-shadow 0.2s; }
        .url-bar:focus-within { border-color:rgba(29,233,255,0.3);box-shadow:0 0 0 3px rgba(29,233,255,0.05); }
        .url-prefix { padding:0 0.85rem;display:flex;align-items:center;color:var(--dim);font-size:0.75rem;border-right:1px solid var(--border);user-select:none;white-space:nowrap; }
        .url-prefix svg { margin-right:6px; }
        .url-input { flex:1;background:transparent;border:none;padding:0.7rem 0.9rem;color:var(--text);font-family:'DM Mono',monospace;font-size:0.78rem;outline:none;min-width:0; }
        .url-input::placeholder { color:var(--dim); }
        .btn-open { background:linear-gradient(135deg,var(--accent),#00c9e0);color:#050a14;border:none;padding:0.7rem 1.35rem;font-family:'Syne',sans-serif;font-weight:700;font-size:0.75rem;cursor:pointer;transition:opacity 0.2s,transform 0.15s;display:flex;align-items:center;gap:6px;white-space:nowrap; }
        .btn-open:hover { opacity:0.88;transform:translateX(1px); }
        .quick-links { display:flex;gap:0.5rem;flex-wrap:wrap;margin-top:0.55rem; }
        .ql-btn { background:var(--surface2);border:1px solid var(--border);color:var(--muted);font-family:'DM Mono',monospace;font-size:0.65rem;padding:0.3rem 0.75rem;border-radius:20px;cursor:pointer;transition:border-color 0.2s,color 0.2s,background 0.2s;display:flex;align-items:center;gap:5px; }
        .ql-btn:hover { border-color:var(--border-accent);color:var(--accent);background:rgba(29,233,255,0.05); }

        .footer { display:flex;align-items:center;justify-content:space-between;padding:0.8rem 1.75rem;border-top:1px solid var(--border);background:rgba(4,8,18,0.3);gap:12px;flex-shrink:0; }
        .footer-note { font-size:0.62rem;color:var(--dim);line-height:1.5; }
        .footer-badge { font-size:0.6rem;color:var(--dim);border:1px solid var(--border);padding:0.2rem 0.65rem;border-radius:20px;white-space:nowrap;flex-shrink:0; }

        /* ════ MODAL ════ */
        .modal-overlay { position:fixed;inset:0;z-index:200;background:rgba(2,5,14,0.7);backdrop-filter:blur(6px);display:flex;align-items:center;justify-content:center;opacity:0;pointer-events:none;transition:opacity 0.25s; }
        .modal-overlay.open { opacity:1;pointer-events:all; }
        .modal { background:rgba(10,16,32,0.95);border:1px solid rgba(99,224,255,0.15);border-radius:22px;padding:1.75rem;width:min(90vw,420px);box-shadow:0 32px 64px -12px rgba(0,0,0,0.8);transform:translateY(20px) scale(0.96);transition:transform 0.3s cubic-bezier(0.16,1,0.3,1);display:flex;flex-direction:column;gap:1.1rem; }
        .modal-overlay.open .modal { transform:translateY(0) scale(1); }
        .modal-header { display:flex;align-items:center;justify-content:space-between; }
        .modal-title { font-family:'Syne',sans-serif;font-size:1.1rem;font-weight:700;color:var(--text); }
        .modal-close { background:none;border:none;color:var(--muted);font-size:1.2rem;cursor:pointer;padding:4px;border-radius:6px;transition:color 0.2s,background 0.2s; }
        .modal-close:hover { color:var(--text);background:rgba(255,255,255,0.05); }
        .field { display:flex;flex-direction:column;gap:0.4rem; }
        .field label { font-size:0.62rem;text-transform:uppercase;letter-spacing:0.12em;color:var(--dim); }
        .field input,.field select { background:rgba(4,8,18,0.8);border:1px solid var(--border);border-radius:10px;padding:0.65rem 0.85rem;color:var(--text);font-family:'DM Mono',monospace;font-size:0.78rem;outline:none;width:100%;transition:border-color 0.2s,box-shadow 0.2s; }
        .field input:focus,.field select:focus { border-color:rgba(29,233,255,0.35);box-shadow:0 0 0 3px rgba(29,233,255,0.06); }
        .field select option { background:#0a1020; }
        .field-row { display:grid;grid-template-columns:1fr 1fr;gap:0.75rem; }
        .modal-actions { display:flex;gap:0.65rem;margin-top:0.25rem; }
        .btn-cancel { flex:1;background:var(--surface2);border:1px solid var(--border);color:var(--muted);font-family:'Syne',sans-serif;font-size:0.75rem;font-weight:600;padding:0.65rem;border-radius:10px;cursor:pointer;transition:border-color 0.2s,color 0.2s; }
        .btn-cancel:hover { border-color:var(--border-accent);color:var(--text); }
        .btn-save { flex:2;background:linear-gradient(135deg,var(--accent),#00c9e0);border:none;color:#050a14;font-family:'Syne',sans-serif;font-size:0.75rem;font-weight:700;padding:0.65rem;border-radius:10px;cursor:pointer;transition:opacity 0.2s,transform 0.15s; }
        .btn-save:hover { opacity:0.88;transform:translateY(-1px); }
        .modal-hint { font-size:0.62rem;color:var(--dim);text-align:center; }
        .modal-hint span { color:var(--accent); }

        .empty-state { text-align:center;padding:1rem 0;color:var(--dim);font-size:0.7rem;line-height:1.8; }
        .empty-state .icon { font-size:1.5rem;display:block;margin-bottom:0.4rem;opacity:0.4; }
    </style>
</head>
<body>
<canvas id="bg"></canvas>
<div class="glow-orb a"></div>
<div class="glow-orb b"></div>
<div id="toast-container"></div>

<!-- ALARM OVERLAY -->
<div id="alarm-overlay">
    <div id="alarm-box">
        <div class="alarm-icon-wrap" id="al-icon">🔔</div>
        <div class="alarm-eyebrow">⏰ Reminder Due</div>
        <div class="alarm-title-text" id="al-title">—</div>
        <div class="alarm-due" id="al-due">—</div>
        <div class="alarm-btns">
            <button class="btn-snooze"  onclick="snoozeAlarm()">⏱ Snooze 5 min</button>
            <button class="btn-dismiss" onclick="dismissAlarm()">✓ Dismiss</button>
        </div>
    </div>
</div>

<!-- ADD TASK MODAL -->
<div class="modal-overlay" id="modal">
    <div class="modal">
        <div class="modal-header">
            <span class="modal-title">New Task Reminder</span>
            <button class="modal-close" onclick="closeModal()">✕</button>
        </div>
        <div class="field">
            <label>Task Title</label>
            <input id="m-title" type="text" placeholder="e.g. Review pull request" maxlength="60">
        </div>
        <div class="field-row">
            <div class="field"><label>Due Date</label><input id="m-date" type="date"></div>
            <div class="field"><label>Due Time</label><input id="m-time" type="time"></div>
        </div>
        <div class="field-row">
            <div class="field">
                <label>Icon</label>
                <select id="m-icon">
                    <option value="📋">📋 Clipboard</option>
                    <option value="⚙️">⚙️ Settings</option>
                    <option value="🚀">🚀 Launch</option>
                    <option value="💡">💡 Idea</option>
                    <option value="🔍">🔍 Research</option>
                    <option value="📝">📝 Notes</option>
                    <option value="🗂️">🗂️ Files</option>
                    <option value="⭐">⭐ Important</option>
                    <option value="🔔">🔔 Reminder</option>
                    <option value="🧪">🧪 Testing</option>
                </select>
            </div>
            <div class="field">
                <label>Color</label>
                <select id="m-color">
                    <option value="blue">Blue</option>
                    <option value="teal">Teal</option>
                    <option value="purple">Purple</option>
                    <option value="green">Green</option>
                    <option value="pink">Pink</option>
                </select>
            </div>
        </div>
        <p class="modal-hint">🔔 An <span>alarm screen & sound</span> will play at the due time.</p>
        <div class="modal-actions">
            <button class="btn-cancel" onclick="closeModal()">Cancel</button>
            <button class="btn-save"   onclick="saveTask()">+ Add Task</button>
        </div>
    </div>
</div>

<!-- MAIN CARD -->
<div class="card">
    <div class="header">
        <div class="logo-group">
            <div class="status-dot"></div>
            <span class="logo-text">richardweb.com</span>
            <span class="tag" id="alarm-tag">reminders on</span>
        </div>
        <div class="datetime">
            <span class="t" id="cal">—</span>
            <div class="sep"></div>
            <span class="t" id="clk">—</span>
        </div>
    </div>

    <div class="body">
        <div class="hero">
            <h1>richardweb.com</h1>
            <p>Your personal workspace. Browse the web safely via external tabs.</p>
        </div>

        <div>
            <div class="section-label">Task Reminders</div>
            <div class="tasks" id="task-list"></div>
            <div class="btn-row">
                <button class="btn-add-task" onclick="openModal()">
                    <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/></svg>
                    Add Reminder
                </button>
                <button class="btn-test" onclick="testAlarm()">🔔 Test Alarm</button>
            </div>
        </div>

        <div>
            <div class="section-label">Open External URL</div>
            <div class="url-bar">
                <div class="url-prefix">
                    <svg width="10" height="10" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><circle cx="12" cy="12" r="10"/><line x1="2" y1="12" x2="22" y2="12"/><path d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"/></svg>
                    https://
                </div>
                <input id="url" class="url-input" type="text" value="www.google.com" placeholder="www.google.com" spellcheck="false" autocomplete="off">
                <button class="btn-open" onclick="openURL()">
                    Open
                    <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>
                </button>
            </div>
            <div class="quick-links">
                <button class="ql-btn" onclick="setURL('www.google.com')">🔍 Google</button>
                <button class="ql-btn" onclick="setURL('www.youtube.com')">▶ YouTube</button>
                <button class="ql-btn" onclick="setURL('mail.google.com')">✉ Gmail</button>
                <button class="ql-btn" onclick="setURL('www.wikipedia.org')">📖 Wikipedia</button>
            </div>
        </div>
    </div>

    <div class="footer">
        <p class="footer-note">⚠ Enable popups and click anywhere once to unlock alarm sounds.</p>
        <span class="footer-badge">v4.2 · running</span>
    </div>
</div>

<script>
/* ── PARTICLES ── */
(function(){
    const cv=document.getElementById('bg'),cx=cv.getContext('2d');
    let W,H,P=[];
    const resize=()=>{W=cv.width=innerWidth;H=cv.height=innerHeight;};
    const init=()=>{P=[];for(let i=0;i<55;i++)P.push({x:Math.random()*W,y:Math.random()*H,r:Math.random()*1.2+0.3,vx:(Math.random()-.5)*.25,vy:(Math.random()-.5)*.25,o:Math.random()*.5+.1});};
    const draw=()=>{
        cx.clearRect(0,0,W,H);
        for(let i=0;i<P.length;i++)for(let j=i+1;j<P.length;j++){const dx=P[i].x-P[j].x,dy=P[i].y-P[j].y,d=Math.sqrt(dx*dx+dy*dy);if(d<130){cx.beginPath();cx.moveTo(P[i].x,P[i].y);cx.lineTo(P[j].x,P[j].y);cx.strokeStyle=`rgba(29,233,255,${.07*(1-d/130)})`;cx.lineWidth=.5;cx.stroke();}}
        P.forEach(p=>{cx.beginPath();cx.arc(p.x,p.y,p.r,0,Math.PI*2);cx.fillStyle=`rgba(29,233,255,${p.o})`;cx.fill();p.x+=p.vx;p.y+=p.vy;if(p.x<0)p.x=W;if(p.x>W)p.x=0;if(p.y<0)p.y=H;if(p.y>H)p.y=0;});
        requestAnimationFrame(draw);
    };
    resize();init();draw();
    addEventListener('resize',()=>{resize();init();});
})();

/* ── CLOCK ── */
function tick(){
    const n=new Date();
    document.getElementById('cal').textContent=n.toLocaleDateString('en-US',{weekday:'short',month:'short',day:'numeric',year:'numeric'});
    document.getElementById('clk').textContent=n.toLocaleTimeString('en-US',{hour:'2-digit',minute:'2-digit',second:'2-digit'});
}
tick(); setInterval(tick,1000);

/* ── URL ── */
function openURL(){let v=document.getElementById('url').value.trim();if(!v)return;if(!v.startsWith('http'))v='https://'+v;window.open(v,'_blank','noopener,noreferrer');}
function setURL(u){document.getElementById('url').value=u;document.getElementById('url').focus();}
document.getElementById('url').addEventListener('keydown',e=>{if(e.key==='Enter')openURL();});

/* ── TOAST ── */
function showToast(icon,title,msg,type='',dur=4500){
    const el=document.createElement('div');
    el.className=`toast ${type}`;
    el.innerHTML=`<span class="toast-icon">${icon}</span><div class="toast-body"><div class="toast-title">${esc(title)}</div><div class="toast-msg">${esc(msg)}</div></div><button class="toast-close" onclick="rmToast(this.parentElement)">✕</button>`;
    document.getElementById('toast-container').appendChild(el);
    if(dur>0)setTimeout(()=>rmToast(el),dur);
}
function rmToast(el){if(!el||!el.parentElement)return;el.classList.add('removing');setTimeout(()=>{if(el.parentElement)el.parentElement.removeChild(el);},260);}

/* ── AUDIO SYNC ENGINE ── */
let audioCtx = null;
let alarmInterval = null;

function initAudio() {
    if (!audioCtx) {
        audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    }
    if (audioCtx.state === 'suspended') {
        audioCtx.resume();
    }
}
// Automatically attaches audio contextual unlock hooks to common layout targets
window.addEventListener('click', initAudio, { once: false });

function startAlarmSound() {
    initAudio();
    stopAlarmSound(); 

    // Robust synthetic siren arrangement
    alarmInterval = setInterval(() => {
        if (!audioCtx) return;
        try {
            const time = audioCtx.currentTime;
            
            const osc1 = audioCtx.createOscillator();
            const gain1 = audioCtx.createGain();
            osc1.type = 'triangle';
            osc1.frequency.setValueAtTime(880, time);
            osc1.frequency.exponentialRampToValueAtTime(1200, time + 0.4);
            gain1.gain.setValueAtTime(0.3, time);
            gain1.gain.exponentialRampToValueAtTime(0.001, time + 0.45);
            osc1.connect(gain1);
            gain1.connect(audioCtx.destination);
            osc1.start(time);
            osc1.stop(time + 0.45);

            const osc2 = audioCtx.createOscillator();
            const gain2 = audioCtx.createGain();
            osc2.type = 'sine';
            osc2.frequency.setValueAtTime(660, time + 0.2);
            osc2.frequency.exponentialRampToValueAtTime(950, time + 0.6);
            gain2.gain.setValueAtTime(0.25, time + 0.2);
            gain2.gain.exponentialRampToValueAtTime(0.001, time + 0.65);
            osc2.connect(gain2);
            gain2.connect(audioCtx.destination);
            osc2.start(time + 0.2);
            osc2.stop(time + 0.65);

        } catch (e) {
            console.error("Audio block:", e);
        }
    }, 800);
}

function stopAlarmSound() {
    if (alarmInterval) {
        clearInterval(alarmInterval);
        alarmInterval = null;
    }
}

/* ── STORAGE ── */
const SK='rw_tasks_v1', FK='rw_fired_v1';
function loadTasks(){try{return JSON.parse(localStorage.getItem(SK))||[];}catch{return[];}}
function saveTasks(t){try{localStorage.setItem(SK,JSON.stringify(t));}catch(e){}}
function loadFired(){try{return JSON.parse(localStorage.getItem(FK))||{};}catch{return{};}}
function saveFired(f){try{localStorage.setItem(FK,JSON.stringify(f));}catch(e){}}

let tasks=loadTasks(), fired=loadFired();

/* ── HELPERS ── */
function esc(s){return String(s).replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;');}

// Resolves precision timestamp mapping across local system boundaries
function getDueMs(d, t) {
    if (!d || !t) return null;
    const parts = t.split(':');
    const target = new Date(d);
    target.setHours(parseInt(parts[0], 10), parseInt(parts[1], 10), 0, 0);
    return target.getTime();
}

function fmtDate(d,t){
    if(!d)return'No due date';
    const dueMs = getDueMs(d,t);
    return dueMs ? new Date(dueMs).toLocaleString('en-US',{weekday:'short',month:'short',day:'numeric',year:'numeric',hour:'2-digit',minute:'2-digit'}) : '—';
}

function getBadge(d,t,done){
    if(done)return{label:'Done',cls:'done-pill'};
    if(!d || !t)return{label:'No Time',cls:'upcoming'};
    const diff=getDueMs(d,t)-Date.now();
    if(diff>=-15000&&diff<=15000)return{label:'Now!',cls:'now'};
    if(diff<0)return{label:'Overdue',cls:'overdue'};
    if(diff<3600000)return{label:'< 1 hr',cls:'soon'};
    return{label:'Upcoming',cls:'upcoming'};
}

/* ── RENDER ── */
function renderTasks(){
    const list=document.getElementById('task-list');
    if(!tasks.length){
        list.innerHTML='<div class="empty-state"><span class="icon">📭</span>No reminders yet.<br>Click "+ Add Reminder" to get started.</div>';
        return;
    }
    list.innerHTML='';
    tasks.forEach((t,i)=>{
        const b=getBadge(t.date,t.time,t.done);
        const isFiring = fired[t.id] && !t.done;
        const d=document.createElement('div');
        d.className=`task ${isFiring?'firing':''}`;d.dataset.id=t.id;d.style.animationDelay=(i*.04)+'s';
        d.innerHTML=`
            <div class="task-check ${t.done?'done':''}" onclick="toggleDone('${t.id}')">${t.done?'✓':''}</div>
            <div class="task-icon ${t.color}">${t.icon}</div>
            <div class="task-info">
                <div class="task-title ${t.done?'done-text':''}">${esc(t.title)}</div>
                <div class="task-meta">${fmtDate(t.date,t.time)}</div>
            </div>
            <span class="pill ${b.cls}">${b.label}</span>
            <button class="btn-delete" onclick="deleteTask('${t.id}')" title="Delete">
                <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><polyline points="3 6 5 6 21 6"/><path d="M19 6l-1 14a2 2 0 0 1-2 2H8a2 2 0 0 1-2-2L5 6"/><path d="M10 11v6M14 11v6"/><path d="M9 6V4h6v2"/></svg>
            </button>`;
        list.appendChild(d);
    });
}

function toggleDone(id){
    const t=tasks.find(x=>x.id===id);
    if(t){
        t.done=!t.done;
        if(!t.done && fired[id]) delete fired[id]; // Reset if unmarked
        saveTasks(tasks); saveFired(fired); renderTasks();
    }
}

function deleteTask(id){
    const el=document.querySelector(`.task[data-id="${id}"]`);
    if(el){el.classList.add('removing');setTimeout(()=>{tasks=tasks.filter(x=>x.id!==id);delete fired[id];saveTasks(tasks);saveFired(fired);renderTasks();},280);}
}

/* ── NOTIFICATIONS & ALARM ── */
let alarmTask = null;

if ("Notification" in window && Notification.permission === "default") {
    setTimeout(() => {
        Notification.requestPermission().then(permission => {
            if (permission === "granted") {
                showToast('🔔', 'Alerts Active', 'Click workspace background once to ensure sounds unmuted.', 'success');
            }
        });
    }, 1500);
}

function sendDesktopNotification(task) {
    if (!("Notification" in window) || Notification.permission !== "granted") return;
    const title = task.id === '__test__' ? "System Diagnostics" : "⏰ Workspace Alert Due";
    const options = {
        body: task.title,
        icon: `data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 100 100%22><text y=%22.9em%22 font-size=%2290%22>${task.icon}</text></svg>`,
        requireInteraction: true,
        tag: task.id
    };
    const n = new Notification(title, options);
    n.onclick = function(e) { e.preventDefault(); window.focus(); if (alarmTask?.id !== task.id) showAlarm(task); n.close(); };
}

function showAlarm(task){
    alarmTask = task;
    document.getElementById('al-icon').textContent = task.icon;
    document.getElementById('al-title').textContent = task.title;
    document.getElementById('al-due').textContent = task.date ? fmtDate(task.date, task.time) : 'Active test event sequence.';
    document.getElementById('alarm-overlay').classList.add('active');
    
    const tag = document.getElementById('alarm-tag');
    tag.textContent = '🔔 alarm!';
    tag.classList.add('ringing');
    
    startAlarmSound();
    sendDesktopNotification(task);
}

function dismissAlarm(){
    stopAlarmSound();
    document.getElementById('alarm-overlay').classList.remove('active');
    const tag = document.getElementById('alarm-tag');
    tag.textContent = 'reminders on';
    tag.classList.remove('ringing');
    if(alarmTask && alarmTask.id !== '__test__'){
        const t = tasks.find(x => x.id === alarmTask.id);
        if(t){t.done = true; saveTasks(tasks); renderTasks();}
    }
    alarmTask = null;
}

function snoozeAlarm(){
    stopAlarmSound();
    document.getElementById('alarm-overlay').classList.remove('active');
    const tag = document.getElementById('alarm-tag');
    tag.textContent = 'reminders on';
    tag.classList.remove('ringing');
    if(alarmTask && alarmTask.id !== '__test__'){
        const snoozeTime = new Date(Date.now() + 5 * 60 * 1000);
        const pad = x => String(x).padStart(2, '0');
        alarmTask.date = `${snoozeTime.getFullYear()}-${pad(snoozeTime.getMonth()+1)}-${pad(snoozeTime.getDate())}`;
        alarmTask.time = `${pad(snoozeTime.getHours())}:${pad(snoozeTime.getMinutes())}`;
        delete fired[alarmTask.id];
        saveFired(fired); saveTasks(tasks); renderTasks();
        showToast('⏱', 'Snoozed 5 min', `"${alarmTask.title}" scheduled for ${alarmTask.time}`, 'warn');
    }
    alarmTask = null;
}

function testAlarm(){
    initAudio();
    showAlarm({id: '__test__', icon: '🔔', title: 'Test Alarm — Verification Successful!', date: '', time: ''});
}

/* ── AGGRESSIVE REMINDER ENGINE ── */
function checkReminders(){
    const now = Date.now();
    let updated = false;
    
    tasks.forEach(task => {
        if(task.done || fired[task.id]) return;
        const due = getDueMs(task.date, task.time);
        if(!due) return;
        
        // Catches anything precisely due now, or up to 5 minutes late window
        if(now >= due && now <= (due + 300000)){
            fired[task.id] = true;
            updated = true;
            showAlarm(task);
        }
    });
    
    if(updated) {
        saveFired(fired);
        renderTasks();
    }
}

/* ── MODAL ── */
function openModal(){
    const n = new Date(Date.now() + 60000), pad = x => String(x).padStart(2, '0'); // defaults to 1 minute from now
    document.getElementById('m-date').value = `${n.getFullYear()}-${pad(n.getMonth()+1)}-${pad(n.getDate())}`;
    document.getElementById('m-time').value = `${pad(n.getHours())}:${pad(n.getMinutes())}`;
    document.getElementById('m-title').value = '';
    document.getElementById('modal').classList.add('open');
    setTimeout(() => document.getElementById('m-title').focus(), 200);
}
function closeModal(){document.getElementById('modal').classList.remove('open');}

function saveTask(){
    const title = document.getElementById('m-title').value.trim();
    if(!title){document.getElementById('m-title').focus(); return;}
    const task = {
        id: 't' + Date.now(), title,
        date: document.getElementById('m-date').value,
        time: document.getElementById('m-time').value,
        icon: document.getElementById('m-icon').value,
        color: document.getElementById('m-color').value,
        done: false
    };
    tasks.push(task); saveTasks(tasks); renderTasks(); closeModal();
    showToast(task.icon, 'Reminder Logged', 'System will fire audio visual alerts once due.', 'success');
}

document.getElementById('modal').addEventListener('click', function(e){if(e.target === this) closeModal();});
document.addEventListener('keydown', e => {
    if(e.key === 'Escape'){
        closeModal();
        if(document.getElementById('alarm-overlay').classList.contains('active')) dismissAlarm();
    }
    if(e.key === 'Enter' && document.getElementById('modal').classList.contains('open')){
        const a = document.activeElement;
        if(a && (a.tagName === 'INPUT' || a.tagName === 'SELECT')) saveTask();
    }
});

/* ── INIT ── */
renderTasks();
setInterval(renderTasks,   15000);
setInterval(checkReminders, 2000); // Checked aggressively every 2 seconds
</script>
</body>
</html>
