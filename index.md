# 🧠 Classifica dei Modelli Vision

Questa pagina mostra una classifica aggiornata dei modelli di visione artificiale basata sul punteggio **AUROC** (Area Under ROC Curve).  
Puoi cliccare sulle intestazioni della tabella per ordinarla dinamicamente.

[Pagina2](./v2.html)

<style>
  table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 1.5em;
    font-size: 16px;
  }

  th, td {
    border: 1px solid #e0e0e0;
    padding: 12px;
    text-align: left;
    cursor: default;
  }

  th.sortable:hover {
    background-color: #e0f7fa;
    cursor: pointer;
  }

  th.sorted-asc::after {
    content: " ▲";
  }

  th.sorted-desc::after {
    content: " ▼";
  }

  th {
    background-color: #f0f8ff;
    color: #333;
  }

  tr:nth-child(even) {
    background-color: #fafafa;
  }

  tr:hover {
    background-color: #f1f1f1;
  }

  caption {
    caption-side: top;
    font-weight: bold;
    font-size: 18px;
    margin-bottom: 0.5em;
  }
</style>

<table id="modelTable">
  <caption>📊 Classifica AUROC - Modelli Vision</caption>
  <thead>
    <tr>
      <th class="sortable">Posizione</th>
      <th class="sortable">Nome Modello</th>
      <th class="sortable">AUROC</th>
      <th class="sortable">Organizzazione</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>ViT-L/14 DINOv2</td>
      <td>94.24</td>
      <td>Meta AI</td>
    </tr>
    <tr>
      <td>2</td>
      <td>ViT-L/14 CLIP</td>
      <td>92.04</td>
      <td>OpenAI</td>
    </tr>
    <tr>
      <td>3</td>
      <td>ResNet-50 CLIP</td>
      <td>81.77</td>
      <td>OpenAI</td>
    </tr>
  </tbody>
</table>

<script>
  // Funzione per ordinare la tabella
  document.querySelectorAll("th.sortable").forEach(function(header, columnIndex) {
    header.addEventListener("click", function () {
      const table = header.closest("table");
      const tbody = table.querySelector("tbody");
      const rows = Array.from(tbody.querySelectorAll("tr"));
      const isNumeric = columnIndex === 0 || columnIndex === 2;

      const currentSort = header.classList.contains("sorted-asc") ? "asc" :
                          header.classList.contains("sorted-desc") ? "desc" : null;

      document.querySelectorAll("th").forEach(th => th.classList.remove("sorted-asc", "sorted-desc"));

      const newSort = currentSort === "asc" ? "desc" : "asc";
      header.classList.add("sorted-" + newSort);

      rows.sort((a, b) => {
        const cellA = a.children[columnIndex].innerText;
        const cellB = b.children[columnIndex].innerText;

        if (isNumeric) {
          return newSort === "asc"
            ? parseFloat(cellA) - parseFloat(cellB)
            : parseFloat(cellB) - parseFloat(cellA);
        } else {
          return newSort === "asc"
            ? cellA.localeCompare(cellB)
            : cellB.localeCompare(cellA);
        }
      });

      rows.forEach(row => tbody.appendChild(row));
    });
  });
</script>
