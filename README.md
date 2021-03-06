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
# took about an hour
# docker pull stevetsa/metagenomicantibioticresistance:latest  #update Docker image
docker run -v `pwd`:`pwd` -w `pwd` -i -t stevetsa/metagenomicantibioticresistance:latest
mkdir test
## id.txt (ERR1600439) in the test folder
sh /MetagenomicAntibioticResistance/nastybugs.sh id.txt ./hgDir ./cardgene ./cardsnp 16 ./outDir

magicblast -num_threads 16 -infmt fastq -query ../ERR1600439_1.fastq  -query_mate ../ERR1600439_2.fastq -out ERR1600439.CARD_gene.out.tab -db cardgene/cardgenedb -outfmt tabular 

magicblast -num_threads 16 -infmt fasta -query test.blast.in -out test.blast.out.tab -db MetagenomicAntibioticResistance/cardgene/cardgenedb -outfmt tabular 

/home/mylagimail2004/test/MetagenomicAntibioticResistance/cardgene# grep ">" nucleotide_fasta_protein_homolog_model.fasta > nucleotide_fasta_protein_homolog_model.fasta.header ##2239 lines

### Dokcer remove exited containers
docker rm $(docker ps -a -f status=exited -q)
### Docker remove images with no tag
docker rmi $(docker images -a -q)

/home/mylagimail2004/test/MetagenomicAntibioticResistance/cardgene# makeblastdb -in nucleotide_fasta_protein_homolog_model.fasta -parse_seqids -dbtype nucl -out cardgene2db


### Jupyter
 ssh -L 8888:0.0.0.0:8888 mylagimail2004@35.237.136.251
  159  sudo apt-get install python3-pip
  162  python3 -m pip install --upgrade pip
  163  sudo python3 -m pip install --upgrade pip
  164  sudo python3 -m pip install jupyter
  
  168  jupyter notebook --generate-config
  170  more /home/mylagimail2004/.jupyter/jupyter_notebook_config.py
  171  pico /home/mylagimail2004/.jupyter/jupyter_notebook_config.py
  172  jupyter-notebook --no-browser --port=8888
  
  pip3 install not working
  conda install -c bioconda snakemake 

mkdir -p work
chmod 777 work
  docker run -it --rm -v `pwd`:`pwd` -w `pwd` -p 8888:8888 temp
 

mylagimail2004@superbugs:~/docker/work$ sh MetagenomicAntibioticResistance/nastybugs.sh id.txt ./hgDir ./cardgene ./cardsnp 16 ./outDir
mylagimail2004@superbugs:~/docker/work$ docker run -it --rm -v `pwd`:`pwd` -w `pwd` stevetsa/nastybugs2 /bin/bash

bash MetagenomicAntibioticResistance/nastybugs.sh id.txt  ./hgDir ./cardgene ./cardsnp 16 ./outDir > log &



docker run -it --rm -v `pwd`:`pwd` -w `pwd` stevetsa/temp3 /bin/bash
bash nastybugs3.sh id.txt ./hgDir2 ./cardgene2 ./cardsnp2 16 ./outDir2 ./inDir &

```

docker run --name kallisto_container -it -d stevetsa/kallisto /bin/bash
docker exec -it kallisto_container kallisto index -i cDNAindex 2018-ACMBCB-workshop/transcripts.fasta.gz



