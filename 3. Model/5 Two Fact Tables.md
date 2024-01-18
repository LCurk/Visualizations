i am working in power bi. i have two fact tables (Fact1 and Fact2). they both have 10 different columns and 2 same columns (Column1, Column2). If I make relation by each of these 2 columns, two fact tables are in many:many (N:N) relationship. Fact2 have ID of Dimension1 and is in relationship with dimension table Dimension1. I want to filter Fact1 with Dimension1. is that possible? how?

---

1. naredi refrenčno tabelo za Fact1
2. v referenčno tabelo Facta1 mergaj Fact2 po Column1
3. v referenčno tabelo Facta1 mergaj Fact2 po Column2
4. naredi povezavo med referenčno tabelo Facta1 in unique Dimenzijo1 
5. narediš referenčne tabele za dimenzije, ki so v obeh dveh factih (ampak nimajo istega načina mapiranja, ker sta Column1 in Column2 v vsaki Fact tabeli različna) in jih povežeš na referenčen Fact1
6. naredi vizualizacijo, kjer nekaj iz Facta1 filtriraš po Dimension1