<prompt>
  <task>
    Diseñar y construir una landing page estática para Sagra, una grasa de pella
    fundida envasada, usando la skill huashu-design desde OpenCode. La página debe
    mostrar las dos presentaciones del producto con sus respectivos códigos QR (o
    servir como destino de un QR único), y deployarse en GitHub Pages.
  </task>
  <role>
    Experto en desarrollo frontend estático y diseño de producto, con conocimiento
    de la skill huashu-design y flujos de deploy en GitHub Pages.
  </role>
  <context>
    <background>
      El proyecto se llama Sagra. El producto es grasa de pella fundida envasada,
      con dos presentaciones actuales. Los frascos llevan códigos QR que apuntan
      a esta landing. El contenido es esencialmente estático — actualizaciones
      mínimas y poco frecuentes. El usuario trabaja en OpenCode con modelos
      OpenCode Go y Big Pickle, y tiene experiencia limitada en deploy (solo
      Google Apps Script hasta ahora).
    </background>
    <audience>
      Consumidor final que escanea el QR del frasco y llega a la página buscando
      información sobre el producto.
    </audience>
    <domain>Landing page de producto artesanal / alimenticio</domain>
  </context>
  <constraints>
    <must_include>
      - Descripción breve de Sagra y del producto (grasa de pella fundida)
      - Sección para cada una de las dos presentaciones con nombre, descripción
        y foto real del frasco
      - Diseño responsivo (mobile-first, ya que el tráfico vendrá de escaneos QR)
      - Todo en un único archivo HTML autosuficiente (sin dependencias externas
        de servidor)
      - Instrucciones de deploy en GitHub Pages paso a paso, dado el nivel de
        experiencia del usuario
    </must_include>
    <must_avoid>
      - Frameworks que requieran build step (React, Vite, etc.)
      - Bases de datos o backends de cualquier tipo
      - CMS o paneles de administración
      - Diseño rústico o "campero" — no es la dirección estética buscada
    </must_avoid>
    <scope>
      Una sola página HTML. Las imágenes reales del producto las provee el usuario.
      Si no están disponibles al momento de generar, usar placeholders claramente
      marcados como reemplazables. La decisión de 1 QR vs 2 QR queda abierta:
      la landing debe funcionar bien en ambos casos (puede mostrar ambas
      presentaciones en la misma página).
    </scope>
  </constraints>
  <reasoning>
    Priorizar simplicidad de mantenimiento y cero fricción en el deploy por sobre
    sofisticación técnica. El usuario actualizará el contenido lo menos posible,
    así que la estructura debe ser fácil de editar manualmente (HTML limpio, sin
    abstracciones). GitHub Pages es el target de deploy por su gratuidad y
    simplicidad. El estilo visual debe derivarse de las imágenes del producto:
    limpio y premium, no rústico.
  </reasoning>
  <output_format>
    <structure>
      1. Archivo index.html completo y listo para usar con huashu-design
      2. Guía de deploy en GitHub Pages (paso a paso, asumiendo poca experiencia)
      3. Indicación de dónde y cómo reemplazar las imágenes placeholder por las reales
    </structure>
    <language>Español</language>
    <presentation>
      Presentar primero el HTML, luego la guía de deploy. Marcar claramente
      todo lo que el usuario debe personalizar (textos, imágenes, nombre de repo).
    </presentation>
  </output_format>
  <assumptions>
    - La landing será en español
    - El usuario tiene cuenta en GitHub
    - La skill huashu-design ya está instalada o se instalará con npx skills add
    - No se requiere dominio propio por ahora (se usa el dominio gratuito de GitHub Pages)
    - Una sola página cubre ambas presentaciones (no se necesitan subpáginas separadas)
  </assumptions>
</prompt>