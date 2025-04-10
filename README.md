# Website
This repository contains the Antora playbook and the GitHub actions needed to build and publish the website

```mermaid
erDiagram
    CUSTOMER ||--o{ ORDER : places
    ORDER ||--|{ LINE-ITEM : contains
    CUSTOMER }|..|{ DELIVERY-ADDRESS : uses
```

```mermaid
flowchart LR
    subgraph "<i class="fa-brands fa-github"></i> www"
        subgraph en-www["<i class="fa-solid fa-folder-open"></i> en"]
            en-antora-playbook(antora-playbook.yml)
        end
    end
    subgraph "<i class="fa-brands fa-github"></i> Website-UI"
        subgraph en-ui["<i class="fa-solid fa-folder-open"></i> en"]
            en-ui-bundle(ui-bundle.zip)-->en-www
        end
    end
    subgraph "<i class="fa-brands fa-github"></i> Website-Home-Section"
        subgraph en-hs["<i class="fa-solid fa-folder-open"></i> en"]
            en-hs-content(ui-bundle.zip)-->en-www
        end
        end
    subgraph "<i class="fa-brands fa-github"></i> cti-documentation"
        subgraph en-doc["<i class="fa-solid fa-folder-open"></i> en"]
            en-conv1(<i class="fas fa-code-branch"></i> V1.0)-->en-www
            en-conv2(<i class="fas fa-code-branch"></i> V2.0)-->en-www
        end
    end
```