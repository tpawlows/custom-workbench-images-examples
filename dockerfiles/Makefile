# Makefile for building Custom Workbench Images
# Currently supports:
# - Gaudi PyTorch
# - Gaudi Data Science

.DEFAULT_GOAL := no-default

HABANA_REPO_URL := https://github.com/HabanaAI/Setup_and_Install
HABANA_REPO_TAG := r1.22.1
HABANA_DIR 	    := Setup_and_Install

.PHONY: no-default help gaudi-pytorch gaudi-datascience clean

no-default:
	@echo "Error: no target specified."
	@echo "Usage: make <gaudi-pytorch|gaudi-datascience|help>"
	@exit 2

help:
	@echo "Targets:"
	@echo "  gaudi-pytorch      Build Gaudi PyTorch image"
	@echo "  gaudi-datascience  Build Gaudi Data Science image"

# Clone the repository if not present; otherwise update it
define ensure_repo
    @if [ ! -d "$(1)/.git" ]; then \
        echo "Cloning $(2) into $(1)"; \
        git clone "$(2)" "$(1)"; \
        cd "$(1)" && git checkout "$(3)"; \
    else \
        echo "Updating $(1) to $(3)"; \
        cd "$(1)" && git fetch --all && git checkout "$(3)" && git pull --rebase; \
    fi
endef

# Build Gaudi-PyTorch workbench image
gaudi-pytorch:
	@echo "Cloning HabanaAI/Setup_and_Install repository..."
	$(call ensure_repo,$(HABANA_DIR),$(HABANA_REPO_URL),$(HABANA_REPO_TAG))

	@echo "Copying Dockerfiles to repository..."
	@cp -r ./gaudi-pytorch/base/Dockerfile.rhel9.6.rhoai.pytorch "$(HABANA_DIR)/dockerfiles/base/"
	@cp -r ./gaudi-pytorch/pytorch/Dockerfile.rhel9.6.rhoai.pytorch "$(HABANA_DIR)/dockerfiles/pytorch/"

	@echo "Building Gaudi-PyTorch ..."
	@cd "$(HABANA_DIR)/dockerfiles/pytorch" && \
		make build BUILD_OS=rhel9.6.rhoai.pytorch

# Build Gaudi-DataScience workbench image
gaudi-datascience:
	@echo "Cloning HabanaAI/Setup_and_Install repository..."
	$(call ensure_repo,$(HABANA_DIR),$(HABANA_REPO_URL),$(HABANA_REPO_TAG))

	@echo "Copying Dockerfiles to repository..."
	@cp -r ./gaudi-datascience/base/Dockerfile.rhel9.6.rhoai.datascience "$(HABANA_DIR)/dockerfiles/base/"
	@cp -r ./gaudi-datascience/datascience/Dockerfile.rhel9.6.rhoai.datascience "$(HABANA_DIR)/dockerfiles/pytorch/"

	@echo "Building Gaudi Data Science ..."
	@cd "$(HABANA_DIR)/dockerfiles/pytorch" && \
		make build BUILD_OS=rhel9.6.rhoai.datascience

clean:
	@rm -rf "$(HABANA_DIR)"
	@echo "Removed $(HABANA_DIR)"