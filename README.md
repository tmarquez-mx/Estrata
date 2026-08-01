
# Estrata — publicación académica en capas

> Prototipo experimental de autopublicación digital multicapa para ciencias sociales y humanidades.

---

## Qué es Estrata

Estrata es un proyecto experimental de autopublicación digital dirigido a estudiantes, docentes e investigadores de las ciencias sociales y las humanidades. Su propósito es explorar formas de publicación académica que no reproduzcan únicamente la estructura lineal y cerrada del libro impreso, sino que integren diferentes modos de lectura, interpretación y producción de conocimiento dentro de una misma obra digital.

La propuesta retoma el principio de publicación multicapa desarrollado por el [Journal of Digital History](https://journalofdigitalhistory.org), cuyas publicaciones articulan narrativa académica, reflexión metodológica y materiales documentales o computacionales. Estrata adapta este modelo a un entorno de escritura asistida por inteligencia artificial y propone tres capas complementarias.

### Las tres capas

**Capa 1 · narrativa**
Contiene el texto principal, producido mediante colaboración entre inteligencia artificial y supervisión humana. La intervención humana comprende la definición del argumento, la revisión conceptual, la verificación de fuentes y datos, la corrección de errores y la responsabilidad final sobre lo publicado. Esta capa puede recorrerse mediante texto, visualizaciones, gráficos, simulaciones y narración auditiva.

**Capa 2 · hermenéutica humana**
Reúne la interpretación humana. Incluye notas, comentarios, experiencias, objeciones, decisiones autorales y reflexiones sobre aquello que la inteligencia artificial no identificó, simplificó o interpretó de manera insuficiente. Esta capa hace visible que la producción académica no consiste solamente en presentar resultados, sino también en documentar las operaciones interpretativas mediante las cuales esos resultados adquieren sentido.

**Capa 3 · datos y materiales**
Contiene los datos y materiales de soporte. Puede incorporar bases de datos, documentos, referencias, registros de verificación, código, versiones, criterios de selección y otros elementos que permitan examinar la procedencia y construcción de las afirmaciones. Su función es fortalecer la transparencia, la trazabilidad y la posibilidad de revisión crítica de la publicación.


### Anotación y lectura activa

Estrata concibe la lectura como una práctica activa. Las personas lectoras pueden subrayar fragmentos, escribir anotaciones y producir memos vinculados con pasajes específicos. Para favorecer la interoperabilidad, estas anotaciones podrían estructurarse conforme al [modelo de anotación web del W3C](https://www.w3.org/TR/annotation-model/), diseñado para que los comentarios puedan compartirse, reutilizarse o trasladarse entre sistemas sin perder su relación con el recurso original. Los memos podrán exportarse en Markdown e incorporarse a entornos personales de conocimiento como [Obsidian](https://obsidian.md), que almacena sus notas como archivos de texto plano en este formato.

### Vibe coding como método

El proyecto será desarrollado mediante vibe coding, entendido aquí no como una delegación completa del desarrollo a la inteligencia artificial, sino como un proceso iterativo de diseño, generación, prueba, evaluación y corrección supervisada. Estrata es, por tanto, simultáneamente una plataforma de publicación y un experimento metodológico sobre las posibilidades y los límites de la autoría académica humano-máquina.

**Su pregunta central es:** ¿qué formas de producción, lectura e interpretación del conocimiento se vuelven posibles cuando una publicación académica deja de ser un objeto cerrado y se convierte en una arquitectura explorable de textos, interpretaciones y datos?

---

## Estado actual del proyecto

Este repositorio contiene el **prototipo navegable v0.1**](https://claude.ai/public/artifacts/99928d7d-07d5-4b40-a62c-9a0bf131d92e)de Estrata: un único archivo HTML autónomo que demuestra las funciones centrales de la propuesta.

El prototipo es una prueba de concepto para presentar la idea, reunir equipo y conseguir recursos para una implementación robusta. No es el producto final.

### Qué funciona en el prototipo

- Conmutador de tres capas con efecto de barrido de color al cambiar entre ellas
- Gráfico interactivo (control deslizante reactivo) dentro de la capa narrativa
- Selección de texto para crear anotaciones en la misma página
- Panel de anotaciones con campo de memo editable por el lector
- URL profunda por sección y capa, adjunta a cada anotación
- Exportación individual o colectiva de anotaciones como archivos `.md` para Obsidian (con frontmatter YAML, cita como blockquote, memo y liga a la sección)
- Modo oscuro automático según preferencia del sistema
- Respeta la preferencia de movimiento reducido (`prefers-reduced-motion`)
- Responsivo en móvil

### Qué falta para la versión robusta

| Función | Herramienta prevista |
|---|---|
| Múltiples artículos con navegación | [Quarto](https://quarto.org) (sitio web estático) |
| Gráficos y simulaciones ejecutables | [Observable JS](https://observablehq.com/@observablehq/plot) dentro de Quarto |
| Código ejecutable en el navegador (sin servidor) | [quarto-live](https://r-wasm.github.io/quarto-live/) |
| Anotaciones persistentes, ancladas al texto | [Hypothes.is](https://web.hypothes.is) (estándar W3C) |
| Sincronización de anotaciones con Obsidian | Plugin [obsidian-hypothesis](https://github.com/weichenw/obsidian-hypothesis-plugin) |
| Documento vivo con historial de cambios | Git + GitHub Pages |
| Versiones citables con DOI | [Zenodo](https://zenodo.org) (concept DOI + DOI por versión) |
| Preservación a largo plazo | [CLOCKSS](https://clockss.org) / [Portico](https://www.portico.org) |

---

## Cómo navegar el prototipo

[**clic aquí**](https://claude.ai/public/artifacts/99928d7d-07d5-4b40-a62c-9a0bf131d92e)
No requiere instalación. Es un archivo HTML autónomo que funciona sin internet y sin dependencias externas.

1. Descarga `estrata-prototipo.html`.
2. Abre el archivo con doble clic en cualquier navegador moderno (Chrome, Firefox, Safari, Edge).
3. Cambia de capa con los botones "narrativa", "hermenéutica" y "datos".
4. Selecciona cualquier frase del artículo: aparece el botón "anotar".
5. Escribe tu memo en la tarjeta del panel de anotaciones.
6. Pulsa "exportar a Obsidian" para descargar un archivo `.md` listo para arrastrar a tu bóveda.

<img width="447" height="764" alt="Captura de pantalla 2026-07-31 a la(s) 6 17 35 p m" src="https://github.com/user-attachments/assets/3b8e8dfb-d4d6-4ed2-a042-c6156043e943" />

[**clic aquí **](https://claude.ai/public/artifacts/99928d7d-07d5-4b40-a62c-9a0bf131d92e)


---

## Estructura del repositorio

```
Estrata/
├── README.md                  ← este archivo
├── estrata-prototipo.html     ← prototipo navegable v0.1
└── quarto/                    ← (próximamente) fuente del sitio en Quarto
    ├── _quarto.yml
    ├── index.qmd
    └── styles.css
```

---

## Pila tecnológica prevista

```
Escritura       Obsidian (bóveda local en Markdown)
Publicación     Quarto → HTML estático
Interactividad  Observable JS (gráficos reactivos) + quarto-live (código ejecutable)
Anotación       Hypothes.is (W3C Web Annotation) + sincronización a Obsidian
Control         Git (historial) + GitHub Pages (hospedaje gratuito)
Citabilidad     Zenodo (DOI por versión + concept DOI)
Preservación    CLOCKSS / Portico (archivo oscuro)
```

---

## Cómo contribuir

Este proyecto busca activamente colaboradores con perfiles en:

- **Desarrollo front-end** — implementar el conmutador de capas con enlace párrafo a párrafo (al estilo JDH), la sincronización de anotaciones y la integración con Hypothes.is
- **Publicación con Quarto** — construir el sitio multicapítulo con Observable JS y quarto-live
- **Diseño de interacción** — afinar la experiencia de lectura en capas, especialmente en móvil
- **Humanidades digitales** — producir los primeros artículos reales de Estrata y documentar el proceso de autoría humano-máquina
- **Gestión de metadatos y preservación** — implementar el esquema de citación versionada con Zenodo y la preservación a largo plazo

Si te interesa participar, abre un issue describiendo tu perfil y área de interés, o escribe a la autora del proyecto.

---

## Referencias y antecedentes

- Journal of Digital History (C²DH / De Gruyter): modelo de publicación multicapa — https://journalofdigitalhistory.org
- W3C Web Annotation Data Model: estándar de anotación interoperable — https://www.w3.org/TR/annotation-model/
- Quarto (Posit): sistema de publicación científica web-nativa — https://quarto.org
- Hypothes.is: anotación web abierta — https://web.hypothes.is
- Darnton, R. (1999). "The new age of the book". *The New York Review of Books*.
- Knowledge Futures / PubPub: plataforma de publicación open source — https://pubpub.org
- Zenodo: repositorio abierto con DOI versionados — https://zenodo.org

---

## Licencia

El prototipo y los textos de este repositorio se publican bajo licencia [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Puedes compartir y adaptar el material siempre que se cite la fuente.

---

*Estrata es un documento vivo. Este README y el prototipo evolucionarán a medida que el proyecto crezca.*
