# Lab 01 — Reconocimiento de Red con Nmap

## 🎯 Objetivo
Realizar un reconocimiento básico de red usando herramientas 
estándar de pentesting en un entorno controlado (Kali Linux en VM).

## 🛠️ Herramientas utilizadas
- Kali Linux (VirtualBox)
- Nmap 7.98

## 📋 Pasos realizados

### 1. Reconocimiento de interfaces de red
```bash
ip a
```
Resultado: IP asignada 10.0.2.15 en interfaz eth0.

### 2. Descubrimiento de hosts activos
```bash
nmap -sn 10.0.2.0/24
```
Resultado: 3 hosts activos encontrados (10.0.2.2, 10.0.2.3, 10.0.2.15).

### 3. Escaneo de puertos y servicios
```bash
nmap 10.0.2.2
```
Resultado: 4 puertos abiertos detectados.

| Puerto | Servicio | Descripción |
|--------|----------|-------------|
| 135/tcp | msrpc | Microsoft RPC |
| 445/tcp | microsoft-ds | SMB - Compartir archivos |
| 5357/tcp | wsdapi | Descubrimiento Windows |
| 6881/tcp | bittorrent-tracker | Torrents |

## 🔍 Conclusiones
- El host 10.0.2.2 es una máquina Windows
- El puerto 445 (SMB) es históricamente crítico en seguridad
  (explotado por WannaCry en 2017)
- Reconocimiento completado sin generar tráfico intrusivo

## 📚 Conceptos aprendidos
- Diferencia entre host discovery y port scanning
- Interpretación de resultados de Nmap
- Identificación de servicios por número de puerto

## ⚠️ Entorno
Lab realizado en red virtual controlada (VirtualBox).
Nunca escanear redes sin autorización explícita.
