# CulturIA

Publicidad internacional adaptada a cada cultura con el modelo de Hofstede. Aplicación web de un solo fichero, en español, inglés y portugués.

**Usar la app:** https://fborrasumh.github.io/culturia/

**Idiomas:** español (por defecto), inglés y portugués; selector en la barra superior (o `?lang=en` / `?lang=pt` en la URL).

## Origen de la idea

A partir del cuaderno de Colab «Brújula Cultural Hofstede» de **Andreas Kanther** para la asignatura de Marketing Internacional (Universidad Miguel Hernández de Elche). CulturIA conserva su motor (umbrales, pesos por categoría, índice de Kogut y Singh, informe de mercado y briefing creativo; comprobado caso a caso contra el cuaderno en Python) y lo lleva a una app sin instalación, en tres idiomas y con más casos de uso.

## Qué hace

**Sin IA y sin clave (pasos 1 a 4):**

- Compara hasta seis de los 72 países con datos en las seis dimensiones de Hofstede (PDI, IDV, MAS, UAI, LTO, IVR): tabla, gráfico de barras y perfil en radar.
- Calcula la distancia cultural de Kogut y Singh respecto a un mercado de origen opcional y entre todos los países elegidos (matriz).
- Recomienda cómo adaptar la publicidad en 13 categorías de producto (alimentación, lujo, banca, turismo…), ordenando las recomendaciones por peso de la categoría × intensidad de la dimensión. También admite una **categoría propia** con pesos de 1 a 3 fijados por la persona.
- Redacta un informe de mercado para el país de destino (perfil cultural, implicaciones para la categoría, adaptación desde el origen o campaña nueva, claves del sector), un briefing creativo y lecturas para ampliar.
- Genera un **enlace de actividad** con el caso (países, origen, categoría y destino) para que todo un grupo trabaje lo mismo.

**Con la clave de IA de cada persona (pasos 5 y 6):** OpenAI (Responses API con búsqueda web), Google Gemini (búsqueda de Google) o Anthropic Claude (búsqueda web).

- Actualidad del mercado con búsqueda web: consumidor, mercado, normativa publicitaria, campañas y señales culturales, con fecha, fuente y URL de cada dato.
- Recomendaciones ampliadas en siete secciones que combinan Hofstede y actualidad.
- Propuesta creativa para una marca ficticia: concepto, titular y eslogan en el idioma del país, guion de 30 segundos, versión para redes y justificación cultural.
- Propuesta de pesos y consejos para una categoría propia.
- Consumo de cada llamada (tokens, búsquedas y coste aproximado con precios editables).

**Qué comprueba el código (la IA propone, el código comprueba):**

- Que cada puntuación que cita la IA («UAI = 92») coincida con la de algún país del caso.
- Qué cifras menciona la IA que no estaban en el contexto que recibió.
- Si la URL de cada dato de actualidad está entre las páginas que devolvió la búsqueda (por URL o por dominio); las que no, se marcan como posible fuente inventada.
- Si cada dato tiene fecha y si tiene más de 24 meses; si falta alguna sección.
- Que las recomendaciones tengan siete secciones y su longitud.
- Que el guion dure exactamente 30 s en tramos contiguos (sin huecos ni solapes), que los hashtags estén bien formados (3-5) y que la marca aparezca en el guion.
- Que los pesos de una categoría propuesta por la IA sean enteros de 1 a 3 (los demás se corrigen y se avisa).
- Si la búsqueda web no está disponible (p. ej., nivel gratuito de Gemini), repite la consulta sin búsqueda y lo indica en cada dato.

**Salidas:** informe completo en Word y HTML, consumo en CSV y proyecto en JSON (se puede volver a abrir; nunca incluye la clave).

## Privacidad

Todo se guarda solo en el navegador (IndexedDB). La clave de IA se guarda en el navegador y se envía únicamente al proveedor elegido. Al proveedor solo sale, en los pasos 5 y 6, el caso (países, categoría, puntuaciones e informe) y lo que la persona escriba como marca o producto; antes del primer envío de cada sesión se muestra exactamente lo que sale y se pide confirmación. No hay servidor propio.

## Límites

- El modelo de Hofstede describe medias nacionales con datos de hace décadas; no describe a cada consumidor ni a las culturas regionales. Las recomendaciones son hipótesis para validar con un pretest local.
- El código comprueba que una página exista entre las que consultó la búsqueda, **no que el dato sea cierto**: hay que abrir las fuentes. Con Gemini las fuentes llegan como enlaces de redirección y la comprobación se hace por dominio.
- Los precios de los modelos cambian: los de serie son orientativos (solo para los modelos del cuaderno original) y la persona puede escribir los suyos. El importe real lo da el panel de facturación del proveedor.
- Probado con respuestas simuladas de OpenAI, Gemini y Claude (incluidas búsquedas, fallos de búsqueda y respuestas con errores deliberados). No se ha probado todavía con claves reales.
- Las traducciones al inglés y al portugués (pt-PT) son propias; conviene que las revise un hablante nativo.

## Autoría

Fernando Borrás Rocher (Universidad Miguel Hernández de Elche) y Andreas Kanther (Universidad Miguel Hernández de Elche).
Idea original: cuaderno «Brújula Cultural Hofstede» de Andreas Kanther.

ORCID: Fernando Borrás Rocher [0000-0002-5519-4573](https://orcid.org/0000-0002-5519-4573) · Andreas Kanther [0000-0001-7167-2179](https://orcid.org/0000-0001-7167-2179)

## Cómo citar

Borrás Rocher, F. y Kanther, A. (2026). *CulturIA* (v1.0.0) [Software]. (DOI en trámite)

## Licencia

MIT. Véase [LICENSE](LICENSE).
