include ${CURDIR}/../../../devops/makefiles/Makefile.base
include ${CURDIR}/../../../devops/makefiles/Makefile.helm

# Settings
HELM_RELEASE = "prometheus-alerts-prod"
HELM_NAMESPACE = "prometheus"
HELM_OPTIONS = --values values-prod.yaml

main: helm-template
