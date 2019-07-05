---
categories:
  - ethereum
tags:
  - ethereum
  - golang
  - web3
---

Make sure your gopath is correct

export GOPATH=$HOME/go
export PATH=$PATH:$GOPATH/bin
Install abigen

go get -u github.com/ethereum/go-ethereum
cd $GOPATH/src/github.com/ethereum/go-ethereum/
make
make devtools
Compile abi

solc --abi MyContract.sol | awk '/JSON ABI/{x=1;next}x' > MyContract.abi
solc --bin MyContract.sol | awk '/Binary:/{x=1;next}x' > MyContract.bin
Compile abi to Go package

abigen --bin=MyContract.bin --abi=MyContract.abi --pkg=mycontract --out=MyContract.go
