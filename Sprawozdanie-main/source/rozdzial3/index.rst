Modele Bazy Danych
=========================================


:author: Błażej Uliasz

Wprowadzenie
--------------

w tym rozdziale są zapisane modele bazy danych oparte na sqlite oraz postgresql

Model Konceptualny
---------------------

Baza danych zkłada się z 3 tabel **towary** **tranzakcje** **uzytkownicy**

Relacje
~~~~~~~~

**uzytkownicy** z **tranzakcje** mają relację wielu do wielu 

**towary** z **tranzakcje** mają relację wielu do wielu 

**uzytkownicy** z **towary** mają relację wielu do wielu przez tabelę **tranzakcje**


Model Logiczny
---------------------
tabela **uzytkownicy** składa się z kolumn

- ``username`` — format tekst
- ``password`` — format tekst
- ``user_ID`` — format tekst
- ``join_date`` — format tekst

tabela **towary** składa się z kolumn

- ``name`` — format tekst
- ``price`` — format tekst
- ``item_ID`` — format tekst
- ``add_date`` — format tekst

tabela **tranzakcje** składa się z kolumn

- ``user_ID`` — format tekst
- ``item_ID`` — format tekst
- ``purchase_ID`` — format tekst
- ``purchase_date`` — format tekst

Relacje
~~~~~~~~

**uzytkownicy** z **tranzakcje** mają relację wielu do wielu za pomocą kolumny ``user_ID``

**towary** z **tranzakcje** mają relację wielu do wielu ``item_ID``

**uzytkownicy** z **towary** mają relację wielu do wielu przez tabelę **tranzakcje**


Model Fizyczny
---------------------

Implementacja **sqlite**
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

tabela **uzytkownicy** składa się z kolumn

- ``username`` — format text
- ``password`` — format text
- ``user_ID`` — format text
- ``join_date`` — format text

tabela **towary** składa się z kolumn

- ``name`` — format text
- ``price`` — format text
- ``item_ID`` — format text
- ``add_date`` — format text

tabela **tranzakcje** składa się z kolumn

- ``user_ID`` — format text
- ``item_ID`` — format text
- ``purchase_ID`` — format text
- ``purchase_date`` — format text

Implementacja **postgresql**
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

tabela **uzytkownicy** składa się z kolumn

- ``username`` — format VARCHAR(10)
- ``password`` — format VARCHAR(10)
- ``user_ID`` — format VARCHAR(10)
- ``join_date`` — format DATE

tabela **towary** składa się z kolumn

- ``name`` — format VARCHAR(10)
- ``price`` — format VARCHAR(10)
- ``item_ID`` — format VARCHAR(10)
- ``add_date`` — format DATE

tabela **tranzakcje** składa się z kolumn

- ``user_ID`` — format VARCHAR(10)
- ``item_ID`` — format VARCHAR(10)
- ``purchase_ID`` — format VARCHAR(10)
- ``purchase_date`` — format DATE

