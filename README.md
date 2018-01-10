# Profit-Trailer
Trading Bot Config Files for Different Strategies

## To make life easier on your Linux VPS

1. Untar the following file: `tar xvfz pt_scripts.tar.gz`
2. Put the file `pt` in: `/etc/init.d`
3. Put the following files: `pt-log.sh  pt-start.sh  pt-status.sh  pt-stop.sh` in `/usr/bin`
4. Type `cd` and hit return
5. Put the following line at the bottom of your `~/.bashrc` file: `PATH=$PATH:/etc/init.d`
6. Now type `source ~/.bashrc` and hit return
7. Now to start pt, you just type: `pt start`
8. To stop pt, you type: `pt stop`
9. To restart pt, you type: `pt restart`
10. To see the status of pt, you type: `pt status`
11. To watch the log stream, you type: `pt log`
12. You'll have to change a little bit in the `/usr/bin/pt-start.sh` file:
```
cd /home/bbills/ProfitTrailer
nohup java -jar ProfitTrailer.jar -XX:+UseConcMarkSweepGC -Xmx256m -Xms256m >> ProfitTrailer.out 2>&1&
```
## Note:	
- pt wouldn't start from my home dir without changing directory into where the `ProfitTrailer.jar` file is.
- It seems that the jar file doesn't see it's dependencies if you call it with a path.
- You could always just put the ProfitTrailer folder under `/usr/bin` if you wanted to.
- But you'll have to change that path to where you have pt installed.
