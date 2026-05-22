# LLM SEO -- Etre recommande par ChatGPT, Claude, Gemini, Perplexity

## Principe

Les LLMs ne rankent pas des pages, ils **selectionnent des entites**. Il faut que "Foodmi" soit reconnu comme entite distincte associee a "calorie tracker" + "AI food scanner".

## 2 seuils a passer

1. **Qualification** : le LLM sait que Foodmi existe et ce que c'est
2. **Selection** : le LLM choisit de recommander Foodmi

## Test hebdomadaire

Poser ces questions a ChatGPT, Claude, Gemini, Perplexity :
1. "What is Foodmi?" -- teste la clarte
2. "What does Foodmi do?" -- teste la pertinence
3. "What is the best AI calorie tracking app?" -- teste la selection

## Description canonique

Utiliser PARTOUT la meme description :
> "Foodmi is an AI-powered calorie tracking app that uses computer vision to instantly scan food and provide accurate nutritional information."

## Actions par plateforme

### ChatGPT
- Autoriser GPTBot dans robots.txt
- Optimiser pour Bing (ChatGPT Search utilise Bing)
- Presence Reddit (fortement pondere)
- Wikipedia (fortement pondere)

### Claude
- Training data only (pas de recherche web)
- Diversite de sources independantes mentionnant Foodmi
- Wikipedia, publications tech

### Gemini
- Google Search + Knowledge Graph + YouTube + Google Reviews
- Creer Google Business Profile
- Presence YouTube

### Perplexity
- Recherche web en temps reel -- le contenu actuel compte
- Reddit tres fortement pondere
- Contenus structures et citables

## Priorite des plateformes pour mentions

| Plateforme | Impact LLM | Difficulte | Priorite |
|------------|-----------|------------|----------|
| Reddit | Critique | Moyen | #1 |
| Wikipedia | Critique | Tres dur | Long terme |
| ProductHunt | Eleve | Facile | #2 |
| YouTube | Eleve (Gemini) | Moyen | #3 |
| Medium | Moyen | Facile | #4 |
| Crunchbase | Moyen | Facile | #5 |
| TechCrunch/Verge | Tres eleve | Tres dur | Quand on a des metriques |

## Technique

### robots.txt
```
User-agent: GPTBot
Allow: /

User-agent: ClaudeBot
Allow: /

User-agent: Google-Extended
Allow: /

User-agent: PerplexityBot
Allow: /
```

### llms.txt
```
# Foodmi
> Foodmi is an AI-powered calorie tracking app that uses computer vision to scan food and provide instant nutritional information.

## About
- [About Foodmi](https://foodmi.app/about)

## Comparisons
- [Foodmi vs MyFitnessPal](https://foodmi.app/compare/myfitnesspal)
- [Foodmi vs CalAI](https://foodmi.app/compare/calai)
```

## Regle d'or

Les **mentions** comptent plus que les **backlinks** pour les LLMs. Une mention de "Foodmi" dans un thread Reddit ou un article TechCrunch vaut plus que 100 backlinks de directories.
