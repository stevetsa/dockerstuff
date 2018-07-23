# dockerstuff

Welcome to Ubuntu 14.04.5 LTS (GNU/Linux 4.4.0-130-generic x86_64) on GCP
```{}
sudo apt-get install docker.io
sudo groupadd docker
sudo usermod -aG docker $USER
```

```
# docker pull stevetsa/metagenomicantibioticresistance:latest  #update Docker image
docker run -v `pwd`:`pwd` -w `pwd` -i -t stevetsa/metagenomicantibioticresistance:latest
sh /MetagenomicAntibioticResistance/nastybugs.sh id.txt ./hgDir ./cardgene ./cardsnp 16 ./outDir
```
