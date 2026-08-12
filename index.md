# Bitácora de Aprendizaje: Superando el Desafío de Integración Omnicanal en AURA

## Contexto
Durante el desarrollo del ecosistema omnicanal para AURA (marca de indumentaria premium), diseñamos el sistema *Fast Track Pick-Up*. El objetivo era integrar la tienda web con el stock físico del Showroom Palermo para permitir retiros en tienda en menos de 3 minutos mediante un código QR.

## Problema
En las pruebas de estrés previas al lanzamiento, detectamos un fallo de "stock fantasma": la web permitía vender prendas que acababan de comprarse de forma presencial. Esta desincronización generaba cancelaciones del 12% y demoras en el depósito. Inicialmente, la frustración del equipo provocó sesgos defensivos y bloqueos en la comunicación.

## Acciones (y Post-Mortem Constructivo)
Para solucionar el problema y aplicar una mentalidad de crecimiento ante la falla, realizamos las siguientes acciones:

1. **Análisis Técnico:** Reestructuramos la arquitectura de datos integrando capas de caché en tiempo real (Redis) para evitar la duplicación de ventas.
2. **Post-Mortem Constructivo (Cultura del Error):** Organizamos una sesión de análisis sin búsqueda de culpables (*blameless post-mortem*). Asumí la responsabilidad por haber omitido las pruebas de concurrencia por apurar los plazos de entrega, transformando la falla en un diagnóstico operativo para el equipo.

## Aprendizajes
* **El error como insumo de aprendizaje:** Adoptar una *Mentalidad de Crecimiento* implicó dejar de ver el fallo como un fracaso personal y empezarlo a ver como un indicador claro de dónde debía reforzarse el proceso de integración continua (CI/CD).
* **Comunicación asertiva:** Entendí que la transparencia temprana evita que un problema técnico pequeño se transforme en una crisis de experiencia de usuario (CX) o de empleado (EX).

## Documentación de Control de Versiones

El proceso de iteración y resolución quedó registrado en los siguientes entregables del repositorio:

* **Pull Request #12:** `Fix: Synchronize real-time inventory and add Redis locking` — [Enlace al PR](#)
* **Commit `b3a81f9`:** `Add concurrency tests for checkout system` — [Enlace al Commit](#)
* **Commit `c4d92e1`:** `Update documentation and post-mortem notes` — [Enlace al Commit](#)

## Reflexión: Feedback Radicalmente Sincero (Radical Candor)

Durante la revisión del proyecto, apliqué el principio de **feedback radicalmente sincero** (*Radical Candor*): desafiar directamente cuidando a las personas. 

En lugar de caer en la "empatía ruin" (callar el error por evitar el conflicto) o en la "agresividad ofensiva" (buscar responsables), el equipo me señaló de forma directa y respetuosa la falta de validación en la etapa de testing. Acepté la crítica sin ponerme a la defensiva, comprendiendo que el feedback sobre el trabajo no es un ataque a la capacidad personal. Esta dinámica fortaleció la confianza del grupo, aceleró la búsqueda de soluciones y consolidó una comunicación digital mucho más ágil y honesta.

