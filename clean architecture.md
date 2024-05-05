# Clean Architectures


## Arquitectura hexagonal

graph TD
    A[Application Layer] -->|Uses| B[Domain Layer]
    B -->|Uses| C[Infrastructure Layer]
    C --> D[Inbound Adapters]
    C --> E[Outbound Adapters]
    D --> F[UI/External Interfaces]
    E --> G[Database/External Services]
    B --> H[Business Logic]

    A --> I((Book Service))
    D --> J((Book Controller))
    E --> K((Book Repository))
    E --> L((User Repository))
    E --> M((Lend Repository))
    H --> N{Model}
    N --> O((Author))
    N --> P((Book))
    N --> Q((User))
    N --> R((Category))
    N --> S((DocType))
    N --> T((Lend))
    N --> U((Penalty))

    classDef hexagon fill:#f9f,stroke:#333,stroke-width:4px;
    class A,B,C,D,E,F,G,H hexagon

