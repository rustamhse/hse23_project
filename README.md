# Изучение ранней эволюции белков, выполняющих различные эпигенетические модификации в клетках человека, с помощью методов сравнительной геномики
- Зиёев Рустам группа 3
- Белок - BAHD1, метка - H3K27me
- Колаб - https://colab.research.google.com/drive/1WzYYnLDMbF9O073g8BxxUgnYkaFmFEKH#scrollTo=ECK9LBXTUUtt

BAHD1 играет важную роль в регуляции жирового метаболизма, контроле набора и потери веса, а также в защите клеток от стресса и возможного развития рака. Кроме того, недавние исследования показывают, что BAHD1 может оказывать влияние на дифференцировку клеток, транскрипционную регуляцию, уровень транскрипции генов и другие важные биологические процессы.

Экспрессия
![image](https://github.com/rustamhse/hse23_project/assets/74643940/98c103cb-6a51-4a14-8a67-752dc4f7f190)

## Ход работы

1. С помощью геномного браузера ucsc получил fasta-последовательность.  
![image](https://github.com/rustamhse/hse23_project/assets/74643940/7d1c611e-d501-4e7c-b738-0f58f4cb6179)
![image](https://github.com/rustamhse/hse23_project/assets/74643940/6b827349-4bb0-4600-b65b-32f34015cbbd)


2. Загрузил файл на сервер, создал fasta файл с помощью *touch bahd1.fasta && nano bahd1.fasta*, далее выполнил следующий ряд команд:

```
1. blastp  -query bahd1.fasta  -db /mnt/storage/project_2023/proteomes/c.elegans.faa  -out c.elegans.blast  -outfmt 7
2. blastp  -query bahd1.fasta  -db /mnt/storage/project_2023/proteomes/ciliate.faa  -out ciliate.blast  -outfmt 7
3. blastp  -query bahd1.fasta  -db /mnt/storage/project_2023/proteomes/drosophila.faa  -out drosophila.blast  -outfmt 7
4. blastp  -query bahd1.fasta  -db /mnt/storage/project_2023/proteomes/e.coli.faa  -out e.coli.blast  -outfmt 7
5. blastp  -query bahd1.fasta  -db /mnt/storage/project_2023/proteomes/human.faa  -out human.blast  -outfmt 7
6. blastp  -query bahd1.fasta  -db /mnt/storage/project_2023/proteomes/methanocaldococcus.faa  -out methanocaldococcus.blast  -outfmt 7
7. blastp  -query bahd1.fasta  -db /mnt/storage/project_2023/proteomes/mouse.faa  -out mouse.blast  -outfmt 7
8. blastp  -query bahd1.fasta  -db /mnt/storage/project_2023/proteomes/thermococcus.faa  -out thermococcus.blast  -outfmt 7
9. blastp  -query bahd1.fasta  -db /mnt/storage/project_2023/proteomes/tuberculosis.faa  -out tuberculosis.blast  -outfmt 7
10. blastp  -query bahd1.fasta  -db /mnt/storage/project_2023/proteomes/yeast.faa  -out yeast.blast  -outfmt 7
11. blastp  -query bahd1.fasta  -db /mnt/storage/project_2023/proteomes/zebrafish.faa  -out zebrafish.blast  -outfmt 7
```

![image](https://github.com/rustamhse/hse23_project/assets/74643940/e337afb8-bc88-4361-b4d5-202df222309b)

3. Выполнил выравнивание последовательностей гистонов

![image](https://github.com/rustamhse/hse23_project/assets/74643940/7f76ed4e-defc-4267-9110-5cf53d522fac)

4. Запустил blastp для каждого из гистонов

```
Рустам Зиёев, [06.06.2023 00:01]
blastp -query /mnt/storage/project_2023/histones/H2A.fasta -db /mnt/storage/project_2023/proteomes/c.elegans.faa -out H2A.c.elegans.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H2A.fasta -db /mnt/storage/project_2023/proteomes/ciliate.faa -out H2A.ciliate.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H2A.fasta -db /mnt/storage/project_2023/proteomes/drosophila.faa -out H2A.drosophila.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H2A.fasta -db /mnt/storage/project_2023/proteomes/e.coli.faa -out H2A.e.coli.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H2A.fasta -db /mnt/storage/project_2023/proteomes/human.faa -out H2A.human.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H2A.fasta -db /mnt/storage/project_2023/proteomes/methanocaldococcus.faa -out H2A.methanocaldococcus.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H2A.fasta -db /mnt/storage/project_2023/proteomes/mouse.faa -out H2A.mouse.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H2A.fasta -db /mnt/storage/project_2023/proteomes/thermococcus.faa -out H2A.thermococcus.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H2A.fasta -db /mnt/storage/project_2023/proteomes/tuberculosis.faa -out H2A.tuberculosis.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H2A.fasta -db /mnt/storage/project_2023/proteomes/yeast.faa -out H2A.yeast.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H2A.fasta -db /mnt/storage/project_2023/proteomes/zebrafish.faa -out H2A.zebrafish.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H2B.fasta -db /mnt/storage/project_2023/proteomes/c.elegans.faa -out H2B.c.elegans.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H2B.fasta -db /mnt/storage/project_2023/proteomes/ciliate.faa -out H2B.ciliate.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H2B.fasta -db /mnt/storage/project_2023/proteomes/drosophila.faa -out H2B.drosophila.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H2B.fasta -db /mnt/storage/project_2023/proteomes/e.coli.faa -out H2B.e.coli.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H2B.fasta -db /mnt/storage/project_2023/proteomes/human.faa -out H2B.human.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H2B.fasta -db /mnt/storage/project_2023/proteomes/methanocaldococcus.faa -out H2B.methanocaldococcus.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H2B.fasta -db /mnt/storage/project_2023/proteomes/mouse.faa -out H2B.mouse.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H2B.fasta -db /mnt/storage/project_2023/proteomes/thermococcus.faa -out H2B.thermococcus.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H2B.fasta -db /mnt/storage/project_2023/proteomes/tuberculosis.faa -out H2B.tuberculosis.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H2B.fasta -db /mnt/storage/project_2023/proteomes/yeast.faa -out H2B.yeast.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H2B.fasta -db /mnt/storage/project_2023/proteomes/zebrafish.faa -out H2B.zebrafish.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H3.fasta -db /mnt/storage/project_2023/proteomes/c.elegans.faa -out H3.c.elegans.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H3.fasta -db /mnt/storage/project_2023/proteomes/ciliate.faa -out H3.ciliate.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H3.fasta -db /mnt/storage/project_2023/proteomes/drosophila.faa -out H3.drosophila.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H3.fasta -db /mnt/storage/project_2023/proteomes/e.coli.faa -out H3.e.coli.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H3.fasta -db /mnt/storage/project_2023/proteomes/human.faa -out H3.human.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H3.fasta -db /mnt/storage/project_2023/proteomes/methanocaldococcus.faa -out H3.methanocaldococcus.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H3.fasta -db /mnt/storage/project_2023/proteomes/mouse.faa -out H3.mouse.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H3.fasta -db /mnt/storage/project_2023/proteomes/thermococcus.faa -out H3.thermococcus.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H3.fasta -db /mnt/storage/project_2023/proteomes/tuberculosis.faa -out H3.tuberculosis.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H3.fasta -db /mnt/storage/project_2023/proteomes/yeast.faa -out H3.yeast.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H3.fasta -db /mnt/storage/project_2023/proteomes/zebrafish.faa -out H3.zebrafish.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H4.fasta -db /mnt/storage/project_2023/proteomes/c.elegans.faa -out H4.c.elegans.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H4.fasta -db /mnt/storage/project_2023/proteomes/ciliate.faa -out H4.ciliate.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H4.fasta -db /mnt/storage/project_2023/proteomes/drosophila.faa -out H4.drosophila.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H4.fasta -db /mnt/storage/project_2023/proteomes/e.coli.faa -out H4.e.coli.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H4.fasta -db /mnt/storage/project_2023/proteomes/human.faa -out H4.human.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H4.fasta -db /mnt/storage/project_2023/proteomes/methanocaldococcus.faa -out H4.methanocaldococcus.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H4.fasta -db /mnt/storage/project_2023/proteomes/mouse.faa -out H4.mouse.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H4.fasta -db /mnt/storage/project_2023/proteomes/thermococcus.faa -out H4.thermococcus.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H4.fasta -db /mnt/storage/project_2023/proteomes/tuberculosis.faa -out H4.tuberculosis.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H4.fasta -db /mnt/storage/project_2023/proteomes/yeast.faa -out H4.yeast.blast -outfmt 7 &&
blastp -query /mnt/storage/project_2023/histones/H4.fasta -db /mnt/storage/project_2023/proteomes/zebrafish.faa -out H4.zebrafish.blast -outfmt 7
```
5. Составил таблицу с полями e-value для каждого белка и организма

|    Protein    |   Human  |  Mouse   | Zebrafish | C.elegans | Drosophila |  Ciliate  |   Yeast   | Methanocaldococcus | Thermococcus |  E.coli  | Tuberculosis |
|:-------------:|:--------:|:--------:|:---------:|:---------:|:----------:|:--------:|:---------:|:------------------:|:-----------:|:--------:|:------------:|
|      H4       | 1.09e-67 | 7.6e-68  | 1.13e-68 | 6.15e-68  | 8.02e-68   | 1.96e-45 | 1.08e-52  |       0.000082     |   0.000033  |    1.3   |     0.069    |
|      H3       | 2.19e-96 | 1.54e-96 | 1.77e-95 | 4.46e-94  | 9.39e-96   | 8.41e-86 | 3.31e-87  |        0.034        |    0.057    |    0.9   |      4.6     |
|      H2B      | 2.85e-87 | 1.15e-83 | 1.85e-71 | 5.28e-65  | 3.3e-59    | 1.91e-49 | 3.07e-57  |         2.6         |    0.17     |    1.8   |      2.2     |
|      H2A      | 4.94e-91 | 4.57e-84 | 1.06e-81 |    0      | 2.34e-69   | 2.45e-57 | 8.88e-63  |        0.001        |    0.15     |    1.2   |      0.4     |
|     BAHD1     |    0     |    0     | 7.65e-107 |    0.11   | 5.23e-47   | 4.65e-05 | 4.75e-06  |         0.8         |     1.3     |    2.4   |      2.0     |

6. С помощью lambda-функции вычислил десятичный логарифм каждого значения
```
log_data = df.applymap(lambda x: -1 * np.log10(x) if x > 0 else 100)
log_data
```

|    Protein    |   Human  |  Mouse   | Zebrafish | C.elegans | Drosophila |  Ciliate  |   Yeast   | Methanocaldococcus | Thermococcus |  E.coli  | Tuberculosis |
|:-------------:|:--------:|:--------:|:---------:|:---------:|:----------:|:--------:|:---------:|:------------------:|:-----------:|:--------:|:------------:|
|      H4       |  66.963  | 67.119   | 67.947    | 67.211    | 67.096     | 44.708   | 51.967    |        4.085        |   4.480     | -0.113   |    1.161     |
|      H3       | 95.660   | 95.812   | 94.752    | 93.351    | 95.027     | 85.075   | 86.480    |        1.469        |   1.244     |  0.046   |   -0.663     |
|      H2B      | 86.545   | 82.939   | 70.733    | 64.277    | 58.481     | 48.719   | 56.513    |       -0.415        |   0.770     | -0.255   |   -0.342     |
|      H2A      | 90.306   | 83.340   | 80.975    | 100.000   | 68.631     | 56.611   | 62.052    |        3.000        |   0.824     | -0.079   |    0.398     |
|     BAHD1     | 100.000  | 100.000  | 106.116   | 0.959     | 46.281     | 4.333    | 5.323     |        0.097        |  -0.114     | -0.380   |   -0.301     |

7. По данной таблице построил heatmap

![image](https://github.com/rustamhse/hse23_project/assets/74643940/f11b0d50-6b6a-4583-9a9f-50472981f9e1)


## Вывод

Впервые признаки белка BAHD1 замечены у дрожжей, однако в явной форме они проявляются только у дрозофилы.
