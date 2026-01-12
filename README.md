# FinOps Infrastructure

AWS 인프라 및 Kubernetes 배포 매니페스트

## 프로젝트 구조

```
finops-project/
├── infra/
│   └── terraform/          # AWS 인프라 IaC (VPC, EKS, RDS, S3, ALB)
├── k8s/                    # Kubernetes 매니페스트
│   ├── namespace.yaml
│   ├── cost-collector/     # CronJob
│   ├── cost-api/           # Deployment, Service, Ingress
│   ├── alert-service/      # Deployment, Service
│   ├── frontend/           # Deployment, Service, Ingress
│   └── monitoring/         # Prometheus, Grafana
└── .github/workflows/      # Infrastructure CI/CD
```

## 관련 서비스 리포지토리

- [finops-cost-collector](https://github.com/amy397/finops-cost-collector) - AWS 비용 수집
- [finops-cost-api](https://github.com/amy397/finops-cost-api) - REST API
- [finops-alert-service](https://github.com/amy397/finops-alert-service) - Slack 알림
- [finops-dashboard](https://github.com/amy397/finops-dashboard) - React 대시보드

## 사용법

```bash
# Terraform으로 인프라 생성
cd infra/terraform
terraform init
terraform plan
terraform apply

# Kubernetes 배포
kubectl apply -f k8s/namespace.yaml
kubectl apply -f k8s/
```
