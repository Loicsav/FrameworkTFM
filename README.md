## Framework

El framework es usado para la predicción de perturbaciones genéticas y detección de genes afectados en el contexto de las enfermedades neurodegenerativas.

## Datasets

Los datasets utilizados son los de Adamson y Replogle para replicar el fine-tuning de los autores de [scGPT](https://github.com/bowang-lab/scGPT) para predecir perturbaciones. Para el caso de Adamson contamos con un total de 87 perturbaciones de un solo gen, 68.000 células y 5.060 genes. En Replogle tenemos 1092 perturbaciones, 160.000 células y 5.000 genes. Estos datasets se obtienen de manera automática mediante la librería GEARS.

Para adaptar scGPT a la predicción de perturbaciones genéticas en el contexto de las enfermedades neurodegenerativas se utilizaron los datasets de las bases de datos de [scPerturb](https://projects.sanderlab.org/scperturb/datavzrd/scPerturb_vzrd_v1/dataset_info/index_1.html) con el ID ianKampmann2021 CRISPRa y CRISPRi. En el caso de CRISPRi tenemos 185 perturbaciones de un solo gen y un total de 32.300 células y en CRISPRa tenemos 101 perturbaciones y 21.193 células.

De manera adicional, para realizar una evaluación externa para evaluar la capacidad de generalización del framework utilizamos el dataset GSE183248, obtenido de la base de datos [Gene Expression Omnibus](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE183248) Este dataset cuenta con 4.495 células, 18.097 genes y una única perturbación de la mutación en el gen PINK1.

## Cómo utilizarlo


## Primer vistazo
