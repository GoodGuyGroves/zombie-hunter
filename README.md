## Zombie Hunter


### Description

The `zombiehunter` script searches the process list for all processes that are zombies. It then finds the parent PID's of all the zombie processes and prints the list of zombies and parents to stdout. The `doublebarrel` script takes the output of `zombiehunter` as it's input, parses it and double taps each zombie parent in the head. If you wish to test the script on a system that has no zombie processes, simply make use of `necromancer` or `necromancer.c` which will spawn one zombie process that will last 10 minutes each time you run it.


### Usage

* Download `necromancer` or `necromancer.c`
    * If you downloaded `necromancer.c` execute `cc necromancer.c -o necromancer` to compile it
* Download `zombiehunter` and `doublebarrel`
* Run: `sudo chmod +x zombiehunter && sudo chmod +x doublebarrel`
* Run: `./necromancer &` once per each zombie process you wish to spawn
* Run: `./zombiehunter` to get a list of zombie processes and their parent process PID's
* Run: `./zombiehunter | ./doublebarrel` to pipe the output of the `zombiehunter` script into `doublebarrel` so it can parse the output and kill the parent processes of all zombies.
