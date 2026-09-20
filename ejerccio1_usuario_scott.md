El área de Recursos Humanos utiliza el esquema HR y necesita crear usuarios con distintos niveles de acceso.
Se necesita crear el usuario SCOTT con contraseña TIGER123456.
Al usuario se le debe asignar una cuota máxima de 100 MB sobre el tablespace USERS y otorgar exclusivamente los 
siguientes privilegios sobre la tabla employees: SELECT,INSERT,UPDATE y DELETE.
Escribir TODOS LOS comandos para crearlo.

Importante
---------
No se deberán otorgar privilegios adicionales a los estrictamente necesarios para cumplir con los requerimientos establecidos.
Salvo que se indique lo contrario, suponga que las operaciones administrativas se realizan desde el usuario SYSTEM.




-- 1. Crear el usuario SCOTT con su contraseña
CREATE USER scott IDENTIFIED BY TIGER123456;

-- 2. Asignar la cuota de 100 MB sobre el tablespace USERS
ALTER USER scott QUOTA 100M ON USERS;

-- 3. Otorgar los privilegios específicos sobre la tabla employees del esquema HR
GRANT SELECT, INSERT, UPDATE, DELETE ON hr.employees TO scott;




---

### Explicación de cada comando

* **CREATE USER scott IDENTIFIED BY TIGER123456;**
  Crea la cuenta de usuario con el nombre y la clave requeridos.

* **ALTER USER scott QUOTA 100M ON USERS;**
  Otorga el límite máximo exacto de 100 Megabytes dentro del almacenamiento en el tablespace USERS.

* **GRANT SELECT, INSERT, UPDATE, DELETE ON hr.employees TO scott;**
  Otorga estrictamente los 4 privilegios DML requeridos sobre la tabla employees perteneciente al esquema hr.
