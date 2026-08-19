+++
draft = false
title = 'Sécurité'
weight = 5
+++

## HTTP et HTTPS (Avec chiffrement)

Durant les premières années sur Internet, les pages web n'étaient pas sécurisées pour la plupart. On pouvait lire une page HTTP sans chiffrement. Les pages qui offraient alors la possibilité d'entrer des données sensibles pouvaient chiffrer celles-ci avec le protocol HTTPS qui inclus le chiffrement à l'aide du protocole appelé Transport Layer Security (TLS) qui était auparavant connu sous le nom de Secure Sockets Layer (SSL).

De nos jours, il est très rare de retrouver une page sans chiffrement.

### Risque avec HTTP

Dans les sites web sans HTTPS, il est possible pour les fournisseurs de services Internet (FAI) ou d'autres intermédiaires d'injecter du contenu dans des pages web sans l'approbation du propriétaire du site. Ce contenu a souvent la forme de publicité, lorsqu'un FAI cherchant à augmenter ses revenus injecte de la publicité payante dans les pages web de ses clients. Sans surprise, lorsque cela se produit, les bénéfices issus des annonces publicitaires et le contrôle qualité de ces annonces ne sont en aucun cas partagés avec le propriétaire du site. HTTPS élimine la capacité des tiers non modérés à injecter de la publicité dans du contenu web.


![HTTP](https://www.cloudflare.com/img/learning/security/glossary/what-is-https/not-secure.png)

![HTTPS](https://wecomm.fr/wp-content/uploads/comment-fonctionne-https-ssl.jpg)


Source: https://www.cloudflare.com/fr-fr/learning/ssl/what-is-https/