# TDD Práctica — FizzBuzz y Validador de Contraseñas

Proyecto desarrollado como parte de la Semana 10 del curso **Construcción de Software** (Universidad Continental), aplicando TDD (Test-Driven Development) para construir dos módulos en Python desde cero.

## ¿Qué es TDD?

TDD es una práctica de desarrollo en la que las pruebas se escriben antes que el código de producción.

El ciclo se compone de tres fases:

1. **Red:** escribir un test que falle porque la funcionalidad todavía no existe.
2. **Green:** implementar el código mínimo necesario para que el test pase.
3. **Refactor:** mejorar el código sin alterar su comportamiento, manteniendo los tests en verde.

## Requisitos previos

- Python 3.10 o superior.
- `unittest`, incluido en la biblioteca estándar de Python.
- Git y una cuenta de GitHub.

Comprobar la versión de Python:

```bash
python --version
```

## Estructura del proyecto

```text
tdd-practica/
├── fizzbuzz/
│   ├── __init__.py
│   ├── fizzbuzz.py
│   └── test_fizzbuzz.py
├── validador/
│   ├── __init__.py
│   ├── validador.py
│   └── test_validador.py
└── README.md
```

**Nota:** los archivos `__init__.py` pueden estar vacíos. Permiten identificar las carpetas como paquetes Python y realizar imports.

## Ejercicio 1 — FizzBuzz

**Producción:** `fizzbuzz/fizzbuzz.py`  
**Tests:** `fizzbuzz/test_fizzbuzz.py`

La función `fizzbuzz(n)` recibe un entero y retorna:

- `"Fizz"` si es divisible por 3.
- `"Buzz"` si es divisible por 5.
- `"FizzBuzz"` si es divisible por 3 y por 5.
- `str(n)` en cualquier otro caso.

| Ciclo | Test | Funcionalidad |
|---|---|---|
| 1 | `test_numero_normal` | Retorna el número como texto. |
| 2 | `test_fizz` | Identifica múltiplos de 3. |
| 3 | `test_buzz` | Identifica múltiplos de 5. |
| 4 | `test_fizzbuzz` | Identifica múltiplos de 3 y 5. |
| 5 | `test_rango_completo` | Comprueba un rango mediante `subTest`. |

## Ejercicio 2 — Validador de contraseñas

**Producción:** `validador/validador.py`  
**Tests:** `validador/test_validador.py`

La función `validar_password(pwd)` retorna un diccionario con esta estructura:

```python
{
    "valida": True,
    "errores": []
}
```

Reglas de validación:

- Mínimo 8 caracteres.
- Al menos una letra mayúscula.
- Al menos una letra minúscula.
- Al menos un dígito.
- Al menos un carácter especial de `!@#$%^&*`.

| Ciclo | Tests | Funcionalidad |
|---|---|---|
| 1 | `test_password_muy_corta`, `test_password_longitud_ok` | Longitud mínima. |
| 2 | `test_sin_mayuscula` | Presencia de mayúsculas. |
| 3 | Según la implementación | Presencia de minúsculas. |
| 4 | Según la implementación | Presencia de dígitos. |
| 5 | Según la implementación | Presencia de caracteres especiales. |
| 6 | `test_password_valida_completa`, `test_multiples_errores`, `test_varios_passwords_con_subTest` | Validaciones integrales y refactorización. |

## Cómo ejecutar los tests

Desde la raíz del proyecto:

```bash
python -m unittest discover -v
python -m unittest fizzbuzz.test_fizzbuzz -v
python -m unittest validador.test_validador -v
```

## Herramientas utilizadas

- Python 3.10+
- `unittest`
- Visual Studio Code
- Git y GitHub

## Historial de desarrollo

Consultar los commits del repositorio:

```bash
git log --oneline
git log --stat
```

## Archivo .gitignore

Se recomienda ignorar los archivos generados por Python:

```gitignore
__pycache__/
*.py[cod]
```

## Autor

Oscar Pastor — Estudiante de Ingeniería de Sistemas e Informática, Universidad Continental, sede Cusco.
