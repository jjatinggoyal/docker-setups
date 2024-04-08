# Pre-Requisites

- Runtime Environment for Docker - Docker Desktop, Colima etc.
- ENV `OPENSEARCH_INITIAL_ADMIN_PASSWORD` - password for opensearch nodes
- Ensure kernel parameter value `vm.max_map_count` is set to a minimum of `262144`

    - if using colima, do -
        ```
        colima ssh
        sudo sysctl -w vm.max_map_count=262144
        ```

- Create a topic named `test` in kafka-ui.

# Run

- `docker-compose up`
    
    - Access Opensearch-Dashboard at localhost:5601
    - Opensearch nodes at localhost:9200, localhost:9201 
    - Kafka brokers available at kafka:9092
    - kafka-ui available at localhost:8080
    - Logstash consumes from Kafka topic `test`, and outputs to opensearch nodes