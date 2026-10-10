# Olá, eu sou o Wellington 👋

Trabalho com automação de marketing sobre o **Mautic**, integrado ao **n8n**.

## Como eu trabalho: a IA programa, eu superviso

Aposto que o futuro do desenvolvimento é a IA escrevendo o código e uma pessoa responsável por **garantir que ele esteja certo, seguro e entregue**. Todo o código dos meus projetos é escrito pelo **Claude** (Claude Code, da Anthropic), sob a minha supervisão. Não escondo isso: é o método.

Meu papel é o que a IA não pode assumir sozinha:

- **Definir o que fazer e o que não fazer.** O Claude só faz o que foi pedido. Qualquer ação fora do escopo, como instalar uma dependência, exige minha autorização antes.
- **Validar antes de entrar.** Nada é commitado até eu ver funcionando. O fluxo é fixo: branch, teste, código, execução dos testes, minha validação e só então commit e merge.
- **Desconfiar de alucinação.** Toda afirmação é conferida contra o sistema real: banco de dados, rotas, respostas do servidor e testes ao vivo. Quando algo não foi visto no navegador, o relatório diz isso.
- **Cuidar da segurança.** Ver abaixo.
- **Manter a documentação como contrato.** A cada entrega, a wiki e o README são atualizados, e cada mudança de produção vem com uma lista do que repetir lá.

### Segurança, na prática

- As telas e rotas novas reaproveitam as **permissões do próprio Mautic** (ver, editar, excluir), em vez de criar regras paralelas.
- Ações que alteram dados passam pelo **token CSRF** do Mautic.
- O código nunca altera os arquivos do núcleo: tudo entra pelos pontos de extensão do Mautic, como eventos, rotas e templates.
- Segredos ficam fora do repositório (variáveis de ambiente e `.env` ignorado pelo Git).
- Cada mudança traz testes unitários, testes em JavaScript onde há script na página e testes ao vivo contra a stack rodando.

## Projetos

| Projeto | O que faz |
|---|---|
| [**n8n-dispatch-bundle**](https://github.com/WellingtonFonseca/n8n-dispatch-bundle) | Plugin do Mautic que sincroniza templates de e-mail e dispara e-mail, SMS e HSM (WhatsApp) por meio do n8n, com acompanhamento do status de cada envio, histórico, tela de disparos e reenvio. |
| [**mc-cs-plugin-custom-objects**](https://github.com/WellingtonFonseca/mc-cs-plugin-custom-objects) | Fork do plugin de Custom Objects do Mautic, com busca por campo, filtro na API de itens, campo decimal, melhor desempenho e abas por objeto no contato. |
| [**mautic-patches-bundle**](https://github.com/WellingtonFonseca/mautic-patches-bundle) | Correções e pequenas melhorias de tela do núcleo do Mautic, sem editar o núcleo: tabelas de contatos em segmentos e campanhas, aba de filtros do segmento, atualização de segmento por API, correções de tema escuro e monitor de desempenho. |

## Stack

Mautic 5 · PHP · Symfony · MySQL · Docker · n8n · PHPUnit · Node.js · Claude Code
