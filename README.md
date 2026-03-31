<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Evaluación de Criterios — Oliveto</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --olive: #2D4A1E;
    --olive-mid: #3D6B2A;
    --olive-light: #5A8C42;
    --gold: #C8922A;
    --gold-light: #E8B84B;
    --cream: #F7F3EC;
    --cream-dark: #EDE7DA;
    --warm-gray: #8C8070;
    --text-dark: #1A1612;
    --text-mid: #4A3F35;
    --text-soft: #7A6E64;
    --red-vital: #B83232;
    --red-light: #FBEAEA;
    --amber: #C87820;
    --amber-light: #FDF3E3;
    --green-ok: #2D6B3A;
    --green-light: #EBF5ED;
    --gray-neutral: #6A6460;
    --gray-light: #F0ECE8;
    --border: rgba(45,74,30,0.12);
    --shadow: 0 2px 16px rgba(45,74,30,0.08);
  }
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--cream);
    color: var(--text-dark);
    line-height: 1.6;
    min-height: 100vh;
  }

  /* HEADER */
  .header {
    background: var(--olive);
    padding: 0;
    position: relative;
    overflow: hidden;
  }
  .header-inner {
    max-width: 900px;
    margin: 0 auto;
    padding: 48px 32px 40px;
    position: relative;
    z-index: 1;
  }
  .header-tag {
    display: inline-block;
    font-size: 10px;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--gold-light);
    font-weight: 500;
    border: 1px solid rgba(200,162,42,0.4);
    padding: 4px 10px;
    border-radius: 2px;
    margin-bottom: 18px;
  }
  .header h1 {
    font-family: 'Playfair Display', serif;
    font-size: 34px;
    font-weight: 600;
    color: #fff;
    line-height: 1.2;
    margin-bottom: 10px;
  }
  .header h1 span { color: var(--gold-light); }
  .header-sub {
    font-size: 14px;
    color: rgba(255,255,255,0.6);
    font-weight: 300;
    max-width: 520px;
  }
  .header-deco {
    position: absolute;
    right: -40px;
    top: -40px;
    width: 260px;
    height: 260px;
    border-radius: 50%;
    background: rgba(200,162,42,0.06);
    z-index: 0;
  }
  .header-deco2 {
    position: absolute;
    right: 60px;
    bottom: -60px;
    width: 160px;
    height: 160px;
    border-radius: 50%;
    background: rgba(200,162,42,0.04);
    z-index: 0;
  }

  /* SUMMARY BAR */
  .summary-bar {
    background: var(--olive);
    border-top: 1px solid rgba(255,255,255,0.08);
  }
  .summary-inner {
    max-width: 900px;
    margin: 0 auto;
    padding: 0 32px 28px;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 12px;
  }
  .summary-card {
    background: rgba(255,255,255,0.07);
    border-radius: 8px;
    padding: 14px 16px;
    text-align: center;
    border: 1px solid rgba(255,255,255,0.08);
  }
  .summary-card .num {
    font-family: 'Playfair Display', serif;
    font-size: 26px;
    font-weight: 600;
    color: #fff;
  }
  .summary-card .num.red { color: #F28B82; }
  .summary-card .num.amber { color: var(--gold-light); }
  .summary-card .num.green { color: #81C784; }
  .summary-card .lbl {
    font-size: 11px;
    color: rgba(255,255,255,0.45);
    text-transform: uppercase;
    letter-spacing: 0.06em;
    margin-top: 2px;
  }

  /* INSTRUCTIONS */
  .instructions-wrap {
    max-width: 900px;
    margin: 32px auto 0;
    padding: 0 32px;
  }
  .instructions {
    background: #fff;
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 16px 20px;
    font-size: 13px;
    color: var(--text-soft);
    line-height: 1.65;
    display: flex;
    gap: 14px;
    align-items: flex-start;
  }
  .instructions-icon {
    width: 32px;
    height: 32px;
    border-radius: 50%;
    background: var(--cream-dark);
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
    font-size: 16px;
    margin-top: 1px;
  }

  /* MAIN CONTENT */
  .content {
    max-width: 900px;
    margin: 28px auto 0;
    padding: 0 32px 64px;
  }

  /* CATEGORY */
  .category-block { margin-bottom: 40px; }
  .category-header {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 16px;
  }
  .category-num {
    width: 28px;
    height: 28px;
    border-radius: 50%;
    background: var(--olive);
    color: #fff;
    font-size: 12px;
    font-weight: 500;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
  }
  .category-title {
    font-family: 'Playfair Display', serif;
    font-size: 17px;
    font-weight: 600;
    color: var(--olive);
    letter-spacing: 0.01em;
  }
  .category-line {
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ITEM CARD */
  .item-card {
    background: #fff;
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px 22px;
    margin-bottom: 12px;
    transition: box-shadow 0.2s, border-color 0.2s;
    position: relative;
  }
  .item-card:hover { box-shadow: var(--shadow); }
  .item-card.scored-5 { border-left: 3.5px solid var(--red-vital); }
  .item-card.scored-4 { border-left: 3.5px solid var(--amber); }
  .item-card.scored-3 { border-left: 3.5px solid var(--gold); }
  .item-card.scored-2 { border-left: 3.5px solid var(--gray-neutral); }
  .item-card.scored-1 { border-left: 3.5px solid var(--green-ok); }

  .item-top {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    gap: 16px;
    margin-bottom: 14px;
  }
  .item-left { flex: 1; }
  .item-name {
    font-size: 14px;
    font-weight: 500;
    color: var(--text-dark);
    line-height: 1.4;
    margin-bottom: 4px;
  }
  .item-badge {
    display: inline-block;
    font-size: 10px;
    padding: 2px 8px;
    border-radius: 20px;
    font-weight: 500;
    letter-spacing: 0.04em;
    opacity: 0;
    transition: opacity 0.2s;
  }
  .item-badge.visible { opacity: 1; }
  .badge-5 { background: var(--red-light); color: var(--red-vital); }
  .badge-4 { background: var(--amber-light); color: var(--amber); }
  .badge-3 { background: #FFF8E8; color: var(--gold); }
  .badge-2 { background: var(--gray-light); color: var(--gray-neutral); }
  .badge-1 { background: var(--green-light); color: var(--green-ok); }

  /* DOTS */
  .dots-wrap {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    gap: 6px;
    flex-shrink: 0;
  }
  .dots-label {
    display: flex;
    justify-content: space-between;
    width: 160px;
    font-size: 10px;
    color: var(--text-soft);
    opacity: 0.6;
  }
  .dots-row {
    display: flex;
    gap: 7px;
  }
  .dot {
    width: 30px;
    height: 30px;
    border-radius: 50%;
    border: 1.5px solid rgba(45,74,30,0.2);
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 12px;
    font-weight: 500;
    color: var(--text-soft);
    transition: all 0.15s;
    user-select: none;
    background: transparent;
  }
  .dot:hover { border-color: var(--olive-mid); color: var(--olive); background: var(--cream); }
  .dot.active-1, .dot.active-2 { background: var(--green-light); color: var(--green-ok); border-color: var(--green-ok); }
  .dot.active-3 { background: #FFF8E8; color: var(--gold); border-color: var(--gold); }
  .dot.active-4 { background: var(--amber-light); color: var(--amber); border-color: var(--amber); }
  .dot.active-5 { background: var(--red-light); color: var(--red-vital); border-color: var(--red-vital); }

  /* REASON BOX */
  .reason-box {
    font-size: 12.5px;
    color: var(--text-soft);
    line-height: 1.65;
    background: var(--cream);
    border-radius: 7px;
    padding: 11px 14px;
    margin-bottom: 12px;
    border-left: 2.5px solid var(--cream-dark);
  }
  .reason-label {
    font-size: 10px;
    font-weight: 500;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--warm-gray);
    margin-bottom: 4px;
  }

  /* OBSERVATIONS */
  .obs-label {
    font-size: 10px;
    font-weight: 500;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--warm-gray);
    margin-bottom: 6px;
  }
  .obs-textarea {
    width: 100%;
    border: 1px solid var(--border);
    border-radius: 7px;
    padding: 10px 12px;
    font-family: 'DM Sans', sans-serif;
    font-size: 13px;
    color: var(--text-dark);
    background: #fff;
    resize: vertical;
    min-height: 60px;
    transition: border-color 0.15s;
    line-height: 1.55;
  }
  .obs-textarea:focus {
    outline: none;
    border-color: var(--olive-mid);
    box-shadow: 0 0 0 3px rgba(45,74,30,0.07);
  }
  .obs-textarea::placeholder { color: rgba(122,110,100,0.5); }

  /* PROGRESS BAR */
  .progress-wrap {
    max-width: 900px;
    margin: 20px auto 0;
    padding: 0 32px;
  }
  .progress-bar-outer {
    height: 4px;
    background: var(--cream-dark);
    border-radius: 2px;
    overflow: hidden;
  }
  .progress-bar-inner {
    height: 100%;
    background: var(--olive);
    border-radius: 2px;
    width: 0%;
    transition: width 0.3s ease;
  }
  .progress-label {
    font-size: 11px;
    color: var(--text-soft);
    margin-top: 6px;
    text-align: right;
  }

  /* EXPORT SECTION */
  .export-section {
    max-width: 900px;
    margin: 0 auto;
    padding: 0 32px 64px;
  }
  .export-card {
    background: var(--olive);
    border-radius: 12px;
    padding: 28px 32px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 24px;
  }
  .export-text h3 {
    font-family: 'Playfair Display', serif;
    font-size: 18px;
    color: #fff;
    margin-bottom: 4px;
  }
  .export-text p {
    font-size: 13px;
    color: rgba(255,255,255,0.55);
  }
  .export-btn {
    background: var(--gold);
    color: #fff;
    border: none;
    border-radius: 8px;
    padding: 13px 24px;
    font-family: 'DM Sans', sans-serif;
    font-size: 13px;
    font-weight: 500;
    cursor: pointer;
    transition: background 0.15s;
    white-space: nowrap;
    flex-shrink: 0;
  }
  .export-btn:hover { background: var(--gold-light); }
  .export-btn:active { transform: scale(0.98); }

  /* PRINT / EXPORT MODAL */
  .modal-overlay {
    display: none;
    position: fixed;
    inset: 0;
    background: rgba(26,22,18,0.6);
    z-index: 100;
    align-items: center;
    justify-content: center;
  }
  .modal-overlay.open { display: flex; }
  .modal {
    background: #fff;
    border-radius: 14px;
    padding: 32px;
    max-width: 540px;
    width: 90%;
    max-height: 80vh;
    overflow-y: auto;
  }
  .modal h2 {
    font-family: 'Playfair Display', serif;
    font-size: 20px;
    color: var(--olive);
    margin-bottom: 6px;
  }
  .modal-sub { font-size: 13px; color: var(--text-soft); margin-bottom: 20px; }
  .modal-results { font-size: 13px; line-height: 1.8; color: var(--text-dark); }
  .modal-results .cat-title {
    font-weight: 500;
    color: var(--olive);
    font-size: 12px;
    text-transform: uppercase;
    letter-spacing: 0.06em;
    margin-top: 16px;
    margin-bottom: 6px;
    border-bottom: 1px solid var(--border);
    padding-bottom: 4px;
  }
  .modal-results .result-row {
    display: flex;
    gap: 10px;
    margin-bottom: 4px;
    padding: 5px 8px;
    border-radius: 6px;
    background: var(--cream);
  }
  .modal-results .result-score {
    font-weight: 500;
    min-width: 30px;
    color: var(--olive);
  }
  .modal-results .result-obs {
    font-size: 12px;
    color: var(--text-soft);
    font-style: italic;
    margin-top: 2px;
  }
  .modal-footer { display: flex; gap: 10px; margin-top: 24px; justify-content: flex-end; }
  .btn-close {
    background: var(--cream-dark);
    border: none;
    border-radius: 7px;
    padding: 10px 18px;
    font-family: 'DM Sans', sans-serif;
    font-size: 13px;
    font-weight: 500;
    cursor: pointer;
    color: var(--text-mid);
  }
  .btn-copy {
    background: var(--olive);
    border: none;
    border-radius: 7px;
    padding: 10px 18px;
    font-family: 'DM Sans', sans-serif;
    font-size: 13px;
    font-weight: 500;
    cursor: pointer;
    color: #fff;
  }
  .btn-copy:hover { background: var(--olive-mid); }

  @media (max-width: 600px) {
    .header-inner { padding: 32px 20px 28px; }
    .header h1 { font-size: 26px; }
    .summary-inner { grid-template-columns: repeat(2,1fr); padding: 0 20px 24px; }
    .content { padding: 0 20px 48px; }
    .instructions-wrap, .progress-wrap, .export-section { padding: 0 20px; }
    .item-top { flex-direction: column; gap: 12px; }
    .dots-wrap { align-items: flex-start; }
    .dots-label { width: 100%; }
    .export-card { flex-direction: column; text-align: center; }
  }
</style>
</head>
<body>

<div class="header">
  <div class="header-deco"></div>
  <div class="header-deco2"></div>
  <div class="header-inner">
    <div class="header-tag">Grupo Proyección · Consultandes 2026</div>
    <h1>Evaluación de criterios<br>para <span>nuevos locales</span></h1>
    <p class="header-sub">Herramienta de diagnóstico interno para calificar el grado de importancia de cada criterio en el modelo de negocio y experiencia de Oliveto.</p>
  </div>
  <div class="summary-bar">
    <div class="summary-inner">
      <div class="summary-card">
        <div class="num red" id="cnt5">0</div>
        <div class="lbl">Vitales (5)</div>
      </div>
      <div class="summary-card">
        <div class="num amber" id="cnt4">0</div>
        <div class="lbl">Altos (4)</div>
      </div>
      <div class="summary-card">
        <div class="num green" id="cnt3">0</div>
        <div class="lbl">Medios (3)</div>
      </div>
      <div class="summary-card">
        <div class="num" id="cnt-done" style="color:rgba(255,255,255,0.9);">0/22</div>
        <div class="lbl">Completados</div>
      </div>
    </div>
  </div>
</div>

<div class="progress-wrap">
  <div class="progress-bar-outer">
    <div class="progress-bar-inner" id="progress-bar"></div>
  </div>
  <div class="progress-label" id="progress-label">0 de 22 criterios calificados</div>
</div>

<div class="instructions-wrap" style="margin-top:20px;">
  <div class="instructions">
    <div class="instructions-icon">📋</div>
    <div>
      <strong style="color:var(--text-dark);">Cómo usar esta herramienta</strong><br>
      Para cada criterio, selecciona una calificación del <strong>1 al 5</strong> (5 = vital e innegociable, 1 = deseable pero prescindible). El campo de observaciones es libre: anota contexto, excepciones o comentarios relevantes para Oliveto. Al finalizar, exporta el resumen completo.
    </div>
  </div>
</div>

<div class="content" id="content-area"></div>

<div class="export-section">
  <div class="export-card">
    <div class="export-text">
      <h3>Exportar resultados</h3>
      <p>Genera un resumen con calificaciones y observaciones para el acta de sesión.</p>
    </div>
    <button class="export-btn" onclick="openModal()">Ver resumen completo</button>
  </div>
</div>

<div class="modal-overlay" id="modal-overlay" onclick="closeModalOutside(event)">
  <div class="modal">
    <h2>Resumen de la sesión</h2>
    <p class="modal-sub">Calificaciones y observaciones por criterio — Oliveto</p>
    <div class="modal-results" id="modal-results"></div>
    <div class="modal-footer">
      <button class="btn-close" onclick="closeModal()">Cerrar</button>
      <button class="btn-copy" onclick="copyResults()">Copiar texto</button>
    </div>
  </div>
</div>

<script>
const criterios = [
  {
    cat: "Espacio y capacidad operativa",
    items: [
      { id:"c1", nombre:"Capacidad mínima de 40 sillas en salón", razon:"Oliveto opera como casual dining experiencial. Con menos de 40 cubiertos el punto de equilibrio operativo se rompe: los costos fijos (nómina de cocina y salón, canon, servicios) no se cubren con un volumen tan bajo. En Parkway, Usaquén y Zona G el pico de fines de semana demanda entre 50 y 70 comensales simultáneos." },
      { id:"c2", nombre:"Área mínima total ≥ 100 m² (incluyendo cocina)", razon:"La propuesta gastronómica de Oliveto —pizza en horno de leña o gas, pasta fresca, coctelería— exige una cocina funcional con estaciones diferenciadas. Por debajo de 100 m² totales se sacrifica o el salón o la capacidad de producción, afectando calidad y tiempos de servicio." },
      { id:"c3", nombre:"Terraza o espacio exterior disponible", razon:"El consumidor core de Oliveto (25-40 años, sociable, experiencial) valora altamente el ambiente exterior. Las terrazas generan entre 20-30% de ingresos adicionales los fines de semana y funcionan como vitrina visible hacia el flujo peatonal." },
      { id:"c4", nombre:"Cocina con extracción y gas natural (≥ 1 punto)", razon:"El menú de Oliveto requiere cocción a alta temperatura. Un punto de gas con medidor propio y extracción mecánica es innegociable. Locales sin gas o solo con inducción obligan a reformular el menú o a inversiones de adecuación que pueden superar $80-120M COP." },
    ]
  },
  {
    cat: "Accesibilidad y visibilidad",
    items: [
      { id:"c5", nombre:"Visibilidad directa desde flujo peatonal principal", razon:"El perfil experiencial de Oliveto depende del walk-in y el discovery. Un local sin vitrina visible al paso o en segunda planta sin señalización potente pierde entre 30-40% del tráfico espontáneo, fracción importante de la facturación en días de semana." },
      { id:"c6", nombre:"Disponibilidad de parqueadero cercano (propio o público)", razon:"El cliente de estratos 4-6 en Bogotá se moviliza mayoritariamente en carro propio o app. La ausencia de parqueadero es un freno de visita documentado, especialmente para cenas y grupos familiares." },
      { id:"c7", nombre:"Acceso a transporte público a menos de 5 min a pie", razon:"El buyer persona profesional (30-50 años) usa con frecuencia Transmilenio. Para almuerzos ejecutivos en zonas como El Polo (5 estaciones TM), la accesibilidad en transporte es habilitador de visita en horario laboral, que representa 30-40% del volumen semanal." },
      { id:"c8", nombre:"Fachada diferenciable y apta para branding Oliveto", razon:"El posicionamiento visual de Oliveto —identidad italiana, cálida, auténtica— requiere fachada que permita expresar la marca. Locales en food halls con paleta predefinida o en piso 2 sin fachada limitan la construcción de marca local." },
    ]
  },
  {
    cat: "Entorno y contexto comercial",
    items: [
      { id:"c9", nombre:"Clúster gastronómico activo y de calidad en la zona", razon:"Un clúster de calidad valida la demanda y el nivel de gasto en la zona. Para Oliveto, no implica necesariamente competencia directa si su posicionamiento es diferenciado. Ejemplos ideales: Zona G, Usaquén, Parkway." },
      { id:"c10", nombre:"Predominio de estratos 4-6 en radio de 1 km", razon:"El ticket promedio de $50.000-80.000 por persona solo es sostenible en zonas con ingreso familiar medio-alto. Locales en sectores con estrato predominante 1-3 generan presión de precio que erosiona el margen y la propuesta de valor." },
      { id:"c11", nombre:"Generadores de tráfico cercanos (oficinas, clínicas, universidades, centros comerciales)", razon:"Los mejores locales de Oliveto tienen tráfico garantizado por el entorno. Locales dependientes solo del destino Oliveto son más vulnerables a estacionalidad y días de baja demanda espontánea." },
      { id:"c12", nombre:"Baja saturación gastronómica (menos de 1 restaurante por 300 personas)", razon:"Un mercado sobresaturado erosiona la demanda disponible. En zonas saturadas, el esfuerzo de marketing para capturar cuota es mayor y el riesgo de fracaso en los primeros 12 meses se incrementa significativamente." },
    ]
  },
  {
    cat: "Condiciones contractuales y financieras",
    items: [
      { id:"c13", nombre:"Canon fijo ajustado al volumen proyectado (≤12% de ventas esperadas)", razon:"Canones de $14-21M COP/mes exigen ventas mínimas de $140-175M/mes para ser viables. Un local que no alcance ese volumen en los primeros 6 meses opera en rojo estructural." },
      { id:"c14", nombre:"Periodo de gracia mínimo de 60 días para adecuación", razon:"La adecuación de un local Oliveto implica cocina, horno, extracción, acabados y montaje de sala. 60 días es el mínimo viable para esas obras sin pagar canon, protegiendo el flujo de caja inicial." },
      { id:"c15", nombre:"Plazo de contrato mínimo 5 años (para amortizar inversión)", razon:"La inversión de adecuación se estima entre $150-300M COP. Con plazo inferior a 5 años la amortización es inviable sin aumentar precios o sacrificar rentabilidad. Es el estándar mínimo del sector." },
      { id:"c16", nombre:"Incremento anual de renta máximo IPC + 2 puntos", razon:"Con inflación de 6-9% anual, IPC+2 significa rentas que crecen 8-11% por año. Por encima de ese nivel, el costo de ocupación puede escalar más rápido que los ingresos, destruyendo margen en el mediano plazo." },
    ]
  },
  {
    cat: "Experiencia y propuesta de valor",
    items: [
      { id:"c17", nombre:"Posibilidad de instalar horno italiano visible (show kitchen)", razon:"El horno visible es un elemento identitario de Oliveto. Genera confianza, percepción de calidad artesanal y contenido visual para redes. En locales con restricciones de extracción o espacio mínimo, este diferencial se pierde." },
      { id:"c18", nombre:"Ambiente cálido habilitado (iluminación y materiales naturales)", razon:"El consumidor de Oliveto valora la atmósfera tanto como el producto. Un local con iluminación fría o diseño genérico de food hall obliga a inversión alta en decoración y aún puede no alcanzar el estándar de ambiente esperado." },
      { id:"c19", nombre:"Posibilidad de operar de lunes a lunes sin restricciones de horario", razon:"Locales con restricciones de horario por normativa del centro comercial limitan el potencial de ingresos semanales entre 15-25%, especialmente en días lunes y festivos de alto consumo familiar." },
      { id:"c20", nombre:"Compatibilidad de marcas vecinas con el posicionamiento de Oliveto", razon:"La percepción de marca se contagia del entorno. Oliveto entre marcas de fast food o bajo ticket genera disonancia y dificulta justificar el precio. El entorno ideal: Crepes & Waffles, Buffalo Wings, restaurantes de autor." },
    ]
  },
  {
    cat: "Operación y logística",
    items: [
      { id:"c21", nombre:"Acceso a cargue y descargue sin afectar el salón", razon:"Oliveto recibe insumos diariamente. Sin acceso diferenciado, los proveedores ingresan por el salón en horas de servicio, afectando la experiencia del cliente y generando posibles sanciones del operador del inmueble." },
      { id:"c22", nombre:"Capacidad eléctrica suficiente (≥16 KVa trifásico)", razon:"La operación simultánea de horno, cámaras de refrigeración, extractores, cafetera industrial y sistema de luces exige mínimo 16 KVa. Capacidad insuficiente obliga a priorizar equipos, afectando calidad y velocidad del servicio." },
    ]
  }
];

const scores = {};
const obs = {};
criterios.forEach(cat => cat.items.forEach(it => { scores[it.id] = 0; obs[it.id] = ''; }));

const badgeLabels = { 5:'Vital', 4:'Alto', 3:'Medio', 2:'Bajo', 1:'Prescindible' };

function buildUI() {
  const container = document.getElementById('content-area');
  criterios.forEach((cat, ci) => {
    const block = document.createElement('div');
    block.className = 'category-block';

    const hdr = document.createElement('div');
    hdr.className = 'category-header';
    hdr.innerHTML = `<div class="category-num">${ci+1}</div><div class="category-title">${cat.cat}</div><div class="category-line"></div>`;
    block.appendChild(hdr);

    cat.items.forEach(item => {
      const card = document.createElement('div');
      card.className = 'item-card';
      card.id = 'card-' + item.id;

      card.innerHTML = `
        <div class="item-top">
          <div class="item-left">
            <div class="item-name">${item.nombre}</div>
            <span class="item-badge" id="badge-${item.id}"></span>
          </div>
          <div class="dots-wrap">
            <div class="dots-label"><span>prescindible</span><span>vital</span></div>
            <div class="dots-row" id="dots-${item.id}"></div>
          </div>
        </div>
        <div class="reason-box">
          <div class="reason-label">Contexto para Oliveto</div>
          ${item.razon}
        </div>
        <div class="obs-label">Observaciones de la sesión</div>
        <textarea class="obs-textarea" id="obs-${item.id}" placeholder="Anota comentarios, excepciones o acuerdos con Matías…" oninput="saveObs('${item.id}', this.value)"></textarea>
      `;

      block.appendChild(card);

      setTimeout(() => {
        const dotsRow = document.getElementById('dots-' + item.id);
        for (let i = 1; i <= 5; i++) {
          const dot = document.createElement('div');
          dot.className = 'dot';
          dot.textContent = i;
          dot.onclick = () => setScore(item.id, i);
          dot.id = `dot-${item.id}-${i}`;
          dotsRow.appendChild(dot);
        }
      }, 0);
    });

    container.appendChild(block);
  });
}

function setScore(id, val) {
  scores[id] = val;
  for (let i = 1; i <= 5; i++) {
    const dot = document.getElementById(`dot-${id}-${i}`);
    if (!dot) continue;
    dot.className = 'dot';
    if (i <= val) dot.classList.add(`active-${val}`);
  }
  const badge = document.getElementById('badge-' + id);
  badge.className = 'item-badge visible badge-' + val;
  badge.textContent = badgeLabels[val];
  const card = document.getElementById('card-' + id);
  card.className = 'item-card scored-' + val;
  updateSummary();
}

function saveObs(id, val) { obs[id] = val; }

function updateSummary() {
  const vals = Object.values(scores);
  const done = vals.filter(v => v > 0).length;
  document.getElementById('cnt5').textContent = vals.filter(v => v===5).length;
  document.getElementById('cnt4').textContent = vals.filter(v => v===4).length;
  document.getElementById('cnt3').textContent = vals.filter(v => v===3).length;
  document.getElementById('cnt-done').textContent = done + '/22';
  const pct = (done / 22) * 100;
  document.getElementById('progress-bar').style.width = pct + '%';
  document.getElementById('progress-label').textContent = done + ' de 22 criterios calificados';
}

function openModal() {
  const modal = document.getElementById('modal-results');
  let html = '';
  let totalScore = 0;
  let totalDone = 0;
  criterios.forEach(cat => {
    html += `<div class="cat-title">${cat.cat}</div>`;
    cat.items.forEach(item => {
      const s = scores[item.id];
      const o = obs[item.id] || '';
      if (s > 0) { totalScore += s; totalDone++; }
      const scoreLabel = s > 0 ? `${s}/5 — ${badgeLabels[s]}` : '— Sin calificar';
      html += `<div class="result-row">
        <div class="result-score">${s > 0 ? s : '—'}</div>
        <div>
          <div>${item.nombre}</div>
          ${o ? `<div class="result-obs">"${o}"</div>` : ''}
        </div>
      </div>`;
    });
  });
  const avg = totalDone > 0 ? (totalScore/totalDone).toFixed(1) : '—';
  html = `<div style="display:flex;gap:12px;margin-bottom:16px;flex-wrap:wrap;">
    <div style="background:var(--cream);padding:10px 16px;border-radius:8px;text-align:center;flex:1;min-width:80px;">
      <div style="font-size:20px;font-weight:500;color:var(--olive);">${totalDone}/22</div>
      <div style="font-size:11px;color:var(--text-soft);">Calificados</div>
    </div>
    <div style="background:var(--cream);padding:10px 16px;border-radius:8px;text-align:center;flex:1;min-width:80px;">
      <div style="font-size:20px;font-weight:500;color:var(--red-vital);">${Object.values(scores).filter(v=>v===5).length}</div>
      <div style="font-size:11px;color:var(--text-soft);">Vitales</div>
    </div>
    <div style="background:var(--cream);padding:10px 16px;border-radius:8px;text-align:center;flex:1;min-width:80px;">
      <div style="font-size:20px;font-weight:500;color:var(--olive);">${avg}</div>
      <div style="font-size:11px;color:var(--text-soft);">Promedio</div>
    </div>
  </div>` + html;
  modal.innerHTML = html;
  document.getElementById('modal-overlay').classList.add('open');
}

function closeModal() { document.getElementById('modal-overlay').classList.remove('open'); }
function closeModalOutside(e) { if (e.target === document.getElementById('modal-overlay')) closeModal(); }

function copyResults() {
  let text = 'EVALUACIÓN DE CRITERIOS — OLIVETO\nGrupo Proyección · Consultandes 2026\n';
  const totalDone = Object.values(scores).filter(v=>v>0).length;
  const totalScore = Object.values(scores).filter(v=>v>0).reduce((a,b)=>a+b,0);
  const avg = totalDone > 0 ? (totalScore/totalDone).toFixed(1) : '—';
  text += `Calificados: ${totalDone}/22 | Promedio: ${avg}\n`;
  criterios.forEach(cat => {
    text += `\n${cat.cat.toUpperCase()}\n`;
    cat.items.forEach(item => {
      const s = scores[item.id];
      const o = obs[item.id];
      text += `  [${s > 0 ? s : '—'}/5] ${item.nombre}`;
      if (s > 0) text += ` — ${badgeLabels[s]}`;
      if (o) text += `\n       Obs: ${o}`;
      text += '\n';
    });
  });
  navigator.clipboard.writeText(text).then(() => {
    const btn = document.querySelector('.btn-copy');
    const orig = btn.textContent;
    btn.textContent = '¡Copiado!';
    setTimeout(() => btn.textContent = orig, 2000);
  });
}

buildUI();
</script>
</body>
</html>
