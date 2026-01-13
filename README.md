# University Digital Notice Board 🎓

## 📌 Project Overview

The **University Digital Notice Board** is a static web application designed to display academic notices, examination schedules, admission updates, university events, and contact information.

The project follows **DevOps best practices** using CI pipelines, automated linting, build verification, and containerization.

This project was developed collaboratively by a team using **GitHub feature branches, pull requests, and branch protection rules**.

---

## 🚀 Objectives

- Implement an industry-aligned CI/CD pipeline  
- Enforce HTML and CSS code quality  
- Automate static website builds  
- Containerize the application using Docker  
- Practice collaborative development using GitHub workflows  

---

## 🛠️ Technologies Used

| Category | Tools |
|--------|------|
| Version Control | Git, GitHub |
| CI/CD | GitHub Actions |
| Linting | HTMLHint, Stylelint |
| Build Tool | Parcel |
| Containerization | Docker, Nginx |
| Frontend | HTML5, CSS3 |

---

## 📂 Project Structure

```text
uni-notice-board/
├── .github/workflows/ci.yml
├── Dockerfile
├── package.json
├── README.md
├── src/
│   ├── index.html
│   ├── notices.html
│   ├── exams.html
│   ├── admissions.html
│   ├── events.html
│   └── contact.html
└── styles/
    └── style.css
```

---

## 👥 Team Roles

- **Mohammad Rayan**: Project setup, CI/CD, Docker, homepage
- **Muhammad Ahmad**: Academic Notices page
- **Yasir Iftikhar**: Examination Schedule page
- **Abdul Wahab Subhani**: Admissions page
- **Kaif Baig**: Contact page
- **Umar Draz**: Events page
---

## 🌿 Branching Strategy

- `main` → Production-ready branch
- `develop` → Integration branch
- `feature/*` → Individual feature branches

### Branch Protection Rules
- Direct pushes disabled
- Pull Requests required
- CI checks must pass
- Only Team Lead can merge PRs

---

## ⚙️ CI Pipeline Workflow

The CI pipeline consists of **three sequential jobs**:

1. **Linting Job**
   - HTMLHint for HTML files
   - Stylelint for CSS files

2. **Build Job**
   - Builds the website using Parcel

3. **Docker Job**
   - Builds Docker image
   - Pushes image to Docker Hub using secrets

---

## 🐳 Docker Configuration

- Base image: `nginx:alpine`
- Static files served from `/usr/share/nginx/html`
- Image built and pushed automatically via CI

---

## ▶️ Run Project Locally

```bash
npm install
npx htmlhint "src/**/*.html"
npx stylelint "styles/**/*.css"
npm run build
docker build -t uni-notice-board .
docker run -p 8080:80 uni-notice-board
```

## 🌐 Open in Browser

[http://localhost:8080](http://localhost:8080)

---

## 🔐 Secrets Management

Docker Hub credentials are stored securely using **GitHub Actions Secrets**:

- `DOCKER_USERNAME`
- `DOCKER_PASSWORD`

---

## 📝 Reflection

This project improved our understanding of CI/CD pipelines, automated quality enforcement, Docker-based deployment, and collaborative DevOps workflows.

---

## 📜 License

Academic project for **DevOps Fundamentals – Fall 2025**
