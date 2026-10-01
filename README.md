Desafio DevSecOps — Gerenciador de Tarefas
Sobre o Projeto
Este repositório faz parte do desafio prático do módulo de DevSecOps da ADA Tech. Você receberá este projeto com vulnerabilidades propositais e uma pipeline incompleta. Seu objetivo é implementar a pipeline de segurança e corrigir as vulnerabilidades.

Estado atual
A pipeline está incompleta. Os steps de segurança precisam ser implementados por você.

Sua missão
Implementar os steps de segurança no pipeline.yml
Fazer a pipeline quebrar ao detectar os problemas
Corrigir as vulnerabilidades encontradas
Fazer a pipeline passar com tudo verde ✅
Documentar o funcionamento da pipeline neste README
O que implementar
 Secrets Scanning com Gitleaks
 SAST com Semgrep
 SCA com Grype
 Deploy com GitHub Pages
Como a pipeline funciona
A pipeline é executada automaticamente a cada push na branch main e tem como objetivo validar a segurança da aplicação antes do deploy.

1. Checkout do código
Utiliza o GitHub Actions para baixar o conteúdo do repositório e disponibilizá-lo para as próximas etapas.

2. Secrets Scanning — Gitleaks
Executa o Gitleaks para identificar possíveis segredos expostos no código, como tokens, senhas, chaves de API e credenciais que possam ter sido commitadas acidentalmente.

Objetivo: evitar vazamento de informações sensíveis.

3. SAST — Semgrep
Executa uma análise estática de segurança do código-fonte (SAST), procurando padrões inseguros e vulnerabilidades conhecidas.

Objetivo: identificar falhas de segurança antes da aplicação entrar em produção.

4. SCA — Grype
Analisa as dependências do projeto para detectar bibliotecas com vulnerabilidades conhecidas (CVEs).

Objetivo: garantir que componentes de terceiros utilizados pela aplicação estejam seguros.

5 Deploy
Após todas as validações serem aprovadas, o conteúdo da aplicação é publicado no GitHub Pages.

Objetivo: disponibilizar a aplicação apenas quando todas as verificações de segurança forem concluídas com sucesso.

Fluxo da pipeline
Build → Gitleaks → Semgrep → Grype → Deploy

Caso qualquer etapa encontre um problema crítico, a execução é interrompida e o deploy não é realizado.
https://github.com/vivianispn-spec/projeto-devsecop-desafio