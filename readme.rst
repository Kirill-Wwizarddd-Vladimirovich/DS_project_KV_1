===============================================================================
DS_project
===============================================================================

Промышленность
Предсказание конечной температуры сплава
Чтобы оптимизировать производственные расходы, металлургический комбинат ООО «Так закаляем сталь» решил уменьшить потребление электроэнергии на этапе обработки стали. Вам предстоит построить модель, которая предскажет температуру стали.

Описание этапа обработки
Сталь обрабатывают в металлическом ковше вместимостью около 100 тонн. Чтобы ковш выдерживал высокие температуры, изнутри его облицовывают огнеупорным кирпичом. Расплавленную сталь заливают в ковш и подогревают до нужной температуры графитовыми электродами. Они установлены в крышке ковша.

Из сплава выводится сера (десульфурация), добавлением примесей корректируется химический состав и отбираются пробы. Сталь легируют — изменяют её состав — подавая куски сплава из бункера для сыпучих материалов или проволоку через специальный трайб-аппарат (англ. tribe, «масса»).

Перед тем как первый раз ввести легирующие добавки, измеряют температуру стали и производят её химический анализ. Потом температуру на несколько минут повышают, добавляют легирующие материалы и продувают сплав инертным газом. Затем его перемешивают и снова проводят измерения. Такой цикл повторяется до достижения целевого химического состава и оптимальной температуры плавки.

Тогда расплавленная сталь отправляется на доводку металла или поступает в машину непрерывной разливки. Оттуда готовый продукт выходит в виде заготовок-слябов (англ. slab, «плита»).

Описание данных
Данные состоят из файлов, полученных из разных источников:

data_arc.csv — данные об электродах;
data_bulk.csv — данные о подаче сыпучих материалов (объём);
data_gas.csv — данные о продувке сплава газом;
data_temp.csv — результаты измерения температуры;
data_wire.csv — данные о проволочных материалах (объём);
Во всех файлах столбец key содержит номер партии. В файлах может быть несколько строк с одинаковым значением key: они соответствуют разным итерациям обработки.

Getting Started:
-------------------------------------------------------------------------------
- Create virtual environment for development:

.. code::

    $ conda env create -f devenv.yaml

- Activate virtual environment:

.. code::

    $ conda activate cookiecutter

- Install src package in development mode (to solve the import problem, then
  you can use `import src` inside jupyter notebook):

.. code::

    $ conda-develop .

- Set environment variables **(in the root directory!)**. Create and fill out
  in the file `.env` like sample `.env.example`.

Project Organization
-------------------------------------------------------------------------------

.. code::

   ├── README.rst         <- The top-level readme for developers.
   │
   ├── data
   │   ├── external       <- Data from third party sources.
   │   ├── interim        <- Intermediate data that has been transformed.
   │   ├── processed      <- The final, canonical data sets for modeling.
   │   └── raw            <- The original, immutable data dump.
   │
   ├── docs               <- Technical documentation.
   │
   ├── models             <- Trained and serialized models, model predictions,
   │                         or model summaries.
   │
   ├── notebooks          <- Jupyter notebooks. Naming convention is a number
   │                         (for ordering), the creator's initials, and a
   │                         short `-` delimited description, e.g.
   │                         `001.001-jqp-initial-data-exploration`.
   │
   ├── references         <- Data dictionaries, manuals, and all other
   │                         explanatory materials.
   │
   ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
   │   └── figures        <- Generated graphics and figures to be used in
   │                         reporting.
   │
   ├── devenv.yaml        <- The environment file for reproducing the analysis
   │                         environment, e.g. generated with
   │                         `conda env export --from-history > devenv.yaml`
   │
   ├── src                <- Source code for use in this project.
   │   ├── __init__.py    <- Makes src a Python package.
   │   │
   │   ├── data           <- Scripts to download or generate data.
   │   │
   │   ├── features       <- Scripts to turn raw data into features for
   │   │                     modeling.
   │   │
   │   ├── models         <- Scripts to train models and then use trained
   │   │                     models to make predictions.
   │   │
   │   └── reports        <- Scripts to create exploratory reports and results
   │                         oriented visualizations.
   │
   ├── workflow           <- Snakemake workflow storage.
   │   ├── envs           <- Conda environments for snakemake rules.
   │   │   └── default.yaml
   │   │
   │   ├── rules          <- Rules as modules.
   │   │   └── clean.smk
   │   │
   │   ├── scripts        <- Support functions for using in snakemake workflow.
   │   │
   │   ├── config.yaml    <- Parameters for workflow in yaml format.
   │   │
   │   └── Snakefile      <- Entrypoint of the workflow (it will be
   │                         automatically discovered when running snakemake
   │                         from the root of above structure).
   │
   └── .env.example       <- Example of file for environment variables, like
                             MinIO access or Postgresql credentials. It is
                             necessary to create an `.env` file based on it.
