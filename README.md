<!doctype html>
<html lang="pt">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1,user-scalable=no" />
  <title>Convite de Casamento — Confirmação de Presença</title>

  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Inter:wght@300;400;600&display=swap" rel="stylesheet">

  <style>
    :root{
      --bg:#F7F6F4;
      --card:#FFFFFF;
      --accent:#8A5D35;
      --muted:#6B6B6B;
    }
    *{box-sizing:border-box;margin:0;padding:0}
    html,body{
      width:100%;
      height:100%;
      font-family:'Inter',system-ui,-apple-system,"Segoe UI",Roboto,"Helvetica Neue",Arial;
      background:linear-gradient(180deg,#FBFBFA,var(--bg));
      color:#222;
      overflow-x:hidden;
      scroll-behavior:smooth;
    }
    body{
      display:flex;
      justify-content:center;
      align-items:flex-start;
      padding:20px;
    }

    .wrap{
      width:100%;
      max-width:960px;
      background:linear-gradient(180deg, rgba(255,255,255,0.9), var(--card));
      border-radius:22px;
      box-shadow: 0 10px 25px rgba(20,20,20,0.08);
      overflow:hidden;
      display:grid;
      grid-template-columns:1fr 400px;
      transition:all 0.3s ease;
    }

    .hero{
      padding:48px;
      display:flex;
      flex-direction:column;
      justify-content:center;
      background:
        radial-gradient(600px 200px at 10% 10%, rgba(138,93,53,0.03), transparent 10%),
        linear-gradient(180deg, rgba(255,255,255,0.6), transparent 30%);
    }

    .names{
      font-family:'Playfair Display',serif;
      font-size:clamp(28px,5vw,46px);
      color:var(--accent);
      margin-bottom:10px;
    }
    .date{
      color:var(--muted);
      font-size:clamp(13px,2vw,15px);
      font-weight:600;
      letter-spacing:0.8px;
      text-transform:uppercase;
      margin-bottom:6px;
    }
    .lead{
      font-size:clamp(14px,2vw,16px);
      color:#333;
      line-height:1.6;
      max-width:60ch;
    }

    .side{
      padding:28px;
      background:linear-gradient(180deg, rgba(255,255,255,0.75), rgba(255,255,255,0.9));
      border-left:1px solid rgba(0,0,0,0.03);
      display:flex;
      flex-direction:column;
      gap:16px;
    }

    form.rsvp{
      display:flex;
      flex-direction:column;
      gap:12px;
    }
    .field{display:flex;flex-direction:column;gap:6px}
    label{
      font-size:13px;
      color:var(--muted);
      font-weight:600;
    }
    input[type="text"], select, textarea{
      padding:10px 12px;
      border-radius:10px;
      border:1px solid rgba(0,0,0,0.08);
      background:transparent;
      outline:none;
      font-size:15px;
      transition:all 0.2s;
    }
    input:focus, select:focus, textarea:focus{
      border-color:var(--accent);
      box-shadow:0 0 0 2px rgba(138,93,53,0.15);
    }
    textarea{min-height:84px;resize:vertical}
    .row{display:flex;gap:10px;flex-wrap:wrap}
    .row .field{flex:1;min-width:120px}
    .btn{
      padding:12px 18px;
      border-radius:12px;
      border:0;
      cursor:pointer;
      font-weight:600;
      font-size:15px;
      background:linear-gradient(90deg,var(--accent),#6e4a2b);
      color:#fff;
      transition:opacity .3s;
    }
    .btn:hover{opacity:0.9}
    .success{
      padding:12px;
      border-radius:10px;
      background:linear-gradient(180deg,#EAF8F0,#DFF2E6);
      color:#0A7A3A;
      border:1px solid rgba(10,122,58,0.08);
    }
    footer.invite-note{
      margin-top:auto;
      font-size:12px;
      color:var(--muted);
      text-align:center;
      margin-top:20px;
    }

    /* ===== RESPONSIVIDADE ===== */
    @media (max-width:880px){
      .wrap{
        grid-template-columns:1fr;
        border-radius:16px;
      }
      .hero{
        padding:30px 22px;
        text-align:center;
        align-items:center;
      }
      .side{
        padding:24px 20px;
        border-left:none;
        border-top:1px solid rgba(0,0,0,0.05);
      }
    }

    @media (max-width:480px){
      body{padding:10px}
      .wrap{border-radius:12px}
      .hero{padding:20px 16px}
      .lead{font-size:14px}
      .btn{font-size:14px}
    }
  </style>
</head>
<body>
  <div class="wrap">
    <section class="hero">
      <p class="date">Cerimónia Religiosa e Salão do Evento</p>
      <h1 class="names">Lerry & Fátima</h1>
      <p class="lead">
        Temos a honra de convidar-te para celebrar connosco o início da nossa vida a dois.
        Será um momento de alegria, música e amor — esperamos contar com a tua presença.
      </p>
    </section>

    <aside class="side">
      <div>
        <h3 style="margin:0;font-family:'Playfair Display',serif;color:var(--accent)">Confirmação de Presença</h3>
        <p style="font-size:13px;color:var(--muted);margin:6px 0 0 0">Preenche o formulário para confirmarmos o teu lugar à mesa.</p>
      </div>

      <form id="rsvpForm" class="rsvp" autocomplete="off">
        <div class="row">
          <div class="field">
            <label for="name">Nome completo</label>
            <input id="name" name="nome" type="text" required placeholder="Ex.: Maria Fernandes" />
          </div>
          <div class="field">
            <label for="attend">Comparecerá?</label>
            <select id="attend" name="comparecera" required>
              <option value="">Selecciona...</option>
              <option value="Sim">Sim — Confirmo a presença</option>
              <option value="Não">Não — Infelizmente</option>
            </select>
          </div>
        </div>

        <div class="field">
          <label for="guests">Número de acompanhantes</label>
          <select id="guests" name="acompanhante" required>
            <option value="">Selecciona...</option>
            <option value="sozinho">Apenas eu</option>
            <option value="1">Eu + 1 acompanhante</option>
          </select>
        </div>

        <div class="field">
          <label for="message">Mensagem para Noivos - opcional</label>
          <textarea id="message" name="mensagem" placeholder="Deixa uma mensagem para os noivos..."></textarea>
        </div>

        <button type="submit" class="btn">Confirmar Presença</button>

        <div id="responseMsg" role="status" style="display:none;margin-top:8px"></div>

        <footer class="invite-note">
          Dúvidas? Contacta: <strong>+258 86 296 4125 / +258 85 320 6058</strong>
        </footer>
      </form>
    </aside>
  </div>

  <script>
    const FORMSPREE_ENDPOINT = "https://formspree.io/f/xzzjlqjq";
    const form = document.getElementById('rsvpForm');
    const responseMsg = document.getElementById('responseMsg');

    form.addEventListener('submit', async (e) => {
      e.preventDefault();
      responseMsg.style.display = 'none';
      responseMsg.className = '';
      responseMsg.textContent = '';

      const name = form.nome.value.trim();
      if(!name){ alert('Por favor preenche o teu nome.'); return; }

      const fd = new FormData(form);
      try{
        const res = await fetch(FORMSPREE_ENDPOINT, {
          method: 'POST',
          headers: {'Accept': 'application/json'},
          body: fd
        });
        if(res.ok){
          responseMsg.style.display = 'block';
          responseMsg.className = 'success';
          responseMsg.innerHTML = '✔️ Obrigado! A tua presença foi registada.';
          form.reset();
        } else {
          responseMsg.style.display = 'block';
          responseMsg.innerHTML = '❌ Erro ao enviar. Tenta novamente.';
        }
      } catch(err){
        responseMsg.style.display = 'block';
        responseMsg.innerHTML = '❌ Erro de rede.';
      }
    });
  </script>
</body>
</html>
