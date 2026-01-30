# Khipu Research Methods

**Official documentation site for Khipu Research Labs (KRL) frameworks**

This repository hosts the source of truth for KRL framework documentation—computational tools for understanding the intersection of economic systems, cultural dynamics, and social equity.

**Live Site:** [khipuresearch.github.io/Khipu-Research-Methods](https://khipuresearch.github.io/Khipu-Research-Methods/)

## Purpose

Khipu Research Labs develops rigorous, transparent, and accessible research frameworks that support equitable policy deliberation. This site serves as the canonical reference for:

- **Framework Documentation** — IMRAD-structured summaries of each framework (Introduction, Methods, Results, Discussion)
- **Full Whitepapers** — Complete technical documentation available via registration
- **Methodological Position** — Our stance on abstraction, uncertainty, and the limits of quantification

## Research Domains

KRL frameworks span six interconnected research domains:

| Domain | Focus |
|--------|-------|
| **Socioeconomic & Academic** | Development indices, poverty measurement, integrated assessment |
| **Government & Policy** | Regulatory analysis, policy evaluation, program assessment |
| **Experimental & Research** | Causal inference methods, impact evaluation, research design |
| **Financial & Economic** | Risk assessment, macroeconomic modeling, financial systems |
| **Arts, Media & Culture** | Cultural economics, creative industries, media impact |
| **Integration & Orchestration** | Multi-framework coordination, cross-domain synthesis |

## Available Framework Papers

### CGE-ABM Framework for Cultural-Economic Systems
A multi-scale approach integrating Computable General Equilibrium (CGE) models with Agent-Based Modeling (ABM) for equity analysis. The framework enables exploration of how economic policies interact with social and cultural dynamics to produce distributional outcomes.

**Key Features:**
- Bi-directional coupling between macro equilibrium and micro heterogeneity
- Explicit equity measurement (Gini, Theil, Atkinson indices)
- Cultural trait evolution via social networks and media influence
- Scenario exploration for policy deliberation

*Additional framework papers will be published as development and validation proceed.*

## Site Structure

| Page | Description |
|------|-------------|
| **Home** | Framework tiles with IMRAD summaries |
| **Landing** | Overview of KRL research archive |
| **Methodology** | Core principles and methodological position |
| **About** | Khipu Research Labs background and mission |
| **Register** | Gated access to full whitepaper downloads |
| **All Posts** | Archive of all framework papers |

## Accessing Full Whitepapers

Complete technical documentation is available to registered users. Registration captures:
- Contact information for research community engagement
- Framework interest for targeted updates
- Use case for understanding community needs

Registration is integrated with HubSpot for lead management.

## Technical Stack

- **Static Site Generator:** Jekyll 4.x
- **Theme:** Forty (HTML5 UP), customized for research publication
- **Hosting:** GitHub Pages
- **Forms:** HubSpot Forms API integration
- **CI/CD:** GitHub Actions for automated deployment

## Local Development

```bash
# Install dependencies
bundle install

# Serve locally
bundle exec jekyll serve

# Build for production
bundle exec jekyll build
```

## Repository Structure

```
├── _config.yml          # Jekyll configuration
├── _layouts/            # Page templates
├── _includes/           # Reusable components (header, footer)
├── _posts/              # Framework papers (IMRAD summaries)
├── _sass/               # Theme styles
├── assets/
│   ├── css/             # Compiled styles
│   ├── images/          # Page images and banners
│   ├── downloads/       # Whitepaper files (PDF)
│   ├── fonts/           # Font Awesome icons
│   └── js/              # JavaScript files
├── index.md             # Home page
├── landing.md           # Landing page
├── methodology.md       # Methodological position
├── about.md             # About KRL
├── register.md          # Registration form
└── all_posts.md         # Framework archive
```

## Use and Citation

All materials are intended for research, policy exploration, and scholarly discussion. Citation guidance is provided within individual framework papers.

**Important:** Framework outputs are decision-support tools for exploration, not predictive engines. They quantify trade-offs but cannot determine optimal policy—that requires normative judgments and democratic deliberation.

## Contact

**Khipu Research Labs**
16192 Coastal Highway
Lewes, DE 19958

**Email:** info@krlabs.dev
**GitHub:** [KhipuResearch](https://github.com/KhipuResearch)

## License

Content is released under permissive licensing for research and educational use. Theme components retain their original licenses (MIT for Jekyll integration, CCA 3.0 for HTML5 UP design).

---

### Theme Credits

- **Forty** by HTML5 UP — [html5up.net](https://html5up.net)
- **Jekyll Integration** by Andrew Banchich — [github.com/andrewbanchich](https://github.com/andrewbanchich/forty-jekyll-theme)
- **Icons:** Font Awesome
- **Libraries:** jQuery, Skel
