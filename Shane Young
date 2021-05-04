const readlineSync = require('readline-sync');

const name = readlineSync.question('Enter your name! ');

readlineSync.question('Hello ' + name +', welcome to Zombie Land! Where you will have to deaf the evil zombies to stay alive. Press Enter to start');

const killerZombies = ['Flesh', 'Ghoul', 'Crawler', 'Karen',  'Sal'];
const treasure = ['Medic Pack', 'Gemstones', 'Body Armor', 'Speed Boost'];
var prize = [];
let userHealth = 30;
const options = ['Walk', 'Exit', 'Print'];
let pickUp = treasure[Math.floor(Math.random()*treasure.length)];

function warZone(){
    const attackPower = Math.floor(Math.random() * (5 - 2 + 4) + 6);
    const killerZombie = killerZombies[Math.floor(Math.random() * killerZombies.length)];
    let killerZombiesHealth = 30;
    const killerZombiesPower = Math.floor(Math.random() * (4 - 3 + 5) + 5);

    const index = readlineSync.keyInSelect(options, 'What would you like do to next?');

    if (options[index] == 'Exit') {
        return userHealth = 0;
    } else if (options[index] == 'Print'){
        console.log(name + ': \n' + userHealth + '\nTreasure: ' + pickUp);
    } else if (options[index] === 'Walk'){
        let key = Math.random();
        if (key <= .3) {
            console.log('Walking....');
        } else if (key >= .3) {
            console.log(killerZombie + ' has arrived');
        
            while(killerZombiesHealth > 0 && userHealth > 0) {

                const user = readlineSync.question('Please select an option! enter "r" to run or "a" to attack: ');

                switch (user){
                    case 'r': //runaway
                        const run = Math.random();
                        if(run < .5) {
                            console.log('Before you can run away ' + killerZombie + ' attacks you with: ' + killerZombiesPower);
                        }else {
                            console.log('You got away! That was a close one!!');
                            break;
                        }

                    case 'a': 
                        // attack the zombie
                        killerZombiesHealth -= attackPower;
                        console.log('You attacked ' + killerZombie + ' with '  + attackPower + ' attack power ');

                        userHealth -= killerZombiesPower;
                        console.log('Zombie just attacked you with: ' + killerZombiesPower + ' attack power');

                        if (killerZombiesHealth <= 0){
                            console.log('You have defeated ' + killerZombie + '.\n' + killerZombie + ' left: ' + pickUp);
                            let loot = Math.random();
                            if (loot <= .3){
                                prize.push(pickUp);
                            }
                            } else if(userHealth <= 0){
                                console.log(killerZombie + ' has killed you. GAME OVER!!');
                            }       
                    }
                }
            }
        }  
}            

while(userHealth > 0){
    userRestore = function(){
        userActive = true;
        userHealth = 60;
    };
    userRestore();
    warZone();
}
