Gossip data 배포 프로토콜

hyperledger fabric은 transaction (승인 및 commit) 실행 peer 및
transaction ordering node에서 작업 부하 분산을 통해 blockchain network 성능,
보안 그리고 확장성을 최적화합니다.

이러한 분산된 네트워크는 데이터 무결성 및 일관성을 보장하기 위해 
안전하고 신뢰할수 있으며, 확장 가능한 데이터 배포 프로토콜이 필요합니다.

To meet these requirements,
Fabric implements a gossip data dissemination protocol.
이러한 요구사항을 충족시키기 위해,
Fabric은 gossip data 배포 프로토콜을 구현하였습니다.

