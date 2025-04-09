```mermaid
flowchart BT
  subgraph band_td [ ]
    direction LR
    
    cto[CTO]

    hoe[Head of Engineering]

    cse[Head of Cloud & Security Engineering]

    subgraph legend [Where]
      direction LR

      A -->|Reports To| C
      B -.->|Career Pathway| C
    end  
  end

  subgraph band_mgmt [ ]
    direction LR

    em[Engineering Manager]
    qam[QA/QE Manager]
    eol[Engineering Operations Lead]
  end

  subgraph band_teams [ ]
    direction LR

    subgraph report_cto [ ]
      direction BT
      
      pa[Principal Architect]
      a[Architect]
      de[Distinguised Engineer]

      a -.-> pa
    end

    subgraph report_em [ ]
      direction BT

      pe[Principal Engineer]
      le[Lead Engineer]
      se[Senior Engineer]
      e[Engineer]
      ge[Graduate Engineer]

      ge -.-> e
      e -.-> se

      subgraph stream_lead [ ]
        direction BT

        se -.-> pe
        se -.-> le
      end
    end

    subgraph report_cse [ ]
      direction BT

      pce[Principal Cloud Engineer]
      lce[Lead Cloud Engineer]
      sce[Senior Cloud Engineer]
      ce[Cloud Engineer]
      gce[Graduate Cloud Engineer]

      gce -.-> ce
      ce -.-> sce
      sce -.-> pce
      sce -.-> lce
    end

    subgraph report_qam [ ]
      direction BT

      lqe[Lead QA/QE Engineer]
      pae[Principal Automation Engineer]
      sqe[Senior QA/QE Engineer]
      qe[QA/QE Engineer]
      gqe[Graduate QA/QE Engineer]

      gqe -.-> qe
      qe -.-> sqe
      sqe -.-> pae
      sqe -.-> lqe
    end
  end

  report_em --> em
  report_cse --> cse
  report_qam --> qam
  report_cto --> cto

  qam --> cto

  em --> hoe
  eol --> hoe

  pae -.-> report_em
  le -.-> eol
  le -.-> em
  pe -.-> report_cto

  classDef band fill:transparent,stroke:none;
  class band_td,band_mgmt,band_teams band;
  style legend fill:transparent,stroke-dasharray:5;
```