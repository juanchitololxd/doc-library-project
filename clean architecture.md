# Clean Architectures


## Arquitectura hexagonal

```mermaid
graph TD
    app[Application Layer] -->|Uses| dom[Domain Layer]
    dom -->|Uses| infra[Infrastructure Layer]

    subgraph dom[Domain Layer]
        exceptions[Exceptions]
        model[Model]
    end

    subgraph app[Application Layer]
        bookService[Book Service]
    end

    subgraph infra[Infrastructure Layer]
        inbound[Inbound]
        repo[Repositories]
    end

    subgraph inbound[Inbound]
        bookController[Book Controller]
    end

    subgraph repo[Repositories]
        bookRepo[Book Repository]
        lendRepo[Lend Repository]
        userRepo[User Repository]
    end

    subgraph exceptions[Exceptions]
        lendsExc[Lends Exception]
        libExc[Library Exception]
        usersExc[Users Exception]
    end

    subgraph model[Model]
        author[Author]
        book[Book]
        category[Category]
        docType[DocType]
        lend[Lend]
        penalty[Penalty]
        user[User]
    end
