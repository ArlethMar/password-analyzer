Analizador de Seguridad de Contraseñas en Tiempo Real

Herramienta web interactiva diseñada para evaluar la robustez de contraseñas mediante análisis combinatorio, cálculo de entropía en bits y estimación de resistencia frente a ataques de fuerza bruta.

Demo en vivo: [Ver aplicación en GitHub Pages](https://arlethmar.github.io/password-analyzer/)

---
Objetivo del Proyecto:

Demostrar de forma práctica y visual cómo el crecimiento exponencial del espacio de búsqueda ($R^L$) impacta directamente en el tiempo de cómputo necesario para vulnerar una credencial mediante fuerza bruta.

---
 Funcionalidades Principales:

* **Evaluación en tiempo real:** Análisis instantáneo carácter por carácter sin latencia ni envío de datos a servidores externos (100% *client-side*).
* **Cálculo de espacio de búsqueda ($R^L$):** Determina dinámicamente el tamaño del alfabeto activo ($R$) según los conjuntos de caracteres detectados (minúsculas, mayúsculas, números y símbolos) y su longitud ($L$).
* **Medición de entropía:** Calcula la incertidumbre criptográfica en bits mediante $E = L \cdot \log_2(R)$.
* **Estimación de fuerza bruta:** Proyecta el tiempo promedio de descifrado asumiendo un escenario de ataque moderno por GPU de $10^{10}$ intentos por segundo.
* **Detección de patrones débiles:** Identifica contraseñas comunes de diccionario y repeticiones consecutivas de caracteres.
* **Generador criptográficamente seguro:** Utiliza la API nativa `window.crypto.getRandomValues()` para generar credenciales aleatorias de 16 caracteres de alta entropía.

---
Fundamento Matemático y Complejidad

1. Espacio de búsqueda (Ataque de fuerza bruta):
   Combinaciones = R^L$$
   Donde $R \in [26, 94]$ representa el conjunto de caracteres posibles y $L$ la longitud de la contraseña. Un atacante de fuerza bruta enfrenta una complejidad temporal exponencial **$O(R^L)$** en el peor de los casos.

2. Eficiencia del analizador:
   La evaluación de reglas mediante expresiones regulares y el cálculo de métricas se ejecutan en tiempo lineal **$O(L)$** respecto a la longitud de la cadena ingresada, con espacio auxiliar constante **$O(1)$**.

---
Tecnologías Utilizadas:

* **HTML5:** Estructura semántica de la interfaz.
* **CSS3:** Diseño responsivo con variables CSS y transiciones dinámicas.
* **JavaScript (ES6+):** Lógica de análisis combinatorio, expresiones regulares y Web Crypto API.

---
Ejecución Local

No requiere instalación de dependencias ni servidores externos:

1. Clona este repositorio:
   ```bash
   git clone [https://github.com/arlethmar/password-analyzer.git](https://github.com/arlethmar/password-analyzer.git)
