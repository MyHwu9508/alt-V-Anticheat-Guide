<h1 align="center">alt-V-Anticheat-Guide</h1>

---

## :warning: **DISCLAIMER** :warning:

This guide is more or less designed to help you find approaches to detect & ban cheaters. Please do not use the same variable names, metas, or code in any case.
An anticheat is characterized by individuality, because otherwise the cheat developers can understand your anticheat and outsmart it easily!

## Contents

1. [Introduction](#1-introduction)
2. [Type of cheaters](#2-type-of-cheaters)  
   2.1 [The rager](#21-the-rager)  
   2.2 [Casual cheaters](#22-casual-cheaters)  
   2.3 [Legit cheaters](#23-legit-cheaters)  
   2.4 [Careful cheaters](#24-careful-cheaters)
3. [Type of cheats](#3-type-of-cheats)  
   3.1 [Injectors & Executors](#31-injectors--executors)  
   3.2 [Casual cheats](#32-casual-cheats)
4. [Anticheat Implementations](#4-anticheat-implementations)  
   4.1 [Code security](#41-code-security)  
   4.2 [Data security](#42-data-security)  
   4.3 [Self banning events](#43-self-banning-events)  
   4.4 [No bushes/ props detection](#44-no-bushesprops-detection)  
   4.5 [Code injectors](#45-code-injectors)  
   4.6 [ESP](#46-esp)  
   4.7 [Weapon (attachments) giving](#47-weapon-attachments-giving)  
   4.8 [Weapon modifications](#48-weapon-modifications)  
   4.9 [Classic aimbot](#49-classic-aimbot)  
   4.10 [Silent aimbot & magic bullets](#410-silent-aimbot--magic-bullets)  
   4.11 [Healing](#411-healing)  
   4.12 [Ammunition](#412-ammunition)  
   4.13 [Pressed keys](#413-pressed-keys)  
   4.14 [Explosives](#414-explosives)  
   4.15 [Teleporting](#415-teleporting)  
   4.16 [Noclip](#416-noclip)  
5. [Multiaccount detection](#5-multiaccount-detection)
6. [Things you should consider](#6-things-you-should-consider)  
   6.1 [Spectator mode](#61-specator-mode)  
   6.2 [forced debug mode](#62-force-debug-mode)  
   6.3 [Bullet tracers](#63-bullet-tracers)  
   6.4 [hiding while spectator mode](#64-hiding-while-spectator-mode)   
   6.5 [Vehicle cheats](#65-vehicle-cheats)

## 1. Introduction

Cheats are a problem for many GTA5 MP servers. It is often the case that cheaters can use software for several months and years without being detected. So-called PC checks, or video recordings are also not really helpful, because almost every cheat leaves no trace and e.g. Silent Aimbots with low FOV is impossible to detect in video recordings.

It is also important that you always protect your code and especially the anticheat, so that players can't easily trick it!

It is also absolutely important that you only ban people from your server with your anticheat who are really obviously cheating and causing damage. If you are unsure about a cheater, then really check all parameters before the ban and make sure that you have as few false-bans as possible. Nothing is worse than being banned without having cheated. After all, there's hardly anything you can do about a ban, and of course it can damage the server's reputation in a very negative way.

## 2. Type of cheaters

Each cheater has their own mindset and as an anticheat developer you really have to think about each of these players and really cover all of them seamlessly so that you really get them all. However, on a server with a strict whitelist with multiaccount mechanisms, for example, you can often skip a lot of checks on Rage cheaters because you simply won't have them. Likewise, on a freeroam server, legit cheaters are unimportant, as they may even have the same options in their cheat as the server itself.

Also, try to put yourself in a cheater's position and think about what they would use to achieve certain advantages.

### 2.1 The rager

Rage cheaters are a really special species, as they try to forcefully inflict as much damage as quickly as possible. On an RP server, for example, they disrupt really big and important RP situations and usually want the maximum attention. Not infrequently, these are well-known groups, which then upload these situations to YouTube and are happy about a few views.
A rage cheater usually uses an executor to run his own code. This then, for example, has found out the synced metas and can use ESP to pick out exactly the people who want to harass anyway. He then teleports directly there or uses noclip. Also popular are things like exploding cars or players, spawning objects that crash all players in the vicinity or the classic RPG. Also in rare cases they check your server for open source code from different modules (eg. chat, speedometer etc.) and try to spam events to crash or lag the server.
To sum up, these don't appear often, but they can do some really heavy damage.

### 2.2 Casual cheaters

The classic casual cheater doesn't always have his cheats on and likes to use them only for a very short moment to enrich himself with them in a special situation. He is characterized by the fact that he only uses very few functions of his cheat and the damage is limited to a very small group of players. The casual cheater also often uses old open source cheats, which are often detected. On FiveM for example you can sort out such people very well, because you can search for loaded textures there. (FiveM cheats like to have a custom texture in their NativeUI banner, which of course is loaded into the game).
A casual cheater can also be someone who, for example, develops frustration in PvP situations due to a lack of skills, grabs the next best cheat and sets the Recoil of all weapons to 0 at first.

### 2.3 Legit cheaters

This group of cheaters is by far more widespread. These cheaters often know exactly what they are doing and also know what is detected and what is not. I would go so far as to say that some write their cheats themselves with the help of executors or injectors, in order to circumvent known patterns.
The most popular among legit cheaters is the Aimbot. Be it Silent Aimbot, Magic Bullets, or a simple Aimbot with a lot of smoothening. These players are hardly noticeable, because they are only slightly helped by the cheats in PvP compared to their skills through e.g. low FOV or high smoothening. Sometimes these people just use ESP to recognize opponents better, or to win RP situations decisively through such an advantage. Often, legit cheaters also have previous experience and are very likely to use hardware ID changers. You should keep an eye on that and if someone often changes his HardwareID, then that is already suspicious.

### 2.4 Careful cheaters

The average cautious cheater is comparable to a legit cheater, except that he uses his cheat functions even less often and even less. He doesn't want to be detected at all costs and is actually not a problem for most servers, because these people don't gain much in PvP or RP situations. Whether you want to cat these people is ultimately a cost/benefit question that everyone must answer for themselves. Often these people can only be caught by very intensive spectating, or own video recordings. Among the careful cheaters you can even count more and more streamers, because they want to be particularly good for their viewers, etc..

## 3. Type of cheats

There are many different types of cheats. Cheats may be self-developed and a player may use VMs, DMA PCIE devices, or other hardware to write directly to and read from the computer's memory. However, this type of cheat is absolutely rare and is more likely to be seen in games like Escape from Tarkov or Rust. For GTA, simpler methods are sufficient:

### 3.1 Injectors & Executors

There are several private executors a player can use. An executor simply hooks up to an alt:V JS resource and the player can modify and use it completely at will. You can use it to access the entire alt:V interface (alt-client) and all natives. Also you can use the local metas from the said resource.

Some executors also have functions that are specifically designed for alt:V. These can then among other things the following:

#### Spoofer

The cheater can make up all sorts of values and then only has to make sure that he has a different IP and possibly a new Discord account, and then he can get started.  
<img src='https://i.imgur.com/o4SvC7U.png' width=300><br>

#### Executor

You can run custom written code. The developer in this example provides a bad template, which can be detected very well. Often used to trigger certain events on the server.  
<img src='https://i.imgur.com/buhgxoE.png' width=300><br>

#### Dumper

The function can be used to dump all clientside code and resources. All vehicles and meta files are unencrypted and you can analyze them immediately without additional effort, or use them yourself.

The clientside code is readable without any encryption in the same structure as it is downloaded from the client. So all variables have plausible names and the file structure is also completely present.

If a server has taken steps against this, for example with the bytecode module, or JS obfuscation, then the whole thing is more difficult for the attacker to read. It should be noted, however, that from dumped bytecode module code you can still read all strings properly and you can also see which natives are called.  
<img src='https://i.imgur.com/xkV0cbE.png' width=300><br>

#### Event Logging

You can view all events that are exchanged between client and server and of course you can read all parameters in plain text.

For example, if you allow certain events only in one area, then this can be very exploitable under certain circumstances. For example, the cheater interacts with an object that is further away than expected.  
<img src='https://i.imgur.com/HPJoMi9.png' width=300><br>

#### Event Blocker

You can block predefined events and thus, for example, avoid a ban by a clientside cheat detection by simply blocking the event.  
<img src='https://i.imgur.com/A6z8Bi7.png' width=300><br>

#### Misc Options

You can at least connect to any server in debug mode with the executor shown here and thus possibly use developer options. You should definitely be careful what you allow in debug mode and what not!
The Anti Weapon detection can be very well counteracted by a good Anticheat.  
<img src='https://i.imgur.com/tfoXMnh.png' width=300>

#### Availability

There are not many providers for alt:V specialized executors and also few users of it, nevertheless this part of cheaters should be considered with caution as they can cause the most damage.

### 3.2 Casual cheats

Casual cheats include everything that is available on the Clear Web for a few euros per month or is open source. Depending on the quality of the cheat and the settings the user chooses, it can be a bit difficult to detect.

#### ESP

ESPs are used to find players behind walls and at long distances. Since alt:V uses GTA sync, many stats are synced and you can use the ESP to display life, armor, possibly usernames and other details.

Most ESPs use the RAGE engine functions to draw lines directly in the game and others use external drawers to be stream proof for example. You can then record your gameplay, or stream it, and you can't see the ESP as a spectator.

#### Aim Helpers

Aim helpers are the main reason why people cheat. There are as many ways to cheat as there are ways to detect them. The most commonly used is a silent aimbot. This ensures that the shots from the player's weapon are always fired in a previously calculated direction. If a player sets the FOV low, this can be very difficult to detect. The disadvantage of this variant is that it is easily visible with tracers and often just aims at a certain body part.

Then there is the classic aimbot, which uses values calculated in the cheat to move the camera so that the player aims the weapon at the opponent. The cheater can not only adjust the FOV, but also other parameters like smoothening. Smoothening ensures that the cheat only very slightly interferes with the player's camera movement.

Finally, there is a currently newer variant and that is the Magic Bullet Aimbot. This changes the course of the shots and ensures that the fired bullets don't start at the cheaters position, but only a few centimeters in front of the opponent. This way, the cheat can calculate the exact position of the bullet's arrival and it is often possible to shoot through walls.

#### Weapon Modification

This function changes live weapon metas of the weapons. For example, you can adjust the recoil, damage and range of the weapons and of course set them as desired.

#### Godmode

Most cheats have a dozen options on how you want to set your godmode. There are options that simply make the player invincible, others add the lost HP back to the player, and yet other cheats activate a light generation. Whatever cheaters use. With a good anticheat, no cheater is safe from a ban.

#### Availability

Casual cheats are extremely easy to use and often cost very little money, or are even completely free. It can be assumed that on a PvP focused server a really large part of the players use or have used such software.  
Even on Freeroam servers there are dozens of people who test out their cheats and generate their attention with explosions, etc.

## 4. Anticheat Implementations

In this part, things finally get interesting, because I'm going to present a few suggestions on how you can fight cheaters.

### 4.1 Code security

The security of your code should be your highest asset. If a cheater gets hold of some of your source code, he can really do a lot of damage. Also, it can happen that other server developers help themselves to your work and you end up being robbed of your work and time.

alt:V offers with the bytecode module a very good protection against code theft. The only problem is that you can still read all strings with a code dumper and also which natives you use in which places. With a little effort, a cheater can then, for example, easily use your synced metas for usernames, IDs and auth levels and thus set his ESP really nice.

I currently only use the obfuscation method, since the alt:V bytecode module has caused massive crashes for all my players.

So you might want to go one step further and use a bundler and obfuscation. I use for example the module [altv-esbuild](https://github.com/xxshady/altv-esbuild) from xxshady and the [JS obfuscator](https://obfuscator.io/) to protect my code. With this, strings are still readable, but they are split in places and you can make it much harder for the cheater.

The only advantage of the bytecode module over obfuscation is performance, according to most developers. It is assumed that due to the more complex code of the obfuscator the player will have less FPS and the performance will suffer. In the live test I could not confirm this thesis myself. No matter if bytecode module or obfuscation, the players had the same performance.

The esbuild module is also so handy that it really includes all the resources including the resources in the shared folder so you don't have to send it to the client. This way you can also effectively obfuscate all assets in text form, etc.

Here my build.js file I use to build my resource for production:

```js
import esbuild from "esbuild";
import { altvEsbuild } from "altv-esbuild";
import glob from "glob";
import obfuscator from "javascript-obfuscator";
import fs from "fs";

esbuild
  .build({
    entryPoints: ["resources/<your Resource>/client/startup.js"],
    outfile: "dist/bundle.js",
    bundle: true,
    plugins: [
      altvEsbuild({
        mode: "client", // use "server" for server code, and "client" for client code
      }),
    ],
  })
  .then(() => {
    glob("dist/bundle.js", {}, (err, files) => {
      const result = obfuscator.obfuscate(fs.readFileSync("dist/bundle.js", "utf8"), {
        compact: true,
        target: "node",
        controlFlowFlattening: true,
        controlFlowFlatteningThreshold: 1,
        numbersToExpressions: true,
        simplify: true,
        stringArrayShuffle: true,
        splitStrings: true,
        stringArrayThreshold: 1,
        deadCodeInjection: true, // may increase performance issues!
      });
      fs.writeFileSync("resources/code/client/startup.js", result.getObfuscatedCode(), { encoding: "utf8" });
    });
  });
```

#### How JS bytecode looks like:

<img src='https://i.imgur.com/iTM8MBX.png'>

#### How obfuscated code looks like:

<img src='https://i.imgur.com/0rhYlfU.png'>

### 4.2 Data security

#### Secure your server

I don't think I need to mention that you should secure your servers well under all circumstances. This starts with setting up a firewall that prevents attacks on the database structure, or that you can only access the SSH login of your server with a VPN, for example. If you are not well informed in this area, then try to get a rough overview by googling or using the [ChatGPT](https://chat.openai.com/chat) bot. Also every system administrator will help you with such questions.  
Also remember to make regular offshore backups of your database so that you don't suffer total data loss due to a failure. For example, there are very good free tools like [Duplicati](https://www.duplicati.com/).

#### Secure synced metas

We now know that the cheater can read the strings. But now you surely need strings to sync for example names, IDs, auth levels and so on with the players. To protect yourself from this you should use cryptic names for the synced metas or have them regenerated with every server restart. This way the cheater would have to search out the strings again with every server restart. The implementation of such a system should not bother you, because really few cheaters go so far and display the names in their ESP.

#### Secure events

Since events are sent to the server and also come from the server, they should be made unrecognizable to the cheater. You can change the event names when building the production version of the code, generate them automatically at server startup and send them encrypted to the client, and so on.

The complexity of the implementation depends on the desired security level.

#### Sanitizing & Storing passwords

Never store user passwords in the database in plain text. Ideally, you should also never send user-entered passwords to the server in clear text. It is best to use a function that creates a hash from the user's password and use it for storage and authorization.
Sanitize all values that the user can enter and save before saving them to the database. Most database modules have such a function integrated.
If you like to write your own SQL commands, [mysql2](https://www.npmjs.com/package/mysql2) is the best choice.

### 4.3 Self banning events

If you run client-side checks to see if the player is using cheats or not, then you should make sure in any case that you transfer the event to the server securely. We've learned that certain cheats can be used to block events, and that would undermine your entire anticheat.
Don't use heartbeat checks, because the cheater can simply intercept and trigger implemented checks himself.
You should also avoid using websockets without any special security, because the player can easily trick them too.

For me, the best solution was to send the ban reason as an event to the server and insert the current time. The server then checks if the incoming event is known or not and such an event can ban the cheater very easily and safely and the cheater can't prevent it.

Example:

```js
alt.emitServer(`No Bushes detected! ${Date.now()}`);
```

### 4.4 No bushes/props detection

As we know, there are players who really try to get an advantage in any situation by any means. The player. The no bush or no prop modification described here ensures that the player does not see certain bushes, trees and objects. These often have no collision and the player can even shoot through them.

This modification is not used by many cheaters, because the installation is a bit more complex and you first have to search for hours on the Internet for suitable files.

However, the detection of it is also that easy:

```js
function checkGameFiles() {
  let textureRes;
  textureRes = native.getTextureResolution("ext_veg_reeds", "nxg_prop_sl_reeds");
  if ((Math.round(textureRes.x) < 512 || textureRes.y < 256) && Math.round(textureRes.x) != 4) {
    //Run Detection Event
    return;
  }

  textureRes = native.getTextureResolution("prop_coral_2", "prop_coral_sweed_03");
  if ((Math.round(textureRes.x) < 128 || textureRes.y < 256) && Math.round(textureRes.x) != 4) {
    //Run Detection Event
    return;
  }

  textureRes = native.getTextureResolution("prop_coral_2", "prop_coral_kelp_01_lod");
  if ((Math.round(textureRes.x) < 32 || textureRes.y < 128) && Math.round(textureRes.x) != 4) {
    //Run Detection Event
    return;
  }

  textureRes = native.getTextureResolution("prop_bbq_4", "prop_bbq_4_ng");
  if ((Math.round(textureRes.x) < 256 || textureRes.y < 256) && Math.round(textureRes.x) != 4) {
    //Run Detection Event
    return;
  }

  textureRes = native.getTextureResolution("prop_trafficlight", "prop_traffic_01a");
  if ((Math.round(textureRes.x) < 128 || textureRes.y < 256) && Math.round(textureRes.x) != 4) {
    //Run Detection Event
    return;
  }

  textureRes = native.getTextureResolution("prop_trafficlight", "rsn_os_security_oldwide");
  if ((Math.round(textureRes.x) < 128 || textureRes.y < 128) && Math.round(textureRes.x) != 4) {
    //Run Detection Event
    return;
  }

  textureRes = native.getTextureResolution("prop_fnclink_04", "prop_fnclink_02_dark");
  if ((Math.round(textureRes.x) < 128 || textureRes.y < 512) && Math.round(textureRes.x) != 4) {
    //Run Detection Event
    return;
  }

  if (native.isModelInCdimage(alt.hash("prop_bin_07d")) === false) {
    //Run Detection Event
    return;
  }

  if (0.4153 - native.getModelDimensions(alt.hash("prop_bin_07d"))[2].x > 0.1) {
    //Run Detection Event
    return;
  }

  if (native.isModelInCdimage(alt.hash("prop_dumpster_01a")) === false) {
    //Run Detection Event
    return;
  }

  if (native.isModelInCdimage(alt.hash("prop_elecbox_01a")) === false) {
    //Run Detection Event
    return;
  }

  textureRes = native.getTextureResolution("prop_elecbox_01a", "prop_elecbox_01a");
  if ((Math.round(textureRes.x) < 128 || textureRes.y < 256) && Math.round(textureRes.x) != 4) {
    //Run Detection Event
    return;
  }
}
```

I downloaded a pack to remove bushes and picked out a few of the hundreds of objects and textures, which I check. The cheapest of these modifications set the texture resolution to 100x100, which is really easy to see, and others use even lower values, or delete them completely from the client. To check if the objects are present I took a few, which are important for the cheater and check them with several natives.

Note that if the texture resolution is the value 4, that means that the texture is either not loaded or not present. You should not ban a player just because the value is 4.

Also, keep in mind that you only need to do this once on the player, since they can't easily change these files during the session.

### 4.5 Code injectors

Depending on the code the cheater injected, you can easily get it. For example, you can make sure that you count the number of [event listeners](https://docs.altv.mp/js/api/alt-client.html#_altmp_altv_types_alt_client_getEventListeners) and if the player has more keydown or keyup events than expected, then you can ban him immediately without any doubt.

You should also implement a function on the server side that checks whether the player sends too many events in too short a time and then kicks or bans him depending on the intensity. Many Rage cheaters exploit open source resources and can flood the chat with as many messages per second as they have frames per second. So if the cheater has 120 fps or more, then your server is actually almost instantly offline, or all players who are affected by it go down.

Also, for all localized events, make sure you check on the server side if the player is really close enough to the event to run it.

Also be sure to note that the executor attaches to one of the clientside javascript resources. So if you have multiple resources, it may be a bit more difficult to detect, since the event listeners only apply per resource.

### 4.6 ESP

Unfortunately, there is currently little that can be done automatically against an ESP. One possibility would be to test with a few natives and position checks whether the player looks directly at others through walls. (Many cheaters with ESP are so smart and look directly at the players through walls).

Such a system is certainly a bit more complex to develop and can possibly cause many false positives.

The best way to fight ESPs is to watch conspicuous players and analyze their behavior accurately.

### 4.7 Weapon (attachments) giving

Check at certain intervals or for certain actions whether the player is allowed to carry the currently selected weapon, whether he has only mounted allowed attachments and whether the number of bullets in the magazine is correct.

These checks are really easy to implement and usually keep away rage cheaters with miniguns and rocket launchers.

### 4.8 Weapon modifications

This method of cheating is also one of the most commonly used. There are really a lot of players who change the recoil, damage or range of their weapon to get an advantage.

Thanks to the [alt:V Weapon Data API](https://docs.altv.mp/js/api/alt-client.WeaponData.html), it is really easy to detect and ban these colleagues.

The easiest way to detect even the slightest differences is to create a dump yourself and then share it with the client and have it counterchecked.

There are cheaters who do not change the values much (e.g. Recoil to 0), but try to get closer with slight changes. With a dump you can detect even the smallest deviations and ban the cheater.

#### client:

```js
const data = {};
Object.values(weaponComponents).forEach((weapon) => {
  const weaponHash = alt.hash(weapon.HashKey);
  const weaponData = alt.WeaponData.getForHash(weaponHash);
  const weaponDataObj = {
    clipSize: weaponData.clipSize,
    accuracySpread: weaponData.accuracySpread,
    animReloadRate: weaponData.animReloadRate,
    damage: weaponData.damage,
    headshotDamageModifier: weaponData.headshotDamageModifier,
    lockOnRange: weaponData.lockOnRange,
    playerDamageModifier: weaponData.playerDamageModifier,
    range: weaponData.range,
    recoilAccuracyMax: weaponData.recoilAccuracyMax,
    recoilAccuracyToAllowHeadshotPlayer: weaponData.recoilAccuracyToAllowHeadshotPlayer,
    recoilRecoveryRate: weaponData.recoilRecoveryRate,
    recoilShakeAmplitude: weaponData.recoilShakeAmplitude,
    timeBetweenShots: weaponData.timeBetweenShots,
  };
  data[weaponHash] = weaponDataObj;
});
alt.emitServer("refreshWeaponData", data);
```

#### server:

```js
alt.onClient("refreshWeaponData", refreshWeaponData);
function refreshWeaponData(player, data) {
  if (!player.valid) return;
  //if(player.data.authlevel < 1)return; MAKE SURE TO CHECK FOR PERMISSIONS!
  alt.log("saved weapon data");
  fs.writeFileSync("./resources/assets/DataDumps/weaponData.json", JSON.stringify(data));
}
```

#### client checking:

```js
function acCheckWeapon(hash = undefined) {
  const weaponHashToCheck = hash != undefined ? hash : player.currentWeapon;
  if (weaponHashToCheck == 0xa2719263) return; //do not check fist
  const currWeaponStoredData = weaponData[weaponHashToCheck];
  const currWeaponData = alt.WeaponData.getForHash(weaponHashToCheck);

  if (!currWeaponStoredData || !currWeaponData) {
    alt.log("e");
    return;
  }

  let found = [];
  if (currWeaponData.clipSize != currWeaponStoredData.clipSize && weaponHashToCheck !== 1171102963 && weaponHashToCheck !== 911657153) found.push("clipSize" + `(${weaponHashToCheck})` + `(${currWeaponData.clipSize})`);
  if (currWeaponData.accuracySpread != currWeaponStoredData.accuracySpread) found.push("accuracySpread" + `(${weaponHashToCheck})` + `(${currWeaponData.accuracySpread})`);
  if (currWeaponData.animReloadRate != currWeaponStoredData.animReloadRate) found.push("animReloadRate" + `(${weaponHashToCheck})` + `(${currWeaponData.animReloadRate})`);
  if (currWeaponData.damage != currWeaponStoredData.damage) found.push("damage" + `(${weaponHashToCheck})` + `(${currWeaponData.damage})`);
  if (currWeaponData.headshotDamageModifier != currWeaponStoredData.headshotDamageModifier) found.push("headshotDamageModifier" + `(${weaponHashToCheck})` + `(${currWeaponData.headshotDamageModifier})`);
  if (currWeaponData.playerDamageModifier != currWeaponStoredData.playerDamageModifier) found.push("playerDamageModifier" + `(${weaponHashToCheck})` + `(${currWeaponData.playerDamageModifier})`);
  if (currWeaponData.range != currWeaponStoredData.range) found.push("range" + `(${weaponHashToCheck})` + `(${currWeaponData.range})`);
  if (currWeaponData.recoilAccuracyMax != currWeaponStoredData.recoilAccuracyMax) found.push("recoilAccuracyMax" + `(${weaponHashToCheck})` + `(${currWeaponData.recoilAccuracyMax})`);
  if (currWeaponData.recoilAccuracyToAllowHeadshotPlayer != currWeaponStoredData.recoilAccuracyToAllowHeadshotPlayer) found.push("recoilAccuracyToAllowHeadshotPlayer" + `(${weaponHashToCheck})` + `(${currWeaponData.recoilAccuracyToAllowHeadshotPlayer})`);
  if (currWeaponData.recoilRecoveryRate != currWeaponStoredData.recoilRecoveryRate) found.push("recoilRecoveryRate" + `(${weaponHashToCheck})` + `(${currWeaponData.recoilRecoveryRate})`);
  if (currWeaponData.recoilShakeAmplitude != currWeaponStoredData.recoilShakeAmplitude) found.push("recoilShakeAmplitude" + `(${weaponHashToCheck})` + `(${currWeaponData.recoilShakeAmplitude})`);
  if (currWeaponData.timeBetweenShots != currWeaponStoredData.timeBetweenShots) found.push("timeBetweenShots" + `(${weaponHashToCheck})` + `(${currWeaponData.timeBetweenShots})`);

  if (found.length != 0) {
    alt.emitServer(JSON.stringify(found) + new Date());
  }
}
```

You can grab the weapon component data from: https://gist.github.com/root-cause/3f29d38179b12245a003fb4fff615335

### 4.9 Classic aimbot

The classic Aimbot is used to target enemy players using camera arotaion, or targeted mouse inputs. I present here a method that works really well against it.

#### client:

```js
let preventSusReport = false;
let preventSusReportTimeout;

alt.on("playerWeaponShoot", (weaponHash, totalAmmo, ammoInClip) => {
  if (preventSusReport) {
    if (!preventSusReportTimeout) {
      preventSusReportTimeout = setTimeout(() => {
        preventSusReport = false;
        preventSusReportTimeout = undefined;
      }, 1000);
    }
  } else {
    //gather all needed variables for calculation
    const cameraRotation = native.getGameplayCamRot(2);
    const currentMousePos = alt.getCursorPos(false);
    const screenResolution = alt.getScreenResolution();

    //check if the players mouse is not near any borders of the screen > could lead to a lot false positives
    const xDist = screenResolution.x - currentMousePos.x;
    const xDistCheck = xDist > screenResolution.x.toFixed(0) * 0.95 || xDist < screenResolution.x.toFixed(0) * 0.05;

    if (!xDistCheck) {
      if (lastKnownMousePos.x == currentMousePos.x) {
        // if mouse position since last shot didnt changed
        /* the screenResolution.x*0.0005 is absolutely important,
                because the mouse position is only in integer values and when moving the mouse it could lead to different coordinates of the gameplay camera,
                but the mouse position is still the same. This is espacially important for really low screen resolutions!
                */
        if (Math.abs(cameraRotation.z - lastKnownCameraRot) > screenResolution.x * 0.0005) {
          // Detection handle
        }
      }
    }

    lastKnownMousePos = alt.getCursorPos(false);
    lastKnownCameraRot = cameraRotation.z.toFixed(3);
  }
});

alt.everyTick(() => {
  //prevent aimbot detection, when turning the camera by pressing C or right click
  if (native.isControlPressed(0, 26) || native.isControlJustPressed(0, 25)) {
    preventSusReport = true;
    if (preventSusReportTimeout) {
      alt.clearTimeout(preventSusReportTimeout);
      preventSusReportTimeout = undefined;
    }
  }
});
```

With the method shown above, you can detect players with aimbots really easily, even if they set the smoothening very high. The cheater just has to make the mistake of not moving his mouse while the aimbot is moving the camera :)

Just pay attention with the c and right click pressing while holding weapons, cheaters who got lost and have read this guide can keep pressing c or right mouse to prevent flagging.

Against Aimbots you can also check on the server side if the player is cheating or not. For example, you can calculate whether the player is targeting a bone particularly often in a row. Often people set their cheats to headshot only and if someone has hit the head more than, say, 40 times in a row, that's a bit sus.

A really good method is also to check the offsets and if the player hits close to a low value multiple times. The following example throws a false positive, but it is a better way to confirm acute suspicions.

(But if players hit the offsets 0, 0, 0 several times, you can ban them immediately for Magic Bullet cheat).

#### server:

```js
alt.on("weaponDamage", (player, target, weaponHash, damage, offset, bodyPart) => {
  if (!player.valid || !target.valid) return;
  if (bodyPart != undefined) anticheatCheckAimbot(player, bodyPart);

  if ((Math.abs(offset.x) < 0.015 || Math.abs(offset.y) < 0.015 || Math.abs(offset.z) < 0.015) && player.lastPos.distanceTo(player.pos) > 0.001 && target.lastPos.distanceTo(target.pos) > 0.001) {
    player.offsetFlags++;
    if (player.offsetFlags % 5 === 0) {
      // handle logging/ detection
    }
  } else {
    player.offsetFlags = 0;
  }
  // do not forget to set the lastPos once upon connection complete to not break this function
  // Or however I suggest to refactor this :D It's just a proof of concept
  player.lastPos = player.pos;
  target.lastPos = target.pos;
});
```

#### server:

```js
function anticheatCheckAimbot(player, bone) {
  if (!player.valid) return;
  let currentData = player.getMeta("acAimbotCheck") ?? [bone, 0];
  if (currentData[0] === bone) {
    currentData[1]++;
  } else {
    currentData[0] = bone;
    currentData[1] = 0;
  }
  if (currentData[1] == 20) {
    // handle logging
    currentData[1] = 0;
  }
  player.setMeta("acAimbotCheck", currentData);
}
```

### 4.10 Silent aimbot & magic bullets

Silent aimbots and magic bullets are the hot shit among cheats and can hardly be detected like ESP.

Latest magic bullet cheats (or the leaks of the function for it) can be detected well, as players influence the bullet's trajectory and they spawn right in front of the enemy player. Thus, the offset in weaponDamage is well and truly 0, 0, 0 on the server side.

However, I have also developed a method for this, which can also filter out such cheaters:  
(Silent, Magic Bullet & trigger bots)

#### client:

```js
alt.on("playerWeaponShoot", (weaponHash, totalAmmo, ammoInClip) => {
  // if player is shooting a bullet, while he is not allowed to do so, then yea...
  if (player.hasMeta("TRIGGERBOT_CHALLENGE")) {
    // logging or instant ban handle here
  }

  /*  
    I implemented a little pre-check before running this, because triggerbot detection
    can be very annoying for non-cheaters
    and it also only checks if there are enough bullets in the magazine to make sure that the player 
    actually shoots in that time frame he is beeing checked.
    */
  if (alt.getLocalMeta("PlayerActedWeird") && ammoInClip > 10) {
    if (getRandomInt(0, 1000) <= 3) {
      runSilentCheck();
    }
  }
});

function runSilentCheck() {
  /*
    To explain this: The most magic bullet or silent cheats are using the function setPedShootsAtCoord
    This is used to shoot a bullet, but however this ignores the disablePlayerFiring flag.
    So if a player shoots a bullet, while he is not allowed to do so, it's 100% silent or magic bullet cheat.
    However this can be really annoying for normal players, but this detection gives you the best chance to catch them all.
    */
  const ticky = alt.everyTick(() => {
    native.disablePlayerFiring(0, true);
  });

  player.setMeta("TRIGGERBOT_CHALLENGE", true);

  setTimeout(() => {
    alt.emitServer("playerRanTriggeraimbot");
    player.deleteMeta("TRIGGERBOT_CHALLENGE");
    alt.clearEveryTick(ticky);
  }, 1000); // you can lower this value to 200ms, but one second works the best for revolvers, pistols etc.
}

// just a little helper
function getRandomInt(min, max) {
  min = Math.ceil(min);
  max = Math.floor(max);
  return Math.floor(Math.random() * (max - min + 1)) + min;
}
```

### 4.11 Healing

Healing cheats are used less by players on alt:V, because they are warned in the cheat tools and know what to expect when using it.

An implementation of such checks is very simple and you can simply check in an interval x, or after each shot, whether the player has more HP than he should have.

Here an implementation to check if someone has godmode active, or is healing himself automatically:
Run the function if the player is suspicous, or in a random interval. It is up to you.

```js
let isChecking = false;
let healhackviolation = 0;

if (player.health > 110 && !isChecking  /* Maybe exclude some edge cases like using medkits etc. in here*/) {
    isChecking = true;
    const oldHealth = player.health;
    native.setEntityHealth(player, player.health - 1, 0); // take 1hp and check if the player regains it. If so, ban him :)
    alt.setTimeout(() => {
        alt.setTimeout(() => {
            isChecking = false;
        }, 500);
        if (/* Maybe include some case to reset the counter */) {
            healhackviolation = 0; //reset when left gamemode while test
            return;
        }
        if (player.health >= oldHealth) {
            healhackviolation++;
        }
        else {
            healhackviolation = 0;
            if (player.health < 200 && player.health > 100) { // not dead and not fullhp
                native.setEntityHealth(player, player.health + 1, 0); //give back the 1 hp we stole the player
            }
        }
        if (healhackviolation == 3) {
            // Send Au Revoir
            return;
        }
    }, 100);
}
```

### 4.12 Ammunition

Just check after each shot if the player has more rounds in the magazine than he should have.

Be sure to take into account all eventualities in which the weapon magazine is refilled by intercation.

- Reloading
- Weapon switch
- Climbing onto objects

### 4.13 Pressed keys

My absolute favorite. You only have to log somewhere which special keys the player presses and you can justify suspicions very well.

Here is an example to detect this:

```js
let pressedSusKeys;
alt.on("keyup", (key) => {
  /* if (player.hasAnyMenuOpen()) return; -> Depends on the server menu.
  If you have something with NativeUI or arrow keys navigation 
  exclude detection while the menu is open.
*/
  let keyCode = "";
  switch (key) {
    case 0x2e:
      keyCode = "DEL";
      break;

    case 0x2d:
      keyCode = "INS";
      break;

    case 0x23:
      keyCode = "END";
      break;
    case 0x91:
      keyCode = "ROLL";
      break;

    /* 
I suggest to disable arrow left, because some custom keyboards
like mine are pressing the left key button randomly and this is just spamming the logs
        case 0x25:
            keyCode = 'ARROW LEFT';
            break;
*/
    case 0x26:
      keyCode = "ARROW UP";
      break;

    case 0x27:
      keyCode = "ARROW RIGHT";
      break;
    case 0x28:
      keyCode = "ARROW DOWN";
      break;
    case 0x24:
      keyCode = "HOME";
      break;
    default:
      return;
  }

  // Use this object to store multiple interactions and send them bundled to prevent logging overload.
  if (!pressedSusKeys) pressedSusKeys = {};
  if (!pressedSusKeys[keyCode]) pressedSusKeys[keyCode] = 1;
  pressedSusKeys[keyCode]++;
});

alt.setInterval(() => {
  if (pressedSusKeys) {
    // handle sending content to server.
    pressedSusKeys = undefined;
  }
}, 60000);
```

### 4.14 Explosives

Rage cheaters like to use various functions to cause a lot of damage with explosions.

Depending on the game mode, you can return explosions in the weaponDamage with false and thus block the whole thing, or you track how many explosions a player causes in a period of time.

There are also cheats that teleport to the driver's seat of all vehicles in the area and then explode them.

The most common explosion hash is the following:

```js
weaponHash == 539292904;
```

### 4.15 Teleporting

Teleport cheats are often used by Rage hackers or players in PvP modes, who port to another location shortly before death.

When detecting, it is important to take into account that the player may have lags, fall under the map or simply have a really bad computer.

Here is a small implementation approach:

#### client

```js
const player = alt.Player.local;
let latestPosition = player.pos;

alt.everyTick(() => {
  if (player.pos.distanceTo(latestPosition) > 100 /*&& player.health > 100*/) {
    // somehow pause this detection when a player is about to teleport, because its requested by the gamemode or server.
    // Also people with really bad fps may ban themselves. The best option is to track the performance and in PvP modes consider kicking players with really bad fps
    if (player.getMeta("PREVENTTPDETECTION") || alt.getFps() < 20) {
      latestPosition = player.pos;
      return;
    }
    //handle teleport detection
    alt.emitServer("CheatingIsBad", `Teleport/Speedhack ${latestPosition} -> ${player.pos} in one frame ${player.pos.distanceTo(latestPosition)}m traveled!`, 0);
    latestPosition = player.pos;
  } else {
    latestPosition = player.pos;
  }
});
```
### 4.16 Noclip
Noclip is also a function that is often only used by Rage cheaters and you can detect them relatively well. Here is an example:

```js
const player = alt.Player.local;
let noclipviolation = 0

// exlude vehicles with caution! Some cheats know that noclipping in vehicles is safe!
if (!native.isPedRagdoll(player) && !player.vehicle && !native.isPedClimbing(player)) {
            // we try to get the actual ground position of the player. Sometimes the function fails due to roof etc.
            // may lead to issues in interiors or parking garages, make sure to test all possible locations and before only carefully execute automated bans
            let [_, height] = native.getGroundZFor3dCoord(player.pos.x, player.pos.y, player.pos.z, undefined, undefined);
            if (height == 0) [_, height] = native.getGroundZFor3dCoord(player.pos.x, player.pos.y, player.pos.z + 2, undefined, undefined);
            if (height == 0) [_, height] = native.getGroundZFor3dCoord(player.pos.x, player.pos.y, player.pos.z + 50, undefined, undefined);
            // If the game found no ground height the result is simply 0
            if (height != 0) {
                const heightdiff = player.pos.z - height;
                if (heightdiff < -3 || heightdiff > 10) {
                    // check if the player is swimming or at least over water and ignore it
                    const [waterprobe, ___] = native.testVerticalProbeAgainstAllWater(player.pos.x, player.pos.y, player.pos.z, 0, 30);
                    if(!waterprobe){ //if not over water and height difference above ground is too bad
                        noclipviolation++;
                    }
                } else {
                    noclipviolation = 0;
                }
                if (noclipviolation == 5) {
                    // Send Noclip detection to server
                    // Sending the detection after the first violation may lead to false positives, so we use 5 violations in a row
                }
            }
        }
```

## 5. Multiaccount detection

Depending on the effort, multiaccounts can be detected very quickly. If you run a RP server with forum, then you can filter out almost all players with a plugin for the Woltlab Suite, because they have to reset their browser agent and also other attributes are checked.

But if you don't have a forum, it's a bit more complicated. In the first place, you can actually throw all of alt:V's or GTA's built-in checks in the garbage can. A cheater can spoof all these values with one click, or just fix the necessary adjustments.

#### hwidHash & hwidExHash

hwidHash and hwidExHash should also be viewed with absolute caution, as these values tend to change with a new installation of Windows, or a BIOS update.

ASRock motherboards with a certain type and an old BIOS version also have the bug that all players have the same hardware ID.

If you want to consider these values for identification, then you should form a hash from both and consider this combined. Individually, it can really lead to many difficulties.

#### socialID

It is recommended to block all players with the value set to 0, because they either use bad cheats, or try to connect in offline mode.
(Possibly allow temporarily after a GTA update, otherwise hardly anyone can join the server). You should also keep in mind, that every players SocialID can be 0 if Rockstars servers are offline or not working correctly.

If the socialclub id is 488923086, then the player is using a version of a launcher that is very widespread in Eastern Europe, with which GTA can be played without a purchased license. I recommend to inform players with this ID to buy the game and also to kick/ban them from the server.

#### discordID

The discordID has one major purpose which makes it handy to use. It allows servers to dynamically create whitelists, which are connected to discord roles. The server can check if the user with discordId `123` has the role `abc`. Using only discordID allows cheaters to gain access using a spoofer to change their discordID to a whitelisted one so you should also consider using different methods at the same time. [We suggest using OAuth2](#so-if-all-is-bad-what-can-i-actually-use)

#### ip

By IP, I would only ban players if the account that matches that IP is also banned.
Because at least in Germany many providers use Dual Stack Lite and it happens more often that players have the same public IP address. Also, IPs are reassigned after x hours and with a little luck you get that of another player.

Furthermore, it can be that in a household several people play on the server and you would first have to whitelist all accounts in the household, so that they are no longer flagged.

### So if all is bad, what can I actually use?

You should have the player log in with a Discord login and work with the player's token. No spoofer can influence these values and the player would have to create a new Discord account with every ban, which increases the hurdle significantly.

You should also best check the IP, HardwareID etc on other accounts when the player logs in and if the other accounts are banned with matching data. If you ban the player at every overlap, then you first need a larger team, which takes care of the support tickets :D

Use the [OAuth2 implementation from alt:V](https://docs.altv.mp/articles/discord_oauth.html) and please add a [fallback for Linux users](https://github.com/Stuyk/altv-discord-auth)

## 6. Things you should consider

Always keep in mind that the race between cheaters and anticheat never ends and you as a server developer should regularly check your anticheat for updates and update it if necessary.
Here are a few more ideas that come to my mind

### 6.1 Specator mode

Develop a Spectator Mode that allows you to look from the cheater's point of view and closely observe his movements. You can use the native attachToEntity etc. for this.

### 6.2 Force debug mode

The executor shown at the beginning of the guide allows cheaters with debug mode to connect to servers that do not allow it, and the player could get access to developer options, or hidden menus. Make sure that such accesses are secured on the server side, or are not even on the live server.
Also, the player could produce sync errors and duplicate items or money. Pay attention to how fast the player reconnects after a disconnect.

### 6.3 Bullet tracers

The new alt:V JS hook weaponShoot allows you to draw tracers of the bullets fired without silent or magic aimbot and you can better detect possible cheaters while spectating.

### 6.4 Hiding while spectator mode

Never just set your player invisible while spectating, but move it to a negative dimension, or set the streamed parameter to false!
Cheaters can see players who are invisible with their ESP and aimbots ignore any players who are invisible or in godmode.

### 6.5 Vehicle cheats

Vehicle cheats are unfortunately a little too short here in the guide, but you can certainly use vehicle handling similar to the weapon metas in the first place to see whether the player has modified them and also check whether, for example, the acceleration or maximum speed is too high.

# Happy hunting! :heart:

If you have any question feel free to write me on Discord Kaniggel#6969
And if you like to contribute to this guide, feel free to help me adding more content!
