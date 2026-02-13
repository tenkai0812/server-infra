## 📅 Roadmap
```mermaid
gantt
    title Sky-Server Development Roadmap
    dateFormat  2026-02-12
    section Phase 1: Infra
    K8s Setup               :done,  des1, 2026-02-01, 2d
    Ingress & Cloudflare    :done,  des2, 2026-02-03, 3d
    Postgres & pgAdmin      :done,  des3, 2026-02-06, 2d
    
    section Phase 2: Security
    Cert-Manager Install    :done,  des4, 2026-02-12, 1d
    DNS-01 Challenge        :done,  des5, 2026-02-13, 1d
    Full Strict SSL         :done,  des6, 2026-02-13, 1d
    
    section Phase 3: CI/CD
    Jenkins Pipeline        :done,  des7, 2026-02-13, 3d
    Automation Docker Image :active,des8, 2026-02-15, 3d
```