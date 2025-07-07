flowchart TD
    User --> ReactApp
    ReactApp --> GoBackend
    GoBackend --> DB[(App Database)]
    GoBackend --> MetabaseEmbed[Generate JWT for Metabase]

    ReactApp -->|iframe w/ JWT| MetabasePod[Metabase Dashboard]
    MetabasePod --> DB

    subgraph Kubernetes
        MetabasePod
        GoBackend
        ReactApp
    end
