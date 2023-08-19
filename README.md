# Ali_Khatami_Lottery5(Learning from the video of Stephen Fluin)

### Introduction to Chainlink keepers 

now we update our contract at https://github.com/C191068/Ali_Khatami_Lottery4.git<br>
so that it can not only pick up a verifiably random winner but it can also do <br>

this all programmatically and automatically trigger picking up of random winner based on some time interval <br>

without us having interact with it and in a deentralized contract  <br>

In order for us to automatically  trigger a smart contract based on some parameter <br>

be time parameter , maybe the price of some asset ,maybe there is some money in <br>

the liquidity pool or really whatever trigger that we want  <br>

We can use chain link keepers <br>

![c54](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/e57ceaf3-e63d-44cd-b694-dfdb89ef3208)
Chainlink keepers is now chainlink automation and the link is given below:
https://docs.chain.link/chainlink-automation/automation-release-notes#chainlink-keepers-is-now-chainlink-automation

![c55](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/7aef0a10-8f84-43ab-8e41-42d2cd48b94d)

There are mainly two part in building chainlink keeper  smart contract <br>


![c56](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/b4829e64-f778-4e5a-94aa-d27453531f0c)

fisrst wwe need to write a smart contract by implementi9ng the above two methods <br>

next we need to register that smart contract for upkeep with the chainlink keeper network <br>















