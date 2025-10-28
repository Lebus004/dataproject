# Stream App (Maven)

This is a Maven multi-module project containing:
- `stream-generator`: produces events to Kafka (from `event_generator.EventGenerator`).
- `stream-processor`: Kafka Streams processors (basic and advanced).

## Build

```bash
mvn -q -f pom.xml clean package
```

## Run

From within each module, run the main class, e.g.

```bash
# Generator
mvn -q -pl stream-generator -am exec:java -Dexec.mainClass=event_generator.EventGenerator

# Processor (basic)
mvn -q -pl stream-processor -am exec:java -Dexec.mainClass=event_processor_basic.EventProcessorBasic

# Processor (advanced)
mvn -q -pl stream-processor -am exec:java -Dexec.mainClass=event_processor_advanced.EventProcessorAdvanced
```
You may need to add appropriate Kafka bootstrap server configs in the code or via environment variables as expected by your classes.
