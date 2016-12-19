## Concordancia de los códigos de UBIGEO de INEI, RENIEC y SUNAT

Versión: 2016-12-14

Fuentes de datos (descargadas el 2016-12-07):

*INEI*:
http://webinei.inei.gob.pe:8080/sisconcode/proyecto/index.htm?proyectoTitulo=UBIGEO&proyectoId=3

*RENIEC*:
https://www.reniec.gob.pe/Adherentes/jsp/ListaUbigeos.jsp

*SUNAT*:
http://www2.sunat.gob.pe/pdt/pdtModulos/independientes/p601/Anexo2-Tablas260510.xls

**Notas**:

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

