graph TD
    A[客户下单] --> B[订单类型判定]
    B -->|标准订单| C[标准生产排程]
    B -->|定制订单| D[定制需求审核]
    C --> E[零件库存检查]
    D -->|审核通过| E
    D -->|需要额外时间| F[通知客户延期]
    E -->|库存充足| G[装配生产]
    E -->|库存不足| H[零件采购]
    H -->|国内供应商| I[短期采购]
    H -->|国际供应商| J[长期采购]
    I --> G
    J --> G
    G --> K[质量控制]
    K -->|合格| L[物流配送]
    K -->|不合格| M[返工]
    M --> K
    L -->|国内交付| N[国内配送]
    L -->|国际交付| O[国际物流]
    N --> P[客户交付]
    O --> P

    classDef default fill:#f9f,stroke:#333,stroke-width:2px;
    class A,B,C,D,E,F,G,H,I,J,K,L,M,N,O,P default;
