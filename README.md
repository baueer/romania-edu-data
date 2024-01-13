# romania-edu-data
Set de date cu 17284 unitățile de învățământ acreditate din mediul preuniversitar și 3186 localități din România.

**Surse:** 
[data.gov.ro](https://data.gov.ro/dataset/reteaua-scolara-2020-2021) (rețeaua școlară) / [SENIN](http://80.96.186.4:81/senin/classifications.htm?selectedClassification=SIRUTA_S1_2023&action=general_information) (nomenclator localități)

## Exemple
#### Unitate de învățământ
```json
{
    "siiir": "4061103541",
    "denumire": "Colegiul Naţional \"Sfântul Sava\"",
    "categorie": "Colegiu",
    "siruta": 179141,
    "localitate": "BUCUREŞTI SECTORUL 1",
    "judet": "B"
}
```

#### Localitate
```json
{
    "siruta": "179141",
    "denumire": "SECTORUL 1",
    "tip": "sector",
    "judet": "MUNICIPIUL BUCURESTI"
}
```

## Model
#### Unitate de învățământ
```typescript
type Unitate = {
    siiir: string,
    denumire: string,
    categorie: Categorie,
    siruta: string,
    localitate: string,
    judet: string
}

enum Categorie {
    Gradinita = "Grădiniță",
    Primara = "Școală Primară",
    Gimnaziala = "Școală Gimnazială",
    Liceu = "Liceu",
    Colegiu = "Colegiu",
    LiceuTehn = "Liceu Tehnologic / Școală Profesională",
    Profesionala = "Școală Profesională / Învățământ dual",
    Postliceala = "Școală Postliceală",

    // instituții specializate
    ClubSportivScolar = "Club Sportiv Școlar",
    ClubulCopiilor = "Clubul Copiilor",
    PalatulCopiilor = "Palatul Copiilor",
    CentruEducatieIncluziva = "Centru de Educație Incluzivă",
    CentruSpecialEducatieIncluziva = "Centru Special de Educație Incluzivă",

    // altele
    ComisieUniversitati = "Comisie Universități"
}
```

#### Localitate 
```typescript
type Localitate = {
    siruta: string,
    denumire: string,
    tip: Tip,
    judet: string
}

enum Tip {
    Municipiu = "Municipiu",
    Oras = "Oraș",
    Comuna = "Comună",
    Sector = "Sector"
}
```