allow_k8s_contexts('local')
docker_prune_settings(num_builds=1, keep_recent=1)

aissemble_version = '1.11.0-SNAPSHOT'

build_args = { 'DOCKER_BASELINE_REPO_ID': 'ghcr.io/',
               'VERSION_AISSEMBLE': aissemble_version}

# Kafka
yaml = helm(
    'verify-invocation-service-deploy/src/main/resources/apps/kafka-cluster',
    values=['verify-invocation-service-deploy/src/main/resources/apps/kafka-cluster/values.yaml',
        'verify-invocation-service-deploy/src/main/resources/apps/kafka-cluster/values-dev.yaml']
)
k8s_yaml(yaml)

# Add deployment resources here