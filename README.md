### Informe de Backups Automáticos - Crontab

A continuación, se describe la programación, la fuente y el destino de los respaldos automáticos para cada base de datos, estructurados según las diferentes frecuencias configuradas en el crontab.

---

#### 1. **Backups de Lupajuridica y Controles**

   - **Diario**
     - **Horario:** 2:00 am y 2:30 am, de lunes a sábado.
     - **Bases de Datos Respaldadas:**
       - `bases_de_datos` y `db_lupajuridica`.
     - **Destinos:**
       - `bases_de_datos`: `/backup_sdb/databases/bases_de_datos/lupajuridica/controles/diario/`
       - `db_lupajuridica`: `/backup_sdb/databases/bases_de_datos/lupajuridica/db_lupajuridica/diario/`

   - **Semanal**
     - **Frecuencia:** Una vez por semana.
     - **Bases de Datos Respaldadas:**
       - `bases_de_datos` y `db_lupajuridica`.
     - **Destinos:**
       - `bases_de_datos`: `/backup_sdb/databases/bases_de_datos/lupajuridica/controles/semanal/`
       - `db_lupajuridica`: `/backup_sdb/databases/bases_de_datos/lupajuridica/db_lupajuridica/semanal/`

   - **Mensual**
     - **Frecuencia:** Una vez al mes.
     - **Bases de Datos Respaldadas:**
       - `bases_de_datos` y `db_lupajuridica`.
     - **Destinos:**
       - `bases_de_datos`: `/backup_sdb/databases/bases_de_datos/lupajuridica/controles/mensual/`
       - `db_lupajuridica`: `/backup_sdb/databases/bases_de_datos/lupajuridica/db_lupajuridica/mensual/`

---

#### 2. **Backups de Soporte**

   - **Diario**
     - **Horario:** 2:00 am, de lunes a sábado.
     - **Bases de Datos Respaldadas:**
       - `soporte` y `db`.
     - **Destinos:**
       - `soporte`: `/backup_sdb/databases/bases_de_datos/soporte/soporte_lupa/diario/`
       - `db`: `/backup_sdb/databases/bases_de_datos/soporte/otros/diario/`

   - **Semanal**
     - **Frecuencia:** Una vez por semana.
     - **Bases de Datos Respaldadas:**
       - `soporte` y `db`.
     - **Destinos:**
       - `soporte`: `/backup_sdb/databases/bases_de_datos/soporte/soporte_lupa/semanal/`
       - `db`: `/backup_sdb/databases/bases_de_datos/soporte/otros/semanal/`

   - **Mensual**
     - **Frecuencia:** Una vez al mes.
     - **Bases de Datos Respaldadas:**
       - `soporte` y `db`.
     - **Destinos:**
       - `soporte`: `/backup_sdb/databases/bases_de_datos/soporte/soporte_lupa/mensual/`
       - `db`: `/backup_sdb/databases/bases_de_datos/soporte/otros/mensual/`

---

#### 3. **Backups de MiprocesoJudicial**

   - **Diario**
     - **Horario:** 1:00 am, todos los días.
     - **Base de Datos Respaldada:** `databases` de MiprocesoJudicial.
     - **Destino:** `/backup_sdb/databases/bases_de_datos/miprocesojudicial/`

---

#### 4. **Backups de Robots**

   - **Diario**
     - **Horario:** 4:00 pm, todos los días.
     - **Base de Datos Respaldada:** `robots`.
     - **Destino:** `/backup_sdb/databases/bases_de_datos/robots/diario/`

   - **Copia Ayer**
     - **Horario:** 8:00 am, todos los días.
     - **Función:** Copia la última versión diaria a un directorio adicional de respaldo diario.
     - **Destino:** `/backup_sdb/databases/bases_de_datos/robots/ayer/`

---

#### 5. **Backups de Tableros**

   - **Diario**
     - **Horario:** 9:00 pm, de lunes a sábado.
     - **Base de Datos Respaldada:** `backup_tableros`.
     - **Destino:** `/backup_sdb/databases/bases_de_datos/tableros/diario/`

   - **Semanal**
     - **Frecuencia:** Una vez por semana.
     - **Base de Datos Respaldada:** `backup_tableros`.
     - **Destino:** `/backup_sdb/databases/bases_de_datos/tableros/semanal/`

   - **Mensual**
     - **Frecuencia:** Una vez al mes.
     - **Base de Datos Respaldada:** `backup_tableros`.
     - **Destino:** `/backup_sdb/databases/bases_de_datos/tableros/mensual/`

---

### Tabla Resumen de Backups

| Hora del Backup | Servidor Origen       | LUPABACKUP                               |
|-----------------|-----------------------|------------------------------------------------------------------------|
| 2:00 am (lun-sáb) | 181.79.32.58 (Lupajuridica bases_de_datos) | /backup_sdb/databases/bases_de_datos/lupajuridica/controles/diario/      |
| 2:30 am (lun-sáb) | 181.79.32.58 (Lupajuridica db_lupajuridica) | /backup_sdb/databases/bases_de_datos/lupajuridica/db_lupajuridica/diario/|
| Semanal         | 181.79.32.58 (Lupajuridica bases_de_datos) | /backup_sdb/databases/bases_de_datos/lupajuridica/controles/semanal/     |
| Semanal         | 181.79.32.58 (Lupajuridica db_lupajuridica) | /backup_sdb/databases/bases_de_datos/lupajuridica/db_lupajuridica/semanal|
| Mensual         | 181.79.32.58 (Lupajuridica bases_de_datos) | /backup_sdb/databases/bases_de_datos/lupajuridica/controles/mensual/     |
| Mensual         | 181.79.32.58 (Lupajuridica db_lupajuridica) | /backup_sdb/databases/bases_de_datos/lupajuridica/db_lupajuridica/mensual|
| 2:00 am (lun-sáb) | 38.242.195.66 (Soporte)                 | /backup_sdb/databases/bases_de_datos/soporte/soporte_lupa/diario/        |
| 2:00 am (lun-sáb) | 38.242.195.66 (DB)                      | /backup_sdb/databases/bases_de_datos/soporte/otros/diario/               |
| Semanal         | 38.242.195.66 (Soporte)                 | /backup_sdb/databases/bases_de_datos/soporte/soporte_lupa/semanal/       |
| Semanal         | 38.242.195.66 (DB)                      | /backup_sdb/databases/bases_de_datos/soporte/otros/semanal/              |
| Mensual         | 38.242.195.66 (Soporte)                 | /backup_sdb/databases/bases_de_datos/soporte/soporte_lupa/mensual/       |
| Mensual         | 38.242.195.66 (DB)                      | /backup_sdb/databases/bases_de_datos/soporte/otros/mensual/              |
| 1:00 am (diario)| 161.97.83.53 (MiprocesoJudicial)        | /backup_sdb/databases/bases_de_datos/miprocesojudicial/                  |
| 4:00 pm (diario)| 181.79.32.60 (Robots)                   | /backup_sdb/databases/bases_de_datos/robots/diario/                      |
| 8:00 am (diario)| Local                                   | /backup_sdb/databases/bases_de_datos/robots/ayer/                        |
| 9:00 pm (lun-sáb)| 181.79.32.58 (Tableros)                 | /backup_sdb/databases/bases_de_datos/tableros/diario/                    |
| Semanal         | 181.79.32.58 (Tableros)                 | /backup_sdb/databases/bases_de_datos/tableros/semanal/                   |
| Mensual         | 181.79.32.58 (Tableros)                 | /backup_sdb/databases/bases_de_datos/tableros/mensual/                   |

---
