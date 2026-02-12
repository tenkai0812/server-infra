## 📅 Roadmap
```mermaid
gantt
    title Sky-Server Development Roadmap
    dateFormat  2026-02-12
    section Phase 1: Infra
    K8s Setup           :done,    des1, 2026-02-01, 2d
    Ingress & Cloudflare:done,    des2, 2026-02-03, 3d
    Postgres & pgAdmin  :done,    des3, 2026-02-06, 2d
    
    section Phase 2: Security
    Cert-Manager Install:active,  des4, 2026-02-12, 1d
    DNS-01 Challenge    :         des5, after des4, 2d
    Full Strict SSL     :         des6, after des5, 1d
    
    section Phase 3: CI/CD
    Jenkins Pipeline    :         des7, after des6, 5d
```