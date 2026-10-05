# resume-ats

Skill do Claude Code para montar, revisar e otimizar currículos em português para passarem bem por sistemas de triagem automática (ATS — Applicant Tracking System).

## O que ela faz

- Converte experiências descritas de forma vaga em bullets com métricas quantificáveis (números, %, R$, tempo), seguindo a fórmula *verbo de ação + o que foi feito + resultado*.
- Revisa currículos prontos em busca de elementos que costumam quebrar a leitura por parsers de ATS (tabelas, colunas múltiplas, ícones, fotos, barras de progresso visuais) e reescreve em formato de coluna única.
- Extrai palavras-chave de uma descrição de vaga e ajuda a alinhar o currículo a elas, sem inventar habilidades que a pessoa não tem.
- Sugere uma checklist de autoavaliação de compatibilidade ATS antes da entrega final.

## Como instalar

Copie a pasta `resume-ats` (ou todo este repositório) para dentro do diretório de skills do Claude Code, por exemplo:

```
%USERPROFILE%\.claude\skills\resume-ats\
```

Certifique-se de que `SKILL.md` e a pasta `references/` fiquem juntos dentro dessa pasta.

## Estrutura

```
resume-ats-skill/
├── SKILL.md                      # instruções principais da skill
├── references/
│   └── verbos-e-metricas.md      # banco de verbos de ação e exemplos de métrica por área
└── evals/
    └── evals.json                # casos de teste usados para validar a skill
```

## Uso

Basta pedir, em uma conversa com o Claude Code, algo como:

- "me ajuda a montar meu currículo do zero"
- "revisa meu currículo pra ver se ele passa num ATS"
- "adapta meu currículo pra essa vaga: [colar descrição da vaga]"
