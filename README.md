# 🐹 GOLANG DESDE CERO - GUÍA COMPLETA

**Golang desde Cero** es un sitio educativo completo diseñado para enseñar Go desde los fundamentos hasta conceptos avanzados, con explicaciones claras, ejemplos prácticos y código listo para usar.

> *"Go is an open source programming language supported by Google that makes it easy to build simple, reliable, and efficient software."*

---

## 🎯 ¿Qué es este Proyecto?

Este proyecto proporciona un recurso educativo gratuito para aprender Go, incluyendo:

- **Documentación completa** de cada tema
- **Ejemplos de código** listos para ejecutar
- **Ejercicios prácticos** para reforzar el aprendizaje
- **Sitio web educativo** con navegación intuitiva

---

## 📚 Contenido del Curso

### Módulo 1: Fundamentos

1. **Introducción**
   - Historia de Go
   - Filosofía del lenguaje
   - Casos de uso (Cloud, CLI, Microservicios)

2. **Instalación**
   - Go en Windows, Mac, Linux
   - Configuración de GOPATH y GOMOD
   - Go modules
   - IDEs recomendados (VS Code, GoLand)

3. **Conceptos básicos**
   - Variables y tipos de datos
   - Funciones múltiples returns
   - Control de flujo
   - Punteros básicos

### Módulo 2: Intermedio

4. **Ejemplos prácticos**
   - Structs y métodos
   - Interfaces
   - Manejo de errores
   - Concurrencia (goroutines, channels)

5. **Buenas prácticas**
   - Effective Go
   - Testing con testing package
   - Benchmarking
   - Documentación con godoc

### Módulo 3: Avanzado

6. **Casos reales**
   - APIs HTTP/REST
   - gRPC y Protocol Buffers
   - Microservicios
   - CLI tools con Cobra

7. **Proyecto final**
   - Servicio completo concurrente
   - Deploy con Docker
   - CI/CD pipeline

---

## 🗂️ Estructura del Proyecto

```
KRILIN-WORLD-UNITY/
├── index.html          # Página principal
├── css/
│   └── styles.css      # Estilos del sitio
├── js/
│   └── main.js         # JavaScript del sitio
└── README.md
```

---

## 🚀 Cómo Usar este Proyecto

### Opción 1: Navegar el Sitio Web

1. Abre `index.html` en tu navegador
2. Navega por las secciones del curso
3. Haz clic en los temas para ver la documentación detallada

### Opción 2: Ejecutar los Ejemplos

1. Instala Go desde go.dev
2. Crea archivo .go
3. Ejecuta con `go run archivo.go`

### Requisitos

- **Go 1.20** o superior
- Editor de código (VS Code con extensión Go)

---

## 📝 Ejemplos Rápidos

### Variables y Tipos

```go
package main

import "fmt"

func main() {
    var nombre string = "Juan"
    edad := 30
    const PI = 3.1416
    
    var (
        usuario = "admin"
        activo  = true
    )
    
    fmt.Println(nombre, edad, PI, usuario, activo)
}
```

### Funciones

```go
package main

import "fmt"

// Múltiples retornos
func dividir(a, b float64) (float64, error) {
    if b == 0 {
        return 0, fmt.Errorf("división por cero")
    }
    return a / b, nil
}

// Función variádica
func sumar(numeros ...int) int {
    total := 0
    for _, n := range numeros {
        total += n
    }
    return total
}
```

### Structs y Métodos

```go
package main

import "fmt"

type Persona struct {
    Nombre string
    Edad   int
}

func (p Persona) Saludar() string {
    return "Hola, soy " + p.Nombre
}

func (p *Persona) CumplirAnios() {
    p.Edad++
}

func main() {
    juan := Persona{Nombre: "Juan", Edad: 30}
    fmt.Println(juan.Saludar())
}
```

### Interfaces

```go
package main

import "fmt"

type Hablador interface {
    Hablar() string
}

type Persona struct {
    Nombre string
}

func (p Persona) Hablar() string {
    return "Hola, soy " + p.Nombre
}

func saludar(h Hablador) {
    fmt.Println(h.Hablar())
}
```

### Concurrencia

```go
package main

import (
    "fmt"
    "time"
)

func trabajador(id int, jobs <-chan int, results chan<- int) {
    for job := range jobs {
        results <- job * 2
    }
}

func main() {
    jobs := make(chan int, 10)
    results := make(chan int, 10)
    
    for w := 1; w <= 3; w++ {
        go trabajador(w, jobs, results)
    }
    
    for j := 1; j <= 5; j++ {
        jobs <- j
    }
    close(jobs)
    
    for r := 1; r <= 5; r++ {
        fmt.Println(<-results)
    }
}
```

---

## 🎓 Metodología de Aprendizaje

### 1. Leer la Teoría
Cada tema comienza con una explicación clara del concepto.

### 2. Ver Ejemplos
Los ejemplos de código muestran la aplicación práctica.

### 3. Practicar
Los ejercicios te permiten aplicar lo aprendido.

### 4. Experimentar
Modifica los ejemplos para entender cómo funcionan.

---

## 🔧 Comandos Esenciales

### Terminal/Consola

```bash
# Ver versión de Go
go version

# Inicializar módulo
go mod init mi-proyecto

# Descargar dependencias
go mod tidy

# Ejecutar programa
go run main.go

# Compilar
go build -o mi-app

# Ejecutar tests
go test ./...

# Formatear código
go fmt ./...
```

---

## 📖 Recursos Adicionales

### Documentación Oficial

- [Go Documentation](https://go.dev/doc/)
- [Go by Example](https://gobyexample.com/)
- [Effective Go](https://go.dev/doc/effective_go)

### Herramientas Recomendadas

- **VS Code** + Go extension
- **GoLand** - IDE profesional de JetBrains
- **golangci-lint** - Linter rápido
- **Delve** - Debugger para Go

### Comunidades

- [Go Community](https://go.dev/community/)
- [Stack Overflow - Go](https://stackoverflow.com/questions/tagged/go)
- [Reddit r/golang](https://www.reddit.com/r/golang/)

---

## 💡 Consejos para Principiantes

1. **Aprende el manejo de errores**: Es fundamental en Go.
2. **Usa goroutines temprano**: La concurrencia es poderosa.
3. **Sigue Effective Go**: Estilo consistente desde el inicio.
4. **Prueba todo**: Testing es primera clase en Go.
5. **Mantén simple**: Go valora simplicidad sobre complejidad.

---

## ⚠️ Mejores Prácticas

### Código Limpio

- Sigue Effective Go
- Usa nombres cortos pero descriptivos
- Maneja errores explícitamente

### Concurrencia

- Usa channels para comunicación
- Evita race conditions con `go test -race`
- Usa sync.WaitGroup cuando necesites esperar

### Rendimiento

- Usa benchmarks para medir
- Evita allocations innecesarias
- Pool de objetos cuando sea necesario

---

## 🧪 Ejercicios Prácticos

### Nivel Básico

1. Calculadora de operaciones básicas
2. Conversor de temperaturas
3. Juego de adivinar números

### Nivel Intermedio

1. API REST con net/http
2. CLI tool para procesar archivos
3. Worker pool concurrente

### Nivel Avanzado

1. Microservicio con gRPC
2. Sistema distribuido con channels
3. Herramienta de monitoring

---

## 👨‍💻 Desarrollado por Isaac Esteban Haro Torres

**Ingeniero en Sistemas · Full Stack · Automatización · Data**

- 📧 Email: zackharo1@gmail.com
- 📱 WhatsApp: 098805517
- 💻 GitHub: https://github.com/ieharo1
- 🌐 Portafolio: https://ieharo1.github.io/portafolio-isaac.haro/

---

© 2026 Isaac Esteban Haro Torres - Todos los derechos reservados.
