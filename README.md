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

![c57](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/d9bc798d-e8f0-4de6-be28-073c658f7b1a)

Now we will deploy the above contract in REMIX <br>

![c58](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/15daf5a1-be8a-4ae6-93fa-e46c17d2511e)

We opened the contarct at REMIX IDE <br>


![c59](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/308c0973-e4ab-4dcf-a11c-ec376f187695)

We can see simple counter here <br>

![c60](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/cf12803a-dc01-4efd-9714-8e40767f2392)

we are able to specify when we create the contract and upddate interval <br>

![c61](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/99ca7e33-a2ef-4e2a-95ff-db20a73aca7c)


And the contract can verify Hey, it has enough time passed and if it has let update the counter <br>




![c62](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/99a46e07-5ea7-46e8-a072-a14f7109fdca)

Chainlink keeper compatible contract use two important methods that are part of this AutomationCompatibleInterface <br>

![c63](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/0003f1a1-b4b8-4a4a-9bd8-b73e5e1b3bb6)

The first one is function checkUpkeep  <br>

function checkUpkeep is special because this is where the off chain computation happens <br>

This is a method that not actually run on chain <br>

This is run off chain by anode form chainlink keeper network <br>

But the gas used here is not the gas on chain <br>

If the function checkUpkeep returns that bool upkeepNeeded then it is gonna go ahead and perform upkeep <br>\

![c64](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/6da62ee8-66b3-47ec-b496-74e7931fa038)

So we can generate data off chain  and here in the above there is a new update about checkData <br>















