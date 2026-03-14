# RustScan - Guía Técnica

Guía técnica de **RustScan**, una herramienta de escaneo de puertos extremadamente rápida utilizada en **reconocimiento de redes y pentesting**.

---

# Índice

- [Introducción](#introducción)
- [Características](#características)
- [Instalación](#instalación)
- [Uso básico](#uso-básico)
- [Opciones principales](#opciones-principales)
- [Integración con Nmap](#integración-con-nmap)
- [Ejemplos prácticos](#ejemplos-prácticos)
- [Buenas prácticas](#buenas-prácticas)
- [Estructura del repositorio](#estructura-del-repositorio)
- [Conclusión](#conclusión)
- [Referencias](#referencias)

---

# Introducción

**RustScan** es una herramienta de escaneo de puertos escrita en **Rust** diseñada para ser extremadamente rápida. Su objetivo es acelerar el proceso de descubrimiento de puertos abiertos y posteriormente utilizar **Nmap** para realizar un análisis más profundo.

RustScan permite escanear **todos los puertos de un host en pocos segundos**, lo que lo convierte en una herramienta muy útil para:

- Pentesting
- Auditorías de seguridad
- Reconocimiento de redes
- Enumeración de servicios

Repositorio oficial:

https://github.com/RustScan/RustScan

---

# Características

Principales características de RustScan:

- Escaneo de puertos extremadamente rápido
- Desarrollado en **Rust**
- Integración automática con **Nmap**
- Configuración flexible
- Control del número de conexiones simultáneas
- Compatible con Linux, Windows y macOS

Comparación de velocidad:

| Herramienta | Velocidad |
|-------------|-----------|
| Nmap | Media |
| Masscan | Muy alta |
| RustScan | Muy alta |

---

# Instalación

## Instalación en Linux (Debian / Ubuntu / Kali)

Descargar el paquete:

```bash
wget https://github.com/RustScan/RustScan/releases/download/2.1.1/rustscan_2.1.1_amd64.deb
```

Instalar:

```bash
sudo dpkg -i rustscan_2.1.1_amd64.deb
```

Verificar instalación:

```bash
rustscan --version
```

![RustScan version](https://github.com/javyan05/RustScan/blob/main/images/Rustscan_version.png)

---

## Instalación con Cargo

Si tienes Rust instalado:

```bash
cargo install rustscan
```

---

## Instalación con Docker

Descargar imagen:

```bash
docker pull rustscan/rustscan
```

Ejecutar:

```bash
docker run rustscan/rustscan:latest -a 192.168.1.1
```

---

# Uso básico

Ejecutar RustScan contra una dirección IP:

```bash
rustscan -a 192.168.1.1
```

RustScan realizará:

1. Escaneo rápido de puertos
2. Envío automático de los puertos abiertos a **Nmap**



```bash
rustscan -a <IP_objetivo>
```

![RustScan basic scan](https://github.com/javyan05/RustScan/blob/main/images/basic_scan.png)

---

# Opciones principales

| Opción | Descripción |
|------|------|
| `-a` | Dirección IP objetivo |
| `-p` | Puertos específicos |
| `-r` | Rango de puertos |
| `-u` | Escaneo UDP |
| `--ulimit` | Ajusta el número máximo de archivos abiertos |
| `-b` | Tamaño del batch |

Ejemplo:

```bash
rustscan -a 192.168.1.1 -r 1-1000
```

---

# Integración con Nmap

RustScan permite ejecutar **Nmap automáticamente** sobre los puertos abiertos.

Ejemplo:

```bash
rustscan -a 192.168.1.1 -- -sV -sC
```

Explicación:

- `--` separa los argumentos de RustScan y Nmap
- `-sV` detecta versiones de servicios
- `-sC` ejecuta scripts básicos de Nmap

Ejecutar:

```bash
rustscan -a <IP> -- -sV -sC
```

![RustScan with Nmap](https://github.com/javyan05/RustScan/blob/main/images/rustscan_nmap.png)


---

# Ejemplos prácticos

## Escaneo completo de puertos

```bash
rustscan -a 192.168.1.1 -r 1-65535
```

---

## Escaneo de puertos específicos

```bash
rustscan -a 192.168.1.1 -p 22,80,443
```

---

## Escaneo avanzado con Nmap

```bash
rustscan -a 192.168.1.1 -- -A
```

La opción `-A` activa:

- detección de sistema operativo
- detección de versiones
- traceroute
- scripts de Nmap

---

# Buenas prácticas

Para obtener mejores resultados:

Ejecutar con privilegios de administrador:

```bash
sudo rustscan -a 192.168.1.1
```

Usar RustScan como **fase inicial de reconocimiento**.

Flujo típico en pentesting:

```
RustScan → Nmap → Enumeración → Explotación
```

---

# Estructura del repositorio

Estructura recomendada:

```
rustscan-guide
│
├── README.md
└── images
    ├── rustscan_version.png
    ├── basic_scan.png
    └── rustscan_nmap.png
```

---

# Conclusión

RustScan es una herramienta moderna que mejora significativamente la velocidad del reconocimiento de puertos. Su integración con Nmap permite combinar **velocidad y profundidad de análisis**, convirtiéndola en una herramienta muy útil para profesionales de ciberseguridad.

---

# Referencias

RustScan GitHub  
https://github.com/RustScan/RustScan

Documentación oficial  
https://rustscan.github.io/RustScan/
