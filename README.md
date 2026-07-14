
# BAGP_UNIV_PY

## Conjunto de datos histórico de las Universidades Públicas del Paraguay (2014–2024)

Este repositorio contiene el conjunto de datos desarrollado a partir de los **Balances Anuales de Gestión Pública (BAGP)** de las universidades públicas del Paraguay correspondientes al período **2014–2024**.

El proyecto tiene como objetivo facilitar la reutilización de información oficial mediante un conjunto de datos abierto, documentado y normalizado, acompañado por un tablero interactivo para su exploración.

---

## Estado del conjunto de datos

**Versión actual:** v1.0

**Cobertura temporal:** 2014–2024*

\* La cobertura temporal corresponde a la versión del conjunto de datos disponible al momento de la publicación. El proyecto fue concebido como un recurso abierto y evolutivo; conforme el Ministerio de Economía y Finanzas publique nuevos Balances Anuales de Gestión Pública (BAGP), el conjunto de datos podrá ampliarse incorporando los nuevos períodos sin modificar su estructura general ni la metodología de integración.

---

## Dashboard

El tablero interactivo puede utilizarse directamente desde:

**https://hectorpyco.github.io/BAGP_UNIV_PY_data_viz/**

Enlace corto:

**https://bit.ly/BAGP_viz**

---

## Contenido del repositorio

```
.
├── index.html
├── LICENSE
├── presup_por_univ.csv
├── README.md
├── universidades_py_con_area.csv
│
└── PDF MEF PY/
    ├── BAGP/
    │   ├── bagp 2014/
    │   ├── bagp 2015/
    │   ├── bagp 2016/
    │   ├── bagp 2017/
    │   ├── bagp 2018/
    │   ├── bagp 2019/
    │   ├── bagp 2020/
    │   ├── bagp 2021/
    │   ├── bagp 2022/
    │   ├── bagp 2023/
    │   ├── bagp 2024/
    │   └── bagp 2025/
    │
    └── PGN/
        ├── PGN 2016/
        ├── PGN 2017/
        ├── PGN 2018/
        ├── PGN 2019/
        ├── PGN 2020/
        ├── PGN 2021/
        ├── PGN 2022/
        ├── PGN 2023/
        └── PGN 2024/
```

El repositorio incluye:

- Conjunto de datos consolidado en formato CSV (`universidades_py_con_area.csv` y `presup_por_univ.csv`), en la raíz del repositorio.
- Código fuente completo del tablero interactivo (`index.html`), autocontenido y sin dependencias de build.
- Balances Anuales de Gestión Pública (BAGP) originales utilizados durante el proceso de extracción, organizados por año en `PDF MEF PY/BAGP/`.
- Documentos del Presupuesto General de la Nación (PGN) utilizados como fuente complementaria del presupuesto, organizados por año en `PDF MEF PY/PGN/`.
- Archivo `LICENSE` con el texto completo de la licencia MIT.

> **Nota:** los nombres de archivo de los PDF originales varían año a año (mayúsculas, guiones, sufijos `_0`/`_1`/`_2` por reemplazos de publicación, codificación de caracteres irregular en algunos años de PGN, etc.), ya que se conservan tal como fueron publicados por el Ministerio de Economía y Finanzas, sin renombrarlos, para preservar la trazabilidad hacia la fuente original.

---

# Variables principales

**Archivo:** `universidades_py_con_area.csv`

| Campo | Descripción |
|--------|-------------|
| anho | Año del Balance Anual de Gestión Pública |
| universidad | Universidad pública |
| nivel | G = Grado, P = Posgrado |
| unidad_academica | Facultad, instituto o escuela |
| programa_curso | Carrera o programa |
| area_conocimiento | Área de conocimiento |
| matriculados_m | Mujeres matriculadas |
| matriculados_h | Hombres matriculados |
| matriculados_t | Total de matriculados informado en la fuente |
| egresados_m | Mujeres egresadas |
| egresados_h | Hombres egresados |
| egresados_t | Total de egresados informado en la fuente |
| docentes_m | Mujeres docentes |
| docentes_h | Hombres docentes |
| docentes_t | Total de docentes informado en la fuente |
| total_general | Total general reportado por la institución cuando corresponde |

**Archivo:** `presup_por_univ.csv`

| Campo | Descripción |
|--------|-------------|
| Univ | Universidad pública |
| Anho | Año del Presupuesto General de la Nación (PGN) |
| Presupuesto | Presupuesto institucional asignado, en guaraníes |

> **Nota:** este conjunto de datos está disponible solo desde **2016**, ya que no se identificaron registros de presupuesto anteriores a ese año en las fuentes oficiales relevadas.

---

# Calidad de los datos

La información proviene exclusivamente de documentos oficiales publicados por el Ministerio de Economía y Finanzas.

Durante el proceso de integración se identificaron diferencias en la nomenclatura utilizada para universidades, unidades académicas y programas entre distintos años e instituciones. Estas diferencias fueron normalizadas para favorecer la comparabilidad histórica, preservando en todo momento la trazabilidad hacia la fuente original.

Asimismo, se detectó un número reducido de inconsistencias entre algunos totales reportados y la suma de sus componentes desagregados por sexo. Cuando fue posible verificar el valor correcto mediante la información contenida en el documento original, se corrigieron las variables desagregadas correspondientes. Las columnas terminadas en `_t` se conservan como referencia del valor total informado por la fuente oficial, aunque el tablero interactivo calcula los totales dinámicamente a partir de las variables desagregadas (`_m` y `_h`).

No se realizaron imputaciones estadísticas ni estimaciones para completar información ausente. Cuando un indicador no se encontraba disponible en el documento original, el conjunto de datos conserva dicha ausencia.

---

# Metodología

El conjunto de datos fue construido mediante las siguientes etapas:

1. Recopilación de los BAGP y PGN publicados por el Ministerio de Economía y Finanzas.
2. Extracción de las tablas de interés.
3. Validación manual de los registros.
4. Normalización de nombres de instituciones, unidades académicas y programas.
5. Consolidación del conjunto de datos.
6. Desarrollo del tablero interactivo para la exploración de la información.

---

# Reproducibilidad

Este repositorio contiene los datos utilizados en el artículo científico asociado, junto con el código fuente del tablero interactivo y la documentación necesaria para facilitar la reutilización del conjunto de datos.

---

# Cómo citar

Estigarribia Barreto, H. R. (2026).

**BAGP_UNIV_PY: Conjunto de datos histórico de las Universidades Públicas del Paraguay (2014–2024).**

GitHub.

https://github.com/hectorpyco/BAGP_UNIV_PY_data_viz

---

# Licencia

El código fuente de este proyecto se distribuye bajo la licencia MIT.

Los conjuntos de datos fueron elaborados a partir de documentos públicos publicados por el Ministerio de Economía y Finanzas y otras instituciones oficiales del Paraguay. Se incluyen con fines de investigación, transparencia y reutilización académica, manteniendo la referencia a sus fuentes originales.

---

# Contacto

Héctor R. Estigarribia Barreto
FCyT UNCA, Dirección de investigación
https://github.com/hectorpyco
