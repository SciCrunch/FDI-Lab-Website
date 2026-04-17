# FDI Lab GitHub Pages Website

Static website for the [FAIR Data Informatics Lab](https://fdilab.org) at UC San Diego, built for GitHub Pages.

## Pages

| File | URL |
|------|-----|
| `index.html` | Home |
| `about.html` | About the Lab |
| `team.html` | Team |
| `projects.html` | Projects |
| `funding.html` | Funding |
| `contact.html` | Contact |

## Deploying to GitHub Pages

1. Push this repository to GitHub.
2. Go to **Settings → Pages**.
3. Under **Source**, select `Deploy from a branch`.
4. Choose branch `main` (or `master`) and folder `/ (root)`.
5. Click **Save**. Your site will be live at `https://<your-org>.github.io/<repo-name>/`.

## Customizing

- **Colors & fonts**: edit `css/style.css` — all design tokens are CSS variables at the top of the file.
- **Content**: edit the relevant `.html` file.
- **Custom domain**: add a `CNAME` file containing your domain (e.g. `fdilab.org`) and configure DNS.

## Structure

```
FDI-Lab-Website/
├── index.html
├── about.html
├── team.html
├── projects.html
├── funding.html
├── contact.html
├── css/
│   └── style.css
├── _config.yml
└── README.md
```
