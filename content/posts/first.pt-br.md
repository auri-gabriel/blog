+++
title = "Por que escolhi o Zola para um blog profissional de engenharia"
date = 2026-03-14
translation_key = "why-i-chose-zola"
authors = ["Auri Gabriel"]

[taxonomies]
categories = ["Desenvolvimento", "Arquitetura"]
tags = ["zola", "blog", "engenharia", "workflow"]

[extra]
lead = "Um relato prático sobre por que adotei o Zola, quais trade-offs aceitei e como pretendo evoluir este blog."
+++

Eu queria um blog rápido, simples de manter e centrado em escrita. Avaliei algumas opções e escolhi o Zola porque ele oferece um fluxo estático limpo, sem overhead de frameworks JavaScript no runtime.

Este é o primeiro post real do blog. Em vez de focar em testes visuais, quero registrar decisões técnicas concretas e o raciocínio por trás delas.

## O que eu precisava de uma stack para blog

Antes de escolher a stack, defini alguns requisitos não negociáveis:

- build e deploy rápidos
- escrita em Markdown sem fricção
- saída estática excelente para SEO
- poucas dependências em runtime
- suporte simples a múltiplos idiomas

O Zola atende esses pontos com ótima relação entre simplicidade e controle.

## Por que o Zola venceu

A principal vantagem para mim foi a clareza do modelo de desenvolvimento:

1. escrever conteúdo em Markdown
2. estruturar com templates
3. estilizar com Sass
4. publicar arquivos estáticos

Esse fluxo é direto e eficiente para um blog técnico pessoal.

Também gostei do suporte nativo a taxonomias, paginação e multilíngue sem depender de um ecossistema de plugins pesado.

## Trade-offs que eu aceitei

Nenhuma stack é perfeita. Com Zola, os trade-offs foram:

- menos plugins prontos do que algumas plataformas maiores
- mais trabalho manual de template para UX muito customizada
- necessidade de manter convenções de conteúdo bem definidas

Para este projeto, esses pontos são aceitáveis.

## Fluxo atual de publicação

Hoje meu processo está assim:

```bash
# preview local
zola serve

# validação para publicar
zola build
```

Só publico quando o build passa e o artigo está bom em desktop e mobile.

## Próximos temas do blog

Com a base estável, os próximos posts vão focar em:

- decisões de arquitetura frontend
- padrões práticos de TypeScript
- CI/CD e experiência de desenvolvimento
- histórias reais de migração e lições aprendidas

A meta é consistência: menos experimentos aleatórios, mais conteúdo técnico útil.

## Nota final

Escolher ferramenta é menos sobre hype e mais sobre restrições reais. Para este blog, o Zola me dá o equilíbrio certo entre velocidade, controle e simplicidade.
