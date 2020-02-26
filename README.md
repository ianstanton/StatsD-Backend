# AppD-StatsD-Backend
StatsD Backend to push metrics to AppDynamics

# Clone this repository
git clone https://github.com/APPDRYDER/AppD-StatsD-Backend.git

# Clone statsd
git clone https://github.com/statsd/statsd.git

# Download AppDynamics Machine Agent

Download machineagent-bundle-64bit-linux-4.5.18.2430.zip in the directory Agents

From https://download.appdynamics.com/

# Configure AppDynamics Controller Environment Variables
Edit envvars.controller1.sh to align to an AppDynamcis Controller and Account

# Build the container
. envvars.sh

./docker-ctl.sh build

# Run the container
./docker-ctl run

This will start the Machine Agent, the StatsD daemon with the AppDynamics Backend, and the sample metrics load generator test1.py
Sample metrics will be pushed to statsd using test1.py. The AppDynamics Backend will push the metrics to the Machine Agent

# Bash into the container
./docker-ctl bash

# Review logs in logs dir
tail -f logs/statsd.log

# Stop the container
exit

./docker-ctl stop


