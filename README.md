# SIGIP-Common

Librería compartida de SIGIP: seguridad JWT, formato único de errores, propagación del token en Feign
y contrato de eventos. No es un servicio que se ejecute; la usan auth, catalog, sales, design, production,
inventory, notification y report como dependencia Maven:

```xml
<dependency>
    <groupId>pe.edu.cibertec.sigip</groupId>
    <artifactId>sigip-common</artifactId>
    <version>0.0.1-SNAPSHOT</version>
</dependency>
```

## Instalar

Requisitos: Java 25 (Maven no hace falta, el repo trae `mvnw`).

```powershell
.\mvnw.cmd install -DskipTests
```

Esto deja el `.jar` en tu repositorio Maven local (`%USERPROFILE%\.m2`) y los demás servicios ya
pueden compilar. Repite el comando cada vez que cambies algo en esta librería.

En Docker no hace falta instalarla: cada servicio la compila dentro de su imagen
(`docker build --build-context common=..\SIGIP-Common ...`), y el CI de cada servicio la descarga de
GitHub desde `<tu-usuario>/SIGIP-Common`.
