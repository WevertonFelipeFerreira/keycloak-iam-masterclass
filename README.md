# 🔐 Keycloak IAM Masterclass

**A hands-on Identity and Access Management laboratory built with Keycloak, Docker, OAuth 2.0, OpenID Connect, and .NET.**

This repository documents a practical learning journey through modern authentication, authorization, identity federation, and access management architectures.

The goal is to go beyond basic username/password authentication and understand how identity protocols work, how tokens are issued and validated, and how secure applications integrate with an Identity Provider (IdP).

## 🎯 Objectives

- Understand Keycloak architecture and core IAM concepts.
- Explore realms, clients, users, groups, roles, and scopes.
- Implement and test OAuth 2.0 and OpenID Connect flows.
- Understand JWT structure, claims, signatures, and token validation.
- Implement Single Sign-On (SSO) and session management.
- Configure Multi-Factor Authentication (MFA) and OTP.
- Explore identity federation and social login.
- Secure REST APIs using Keycloak and ASP.NET Core.
- Learn IAM security best practices and production considerations.

## 🏗️ Lab Architecture

The environment will evolve incrementally throughout the masterclass.

**Planned architecture:**

```text
                  ┌──────────────────┐
                  │    Keycloak      │
                  │ Identity Provider│
                  └────────┬─────────┘
                           │
               OAuth 2.0 / OIDC
                           │
              ┌────────────┴───────────┐
              │                        │
       ┌──────▼──────┐          ┌──────▼──────┐
       │ Web Client  │          │  REST API   │
       │ SSO / PKCE  │          │ ASP.NET Core│
       └─────────────┘          └─────────────┘

       Future integrations:
       - PostgreSQL
       - Social Identity Providers
       - OTP / MFA
       - Identity Federation
```

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| Keycloak | Identity and Access Management |
| Docker Compose | Local infrastructure |
| PostgreSQL | Persistent database (planned) |
| OAuth 2.0 | Authorization framework |
| OpenID Connect | Authentication protocol |
| JWT / JWKS | Token handling and signature validation |
| ASP.NET Core | Protected REST APIs (planned) |
| cURL / Postman / PowerShell | Authentication flow testing |
| Git | Version control and learning history |

## 📚 Learning Roadmap

Each module introduces a new concept, practical implementation, security considerations, and reproducible tests.

| Module | Topic | Status |
|---|---|---|
| 01 | Environment Setup & Keycloak Architecture | 🚧 In Progress |
| 02 | Realms, Clients & User Management | ⏳ Planned |
| 03 | Roles, Groups, Scopes & Claims | ⏳ Planned |
| 04 | Client Credentials & Password Grant | ⏳ Planned |
| 05 | Authorization Code Flow & PKCE | ⏳ Planned |
| 06 | SSO, Sessions & Token Lifecycle | ⏳ Planned |
| 07 | MFA, OTP & Authentication Flows | ⏳ Planned |
| 08 | Identity Federation & Social Login | ⏳ Planned |
| 09 | Advanced OAuth/OIDC Flows & SAML | ⏳ Planned |
| 10 | ASP.NET Core API Security | ⏳ Planned |
| 11 | Keycloak Admin REST API & Automation | ⏳ Planned |
| 12 | Production Architecture & Security Hardening | ⏳ Planned |

## 🚀 Getting Started

### Prerequisites

- Docker Engine or Docker Desktop
- Docker Compose
- Git
- PowerShell, cURL, or another HTTP client

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/keycloak-iam-masterclass.git
cd keycloak-iam-masterclass
```

### 2. Configure environment variables

Create a `.env` file based on `.env.example`:

```env
KC_ADMIN_USER=admin
KC_ADMIN_PASSWORD=your-local-password
```

Never commit credentials, access tokens, or client secrets.

### 3. Start Keycloak

```bash
docker compose up -d
```

Access the Admin Console:

**URL:** http://localhost:8080/admin/

Use the administrator credentials configured in your `.env` file.

### 4. Explore OpenID Connect Discovery

```bash
curl http://localhost:8080/realms/master/.well-known/openid-configuration
```

This endpoint provides metadata such as:

- Authorization Endpoint
- Token Endpoint
- JWKS URI
- UserInfo Endpoint
- Logout Endpoint

## 📁 Repository Structure

```text
keycloak-iam-masterclass/
├── docker-compose.yml
├── .env.example
├── .gitignore
├── README.md
│
├── docs/
│   └── aula-01.md
│
├── scripts/
│
└── realms/
```

The repository structure will expand as new modules introduce APIs, applications, automation scripts, and realm configurations.

## 🔒 Security Considerations

This repository is designed for educational and local development purposes.

- Never expose development credentials publicly.
- Avoid committing access tokens, passwords, or client secrets.
- Use HTTPS and secure configuration in production.
- Prefer Authorization Code with PKCE for interactive applications.
- Treat Resource Owner Password Credentials as a legacy flow.
- Validate JWT signatures, issuer, audience, and expiration.
- Follow least-privilege principles when configuring roles and permissions.

## 📖 Learning Approach

Every module follows the same process:

**Theory → Architecture → Implementation → API Testing → Security Analysis → Git Commit**

The objective is to build a reproducible IAM environment while understanding the protocols and security mechanisms behind each implementation.

## 📚 References

- [Keycloak Documentation](https://www.keycloak.org/documentation)
- [OAuth 2.0 — RFC 6749](https://www.rfc-editor.org/rfc/rfc6749)
- [OpenID Connect Core](https://openid.net/specs/openid-connect-core-1_0.html)
- [OAuth 2.0 Security Best Current Practice — RFC 9700](https://www.rfc-editor.org/rfc/rfc9700)
- [JWT — RFC 7519](https://www.rfc-editor.org/rfc/rfc7519)

---

**Built as a continuous hands-on learning project focused on IAM architecture, application security, and modern identity protocols.**
