A partir de las proto personas definidas dentro de [proto_personas], genera una tabla HTML para cada proto persona.

[proto_personas]
Aquí pega las proto personas con este formato:

Nombre y apellido:
Rol / tipo de usuario:
Descripción del rol:
Puntos de dolor:
Necesidades:
[/proto_personas]

## REGLAS OBLIGATORIAS:

1. Genera una tabla HTML por cada proto persona.
2. No agregues campos nuevos.
3. No elimines ningún campo.
4. No cambies el contenido de las proto personas.
5. Usa fondo blanco en todas las celdas.
6. Usa borde visible.
7. Usa rowspan="3" en la primera celda de cada tabla.
8. La primera celda debe contener:
   - Nombre y apellido
   - Rol / tipo de usuario

9. La segunda columna debe contener, en filas separadas:
   - Descripción del rol
   - Puntos de dolor
   - Necesidades

10. Centra vertical y horizontalmente el contenido de todas las celdas usando:

- vertical-align: middle;
- text-align: center;

11. No escribas explicaciones antes ni después.
12. Devuelve únicamente código HTML.

## FORMATO DE SALIDA:

<table border="1" cellspacing="0" cellpadding="14" style="border-collapse: collapse; width: 100%; font-family: Arial, sans-serif; background-color: white; margin-bottom: 24px;">
  <tbody>
    <tr>
      <td rowspan="3" style="width: 35%; background-color: white; vertical-align: middle; text-align: center;">
        <strong>Nombre y apellido:</strong><br>
        [Nombre y apellido]<br><br>

        <strong>Rol / tipo de usuario:</strong><br>
        [Rol / tipo de usuario]
      </td>

      <td style="background-color: white; vertical-align: middle; text-align: center;">
        <strong>Descripción del rol:</strong><br>
        [Descripción del rol]
      </td>
    </tr>

    <tr>
      <td style="background-color: white; vertical-align: middle; text-align: center;">
        <strong>Puntos de dolor:</strong><br>
        [Puntos de dolor]
      </td>
    </tr>

    <tr>
      <td style="background-color: white; vertical-align: middle; text-align: center;">
        <strong>Necesidades:</strong><br>
        [Necesidades]
      </td>
    </tr>

  </tbody>
</table>
