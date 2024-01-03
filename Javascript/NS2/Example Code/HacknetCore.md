```javascript
/** @param {NS} ns */

export async function main(ns) {

  do{

    var map1 = [];

    var min;

    var index;

    var target=1;

    for (var i=0;i < ns.hacknet.numNodes();i++){

      var value = ns.hacknet.getCoreUpgradeCost(i);

      map1[i]=value;

      if(min>value || i==0){

        min = value;

        index = i;

      }

      target = min;

      await ns.sleep(10);

    }

  ns.hacknet.upgradeCore(index,1);

  await ns.sleep(10);

  }while((ns.getServerMoneyAvailable("home")>target*2));

}
```