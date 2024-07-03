# OpenAirInterface_Notes
My notes from working with the OpenAirInterface

# setup of gNB
navigate to location of openairinterface5g
```cd openairinterface5g/cmake_targes```

navigate to build 
```cd openairinterface5g/cmake_targes/ran_build/build```

Build the OAI in the 
```
sudo ./nr-softmodem -O ~/gnb.conf --sa -E --rfsim --log_cofig.global_log_options level,nocolor,time
```
where:
~/gnb.conf is the location of the configuration file 

-- sa is stand alone 

-E ? 

--log_cofig.global_log_options level,nocolor,time What we want to log

-- rfsim The RFsimulator is an OAI device replacing the radio heads (for example the
USRP device). It allows connecting the oai UE (LTE or 5G) and respectively the
oai eNodeB or gNodeB through a network interface carrying the time-domain
samples, getting rid of over the air unpredictable perturbations. This is the
ideal tool to check signal processing algorithms and protocol implementation.
The RFsimulator has some preliminary support for channel modeling.

# Docker
Primaryly this tutorial: https://gitlab.eurecom.fr/oai/openairinterface5g/-/blob/develop/ci-scripts/yaml_files/5g_rfsimulator/README.md
How to set up the docker 
navigate to loaction of openairinterface5g 
```cd openairinterface5g/ci-scripts/yaml_files/5g_rfsimulator```

build docker containers
```docker-compose up -d mysql oai-amf oai-smf oai-upf oai-ext-dn```

check if they are build 
```docker-compose ps -a```

build docker container for gNB
```docker-compose up -d oai-gNB```

build docker container for UE
```docker-compose up -d oai-nr-ue```





