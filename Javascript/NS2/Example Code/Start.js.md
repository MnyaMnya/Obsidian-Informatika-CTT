```javascript
/** @param {NS} ns */

export function UsedRam(ns,script,host) {

  var result = (ns.getServerMaxRam(host)-ns.getServerUsedRam(host))/ns.getScriptRam(script,host);

  return result.toFixed(0);

}

export async function main(ns) {

  var host = ns.getHostname();

  var list = ns.scan(host);

  while(true){

  for(let i = 0; i<list.length; i++){

    if(ns.getServerRequiredHackingLevel(list[i])<=ns.getHackingLevel(list[i])){

      if(ns.hasRootAccess(list[i])==false&&ns.getServerNumPortsRequired(list[i])==0){

        await ns.nuke(list[i]);

      }

      if (ns.hasRootAccess(list[i])==false&&ns.getServerNumPortsRequired(list[i])==1){

        ns.brutessh(list[i]);

      }

      if (ns.hasRootAccess(list[i])==false&&ns.getServerNumPortsRequired(list[i])==2){

        await ns.ftpcrack(list[i]);

      }

      if (ns.hasRootAccess(list[i])==false&&ns.getServerNumPortsRequired(list[i])==3){

        await ns.relaysmtp(list[i]);

      }

      if(ns.hasRootAccess(list[i])==true){

       await ns.scp("weaken.js",list[i]);

       await ns.scp("grow.js",list[i]);

        await ns.scp("hack.js",list[i]);

       for(let i = 0; i<list.length; i++){

          if(ns.getServerMaxRam(list[i])-ns.getServerUsedRam(list[i])>=2)

if(ns.getServerSecurityLevel(list[i])-ns.getServerMinSecurityLevel(list[i])>ns.getServerMinSecurityLevel(list[i])/4&&UsedRam(ns,"weaken.js",list[i])!=0){

        ns.exec("weaken.js",list[i],UsedRam(ns,"weaken.js",list[i]));

       }

       if(ns.getServerMoneyAvailable(list[i])/ns.getServerMaxMoney(list[i])<0.75&&UsedRam(ns,"grow.js",list[i])!=0){

        ns.exec("grow.js",list[i],UsedRam(ns,"grow.js",list[i]));

       }

       if(ns.getServerMoneyAvailable(list[i])/ns.getServerMaxMoney(list[i])>0.25&&UsedRam(ns,"hack.js",list[i])!=0){

        ns.exec("hack.js",list[i],UsedRam(ns,"hack.js",list[i]));

       }

       await ns.sleep(10);

       }

       }

    }}

    await ns.sleep(10);

  }

  await ns.sleep(10);

}
```