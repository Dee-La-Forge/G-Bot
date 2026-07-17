# G-Bot

Chart de trading autonome en **un seul fichier** — aucun build, aucune dépendance installée.

![logo](lwc-minimal/logo.png)

## Lancer

Ouvrir `lwc-minimal/index.html` dans un navigateur (double-clic suffit, connexion internet requise), ou servir le dossier :

```bash
python -m http.server 8749 --directory lwc-minimal
# http://localhost:8749/index.html
```

## Fonctionnalités

- **Binance Futures Perpetual** (USDT-M) : 28 paires prédéfinies + saisie libre, 15 timeframes natifs (1m → 1M)
- **Temps réel** : WebSocket `fstream` avec bascule automatique en polling REST (2 s) si le flux est muet ou injoignable, rattrapage des trous après veille/coupure
- **Replay** façon TradingView : rideau de sélection du départ, lecture/pause/pas-à-pas, vitesses 0,25× → 10×
- **Outils de dessin** éditables (sélection, déplacement, poignées, couleurs/épaisseur/style) : tendance, rayon, flèche, lignes H/V, rayon horizontal, canal parallèle, pinceau, rectangle, ellipse, Fibonacci, texte, règle de mesure, positions long/short (R/R), aimant OHLC, gomme
- **Persistance** : tracés ancrés en temps absolu (survie aux changements de timeframe), sauvegardés par symbole en localStorage ; thème mémorisé
- **Indicateur** : ATR 233 lissé SMA dans la zone volume ; historique infini au scroll gauche ; compte à rebours de clôture soudé au prix
- **Thèmes** : clic droit sur le chart (Noir & Or, Classique, Nuit, Ivoire + couleurs personnalisées)

## Stack

[TradingView Lightweight Charts v5](https://github.com/tradingview/lightweight-charts) (CDN épinglé + SRI) · API Binance Futures publique · HTML/CSS/JS vanille.
