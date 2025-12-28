  # 📊 Raspberry Monitoring

Ce dépôt contient la stack de **monitoring et supervision** du Raspberry Pi et des services Docker :

- Surveillance du Raspberry (CPU, RAM, Température, Disque)
- Surveillance des conteneurs Docker
- Dashboard graphique
- Alerting (mail / webhook / Telegram)

---

## 🎯 Objectif

Être alerté AVANT qu’un problème apparaisse :

- surchauffe
- saturation RAM
- disque plein
- conteneur en panne

---

## 🧱 Architecture

Stack envisagée (en fonction du choix final) :

```
/monitoring
  docker-compose.yml
  /config
  /data
```

Possibilités :
- Prometheus + Grafana
- Netdata
- combinaison légère

---

## 🚀 Déploiement

📌 via **GitHub Actions + Runner Raspberry**

Sur le Raspberry :

```
git clone https://github.com/....../raspberry-monitoring.git
cd raspberry-monitoring
docker compose up -d
```

---

## 🔔 Alerting

Support prévu :

- Email
- Webhook
- Telegram
- Discord / Slack

Configuration uniquement via `.env` local (jamais commitée).

---

## 🖥️ Accès

UI Monitoring accessible :

- `http://<IP_RASPBERRY>:PORT`
- ou via proxy :
  - `https://monitoring.mondomaine`

---

## 🔐 Sécurité

- accès restreint
- pas d’ouverture publique obligatoire
- mots de passe hors repo

---

## 📦 CI/CD

- workflow `workflow_dispatch`
- exécution runner `raspberry`
- `docker compose up -d`

---

## 🧭 Roadmap

- [ ] Choix stack finale
- [ ] Configuration alerting
- [ ] Dashboards personnalisés
- [ ] Proxy optionnel

---

## 📜 Licence

Usage personnel.
