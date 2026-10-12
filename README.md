# Conventional Commits — Guia em pt-BR

O **Conventional Commits** é uma convenção para padronizar mensagens de commit do Git. Ela facilita a leitura do histórico, a identificação do tipo de alteração e a automação de processos, como geração de changelogs.

## 1. Formato de uma mensagem

```text
<tipo>(<escopo>): <descrição>
```

- **Tipo:** categoria da alteração, como `feat`, `fix` ou `docs`.
- **Escopo:** parte do projeto afetada; é opcional.
- **Descrição:** resumo curto e claro da alteração.

Exemplos:

```text
feat(funcionario): adiciona 
fix(empresa): corrige 
refactor(service): simplifica lógica de negócio
test(funcionario): adiciona testes de cadastro
docs(readme): atualiza instruções de instalação
build(maven): atualiza dependências do projeto
```

## 2. Tipos de commit

| Tipo | Quando utilizar |
|---|---|
| `feat` | Adiciona uma nova funcionalidade. |
| `fix` | Corrige um bug ou erro. |
| `refactor` | Reestrutura o código sem alterar seu comportamento externo. |
| `perf` | Melhora o desempenho da aplicação. |
| `style` | Altera formatação do código, como espaços, quebras de linha ou ponto e vírgula, sem mudar sua lógica. |
| `test` | Adiciona ou corrige testes. |
| `docs` | Altera apenas a documentação. |
| `build` | Altera ferramentas de build, dependências, versões ou componentes necessários para compilar o projeto. |
| `ops` | Altera aspectos operacionais, como infraestrutura, deploy, backup ou recuperação. |
| `chore` | Realiza tarefas gerais de manutenção que não se encaixam nos outros tipos, como alterações no `.gitignore`. |

### Como escolher o tipo?

- Use `feat` para uma funcionalidade nova.
- Use `fix` para corrigir um comportamento incorreto.
- Use `refactor` quando reorganizar ou melhorar a estrutura do código sem mudar o comportamento externo.
- Use `perf` quando o objetivo principal for melhorar o desempenho.
- Use `style` para formatação do código, não para mudanças no visual da interface.
- Use `test` para alterações em testes.
- Use `docs` para documentação.
- Use `build` para dependências e ferramentas de compilação.
- Use `ops` para infraestrutura e operação, caso o projeto adote esse tipo.
- Use `chore` para manutenção geral.

> **Observação:** `ops` e `chore` são tipos adicionais usados por algumas equipes, não tipos obrigatórios da especificação básica do Conventional Commits.

## 3. Escopos (*scopes*)

O escopo indica qual parte do projeto foi afetada. É opcional, e os nomes devem seguir um padrão coerente dentro do projeto.

| Escopo | Exemplo de utilização |
|---|---|
| `funcionario` | Alterações relacionadas a funcionários |
| `empresa` | Alterações relacionadas a empresas |
| `controller` | Alterações nos controllers |
| `service` | Alterações na camada de serviços |
| `repository` | Alterações nos repositórios |
| `entity` | Alterações nas entidades JPA |
| `database` | Alterações no banco de dados |
| `config` | Alterações de configuração |

Com escopo:

```text
fix(empresa): corrige relacionamento com funcionários
```

Sem escopo:

```text
feat: adiciona cadastro de funcionários
```

**Boas práticas para escopos:**

- O escopo é opcional.
- Escolha nomes curtos e claros.
- Mantenha consistência entre os commits do projeto.
- Não use o identificador de uma issue ou tarefa como escopo. Prefira `fix(empresa): ...` em vez de `fix(123): ...`.

## 4. Mudanças incompatíveis (*breaking changes*)

Quando uma alteração quebra a compatibilidade com o uso anterior da API ou do sistema, indique isso com `!` após o tipo ou após o escopo.

Exemplo:

```text
feat(api)!: altera formato da resposta

BREAKING CHANGE: o campo nome foi substituído por razaoSocial.
```

Também é possível registrar a mudança incompatível usando um rodapé iniciado por `BREAKING CHANGE:`.

## 5. Exemplos para Java e Spring Boot

```text
feat(funcionario): adiciona entidade de funcionário
feat(empresa): adiciona relacionamento com funcionários
fix(repository): corrige consulta de funcionários
refactor(service): extrai validação para método separado
test(funcionario): adiciona testes para cadastro
docs(readme): documenta como executar a aplicação
build(maven): atualiza versão de dependência
```

## 6. Recomendações

- Escreva descrições objetivas, com foco no que foi alterado.
- Prefira uma mensagem por alteração lógica.
- Evite mensagens vagas, como `ajustes`, `correções` ou `alterações`.
- Use o mesmo idioma nas descrições de forma consistente no projeto.
- Não inclua ponto final na descrição, salvo se o padrão da equipe exigir.
- Lembre-se de que a convenção padroniza a mensagem; ela não substitui uma boa organização dos commits.

## 7. Referência oficial

- [Conventional Commits — especificação 1.0.0](https://www.conventionalcommits.org/en/v1.0.0/)

A especificação oficial define a estrutura básica da mensagem e os significados de `feat`, `fix` e mudanças incompatíveis. Outros tipos, como `build`, `ops` e `chore`, podem ser adotados pela equipe conforme a necessidade.
