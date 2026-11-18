Informe NILs
================
David Clapés Gámez
2026-11-18

<img src="Logo_UCO.png" style="width:10.0%" />

<img src="Logo_FacCiencias.png" style="width:10.0%" />

------------------------------------------------------------------------

<!-- Inicio Rmd -->

<!-- Configuración global de los bloques de código, `echo = TRUE` -> todo el código utilizado en este documento aparecerá en el documento final salvo que se expecifique lo contrario, a excepción de este bloque de código, `include=TRUE`  -->

<!-- Para generar títulos, subtítulos etc se usa # el número de # determina el estilo y el formato del texto -->

# Introducción

## El trabajo seleccionado

<!-- Trabajamos los diferentes estilos de text (negrita, cursiva, tachado, superíndice y subíndice), notas a pie de página [^N], citas >  -->

<!-- En HTML podemos usar la etiqueda de css para usar diferentes colores en el texto:  -->

<!-- {style="color:______; font-size:_____;"} -->

Vamos a trabajar con los datos de Pérez-Rial et al. 2024. Este trabajo
describe <span style="color: green;">genes candidatos de la
floración</span> en <span style="color: red;">garbanzo</span> (*Cicer
arietinum*) como ***MED16***, ***BBX24*** o ***ELF3***, este último
también reportado por otros estudios como Rigde et al. 2017. Los
mecanismos básicos de floración estudiados en la planta modelo
*Arabidopsis thaliana* están conservados en las leguminosas (Weller et
al. 2019, Hecht et al. 2005, Weller et al. 2015), exceptuando ciertos
genes como ***CONSTANS*** (Wong et al. 2014)

## Los datos

<!-- Leer los datos desde el fichero que está en la misma carpeta que Rmarkdown. Si el fichero está en otra carpeta actualizar la localización del archivo -->

<!-- Primera vista de los datos -->

| CHROM | POS | ID | REF | ALT | NF10/82-L | NF10/82-E | QUAL | FILTER | INFO | FORMAT |
|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| NC_021160.1 | 72 | . | T | C,G | 0/1 | 1/2 | 2117.19 | PASS | AC=2,1;AF=0.500,0.250;AN=4;ANN=C\|downstream_gene_variant\|MODIFIER\|exon-XR_001143330.2-1\|GENE_exon-XR_001143330.2-1\|transcript\|rna-XR_001143330.2\|pseudogene\|\|n.*169A\>G\|\|\|\|\|169\|,G\|downstream_gene_variant\|MODIFIER\|exon-XR_001143330.2-1\|GENE_exon-XR_001143330.2-1\|transcript\|rna-XR_001143330.2\|pseudogene\|\|n.*169A\>C\|\|\|\|\|169\|,C\|intergenic_region\|MODIFIER\|exon-XR_001143330.2-1\|GENE_exon-XR_001143330.2-1\|intergenic_region\|GENE_exon-XR_001143330.2-1\|\|\|n.72T\>C\|\|\|\|\|\|,G\|intergenic_region\|MODIFIER\|exon-XR_001143330.2-1\|GENE_exon-XR_001143330.2-1\|intergenic_region\|GENE_exon-XR_001143330.2-1\|\|\|n.72T\>G\|\|\|\|\|\|;BaseQRankSum=-3.993e+00;ClippingRankSum=0.00;DP=132;ExcessHet=3.0103;FS=7.468;MLEAC=2,1;MLEAF=0.500,0.250;MQ=42.94;MQRankSum=-2.035e+00;QD=18.74;ReadPosRankSum=1.20;SOR=0.208;SAL5=2;SAL10=2;SAL15=2;SAL20=2;SAL30=2;SAL40=2;SAL50=2 | GT:AD:DP:GQ:PL |
| NC_021160.1 | 126 | . | TA | T | 0/0 | 0/1 | 79.83 | QD2 | AC=1;AF=0.250;AN=4;ANN=T\|downstream_gene_variant\|MODIFIER\|exon-XR_001143330.2-1\|GENE_exon-XR_001143330.2-1\|transcript\|rna-XR_001143330.2\|pseudogene\|\|n.\*114delT\|\|\|\|\|114\|,T\|intergenic_region\|MODIFIER\|exon-XR_001143330.2-1\|GENE_exon-XR_001143330.2-1\|intergenic_region\|GENE_exon-XR_001143330.2-1\|\|\|n.127delA\|\|\|\|\|\|;BaseQRankSum=-1.883e+00;ClippingRankSum=0.00;DP=313;ExcessHet=3.9794;FS=5.326;MLEAC=2;MLEAF=0.500;MQ=56.41;MQRankSum=-5.369e+00;QD=0.66;ReadPosRankSum=-1.808e+00;SOR=0.182;SAL5=2;SAL10=2;SAL15=2;SAL20=2;SAL30=2;SAL40=2;SAL50=2 | GT:AD:DP:GQ:PL |
| NC_021160.1 | 161 | . | G | A | 0/0 | 0/1 | 22.21 | QD2 | AC=1;AF=0.250;AN=4;ANN=A\|downstream_gene_variant\|MODIFIER\|exon-XR_001143330.2-1\|GENE_exon-XR_001143330.2-1\|transcript\|rna-XR_001143330.2\|pseudogene\|\|n.\*80C\>T\|\|\|\|\|80\|,A\|intergenic_region\|MODIFIER\|exon-XR_001143330.2-1\|GENE_exon-XR_001143330.2-1\|intergenic_region\|GENE_exon-XR_001143330.2-1\|\|\|n.161G\>A\|\|\|\|\|\|;BaseQRankSum=3.05;ClippingRankSum=0.00;DP=418;ExcessHet=3.0103;FS=29.583;MLEAC=1;MLEAF=0.250;MQ=53.42;MQRankSum=-4.827e+00;QD=0.13;ReadPosRankSum=2.02;SOR=2.047;SAL5=2;SAL10=2;SAL15=2;SAL20=2;SAL30=2;SAL40=2;SAL50=2 | GT:AD:DP:GQ:PGT:PID:PL |
| NC_021160.1 | 450 | . | G | A | 0/0 | 0/1 | 50.19 | QD2 | AC=1;AF=0.250;AN=4;ANN=A\|intragenic_variant\|MODIFIER\|LOC101497325\|gene-LOC101497325\|gene_variant\|gene-LOC101497325\|\|\|n.450G\>A\|\|\|\|\|\|,A\|non_coding_transcript_exon_variant\|MODIFIER\|exon-XR_001143330.2-1\|GENE_exon-XR_001143330.2-1\|transcript\|rna-XR_001143330.2\|pseudogene\|3/3\|n.310C\>T\|\|\|\|\|\|;BaseQRankSum=3.69;ClippingRankSum=0.00;DP=161;ExcessHet=3.0103;FS=48.565;MLEAC=1;MLEAF=0.250;MQ=56.46;MQRankSum=0.268;QD=0.63;ReadPosRankSum=0.049;SOR=5.892;SAL5=2;SAL10=2;SAL15=2;SAL20=2;SAL30=2;SAL40=2;SAL50=2 | GT:AD:DP:GQ:PL |
| NC_021160.1 | 1942 | . | C | A | 0/1 | 1/1 | 1162.33 | MQ40;map;mrd30 | AC=3;AF=0.750;AN=4;ANN=A\|upstream_gene_variant\|MODIFIER\|exon-XR_001143330.2-1\|GENE_exon-XR_001143330.2-1\|transcript\|rna-XR_001143330.2\|pseudogene\|\|n.-960G\>T\|\|\|\|\|960\|,A\|intergenic_region\|MODIFIER\|exon-XR_001143330.2-1-exon-XR_001143419.2-1\|GENE_exon-XR_001143330.2-1-GENE_exon-XR_001143419.2-1\|intergenic_region\|GENE_exon-XR_001143330.2-1-GENE_exon-XR_001143419.2-1\|\|\|n.1942C\>A\|\|\|\|\|\|;BaseQRankSum=3.03;ClippingRankSum=0.00;DP=61;ExcessHet=3.0103;FS=1.436;MLEAC=3;MLEAF=0.750;MQ=36.83;MQRankSum=-1.360e-01;QD=19.05;ReadPosRankSum=0.477;SOR=0.364;SAL5=2;SAL10=2;SAL15=2;SAL20=2;SAL30=1;SAL40=0;SAL50=0 | GT:AD:DP:GQ:PL |
| NC_021160.1 | 4132 | . | G | T | 0/0 | 0/1 | 89.19 | QD2 | AC=1;AF=0.250;AN=4;ANN=T\|upstream_gene_variant\|MODIFIER\|exon-XR_001143330.2-1\|GENE_exon-XR_001143330.2-1\|transcript\|rna-XR_001143330.2\|pseudogene\|\|n.-3150C\>A\|\|\|\|\|3150\|,T\|intergenic_region\|MODIFIER\|exon-XR_001143330.2-1-exon-XR_001143419.2-1\|GENE_exon-XR_001143330.2-1-GENE_exon-XR_001143419.2-1\|intergenic_region\|GENE_exon-XR_001143330.2-1-GENE_exon-XR_001143419.2-1\|\|\|n.4132G\>T\|\|\|\|\|\|;BaseQRankSum=-5.200e-01;ClippingRankSum=0.00;DP=136;ExcessHet=3.0103;FS=0.000;MLEAC=1;MLEAF=0.250;MQ=57.11;MQRankSum=-6.841e+00;QD=1.27;ReadPosRankSum=-7.000e-02;SOR=0.717;SAL5=2;SAL10=2;SAL15=2;SAL20=2;SAL30=2;SAL40=2;SAL50=2 | GT:AD:DP:GQ:PGT:PID:PL |
| NC_021160.1 | 4147 | . | G | C | 0/0 | 0/1 | 82.19 | QD2 | AC=1;AF=0.250;AN=4;ANN=C\|upstream_gene_variant\|MODIFIER\|exon-XR_001143330.2-1\|GENE_exon-XR_001143330.2-1\|transcript\|rna-XR_001143330.2\|pseudogene\|\|n.-3165C\>G\|\|\|\|\|3165\|,C\|intergenic_region\|MODIFIER\|exon-XR_001143330.2-1-exon-XR_001143419.2-1\|GENE_exon-XR_001143330.2-1-GENE_exon-XR_001143419.2-1\|intergenic_region\|GENE_exon-XR_001143330.2-1-GENE_exon-XR_001143419.2-1\|\|\|n.4147G\>C\|\|\|\|\|\|;BaseQRankSum=0.265;ClippingRankSum=0.00;DP=131;ExcessHet=3.0103;FS=0.000;MLEAC=1;MLEAF=0.250;MQ=57.77;MQRankSum=-6.336e+00;QD=1.23;ReadPosRankSum=-6.480e-01;SOR=0.602;SAL5=2;SAL10=2;SAL15=2;SAL20=2;SAL30=2;SAL40=2;SAL50=2 | GT:AD:DP:GQ:PGT:PID:PL |
| NC_021160.1 | 6539 | . | C | A | 0/1 | 0/0 | 226.19 | PASS | AC=1;AF=0.250;AN=4;ANN=A\|intergenic_region\|MODIFIER\|exon-XR_001143330.2-1-exon-XR_001143419.2-1\|GENE_exon-XR_001143330.2-1-GENE_exon-XR_001143419.2-1\|intergenic_region\|GENE_exon-XR_001143330.2-1-GENE_exon-XR_001143419.2-1\|\|\|n.6539C\>A\|\|\|\|\|\|;BaseQRankSum=1.29;ClippingRankSum=0.00;DP=170;ExcessHet=3.0103;FS=22.385;MLEAC=1;MLEAF=0.250;MQ=57.27;MQRankSum=-6.478e+00;QD=2.41;ReadPosRankSum=-9.470e-01;SOR=4.461;SAL5=2;SAL10=2;SAL15=2;SAL20=2;SAL30=2;SAL40=2;SAL50=2 | GT:AD:DP:GQ:PL |

Tabla 1: Diez primeras filas

<!-- El código R en línea -->

Los datos tienen 120441 filas y 11 columnas.

Cada fila se corresponde con un SNP, por tanto, hay 120441 SNPs.

<!-- cargar las librerias que vamos a utilizar, queremos que el código se ejecute, pero no que aparezca en el documento final, también excluímos los avisos y mensajes -->

<!-- Filtra los datos para quedarte solo con los cromosomas (sus códigos empiezan por NC_) -->

Del total de SNPs detectados, 120441 se corresponden con SNPs situados
en cromosomas (Figura 1).

<!-- Calcula el número de SNPs por cromosoma que tiene el garbanzo con la función `count` y guarda los datos ordenados de forma descendiente en variable nueva -->

<!-- Utilizar la variable nueva para hacer un gráfico de barras incluyendo el pie de figura y la posición -->

<div class="figure" style="text-align: center">

<img src="index_files/figure-gfm/grafico-cromosoma-SNPs-1.png" alt="Figura 1. Número de SNPs por cromosomas" width="60%" />
<p class="caption">

Figura 1. Número de SNPs por cromosomas
</p>

</div>

## Hipótesis

Nuestra hipótesis es que los cromosomas con mayor número de SNPs
presentan mayor % de SNPs que no pasan el filtro de calidad

------------------------------------------------------------------------

# Materiales y Methods

Para llevar a cabo el análisis usamos R con las librerias dplyr y
ggplot.

------------------------------------------------------------------------

# Resultados

<!-- Selecciona del dataset `Data` únicamente las columnas **CHROM**, **POS** y **FILTER**.   -->

<!-- Puedes describir las columnas con las que te quedas.
<!-- Por ejemplo: En CHROM aparecen los diferentes cromosomas del garbanzo, 
<!-- en POS aparecen las posiciones de los SNPs
<!-- detectados y en FILTER aparece el filtro de calidad.
<!-- Los SNPs que pasan el filtro aparecen
<!-- descritos como PASS. -->

<!-- Crea una nueva variable en la que todo valor distinto de *PASS* se transforme en *NOT_PASS*.   -->

## Cálculo de porcentajes por cromosoma

El procentaje de SNPs que no pasan el filtro se muentra en la Tabla 2.

| CHROM       | total_SNPs | not_pass | porcentaje_not_pass |
|:------------|-----------:|---------:|--------------------:|
| NC_021160.1 |      31790 |    16175 |                50.9 |
| NC_021161.1 |       7012 |     5147 |                73.4 |
| NC_021162.1 |       5311 |     4591 |                86.4 |
| NC_021163.1 |       5371 |     4580 |                85.3 |
| NC_021164.1 |       6843 |     5814 |                85.0 |
| NC_021165.1 |      12594 |     8388 |                66.6 |
| NC_021166.1 |       6598 |     5699 |                86.4 |
| NC_021167.1 |       1651 |     1283 |                77.7 |

Tabla 2. Porcentaje de SNPs que pasan y no pasan el filtro por cromosoma

## Representación gráfica

El siguiente modelo muestra la relación entre el número total y los SNPs
no filtrados (Figura 2).

<figure>
<img src="index_files/figure-gfm/grafico-relacion-1.png"
alt="Fig 2. Relación entre el número total de SNPs y el porcentaje de SNPs que no pasan el filtro de calidad" />
<figcaption aria-hidden="true">Fig 2. Relación entre el número total de
SNPs y el porcentaje de SNPs que no pasan el filtro de
calidad</figcaption>
</figure>

------------------------------------------------------------------------

# Conclusiones

Los datos NO apoyan nuestra hipótesis. Es la contraria: los cromosomas
en los que se detectan menos SNPs, presentan mayor porcentaje de SNPs
que no pasan el filtro.

# Bibliografía
