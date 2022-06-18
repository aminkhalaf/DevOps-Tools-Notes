## Create a new environment variable
export PROJECT=MERCURY

and add the value to the (.profile) by running (echo 'export PROJECT=MERCURY' >> /home/bob/.profile)

## Set an alias called up for the command uptime

alias up=uptime
echo 'alias up=uptime' >> ~username/.profile

## Update Bob's prompt so that it displays the date

PS1='[\d]\u@\h:\w$'
echo 'PS1="[\d]\u@\h:\w$"' >> ~/.profile