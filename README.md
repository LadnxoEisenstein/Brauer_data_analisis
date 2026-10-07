# El Efecto Mateo en Redes de Citación: un análisis mediante Álgebras de Configuración de Brauer

*The Matthew Effect in Citation Networks: an analysis via Brauer Configuration Algebras*

[Español](#español) · [English](#english)

---

## Español

### Resumen

El Efecto Mateo describe el fenómeno de ventaja acumulativa en la ciencia: los trabajos y autores ya reconocidos reciben reconocimiento adicional de manera desproporcionada. Este trabajo traslada el estudio del fenómeno al lenguaje de las álgebras de configuración de Brauer. Se construye una configuración $\Gamma=(M,\mathfrak{m},\mu,O)$ a partir de una red concreta de **17 artículos** y sus **539 referencias**, donde los vértices son los **621 autores citados** y los multiconjuntos son los artículos. Del álgebra $\Lambda_\Gamma$ asociada se extraen tres invariantes:

- la **valencia**, que mide la acumulación individual;
- la **dimensión** $\dim_K\Lambda_\Gamma = 8411$, que mide la concentración global;
- la **entropía** $\mathcal{H}(\Lambda_\Gamma) = 8{,}9085$ bits, que mide la diversidad efectiva.

Se desarrolla en detalle la justificación logarítmica de la entropía y se verifica que el diagrama de Dynkin $\mathbb{A}_n$ realiza el caso de entropía máxima $\mathcal{H}(\Lambda_{\mathbb{A}_n})=\log_2 n$, lo que proporciona el patrón uniforme contra el cual se mide la desigualdad de la red real.

### La configuración

- $M$: los 621 autores citados ($v_1,\dots,v_{621}$, ordenados por valencia).
- $\mathfrak{m}=\{e_1,\dots,e_{17}\}$: los 17 artículos (ver [lista de artículos](#lista-de-artículos--list-of-articles)).
- $\mu(v)=1$ si $\mathrm{val}(v)>1$ y $\mu(v)=2$ si $\mathrm{val}(v)=1$.
- $O$: orden cronológico, $e_i<e_j \iff i<j$.

### Contenido del repositorio

| Archivo | Descripción |
|---|---|
| `Configuracion_Ejercicio_completo_autores_17_articulos_corregido_V2.xlsm` | Libro de Excel con la construcción completa de la configuración. Hojas: `Artículos` (los 17 artículos y sus 539 referencias), `Multiconjuntos`, `M_vertices`, `Sucesores` y `Matriz_occ`. Contiene macros (VBA). |
| `matriz_occ_V2.csv` | Matriz de ocurrencias $\Omega$: una fila por autor y una columna por artículo. $\Omega_{ij}=\mathrm{occ}(v_i,e_j)$ es el número de referencias de $e_j$ en las que aparece $v_i$. Es la entrada del notebook. |
| `dimension_por_vertice.csv` | Por autor: valencia (`val`), multiplicidad (`mu`), producto `val_x_mu` y su aporte a $\dim_K\Lambda_\Gamma$ (`aporte_dim`). |
| `entropia_por_autor.csv` | Por autor: valencia, multiplicidad, número de artículos en que aparece (`n_articulos`), entropía (`H_autor`), entropía relativa (`H_rel`) y diversidad efectiva $2^{H}$ (`dos_a_la_H`). |
| `Carcaj_Brauer_V2.ipynb` | Notebook de Python (Jupyter / Google Colab) que construye el carcaj de Brauer $Q_{\mathfrak{m}}$, dibuja las figuras y calcula las relaciones del ideal, la dimensión y la entropía. |
| `carcaj_val1_agregado.png` | Carcaj de Brauer $Q_{\mathfrak{m}}$ completo ($\mathrm{val}(v)\geq 1$), en modo agregado: las flechas paralelas se funden (grosor = cantidad) y los bucles se resumen con su número. |
| `ciclo_v1.png` … `ciclo_v5.png` | Ciclos especiales $C_v$ de los cinco autores de mayor valencia ($v_1,\dots,v_5$). |

Los archivos CSV usan codificación UTF-8 y coma (`,`) como separador.

### Cómo reproducir los resultados

1. Abre `Carcaj_Brauer_V2.ipynb` en [Google Colab](https://colab.research.google.com/) (*Archivo → Subir notebook*) o en Jupyter.
2. Ejecuta las celdas en orden. En Colab te pedirá subir un archivo: elige `matriz_occ_V2.csv`. En Jupyter, deja el CSV en la misma carpeta que el notebook.
3. Requisitos: Python 3 con `numpy`, `pandas` y `matplotlib`.

El notebook reproduce $|M|=621$, $\sum \mathrm{val}=1083$, $\dim_K\Lambda_\Gamma=8411$ y $\mathcal{H}(\Lambda_\Gamma)=8{,}9085$ bits.

### Autor

**Juan David Gaitán Zamudio**
Programa de Matemáticas, Universidad Distrital Francisco José de Caldas (Bogotá, Colombia).
Trabajo desarrollado en el **Semillero ITENUA**, Semillero de Investigación en Teoría de Números y Álgebra, como parte de un proyecto de investigación en álgebras de configuración de Brauer.

### Cómo citar

> Gaitán Zamudio, J. D. (2026). *El Efecto Mateo en Redes de Citación: un análisis mediante Álgebras de Configuración de Brauer* [Conjunto de datos y código]. GitHub. https://github.com/LadnxoEisenstein/Brauer_data_analisis

### Licencia

Este contenido se distribuye bajo la licencia [Creative Commons Atribución 4.0 Internacional (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/deed.es). Puedes copiarlo, redistribuirlo y adaptarlo, incluso con fines comerciales, siempre que cites la autoría. Consulta el archivo [`LICENSE`](LICENSE).

---

## English

### Abstract

The Matthew Effect describes the phenomenon of cumulative advantage in science: already-recognized works and authors receive disproportionate additional recognition. This work translates the study of this phenomenon into the language of Brauer configuration algebras. A configuration $\Gamma=(M,\mathfrak{m},\mu,O)$ is built from a concrete network of **17 articles** and their **539 references**, where the vertices are the **621 cited authors** and the multisets are the articles. Three invariants are extracted from the associated algebra $\Lambda_\Gamma$:

- the **valency**, which measures individual accumulation;
- the **dimension** $\dim_K\Lambda_\Gamma = 8411$, which measures global concentration;
- the **entropy** $\mathcal{H}(\Lambda_\Gamma) = 8.9085$ bits, which measures effective diversity.

The logarithmic justification of the entropy is developed in detail, and it is verified that the Dynkin diagram $\mathbb{A}_n$ attains the maximum-entropy case $\mathcal{H}(\Lambda_{\mathbb{A}_n})=\log_2 n$, which provides the uniform baseline against which the inequality of the real network is measured.

### The configuration

- $M$: the 621 cited authors ($v_1,\dots,v_{621}$, sorted by valency).
- $\mathfrak{m}=\{e_1,\dots,e_{17}\}$: the 17 articles (see the [list of articles](#lista-de-artículos--list-of-articles)).
- $\mu(v)=1$ if $\mathrm{val}(v)>1$ and $\mu(v)=2$ if $\mathrm{val}(v)=1$.
- $O$: chronological order, $e_i<e_j \iff i<j$.

### Repository contents

| File | Description |
|---|---|
| `Configuracion_Ejercicio_completo_autores_17_articulos_corregido_V2.xlsm` | Excel workbook with the full construction of the configuration. Sheets: `Artículos` (the 17 articles and their 539 references), `Multiconjuntos`, `M_vertices`, `Sucesores` and `Matriz_occ`. Contains macros (VBA). |
| `matriz_occ_V2.csv` | Occurrence matrix $\Omega$: one row per author and one column per article. $\Omega_{ij}=\mathrm{occ}(v_i,e_j)$ is the number of references of $e_j$ in which $v_i$ appears. Input for the notebook. |
| `dimension_por_vertice.csv` | Per author: valency (`val`), multiplicity (`mu`), the product `val_x_mu`, and its contribution to $\dim_K\Lambda_\Gamma$ (`aporte_dim`). |
| `entropia_por_autor.csv` | Per author: valency, multiplicity, number of articles in which the author appears (`n_articulos`), entropy (`H_autor`), relative entropy (`H_rel`), and effective diversity $2^{H}$ (`dos_a_la_H`). |
| `Carcaj_Brauer_V2.ipynb` | Python notebook (Jupyter / Google Colab) that builds the Brauer quiver $Q_{\mathfrak{m}}$, draws the figures, and computes the ideal relations, the dimension and the entropy. |
| `carcaj_val1_agregado.png` | Full Brauer quiver $Q_{\mathfrak{m}}$ ($\mathrm{val}(v)\geq 1$) in aggregated mode: parallel arrows are merged (width = count) and loops are summarized by their number. |
| `ciclo_v1.png` … `ciclo_v5.png` | Special cycles $C_v$ of the five authors with the highest valency ($v_1,\dots,v_5$). |

CSV files are UTF-8 encoded and comma-separated. Column names and code comments are in Spanish.

### How to reproduce the results

1. Open `Carcaj_Brauer_V2.ipynb` in [Google Colab](https://colab.research.google.com/) (*File → Upload notebook*) or in Jupyter.
2. Run the cells in order. Colab will ask you to upload a file: choose `matriz_occ_V2.csv`. In Jupyter, keep the CSV in the same folder as the notebook.
3. Requirements: Python 3 with `numpy`, `pandas` and `matplotlib`.

The notebook reproduces $|M|=621$, $\sum \mathrm{val}=1083$, $\dim_K\Lambda_\Gamma=8411$ and $\mathcal{H}(\Lambda_\Gamma)=8.9085$ bits.

### Author

**Juan David Gaitán Zamudio**
Mathematics Program, Universidad Distrital Francisco José de Caldas (Bogotá, Colombia).
Work carried out at **Semillero ITENUA** (Research Group on Number Theory and Algebra) as part of a research project on Brauer configuration algebras.

### How to cite

> Gaitán Zamudio, J. D. (2026). *El Efecto Mateo en Redes de Citación: un análisis mediante Álgebras de Configuración de Brauer* [Data set and code]. GitHub. https://github.com/LadnxoEisenstein/Brauer_data_analisis

### License

This content is released under the [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) license. You may copy, redistribute and adapt it, including for commercial purposes, as long as you give appropriate credit. See the [`LICENSE`](LICENSE) file.

---

## Lista de artículos / List of articles

| | Artículo / Article |
|---|---|
| $e_1$ | Relationships between the Chicken McNugget Problem, Mutations of Brauer Configuration Algebras and the Advanced Encryption Standard |
| $e_2$ | Building Emerging Images with Tiled Orders and Posets |
| $e_3$ | {0,1}-Brauer Configuration Algebras and Their Applications in Graph Energy Theory |
| $e_4$ | Wargaming with Quadratic Forms and Brauer Configuration Algebras |
| $e_5$ | Categorification of Integer Sequences via Brauer Configuration Algebras and the Four Subspace Problem |
| $e_6$ | Brauer Configuration Algebras Arising from Dyck Paths |
| $e_7$ | Snake Graphs Arising from Groves with an Application in Coding Theory |
| $e_8$ | Cayley Hash Values of Brauer Messages and Some of Their Applications in the Solutions of Systems of Differential Equations |
| $e_9$ | Solutions of the Yang–Baxter Equation Arising from Brauer Configuration Algebras |
| $e_{10}$ | Solutions of the Yang–Baxter Equation and Automaticity Related to Kronecker Modules |
| $e_{11}$ | Seaweeds Arising from Brauer Configuration Algebras |
| $e_{12}$ | An Algebraic Approach to the Solutions of the Open Shop Scheduling Problem |
| $e_{13}$ | Algebraic Structures Induced by the Insertion and Detection of Malware |
| $e_{14}$ | Brauer Analysis of Some Cayley and Nilpotent Graphs and Its Application in Quantum Entanglement Theory |
| $e_{15}$ | Brauer Configuration Algebras Induced by Integer Partitions and Their Applications in the Theory of Branched Coverings |
| $e_{16}$ | Brauer Analysis of Some Time–Memory Trade-Off Attacks and Its Application to the Solution of the Yang–Baxter Equation |
| $e_{17}$ | Brauer Analysis of Thompson's Group F and Its Application to the Solutions of Some Yang–Baxter Equations |

Las referencias completas de cada artículo están en la hoja `Artículos` del archivo Excel. / The full reference lists are in the `Artículos` sheet of the Excel file.
