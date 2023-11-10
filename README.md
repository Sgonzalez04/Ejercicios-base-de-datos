### Bloque 1

##### Consultas

1. Listar los nombres de los usuarios

   ```sql
   mysql> SELECT nombre FROM tblUsuarios;
+-----------+
| nombre    |
+-----------+
| BRENDA    |
| OSCAR     |
| JOSE      |
| LUIS      |
| LUIS      |
| DANIEL    |
| JAQUELINE |
| ROMAN     |
| BLAS      |
| JESSICA   |
| DIANA     |
| RICARDO   |
| VALENTINA |
| BRENDA    |
| LUCIA     |
| JUAN      |
| ELPIDIO   |
| JESSICA   |
| LETICIA   |
| LUIS      |
| HUGO      |
+-----------+
21 rows in set (0.00 sec)
   ```

2. Calcular el saldo máximo de los usuarios de sexo “Mujer”

     ```sql
      mysql> SELECT max(saldo) FROM tblUsuarios WHERE sexo="M";
+------------+
| max(saldo) |
+------------+
|        500 |
+------------+
1 row in set (0.00 sec)
     ```

3. Listar nombre y teléfono de los usuarios con teléfono NOKIA, BLACKBERRY o SONY

     ```sql
      mysql> SELECT nombre, telefono FROM tblUsuarios WHERE marca IN ('NOKIA', 'BLACKBERRY', 'SAMSUNG');
+-----------+--------------+
| nombre    | telefono     |
+-----------+--------------+
| BRENDA    | 655-330-5736 |
| JOSE      | 655-143-3922 |
| LUIS      | 655-137-1279 |
| LUIS      | 655-100-8260 |
| JAQUELINE | 655-330-5514 |
| JESSICA   | 655-143-6861 |
| VALENTINA | 655-137-4253 |
| LUCIA     | 655-145-4992 |
| JUAN      | 655-100-6517 |
| LETICIA   | 655-143-4019 |
+-----------+--------------+
10 rows in set (0.00 sec)
     ```

4. Contar los usuarios sin saldo o inactivos

     ```sql
      mysql> SELECT COUNT(*) FROM tblUsuarios WHERE NOT activo OR saldo <=0;
+----------+
| COUNT(*) |
+----------+
|        7 |
+----------+
1 row in set (0.00 sec)
     ```

5. Listar el login de los usuarios con nivel 1, 2 o 3

     ```sql
      mysql> SELECT usuario FROM tblUsuarios WHERE nivel = 1 OR 2 OR 3;
+---------+
| usuario |
+---------+
| BRE2271 |
| OSC4677 |
| JOS7086 |
| LUI6115 |
| LUI7072 |
| DAN2832 |
| JAQ5351 |
| ROM6520 |
| BLA9739 |
| JES4752 |
| DIA6570 |
| RIC8283 |
| VAL6882 |
| BRE8106 |
| LUC4982 |
| JUA2337 |
| ELP2984 |
| JES9640 |
| LET4015 |
| LUI1076 |
| HUG5441 |
+---------+
21 rows in set (0.00 sec)
     ```

6. Listar los números de teléfono con saldo menor o igual a 300

     ```sql
      mysql> SELECT telefono FROM tblUsuarios WHERE saldo <= 300;
+--------------+
| telefono     |
+--------------+
| 655-330-5736 |
| 655-143-4181 |
| 655-143-3922 |
| 655-137-1279 |
| 655-100-8260 |
| 655-145-2586 |
| 655-330-5514 |
| 655-330-3263 |
| 655-330-3871 |
| 655-143-3952 |
| 655-145-6049 |
| 655-137-4253 |
| 655-100-1351 |
| 655-145-4992 |
| 655-100-6517 |
| 655-330-5143 |
| 655-143-4019 |
| 655-100-5085 |
+--------------+
18 rows in set (0.00 sec)
     ```

7. Calcular la suma de los saldos de los usuarios de la compañia telefónica NEXTEL

     ```sql
      mysql> SELECT sum(saldo) FROM tblUsuarios WHERE compañia='NEXTEL';
+------------+
| sum(saldo) |
+------------+
|        150 |
+------------+
1 row in set (0.00 sec)
     ```

8. Contar el número de usuarios por compañía telefónica

     ```sql
      mysql> SELECT compañia, COUNT(*) FROM tblUsuarios GROUP BY compañia;
+----------+----------+
| compañia | COUNT(*) |
+----------+----------+
| IUSACELL |        6 |
| TELCEL   |        3 |
| MOVISTAR |        2 |
| UNEFON   |        5 |
| AXEL     |        2 |
| AT&T     |        2 |
| NEXTEL   |        1 |
+----------+----------+
7 rows in set (0.00 sec)
     ```

9. Contar el número de usuarios por nivel

     ```sql
      mysql> SELECT nivel, COUNT(*) FROM tblUsuarios GROUP BY nivel;
+-------+----------+
| nivel | COUNT(*) |
+-------+----------+
|     2 |        5 |
|     3 |        6 |
|     0 |        6 |
|     1 |        4 |
+-------+----------+
4 rows in set (0.00 sec)
     ```

10. Listar el login de los usuarios con nivel 2

      ```sql
       mysql> SELECT usuario FROM tblUsuarios WHERE nivel = 2;
+---------+
| usuario |
+---------+
| BRE2271 |
| ROM6520 |
| RIC8283 |
| LET4015 |
| HUG5441 |
+---------+
5 rows in set (0.00 sec)
      ```

11. Mostrar el email de los usuarios que usan gmail

      ```sql
       mysql> SELECT usuario FROM tblUsuarios WHERE email LIKE '%gmail.com';
+---------+
| usuario |
+---------+
| OSC4677 |
| JOS7086 |
| ROM6520 |
| BRE8106 |
| LUC4982 |
+---------+
5 rows in set (0.00 sec)
      ```

12. Listar nombre y teléfono de los usuarios con teléfono LG, SAMSUNG o MOTOROLA

      ```sql
       mysql>  SELECT nombre, telefono FROM tblUsuarios WHERE marca IN ('LG', 'SAMSUNG', 'MOTOROLA');
+---------+--------------+
| nombre  | telefono     |
+---------+--------------+
| BRENDA  | 655-330-5736 |
| OSCAR   | 655-143-4181 |
| LUIS    | 655-137-1279 |
| ROMAN   | 655-330-3263 |
| BLAS    | 655-330-3871 |
| JESSICA | 655-143-6861 |
| RICARDO | 655-145-6049 |
| BRENDA  | 655-100-1351 |
| JUAN    | 655-100-6517 |
| ELPIDIO | 655-145-9938 |
| HUGO    | 655-137-3935 |
+---------+--------------+
11 rows in set (0.00 sec)
      ```

------

### Bloque 2

##### Consultas

1. Listar nombre y teléfono de los usuarios con teléfono que no sea de la marca LG o SAMSUNG

     ```sql
      mysql> SELECT nombre, telefono FROM tblUsuarios WHERE marca <>'LG' AND marca <>'SAMSUNG';
+-----------+--------------+
| nombre    | telefono     |
+-----------+--------------+
| JOSE      | 655-143-3922 |
| LUIS      | 655-100-8260 |
| DANIEL    | 655-145-2586 |
| JAQUELINE | 655-330-5514 |
| DIANA     | 655-143-3952 |
| RICARDO   | 655-145-6049 |
| VALENTINA | 655-137-4253 |
| BRENDA    | 655-100-1351 |
| LUCIA     | 655-145-4992 |
| ELPIDIO   | 655-145-9938 |
| JESSICA   | 655-330-5143 |
| LETICIA   | 655-143-4019 |
| LUIS      | 655-100-5085 |
| HUGO      | 655-137-3935 |
+-----------+--------------+
14 rows in set (0.00 sec)
     ```

2. Listar el login y teléfono de los usuarios con compañia telefónica IUSACELL

     ```sql
      mysql> SELECT usuario, telefono FROM tblUsuarios WHERE compañia ='IUSACELL';
+---------+--------------+
| usuario | telefono     |
+---------+--------------+
| BRE2271 | 655-330-5736 |
| LUI7072 | 655-100-8260 |
| ROM6520 | 655-330-3263 |
| RIC8283 | 655-145-6049 |
| LUC4982 | 655-145-4992 |
| JES9640 | 655-330-5143 |
+---------+--------------+
6 rows in set (0.00 sec)
     ```

3. Listar el login y teléfono de los usuarios con compañia telefónica que no sea TELCEL

     ```sql
      mysql> SELECT usuario, telefono FROM tblUsuarios WHERE compañia <>'TELCEL';
+---------+--------------+
| usuario | telefono     |
+---------+--------------+
| BRE2271 | 655-330-5736 |
| JOS7086 | 655-143-3922 |
| LUI7072 | 655-100-8260 |
| DAN2832 | 655-145-2586 |
| JAQ5351 | 655-330-5514 |
| ROM6520 | 655-330-3263 |
| BLA9739 | 655-330-3871 |
| DIA6570 | 655-143-3952 |
| RIC8283 | 655-145-6049 |
| VAL6882 | 655-137-4253 |
| BRE8106 | 655-100-1351 |
| LUC4982 | 655-145-4992 |
| JUA2337 | 655-100-6517 |
| ELP2984 | 655-145-9938 |
| JES9640 | 655-330-5143 |
| LET4015 | 655-143-4019 |
| LUI1076 | 655-100-5085 |
| HUG5441 | 655-137-3935 |
+---------+--------------+
18 rows in set (0.00 sec)
     ```

4. Calcular el saldo promedio de los usuarios que tienen teléfono marca NOKIA

     ```sql
      mysql> SELECT AVG(saldo) FROM tblUsuarios WHERE marca='NOKIA';
+------------+
| AVG(saldo) |
+------------+
|        100 |
+------------+
1 row in set (0.00 sec)
     ```

5. Listar el login y teléfono de los usuarios con compañia telefónica IUSACELL o AXEL

     ```sql
      mysql> SELECT usuario, telefono FROM tblUsuarios WHERE compañia IN('TELCEL','AXEL');
+---------+--------------+
| usuario | telefono     |
+---------+--------------+
| OSC4677 | 655-143-4181 |
| LUI6115 | 655-137-1279 |
| JAQ5351 | 655-330-5514 |
| JES4752 | 655-143-6861 |
| JUA2337 | 655-100-6517 |
+---------+--------------+
5 rows in set (0.00 sec)
     ```

6. Mostrar el email de los usuarios que no usan yahoo

     ```sql
      mysql> SELECT email FROM tblUsuarios WHERE email NOT LIKE '%yahoo.com';
+-----------------------+
| email                 |
+-----------------------+
| brenda@live.com       |
| oscar@gmail.com       |
| francisco@gmail.com   |
| enrique@outlook.com   |
| luis@hotmail.com      |
| daniel@outlook.com    |
| jaqueline@outlook.com |
| roman@gmail.com       |
| blas@hotmail.com      |
| jessica@hotmail.com   |
| diana@live.com        |
| ricardo@hotmail.com   |
| valentina@live.com    |
| brenda2@gmail.com     |
| lucia@gmail.com       |
| juan@outlook.com      |
| elpidio@outlook.com   |
| jessica2@live.com     |
| luis2@live.com        |
| hugo@live.com         |
+-----------------------+
20 rows in set (0.00 sec)
     ```

7. Listar el login y teléfono de los usuarios con compañia telefónica que no sea TELCEL o IUSACELL

     ```sql
      mysql> SELECT usuario, telefono FROM tblUsuarios WHERE compañia NOT IN('TELCEL','IUSACELL');
+---------+--------------+
| usuario | telefono     |
+---------+--------------+
| JOS7086 | 655-143-3922 |
| DAN2832 | 655-145-2586 |
| JAQ5351 | 655-330-5514 |
| BLA9739 | 655-330-3871 |
| DIA6570 | 655-143-3952 |
| VAL6882 | 655-137-4253 |
| BRE8106 | 655-100-1351 |
| JUA2337 | 655-100-6517 |
| ELP2984 | 655-145-9938 |
| LET4015 | 655-143-4019 |
| LUI1076 | 655-100-5085 |
| HUG5441 | 655-137-3935 |
+---------+--------------+
12 rows in set (0.00 sec)
     ```

8. Listar el login y teléfono de los usuarios con compañia telefónica UNEFON

     ```sql
      mysql> SELECT usuario, telefono FROM tblUsuarios WHERE compañia ='UNEFON';
+---------+--------------+
| usuario | telefono     |
+---------+--------------+
| DAN2832 | 655-145-2586 |
| BLA9739 | 655-330-3871 |
| DIA6570 | 655-143-3952 |
| LET4015 | 655-143-4019 |
| LUI1076 | 655-100-5085 |
+---------+--------------+
5 rows in set (0.00 sec)
     ```

9. Listar las diferentes marcas de celular en orden alfabético descendentemente

     ```sql
      mysql> SELECT DISTINCT compañia FROM tblUsuarios ORDER BY compañia DESC;
+----------+
| compañia |
+----------+
| UNEFON   |
| TELCEL   |
| NEXTEL   |
| MOVISTAR |
| IUSACELL |
| AXEL     |
| AT&T     |
+----------+
7 rows in set (0.00 sec)
     ```

10. Listar las diferentes compañias en orden alfabético aleatorio

      ```sql
       mysql> SELECT DISTINCT compañia FROM tblUsuarios ORDER BY RAND();
+----------+
| compañia |
+----------+
| TELCEL   |
| IUSACELL |
| UNEFON   |
| NEXTEL   |
| MOVISTAR |
| AXEL     |
| AT&T     |
+----------+
7 rows in set (0.00 sec)
      ```

11. Listar el login de los usuarios con nivel 0 o 2

      ```sql
       mysql> SELECT usuario FROM tblUsuarios WHERE nivel IN(0,2);
+---------+
| usuario |
+---------+
| BRE2271 |
| LUI6115 |
| DAN2832 |
| JAQ5351 |
| ROM6520 |
| BLA9739 |
| RIC8283 |
| VAL6882 |
| JUA2337 |
| LET4015 |
| HUG5441 |
+---------+
11 rows in set (0.00 sec)
      ```

12. Calcular el saldo promedio de los usuarios que tienen teléfono marca LG

      ```sql
       mysql> SELECT AVG(saldo) FROM tblUsuarios WHERE marca='LG';
+------------+
| AVG(saldo) |
+------------+
|         50 |
+------------+
1 row in set (0.00 sec)
      ```

------

### Bloque 3

##### Consultas

1. Listar el login de los usuarios con nivel 1 o 3

     ```sql
      SELECT usuario FROM tblUsuarios WHERE nivel IN(1,3);
+---------+
| usuario |
+---------+
| OSC4677 |
| JOS7086 |
| LUI7072 |
| JES4752 |
| DIA6570 |
| BRE8106 |
| LUC4982 |
| ELP2984 |
| JES9640 |
| LUI1076 |
+---------+
10 rows in set (0.00 sec)
     ```

2. Listar nombre y teléfono de los usuarios con teléfono que no sea de la marca BLACKBERRY

     ```sql
      mysql> SELECT usuario, telefono FROM tblUsuarios WHERE marca <>'BLACKBERRY';
+---------+--------------+
| usuario | telefono     |
+---------+--------------+
| BRE2271 | 655-330-5736 |
| OSC4677 | 655-143-4181 |
| JOS7086 | 655-143-3922 |
| LUI6115 | 655-137-1279 |
| LUI7072 | 655-100-8260 |
| DAN2832 | 655-145-2586 |
| ROM6520 | 655-330-3263 |
| BLA9739 | 655-330-3871 |
| JES4752 | 655-143-6861 |
| DIA6570 | 655-143-3952 |
| RIC8283 | 655-145-6049 |
| BRE8106 | 655-100-1351 |
| JUA2337 | 655-100-6517 |
| ELP2984 | 655-145-9938 |
| JES9640 | 655-330-5143 |
| LUI1076 | 655-100-5085 |
| HUG5441 | 655-137-3935 |
+---------+--------------+
17 rows in set (0.00 sec)
     ```

3. Listar el login de los usuarios con nivel 3

     ```sql
      mysql> SELECT usuario FROM tblUsuarios WHERE nivel =3;
+---------+
| usuario |
+---------+
| OSC4677 |
| JOS7086 |
| BRE8106 |
| LUC4982 |
| JES9640 |
| LUI1076 |
+---------+
6 rows in set (0.00 sec)

     ```

4. Listar el login de los usuarios con nivel 0

     ```sql
      mysql> SELECT usuario FROM tblUsuarios WHERE nivel =0;
+---------+
| usuario |
+---------+
| LUI6115 |
| DAN2832 |
| JAQ5351 |
| BLA9739 |
| VAL6882 |
| JUA2337 |
+---------+
6 rows in set (0.00 sec)
     ```

5. Listar el login de los usuarios con nivel 1

     ```sql
      mysql> SELECT usuario FROM tblUsuarios WHERE nivel =1;
+---------+
| usuario |
+---------+
| LUI7072 |
| JES4752 |
| DIA6570 |
| ELP2984 |
+---------+
4 rows in set (0.00 sec)
     ```

6. Contar el número de usuarios por sexo

     ```sql
      mysql> SELECT sexo, COUNT(*) FROM tblUsuarios GROUP BY sexo;
+------+----------+
| sexo | COUNT(*) |
+------+----------+
| M    |        9 |
| H    |       12 |
+------+----------+
2 rows in set (0.00 sec)
     ```

7. Listar el login y teléfono de los usuarios con compañia telefónica AT&T

     ```sql
      
mysql> SELECT usuario, telefono FROM tblUsuarios WHERE compañia='AT&T';
+---------+--------------+
| usuario | telefono     |
+---------+--------------+
| VAL6882 | 655-137-4253 |
| HUG5441 | 655-137-3935 |
+---------+--------------+
2 rows in set (0.00 sec)

     ```

8. Listar las diferentes compañias en orden alfabético descendentemente

     ```sql
      mysql> SELECT DISTINCT compañia FROM tblUsuarios ORDER BY compañia DESC;
+----------+
| compañia |
+----------+
| UNEFON   |
| TELCEL   |
| NEXTEL   |
| MOVISTAR |
| IUSACELL |
| AXEL     |
| AT&T     |
+----------+
7 rows in set (0.00 sec)
     ```

9. Listar el logn de los usuarios inactivos

     ```sql
      mysql> SELECT usuario FROM tblUsuarios WHERE activo =0;
+---------+
| usuario |
+---------+
| LUI7072 |
| DIA6570 |
| VAL6882 |
| JUA2337 |
+---------+
4 rows in set (0.00 sec)
     ```

10. Listar los números de teléfono sin saldo

      ```sql
       mysql> SELECT usuario FROM tblUsuarios WHERE saldo =0;
+---------+
| usuario |
+---------+
| OSC4677 |
| JAQ5351 |
| LUC4982 |
| JUA2337 |
+---------+
4 rows in set (0.00 sec)
      ```

11. Calcular el saldo mínimo de los usuarios de sexo “Hombre”

      ```sql
       mysql> SELECT MIN(saldo) FROM tblUsuarios WHERE sexo='H';
+------------+
| MIN(saldo) |
+------------+
|          0 |
+------------+
1 row in set (0.00 sec)
      ```

12. Listar los números de teléfono con saldo mayor a 300

      ```sql
       mysql> SELECT telefono FROM tblUsuarios WHERE saldo>300;
+--------------+
| telefono     |
+--------------+
| 655-143-6861 |
| 655-145-9938 |
| 655-137-3935 |
+--------------+
3 rows in set (0.00 sec)
      ```

------

### Bloque 4

##### Consultas

1. Contar el número de usuarios por marca de teléfono

     ```sql
      mysql> SELECT compañia, COUNT(*) FROM tblUsuarios GROUP BY compañia;
+----------+----------+
| compañia | COUNT(*) |
+----------+----------+
| IUSACELL |        6 |
| TELCEL   |        3 |
| MOVISTAR |        2 |
| UNEFON   |        5 |
| AXEL     |        2 |
| AT&T     |        2 |
| NEXTEL   |        1 |
+----------+----------+
7 rows in set (0.00 sec)
     ```

2. Listar nombre y teléfono de los usuarios con teléfono que no sea de la marca LG

     ```sql
      mysql> SELECT nombre, telefono FROM tblUsuarios WHERE marca <> 'LG' ;
+-----------+--------------+
| nombre    | telefono     |
+-----------+--------------+
| BRENDA    | 655-330-5736 |
| JOSE      | 655-143-3922 |
| LUIS      | 655-137-1279 |
| LUIS      | 655-100-8260 |
| DANIEL    | 655-145-2586 |
| JAQUELINE | 655-330-5514 |
| JESSICA   | 655-143-6861 |
| DIANA     | 655-143-3952 |
| RICARDO   | 655-145-6049 |
| VALENTINA | 655-137-4253 |
| BRENDA    | 655-100-1351 |
| LUCIA     | 655-145-4992 |
| JUAN      | 655-100-6517 |
| ELPIDIO   | 655-145-9938 |
| JESSICA   | 655-330-5143 |
| LETICIA   | 655-143-4019 |
| LUIS      | 655-100-5085 |
| HUGO      | 655-137-3935 |
+-----------+--------------+
18 rows in set (0.00 sec)
     ```

3. Listar las diferentes compañias en orden alfabético ascendentemente

     ```sql
      mysql> SELECT DISTINCT compañia FROM tblUsuarios ORDER BY compañia ASC ;
+----------+
| compañia |
+----------+
| AT&T     |
| AXEL     |
| IUSACELL |
| MOVISTAR |
| NEXTEL   |
| TELCEL   |
| UNEFON   |
+----------+
7 rows in set (0.00 sec) 
     ```

4. Calcular la suma de los saldos de los usuarios de la compañia telefónica UNEFON

     ```sql
      mysql> SELECT SUM(saldo) FROM tblUsuarios WHERE compañia ='UNEFON';
+------------+
| SUM(saldo) |
+------------+
|        550 |
+------------+
1 row in set (0.00 sec)
     ```

5. Mostrar el email de los usuarios que usan hotmail

     ```sql
      mysql> SELECT email FROM tblUsuarios WHERE email LIKE'%hotmail%';
+---------------------+
| email               |
+---------------------+
| luis@hotmail.com    |
| blas@hotmail.com    |
| jessica@hotmail.com |
| ricardo@hotmail.com |
+---------------------+
4 rows in set (0.00 sec)
     ```

6. Listar los nombres de los usuarios sin saldo o inactivos

     ```sql
      mysql> SELECT nombre FROM tblUsuarios WHERE saldo=0 OR activo=0;
+-----------+
| nombre    |
+-----------+
| OSCAR     |
| LUIS      |
| JAQUELINE |
| DIANA     |
| VALENTINA |
| LUCIA     |
| JUAN      |
+-----------+
7 rows in set (0.00 sec)
     ```

7. Listar el login y teléfono de los usuarios con compañia telefónica IUSACELL o TELCEL

     ```sql
     ```

8. Listar las diferentes marcas de celular en orden alfabético ascendentemente

     ```sql
      mysql> SELECT usuario, telefono FROM tblUsuarios WHERE compañia IN ('IUSACELL','TELCEL');
+---------+--------------+
| usuario | telefono     |
+---------+--------------+
| BRE2271 | 655-330-5736 |
| OSC4677 | 655-143-4181 |
| LUI6115 | 655-137-1279 |
| LUI7072 | 655-100-8260 |
| ROM6520 | 655-330-3263 |
| JES4752 | 655-143-6861 |
| RIC8283 | 655-145-6049 |
| LUC4982 | 655-145-4992 |
| JES9640 | 655-330-5143 |
+---------+--------------+
9 rows in set (0.00 sec)
     ```

9. Listar las diferentes marcas de celular en orden alfabético aleatorio

     ```sql
      mysql> SELECT DISTINCT marca FROM tblUsuarios ORDER BY RAND() ;
+------------+
| marca      |
+------------+
| MOTOROLA   |
| SAMSUNG    |
| BLACKBERRY |
| NOKIA      |
| LG         |
| SONY       |
+------------+
6 rows in set (0.00 sec)
     ```

10. Listar el login y teléfono de los usuarios con compañia telefónica IUSACELL o UNEFON

      ```sql
       mysql> SELECT usuario, telefono FROM tblUsuarios WHERE compañia IN ('IUSACELL','UNEFON');
+---------+--------------+
| usuario | telefono     |
+---------+--------------+
| BRE2271 | 655-330-5736 |
| LUI7072 | 655-100-8260 |
| DAN2832 | 655-145-2586 |
| ROM6520 | 655-330-3263 |
| BLA9739 | 655-330-3871 |
| DIA6570 | 655-143-3952 |
| RIC8283 | 655-145-6049 |
| LUC4982 | 655-145-4992 |
| JES9640 | 655-330-5143 |
| LET4015 | 655-143-4019 |
| LUI1076 | 655-100-5085 |
+---------+--------------+
11 rows in set (0.00 sec)
      ```

11. Listar nombre y teléfono de los usuarios con teléfono que no sea de la marca MOTOROLA o NOKIA

      ```sql
       mysql> SELECT usuario, telefono FROM tblUsuarios WHERE marca NOT IN ('MOTOROLA','NOKIA');
+---------+--------------+
| usuario | telefono     |
+---------+--------------+
| BRE2271 | 655-330-5736 |
| OSC4677 | 655-143-4181 |
| LUI6115 | 655-137-1279 |
| DAN2832 | 655-145-2586 |
| JAQ5351 | 655-330-5514 |
| ROM6520 | 655-330-3263 |
| BLA9739 | 655-330-3871 |
| JES4752 | 655-143-6861 |
| DIA6570 | 655-143-3952 |
| VAL6882 | 655-137-4253 |
| LUC4982 | 655-145-4992 |
| JUA2337 | 655-100-6517 |
| JES9640 | 655-330-5143 |
| LET4015 | 655-143-4019 |
| LUI1076 | 655-100-5085 |
+---------+--------------+
15 rows in set (0.00 sec)
      ```

12. Calcular la suma de los saldos de los usuarios de la compañia telefónica TELCEL

      ```sql
       mysql> SELECT SUM(saldo) FROM tblUsuarios WHERE compañia ='TELCEL';
+------------+
| SUM(saldo) |
+------------+
|        550 |
+------------+
1 row in set (0.00 sec)
      ```
