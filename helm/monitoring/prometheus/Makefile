include ${CURDIR}/../../../devops/makefiles/Makefile.base
include ${CURDIR}/../../../devops/makefiles/Makefile.helm

# Settings
HELM_NAMESPACE = "prometheus"
HELM_RELEASE = "prometheus"

HELM_OPTIONS = --values values-prod.yaml
# HELM_OPTIONS = --values values-web-dev.yaml

main: helm-template
