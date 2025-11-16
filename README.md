<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <title>Prevent → Linha de Exames</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <style>
    :root {
      --bg: #f5f5fb;
      --card-bg: #ffffff;
      --primary: #2563eb;
      --primary-soft: rgba(37, 99, 235, 0.08);
      --border: #e2e8f0;
      --text: #111827;
      --muted: #6b7280;
      --radius: 16px;
      --shadow: 0 18px 40px rgba(15, 23, 42, 0.12);
    }

    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      padding: 24px;
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI",
        sans-serif;
      background: radial-gradient(circle at top left, #dbeafe, #f5f5fb 40%);
      color: var(--text);
    }

    .app {
      max-width: 900px;
      margin: 0 auto;
      background: linear-gradient(135deg, #eff6ff, #ffffff);
      border-radius: 24px;
      box-shadow: var(--shadow);
      padding: 24px 24px 28px;
      border: 1px solid rgba(148, 163, 184, 0.4);
    }

    header {
      display: flex;
      justify-content: space-between;
      gap: 12px;
      align-items: center;
      margin-bottom: 20px;
      flex-wrap: wrap;
    }

    header h1 {
      font-size: 1.3rem;
      margin: 0;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    header h1 span.logo-pill {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      width: 28px;
      height: 28px;
      border-radius: 999px;
      background: radial-gradient(circle at 20% 20%, #3b82f6, #1d4ed8);
      color: #fff;
      font-weight: 700;
      font-size: 0.9rem;
      box-shadow: 0 0 15px rgba(37, 99, 235, 0.4);
    }

    header p {
      margin: 0;
      font-size: 0.85rem;
      color: var(--muted);
    }

    .badge {
      border-radius: 999px;
      padding: 4px 10px;
      font-size: 0.7rem;
      text-transform: uppercase;
      letter-spacing: 0.06em;
      background: var(--primary-soft);
      color: #1d4ed8;
      border: 1px solid rgba(37, 99, 235, 0.22);
      font-weight: 600;
    }

    .card {
      background: var(--card-bg);
      border-radius: var(--radius);
      padding: 16px 16px 18px;
      border: 1px solid var(--border);
      margin-bottom: 14px;
    }

    .card h2 {
      margin: 0 0 10px;
      font-size: 1rem;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .card h2 span.chip {
      width: 22px;
      height: 22px;
      border-radius: 999px;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      font-size: 0.8rem;
      background: #e0f2fe;
      color: #0369a1;
    }

    label {
      display: inline-block;
      font-size: 0.8rem;
      margin-bottom: 4px;
      color: #4b5563;
    }

    input[type="date"],
    input[type="file"] {
      font-size: 0.85rem;
    }

    textarea {
      width: 100%;
      min-height: 140px;
      resize: vertical;
      padding: 10px 11px;
      font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas,
        "Liberation Mono", "Courier New", monospace;
      border-radius: 12px;
      border: 1px solid var(--border);
      font-size: 0.8rem;
      line-height: 1.4;
      outline: none;
      background: #f9fafb;
    }

    textarea:focus {
      border-color: var(--primary);
      box-shadow: 0 0 0 1px rgba(37, 99, 235, 0.25);
      background: #ffffff;
    }

    .input-row {
      display: flex;
      gap: 10px;
      align-items: center;
      flex-wrap: wrap;
      margin-bottom: 10px;
    }

    .input-row input[type="date"] {
      padding: 6px 8px;
      border-radius: 10px;
      border: 1px solid var(--border);
      min-width: 160px;
    }

    .btn {
      border-radius: 999px;
      border: none;
      padding: 7px 14px;
      font-size: 0.8rem;
      font-weight: 600;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      gap: 6px;
      transition: transform 0.05s ease, box-shadow 0.08s ease,
        background 0.15s ease;
    }

    .btn-primary {
      background: linear-gradient(135deg, #2563eb, #1d4ed8);
      color: #fff;
      box-shadow: 0 6px 14px rgba(37, 99, 235, 0.4);
    }

    .btn-primary:hover {
      transform: translateY(-1px);
      box-shadow: 0 10px 20px rgba(37, 99, 235, 0.45);
    }

    .btn-ghost {
      background: transparent;
      border: 1px solid var(--border);
      color: #374151;
    }

    .btn-ghost:hover {
      background: #f3f4f6;
    }

    .hint {
      font-size: 0.75rem;
      color: var(--muted);
      margin-top: 4px;
    }

    .footer-note {
      margin-top: 8px;
      font-size: 0.75rem;
      color: var(--muted);
    }

    .footer-note code {
      background: #f3f4f6;
      padding: 1px 4px;
      border-radius: 4px;
      font-size: 0.72rem;
    }
  </style>
</head>
<body>
  <main class="app">
    <header>
      <div>
        <h1>
          <span class="logo-pill">Rx</span>
          Prevent → Linha de Exames
        </h1>
        <p>
          Sobe o PDF da Prevent, escolhe a data e gera
          <strong>“data: exame / exame / exame”</strong>.
        </p>
      </div>
      <span class="badge">Versão 1 – focada em Prevent</span>
    </header>

    <!-- Entrada -->
    <section class="card">
      <h2><span class="chip">1</span> Entrada (PDF ou texto)</h2>
      <div class="input-row">
        <div>
          <label for="examDate">Data dos exames</label><br />
          <input type="date" id="examDate" />
        </div>
        <button class="btn btn-ghost" id="btnClearAll" type="button">
          Limpar tudo
        </button>
      </div>

      <label for="fileInput">Arquivo PDF da Prevent</label><br />
      <input type="file" id="fileInput" accept=".pdf,.txt" />
      <div class="hint">
        • Ideal: PDF com texto (não apenas imagem escaneada).<br />
        • Também funciona com <strong>.txt</strong> ou colando o texto manualmente abaixo.
      </div>

      <div style="margin-top: 10px;">
        <label for="inputText">Texto dos exames (opcional – copiar/colar)</label>
        <textarea
          id="inputText"
          placeholder="Se o PDF não for lido, cole aqui o texto do laudo da Prevent..."
        ></textarea>
        <div class="hint">
          O programa usa principalmente a grade tipo: “UREIA 148 156 104(*) ...”, “CREATININA 2.20 2.47 1.84(*) ...” etc.
        </div>
      </div>
    </section>

    <!-- Saída -->
    <section class="card">
      <h2><span class="chip">2</span> Saída formatada</h2>

      <div class="input-row" style="justify-content: space-between;">
        <span class="hint">
          Saída: <strong>DD.MM.AAAA: Ureia 148 / Cr 2,20 / Na 136 / ...</strong>
        </span>
        <div>
          <button class="btn btn-ghost" type="button" id="btnCopy">
            Copiar linha
          </button>
          <button class="btn btn-primary" type="button" id="btnGenerate">
            Gerar linha
          </button>
        </div>
      </div>

      <label for="outputText">Linha pronta para o prontuário</label>
      <textarea
        id="outputText"
        readonly
        placeholder="15.11.2025: Ureia 148 / Cr 2,20 / Na 136 / K 4,5 / PCR 30,6 / TGO 246 / TGP 193 / BT 0,40 / BD 0,20 / BI 0,20"
      ></textarea>

      <p class="footer-note">
        • Exames conhecidos (Prevent): <code>UREIA</code>, <code>CREATININA</code>,
        <code>SÓDIO</code>, <code>POTASSIO</code>, <code>PCR</code>, <code>TGO</code>,
        <code>TGP</code>, <code>BILI TOTAL</code>, <code>BILI DIRETA</code>,
        <code>BILI INDIRETA</code> viram abreviações (Ureia, Cr, Na, K, PCR, TGO, TGP, BT, BD, BI).<br />
        • Qualquer outro exame em formato “NOME 123,4 mg/dL” sai por extenso (NOME 123,4).
      </p>
    </section>
  </main>

  <!-- PDF.js para ler PDFs -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/pdf.js/2.6.347/pdf.min.js"></script>
  <script>   // ============================   // EXAMES CONHECIDOS (PREVENT)   // ============================   const KNOWN_EXAMS = {     "UREIA": "UREIA",     "CREATININA": "CR",     "SODIO": "NA",     "SÓDIO": "NA",     "POTASSIO": "K",     "POTÁSSIO": "K",     "PCR": "PCR",     "TGO": "TGO",     "TGP": "TGP",     "BILI TOTAL": "BT",     "BILI DIRETA": "BD",     "BILI INDIRETA": "BI"   };    const BLOCKED_NAMES = [     "REFERENCIA",     "VALOR",     "MATERIAL",     "METODO",     "UNIDADE",     "HASH",     "LIBERACAO",     "ENDERECO",     "TEMPO",     "HORA",     "COLETA",     "IDADE",     "NOTA",     "NOVOS",     "POPULACAO",     "SANGUE",     "PACIENTE",     "HOSPITAL",     "SERVICO",     "CLIENTE",     "CNES",     "ADVIA",     "RESULTADO"   ].map((s) => s.toUpperCase());    function normalizeNameKey(name) {     let s = (name || "").toUpperCase();     s = s.normalize("NFD").replace(/[\u0300-\u036f]/g, "");     s = s.replace(/[^A-Z ]+/g, " ");     return s.replace(/\s+/g, " ").trim();   }    function normalizeValue(value) {     const v = (value || "").trim();     // 2.20 -> 2,20 (mas não mexe em 10.910)     if (/^\d{1,3}\.\d{1,2}$/.test(v)) {       return v.replace(".", ",");     }     return v;   }    function formatDateDots(dateValue) {     if (!dateValue) return "";     const parts = dateValue.split("-");     if (parts.length !== 3) return "";     const [y, m, d] = parts;     return `${d}.${m}.${y}`;   }    // dd/mm/aaaa -> dd.mm.aaaa   function brDateToDots(brDate) {     if (!brDate) return "";     const parts = brDate.split("/");     if (parts.length !== 3) return "";     const [d, m, y] = parts;     return `${d}.${m}.${y}`;   }    // Tenta extrair “14/11/2025” de “Hora de coleta aproximada (14/11/2025 00:12)”   function extractDateFromText(text) {     if (!text) return "";     const m1 = text.match(       /Hora de coleta aproximada\s*\((\d{2}\/\d{2}\/\d{4})\s+\d{2}:\d{2}\)/i     );     if (m1 && m1[1]) return m1[1];      // fallback: primeira data dd/mm/aaaa que aparecer     const m2 = text.match(/(\d{2}\/\d{2}\/\d{4})/);     if (m2 && m2[1]) return m2[1];      return "";   }    // ============================   // PARSE PRINCIPAL   // ============================   function parseExamsFromText(rawText) {     const text = (rawText || "").replace(/\s+/g, " ");     const usedKeys = new Set();     const parts = [];      function addExam(labelKey, displayLabel, regex) {       const match = text.match(regex);       if (match && match[1]) {         const key = normalizeNameKey(labelKey);         if (usedKeys.has(key)) return;         usedKeys.add(key);         const val = normalizeValue(match[1]);         parts.push(`${displayLabel} ${val}`);       }     }      // Padrão genérico Prevent: NOME ... Resultado: 37 mg/dL     // ou tabelão: NOME 37 ---- ---- ...     addExam("UREIA", "UREIA", /\bUREIA\b[^0-9]{0,40}([-+]?\d+[.,]?\d*)/i);     addExam("CREATININA", "CR", /\bCREATININA\b[^0-9]{0,40}([-+]?\d+[.,]?\d*)/i);     addExam("SODIO", "NA", /\bS[ÓO]DIO\b[^0-9]{0,40}([-+]?\d+[.,]?\d*)/i);     addExam("POTASSIO", "K", /\bPOT[ÁA]SSIO\b[^0-9]{0,40}([-+]?\d+[.,]?\d*)/i);     addExam("PCR", "PCR", /\bPCR\b[^0-9]{0,40}([-+]?\d+[.,]?\d*)/i);     addExam("TGO", "TGO", /\bTGO\b[^0-9]{0,40}([-+]?\d+[.,]?\d*)/i);     addExam("TGP", "TGP", /\bTGP\b[^0-9]{0,40}([-+]?\d+[.,]?\d*)/i);     addExam(       "BILI TOTAL",       "BT",       /\bBILI TOTAL\b[^0-9]{0,40}([-+]?\d+[.,]?\d*)/i     );     addExam(       "BILI DIRETA",       "BD",       /\bBILI DIRETA\b[^0-9]{0,40}([-+]?\d+[.,]?\d*)/i     );     addExam(       "BILI INDIRETA",       "BI",       /\bBILI INDIRETA\b[^0-9]{0,40}([-+]?\d+[.,]?\d*)/i     );      // Fallback: QUALQUER exame do tipo "NOME 123,4 mg/dL"     const fallbackRegex =       /([A-ZÁÂÃÉÊÍÓÔÕÚÇa-záâãéêíóôõúç]{3,40})\s+([-+]?\d+[.,]?\d*)\s+(mg\/dL|g\/dL|mEq\/L|U\/L|mmol\/L|%|ng\/mL|µg\/mL|mL\/min[^ ]*|UI\/L)/g;      let m;     while ((m = fallbackRegex.exec(text)) !== null) {       const rawName = m[1].trim();       const value = normalizeValue(m[2]);       const unit = m[3] || "";       const key = normalizeNameKey(rawName);        if (!key) continue;       if (usedKeys.has(key)) continue;       if (BLOCKED_NAMES.includes(key)) continue;        usedKeys.add(key);        const knownAbbrev =         KNOWN_EXAMS[key] || KNOWN_EXAMS[rawName.toUpperCase()] || rawName;        const label = knownAbbrev;       const valueWithUnit = unit ? `${value} ${unit}` : value;       parts.push(`${label} ${valueWithUnit}`);     }      return parts;   }    // ============================   // GERA LINHA FINAL   // ============================   function generateLine() {     const rawText = document.getElementById("inputText").value || "";     const dateValue = document.getElementById("examDate").value;      if (!rawText.trim()) {       alert("Suba um PDF ou cole o texto do laudo da Prevent antes.");       return;     }      let dateDots = "";      if (dateValue) {       // usuário escolheu manualmente       dateDots = formatDateDots(dateValue);     } else {       // tentar descobrir do PDF       const brDate = extractDateFromText(rawText);       if (brDate) {         dateDots = brDateToDots(brDate);         // preencher o campo de data para ficar visível         const [d, m, y] = brDate.split("/");         if (d && m && y) {           document.getElementById("examDate").value = `${y}-${m}-${d}`;         }       }     }      const exams = parseExamsFromText(rawText);      if (!exams.length) {       const msg =         (dateDots ? dateDots + ": " : "") +         "[NenHUM EXAME RECONHECIDO NO TEXTO RECEBIDO. VERIFIQUE SE O PDF TEM TEXTO OU SE O MODELO DO LAUDO É DIFERENTE.]";       document.getElementById("outputText").value = msg.toUpperCase();       return;     }      const line =       (dateDots ? dateDots + ": " : "") + exams.join(" / ");      // tudo em CAIXA ALTA, como você pediu     document.getElementById("outputText").value = line.toUpperCase();   }    // ============================   // LEITURA DO ARQUIVO   // ============================   function handleFileInput(event) {     const file = event.target.files && event.target.files[0];     if (!file) return;      const name = file.name.toLowerCase();     const ext = name.split(".").pop();      if (ext === "txt") {       const reader = new FileReader();       reader.onload = (e) => {         const text = e.target.result || "";         document.getElementById("inputText").value = text;       };       reader.readAsText(file, "utf-8");       return;     }      if (ext === "pdf") {       if (!window["pdfjsLib"]) {         alert(           "PDF.js não foi carregado corretamente. Verifique a conexão com a internet."         );         return;       }        const reader = new FileReader();       reader.onload = function (e) {         const typedArray = new Uint8Array(e.target.result);         const input = document.getElementById("inputText");         input.value = "Lendo PDF, aguarde...";          pdfjsLib           .getDocument({ data: typedArray })           .promise.then(function (pdf) {             const maxPages = pdf.numPages;             const pagePromises = [];             let allText = "";              for (let i = 1; i <= maxPages; i++) {               pagePromises.push(                 pdf.getPage(i).then(function (page) {                   return page.getTextContent().then(function (textContent) {                     const pageText = textContent.items                       .map((item) => item.str)                       .join(" ");                     allText += "
" + pageText;                   });                 })               );             }              return Promise.all(pagePromises).then(function () {               input.value =                 allText.trim() ||                 "[NÃO FOI POSSÍVEL EXTRAIR TEXTO DO PDF (PODE SER SÓ IMAGEM ESCANEADA).]";             });           })           .catch(function (err) {             console.error(err);             alert("Erro ao ler o PDF: " + err.message);             document.getElementById("inputText").value = "";           });       };       reader.readAsArrayBuffer(file);       return;     }      alert("Formato não suportado. Use PDF ou TXT, ou cole o texto manualmente.");   }    // ============================   // UI   // ============================   function clearAll() {     document.getElementById("examDate").value = "";     document.getElementById("fileInput").value = "";     document.getElementById("inputText").value = "";     document.getElementById("outputText").value = "";   }    function copyOutput() {     const text = document.getElementById("outputText").value || "";     if (!text.trim()) {       alert("Não há nada para copiar.");       return;     }     navigator.clipboard       .writeText(text)       .then(() => alert("Linha copiada para a área de transferência."))       .catch(() =>         alert("Não foi possível copiar automaticamente. Selecione e copie manualmente.")       );   }    // ============================   // EVENTOS   // ============================   document     .getElementById("fileInput")     .addEventListener("change", handleFileInput);   document     .getElementById("btnGenerate")     .addEventListener("click", generateLine);   document     .getElementById("btnClearAll")     .addEventListener("click", clearAll);   document     .getElementById("btnCopy")     .addEventListener("click", copyOutput); </script> </body> </html>
    if (window["pdfjsLib"]) {
      pdfjsLib.GlobalWorkerOptions.workerSrc =
        "https://cdnjs.cloudflare.com/ajax/libs/pdf.js/2.6.347/pdf.worker.min.js";
    }
  </script>
