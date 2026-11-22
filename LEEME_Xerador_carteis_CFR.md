# Xerador de carteis — CFR de Vigo

Ferramenta HTML autónoma (sen servidor, sen conexión a internet unha vez aberta) para xerar de forma consistente os materiais gráficos dunha actividade formativa: carteis para redes sociais, o banner de cabeceira do curso na Aula Virtual de Moodle e a imaxe para o carrusel de Moodle.

## Como abrila

É un só ficheiro `.html`. Abrino co navegador (dobre clic ou arrastralo a unha xanela do navegador). Non precisa instalación nin conexión a internet: as librarías de exportación (html2canvas, jsPDF, JSZip) e a tipografía Xunta Sans están incrustadas no propio ficheiro.

Gárdao xunto ás outras apps do CFR (Boxabalar) para telo sincronizado entre o equipo de traballo e o portátil.

Dentro do propio aplicativo hai un botón **"❓ Axuda"** (arriba do panel de edición) cun resumo equivalente a este documento.

---

## 1. Formatos dispoñibles

| Formato | Tamaño por defecto | Uso |
|---|---|---|
| **Cadrado (IG feed)** | 1080 × 1080 px | Publicación cadrada de Instagram |
| **Story (IG/vertical)** | 1080 × 1920 px | Historia de Instagram |
| **X / Twitter** | 1600 × 900 px | Publicación en X |
| **Moodle (etiqueta)** | 1600 × 400 px (editable) | Cabeceira do curso na Aula Virtual |
| **Carrusel (ficha)** | 1600 × 900 px (16:9) | Imaxe da columna de ilustración das fichas do carrusel de Moodle |

Cada formato ten a súa propia pestana na vista previa. O botón **"Ver os 3 á vez"** amosa cadrado, story e X en paralelo (o banner de Moodle e a imaxe do carrusel non entran nesa vista conxunta, xa que teñen un propósito distinto e a súa propia exportación).

---

## 2. Datos do cartel

Campos do formulario, comúns a cadrado, story, X e Moodle (a imaxe do carrusel non os usa):

- **Código da actividade** (ex. `V2601030`)
- **Título**
- **Ponente / boas prácticas de centro** — cada liña do texto aparece como unha liña separada no cartel
- **Lugar de celebración**
- **Datas**
- **Horario**

O banner de Moodle **non** amosa ponentes, lugar, datas nin horario — só código, título e os dous logos.

---

## 3. Patróns de colocación

Cadrado, Story e X teñen un selector de **patrón** independente cada un (podes combinar, por exemplo, "banda inferior única" en cadrado con "columna lateral" en X):

- **Estándar** — cabeceira arriba, ilustración no medio, pé abaixo.
- **Pé arriba / información abaixo** — os logos pasan arriba; título e datos van nunha franxa inferior.
- **Banda inferior única** — a ilustración ocupa case todo o cartel; cabeceira e pé quedan xuntos ao final, formando unha soa banda de cor.
- **Columna lateral** — texto nunha columna lateral, coa ilustración ao carón. **Só dispoñible en X** (en cadrado e story non se ofrece esta opción).
- **Ilustración a sangre + texto superposto** — a imaxe ocupa todo o cartel, con cabeceira e pé en faixas semitransparentes por riba.

En X, os catro patróns que non son "columna lateral" usan unha disposición en fila (título+ponentes á esquerda, lugar/datas/horario á dereita) coherente coa de IG feed, con letra maior. A "columna lateral" mantén o seu propio deseño compacto.

En Story, os catro patróns dispoñibles amosan unha fila debaixo do título con ponentes á esquerda e lugar/datas/horario á dereita, á mesma altura — isto reduce a banda azul fronte a telos un debaixo do outro.

O banner de Moodle ten o seu propio deseño fixo (columna azul institucional coa información + ilustración ao carón) e non usa este selector.

Todos os formatos teñen **auto-axuste do tamaño de letra do título**: se é longo, redúcese automaticamente para non desbordar.

---

## 4. Personalización

- **Aliñamento do texto**: esquerda ou centrado (título e ponentes).
- **Cor de acento**: por defecto o azul institucional da Xunta, `rgb(0, 123, 196)`. Pódese cambiar escribindo outro valor (`rgb(...)` ou `#rrggbb`) ou co **selector de cor** situado xunto ao campo — sincronízanse automaticamente entre si. Se o texto non é unha cor válida, volve ao azul institucional.
- **Logos**: veñen cargados por defecto (Xunta de Galicia e Xacobeo 2027, versión branca). Pódense substituír cargando outra imaxe nos campos correspondentes.
- **Tamaño do banner Moodle**: ancho e alto editables en píxeles (non hai unha medida única estándar en Moodle — depende do tema visual de cada Aula Virtual).

---

## 5. Axuste da ilustración

Na sección **«Axuste da ilustración»** escóllese, para cada formato, como se coloca a imaxe na súa zona:

- **Recortar**: enche a zona e pode cortar os bordos. En cadrado e story pódese fixar a posición (arriba, centro ou abaixo) ou escoller **posición libre**: arrastras a imaxe sobre a vista previa e a descarga respecta esa posición.
- **Encaixar completa**: móstrase enteira, sen cortar; as franxas que sobran quedan en branco.

Valores por defecto: cadrado, recortar arriba; story, recortar centro; X e Moodle, encaixar completa.

Ao cargar unha ilustración, se o seu lado maior pasa de 2000 px, reescálase e gárdase en JPEG ao 92 % (menos peso na garda e no PDF); se é menor, non se toca.

A descarga sae **igual que a vista previa**. (Nunha versión anterior as descargas podían estirar a ilustración; xa está corrixido.)

Baixo cada campo de carga amósase o **tamaño en píxeles e a proporción** da imaxe cargada, cun aviso se a horizontal non é preto de 16:9 ou a vertical preto de 9:16.

---

## 6. Ilustracións e prompts para IA

Fan falta **dúas ilustracións distintas**, cargadas en campos separados:

- **Ilustración horizontal** — úsase en X, no banner de Moodle e na imaxe do carrusel.
- **Ilustración vertical** — úsase en Cadrado e Story.

Para axudar a xeralas cunha ferramenta de IA (ex. Gemini), a sección "Ilustración" inclúe:

- **Marxe e letras**: os dous prompts piden unha marxe libre de polo menos un 8 % en todos os bordos e prohiben letras, números e texto en calquera parte da imaxe, tamén en obxectos (cubos, xoguetes, reloxos, paneis, pictogramas).
- **Elementos visuais** (opcional, común ás dúas imaxes): un campo de texto cunha lista despregable de suxestións predefinidas (portátil e traballo en equipo, libros e material, reunión de claustro, recursos TIC, benestar/mindfulness, traballo colaborativo, alumnado e profesorado, formación online, natureza/sustentabilidade, inclusión/diversidade), pero admite tamén escribir texto libre.
- **Cor da paleta para os prompts** (opcional): por defecto úsase a cor de acento do cartel; pódese indicar outra só para a ilustración, en texto ou co selector de cor. Se se deixa baleira ou non é válida, cae de volta á cor de acento.
- **"Xerar prompt horizontal"** → xera un texto listo para pegar nunha IA, pedindo unha imaxe en proporción **16:9** (~1600×900), coa temática, cor e elementos indicados.
- **"Xerar prompt vertical"** → pide unha imaxe en proporción **9:16** (~1080×1920), coa instrución explícita de distribuír os elementos por todo o eixe vertical (arriba, medio e abaixo) — para evitar que a IA simplemente estire a composición horizontal no medio dun lenzo vertical — e co motivo principal na metade superior, para que aguante ben o recorte a 1:1 no cadrado.
- Cada prompt ten o seu botón **"Copiar prompt"** para pasalo ao portapapeis.

Ademais, agora podes axustar:

- **🪄 Asistente de ilustración**: botón na sección «Ilustración» que guía en 5 pasos, pensado para persoas sen coñecementos de deseño:
  1. **Uso**: todo (redes, Moodle e carrusel), só redes e Moodle, ou só o carrusel. Decide se fan falta a imaxe horizontal, a vertical ou as dúas.
  2. **Tema**: título da actividade e elementos visuais (con suxestións).
  3. **Aspecto**: estilo explicado en linguaxe sinxela (con indicación de cales conveñen ao carrusel) e «escena completa» ou «poucos elementos grandes».
  4. **Prompt**: xéranse con botón de copiar, e inclúense pasos xerais para usar unha ferramenta de IA (sen depender de ningunha concreta) e o consello de fixar a proporción 16:9 ou 9:16 no selector da ferramenta, se o permite. Hai tamén un botón **«Copiar os dous prompts xuntos»** (etiquetados como «X / Moodle / Carrusel» e «Cadrado / Story»), igual que no panel.
  5. **Carga e comprobación**: a app comproba automaticamente o tamaño, a proporción e se os bordos non son brancos (esta última é unha **estimación**), e a persoa revisa á man o que a app non pode detectar (texto na imaxe, elementos que tocan o bordo, marco, persoas identificables). Os botóns **«Ver en…»** recollen o asistente nunha barra pequena (esquina inferior esquerda) e cambian a vista previa ao formato escollido, para ver o resultado no cartel; con «Volver ao asistente» retómase onde estaba.

  O asistente configura os mesmos campos do panel e usa o mesmo xerador de prompts.
- **Estilo visual**: vectorial plano (por defecto), liña fina, isométrico, acuarela suave, plano con contorno groso, iconográfico (obxectos grandes), duotono ou xeométrico minimalista. A frase de paleta do prompt adáptase a cada estilo. Para o carrusel, onde a imaxe se ve pequena sobre branco, convén un estilo de formas grandes e poucos detalles (evita acuarela e isométrico). Esta recomendación é orientativa e non está probada con todas as ferramentas de IA.
- **Densidade**: «escena completa» (por defecto) ou «poucos elementos grandes» (3 ou 4 elementos claros, que se len mellor a tamaño reducido).
- **Idioma do prompt**: galego ou inglés (o texto que escribas en "Elementos visuais" mantense tal cal, na lingua en que o escribiches).
- **Ferramenta destino**: xenérica ou Midjourney (engade automaticamente `--ar 16:9` / `--ar 9:16` ao final do prompt).
- **Recentes**: os últimos "elementos visuais" e cores que usaches aparecen como botóns rápidos debaixo dos seus campos.
- **Copiar os dous prompts xuntos**: unha vez xerados os dous, cópianse nun só texto, etiquetados e separados.

Despois de xerar as imaxes fóra desta ferramenta, cárganse cada unha no seu campo (horizontal / vertical).

---

## 7. Imaxe para o carrusel

Xera a imaxe da columna de ilustración das fichas do carrusel de Moodle (`carrusel-cfr`). Reutiliza a **ilustración horizontal** (non hai que subir outra) e **non usa** código, título, datas, ponentes nin lugar: a ficha do carrusel ten a súa propia lóxica.

- **Resultado**: 1600 × 900 px (16:9), só ilustración (sen texto nin logos), encaixada **enteira, sen cortar**, sobre un lenzo **branco opaco**.
- **Marxe de seguridade**: 0 % por defecto (a ilustración ocupa todo o lenzo); pódese subir ata 20 %.
- **Fundir bordos con branco** (activado por defecto): suaviza os bordos para que non se vexa un rectángulo se a ilustración non é branca nos extremos. Pódese desactivar.
- **Formato**: PNG ou JPG ao 90 % (máis lixeiro; sempre sobre fondo branco).
- **Vista previa**: amosa a imaxe nunha caixa grande e en dúas caixas simuladas da ficha (a máis ancha, 2,05:1, e a máis alta, 1,71:1, segundo o que se mediu no código do carrusel). É unha aproximación: convén comprobalo co carrusel real.
- **Cor para a columna K («CorFondo»)**: amosa a cor de acento do cartel en `#rrggbb`, cun botón para copiala. Se o contraste co branco (texto da ficha) é inferior a 4,5:1 (WCAG AA), aparece un aviso informativo.
- A altura da ficha depende do contido da columna de información; imaxes do mesmo tamaño non garanten por si soas fichas sempre da mesma altura.

Descarga: botón **«Descargar imaxe (carrusel)»** → `{codigo}_carrusel.png` (ou `.jpg`). Tamén vai no ZIP e no PDF.

---

## 8. Exportar

- **Descargar PNG (formato actual)** — só o formato e patrón que se está a ver.
- **🔍 Ver a tamaño real** — amosa o formato/patrón actual a escala 1:1 (1 píxel = 1 píxel), nunha xanela con scroll, útil para revisar detalles antes de exportar.
- **Descargar imaxes (os 5 formatos, ZIP)** — cadrado + story + X + etiqueta de Moodle + imaxe do carrusel nun único ZIP (o carrusel co formato PNG/JPG escollido).
- **Descargar PDF (os 5 formatos)** — os mesmos 5 formatos como páxinas dun PDF. As páxinas van en JPEG ao 92 % (pesa moito menos ca en PNG, con algo menos de nitidez nos bordos finos).
- **Descargar PNG (etiqueta Moodle)** e **Descargar imaxe (carrusel)** — botóns independentes, sempre visibles, para descargar só esa imaxe.

**Avisos antes de exportar:** se falta a ilustración, o código ou o título, se o título é moi longo (máis de 100 caracteres) ou se a cor de acento dá un contraste co texto branco inferior a 4,5:1, aparece unha lista e podes exportar igualmente ou cancelar.

Antes de exportar, se falta a ilustración horizontal (necesaria tamén para o carrusel) ou a vertical necesaria para ese formato, a ferramenta pregunta se se quere continuar así mesmo.

---

## 9. Garda automática e xestión da sesión

- **Garda automática**: os datos do formulario (texto, ilustracións, cores, patróns e opcións do carrusel) gárdanse sós neste navegador a medida que os escribes. Non se envía nada a ningún servidor. Se pechas a lapela por accidente, ao reabrir a ferramenta recuperas o traballo.
- As **preferencias** (cor de acento, aliñamento, logos) gárdanse á parte do **borrador** (os datos concretos da actividade) — así podes limpar unha actividade sen perder a túa configuración habitual.
- **⬇ Exportar / ⬆ Importar actividade (.json)**: copia de seguridade ou traslado a outro ordenador ou persoa. Inclúe texto, patróns, axustes, cores e opcións do carrusel; coa caixa «Incluír ilustracións e logos» marcada, tamén as imaxes (o ficheiro pesa máis). Importar substitúe a actividade actual, tras confirmación; se o ficheiro non trae ilustracións, mantéñense as cargadas.
- **Textos para as redes**: xera un texto alternativo e un texto de publicación a partir dos datos do cartel (código, título, persoas relatoras, lugar, datas e horario), editables e con botón de copiar. Non describen a ilustración.
- **Versión**: o número (agora v1.4) aparece ao final do panel de edición e na axuda. Para cambialo, edítase a constante `APP_VERSION` no código.
- **Aviso de garda**: o texto e as ilustracións gárdanse por separado. Se as imaxes non caben no almacenamento do navegador, aparece un aviso e o texto gárdase igual. Ao estar a ferramenta publicada, a garda é **por navegador e por enderezo**: non se comparte entre ordenadores; para iso serve o .json.
- **🗑️ Nova actividade**: limpa código, título, ponentes, lugar, datas, horario, ilustracións e patróns, para empezar unha actividade nova de cero. Pide confirmación antes de borrar. A cor de acento, o aliñamento e os logos cargados **non** se ven afectados.

---

## Axuda e preguntas frecuentes

**O título non se le ben, queda moi grande ou desbordado.**
Non hai que facer nada: todos os formatos teñen auto-axuste de letra. Se o título é moi longo, proba a "banda inferior única" (dá máis marxe vertical á cabeceira).

**Cal ilustración uso en cada formato?**
A horizontal vai en X, no banner de Moodle e no carrusel; a vertical vai en Cadrado e Story. Se só cargas unha delas, o formato que precise a outra amosará "Sen ilustración cargada".

**A cor que puxen non se aplicou.**
Os campos de cor só aceptan `rgb(r, g, b)` ou `#rrggbb`. Calquera outro formato (nomes de cor, HSL, etc.) non se recoñece e a ferramenta volve automaticamente á cor de acento (ou ao azul institucional, no caso do propio campo de acento).

**Que fago se o meu Moodle precisa outro tamaño de banner?**
Cambia os campos "Ancho (px)" e "Alto (px)" na sección "Banner Moodle" antes de descargar. Non hai unha medida única estándar en Moodle.

**Pode fallar a descarga se o ordenador non ten conexión a internet?**
Non — as librarías necesarias (html2canvas, jsPDF, JSZip) e a tipografía Xunta Sans están incrustadas dentro do propio ficheiro HTML, así que funciona sen conexión unha vez aberto no navegador.

**Quero engadir un novo patrón de colocación ou un formato novo.**
Isto require editar o código (ficheiro HTML). Non hai un editor visual para iso; pídello a quen xestione a ferramenta.

---

*Ferramenta de uso interno do CFR de Vigo. Non recolle nin envía datos a ningún servidor: todo o procesamento (incluída a xeración de imaxes) ocorre no propio navegador.*
