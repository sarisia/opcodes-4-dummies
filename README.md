# opcodes-4-dummies

how to find opcodes 4 dummies
by beng

# INSTRUCTIONS

inside you should see two folders named "bin" and "node_modules". the placement of the modules inside is important.
open up the "bin" folder and you should see a "node_modules" folder inside. open up that folder and you should see two folders named "alex-logger" and "alex-packet-id-finder".
both "alex-logger" and "alex-packet-id-finder" go into your tera-proxy / bin / node_modules folder, where you put all of your other modules.

go back to where you see the "README" file and open the "node_modules" folder. you should see a folder called "hexy". this is a dependency (you need it for "alex-logger" and "alex-packet-id-finder" to work).
put this folder into your tera-proxy / node_modules folder **NOT YOUR BIN / NODE_MODULES FOLDER**. it should be placed in the same folder as where you find the "tera-data" folder.

once you have installed both modules and the dependency, you are ready to begin find opcodes.

# COMMANDS FOR LOGGING

there are only three commands you need to be concerned with for logging packets.

"logc": this is a command for "alex-logger". it logs all client -> server packets (or packets starting with C_). type "logc" again to turn it off.

"logs": this is the other command for "alex-logger". it logs all server -> client packets (or packets starting with S_). type "logs" again to turn it off.

commands used for "alex-logger" will display the opcode for the packet enclosed in parentheses. it will always look like (id xxxxx).

"fpi PACKET_NAME": this is the command for "alex-packet-id-finder". after enabling this command, you have to find some way to proc the packet you are trying to log.

for example, if you are trying to log "C_PLAYER_LOCATION", you'd type "fpi C_PLAYER_LOCATION". to proc the packet, you would have to move around.

### IMPORTANT
it has come to our attention that "alex-packet-id-finder" may not be reliable or may not be working correctly (i.e, not logging packets when it should).

# AFTER YOU HAVE FOUND THE OPCODE

after you have found the opcode you are looking for, you need to go to tera-proxy / node_modules / tera_data / "map" folder. this is the folder where all your opcodes are found.
open up your respective protocol.xxxxx.map folder that corresponds to your region. the list is as follows:

protocol.324670.map = NA

protocol.324671.map = EU

protocol.324672.map = RU

protocol.324674.map = JP

protocol.323464.map = KR-PTR

protocol.323767.map = KR

protocol.323311.map = TW

once you have opened up your respective region's opcode map, insert the PACKET_NAME anywhere (doesn't have to be in alphabetical order) and then put the opcode after it.
for example,

C_LEGITIMATE_PACKET_NAME = 42069

then, save the file and restart your proxy /game.

afterwards, your modules should be good to go!
