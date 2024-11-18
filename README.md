Algoritmo de Q-Learning para Resolver Laberintos

Este proyecto implementa un agente que utiliza el algoritmo de Q-Learning para encontrar un camino óptimo a través de un laberinto de tamaño 100x100. Q-Learning es un método de aprendizaje por refuerzo que permite a un agente aprender el mejor camino en un entorno desconocido, utilizando recompensas para evaluar la calidad de cada paso. El laberinto es generado aleatoriamente, con obstáculos y una posición objetivo. Este proyecto visualiza tanto el laberinto como el recorrido óptimo encontrado por el agente entrenado.

Objetivo del Proyecto
El objetivo principal es resolver un laberinto complejo usando el aprendizaje por refuerzo. El algoritmo de Q-Learning entrena a un agente para encontrar el camino más corto desde el punto de inicio hasta el objetivo, evitando obstáculos y aprovechando las recompensas asociadas al avance hacia el objetivo. Este proyecto incluye:

La generación de un laberinto aleatorio de tamaño configurable.
Un agente que se entrena con el algoritmo de Q-Learning para encontrar el mejor camino.
Visualización del laberinto y del camino recorrido por el agente.
Descripción del Código
El código está estructurado en diferentes secciones que cumplen funciones específicas para el entrenamiento y la visualización del recorrido del agente en el laberinto.

1. Generación del Laberinto
La función generate_maze crea un laberinto con una configuración de obstáculos y un objetivo. Los obstáculos ocupan aproximadamente el 40% de las celdas del laberinto, y el objetivo se coloca en una celda aleatoria sin obstáculo. El punto de inicio está siempre en la celda (0, 0), y se garantiza un camino despejado entre el inicio y el objetivo para asegurar que exista una solución.

2. Movimientos del Agente
El diccionario ACTIONS define los posibles movimientos del agente (arriba, abajo, izquierda y derecha). La función is_valid_move verifica que el movimiento esté dentro de los límites del laberinto y no se dirija a un obstáculo. La función move ejecuta el movimiento si es válido y devuelve la nueva posición.

3. Entrenamiento con Q-Learning
La función q_learning implementa el algoritmo de Q-Learning, en el cual el agente explora diferentes caminos a través del laberinto y ajusta sus decisiones en base a recompensas. Para cada posición y movimiento, la Q-Table almacena el valor estimado de la recompensa. El agente explora al principio, pero conforme aprende, se enfoca en las decisiones que maximizan la recompensa. Este proceso se repite por un número configurado de episodios para que el agente aprenda el camino óptimo.

4. Evaluación del Agente
La función evaluate evalúa el desempeño del agente en el laberinto usando la Q-Table entrenada. A partir del inicio, el agente sigue el camino sugerido por la Q-Table hasta llegar al objetivo, y se guarda este recorrido.

5. Visualización del Recorrido
La función visualize_path muestra una visualización del laberinto, resaltando el camino encontrado por el agente desde el inicio hasta el objetivo. El laberinto y el recorrido se visualizan con un mapa de colores que permite identificar obstáculos, el objetivo y el camino recorrido.
