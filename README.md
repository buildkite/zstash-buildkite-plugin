# Zstash Buildkite Plugin

Uses zstash to cache dependencies.

# Example Configuration

```
steps:
  - plugins:
    - bk-playground/zstash#v0.1.0:
        id: "node"
        key: '{{ id }}-{{ agent.os }}-{{ agent.arch }}-{{ checksum "package-lock.json" }}'
        fallback_keys: |
          {{ id }}-{{ agent.os }}-{{ agent.arch }}-
        paths: |
          node_modules
        bucket-url: $BUCKET_URL
```

## License

This application is released under Apache 2.0 license.