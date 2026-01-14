# University Digital Notice Board 🎓

## 📌 Project Overview

The **University Digital Notice Board** is a static web application designed to display academic notices, examination schedules, admission updates, university events, and contact information.

The project follows **DevOps best practices** using CI pipelines, automated linting, build verification, and containerization.

This project was developed collaboratively by a team using **GitHub feature branches, pull requests, and branch protection rules**.


## 📋 Group Details


| Sr # | Student Name | GitHub Username | Role (Lead/Member) | Branch Worked On | Verification Screenshots Added (Yes/No) |
|------|--------------|-----------------|-------------------|------------------|----------------------------------------|
| 1 | Mohammad Rayan | | Lead | main/develop | |
| 2 | Muhammad Ahmad | | Member | feature/notices | |
| 3 | Yasir Iftikhar | | Member | feature/exams | |
| 4 | Abdul Wahab Subhani | | Member | feature/admissions | |
| 5 | Kaif Baig | | Member | feature/contact | |
| 6 | Umar Draz | | Member | feature/events | |

**Group Repository URL:** [https://github.com/DevOps-Fundamentals/uni-notice-board.git]

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
├── .github/
│   └── workflows/
│       └── ci.yaml           # CI/CD pipeline configuration
├── src/
│   ├── index.html           # Homepage
│   ├── notices.html         # Academic Notices page
│   ├── exams.html          # Examination Schedule page
│   ├── admissions.html     # University Admissions page
│   ├── events.html         # University Events page
│   └── contact.html        # Contact Information page
├── styles/
│   └── style.css           # Global styles for all pages
├── .stylelintrc.json       # Stylelint configuration
├── Dockerfile              # Container configuration
├── package.json            # Node.js dependencies and scripts
└── README.md               # Project documentation
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

The CI pipeline consists of **three sequential jobs** that run automatically on push to `main` and pull requests to `develop`:

### 1. **Linting Job** 🔍
   - **HTMLHint**: Validates HTML structure and syntax
   - **Stylelint**: Enforces CSS coding standards and best practices
   - **Files checked**: All HTML files in `src/` and CSS files in `styles/`

### 2. **Build Job** 🔨
   - **Dependencies**: Runs only after linting passes
   - **Parcel Build**: Compiles and optimizes the static website
   - **Output**: Generates production-ready files in `dist/` directory

### 3. **Docker Job** 🐳
   - **Dependencies**: Runs only after build succeeds
   - **Image Build**: Creates Docker image with Nginx
   - **Registry**: Automatically pushes to Docker Hub with latest tag
   - **Security**: Uses GitHub Actions secrets for authentication

### Pipeline Features
- ✅ **Sequential execution** ensures quality gates
- ✅ **Fail-fast** approach stops pipeline on first error
- ✅ **Automated deployment** to Docker Hub
- ✅ **Branch protection** enforces PR workflow

---

## 🐳 Docker Configuration

- Base image: `nginx:alpine`
- Static files served from `/usr/share/nginx/html`
- Image built and pushed automatically via CI

---

## 💻 Local Development

### Prerequisites
- **Node.js** (v16+ recommended)
- **npm** or **yarn**
- **Docker** (for containerization)
- **Git** (for version control)

### Setup Instructions

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd uni-notice-board
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Run quality checks**
   ```bash
   # HTML linting
   npx htmlhint "src/**/*.html"
   
   # CSS linting
   npx stylelint "styles/**/*.css"
   ```

4. **Build the project**
   ```bash
   npx parcel build "./src/index.html" --dist-dir "./dist" --public-url "./" --no-cache
   ```

5. **Run with Docker**
   ```bash
   # Build Docker image
   docker build -t uni-notice-board .
   
   # Run container
   docker run -p 8080:80 uni-notice-board
   ```

6. **Access the application**
   - Local development: [http://localhost:8080](http://localhost:8080)
   - Docker container: [http://localhost:8080](http://localhost:8080)

### Development Workflow
1. Create a feature branch from `develop`
2. Make your changes
3. Run linting and build locally
4. Create a pull request to `develop`
5. Wait for CI pipeline to pass
6. Get approval and merge

---

## 🔐 Secrets Management

Docker Hub credentials are stored securely using **GitHub Actions Secrets**:

- `DOCKERHUB_USERNAME` - Docker Hub username
- `DOCKERHUB_TOKEN` - Docker Hub access token (not password)

### Setting up secrets:
1. Go to repository **Settings** → **Secrets and variables** → **Actions**
2. Add the required secrets with the exact names above
3. Secrets are automatically injected into the CI pipeline

---

## 🧪 Quality Assurance

### Code Quality Tools

| Tool | Purpose | Configuration |
|------|---------|---------------|
| HTMLHint | HTML validation | Default rules |
| Stylelint | CSS linting | `.stylelintrc.json` |
| Parcel | Build optimization | Zero-config bundler |

### Quality Gates
- ✅ All HTML files must pass HTMLHint validation
- ✅ All CSS files must follow Stylelint rules
- ✅ Build must succeed without errors
- ✅ Docker image must build successfully

---

## 🏗️ Architecture

### Frontend Architecture
- **Static Site**: Pure HTML/CSS without JavaScript frameworks
- **Responsive Design**: Mobile-first approach
- **Navigation**: Consistent header navigation across all pages
- **Semantic HTML**: Proper HTML5 semantic elements

### DevOps Architecture
- **Git Workflow**: Feature branch strategy with PR reviews
- **CI/CD**: GitHub Actions with multi-stage pipeline
- **Containerization**: Docker with Nginx for production
- **Quality Gates**: Automated linting and build verification

---

## 📊 Project Features

### Website Pages
- 🏠 **Homepage** - University overview and navigation
- 📢 **Notices** - Academic announcements and updates
- 📝 **Exams** - Examination schedules and information
- 🎓 **Admissions** - University admission details
- 🎉 **Events** - Campus events and activities
- 📞 **Contact** - University contact information

### DevOps Features
- 🔄 **Continuous Integration** - Automated testing and building
- 🚀 **Continuous Deployment** - Automated Docker image publishing
- 🛡️ **Quality Control** - Code linting and validation
- 🔒 **Branch Protection** - Enforced code review process
- 📦 **Containerization** - Docker-based deployment

---

## � Troubleshooting

### Common Issues

**1. Linting Failures**
```bash
# Check specific errors
npx htmlhint "src/**/*.html" --format=compact
npx stylelint "styles/**/*.css" --formatter=verbose
```

**2. Build Failures**
```bash
# Clear Parcel cache
rm -rf .parcel-cache dist/
npx parcel build "./src/index.html" --dist-dir "./dist" --public-url "./" --no-cache
```

**3. Docker Issues**
```bash
# Check if port is in use
netstat -an | grep :8080

# Remove existing container
docker rm -f uni-notice-board-container
```

**4. CI Pipeline Failures**
- Check GitHub Actions logs for specific error messages
- Ensure all secrets are properly configured
- Verify branch protection rules are correctly set

---

## 📚 Learning Outcomes

This project demonstrates proficiency in:

### Technical Skills
- ✅ **HTML/CSS Development** - Semantic markup and responsive design
- ✅ **Git Workflow** - Feature branches, PRs, and code reviews
- ✅ **CI/CD Pipelines** - Automated testing, building, and deployment
- ✅ **Docker Containerization** - Image creation and registry publishing
- ✅ **Code Quality** - Linting, validation, and best practices

### DevOps Practices
- ✅ **Infrastructure as Code** - Configuration files in version control
- ✅ **Automated Testing** - Quality gates in CI pipeline
- ✅ **Security** - Secrets management and secure deployment
- ✅ **Collaboration** - Team-based development with proper workflows
- ✅ **Documentation** - Comprehensive project documentation

### Professional Skills
- ✅ **Project Management** - Task distribution and role assignment
- ✅ **Code Review** - Peer review and quality assurance
- ✅ **Problem Solving** - Debugging and troubleshooting
- ✅ **Best Practices** - Industry-standard development workflows

---

## 🎯 Future Enhancements

### Planned Improvements
- 📱 **Progressive Web App** features
- 🎨 **Advanced CSS animations** and interactions
- 📊 **Analytics integration** for usage tracking
- 🔍 **Search functionality** for notices and events
- 🌙 **Dark mode** theme support
- 📱 **Mobile app** version using Cordova/PhoneGap

### Infrastructure Enhancements
- ☁️ **Cloud deployment** (AWS S3, Azure Static Web Apps)
- 🔄 **CD Pipeline** for automatic deployments
- 📊 **Monitoring and logging** integration
- 🧪 **Automated testing** with Cypress or Playwright
- 🚀 **Performance optimization** and caching strategies

---

## 👨‍💻 Contributing

### Contribution Guidelines
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Follow the coding standards (HTMLHint + Stylelint)
4. Commit changes (`git commit -m 'Add amazing feature'`)
5. Push to branch (`git push origin feature/amazing-feature`)
6. Open a Pull Request

### Code Standards
- Use semantic HTML5 elements
- Follow CSS naming conventions (BEM methodology preferred)
- Ensure responsive design for all screen sizes
- Write descriptive commit messages
- Add comments for complex CSS rules

---

## 📝 Project Reflection

### Team Collaboration Success
This project successfully demonstrated **collaborative DevOps development** through:
- **Structured teamwork** with clearly defined roles and responsibilities
- **Professional git workflow** using feature branches and pull requests
- **Quality assurance** through automated linting and code reviews
- **Continuous integration** ensuring code quality at every step

### Technical Achievements
- **Zero-downtime deployment** pipeline with Docker containerization
- **Automated quality gates** preventing broken code from reaching production
- **Scalable architecture** ready for cloud deployment
- **Industry-standard practices** applicable to real-world projects

### Learning Impact
This project significantly enhanced our understanding of:
- **DevOps culture** and collaborative development practices
- **CI/CD implementation** with real-world quality gates
- **Container orchestration** and deployment strategies
- **Code quality enforcement** through automated tooling
- **Professional software development** lifecycle management

The experience gained here directly applies to **enterprise software development** environments and provides a solid foundation for **cloud-native application development**.

---

## 📞 Support

### Getting Help
- 📧 **Email**: Create an issue in the repository
- 💬 **Discussions**: Use GitHub Discussions for questions
- 🐛 **Bug Reports**: Open an issue with detailed reproduction steps
- 💡 **Feature Requests**: Submit enhancement proposals via issues

### Team Contacts
- **Project Lead**: Mohammad Rayan
- **DevOps Engineer**: Multiple team members
- **Frontend Developers**: Individual page owners (see Team Roles)

---

## 📜 License

**Academic Project** - DevOps Fundamentals Course, Fall 2025

This project is for educational purposes and demonstrates industry-standard DevOps practices in a university setting.

### Usage Rights
- ✅ **Educational use** encouraged
- ✅ **Portfolio inclusion** permitted
- ✅ **Learning reference** allowed
- ❌ **Commercial use** prohibited without permission

---

## 🏆 Acknowledgments

### Technologies
- **GitHub Actions** - For robust CI/CD pipeline
- **Docker & Nginx** - For reliable containerization
- **HTMLHint & Stylelint** - For code quality assurance
- **Parcel** - For seamless build process

### Course
- **DevOps Fundamentals** - Fall 2025
- **Instructor**: Course faculty
- **Institution**: University setting

### Team Achievement
Special recognition to all team members who contributed to making this project a comprehensive demonstration of **collaborative DevOps excellence**. 🎉

---

*Last updated: January 2026*
