# RockPaperScissors
Ethereum Rock Paper Scissors Dapp

# How to play  
 To play all you need is to use JSON Interface.  
- Generate a pair of values: "Hash" & "SecretRand" in public function CreateHash and save it somewhere. Remember to provide good random seed!  
- Send the Hash with 0.1 ETH to Play function  
- Enter your hash to public "Is payout ready_info function", from now on you should get hints what you should do in "Info" field.  
- Wait for Other Player / or just for new block mined in some cases (always rely on IsPayoutReadyInfoFunction() with your hash provided!)  
- Announce your SecretRand in announce function.  
- Wait for other player announce / new block  
- Withdraw your win/draw  
- Play again ;)  
  
# Address of contract 
    0x1d77340D3819007BbfD7fdD37C22BD3b5c311350

# JSON Interface (ABI)

    [{"constant":true,"inputs":[],"name":"Announcement","outputs":[{"name":"","type":"string"}],"type":"function"},{"constant":false,"inputs":[{"name":"HASH","type":"bytes32"}],"name":"play","outputs":[],"type":"function"},{"constant":false,"inputs":[{"name":"MySecretRand","type":"bytes32"}],"name":"announce","outputs":[],"type":"function"},{"constant":true,"inputs":[{"name":"MyHash","type":"bytes32"}],"name":"IsPayoutReady__InfoFunction","outputs":[{"name":"Info","type":"string"}],"type":"function"},{"constant":true,"inputs":[{"name":"RockPaperOrScissors","type":"uint8"},{"name":"WriteHereSomeUniqeRandomStuff","type":"string"}],"name":"CreateHash","outputs":[{"name":"SendThisHashToStart","type":"bytes32"},{"name":"YourSecretRandKey","type":"bytes32"},{"name":"Info","type":"string"}],"type":"function"},{"constant":true,"inputs":[{"name":"SecretRand","type":"bytes32"}],"name":"WhatWasMyHash","outputs":[{"name":"HASH","type":"bytes32"}],"type":"function"},{"constant":false,"inputs":[{"name":"HASH","type":"bytes32"}],"name":"withdraw","outputs":[],"type":"function"},{"constant":true,"inputs":[],"name":"LimitOfMinutes","outputs":[{"name":"","type":"uint8"}],"type":"function"},{"constant":true,"inputs":[],"name":"Cost","outputs":[{"name":"","type":"uint256"}],"type":"function"},{"inputs":[],"type":"constructor"}]
 
# Time limits
- there is public variable "LimitOfMinutes" (at this moment equal to 255) which defines how long you need to wait for other player before you can refund (via Withdraw function).  

# fees
- in case of win you can withdraw 2x the cost of Play function with 1% fee,  
- in case of draw 1x the cost + 1% fee  
- in case of refund there is no fee  

# verify the code
verified code with comments (and Player Interface in it):  
https://etherscan.io/address/0x1d77340D3819007BbfD7fdD37C22BD3b5c311350#code
