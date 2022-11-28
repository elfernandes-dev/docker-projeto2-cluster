# Docker Swarm: Definição de um cluster com o Vagrant


## _Projeto original: DIO -> Denilson Bonatti_

1 - O Vagrantfile tem como objetivo o provisionamento de 2 máquinas virtuais (VMs). Sendo uma máquina com o nome de master e a outra com o nome de node01 (Mais máquinas "nodeXX" podem ser incluídas no vagrantfile);

2 - Cada VM terá um ip fixo;

3 - O Docker será pré-instalado em cada VM;

4 - A máquina com o nome de master será o nó manager do cluster.

5 - As demais máquinas serão incluídas no cluster swarm como workers.