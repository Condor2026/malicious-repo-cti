INFORME CTI BÁSICO – FASE PRIMARIA  
Amenaza: Distribución de GhostSocks vía repositorio GitHub falso “GLM-5.3”  
Fecha del informe: 08 de septiembre de 2026  
Clasificación: TLP:WHITE (información pública)  
Autor / Fuente inicial: Análisis colaborativo (OpcodeIntel + Panda_Sec_Intel)  
Estado: Fase primaria (recolección de IOCs y contexto). Pendiente de análisis dinámico/estático profundo y expansión de indicadores.

1. Resumen Ejecutivo
Se identifica un repositorio malicioso en GitHub (GLM-5-3-app/GLM-5.3) que se hace pasar por un instalador “one-click” del modelo legítimo de IA GLM-5.3 (Z.ai). El payload principal es un ejecutable Windows (~109 MB) detectado como familia GhostSocks (troyano/proxy SOCKS5 backconnect + capacidades de stealer/backdoor).  
El objetivo es convertir las máquinas de las víctimas en proxies residenciales y/o robar información. Campaña activa al momento del informe.

2. Descripción de la Amenaza
Nombre / Alias:** Fake GLM-5.3 Installer / PhalanxShield.exe / GLM-5.3-x64.exe  
Familia principal:** GhostSocks (Golang-based SOCKS5 backconnect proxy malware, ofrecido como MaaS).  
Capacidades observadas (según detecciones y reports públicos de la familia):**  
  Proxy SOCKS5 residencial (permite a actores enrutar tráfico malicioso).  
  Posible stealer / backdoor / privilege escalation / persistence.  
  Evasión de sandbox y herramientas de seguridad.  
Motivación:** Monetización de bots como proxies + posible robo de credenciales/datos (común en integraciones GhostSocks + stealers).

3. Vector de Distribución / Initial Access
Repositorio GitHub legítimo en apariencia: https://github.com/GLM-5-3-app/GLM-5.3  
Se presenta como “GLM-5.3 — The #1 Open-Weights Coding Model, One Click to Install”.  
Ofrece descargas directas:  
  Windows: GLM-5.3-x64.7z → ejecuta GLM-5.3-x64.exe  
  macOS: GLM-5.3-macOS-arm64.dmg  
Técnicas: Impersonación de software/IA popular + SEO/GitHub para atraer descargas.  
Primer aviso público: @OpcodeIntel (hash relacionado b490a223f931af6efe4be92dfdef4622).

4. Indicadores de Compromiso (IOCs) – Fase Primaria

Archivos  
Nombre: GLM-5.3-x64.exe / PhalanxShield.exe  
Tamaño: ≈ 109.37 MB  
SHA256: 0f6c506f7616965500f242819fb13aee6459fad1e08624b871219b2859b0a493  
VirusTotal: 22/69 detecciones (Troyano / Dropper / Agent / Evo-gen, etc.)  
Community Score: negativo  
Hash adicional reportado en aviso inicial: b490a223f931af6efe4be92dfdef4622 (probable MD5 de archivo/archivo comprimido relacionado)

Red (C2 observados en este sample y muestras relacionadas de GhostSocks)  
147.45.197.92:443  
194.28.225.230:443  
94.228.161.88:443  

Otros  
Repositorio: github.com/GLM-5-3-app/GLM-5.3  
Posibles nombres de proceso / rutas: relacionadas con “PhalanxShield”, instaladores one-click de modelos de IA.

5. TTPs preliminares (MITRE ATT&CK – alto nivel)
Initial Access: T1189 (Drive-by) / T1195 (Supply Chain – falso software) / T1608 (Stage Capabilities vía GitHub)  
Execution: T1204 (User Execution)  
Persistence / Privilege Escalation: posibles (comunes en GhostSocks)  
Defense Evasion: anti-sandbox, ofuscación  
Command and Control: T1090 (Proxy) – SOCKS5 backconnect  
Collection / Exfiltration: posible (stealer capabilities)

6. Contexto de la familia GhostSocks
Malware Golang ofrecido como MaaS desde ~2023-2024. Especializado en convertir víctimas en proxies residenciales. Frecuentemente desplegado junto a stealers (Lumma, Vidar, etc.). Usa arquitectura de relay + C2 para dificultar takedowns. Actividad documentada en 2025-2026 con múltiples campañas vía repos falsos de herramientas/IA.

7. Recomendaciones inmediatas (fase primaria)
Bloquear los IOCs de red y hash en firewalls/EDR/proxies.  
Monitorear descargas desde GitHub de archivos .7z/.exe/.dmg relacionados con “GLM-5.3”, “one click”, “open-weights coding model”.  
No ejecutar instaladores de modelos de IA desde fuentes no oficiales (usar solo Hugging Face / sitios oficiales de Z.ai).  
Revisar sistemas que hayan descargado el archivo por conexiones salientes a los C2 listados y procesos sospechosos.  
Reportar el repositorio a GitHub.

8. Próximos pasos recomendados (para expandir el informe)
Análisis dinámico completo (sandbox) + extracción de config embebida.  
Búsqueda de más samples relacionados (similares hashes, imphash, strings).  
Identificación de más C2 / dominios / afiliados.  
Mapeo completo MITRE + YARA rules.  
Correlación con otras campañas de GhostSocks 2026.  
Monitoreo de actividad del repositorio y posibles mirrors.

Fuentes primarias usadas:  
VirusTotal (análisis del sample), captura de comentarios comunitarios, repositorio GitHub malicioso, reportes públicos de familia GhostSocks (Triage, MalwareBazaar, Darktrace, etc.), aviso inicial de @OpcodeIntel y análisis de @Panda_Sec_Intel.

Este es el esqueleto de fase primaria. Regresaré con más datos.
