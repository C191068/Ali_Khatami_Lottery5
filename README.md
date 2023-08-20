# Ali_Khatami_Lottery5(Learning from the video of Stephen Fluin and Richard Gottleber)

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

So we can generate data off chain  and pass that in this called checkData <br>

![c65](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/cedf677f-e934-42c9-90ed-bcf5df41085b)

and that becomes performdata passed into performUpkeep <br>

performUpkeep method is where we gonna verify that things are correct <br>
and things actually should be modified and run on blockchain <br>

then actually make the stae change <br>


![c66](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/56c1e3bc-28e9-4188-a595-e15db35d9f31)

here 30means it will not update more than 30 seconds <br>

![c67](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/706cbe86-25ae-4966-8ff7-9b96db205524)

here when we click deeploy button metamask window will pop up <br>

![c68](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/4fd7b81f-554c-454e-8087-35cbcb52a522)

Then successful transaction wil coccur <br>

![c72](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/c04d9bcb-81fb-4141-92ff-262d95cb599e)

Now will copy the deployed contract address and register that contract for upkeep <br>

For that we will go to this link https://automation.chain.link/

![c69](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/98237c06-1ebc-41f4-86e1-73a04a2f27d9)

The above is the application that powers the autiomation network <br>

![c70](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/4ba65acf-64ef-4985-ac58-1ade24ec145c)

At first we will connect our metamsk wallet account <br>

![c71](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/8929dfe7-be47-4c90-99c3-9b177f75d8e2)

Then we will click the above button <br>

![k1](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/573e8ac6-db80-4765-9059-9bf7fa3f5096)

then we will select the time based option <br>

![k2](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/4defe603-e24a-4f3b-8c6e-c8c35011ec52)

then we will paste the contract address here <br>

![k3](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/9f3831af-43c1-4f81-bc14-ebcbecd1ad1f)

Then we will write the above <br>

![k4](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/010670b0-3bcf-4215-b101-37adc39479f0)

Then we will write 1 minute like the above <br>


![k6](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/712ae1de-214e-44e3-88cb-221e40e4216a)

after then it will take some time for processing  <br>

![k7](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/06ce29e5-41cf-45b8-931e-11c0909c2bea)

then it will successfuully reegistered <br>

![k8](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/52ef0bf7-b051-4b01-b6bf-d559800cdb03)

It is saying it is underfunded <br>

![k9](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/32bce35c-90da-48c3-9adb-8216ae62b11d)

then we have to select the above optiuon <br>

![k10](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/cdcca891-4327-466f-af1a-90c267cb9b6b)

then we will give 7 link <br>

![k11](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/c397d34a-d867-45cb-a763-8814d542d7da)

metamask will pop up  <br>

![k13](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/f2886c11-68d3-45b8-b9a6-97208fe7175e)
Successful transaction will occur and it will become active <br>


![k14](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/4bb303bd-8d6c-4221-b2d8-207e464b96e4)

here in the history we can keep track of what has happened with our upkeep <br>

We can also see that perform upkeep has run how much it cost us and how much link remaining <br>


![k15](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/c5a9a962-5bf1-4a6c-b5e8-d0f206aebda9)

here we can see minimum balance this is because automation network has run a simulation<br>
to see how much this could cost <br>
we have to keep our balance at least at that minimum balance <br>
In order for to continue functioning <br>

![k16](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/94d53121-422a-45a4-b225-12c35e6c12fa)

here in our deployed ciontract when we click count button it shows 13 becauuse chainlink keeper <br>
network has performed upkeep on my contract <br>

![k17](https://github.com/C191068/Ali_Khatami_Lottery5/assets/89090776/c7049450-6532-4910-800b-583f4ffb9a95)

here in the history we can see how many times chainlinkkeeper called the Performupkeep method <br>

and the amount of link decreasing <br>

























