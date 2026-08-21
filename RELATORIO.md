# Atividade Prática – Integração Contínua

## 1. Nome do aluno / dupla

Nome completo: IGOR ALEXSANDRO BARBOSA DA COSTA - 04134673
               JACKELINE PEREIRA DOMINGUES - 04137210

## 2. Repositório

Link: https://github.com/DEV-4LEX/atividade-devops-ci

## 3. Ferramentas utilizadas

* Git
* GitHub
* GitHub Actions
* Python
* Pytest

## 4. O que foi desenvolvido?

Foi desenvolvida uma aplicação simples em Python contendo três funções matemáticas: soma, subtração e multiplicação. Também foram criados testes automatizados utilizando o Pytest para verificar o funcionamento correto dessas funções.

## 5. Como funciona a pipeline?

A pipeline de Integração Contínua foi configurada utilizando o GitHub Actions. Após cada `git push` realizado na branch `main`, o GitHub Actions executa automaticamente a pipeline.

Primeiramente, o código do repositório é baixado. Em seguida, o ambiente Python é configurado, as dependências do projeto são instaladas por meio do arquivo `requirements.txt` e, por fim, os testes automatizados são executados utilizando o Pytest.

Quando todos os testes são executados corretamente, a pipeline apresenta o resultado **PASS**. Caso algum teste apresente erro, a pipeline apresenta o resultado **FAIL**.

## 6. Teste realizado

Foram criados **3 testes automatizados**, sendo um para cada função da aplicação:

* Teste da função de soma;
* Teste da função de subtração;
* Teste da função de multiplicação.

Inicialmente, os testes foram executados localmente e apresentaram resultado positivo.

## 7. Falha proposital

Foi introduzido propositalmente um erro na função `soma`, alterando seu funcionamento de:

`return a + b`

para:

`return a - b`

Após realizar o commit e o `git push`, a pipeline foi executada automaticamente pelo GitHub Actions.

## 8. Resultado

Sim. A pipeline identificou o erro propositalmente introduzido.

O teste da função de soma apresentou falha, fazendo com que a execução da pipeline fosse marcada como **FAIL**.

Depois disso, o código foi corrigido, restaurando a operação de soma para `return a + b`. Um novo commit e `git push` foram realizados e a pipeline foi executada novamente, apresentando resultado **PASS**.

## 9. Conclusão

Com a atividade, foi possível compreender na prática o conceito de Integração Contínua. A cada alteração realizada no código e enviada para o GitHub por meio do `git push`, o GitHub Actions executou automaticamente os procedimentos definidos na pipeline, incluindo a instalação das dependências e a execução dos testes.

A atividade também demonstrou a importância dos testes automatizados para identificar erros rapidamente. Quando um erro proposital foi introduzido, a pipeline detectou a falha e impediu que uma alteração com problema passasse despercebida. Após a correção, uma nova execução confirmou que os testes estavam funcionando novamente.

Dessa forma, a Integração Contínua permite automatizar a verificação do código e aumentar a confiabilidade do processo de desenvolvimento.
