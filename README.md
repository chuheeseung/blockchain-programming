# README.md

# **blockchain-programming**

2022-1 블록체인프로그래밍 강의

강의 자료 https://github.com/smu405/e

이더리움 remix http://remix.ethereum.org/

# **접속 명령어 정리**

- geth 접속하기 (cmd)
    
    ```python
    _geth_now.bat
    ```
    
- geth 로그 접속하기 (새 cmd) geth 접속 후 실행
    
    ```python
    !geth attach http://localhost:8445
    ```
    
- loadScript 따옴표 잘 확인하기 (주피터노트북)
    
    ```python
    !geth --exec "loadScript('e_test0.js')" attach http://localhost:8445
    ```
    
- 명령어 출력 방법 (geth 콘솔)
    
    ```python
    eth.accounts
    ```
    
- 명령어 출력 방법 (주피터노트북)
    
    ```python
    !geth --exec eth.accounts attach http://localhost:8445
    !geth --exec "eth.accounts" attach http://localhost:8445
    ```
    
- unlockAccount 명령어 (geth 콘솔 cmd)
    
    ```python
    personal.unlockAccount(eth.accounts[1])
    ```
    
- 웹서버 띄우는 명령어
    
    ```python
    python -m http.server 8045
    ```
    

- eth. 명령어
    - **`eth.accounts`** : 계정 확인 (배열)
    - **`eth.getBalance()`** : 계좌 잔고 확인
        
        eth.getBalance(eth.accounts[0]);
        
    - **`miner.start();`** : 마이닝으로 충전
    - **`miner.stop();`** : 마이닝 충전 정지
    - **`eth.blockNumber;`**: 생성된 블록 개수
    - **`eth.coinbase`** : 입출금이 일어나는 주 계정 (앞 5글자로 판별)
    - **`eth.getTransactionCount()`** : 해당하는 nonce 정보 출력
    - web3.fromWei(바꾸려는것, “ether”) : wei → ether 단위 변환

- admin. 명령어
    - **`admin.nodeInfo`** : node 자신과 관련한 정보
    - **`net.peerCount`** : 현재 peer 노드 개수 출력 - peer 수는 가변적
    - **`net.listening`** : peer를 찾고 있는 상태인지 확인 - true : 찾고 있음

- miner 명령어
    - **`miner.setEtherbase(교체해줄계좌)`** : coinbase 변경 함수

- personal 명령어
    - **`personal.listAccounts`** : 자신이 개설한 계정의 목록 출력
    - **`txpool.inpect`** : transaction의 상황 알려줌
        
        txpool : 트랜잭션이 마이닝되기 전에 대기하는 transaction pool 상황 알려줌
        
    - **`txpool.status`** : transaction 상황을 갯수로 알려줌