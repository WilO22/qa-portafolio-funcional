# Glosario Personal - Módulo 1: Fundamentos del Testing

Términos base del Módulo 1 (ISTQB CTFL v4.0) explicados con mis propias palabras y ejemplos prácticos.

1. **Testing de software**
   * **Qué es:** No es solo hacer clic buscando errores; es todo el conjunto de actividades que hacemos para evaluar qué tan bien hecho está un software y bajar el riesgo de que falle cuando llegue a producción. Incluye leer requisitos, diseñar casos, preparar datos, ejecutar y reportar.
   * **Ejemplo:** Antes de lanzar una tienda online, reviso las reglas de compra, armo mis escenarios de prueba, pruebo el carrito y reporto lo que falle antes de que los clientes reales entren.

2. **Debugging (depuración)**
   * **Qué es:** Es el trabajo que hace el desarrollador para meterse al código, encontrar por qué falló algo y corregirlo. El QA encuentra y reporta (testing), el dev corrige (debugging) y luego el QA vuelve a comprobar (retest).
   * **Ejemplo:** Reporto que el filtro de precios de SauceDemo no ordena; el programador entra al código JavaScript, encuentra el error en la función de ordenamiento y lo arregla.

3. **Error (equivocación)**
   * **Qué es:** Es la equivocación humana. Puede pasar porque alguien entendió mal una regla del negocio o simplemente porque se distrajo y escribió mal algo al programar.
   * **Ejemplo:** El desarrollador entiende mal la regla de mayoría de edad y piensa que solo entran mayores de 18 sin incluir el 18, o se equivoca al teclear un signo.

4. **Defecto (bug)**
   * **Qué es:** Es la imperfección concreta que queda escrita dentro del código, en un requisito o en un documento como consecuencia de un error humano. Puede estar ahí escondido sin fallar si nadie pasa por esa parte.
   * **Ejemplo:** En el código queda escrito `edad > 18` en lugar de `edad >= 18`.

5. **Falla**
   * **Qué es:** Es el problema real que yo veo en la pantalla cuando se ejecuta ese defecto y el sistema hace algo distinto a lo que debería.
   * **Ejemplo:** Intento registrar a una persona que tiene exactamente 18 años y el sistema la rechaza.

6. **Causa raíz**
   * **Qué es:** Es el motivo de fondo que terminó provocando el error humano desde el inicio.
   * **Ejemplo:** La historia de usuario era confusa y nadie se sentó a aclararla antes de empezar a programar.

7. **QA (Quality Assurance / Aseguramiento de la calidad)**
   * **Qué es:** Tiene un enfoque preventivo y mira el proceso de trabajo. Busca que el equipo siga buenas prácticas, estándares y revisiones para evitar que entren tantos bugs desde el principio.
   * **Ejemplo:** Definir una lista de verificación obligatoria para revisar cada historia de usuario antes de que los devs escriban código.

8. **QC (Quality Control / Control de calidad)**
   * **Qué es:** Tiene un enfoque correctivo y mira directamente el producto ya construido para comprobar si cumple lo esperado. El testing es su actividad principal.
   * **Ejemplo:** Probar la pantalla de login y el catálogo de SauceDemo para detectar si hay fallas antes de liberar la versión.

9. **Principio de presencia de defectos (no ausencia)**
   * **Qué es:** Probar sirve para demostrar que existen bugs, pero nunca puede garantizar al 100% que un sistema no tiene ninguno.
   * **Ejemplo:** Con `standard_user` todo funcionó bien en SauceDemo, pero eso no significaba que la web estuviera libre de bugs; al entrar con `problem_user` salieron varios.

10. **Imposibilidad de pruebas exhaustivas**
    * **Qué es:** Es imposible probar todas las combinaciones posibles de datos, clics, navegadores y celulares. Por eso usamos técnicas de diseño y priorizamos por riesgo.
    * **Ejemplo:** En un formulario de transferencias no puedo probar monto por monto desde S/ 1 hasta S/ 10,000; elijo casos clave y los límites.

11. **Shift-left testing (probar temprano)**
    * **Qué es:** Empezar a revisar y cuidar la calidad lo antes posible en el proyecto, en vez de esperar a que todo esté programado al final. Ahorra tiempo y dinero.
    * **Ejemplo:** Detectar una contradicción en los criterios de aceptación durante el refinamiento, antes de que el dev pierda dos días programándolo mal.

12. **Agrupación de defectos (Principio de Pareto)**
    * **Qué es:** Por lo general, la mayoría de los bugs no están repartidos por igual, sino concentrados en unos pocos módulos más complejos o tocados seguido.
    * **Ejemplo:** En SauceDemo con `problem_user`, casi todos los problemas (imágenes repetidas, filtro roto, enlaces cruzados) se juntaron en la pantalla del catálogo.

13. **Paradoja del pesticida**
    * **Qué es:** Igual que los insectos se acostumbran al mismo veneno, si siempre ejecuto exactamente las mismas pruebas, llega un punto en que ya no encuentran bugs nuevos. Hay que actualizar casos y variar datos.
    * **Ejemplo:** Si siempre pruebo el login solo con el mismo usuario válido y la misma clave, nunca voy a descubrir problemas con espacios, usuarios bloqueados o caracteres raros.

14. **Testing dependiente del contexto**
    * **Qué es:** No todos los proyectos se prueban igual; la profundidad y el enfoque cambian según el tipo de sistema y su impacto.
    * **Ejemplo:** Una app bancaria que mueve dinero necesita pruebas muy estrictas de seguridad y concurrencia, mucho más que una página informativa simple.

15. **Falacia de la ausencia de defectos**
    * **Qué es:** Creer que un software es un éxito solo porque no tiene bugs. Si el sistema no sirve para lo que el usuario necesita, igual fracasa.
    * **Ejemplo:** Una tienda online que no tiene ningún error técnico, pero cuyo proceso de pago tiene 12 pasos confusos y hace que la gente abandone la compra.

16. **Base de prueba**
    * **Qué es:** Toda la información o documentos en los que me apoyo para saber qué debe hacer exactamente el sistema.
    * **Ejemplo:** Historias de usuario, criterios de aceptación, diseños en Figma, reglas de negocio o la documentación de una API.

17. **Testware**
    * **Qué es:** Todo el material que voy generando durante mi trabajo de pruebas.
    * **Ejemplo:** Mi plan de pruebas, mis casos de prueba en Excel, mis datos de prueba, los scripts automatizados y los informes finales.

18. **Condición de prueba**
    * **Qué es:** Un punto o aspecto concreto que necesito probar, identificado durante la etapa de análisis. Responde al "qué" voy a probar.
    * **Ejemplo:** "Validar el inicio de sesión con usuario bloqueado" o "Probar el ordenamiento por precio".

19. **Caso de prueba**
    * **Qué es:** El detalle paso a paso que creo en la etapa de diseño para probar una condición: incluye precondiciones, datos, pasos y el resultado esperado. Responde al "cómo" probar.
    * **Ejemplo:** Paso 1: entrar a saucedemo.com; Paso 2: poner `locked_out_user` y `secret_sauce`; Paso 3: clic en Login → Resultado esperado: mensaje de usuario bloqueado.

20. **Prueba de componente (unitaria)**
    * **Qué es:** Nivel de prueba donde se revisa una sola pieza chiquita del código aislada del resto (una función, clase o método). Normalmente la hace el desarrollador.
    * **Ejemplo:** El dev prueba únicamente la función que calcula el IGV (18%) de un monto, sin abrir pantallas ni conectarse a la base de datos.

21. **Prueba de integración de componentes**
    * **Qué es:** Nivel donde se prueba cómo conversan dos o más piezas internas dentro de la misma aplicación. La hacen devs o QA.
    * **Ejemplo:** Comprobar que el componente del catálogo le pase bien el ID del producto seleccionado al componente del carrito.

22. **Prueba de sistema**
    * **Qué es:** Nivel donde el QA prueba la aplicación completa de punta a punta contra los requisitos, como la usaría una persona real.
    * **Ejemplo:** Probar en SauceDemo todo el recorrido: iniciar sesión, ordenar productos, entrar al detalle, agregar al carrito y cerrar sesión.

23. **Prueba de integración de sistemas**
    * **Qué es:** Nivel a cargo del QA donde se valida que nuestra aplicación interactúe bien con sistemas externos que no construimos nosotros.
    * **Ejemplo:** Probar que nuestra tienda web envíe correctamente el monto a una pasarela de pagos externa o consulte un servicio externo como RENIEC y reciba la respuesta esperada.

24. **Prueba de aceptación (UAT)**
    * **Qué es:** Nivel enfocado en confirmar que el sistema cumple con lo que necesita el negocio y el usuario final. Participa el usuario/negocio junto con QA.
    * **Ejemplo:** Antes de salir a producción, el cliente prueba los flujos principales de su tienda para dar el visto bueno formal.

25. **Pruebas Alfa y Beta**
    * **Qué es:** Formas de prueba de aceptación. La Alfa se hace en un ambiente controlado dentro de la propia empresa creadora; la Beta la prueban usuarios reales afuera en sus propios dispositivos.
    * **Ejemplo:** Lanzar una versión de prueba (beta) de una app móvil a un grupo pequeño de clientes reales en Android antes de publicarla para todos.

26. **Prueba funcional**
    * **Qué es:** Evalúa *qué hace* el sistema: sus flujos, botones, reglas de negocio y cálculos.
    * **Ejemplo:** Verificar que al agregar dos productos al carrito, la suma total coincida con el precio de ambos.

27. **Prueba no funcional**
    * **Qué es:** Evalúa *cómo lo hace* el sistema, usando características como rendimiento, seguridad, usabilidad, compatibilidad o fiabilidad (ISO/IEC 25010).
    * **Ejemplo:** Medir que la página de inicio cargue en menos de 2 segundos aunque haya 200 usuarios entrando al mismo tiempo.

28. **Prueba de caja negra**
    * **Qué es:** Probar el software mirando solo lo que entra y lo que sale según las reglas de negocio, sin ver ni tocar el código por dentro.
    * **Ejemplo:** Probar `problem_user` en SauceDemo haciendo clic en la pantalla y revisando qué responde, sin abrir el código fuente.

29. **Prueba de caja blanca**
    * **Qué es:** Probar mirando la estructura interna del código, sus condicionales y rutas para asegurar que las líneas se ejecuten bien.
    * **Ejemplo:** Un programador revisa un `if/else` dentro de su clase Java y escribe pruebas para pasar tanto por el camino verdadero como por el falso.

30. **Prueba de confirmación (Retest)**
    * **Qué es:** Volver a ejecutar los mismos pasos de un bug que reporté, después de que el dev lo corrigió, solo para confirmar que ya dejó de fallar.
    * **Ejemplo:** Si arreglan las fotos repetidas del perro en `problem_user`, entro de nuevo con ese usuario para confirmar que ahora sí salen las fotos correctas de cada producto.

31. **Prueba de regresión**
    * **Qué es:** Volver a probar funcionalidades que ya estaban bien para asegurarnos de que un cambio nuevo o una corrección no rompió otra cosa por accidente.
    * **Ejemplo:** Después de arreglar el filtro de precios, vuelvo a probar que el login y el botón de agregar al carrito sigan funcionando normal.

32. **Smoke test (prueba de humo)**
    * **Qué es:** Prueba rápida, amplia y superficial de las funciones más críticas cada vez que llega un nuevo build. Sirve para decidir si la versión es estable para seguir probando.
    * **Ejemplo:** Apenas despliegan una nueva versión de la web, pruebo rápido login, ver productos y logout antes de arrancar con pruebas largas.

33. **Sanity test (prueba de cordura)**
    * **Qué es:** Prueba rápida pero angosta y más profunda sobre una funcionalidad puntual que acaba de cambiar o corregirse, para confirmar si tiene sentido hacer pruebas completas ahí.
    * **Ejemplo:** Si solo modificaron el cálculo del descuento en el carrito, pruebo a fondo varios escenarios de ese descuento antes de correr toda la regresión.

34. **Pruebas estáticas vs. dinámicas (y revisiones)**
    * **Qué es:** En las pruebas estáticas revisamos documentos o código *sin ejecutar* el software (con revisiones que van de menos a más formal: informal, walkthrough guiado por el autor, revisión técnica e inspección). En las dinámicas *sí ejecutamos* la aplicación.
    * **Ejemplo:** Revisar en equipo una historia de usuario en un walkthrough antes de programar es prueba estática; entrar a `saucedemo.com` y probar los botones es prueba dinámica.

35. **Verificación vs. Validación**
    * **Qué es:** Verificar es preguntarnos *"¿estamos construyendo el producto correctamente?"* (cumple exactamente lo que dice la especificación). Validar es preguntarnos *"¿estamos construyendo el producto correcto?"* (realmente resuelve lo que necesita el usuario).
    * **Ejemplo:** Comprobar que un formulario cumple el límite de caracteres del documento es verificación; confirmar con el cliente que ese formulario le permite registrar pedidos sin trabarse es validación.
