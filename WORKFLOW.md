# Workflow de Desenvolvimento e Convenções de Commits

[![GitHub Flow](https://img.shields.io/badge/Workflow-GitHub%20Flow-blue.svg)](https://guides.github.com/introduction/flow/)
[![Commits Semânticos](https://img.shields.io/badge/Commits-Semânticos-green.svg)](https://www.conventionalcommits.org/)
[![Code Review](https://img.shields.io/badge/Code%20Review-Obrigatório-red.svg)](https://github.com/features/code-review/)
[![CI/CD](https://img.shields.io/badge/CI%2FCD-Automático-orange.svg)](https://github.com/features/actions)

## Visão Geral

Este documento define o workflow oficial de desenvolvimento e as convenções de commits para o **Portal de Vagas e Estágios**, garantindo consistência, qualidade e colaboração eficiente entre todos os membros do time.

<div align="center">
  <img src="https://img.icons8.com/color/96/000000/workflow.png" alt="Workflow" width="80"/>
  <p><em>Fluxo de trabalho otimizado para desenvolvimento ágil</em></p>
</div>

## Modelo de Workflow Adotado

### GitHub Flow

Adotamos o **GitHub Flow**, que é simples e eficiente para desenvolvimento contínuo:

<div align="center">
  <p><em>Visualização do GitHub Flow - <a href="https://guides.github.com/introduction/flow/">Fonte: GitHub Guides</a></em></p>
</div>

- **Branch Principal**: `main` (produção)
- **Branches de Feature**: crie uma branch a partir da `main` com o nome `feature/nome-da-feature`
- **Pull Requests**: toda nova feature ou correção deve ser submetida via Pull Request para a `main`
- **Deploy Contínuo**: após aprovação e merge na `main`, o deploy pode ser realizado automaticamente

Esse fluxo incentiva pequenas entregas frequentes e revisões colaborativas.

### Processo do GitHub Flow

<div align="center">
  <img src="https://img.icons8.com/?size=100&id=bGpdQvUlLJDg&format=png&color=000000" alt="Processo" width="80"/>
</div>

1. **🔀 Criar Branch**: A partir da `main` para cada nova feature
2. **💻 Desenvolver**: Implementar a funcionalidade com commits frequentes
3. **📝 Pull Request**: Criar PR para `main` com descrição detalhada
4. **👀 Code Review**: Revisão obrigatória por pelo menos um desenvolvedor
5. **🧪 Testes**: Verificar se todos os testes passam
6. **🔀 Merge**: Após aprovação, fazer merge na `main`
7. **🚀 Deploy Staging**: Deploy automático para ambiente de staging
8. **✅ Validação**: Testes em staging com equipe de QA
9. **🌐 Deploy Produção**: Deploy para produção após validação
10. **🗑️ Deletar Branch**: Remover branch após merge bem-sucedido

### Estratégia de Branches

```
main (produção) 🟢
├── feature/vagas-listing 🟡
├── feature/candidatura-form 🟡
├── feature/admin-dashboard 🟡
├── hotfix/security-patch 🔴
```

<div align="center">
  <img src="https://img.icons8.com/?size=100&id=33277&format=png&color=000000" alt="Git Branches" width="80"/>
  <p><em>Estrutura de branches organizada e clara</em></p>
</div>

#### Regras de Nomeação

- **Features**: `feature/nome-descritivo-em-kebab-case`
- **Hotfixes**: `hotfix/descricao-breve`
- **Bugs**: `bugfix/descricao-do-bug`

#### Fluxo de Merges

<div align="center">
  <img src="https://img.icons8.com/?size=100&id=9315&format=png&color=000000" alt="Merge Flow" width="80"/>
</div>

1. **Feature → Main**: Todas as features são integradas via Pull Request direto para main
2. **Main → Staging**: Deploy automático para ambiente de staging
3. **Staging → Produção**: Deploy para produção após validação da equipe
4. **Hotfix → Main**: Direto para produção em casos críticos

## Convenções de Commits Semânticos

### Tipos Específicos do Projeto

<div align="center">
  <img src="https://img.icons8.com/?size=100&id=33279&format=png&color=000000" alt="Commits" width="80"/>
</div>

- **vaga**: Operações relacionadas ao sistema de vagas
- **candidato**: Operações relacionadas ao sistema de candidatos
- **empresa**: Operações relacionadas ao sistema de empresas
- **match**: Operações relacionadas ao sistema de matching
- **notificacao**: Sistema de notificações e alertas
- **analytics**: Métricas e relatórios
- **seguranca**: Aspectos de segurança e autenticação

### 📋 Sintaxe Padrão

```
tipo(escopo): descrição

[corpo opcional]

[rodapé opcional]
```

### 🏷️ Tipos de Commit

#### Tipos Padrão

- **feat**: Nova funcionalidade
- **fix**: Correção de bug
- **docs**: Documentação
- **style**: Formatação, ponto e vírgula, etc.
- **refactor**: Refatoração de código
- **test**: Adição ou correção de testes
- **chore**: Tarefas de build, configuração, etc.

### 💡 Exemplos de Uso

#### Tipos Padrão
```bash
feat: adicionar sistema de filtros avançados para vagas
fix: corrigir validação de email no formulário de candidatura
docs: atualizar README com instruções de instalação
refactor: reorganizar estrutura de componentes React
test: adicionar testes unitários para serviço de vagas
```

#### Tipos Específicos
```bash
vaga: implementar sistema de busca por localização
candidato: adicionar upload de currículo em PDF
empresa: criar dashboard de métricas de vagas
match: implementar algoritmo de matching inteligente
notificacao: adicionar alertas por email para candidatos
analytics: criar relatório de performance de vagas
seguranca: implementar autenticação de dois fatores
```

## Regras de Atualização

### Branch Principal (main)

<div align="center">
  <img src="https://img.icons8.com/?size=100&id=mb5fHgPn6NuP&format=png&color=000000" alt="Main Branch" width="80"/>
</div>

- **Atualização**: A cada Pull Request aprovado e merge
- **Frequência**: Contínua (deploy automático para staging)
- **Responsável**: Equipe de desenvolvimento
- **Pré-requisitos**: Code review aprovado + testes passando

### Branches de Feature

- **Atualização**: Quando a feature estiver completa
- **Frequência**: Conforme conclusão de cada feature
- **Responsável**: Desenvolvedor da feature
- **Pré-requisitos**: Feature testada + documentada

### Integração Contínua

<div align="center">
  <img src="https://img.icons8.com/?size=100&id=oQrt8Xgfa-yp&format=png&color=000000" alt="CI/CD" width="80"/>
</div>

- **Build**: Automático a cada push
- **Testes**: Unitários, integração e E2E
- **Qualidade**: Análise estática de código
- **Deploy**: Automático para staging após merge na main

### Ambiente de Staging

<div align="center">
  <img src="https://img.icons8.com/?size=100&id=65285&format=png&color=000000" alt="Staging" width="80"/>
</div>

- **Propósito**: Validação final antes da produção
- **Acesso**: Equipe de QA e stakeholders
- **Dados**: Dados anonimizados para testes
- **Deploy**: Automático após merge na main

### Ambiente de Produção

<div align="center">
  <img src="https://img.icons8.com/?size=100&id=NdOvHFhYrPKq&format=png&color=000000" alt="Production" width="80"/>
</div>

- **Propósito**: Aplicação em produção
- **Acesso**: Usuários finais
- **Dados**: Dados reais dos usuários
- **Deploy**: Manual após validação em staging

### 🚀 Processo de Deploy

<div align="center">
  <img src="https://img.icons8.com/?size=100&id=Alvy4ZVgUFlQ&format=png&color=000000" alt="Deploy" width="80"/>
</div>

1. **🔀 Merge na Main**: Deploy automático para staging
2. **✅ Validação em Staging**: Testes da equipe de QA
3. **👍 Aprovação**: Stakeholders aprovam mudanças
4. **🌐 Deploy Produção**: Deploy manual para produção
5. **📊 Monitoramento**: Verificação de saúde da aplicação

## 🔗 Links Úteis

- **📚 GitHub Flow**: [Guia Oficial](https://guides.github.com/introduction/flow/)
- **📝 Commits Semânticos**: [Convenção](https://www.conventionalcommits.org/)
- **🔍 Code Review**: [Boas Práticas](https://github.com/features/code-review/)
- **🚀 GitHub Actions**: [CI/CD](https://github.com/features/actions)
- **📖 Git Cheat Sheet**: [Referência Rápida](https://education.github.com/git-cheat-sheet-education.pdf)

## 📊 Dashboard de Status

<div align="center">

| Métrica | Status | Valor |
|---------|--------|-------|
| **Build Status** | 🟢 | Passando |
| **Test Coverage** | 🟡 | 85% |
| **Code Quality** | 🟢 | A+ |
| **Deploy Staging** | 🟢 | Ativo |
| **Deploy Produção** | 🟡 | Manual |

</div>

---

<div align="center">
  <p>📅 <strong>Última atualização</strong>: $(date)</p>
  <p>🏷️ <strong>Versão</strong>: 1.0.0</p>
  <p>👥 <strong>Responsável</strong>: Equipe de Desenvolvimento</p>
  
  <p>
    <a href="https://github.com/seu-usuario/portal-vagas/issues">🐛 Reportar Problema</a> •
    <a href="https://github.com/seu-usuario/portal-vagas/discussions">💬 Discussões</a> •
    <a href="https://github.com/seu-usuario/portal-vagas/wiki">📖 Wiki</a>
  </p>
</div>
