# Desafios

Escolha um dos desafios abaixo e nos mande o link do seu github com a resolução. Fique à vontade para escolher
qualquer um dos três desafios, faça aquele que você vá conseguir fazer com mais qualidade.

## Desafio 1

Sua primeira tarefa como estagiário será implementar a criação de contas de e-mail para alunos da UFF. Para isso,
será necessário ler o [arquivo csv](datasets/alunos.csv) que contém os dados dos alunos e, de acordo com o nome e o status do aluno oferecer um conjunto de
opções de e-mail para ele escolher. Ao final do processo, o aluno recebe uma mensagem informando que sua conta será criada
nos próximos minutos e que ele receberá um SMS com sua primeira senha de acesso.

### Regras
* Apenas alunos ativos podem criar um UFFMail
* As opções de UFFMail devem ser geradas de acordo com o nome do aluno
* Um aluno só pode ter um UFFMail
* Utilizar Orientação a Objetos para resolver o problema
* Livre escolha para a linguagem a ser utilizada

### Dicas
- Quais classes são necessárias para resolver este problema?
- Desenvolva sempre buscando o menor acoplamento possível entre as classes
- Seu software deve estar preparado para eventuais mudanças
- A geração de opções para o usuário fica a seu critério
- Não é necessário consumir nenhuma API para resolver o problema, basta retornar as mensagens e fingir que o e-mail foi 
criado, faça o mesmo para o SMS
- Você pode atualizar o csv preenchendo a coluna de uffmail quando um e-mail for criado, mas isso é opcional
 
### Exemplo
```bash
Digite sua matrícula:
105457

Laura, por favor escolha uma das opções abaixo para o seu UFFMail
1 - laura_azevedo@id.uff.br
2 - lauraac@id.uff.br
3 - lauracunha@id.uff.br
4 - lcunha@id.uff.br
5 - lazevedocunha@id.uff.br

1

A criação de seu e-mail (laura_azevedo@id.uff.br) será feita nos próximos minutos.
Um SMS foi enviado para 99999-9971 com a sua senha de acesso.
```
## Desafio 2

Seu objetivo é, para um dado endereço, informar quais são os bicicletários (BikeRio) mais próximos em ordem decrescente 
de distância. Para isso, você deve consumir a API do datario que contém a localização de cada bicicletário (latitute e longitute)
 e a API do OpenStreetMap, que retorna a latitute e longitude de um determinado endereço.
 
A API do BikeRio está disponível em: http://dadosabertos.rio.rj.gov.br/apiTransporte/apresentacao/rest/index.cfm/estacoesBikeRio

A API do OpenStreetMap está documentada em: http://wiki.openstreetmap.org/wiki/Nominatim

Exemplo de uso da API do OpenStreetMap: http://nominatim.openstreetmap.org/search?street=Avenida%20Bartolomeu%20Mitre&city=Rio%20de%20Janeiro&format=json&polygon=1&addressdetails=1

O software pode ser entregue na forma de script ou pode ser uma aplicação web e pode ser feito em qualquer linguagem. 
Opte pela que você tem maior domínio e que solucione o problema de forma mais simples.

```bash
Para resolver esse problema, você vai precisar:
1) Realizar uma requisição HTTP para as APIs
2) Realizar parse do JSON retornado pelas APIs
3) Calcular a distância entre dois pontos no mapa (existe uma equação pra isso!)
4) Verificar dentre as estações, qual está mais próxima do endereço passado
```

Será um *plus* caso você:

* Utilize TDD
* Faça o seu projeto rodar web
* Incluir um mapa plotando a localização do usuário e das estações
* Fizer no seu desafio utilizando a sua conta do GitHub


## Desafio 3

Você precisa calcular o CR de alunos de uma universidade. Para isto será preciso ler de um [arquivo csv](datasets/notas.csv) a lista de notas dos alunos e, de acordo com as notas e os critérios da universidade, calcular o CR de todos os alunos. Ao final do processo, será preciso mostrar na tela o CR de todos os alunos e qual a média de CR dos cursos.

### Regras
* A nota do aluno vai de zero até 100;
* Uma nota é associada a uma disciplina e a um código de curso;
* O CR é a média ponderada da nota do aluno naquela turma com a carga horária daquela turma. O cálculo é:
  * > CR = Nota(i)*CargaHoraria(i)/TotalCargaHoraria 
  * i é a i-ésima turma de um aluno
* Utilizar Orientação a Objetos para resolver o problema
* Escolha a linguagem que achar adequada

### Exemplo
Após executar a sua aplicação, o sistema deve exibir uma saída similar a:

```bash
------- O CR dos alunos é: --------
100  -  10 
101  -  11
...
116  -  26
-----------------------------------
----- Média de CR dos cursos ------
10   -  12
11   -  45
..
100  -  13
-----------------------------------
```

### Dicas
- Quais classes são necessárias para resolver este problema?
- Desenvolva sempre buscando o menor acoplamento possível entre as classes;
- Concentre-se em desenvolver uma aplicação simples em console, tentando resolver o problema principal: o cálculo do CR dos alunos e dos cursos;
- Testes automatizados e TDD darão pontos positivos;
- Se for desenvolver uma GUI, dê preferência a um framework web, como rails, spring-boot, etc.
