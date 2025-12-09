# iago-teste01
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <title>Orçamento de Obras - IURD</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <style>
    * {
      box-sizing: border-box;
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    }

    body {
      margin: 0;
      padding: 0;
      background: #f4f4f6;
      color: #222;
    }

    header {
      background: #1f2933;
      color: #fff;
      padding: 16px 24px;
    }

    header h1 {
      margin: 0;
      font-size: 20px;
    }

    header p {
      margin: 4px 0 0;
      font-size: 13px;
      opacity: 0.8;
    }

    main {
      max-width: 1200px;
      margin: 24px auto;
      padding: 0 16px 32px;
    }

    .grid {
      display: grid;
      grid-template-columns: 1.1fr 1.4fr;
      gap: 16px;
    }

    @media (max-width: 900px) {
      .grid {
        grid-template-columns: 1fr;
      }
    }

    .card {
      background: #fff;
      border-radius: 10px;
      padding: 16px 18px 18px;
      box-shadow: 0 8px 20px rgba(15, 23, 42, 0.04);
    }

    .card h2 {
      margin: 0 0 10px;
      font-size: 18px;
    }

    .card small {
      display: block;
      margin-bottom: 12px;
      color: #6b7280;
      font-size: 12px;
    }

    .form-row {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 8px;
    }

    .form-row-3 {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 8px;
    }

    .form-group {
      margin-bottom: 8px;
    }

    label {
      display: block;
      font-size: 12px;
      margin-bottom: 3px;
      color: #374151;
    }

    input[type="text"],
    input[type="number"],
    select {
      width: 100%;
      padding: 6px 8px;
      border-radius: 6px;
      border: 1px solid #d1d5db;
      font-size: 13px;
      background: #f9fafb;
    }

    input:focus,
    select:focus {
      outline: none;
      border-color: #2563eb;
      background: #fff;
      box-shadow: 0 0 0 1px rgba(37, 99, 235, 0.1);
    }

    button {
      border-radius: 999px;
      border: none;
      padding: 8px 14px;
      font-size: 13px;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      gap: 6px;
    }

    .btn-primary {
      background: #2563eb;
      color: #fff;
    }

    .btn-secondary {
      background: #e5e7eb;
      color: #111827;
    }

    .btn-danger {
      background: #ef4444;
      color: #fff;
    }

    .btn-sm {
      padding: 4px 8px;
      font-size: 11px;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      font-size: 12px;
    }

    thead {
      background: #f3f4f6;
    }

    th, td {
      padding: 6px 8px;
      border-bottom: 1px solid #e5e7eb;
      text-align: left;
      vertical-align: middle;
    }

    th {
      font-weight: 600;
      color: #374151;
      white-space: nowrap;
    }

    tbody tr:hover {
      background: #f9fafb;
    }

    .tag {
      display: inline-flex;
      padding: 2px 8px;
      border-radius: 999px;
      font-size: 10px;
      background: #e5e7eb;
      color: #111827;
    }

    .summary {
      margin-top: 12px;
      padding-top: 10px;
      border-top: 1px dashed #d1d5db;
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      font-size: 13px;
    }

    .summary span {
      display: inline-flex;
      align-items: baseline;
      gap: 4px;
    }

    .summary .label {
      color: #6b7280;
      font-size: 12px;
    }

    .summary .value {
      font-weight: 600;
      color: #111827;
    }

    .pill {
      border-radius: 999px;
      padding: 3px 9px;
      font-size: 11px;
      background: #1f2937;
      color: #fff;
      display: inline-flex;
      gap: 6px;
      align-items: center;
    }
  </style>
</head>
<body>
  <header>
    <h1>Orçamento de Obras – IURD</h1>
    <p>Ferramenta simples para montar custos de serviços (Material + Mão de Obra).</p>
  </header>

  <main>
    <div class="grid">
      <!-- CADASTRO DE SERVIÇOS -->
      <section class="card" id="cadastro-servicos">
        <h2>Cadastro de serviços</h2>
        <small>Preencha os dados do serviço e clique em “Salvar serviço”. Eles ficarão gravados no navegador.</small>

        <div class="form-group">
          <label for="descricao-servico">Descrição do serviço</label>
          <input type="text" id="descricao-servico" placeholder="Ex.: Execução de contrapiso, revestimento piso..." />
        </div>

        <div class="form-row">
          <div class="form-group">
            <label for="unidade-servico">Unidade</label>
            <input type="text" id="unidade-servico" placeholder="m², m, un, h..." />
          </div>
          <div class="form-group">
            <label for="grupo-servico">Grupo</label>
            <input type="text" id="grupo-servico" placeholder="Ex.: REVESTIMENTO PISO" />
          </div>
        </div>

        <div class="form-row">
          <div class="form-group">
            <label for="custo-mat">Custo unitário material (R$)</label>
            <input type="number" id="custo-mat" step="0.01" min="0" />
          </div>
          <div class="form-group">
            <label for="custo-mo">Custo unitário mão de obra (R$)</label>
            <input type="number" id="custo-mo" step="0.01" min="0" />
          </div>
        </div>

        <button class="btn-primary" id="btn-salvar-servico">💾 Salvar serviço</button>

        <hr style="margin: 16px 0; border: none; border-top: 1px solid #e5e7eb;" />

        <h3 style="font-size: 14px; margin: 0 0 8px;">Serviços cadastrados</h3>
        <small>Selecione um serviço na outra aba para montar o orçamento.</small>

        <div style="max-height: 230px; overflow: auto; margin-top: 8px;">
          <table id="tabela-servicos">
            <thead>
              <tr>
                <th>Serviço</th>
                <th>Un.</th>
                <th>Grupo</th>
                <th>R$ Mat</th>
                <th>R$ M.O.</th>
                <th></th>
              </tr>
            </thead>
            <tbody>
              <!-- linhas geradas via JS -->
            </tbody>
          </table>
        </div>
      </section>

      <!-- ORÇAMENTO -->
      <section class="card" id="orcamento">
        <div style="display:flex; justify-content:space-between; align-items:center; gap:4px;">
          <div>
            <h2>Orçamento da obra</h2>
            <small>Monte o orçamento selecionando um serviço cadastrado e a quantidade.</small>
          </div>
          <span class="pill">
            💰 Orçamento
            <span id="total-geral-pill">R$ 0,00</span>
          </span>
        </div>

        <div class="form-row-3" style="margin-top: 10px;">
          <div class="form-group">
            <label for="select-servico">Serviço</label>
            <select id="select-servico">
              <!-- opções via JS -->
            </select>
          </div>
          <div class="form-group">
            <label for="quantidade-servico">Quantidade</label>
            <input type="number" id="quantidade-servico" step="0.01" min="0" />
          </div>
          <div class="form-group" style="display:flex; align-items:flex-end; justify-content:flex-end;">
            <button class="btn-primary" id="btn-add-item">➕ Adicionar ao orçamento</button>
          </div>
        </div>

        <div style="max-height: 260px; overflow:auto; margin-top: 10px;">
          <table id="tabela-orcamento">
            <thead>
              <tr>
                <th>Serviço</th>
                <th>Qtd</th>
                <th>Un.</th>
                <th>R$ Mat</th>
                <th>R$ M.O.</th>
                <th>R$ Total</th>
                <th></th>
              </tr>
            </thead>
            <tbody>
              <!-- itens via JS -->
            </tbody>
          </table>
        </div>

        <div class="summary">
          <span>
            <span class="label">Total Material:</span>
            <span class="value" id="total-material">R$ 0,00</span>
          </span>
          <span>
            <span class="label">Total Mão de Obra:</span>
            <span class="value" id="total-mo">R$ 0,00</span>
          </span>
          <span>
            <span class="label">Total Geral:</span>
            <span class="value" id="total-geral">R$ 0,00</span>
          </span>
        </div>

        <div style="margin-top:10px; display:flex; gap:8px; flex-wrap:wrap;">
          <button class="btn-secondary btn-sm" id="btn-limpar-orcamento">🧹 Limpar orçamento</button>
          <button class="btn-secondary btn-sm" id="btn-limpar-tudo">🗑️ Limpar tudo (serviços + orçamento)</button>
        </div>
      </section>
    </div>
  </main>

  <script>
    // -----------------------------
    // UTIL
    // -----------------------------
    function formatMoney(value) {
      return value.toLocaleString("pt-BR", {
        style: "currency",
        currency: "BRL"
      });
    }

    // -----------------------------
    // ESTADO
    // -----------------------------
    let servicos = [];
    let itensOrcamento = [];

    const STORAGE_SERVICOS = "iurd_servicos";
    const STORAGE_ORCAMENTO = "iurd_orcamento";

    function carregarStorage() {
      const s = localStorage.getItem(STORAGE_SERVICOS);
      const o = localStorage.getItem(STORAGE_ORCAMENTO);
      servicos = s ? JSON.parse(s) : [];
      itensOrcamento = o ? JSON.parse(o) : [];
    }

    function salvarStorage() {
      localStorage.setItem(STORAGE_SERVICOS, JSON.stringify(servicos));
      localStorage.setItem(STORAGE_ORCAMENTO, JSON.stringify(itensOrcamento));
    }

    // -----------------------------
    // DOM ELEMENTS
    // -----------------------------
    const tabelaServicosBody = document.querySelector("#tabela-servicos tbody");
    const tabelaOrcamentoBody = document.querySelector("#tabela-orcamento tbody");
    const selectServico = document.getElementById("select-servico");

    const totalMatSpan = document.getElementById("total-material");
    const totalMoSpan = document.getElementById("total-mo");
    const totalGeralSpan = document.getElementById("total-geral");
    const totalGeralPill = document.getElementById("total-geral-pill");

    // -----------------------------
    // RENDERIZAÇÃO
    // -----------------------------
    function renderServicos() {
      tabelaServicosBody.innerHTML = "";
      selectServico.innerHTML = "";

      if (servicos.length === 0) {
        tabelaServicosBody.innerHTML = '<tr><td colspan="6">Nenhum serviço cadastrado.</td></tr>';
        const opt = document.createElement("option");
        opt.value = "";
        opt.textContent = "Cadastre um serviço primeiro";
        selectServico.appendChild(opt);
        selectServico.disabled = true;
        return;
      }

      selectServico.disabled = false;

      servicos.forEach((s, index) => {
        // tabela
        const tr = document.createElement("tr");

        const tdDesc = document.createElement("td");
        tdDesc.textContent = s.descricao;
        tr.appendChild(tdDesc);

        const tdUn = document.createElement("td");
        tdUn.textContent = s.unidade || "-";
        tr.appendChild(tdUn);

        const tdGrupo = document.createElement("td");
        const tag = document.createElement("span");
        tag.className = "tag";
        tag.textContent = s.grupo || "Sem grupo";
        tdGrupo.appendChild(tag);
        tr.appendChild(tdGrupo);

        const tdMat = document.createElement("td");
        tdMat.textContent = formatMoney(s.custoMat || 0);
        tr.appendChild(tdMat);

        const tdMo = document.createElement("td");
        tdMo.textContent = formatMoney(s.custoMo || 0);
        tr.appendChild(tdMo);

        const tdAcoes = document.createElement("td");
        const btnDel = document.createElement("button");
        btnDel.className = "btn-danger btn-sm";
        btnDel.textContent = "Excluir";
        btnDel.onclick = () => {
          if (confirm("Remover este serviço?")) {
            servicos.splice(index, 1);
            salvarStorage();
            renderServicos();
            renderSelectServicos();
          }
        };
        tdAcoes.appendChild(btnDel);
        tr.appendChild(tdAcoes);

        tabelaServicosBody.appendChild(tr);

        // select
        const opt = document.createElement("option");
        opt.value = index;
        opt.textContent =
          s.descricao.substring(0, 50) +
          " | " +
          (s.unidade || "") +
          " | " +
          formatMoney((s.custoMat || 0) + (s.custoMo || 0));
        selectServico.appendChild(opt);
      });
    }

    function renderSelectServicos() {
      // reaproveitado em renderServicos, deixei função separada caso precise depois
      renderServicos();
    }

    function renderOrcamento() {
      tabelaOrcamentoBody.innerHTML = "";

      if (itensOrcamento.length === 0) {
        tabelaOrcamentoBody.innerHTML = '<tr><td colspan="7">Nenhum item no orçamento.</td></tr>';
      } else {
        itensOrcamento.forEach((item, index) => {
          const tr = document.createElement("tr");

          const tdDesc = document.createElement("td");
          tdDesc.textContent = item.descricao;
          tr.appendChild(tdDesc);

          const tdQtd = document.createElement("td");
          tdQtd.textContent = item.quantidade;
          tr.appendChild(tdQtd);

          const tdUn = document.createElement("td");
          tdUn.textContent = item.unidade || "-";
          tr.appendChild(tdUn);

          const tdMat = document.createElement("td");
          tdMat.textContent = formatMoney(item.totalMat);
          tr.appendChild(tdMat);

          const tdMo = document.createElement("td");
          tdMo.textContent = formatMoney(item.totalMo);
          tr.appendChild(tdMo);

          const tdTotal = document.createElement("td");
          tdTotal.textContent = formatMoney(item.totalGeral);
          tr.appendChild(tdTotal);

          const tdAcoes = document.createElement("td");
          const btnDel = document.createElement("button");
          btnDel.className = "btn-danger btn-sm";
          btnDel.textContent = "Remover";
          btnDel.onclick = () => {
            itensOrcamento.splice(index, 1);
            salvarStorage();
            renderOrcamento();
          };
          tdAcoes.appendChild(btnDel);
          tr.appendChild(tdAcoes);

          tabelaOrcamentoBody.appendChild(tr);
        });
      }

      // Totais
      const totals = itensOrcamento.reduce(
        (acc, item) => {
          acc.mat += item.totalMat;
          acc.mo += item.totalMo;
          acc.geral += item.totalGeral;
          return acc;
        },
        { mat: 0, mo: 0, geral: 0 }
      );

      totalMatSpan.textContent = formatMoney(totals.mat);
      totalMoSpan.textContent = formatMoney(totals.mo);
      totalGeralSpan.textContent = formatMoney(totals.geral);
      totalGeralPill.textContent = formatMoney(totals.geral);
    }

    // -----------------------------
    // EVENTOS
    // -----------------------------
    document.getElementById("btn-salvar-servico").addEventListener("click", () => {
      const descricao = document.getElementById("descricao-servico").value.trim();
      const unidade = document.getElementById("unidade-servico").value.trim();
      const grupo = document.getElementById("grupo-servico").value.trim();
      const custoMat = parseFloat(document.getElementById("custo-mat").value.replace(",", ".")) || 0;
      const custoMo = parseFloat(document.getElementById("custo-mo").value.replace(",", ".")) || 0;

      if (!descricao) {
        alert("Informe a descrição do serviço.");
        return;
      }

      const servico = {
        id: Date.now(),
        descricao,
        unidade,
        grupo,
        custoMat,
        custoMo
      };

      servicos.push(servico);
      salvarStorage();
      renderServicos();

      // limpa campos principais
      document.getElementById("descricao-servico").value = "";
      document.getElementById("custo-mat").value = "";
      document.getElementById("custo-mo").value = "";
    });

    document.getElementById("btn-add-item").addEventListener("click", () => {
      if (servicos.length === 0) {
        alert("Cadastre pelo menos um serviço antes de montar o orçamento.");
        return;
      }

      const index = parseInt(selectServico.value, 10);
      if (isNaN(index) || index < 0 || index >= servicos.length) {
        alert("Selecione um serviço válido.");
        return;
      }

      const quantidade = parseFloat(
        document.getElementById("quantidade-servico").value.replace(",", ".")
      );
      if (isNaN(quantidade) || quantidade <= 0) {
        alert("Informe uma quantidade válida.");
        return;
      }

      const serv = servicos[index];

      const totalMat = (serv.custoMat || 0) * quantidade;
      const totalMo = (serv.custoMo || 0) * quantidade;
      const totalGeral = totalMat + totalMo;

      itensOrcamento.push({
        servicoId: serv.id,
        descricao: serv.descricao,
        unidade: serv.unidade,
        quantidade,
        totalMat,
        totalMo,
        totalGeral
      });

      salvarStorage();
      renderOrcamento();

      document.getElementById("quantidade-servico").value = "";
    });

    document.getElementById("btn-limpar-orcamento").addEventListener("click", () => {
      if (!confirm("Tem certeza que deseja limpar TODO o orçamento?")) return;
      itensOrcamento = [];
      salvarStorage();
      renderOrcamento();
    });

    document.getElementById("btn-limpar-tudo").addEventListener("click", () => {
      if (!confirm("Isso vai apagar serviços cadastrados e o orçamento. Continuar?")) return;
      servicos = [];
      itensOrcamento = [];
      salvarStorage();
      renderServicos();
      renderOrcamento();
    });

    // -----------------------------
    // INICIALIZAÇÃO
    // -----------------------------
    carregarStorage();
    renderServicos();
    renderOrcamento();
  </script>
</body>
</html>
