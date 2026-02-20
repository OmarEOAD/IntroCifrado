# Sistema de Cifrado - César y Atbash

## Descripción

Sistema web interactivo para cifrar y descifrar mensajes utilizando dos métodos clásicos de criptografía: el cifrado César y el cifrado Atbash. Este proyecto demuestra los fundamentos de la criptografía histórica y permite experimentar con diferentes conjuntos de caracteres basados en código ASCII.

## Características

- **Dos métodos de cifrado**: César y Atbash
- **Conjunto de caracteres personalizable**: Define tu propio alfabeto para el cifrado
- **Interfaz intuitiva**: Diseño moderno y fácil de usar
- **Responsive**: Funciona en computadoras, tablets y móviles
- **Sin dependencias**: Ejecuta completamente en el navegador

## Cómo usar

### Cifrado César

1. Selecciona el método "Cifrado César" en la parte superior
2. Configura el desplazamiento (número de posiciones a mover)
3. Define el conjunto de caracteres que deseas usar
4. Escribe tu mensaje en el área de texto
5. Haz clic en "Cifrar" para encriptar o "Descifrar" para desencriptar

**Ejemplo:**
- Texto original: `HOLA`
- Desplazamiento: `3`
- Conjunto: `ABCDEFGHIJKLMNOPQRSTUVWXYZ`
- Resultado cifrado: `KROD`

### Cifrado Atbash

1. Selecciona el método "Cifrado Atbash"
2. Define el conjunto de caracteres
3. Escribe tu mensaje
4. Haz clic en "Cifrar / Descifrar" (la operación es la misma en ambos sentidos)

**Ejemplo:**
- Texto original: `HOLA`
- Conjunto: `ABCDEFGHIJKLMNOPQRSTUVWXYZ`
- Resultado: `SLOZ`

## Instalación

No requiere instalación. Simplemente abre el archivo `cifrado.html` en cualquier navegador web moderno, ademas de probarlo en GitHub Pages.

## Fundamentos Teóricos

### Cifrado César

El cifrado César es uno de los métodos de encriptación más antiguos y simples. Fue utilizado por Julio César para proteger mensajes militares. Funciona desplazando cada letra del mensaje un número fijo de posiciones en el alfabeto.

**Fórmula:**
```
Para cifrar: C = (P + k) mod n
Para descifrar: P = (C - k) mod n

Donde:
- P = posición del carácter original
- C = posición del carácter cifrado
- k = desplazamiento (clave)
- n = tamaño del conjunto de caracteres
```

### Cifrado Atbash

El cifrado Atbash es un método de sustitución monoalfabético que invierte el alfabeto. Su nombre proviene del alfabeto hebreo: Aleph (primera letra) se sustituye por Tav (última letra), Bet (segunda) por Shin (penúltima).

**Fórmula:**
```
C = n - 1 - P

Donde:
- P = posición del carácter original
- C = posición del carácter cifrado
- n = tamaño del conjunto de caracteres
```

## Seguridad

**IMPORTANTE**: Estos métodos son educativos y NO deben usarse para proteger información sensible. Son vulnerables a:

1. **Análisis de frecuencia**: Los patrones de letras comunes permanecen reconocibles
2. **Fuerza bruta**: Pocas claves posibles (25 en César)
3. **Ataques por diccionario**: Palabras comunes revelan el desplazamiento

Para protección real, usa algoritmos modernos como:
- AES (Advanced Encryption Standard)
- RSA (Rivest-Shamir-Adleman)
- ChaCha20-Poly1305

## Tecnologías Utilizadas

- HTML5
- CSS3 (con Flexbox y Grid)
- JavaScript (ES6+)
- Sin frameworks ni librerías externas

## Estructura del Código

```
cifrado_clasico.html
├── <head>
│   └── <style>              # Estilos CSS
├── <body>
│   ├── <div.container>      # Contenedor principal
│   │   ├── Título
│   │   ├── Selector de método
│   │   ├── Controles César
│   │   └── Controles Atbash
│   └── <script>             # Lógica JavaScript
│       ├── selectMethod()
│       ├── processCesar()
│       └── processAtbash()
```

## Funciones Principales

### `selectMethod(method)`
Cambia entre los modos César y Atbash, mostrando los controles correspondientes.

### `processCesar(mode)`
Procesa el texto con el algoritmo César. Parámetros:
- `mode`: 'encrypt' o 'decrypt'

### `processAtbash()`
Procesa el texto con el algoritmo Atbash. Como es simétrico, cifrar y descifrar son la misma operación.

## Ejemplos de Uso

### Ejemplo 1: Mensaje Simple
```
Método: César
Desplazamiento: 5
Conjunto: ABCDEFGHIJKLMNOPQRSTUVWXYZ
Entrada: ATACAR AL AMANECER
Salida: FYFHFW FQ FRFSHJHW
```

### Ejemplo 2: Con Números y Símbolos
```
Método: César
Desplazamiento: 3
Conjunto: ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789
Entrada: Clave123
Salida: Fodxh456
```

### Ejemplo 3: Atbash
```
Método: Atbash
Conjunto: ABCDEFGHIJKLMNOPQRSTUVWXYZ
Entrada: SECRETO
Salida: HVXIVGL
```

## Limitaciones Conocidas

1. Los caracteres fuera del conjunto definido no se cifran (permanecen sin cambios)
2. El desplazamiento en César debe ser un número positivo
3. Los espacios y puntuación se pueden incluir en el conjunto o dejarse sin cifrar

## Contribuciones

Este proyecto es de código abierto y acepta contribuciones. Para colaborar:

1. Haz un fork del repositorio
2. Crea una rama para tu característica (`git checkout -b feature/nueva-caracteristica`)
3. Commit tus cambios (`git commit -m 'Agregar nueva característica'`)
4. Push a la rama (`git push origin feature/nueva-caracteristica`)
5. Abre un Pull Request

## Historial de Cambios

### v1.0.0 (Febrero 2026)
- Implementación inicial
- Cifrado César con desplazamiento personalizable
- Cifrado Atbash
- Conjunto de caracteres personalizable
- Interfaz responsive
- Validación de entrada

## Licencia

Este proyecto se distribuye bajo licencia educativa. Libre para usar con fines académicos.

## Autor

Desarrollado como proyecto académico para la materia de Seguridad Informática.
Universidad Autonoma de Aguascalientes.

## Referencias

1. Kahn, D. (1996). *The Codebreakers*
2. Singh, S. (1999). *The Code Book*
3. Al-Kindi, Y. (Siglo IX). *Manuscrito sobre el Descifrado de Mensajes Criptográficos*
4. Menezes, A. J., et al. (1996). *Handbook of Applied Cryptography*

---

**Nota**: Este proyecto es para fines educativos. No utilices estos métodos para proteger información sensible en aplicaciones reales.
