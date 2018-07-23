# dockerstuff

Welcome to Ubuntu 14.04.5 LTS (GNU/Linux 4.4.0-130-generic x86_64) on GCP

Login with email "username" not GitHub

```{}
sudo apt-get install docker.io
sudo groupadd docker
sudo usermod -aG docker $USER
sudo service docker restart
```

```
# docker pull stevetsa/metagenomicantibioticresistance:latest  #update Docker image
docker run -v `pwd`:`pwd` -w `pwd` -i -t stevetsa/metagenomicantibioticresistance:latest
mkdir test
## id.txt (ERR1600439) in the test folder
sh /MetagenomicAntibioticResistance/nastybugs.sh id.txt ./hgDir ./cardgene ./cardsnp 16 ./outDir
```
