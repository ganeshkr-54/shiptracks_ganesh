# Don't print any recipes before executing them
.SILENT:

# Settings
AZURE_REGISTRY = oshelmrepo.azurecr.io
# AZURE_REGISTRY = oshelm.azurecr.io
AZURE_REGISTRY_PATH = /helm/base
CODEFRESH_REPOSITORY = oii-dev

# "lint" is default target
all: lint

lint:
	helm lint .

# Azure
azure-save:
	helm chart save . ${AZURE_REGISTRY}${AZURE_REGISTRY_PATH}:$(shell echo $$(grep "version:" ./Chart.yaml | awk '{ print $$2}'))
	helm chart list

azure-push:
	helm chart push ${AZURE_REGISTRY}${AZURE_REGISTRY_PATH}:$(shell echo $$(grep "version:" ./Chart.yaml | awk '{ print $$2}'))

# Codefresh
codefresh-push:
	helm push . ${CODEFRESH_REPOSITORY}
