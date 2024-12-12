# Helm Chart for Open Bank Project

This Helm chart is used to deploy the Open Bank Project API and related services.

## Parameters


### obp-api Parameters

| Parameter | Description | Default |
| --------- | ----------- | ------- |
| `enabled` | Enable the obp-api service | `true` |
| `replicaCount` | Number of replicas for obp-api | `1` |
| `defaultDomain` | Default domain for obp-api | `api.openbankproject.com` |
| `super_admin_user_ids` | Super admin user IDs | `32274848-c124-49c3-a3c7-d292bebfc3da` |
| `jdbc_driver` | JDBC driver class name | `org.postgresql.Driver` |
| `jdbc_url` | Base64 encoded JDBC URL | `amRiYzpwb3N0Z3Jlc3FsOi8vbXlkYi5jb20vYXBpP3VzZXI9YXBpJnBhc3N3b3JkPW15cGFzcw==` |
| `hostname` | Hostname for the API | `https://api.openbankproject.com` |
| `migration_scripts_enabled` | Enable migration scripts | `true` |
| `migration_scripts_execute_all` | Execute all migration scripts | `true` |
| `webui_override_style_sheet` | URL for the override stylesheet | `https://static.openbankproject.com/css/override.css` |
| `authuser_skipemailvalidation` | Skip email validation for auth users | `true` |
| `connector` | Connector type | `mapped` |
| `webui_api_explorer_url` | URL for the API Explorer | `https://api-explorer.openbankproject.kube` |
| `webui_sofi_url` | URL for SOFI | `https://api-sofit.openbankproject.kube` |
| `webui_api_manager_url` | URL for the API Manager | `https://api-manager.openbankproject.kube` |
| `webui_api_tester_url` | URL for the API Tester | `https://api-tester.openbankproject.kube` |
| `webui_header_logo_left_url` | URL for the header logo | `https://static.openbankproject.com/images/OBP_full_web.png` |
| `write_metrics` | Enable writing metrics | `true` |
| `JAVA_OPTIONS` | Java options | `-Drun.mode=production` |
| `cache_redis_url` | Redis URL for caching | `something.redis.org` |
| `cache_redis_port` | Redis port for caching | `6379` |
| `keystore_password` | Base64 encoded keystore password | `JzEyMzQ1Nic=` |
| `truststore` | Base64 encoded truststore | `YmFzZTY0IGVuY29kZWQgdHJ1c3RzdG9yZS5qa3M=` |
| `keystore` | Base64 encoded keystore | `YmFzZSA2NCBlbmNvZGVkIGtleXN0b3JlLmprcw==` |
| `image` | Docker image for obp-api | `docker.io/openbankproject/obp-api:latest` |

### obp-api-explorer-ii Parameters

| Parameter | Description | Default |
| --------- | ----------- | ------- |
| `enabled` | Enable the obp-api-explorer-ii service | `true` |
| `replicaCount` | Number of replicas for obp-api-explorer-ii | `1` |
| `defaultDomain` | Default domain for obp-api-explorer-ii | `api-explorer.openbankproject.com` |
| `hostname_apimanager` | Hostname for API Manager | `https://api-manager.openbankproject.com` |
| `defaultapiexplorer_ii_Domain` | Default domain for API Explorer II | `https://api-explorer.openbankproject.com` |
| `apiexplorer_ii_consumer_key` | Base64 encoded consumer key for API Explorer II | `c29tZV92YWx1ZQ==` |
| `apiexplorer_ii_consumer_secret` | Base64 encoded consumer secret for API Explorer II | `c29tZV92YWx1ZQ==` |
| `hostname_api` | Hostname for API | `https://api.openbankproject.com` |
| `hostname_apiexplorer_ii` | Hostname for API Explorer II | `https://api-explorer.openbankproject.com` |
| `apiexplorer_ii_replicaCount` | Number of replicas for API Explorer II | `1` |
| `apiexplorer_ii_server_session_password` | Base64 encoded server session password for API Explorer II | `dmVyeV9zZWNyZXQ=` |
| `node_env` | Node environment | `production` |
| `redis_url` | Redis URL | `redis://127.0.0.1:6379` |
| `image_backend` | Docker image for API Explorer II backend | `docker.io/openbankproject/api-explorer-ii:latest` |
| `image_frontend` | Docker image for API Explorer II frontend | `docker.io/openbankproject/apiexplorer-ii-nginx:latest` |

### obp-api-manager Parameters

| Parameter | Description | Default |
| --------- | ----------- | ------- |
| `enabled` | Enable the obp-api-manager service | `true` |
| `replicaCount` | Number of replicas for obp-api-manager | `1` |
| `apimanager_hostname` | Hostname for API Manager | `https://api-manager.openbankproject.kube` |
| `apimanager_callback_base_url` | Callback base URL for API Manager | `https://api-manager.openbankproject.kube` |
| `apimanager_api_version` | API version for API Manager | `4.0.0` |
| `apimanager_secret_key` | Base64 encoded secret key for API Manager | `c29tZXNlY3JldGtleQ==` |
| `apimanager_allowed_hosts` | Allowed hosts for API Manager | `127.0.0.1,localhost,api-manager.openbankproject.kube` |
| `apimanager_consumer_key` | Base64 encoded consumer key for API Manager | `NDBmMDR0aTMzaG9rMmV2bnfdsaffdFSEFSFDSp3d3duNWVqNTVsMjJjcA==` |
| `apimanager_consumer_secret` | Base64 encoded consumer secret for API Manager | `dTViNG5oaXpid3U1MnZ5fdsafFESFDSEFZ2NubGI1YXZ2d2t5cmZheQ==` |
| `apimanager_exclude_apps` | Apps to exclude from API Manager | `[u'API Manager', u'SOFIT', u'API Tester', u'null']` |
| `apimanager_exclude_functions` | Functions to exclude from API Manager | `getMetrics,getConnectorMetrics,getAggregateMetrics` |
| `apimanager_exclude_url_pattern` | URL patterns to exclude from API Manager | `['%management/metrics%', '%management/aggregate-metrics%']` |
| `apimanager_apiexplorer_app_name` | App name for API Explorer | `API Explorer` |
| `image` | Docker image for API Manager | `docker.io/openbankproject/api-manager:develop` |

### legacy obp-api-explorer Parameters

| Parameter | Description | Default |
| --------- | ----------- | ------- |
| `enabled` | Enable the obp-api-explorer service | `false` |
| `replicaCount` | Number of replicas for obp-api-explorer | `1` |
| `defaultDomain` | Default domain for obp-api-explorer | `api-explorer.openbankproject.com` |
| `apiexplorer_log_level` | Log level for API Explorer | `ERROR` |
| `apiexplorer_consumer_key` | Consumer key for API Explorer | `eGpqeXJ2c3drYWFwddsafaDDDCfdsafasdNub3h0ZWdnNDFxNGRmMw==` |
| `apiexplorer_consumer_secret` | Consumer secret for API Explorer | `MGJtcHhnd2Joa2hqeWxuNfdsafadDRJDJKFJFV5d21qbm80eXF3NA==` |

