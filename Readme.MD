# Nombre del proyecto

> Breve descripción del propósito del proyecto y su contexto (modifícalo según tus necesidades).

## Tabla de contenidos

1. [Introducción](#introducción)
2. [Fuentes de datos](#fuentes-de-datos)
3. [Descripción de los conjuntos de datos](#descripción-de-los-conjuntos-de-datos)
4. [Cómo utilizar este repositorio](#cómo-utilizar-este-repositorio)
5. [Estructura de carpetas](#estructura-de-carpetas)
6. [Requisitos](#requisitos)
7. [Ejemplos de uso](#ejemplos-de-uso)
8. [Licencia](#licencia)
9. [Contribuciones](#contribuciones)
10. [Autores](#autores)

## Introducción

Este proyecto recopila y analiza información pública disponible en el portal **datos.gov.co** para facilitar iniciativas de transparencia, investigación y visualización de datos. Se utilizan dos fuentes principales: contratos de la plataforma SECOP II y estadísticas de matriculación del Ministerio de Educación Nacional (MEN).

## Fuentes de datos

| Fuente   | Descripción                                                   | Formato | Enlace                                                                                             |
| -------- | ------------------------------------------------------------- | ------- | -------------------------------------------------------------------------------------------------- |
| SECOP II | Datos abiertos de contratación pública en Colombia            | CSV     | [https://www.datos.gov.co/resource/rpmr-utcd.csv](https://www.datos.gov.co/resource/rpmr-utcd.csv) |
| MEN      | Datos de matrícula del sistema educativo oficial y no oficial | CSV     | [https://www.datos.gov.co/resource/nudc-7mev.csv](https://www.datos.gov.co/resource/nudc-7mev.csv) |

> **Nota:** Las URL apuntan directamente a archivos CSV actualizados dinámicamente por datos.gov.co.

## Descripción de los conjuntos de datos

### 1. SECOP II (`rpmr-utcd.csv`)

- **Cobertura:** Contratos registrados por entidades estatales colombianas.
- **Campos habituales:** identificador del proceso, entidad contratante, fecha de publicación, valor estimado, modalidad de contratación, etc.
- **Actualización:** Automática; la información se refresca varias veces al día.

### 2. Matrícula MEN (`nudc-7mev.csv`)

- **Cobertura:** Número de estudiantes matriculados en instituciones oficiales y no oficiales, por nivel educativo y departamento.
- **Campos habituales:** año, periodo, departamento, municipio, sector (oficial/no oficial), nivel educativo, total de alumnos, etc.
- **Actualización:** Anual.

## Cómo utilizar este repositorio

1. **Clonar el proyecto:**
   ```bash
   git clone https://github.com/usuario/tu-repositorio.git
   cd tu-repositorio
   ```
2. **Instalar dependencias (opcional):**
   ```bash
   pip install -r requirements.txt
   ```
3. **Descargar los datos:** Puedes descargarlos manualmente o mediante un script. Por ejemplo:
   ```bash
   curl -o data/secop.csv "https://www.datos.gov.co/resource/rpmr-utcd.csv"
   curl -o data/men.csv "https://www.datos.gov.co/resource/nudc-7mev.csv"
   ```
4. **Ejecutar los notebooks o scripts de análisis** con Jupyter o tu editor de preferencia.

## Estructura de carpetas

```
├── data/              # Archivos CSV y datasets brutos
├── notebooks/         # Notebooks de análisis exploratorio y visualización
├── src/               # Código fuente (funciones, clases, pipelines)
├── docs/              # Documentación adicional y diagramas
├── tests/             # Pruebas unitarias
└── README.md          # Este archivo
```

## Requisitos

- Python ≥ 3.9
- Pandas
- JupyterLab o Jupyter Notebook (recomendado)
- Otras librerías según el archivo `requirements.txt`

## Ejemplos de uso

A continuación se muestra un ejemplo mínimo para cargar los datasets en Python usando **pandas**:

```python
import pandas as pd

url_secop = "https://www.datos.gov.co/resource/rpmr-utcd.csv"
url_men = "https://www.datos.gov.co/resource/nudc-7mev.csv"

# Cargar datos
secop_df = pd.read_csv(url_secop)
men_df = pd.read_csv(url_men)

# Vista rápida
print(secop_df.head())
print(men_df.head())
```

## Licencia

Este proyecto se publica bajo la licencia **MIT**. Consulta el archivo `LICENSE` para más detalles.

## Contribuciones

¡Las contribuciones son bienvenidas! Si deseas mejorar el proyecto, por favor sigue estos pasos:

1. Haz un **fork** del repositorio.
2. Crea tu rama de características (`git checkout -b feature/nueva-funcionalidad`).
3. Realiza tus cambios y haz *commit* (`git commit -m 'Añade nueva funcionalidad'`).
4. Envía un **pull request** detallando tu propuesta.

## Autores

- **Tu Nombre** – *Mantenimiento y documentación* – [@Linafierro1](https://github.com/Linafierro1)

> Si este proyecto te resulta útil, considera darle una ⭐️ en GitHub y compartirlo.
