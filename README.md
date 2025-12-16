Proyecto de Santiago Ocampo

Perceptrón Multicapa (MLP) desde Cero: Análisis Algorítmico y Optimización

Descripción del Proyecto

Implementación completa de un Perceptrón Multicapa (MLP) sin frameworks de alto nivel, con énfasis en:

Análisis de complejidad temporal y espacial (Big-O)

Estructuras de datos eficientes (Heap, QuickSelect, Hash)

Forward Pass y Backpropagation implementados manualmente

Optimización con Stochastic Gradient Descent (SGD)


Fases de Desarrollo

Fase 1: Fundamentos (RA1)

Red neuronal mínima con 1 capa oculta

Derivación de complejidad: O(n·h + h·k)

Experimentos de escalado (B, h, E)

Análisis empírico vs teórico


Fase 2: Estructuras de Datos (RA2)

QuickSelect para búsqueda de mediana

Heap para top-k elementos

Hard mining para selección inteligente de muestras

Validación con Método Maestro


Fase 3: Integración Avanzada (RA3)

Cola de lotes optimizada

Hash table para caché de pérdidas

Heap/BST para poda de ejemplos

Métricas de impacto en tiempo y memoria


Características Principales

✨ Sistema Interactivo de Retroalimentación (MEJORADO v2):

✓ Generación de dígitos sintéticos MÁS REALISTA (stroke-based)

✓ Entrenamiento acelerado (8 muestras/épocas iniciales)

✓ Learning rate aumentado a 0.8 para convergencia más rápida

✓ Normalización mejorada de entrada (center of mass + contraste)

✓ Botones CORRECTO/INCORRECTO siempre disponibles

✓ Reentrenamiento automático con correcciones (3x por sample)

✓ Historial persistente y búsqueda visual clara


Arquitectura

INPUT (784 píxeles)
    ↓
CAPA OCULTA (32 neuronas) - O(784·32) = O(25,088)
    ↓
CAPA SALIDA (10 clases) - O(32·10) = O(320)
    ↓
PREDICCIÓN + BACKPROP - O(n·h + h·k)

Complejidad Algorítmica

Forward Pass: O(n·h + h·k) = O(25,408)

n = 784 píxeles, h = 32 neuronas ocultas, k = 10 salidas

Multiplicación de matrices: O(784·32) + O(32·10) = O(25,408)

Activación sigmoid: O(32) + O(10)


Backpropagation: O(n·h + h·k)

Cálculo de gradientes: O(32·10) + O(784·32)

Actualización de pesos: O(784·32 + 32·10)


Memoria: ≈110 KB

Pesos entrada–oculta: 784·32·4 bytes = 100 KB

Pesos oculta–salida: 32·10·4 bytes = 1.28 KB

Sesgos e historial: ~8 KB


Estructuras de Datos

Heap (Top-K Selection)

Complejidad: O(n log k)

Caso de uso: Seleccionar top-k muestras con mayor error

Ventaja vs sort: O(n log k) vs O(n log n)


QuickSelect (Mediana)

Complejidad promedio: O(n)

Complejidad peor caso: O(n²)

Caso de uso: Encontrar umbral de pérdida mediana


Hash Table (Caché)

Inserción/búsqueda: O(1) promedio

Caso de uso: Caché de pérdidas calculadas


Criterios de Evaluación

✓ Correctitud: >85% de precisión en validación
✓ Complejidad: Derivaciones Big-O verificadas
✓ Estructuras: Implementaciones justificadas con datos
✓ Recurrencias: Método Maestro aplicado correctamente
✓ Experimentos: Gráficos de escalado (tiempo vs n, B, h)

Cómo Ejecutar

# Instalar dependencias
npm install

# Ejecutar en desarrollo
npm run dev:client

# Visitar http://localhost:5000

Resultados Esperados

La red aprende patrones en <50 épocas

La pérdida (MSE) converge a <0.1

La precisión alcanza ~90% en validación

Tiempo por época: <100 ms en navegador


Archivos Clave

src/lib/mlp.ts – Implementación de la red neuronal

src/lib/algorithms.ts – Heap, QuickSelect, estructuras

src/pages/neural-lab.tsx – Interfaz interactiva

src/lib/python-generator.ts – Equivalente en Python


Referencias

Big-O: T(n) = aT(n/b) + f(n) → Método Maestro

SGD: Actualización: w = w − η∇L

Backprop: δ = (y − ŷ) ⊙ σ'(z)

Sigmoid: σ(x) = 1 / (1 + e⁻ˣ)



---

Autor: Santiago Ocampo
Asignatura: Análisis y Diseño de Algoritmos 1
Fecha: 2025-12-16
