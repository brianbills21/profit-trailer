# Profit-Trailer
Trading Bot Config Files for Different Strategies

- Untar the following file:
`tar xvfz pt_scripts.tar.gz`

Put the file pt in /etc/init.d
Put the files pt-log.sh  pt-start.sh  pt-status.sh  pt-stop.sh in /usr/bin
Type cd and hit return
Put the following line at the bottom of your .bashrc file
PATH=$PATH:/etc/init.d
Now type source .bashrc


Now to start pt, you just type pt start
To stop pt, you type pt stop
To restart pt, you type pt restart
To see the status of pt, you type pt status
To watch the log stream, you type pt log

You'll have to change a little bit in the /usr/bin/pt-start.sh file:

cd /home/bbills/ProfitTrailer
nohup java -jar ProfitTrailer.jar -XX:+UseConcMarkSweepGC -Xmx256m -Xms256m >> ProfitTrailer.out 2>&1&
		
pt wouldn't start from my home dir without changing directory into where the ProfitTrailer.jar file is.
It seems that the jar file doesn't see it's dependencies if you call it with a path.
You could always just put the ProfitTraler folder under /usr/bin if you wanted to.
But you'll have to change that path to where you have pt installed.
