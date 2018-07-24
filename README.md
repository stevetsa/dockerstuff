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
```
