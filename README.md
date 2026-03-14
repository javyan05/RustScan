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

**RustScan** es una herramienta de escaneo de puertos escrita en **Rust** diseñada para ser extremadamente rápida. Su principal objetivo es acelerar el proceso de descubrimiento de puertos abiertos y posteriormente utilizar **Nmap** para realizar un análisis más profundo.

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
