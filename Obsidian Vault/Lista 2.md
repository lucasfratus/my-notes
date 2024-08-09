1. Descreva a hierarquia de memórias em um sistema computacional.
Resp:
A hierarquia é:
- Registradores;
- Memória cache;
- Memoria principal;
- Disco magnético/ SSD;
- Memória óptica;
- Fita magnética;

2. Descreva o principio da localidade.
Resp:
O princípio da localidade se divide em: temporal e espacial.
Principio da localidade temporal: localizações de memória recentemente acessadas tem altas chances de serem acessada novamente.
Principio da localidade espacial: localizações de memória com endereços similares ao de uma região de memória recém acessada tem altas chances de serem acessadas novamente.

4. Quais são os tipos de endereço de uma memória cache? Explique cada um.
	Grande parte das arquiteturas permite o uso da memória virtual: endereçamento da memória principal de maneira lógica, sem considerar a quantidade de memória física disponível.
	Uma unidade de gerenciamento de memória é responsável por traduzir o endereço lógico para o físico.
	Quando se usa memória virtual há duas opções para a cache:
	Cache virtual: 
	- armazena os dados usando endereços virtuais;
	- a cache fica entre o MMU e o processador;
	- A CPU acessa a cache sem acessar o MMU; -> acesso mais rápido.
	-  é necessário esvaziar a cache em troca de processos ou usar bits que indiquem o espaço do endereço virtual.
	 Cache física:
	 - Armazena os dados usando endereços físicos.
	 - A cache fica entre o MMU e a memória principal.
	 - O endereço primeiro é traduzido no MMU, e após isso é buscado na cache. -> acesso mais lento a cache.
	 - Suporta a troca de contexto de processos sem a necessidade de ser esvaziada.

5. Quais são as funções de mapeamento que podem ser usadas na memória cache? Explique o
funcionamento de cada uma delas.
Três técnicas são usadas para o mapeamento:
- Mapeamento direto: Cada bloco da memória só pode estar em uma linha da cache (Dois blocos podem ser mapeadas para uma mesma linha, porém somente um estará na linha em um determinado instante de tempo).
- Mapeamento associativo: pode ser visto como a "outra extremidade" do mapeamento direto; Qualquer bloco pode estar em qualquer linha da cache.
- Mapeamento associativo por conjunto: meio termo entre o mapeamento direto e o mapeamento associativo. A cache é dividida em conjuntos(vias), onde cada conjunto possui uma quantidade fixa de linhas. Cada bloco da MP pode ser mapeado somente em um conjunto(Porém pode estar em qualquer linha daquele conjunto).
6. Quais são os algoritmos de substituição de linhas na cache? Explique cada um deles.
- LRU: Usado menos recentemente. Substitua a linha que está armazenando o bloco que não teve acesso por mais tempo;
- FIFO: primeiro a entrar primeiro a sair. Substitua o bloco que está armazenado há mais tempo. O primeiro bloco a entrar na cache é o primeiro a sair.
- LFU: Usado menos frequentemente. Substitua de acordo com a quantidade de usos. O bloco menos usado que está na cache sai
- Aleatório: escolhe um bloco aleatório e substitui