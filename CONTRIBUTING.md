# Guía para Contribuir a Malicious Repo CTI

¡Gracias por querer ayudar a la comunidad! Este repositorio vive de los reportes de investigadores como tú.

## 🔍 ¿Qué tipo de contribuciones se aceptan?

- **Reporte de nuevos repositorios falsos:** Si encuentras un repositorio que distribuye malware o suplanta un proyecto legítimo.
- **Informes técnicos completos:** Si has analizado una muestra y quieres compartir tu trabajo.
- **IOCs adicionales:** Hashes, IPs, dominios que hayas identificado.
- **Reglas YARA o consultas Sigma:** Para ayudar a otros a detectar la amenaza.

## 📝 Formato para reportar un nuevo repositorio falso (via Issue)

1. Ve a la pestaña **Issues** y crea uno nuevo.
2. Usa este formato:

```markdown
**URL del repositorio:** https://github.com/falso-ejemplo/malware
**Proyecto que suplanta:** (ej. GLM-5.3, OpenClaw, etc.)
**Hash SHA256 del archivo malicioso:** (si lo tienes)
**Fecha de descubrimiento:** YYYY-MM-DD
**Descripción:** (qué técnica usan, typosquatting, README falso, etc.)
**Evidencia adicional:** (capturas de pantalla, enlaces a VirusTotal, etc.)
