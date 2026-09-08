![Static Badge](https://img.shields.io/badge/%F0%9F%A6%85%F0%9F%A6%85%F0%9F%A6%85%20Condor2026%20%E2%80%93%20Threat%20Investigator%20%F0%9F%A6%85%F0%9F%A6%85%F0%9F%A6%85-red)

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=28&duration=3000&pause=500&color=00FF00&center=true&vCenter=true&width=600&lines=Report+Malicius+REPOS+%7C+Threat+Hunter;OSINT+%7C+Purple+Team;Andr%C3%B3MEDA+%5BCTI%5D;Condor+Project+%5BIncidenct%5D;Threat+Intelligence+CYBER+SEC" alt="Typing animation" />
</p>

# 🛡️ Condor Project
### *Malicious Repository Threat Intelligence & Incident Registry*

---

## ⚠️ DISCLAIMER IMPORTANTE (LÉEME)
**Este repositorio NO contiene, distribuye ni promociona el malware "GhostSocks" ni ningún otro código malicioso.**  
El nombre del proyecto, *"GhostSocks"*, hace referencia al **primer caso documentado** (la campaña de suplantación de GLM-5.3).  
Todo el contenido aquí alojado tiene fines **exclusivamente de investigación, educación y defensa cibernética (CTI)**.  
Si eres un actor malicioso, este no es tu lugar. Si eres un defensor, bienvenido.

---

## 🎯 Misión
Centralizar y estandarizar informes técnicos de alta calidad sobre **repositorios falsos/infectados** (GitHub, GitLab, etc.) que utilizan:
- Typosquatting (nombres muy parecidos a proyectos legítimos).
- Suplantación de software popular (IA, herramientas Dev, cripto-wallets).
- Envenenamiento de la cadena de suministro (Supply Chain).

Nuestro objetivo es proporcionar **IOCs accionables** y **contexto táctico** a la comunidad de seguridad para frenar estas campañas.

---

## 📂 Estructura del Repositorio

| Carpeta | Contenido |
| :--- | :--- |
| **`/reports/`** | Informes completos en Markdown/PDF. Cada uno cubre un caso específico (familia + campaña). |
| **`/iocs/`** | Archivos CSV, JSON o STIX con los Indicadores de Compromiso (hashes, IPs, dominios). |
| **`/yara/`** | Reglas YARA para detectar las familias de malware documentadas. |
| **`/scripts/`** | Scripts auxiliares (ej. para consultar VT, extraer configs, o generar gráficos). |
| **`/assets/`** | Capturas de pantalla, logs de sandbox o diagramas de red. |

---

## 📌 Casos Documentados (Registro)

| # | Caso / Campaña | Malware | Repositorio Falso | Fecha de publicación |
| :--- | :--- | :--- | :--- | :--- |
| **001** | **Fake GLM-5.3 "One-Click" Installer** | GhostSocks + Stealer | `github.com/GLM-5-3-app/GLM-5.3` | 2026-09-08 |
| **002** | *[En investigación - Pendiente de publicación]* | *TBD* | *TBD* | *Próximamente* |

*(¿Tienes un caso para añadir? ¡Abre un Issue o haz un Pull Request!)*

---

## 🧠 Cómo usar este repositorio
1. **Para defenders/Blue Team:** Consulta la carpeta `/iocs/` para bloquear en firewalls/EDR. Lee los informes para entender las TTPs y ajustar tus reglas de correlación.
2. **Para investigadores:** Revisa la metodología en los informes. Si replicas el análisis, puedes contrastar resultados.
3. **Para desarrolladores:** Si mantienes paquetes en GitHub, usa estos informes para educar a tu equipo sobre cómo detectar repositorios impostores.

---

## 🤝 Contribuciones
Las contribuciones son bienvenidas y necesarias. Para colaborar:
1. **Reporta un nuevo repositorio falso** abriendo un **Issue** con la URL y el hash del archivo.
2. **Envía un informe completo** mediante un **Pull Request** siguiendo la plantilla base (próximamente en `/templates/`).
3. **Comparte IOCs** aunque no tengas el informe completo; los agregaremos a la base de datos.

---

## 📜 Licencia y Ética
Este proyecto se publica bajo licencia **MIT** para fomentar su uso en la comunidad.  
**Recuerda:** El uso de estos datos para atacar sistemas es ilegal y va contra el espíritu de este proyecto. Úsalo solo para **fortalecer defensas**.

---

## 🌐 Enlaces de interés / Fuentes
- [VirusTotal](https://www.virustotal.com)
- [ANY.RUN](https://any.run)
- [MITRE ATT&CK](https://attack.mitre.org)

---

**Última actualización:** 08 de septiembre de 2026  
**Mantenido por:** [Tu nombre o alias] - ¡Gracias por visitarnos!
