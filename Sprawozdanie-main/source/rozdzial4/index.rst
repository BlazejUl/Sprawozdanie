Skrypty oraz Zapytania
========================

Wstęp
----------

W tej części dokumentu przedstawione i wytłumaczone wszystkie zrobione skrypty i zapytania sql dla obu baz danych.


sqlite
---------

Skrypty
~~~~~~~~~~~~


.. py:function:: kod-db.sqlite.lib.backup()

   Kopiuje główną bazę danych i zapisuje jej stan do zapasowej bazy danych

   :param : none
   :type : none
   :return: none
   :rtype: none



.. py:function:: kod-db.sqlite.lib.restore()

   Kopiuje zapasową bazę danych i zapisuje jej stan do głównej bazy danych

   :param : none
   :type : none
   :return: none
   :rtype: none



.. py:function:: kod-db.sqlite.lib.dropTable(tabName)

   Próbuje usunąć tabelę o nazwie ``tabName`` z głównej bazy danych jeżeli wyskoczy błąd wypisuje *błąd podczas usuwania  tabeli*

   :param tabName: Nazwa tablicy do usunięcia
   :type tabName: string
   :return: none
   :rtype: none


.. py:function:: kod-db.sqlite.lib.jsonToLite(dbPath,jsonPath,tabName,k1,k2,k3,k4)

   Jeżeli w bazie danych nie ma tabeli o nazwie ``tabName`` tworzy ją następnie otwiera plik ``.json`` i zapisuje do tabeli pod nazwą ``tabName`` wartości z pliku

   :param dbPath: Ścieżka do bazy danych
   :type dbPath: string
   :param jsonPath: Ścieżka do pliku json
   :type jsonPath: string
   :param tabName: Nazwa tablicy do stworzenia / otworzenia
   :type tabName: string
   :param k1: pierwsza kolumna tablicy
   :type k1: string
   :param k2: dróga kolumna tablicy
   :type k2: string
   :param k3: trzecia kolumna tablicy
   :type k3: string
   :param k4: czwarta kolumna tablicy
   :type k4: string
   :return: none
   :rtype: none

Zapytania sql
~~~~~~~~~~~~~~~~~~~~~~~~


.. py:function:: kod-db.sqlite.lib.SQLuser_price()

   wyświetla kolumny uzytkownicy.username, towary.price łączy tabelę uzytkownicy z tabelą towary poprzez tabelę tranzakcje używając user_ID item_ID znajdujących się w obu tabelach

   :param : none
   :type : none
   :return: none
   :rtype: none



.. py:function:: kod-db.sqlite.lib.SQLdate_price()

   wyświetla kolumny tranzakcje.purchase_date, towary.price łączy tabelę poprzez item_ID 

   :param : none
   :type : none
   :return: none
   :rtype: none



.. py:function:: kod-db.sqlite.lib.SQLuser_towar_name()

   wyświetla kolumny uzytkownicy.username, towary.name łączy tabelę uzytkownicy z tabelą towary poprzez tabelę tranzakcje używając user_ID item_ID znajdujących się w obu tabelach 

   :param : none
   :type : none
   :return: none
   :rtype: none


postgresql
-------------

Skrypty
~~~~~~~~~~~~


.. py:function:: kod-db.postgresql.lib.connect_db()

   zawiera połączenie z pgadminem używając biblioteki psycopg i parametrów znajdujących się w pliku database_creds.json

   :param : none
   :type : none
   :return: connection
   :rtype: psycopg.connect

.. py:function:: kod-db.postgresql.lib.csvToPostgre(conn,path,tabName,k1,k2,k3,k4)

   Jeżeli w bazie danych nie ma tabeli o nazwie ``tabName`` tworzy ją następnie otwiera plik ``.csv`` i zapisuje do tabeli pod nazwą ``tabName`` wartości z pliku

   :param conn: połączenie z bazą danych
   :type conn: psycopg.connect
   :param path: Ścieżka do pliku csv
   :type path: string
   :param tabName: Nazwa tablicy do stworzenia / otworzenia
   :type tabName: string
   :param k1: pierwsza kolumna tablicy
   :type k1: string
   :param k2: dróga kolumna tablicy
   :type k2: string
   :param k3: trzecia kolumna tablicy
   :type k3: string
   :param k4: czwarta kolumna tablicy
   :type k4: string
   :return: none
   :rtype: none

.. py:function:: kod-db.postgresql.lib.backup(conn)

   tworzy backupa bazy danych

   :param conn: połączenie z bazą danych
   :type conn: psycopg.connect
   :return: none
   :rtype: none


.. py:function:: kod-db.postgresql.lib.restore(conn)

   odtwarza bazę danych z backupa

   :param conn: połączenie z bazą danych
   :type conn: psycopg.connect
   :return: none
   :rtype: none

.. py:function:: kod-db.postgresql.lib.dropTable(conn,table)

   Próbuje usunąć tabelę o nazwie table z bazy danych

   :param conn: połączenie z bazą danych
   :type conn: psycopg.connect
   :param table: Nazwa tablicy do usunięcia
   :type table: string
   :return: none
   :rtype: none




Zapytania sql
~~~~~~~~~~~~~~~~~~~~~~~~


.. py:function:: kod-db.postgresql.lib.SQLuser_price(conn)

   wyświetla kolumny uzytkownicy.username, towary.price łączy tabelę uzytkownicy z tabelą towary poprzez tabelę tranzakcje używając user_ID item_ID znajdujących się w obu tabelach

   :param conn: połączenie z bazą danych
   :type conn: psycopg.connect
   :return: none
   :rtype: none



.. py:function:: kod-db.postgresql.lib.SQLdate_price(conn)

   wyświetla kolumny tranzakcje.purchase_date, towary.price łączy tabelę poprzez item_ID 

   :param conn: połączenie z bazą danych
   :type conn: psycopg.connect
   :return: none
   :rtype: none



.. py:function:: kod-db.postgresql.lib.SQLuser_towar_name(conn)

   wyświetla kolumny uzytkownicy.username, towary.name łączy tabelę uzytkownicy z tabelą towary poprzez tabelę tranzakcje używając user_ID item_ID znajdujących się w obu tabelach 

   :param conn: połączenie z bazą danych
   :type conn: psycopg.connect
   :return: none
   :rtype: none

