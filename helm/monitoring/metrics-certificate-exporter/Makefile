include ${CURDIR}/../../../devops/makefiles/Makefile.base
include ${CURDIR}/../../../devops/makefiles/Makefile.helm

# Settings
HELM_NAMESPACE = "metrics"

# Kubernetes: production
# HELM_RELEASE = "prometheus-metrics-x509-certificate-exporter-prod"
# HELM_OPTIONS = --values values-prod.yaml

# Kubernetes: web-dev
HELM_RELEASE = "prometheus-metrics-x509-certificate-exporter-web-dev"
HELM_OPTIONS = --values values-web-dev.yaml

main: helm-template
