# 🧠 Classifica dei Modelli Vision

Questa pagina mostra una classifica aggiornata dei modelli di visione artificiale basata sul punteggio **AUROC** (Area Under ROC Curve).  
I dati sono presentati in formato tabellare, con uno stile migliorato per una migliore leggibilità.

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

<table>
  <caption>📊 Classifica AUROC - Modelli Vision</caption>
  <thead>
    <tr>
      <th>Posizione</th>
      <th>Nome Modello</th>
      <th>AUROC</th>
      <th>Organizzazione</th>
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
