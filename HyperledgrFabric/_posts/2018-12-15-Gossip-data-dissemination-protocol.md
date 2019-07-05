---
categories: HyperledgrFabric
---
Gossip data 배포 프로토콜

hyperledger fabric은 endorse peer와 commit peer 및 transaction ordering node에서
작업 부하 분산을 통해 blockchain network 성능,보안 그리고 확장성을 최적화합니다.
이러한 분산된 네트워크는 데이터 무결성 및 일관성을 보장하기 위해 안전하고 신뢰할수 있으며,
확장 가능한 데이터 배포 프로토콜이 필요합니다.
이와 같은 요구사항을 충족시키기 위해, Fabric은 gossip data 배포 프로토콜을 구현하였습니다.

Gossip protocol

peer들은 gossip을 활용하여, 원장과 channel data를 확장가능한 방식으로 전파합니다.
gossip 전달은 지속적으로 일어나며, 채널의 각 peer는 (현재와?) 일관된 원장 데이터를 여러 peer로부터 끊임없이 수신받는다.
각각의 gossiped 메시지에 서명함으로써, 위조된 메시지를 보내는 비잔틴 참가자가 쉽게 식별되고,
원치않는 목표에 대한 메세시(들)의 배포를 막을 수 있습니다.

Peers affected by delays, network partitions, or other causes resulting in missed blocks will eventually be synced up to the current ledger state by contacting peers in possession of these missing blocks.

지연, network 

peer들은 영향을 받는다. 지연, network 분할 또는 누락된 블락안의 다른 원인들의 결과로 결국 동기화된다.
이 누락된 블락들의 소유물안의 연결되어 있는 peer들에 의하여 현재 원장 상태 
