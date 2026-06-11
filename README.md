## Framework

El framework es usado para la predicción de perturbaciones genéticas y detección de genes afectados en el contexto de las enfermedades neurodegenerativas.

## Datasets

Los datasets utilizados son los de Adamson y Replogle para replicar el fine-tuning de los autores de [scGPT](https://github.com/bowang-lab/scGPT) para predecir perturbaciones. Para el caso de Adamson contamos con un total de 87 perturbaciones de un solo gen, 68.000 células y 5.060 genes. En Replogle tenemos 1092 perturbaciones, 160.000 células y 5.000 genes. Estos datasets se obtienen de manera automática mediante la librería GEARS.

Para adaptar scGPT a la predicción de perturbaciones genéticas en el contexto de las enfermedades neurodegenerativas se utilizaron los datasets de las bases de datos de [scPerturb](https://projects.sanderlab.org/scperturb/datavzrd/scPerturb_vzrd_v1/dataset_info/index_1.html) con el ID ianKampmann2021 CRISPRa y CRISPRi. En el caso de CRISPRi tenemos 185 perturbaciones de un solo gen y un total de 32.300 células y en CRISPRa tenemos 101 perturbaciones y 21.193 células.

De manera adicional, para realizar una evaluación externa para evaluar la capacidad de generalización del framework utilizamos el dataset GSE183248, obtenido de la base de datos [Gene Expression Omnibus](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE183248) Este dataset cuenta con 4.495 células, 18.097 genes y una única perturbación de la mutación en el gen PINK1.

## Cómo utilizarlo

Para empezar, si se quiere realizar el fine-tuning de manera propia es necesario descargarse el modelo scGPT de su repositorio de [Hugging Face](https://huggingface.co/wanglab/scGPT-human/tree/main).

En este [repositorio]([https://huggingface.co/wanglab/scGPT-human/tree/main](https://univmurcia-my.sharepoint.com/:f:/r/personal/manuel_s_d_um_es/Documents/Modelos%20Fine-tuning?csf=1&web=1&e=Zy9a93)) se pueden descargar los modelos con el fine-tuning ya aplicado. Hay modelos entrenados con el dataset de Adamson y otros con el de Tiankampmann utilizando las tecnologías CRISPRi o CRISPRa, todos ellos con distintas estrategias de fine-tuning. Las distintas estrategias fueron utilizar los hiperparámetros orginales del tutorial de fine-tuning de los autores de scGPT, otra fue realizar un cambio de los hiperparámetros, en concreto del weight_decay, el learning rate y el dropout, otra fue realizar un fine-tuning parcial congelando las últimas 6 capas del encoder y la última fue aplicar LoRA al encoder y decoder.

Todos los ficheros necesarios se encuentran en la carpeta `tutorials` donde los ficheros llamados **Tutorial** son los notebooks donde se puede hacer fine-tuning del modelo de scGPT para predecir perturbaciones según el dataset que se le indique. Los ficheros llamados **Parkinson** son los notebooks donde se puede hacer fine-tuning del modelo de scGPT para predecir perturbaciones pero con el dataset de Tiankampmann de genes neuronales.

El fichero Pipeline_Atttention.ipynb es el fichero principal que toma como entrada un conjunto de células control y un gen perturbado y devuelve unas estadísticas sobre el ranking de los 20 DEGs para dicha perturbación junto a un plot y tabla del análisis de enriquecimiento de dicha perturbación. El fichero viene perfectamente comentado con todos los procedimiento que se llevan a cabo.

