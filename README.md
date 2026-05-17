# 🍯 HoneyNet Deployment — SOC Lab

<img src="https://img.shields.io/badge/Status-Actif-E8000D?style=for-the-badge" />
<img src="https://img.shields.io/badge/Type-Blue%20Team%20Lab-0A0A0A?style=for-the-badge" />
<img src="https://img.shields.io/badge/Niveau-Junior%20SOC-006747?style=for-the-badge" />

---

## 📌 Objectif

Déployer un environnement honeypot complet pour capturer, analyser et visualiser des attaques réelles sur internet. Ce lab simule un environnement SOC où les alertes sont générées, triées et documentées comme dans un vrai centre de supervision.

---

## 🧰 Outils utilisés

| Outil | Rôle |
|---|---|
| **T-Pot** | Plateforme honeypot multi-services |
| **Kibana** | Visualisation des attaques en temps réel |
| **Elasticsearch** | Stockage et indexation des logs |
| **Suricata** | Détection d'intrusion réseau (IDS) |
| **VirtualBox / VM** | Environnement isolé pour le déploiement |

---

## 🏗️ Architecture du lab

```
Internet
    │
    ▼
[VM Honeypot - T-Pot]
    │
    ├── SSH Honeypot     → capture brute-force
    ├── HTTP Honeypot    → capture scans web
    ├── FTP Honeypot     → capture tentatives FTP
    └── Suricata IDS     → détection d'intrusion
    │
    ▼
[Elasticsearch]
    │
    ▼
[Kibana Dashboard]  → visualisation des attaques
```

---

## 📋 Étapes réalisées

### Étape 1 — Préparation de la VM
- Création d'une machine virtuelle sous Debian/Ubuntu
- Configuration réseau en mode Bridge pour exposition sur internet
- Allocation des ressources : 8GB RAM, 128GB stockage

### Étape 2 — Installation de T-Pot
```bash
git clone https://github.com/telekom-security/tpotce
cd tpotce
sudo ./install.sh
```
- Sélection du mode **HIVE** pour activer tous les honeypots
- Configuration des ports exposés

### Étape 3 — Surveillance des attaques
- Accès au dashboard Kibana sur `https://[IP]:64297`
- Observation des premières attaques en moins de 10 minutes après déploiement
- Types d'attaques capturées :
  - SSH brute-force (le plus fréquent)
  - Scans de ports
  - Tentatives d'exploitation HTTP

### Étape 4 — Analyse des logs
- Identification des IPs sources des attaques
- Géolocalisation des attaquants via Kibana
- Extraction des IOC (Indicators of Compromise)
- Documentation des patterns d'attaque

### Étape 5 — Rapport d'incident
- Triage des alertes par criticité
- Rédaction d'un rapport d'analyse
- Identification des Top 10 IPs malveillantes

---

## 📊 Résultats obtenus

| Métrique | Résultat |
|---|---|
| Attaques SSH capturées | 500+ tentatives / heure |
| Pays sources identifiés | 30+ pays |
| IOC extraits | 200+ IPs malveillantes |
| Protocoles attaqués | SSH, HTTP, FTP, Telnet |

---

## 📸 Screenshots

> *Screenshots à ajouter : dashboard Kibana, carte des attaques, logs Suricata*

---

## 🎯 Compétences développées

- ✅ Déploiement d'infrastructure de sécurité
- ✅ Analyse de logs et triage d'alertes
- ✅ Visualisation de données sécurité avec Kibana
- ✅ Extraction et documentation d'IOC
- ✅ Rédaction de rapports d'incidents

---

## 🔗 Liens utiles

- [T-Pot GitHub](https://github.com/telekom-security/tpotce)
- [Portfolio complet](https://github.com/Amet-19/Portfolio-de-Mohamed-Lamine-Sow)
- [LinkedIn](https://www.linkedin.com/in/mohamed-lamine-sow/)

---

*Lab réalisé par **Mohamed Lamine Sow** — Junior SOC Analyst · Dakar, Sénégal*
