[Google Colab](https://colab.research.google.com/drive/1SjZOInQi1qs3LfCIy6qqdyIAen6Em5ae?usp=sharing)

## Данные

Рассматривалась клеточная линия OCI-LY3, гистоновая метка H3K27me3, реплики ENCFF002BCC и ENCFF969JAR, а также ENCFF475WXS для контроля.

## FastQC

### ENCFF002BCC

В изначальном отчёте качество чтений не везде было хорошим, поэтому для этого файла было проведено подрезание чтений. Оно проводилось с помощью программы trimmomatic. В итоге, отчёт в файле [ENCFF002BCC_trimmed_fastqc.html](./ENCFF002BCC_trimmed_fastqc.html)

![image](https://user-images.githubusercontent.com/52814490/222259963-af4c13ee-178c-4b9b-913b-c60c3bf2918b.png)
![image](https://user-images.githubusercontent.com/52814490/222260392-f20b3343-de64-4321-98b0-cb29da7800a5.png)
![image](https://user-images.githubusercontent.com/52814490/222260460-367e453d-49e3-4653-b5fd-6f5a092aca1c.png)

### ENCFF969JAR

Отчёт в файле [ENCFF969JAR_fastqc.html](./ENCFF969JAR_fastqc.html)

![image](https://user-images.githubusercontent.com/52814490/222260706-9f46dfcc-924a-49b6-a049-aa0172c8aad9.png)
![image](https://user-images.githubusercontent.com/52814490/222260780-2d8af9e8-92da-4d3d-94f7-54a5b8f43755.png)
![image](https://user-images.githubusercontent.com/52814490/222260842-0d140b4f-6b43-462a-81cf-2e5df63e2220.png)

### ENCFF475WXS

Отчёт в файле [ENCFF475WXS_fastqc.html](./ENCFF475WXS_fastqc.html)

![image](https://user-images.githubusercontent.com/52814490/222261078-659407fa-e251-413f-ae33-2703e868b620.png)
![image](https://user-images.githubusercontent.com/52814490/222261232-31bb85fb-f370-405c-999b-4d854f0e8277.png)
![image](https://user-images.githubusercontent.com/52814490/222261313-3b4b53d7-0368-4217-8e2b-e43cea784cec.png)

### Анализ отчётов

Во всех трёх отчётах почти все чтения очень хорошего качества, и распределение GC примерно одинаковое, почти совпадает с теоретическим.

## Выравнивание ридов

Выравнивание проводилось на 14 хромосому человека

### Таблица со статистикой выравнивания

| Реплика      | Число ридов | Выравнилось уникально | Выравнилось не-уникально | Не выравнилось   |
| ------------ | ----------- | --------------------- | ------------------------ | ---------------- |
| ENCFF002BCC  | 28703495    | 1221892 (4.26%)       | 3301297 (11.50%)         | 24180306 (84.24%)|
| ENCFF969JAR  | 13627324    | 564374  (4.14%)       | 1253953 (9.20%)          | 11808997 (86.66%)|
| ENCFF475WXS  | 23610501    | 1003578 (4.25%)       | 2055500 (8.71%)          | 20551423 (87.04%)|

### Анализ таблицы

Процент выравниваний получается низким, так как выравнивание происходит только на одну хромосому, а реплики были получены для всего генома.

## Пересечение MACS2 пиков и ENCODE пиков для двух реплик

[Сравнение MACS2 с ENCODE](./venn1.pdf)

[Сравнение ENCODE с MACS2](./venn2.pdf)

### Сравнение результатов

В моём случае, результаты пересечения совпадают. Вероятно, это связано с тем, что число пересечений получилось небольшим, и среди них не оказалось участков, где несколько пиков из одного файла попадают в рамки одного пика из другого файла. Также, возможно, стоило взять файл для "ENCODE4 v1.6.1 GRCh38", в то время как я взял файл для "ENCODE3 GRCh38"
