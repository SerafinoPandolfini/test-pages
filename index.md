<!DOCTYPE html>
<html lang="it">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Leaderboard Deep Learning - Classificazione Binaria</title>

<style>
  body {
    font-family: Arial, sans-serif;
    margin: 40px;
    background-color: #fafafa;
    color: #222;
  }

  h1 {
    font-size: 2em;
    margin-bottom: 0.2em;
  }

  h2 {
    font-size: 1.2em;
    margin-top: 0;
    color: #444;
  }

  a {
    color: #0056b3;
    text-decoration: none;
  }
  a:hover {
    text-decoration: underline;
  }

  .links {
    margin: 15px 0;
  }

  .abstract {
    background: #fff;
    padding: 15px;
    border-left: 4px solid #007acc;
    box-shadow: 0 1px 3px rgba(0,0,0,0.1);
    margin-bottom: 30px;
  }

  .image-container {
    text-align: center;
    margin: 20px 0;
  }

  img {
    max-width: 80%;
    border-radius: 8px;
    box-shadow: 0 2px 6px rgba(0,0,0,0.15);
  }

  table {
    width: 100%;
    border-collapse: collapse;
    background: white;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  }

  th, td {
    padding: 12px;
    text-align: left;
    border-bottom: 1px solid #ddd;
  }

  th {
    background-color: #007acc;
    color: white;
    cursor: pointer;
  }

  th:hover {
    background-color: #005f99;
  }

  tr:nth-child(even) {
    background-color: #f5f5f5;
  }

  pre {
    background-color: #f0f0f0;
    padding: 15px;
    border-radius: 5px;
    overflow-x: auto;
  }
</style>
</head>

<body>

<h1>Leaderboard dei Modelli di Deep Learning per la Classificazione Binaria</h1>
<h2>Autori: Mario Rossi, Laura Bianchi, e Team AI Lab</h2>

<div class="links">
  🔗 <a href="https://github.com/example-repo" target="_blank">Repository GitHub</a>  
  📄 <a href="https://arxiv.org/abs/0000.00000" target="_blank">Pubblicazione</a>
</div>

<div class="abstract">
  <strong>Abstract:</strong>  
  Questo lavoro presenta una comparativa di modelli di deep learning per la classificazione binaria in un contesto biomedico. 
  Sono stati valutati diversi approcci basati su reti neurali convoluzionali e transformer, analizzando le prestazioni su dataset bilanciati e sbilanciati. 
  I risultati evidenziano l'importanza del tuning dei parametri e della scelta delle architetture nella generalizzazione del modello.
</div>

<div class="image-container">
  <img src="https://via.placeholder.com/800x400.png?text=Immagine+Illustrativa" alt="Immagine illustrativa del modello o dataset">
</div>

<h2>📊 Leaderboard dei Modelli</h2>
<table id="leaderboard">
  <thead>
    <tr>
      <th onclick="sortTable(0)">Nome modello</th>
      <th onclick="sortTable(1)">Autore / Team</th>
      <th onclick="sortTable(2)">Data sottomissione</th>
      <th onclick="sortTable(3)"># Parametri</th>
      <th onclick="sortTable(4)">AUROC</th>
      <th onclick="sortTable(5)">Accuracy</th>
      <th onclick="sortTable(6)">Link al paper / modello</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>BinaryNet v1</td>
      <td>AI Lab</td>
      <td>2025-03-12</td>
      <td>12M</td>
      <td>0.942</td>
      <td>0.905</td>
      <td><a href="https://arxiv.org/abs/1234.5678" target="_blank">Paper</a></td>
    </tr>
    <tr>
      <td>ResNet50 FineTuned</td>
      <td>DeepVision Team</td>
      <td>2025-04-20</td>
      <td>23.5M</td>
      <td>0.956</td>
      <td>0.917</td>
      <td><a href="https://example.com/model2" target="_blank">Pagina modello</a></td>
    </tr>
    <tr>
      <td>Transformer-Binary</td>
      <td>ML Group</td>
      <td>2025-06-05</td>
      <td>45M</td>
      <td>0.971</td>
      <td>0.932</td>
      <td><a href="https://example.com/model3" target="_blank">Paper</a></td>
    </tr>
  </tbody>
</table>

<h2>📚 BibTeX</h2>
<pre>
@article{rossi2025binarydl,
  title={Deep Learning Approaches for Binary Classification in Biomedical Data},
  author={Rossi, Mario and Bianchi, Laura and AI Lab Team},
  journal={Journal of Artificial Intelligence Research},
  year={2025},
  volume={58},
  pages={123-145},
  doi={10.1234/jairesearch.2025.58.123}
}
</pre>

<script>
function sortTable(n) {
  var table, rows, switching, i, x, y, shouldSwitch, dir, switchcount = 0;
  table = document.getElementById("leaderboard");
  switching = true;
  dir = "asc"; 
  while (switching) {
    switching = false;
    rows = table.rows;
    for (i = 1; i < (rows.length - 1); i++) {
      shouldSwitch = false;
      x = rows[i].getElementsByTagName("TD")[n];
      y = rows[i + 1].getElementsByTagName("TD")[n];
      if (dir === "asc") {
        if (x.innerHTML.toLowerCase() > y.innerHTML.toLowerCase()) {
          shouldSwitch = true;
          break;
        }
      } else if (dir === "desc") {
        if (x.innerHTML.toLowerCase() < y.innerHTML.toLowerCase()) {
          shouldSwitch = true;
          break;
        }
      }
    }
    if (shouldSwitch) {
      rows[i].parentNode.insertBefore(rows[i + 1], rows[i]);
      switching = true;
      switchcount++;      
    } else {
      if (switchcount === 0 && dir === "asc") {
        dir = "desc";
        switching = true;
      }
    }
  }
}
</script>

</body>
</html>
