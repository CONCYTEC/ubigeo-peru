## Concordancia de los códigos de UBIGEO de INEI, RENIEC y SUNAT

Datos de concordancia/equivalencia entre los códigos y nombres de locaciones
(Departamentos, Provincias y Distritos) del Perú, en función a los UBIGEO empleados
por INEI, RENIEC y SUNAT.

En el caso de SUNAT, se han obtenidos estos valores de un archivo en formato
MS Excel publicado en su sitio web.

Los datos de INEI y de RENIEC provienen de sus fuentes oficiales públicas.

La tabla de equivalencias se presenta en formato CSV y en SQL, en el segundo
caso, el esquema sugerido es el siguiente:

```{sql}
CREATE TABLE ubigeo(
   cod_dep_inei       CHAR(2),
   desc_dep_inei      VARCHAR(13),
   cod_prov_inei      CHAR(4),
   desc_prov_inei     VARCHAR(25),
   cod_ubigeo_inei    CHAR(6),
   desc_ubigeo_inei   VARCHAR(36),
   cod_dep_reniec     CHAR(2),
   desc_dep_reniec    VARCHAR(23),
   cod_prov_reniec    CHAR(4),
   desc_prov_reniec   VARCHAR(25),
   cod_ubigeo_reniec  CHAR(6),
   desc_ubigeo_reniec VARCHAR(30),
   cod_dep_sunat      CHAR(2),
   desc_dep_sunat     VARCHAR(23),
   cod_prov_sunat     CHAR(4),
   desc_prov_sunat    VARCHAR(25),
   cod_ubigeo_sunat   CHAR(6),
   desc_ubigeo_sunat  VARCHAR(36)
);
```

Se podría usar el campo `cod_dep_inei` como llave primaria, pero primero se 
deben de eliminar dos locaciones que SUNAT y RENIEC marcan como Distritos, pero
que en realidad no lo son (ver mas detalles en la sección "Notas")

### Versiones
- Versión 1.0
	- Fecha: 2016-12-14
	- Preparada por: Henry Yovanni Francisco Carpio
      (Administrador de Bases de Datos, OTI, CONCYTEC)

### Fuentes de datos 

- *INEI*:
  http://webinei.inei.gob.pe:8080/sisconcode/proyecto/index.htm?proyectoTitulo=UBIGEO&proyectoId=3
- *RENIEC*:
  https://www.reniec.gob.pe/Adherentes/jsp/ListaUbigeos.jsp
- *SUNAT*:
  http://www2.sunat.gob.pe/pdt/pdtModulos/independientes/p601/Anexo2-Tablas260510.xls

Datos descargados desde las fuentes primarias el 2016-12-07

### Notas

- INEI tiene el conjunto de datos mas completo, incluyendo los distritos
  creados recientemente.
- RENIEC e INEI difieren a nivel de departamentos a partir de Callao,
  posiblemente porque INEI lo denomina "CALLAO" y RENIEC usa el nombre
  "PROV. CONST. DEL CALLAO". Esto hace que el código de INEI sea "07",
  y el de RENIEC "24", pues ambas listas parecen usar el orden alfabético
  de los departamentos.
- SUNAT parece usar una mezcla de códigos de INEI, con nombres/denominaciones
  de RENIEC en algunos casos. En el caso de Callao, por ejemplo, los nombra
  como lo hace RENIEC, y usa el código de INEI.
- INEI parece usar una codificación (generalmente) secuencial y en orden
  alfabético para las provincias dentro de un departamento y los distritos
  dentro de una provincia. No se discierne un patrón similar para RENIEC.
- Existen dos distritos que no existen en INEI, pero que si existen uno en 
  SUNAT y el otro en RENIEC:
	- *SUNAT*: 131103 (LA LIBERTAD, GRAN CHIMU, COMPIN). Es una localidad del
      distrito de Marmot, y no un distrito.
    - *RENIEC*: 140606 (LIMA, HUAROCHIRI, SAN JOSE DE LOS CHORRILLOS). Este
      distrito no existe desde 1935 cuando se separó en Antioquia y Cuenca.

### Copyright

2016 -- Consejo Nacional de Ciencia, Tecnología e Innovación Tecnológica (CONCYTEC)

### Licencia

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img
alt="Creative Commons License" style="border-width:0"
src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />Este trabajo
está licenciado bajo <a rel="license"
href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution
4.0 International License</a>.
