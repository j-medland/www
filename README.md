# Website
This repository contains the Antora playbook and the GitHub actions needed to build and publish the website

```mermaid
flowchart LR
    subgraph www["📚 <a href='https://github.com/LabVIEWCommunityTraining/www'>www</a>"]
        subgraph en-www["📂 en"]
            en-antora-playbook(antora-playbook.yml)
        end
    end
    subgraph website-ui["📚 <a href='https://github.com/LabVIEWCommunityTraining/website-ui'>Website-UI</a>"]
        subgraph en-ui["📂 en"]
            en-ui-bundle(ui-bundle.zip)-->en-www
        end
    end
    subgraph website-home["📚 <a href='https://github.com/LabVIEWCommunityTraining/website-home-section'>Website-Home-Section</a>"]
        subgraph en-hs["📂 en"]
            en-hs-content(ui-bundle.zip)-->en-www
        end
        end
    subgraph cti-docs["📚 <a href='https://github.com/LabVIEWCommunityTraining/cti-documentation'>cti-documentation</a>"]
        subgraph en-doc["📂 en"]
            en-conv1(<i class="fas fa-code-branch"></i> V1.0)-->en-www
            en-conv2(<i class="fas fa-code-branch"></i> V2.0)-->en-www
        end
    end
```