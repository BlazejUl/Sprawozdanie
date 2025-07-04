Skrypty oraz Zapytania
========================

Wstęp
----------

W tej części dokumentu przedstawione i wytłumaczone wszystkie zrobione skrypty i zapytania sql dla obu baz danych.


sqlitedb
---------

skrypty
~~~~~~~~~~~~
.. py:function:: kod-db.sqlite.lib.backup()

   Kopiuje główną bazę danych i zapisuje jej stan do zapasowej bazy danych

   :param kind: none
   :type kind: none
   :return: none
   :rtype: none

.. py:function:: kod-db.sqlite.lib.restore()

   Kopiuje zapasową bazę danych i zapisuje jej stan do głównej bazy danych

   :param kind: none
   :type kind: none
   :return: none
   :rtype: none

.. py:function:: kod-db.sqlite.lib.dropTable(tabName)

   Próbuje usunąć tabelę z głównej bazy danych o nazwie ``tabName`` jeżeli wyskoczy błąd wypisuje *błąd podczas usuwania  tabeli*

   :param tabName: Nazwa tablicy do usunięcia
   :type tabName: string
   :return: none
   :rtype: none





