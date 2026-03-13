# AWS Production Deployment - Developer Questionnaire

**How to fill this form:**
- For checkboxes: Add an `x` inside the brackets like this: `[x]` for selected items
- For text answers: Replace the underscores `_______________` with your answer
- For multi-line answers: Use the provided code blocks or add additional lines as needed
- Save the file and send it back to the DevOps/SA team

**Example:**
```markdown
- [x] Yes - Build command: npm run build
- [ ] No

- **Programming language:** Python 3.11
```

Please complete this checklist to help us deploy your application to AWS production environment. Answer all applicable questions with as much detail as possible.

---

## ✅ **1. APPLICATION ARCHITECTURE & TECHNOLOGY STACK** (Critical)

### Architecture Type
- [ ] **What type of application is this?**
  - [ ] Monolithic (single deployable unit)
  - [ ] Microservices (multiple independent services)
  - [ ] Serverless (Lambda functions, API Gateway, etc.)
  - [ ] Hybrid (combination of above)

- [ ] **How many services/components does the application have?**
  - Answer: _______________

- [ ] **Are there dependencies between services?**
  - Answer: _______________

### Technology Stack
- [ ] **Programming language(s) and runtime versions?**
  - Backend: _______________ (e.g., Python 3.11, Node.js 18.x, Java 17)
  - Frontend: _______________ (e.g., React 18, Vue 3, vanilla JS)

- [ ] **Framework(s) used?**
  - Backend: _______________ (e.g., Django, Flask, Express, Spring Boot)
  - Frontend: _______________ (e.g., Next.js, Create React App, Vue CLI)

- [ ] **Does the application require a build process?**
  - [ ] Yes - Build command: _______________
  - [ ] No

- [ ] **Are there any specific OS requirements?**
  - Answer: _______________ (e.g., Ubuntu 22.04, Amazon Linux 2)

---

## ✅ **2. DATABASE & DATA STORAGE** (Critical)

### Database Requirements
- [ ] **What database(s) does the application use?**
  - [ ] MySQL (version: _______)
  - [ ] PostgreSQL (version: _______)
  - [ ] MongoDB (version: _______)
  - [ ] Redis (version: _______)
  - [ ] Other: _______________

- [ ] **Estimated database size?**
  - Current: _______________
  - Expected growth: _______________

- [ ] **Database configuration requirements?**
  - Extensions needed: _______________
  - Special configurations: _______________

- [ ] **Does it require read replicas or multi-AZ setup?**
  - Answer: _______________

### Data Storage
- [ ] **Does the app need file storage?**
  - [ ] Yes - Type: _______________ (S3, EFS, EBS)
  - [ ] No

- [ ] **Data retention requirements?**
  - Answer: _______________

- [ ] **Backup frequency needed?**
  - Answer: _______________

- [ ] **Any compliance requirements?**
  - [ ] GDPR
  - [ ] HIPAA
  - [ ] PCI-DSS
  - [ ] SOC2
  - [ ] Other: _______________

---

## ✅ **3. APPLICATION CONFIGURATION** (Critical)

### Environment Variables & Secrets
- [ ] **List all environment variables the app requires:**
  ```
  Variable Name          | Description                    | Example Value
  ----------------------|--------------------------------|------------------
  DATABASE_URL          | Database connection string     | postgres://...
  API_KEY               | Third-party API key            | sk_live_...
  
  (Add more rows as needed)
  ```

- [ ] **Are there secrets/credentials that need secure storage?**
  - [ ] Yes - List: _______________
  - [ ] No

- [ ] **Are configurations different per environment?**
  - [ ] Yes - Provide details: _______________
  - [ ] No

### External Dependencies
- [ ] **Does the app integrate with third-party APIs or services?**
  - Service names: _______________
  - API keys needed: _______________

- [ ] **Does it require VPN or private connectivity?**
  - Answer: _______________

---

## ✅ **4. CODE REPOSITORY & ACCESS** (Critical)

- [ ] **Where is the source code hosted?**
  - [ ] GitHub - Repository URL: _______________
  - [ ] GitLab - Repository URL: _______________
  - [ ] Bitbucket - Repository URL: _______________
  - [ ] Other: _______________

- [ ] **How should we access the code?**
  - [ ] Clone repository (provide access)
  - [ ] Fork repository
  - [ ] Zip file download
  - [ ] Other: _______________

- [ ] **What branch should be deployed to production?**
  - Answer: _______________ (e.g., main, master, production)

- [ ] **Is there a .gitignore file?**
  - [ ] Yes
  - [ ] No

---

## ✅ **5. PERFORMANCE & SCALABILITY** (High Priority)

### Traffic & Load
- [ ] **Expected traffic volume?**
  - Requests per second: _______________
  - Concurrent users: _______________
  - Peak traffic times: _______________

- [ ] **Does the app need auto-scaling?**
  - [ ] Yes
  - [ ] No

- [ ] **Acceptable response time SLA?**
  - Answer: _______________ (e.g., < 200ms, < 1s)

### Resource Requirements
- [ ] **Minimum CPU and memory requirements?**
  - CPU: _______________ (e.g., 2 vCPU)
  - Memory: _______________ (e.g., 4GB RAM)

- [ ] **Storage requirements?**
  - Disk space: _______________
  - IOPS requirements: _______________

---

## ✅ **6. NETWORKING & SECURITY** (High Priority)

### Network Requirements
- [ ] **Should the app be publicly accessible?**
  - [ ] Yes - Public internet
  - [ ] No - Internal only
  - [ ] Hybrid - Some endpoints public, some private

- [ ] **Does it need a custom domain?**
  - [ ] Yes - Domain name: _______________
  - [ ] No

- [ ] **Does it need SSL/TLS certificate?**
  - [ ] Yes
  - [ ] No

- [ ] **Any specific ports that need to be open?**
  - Answer: _______________ (e.g., 80, 443, 8080)

### Security Requirements
- [ ] **Authentication mechanism?**
  - [ ] JWT
  - [ ] OAuth 2.0
  - [ ] SAML
  - [ ] Basic Auth
  - [ ] None
  - [ ] Other: _______________

- [ ] **Does it handle sensitive data?**
  - [ ] Yes - Type: _______________ (PII, payment info, health records)
  - [ ] No

- [ ] **Does it need WAF (Web Application Firewall) protection?**
  - [ ] Yes
  - [ ] No
  - [ ] Not sure

---

## ✅ **7. MONITORING & LOGGING** (High Priority)

- [ ] **What logs does the application generate?**
  - Log location: _______________
  - Log format: _______________ (JSON, plain text, etc.)

- [ ] **Does the app have health check endpoints?**
  - [ ] Yes - Endpoint: _______________ (e.g., /health, /api/health)
  - [ ] No

- [ ] **What metrics should be monitored?**
  - [ ] CPU usage
  - [ ] Memory usage
  - [ ] Response time
  - [ ] Error rate
  - [ ] Custom metrics: _______________

- [ ] **Critical alerts that need immediate attention?**
  - Answer: _______________

---

## ✅ **8. DEPLOYMENT & CI/CD** (Medium Priority)

### Build & Deployment
- [ ] **Does the app have a Dockerfile?**
  - [ ] Yes
  - [ ] No

- [ ] **Are there build scripts or deployment documentation?**
  - [ ] Yes - Location: _______________
  - [ ] No

- [ ] **Are there database migrations?**
  - [ ] Yes - How to run: _______________
  - [ ] No

- [ ] **Any pre/post-deployment scripts?**
  - [ ] Yes - Details: _______________
  - [ ] No

- [ ] **What's the desired deployment frequency?**
  - [ ] Multiple times per day
  - [ ] Daily
  - [ ] Weekly
  - [ ] On-demand
  - [ ] Other: _______________

---

## ✅ **9. HIGH AVAILABILITY & DISASTER RECOVERY** (Medium Priority)

### Availability Requirements
- [ ] **What's the acceptable downtime?**
  - [ ] 99.9% uptime (8.76 hours/year downtime)
  - [ ] 99.95% uptime (4.38 hours/year downtime)
  - [ ] 99.99% uptime (52.56 minutes/year downtime)
  - [ ] Other: _______________

- [ ] **Does it need multi-region deployment?**
  - [ ] Yes
  - [ ] No

### Backup & Recovery
- [ ] **What needs to be backed up?**
  - [ ] Database
  - [ ] File storage
  - [ ] Configuration
  - [ ] Other: _______________

- [ ] **Backup frequency?**
  - Answer: _______________ (e.g., hourly, daily, weekly)

- [ ] **Data retention period?**
  - Answer: _______________ (e.g., 30 days, 90 days, 1 year)

---

## ✅ **10. TESTING & QUALITY ASSURANCE** (Medium Priority)

- [ ] **Are there automated tests?**
  - [ ] Yes - Type: _______________ (unit, integration, e2e)
  - [ ] No

- [ ] **How to run tests?**
  - Command: _______________

- [ ] **Test coverage percentage?**
  - Answer: _______________

- [ ] **Do you need a staging/UAT environment?**
  - [ ] Yes
  - [ ] No

---

## ✅ **11. COST & BUDGET** (Medium Priority)

- [ ] **What's the monthly infrastructure budget?**
  - Answer: _______________

- [ ] **Any cost optimization priorities?**
  - Answer: _______________

- [ ] **Preference for instance types?**
  - [ ] On-demand (pay as you go)
  - [ ] Reserved instances (1-3 year commitment for savings)
  - [ ] Spot instances (cheapest but can be interrupted)
  - [ ] No preference

---

## ✅ **12. DOCUMENTATION** (Low Priority but Helpful)

- [ ] **Is there application documentation?**
  - [ ] Yes - Location: _______________
  - [ ] No

- [ ] **Architecture diagrams available?**
  - [ ] Yes - Location: _______________
  - [ ] No

- [ ] **API documentation?**
  - [ ] Yes - Type: _______________ (Swagger, Postman, etc.)
  - [ ] No

- [ ] **Known issues or limitations?**
  - Answer: _______________

---

## ✅ **13. SUPPORT & OPERATIONS** (Low Priority)

- [ ] **Who will be responsible for application support post-deployment?**
  - Name/Team: _______________
  - Contact: _______________

- [ ] **What's the on-call/incident response process?**
  - Answer: _______________

- [ ] **Are there runbooks for common issues?**
  - [ ] Yes - Location: _______________
  - [ ] No

---

## 📋 **ARCHITECTURE-SPECIFIC QUESTIONS**

### If Monolithic (EC2-based):
- [ ] **Preferred operating system?**
  - [ ] Amazon Linux 2
  - [ ] Ubuntu 22.04
  - [ ] RHEL
  - [ ] Other: _______________

- [ ] **Does it need a web server?**
  - [ ] Nginx
  - [ ] Apache
  - [ ] None (application handles HTTP)
  - [ ] Other: _______________

- [ ] **Application server requirements?**
  - Answer: _______________ (e.g., Gunicorn, uWSGI, Tomcat)

- [ ] **Does it need a load balancer?**
  - [ ] Yes - Type: _______________ (ALB, NLB)
  - [ ] No

### If Microservices (EKS/ECS):
- [ ] **How many microservices?**
  - Answer: _______________

- [ ] **Service communication patterns?**
  - [ ] REST API
  - [ ] gRPC
  - [ ] Message queue (RabbitMQ, SQS, Kafka)
  - [ ] Other: _______________

- [ ] **Container orchestration preference?**
  - [ ] EKS (Kubernetes)
  - [ ] ECS (AWS native)
  - [ ] Fargate (serverless containers)
  - [ ] No preference

- [ ] **Do you have Kubernetes manifests or Helm charts?**
  - [ ] Yes - Location: _______________
  - [ ] No

### If Serverless:
- [ ] **Which AWS services are needed?**
  - [ ] Lambda
  - [ ] API Gateway
  - [ ] DynamoDB
  - [ ] S3
  - [ ] Other: _______________

- [ ] **Lambda function execution time?**
  - Answer: _______________ (max 15 minutes)

- [ ] **Memory requirements per function?**
  - Answer: _______________ (128MB - 10GB)

- [ ] **Event sources/triggers?**
  - Answer: _______________ (API Gateway, S3, SQS, etc.)

---

## 📝 **ADDITIONAL INFORMATION**

Please provide any additional information that might be relevant for deployment:

```
(Add any additional context, concerns, or requirements here)
```

---

## ✉️ **DEVELOPER CONTACT INFORMATION**

Please provide your contact details so we can reach you for clarifications:

- **Your Name:** _______________
- **Email:** _______________
- **Phone:** _______________
- **Preferred communication method:** _______________
- **Availability for technical discussions:** _______________

---

**Thank you for completing this questionnaire! This information will help us design and deploy a secure, scalable, and cost-effective AWS infrastructure for your application.**

**Next Steps:**
1. Complete all applicable sections
2. Provide access to the code repository
3. Share any existing documentation
4. Schedule a technical discussion if needed

**Questions?** Feel free to reach out to the DevOps/Solutions Architecture team if you need clarification on any items.
