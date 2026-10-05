---
name: resume-ats
description: Monta, revisa ou otimiza currículos (CV) em português para passarem bem por sistemas de triagem automática (ATS - Applicant Tracking System), transformando experiências em bullets com métricas quantificáveis e alinhando palavras-chave com a vaga-alvo. Use esta skill sempre que o usuário mencionar currículo, CV, resumo profissional, "montar meu currículo", "revisar meu currículo", "ajustar currículo pra uma vaga", "meu currículo não está passando no ATS/triagem", preparar candidatura para uma vaga específica, ou pedir pra tornar suas experiências de trabalho mais fortes/quantificadas para um processo seletivo — mesmo que o usuário não use o termo "ATS" explicitamente.
---

# Currículo com métricas ATS

Currículos são filtrados por softwares (ATS) antes de qualquer humano ler. Um ATS lê texto puro extraído do arquivo e, frequentemente, pontua a compatibilidade comparando o texto do currículo com o texto da vaga. Isso significa duas coisas na prática: (1) o arquivo precisa ser estruturado de um jeito que o parser consiga extrair corretamente, e (2) o conteúdo precisa falar a mesma língua da vaga, com resultados concretos que provem a experiência — não só listar tarefas.

Esta skill cobre as duas frentes. Siga o processo abaixo em vez de só "deixar bonito" — a maioria dos currículos que falham no ATS falha por estrutura (tabelas, colunas, ícones) muito mais do que por conteúdo fraco, então vale a pena checar as duas coisas sempre.

## Processo

### 1. Entenda o ponto de partida
Pergunte (ou infira do que o usuário já mandou):
- Isso é um currículo do zero, uma revisão de um currículo existente, ou uma adaptação pra uma vaga específica?
- Existe uma vaga-alvo? Se sim, peça o texto da descrição da vaga — é a fonte das palavras-chave (passo 4). Sem isso, a otimização de keywords fica genérica.
- Quais experiências, formação e habilidades a pessoa tem? Se o usuário só descreveu em linguagem solta ("cuidava das redes sociais", "ajudava no financeiro"), isso ainda não são bullets prontos — vá para o passo 3 antes de montar o documento final.

Se o usuário colar um currículo pronto em PDF/Word/imagem, extraia o texto e avalie a estrutura dele antes de reescrever (passo 2).

### 2. Estrutura ATS-safe
Um ATS extrai o texto na ordem em que o parser consegue "ver" o documento — não necessariamente na ordem visual. Elementos que quebram essa extração ou confundem o parser:

- **Tabelas e colunas múltiplas** — o parser pode ler linha por linha misturando conteúdo de colunas diferentes, ou pular a coluna inteira.
- **Caixas de texto e elementos gráficos (SmartArt, ícones, barras de "nível de habilidade")** — muitos parsers simplesmente não leem o texto dentro de caixas de texto/imagens.
- **Foto, logos e texto dentro de imagem** — nunca é lido como texto.
- **Cabeçalho/rodapé para informações importantes** (telefone, e-mail) — alguns ATS ignoram cabeçalho e rodapé.
- **Fontes decorativas, símbolos como bullets não-padrão (➤, ✓ customizados), tabelas de contato lado a lado.**
- **Nomes de seção não-convencionais** ("Minha Jornada" em vez de "Experiência Profissional") — o ATS costuma procurar por cabeçalhos de seção conhecidos para categorizar o conteúdo.

Use sempre:
- Layout de coluna única, de cima para baixo.
- Fontes padrão (Arial, Calibri, Times New Roman).
- Cabeçalhos de seção convencionais: **Resumo**, **Experiência Profissional**, **Formação Acadêmica**, **Habilidades**, **Idiomas**, **Certificações** (ajuste os nomes, mas mantenha-os reconhecíveis).
- Bullets com `-` ou `•` simples.
- Datas em formato consistente (ex: `jan/2022 – mar/2024`).
- Nome e contato (telefone, e-mail, cidade, LinkedIn) no topo do corpo do documento, não em cabeçalho/rodapé.

Formato de entrega: por padrão, escreva o currículo em **Markdown/texto simples** (sem tabelas). É o formato mais seguro para ATS e o mais fácil de manter versionado neste repositório. Se o usuário pedir explicitamente um `.docx`, use a skill de Word do Claude e replique as mesmas regras acima dentro do documento (sem tabelas, colunas ou caixas de texto).

### 3. Transforme responsabilidades em bullets com métrica
A maior diferença entre um currículo fraco e um forte não é o design — é se os bullets prometem resultado ou só listam tarefa. Aplique a fórmula:

**Verbo de ação forte + o que foi feito + resultado quantificado (número, %, R$, tempo, volume)**

| Fraco (tarefa) | Forte (resultado quantificado) |
|---|---|
| "Responsável pelo atendimento ao cliente" | "Atendi uma média de 60 clientes/dia via chat e telefone, mantendo 95% de satisfação (CSAT)" |
| "Ajudava na gestão das redes sociais" | "Geri 4 redes sociais da marca, aumentando o engajamento em 38% em 6 meses" |
| "Cuidava do financeiro da empresa" | "Controlei o fluxo de caixa mensal de R$ 150 mil, reduzindo inadimplência em 20%" |
| "Trabalhei com vendas" | "Bati 112% da meta trimestral, gerando R$ 480 mil em vendas novas" |

Quando o usuário não tiver um número exato, não invente — ajude a estimar com perguntas simples: "quantas pessoas/mês?", "qual era a meta e quanto você bateu?", "quanto tempo isso levava antes vs. depois da sua solução?", "quantas pessoas sua equipe tinha?". Métricas aproximadas e honestas ("cerca de", "~30%") são melhores do que nenhuma métrica. Se depois de perguntar o usuário realmente não tiver nenhum número para aquele bullet específico, tudo bem manter um bullet qualitativo forte — não force um número falso.

Consulte `references/verbos-e-metricas.md` para bancos de verbos de ação e exemplos de métricas organizados por área (vendas, atendimento, TI, marketing, operações, RH, financeiro, educação) quando precisar de inspiração para uma área específica.

### 4. Alinhe com palavras-chave da vaga
Se houver uma descrição de vaga:
1. Liste os termos que se repetem ou aparecem em "requisitos"/"responsabilidades" — especialmente nomes de ferramentas, metodologias, certificações e hard skills (ex: "Excel avançado", "Scrum", "SAP", "atendimento B2B").
2. Verifique quais desses termos já aparecem no currículo do usuário com a mesma palavra (não só o sinônimo). Um ATS que faz correspondência literal não necessariamente entende que "planilhas" e "Excel" são a mesma coisa.
3. Incorpore os termos que fazem sentido genuíno com a experiência da pessoa — na seção de Habilidades e espalhados nos bullets de Experiência. Nunca adicione uma habilidade que a pessoa não tem só para "bater" com a vaga; isso quebra na entrevista e pode ser desqualificação por informação falsa.
4. Avise o usuário se perceber um requisito importante da vaga que ele claramente não atende — é mais útil saber disso agora do que descobrir na entrevista.

### 5. Monte o documento final
Template padrão (adapte os nomes de seção ao contexto, mas mantenha esta ordem e esta simplicidade estrutural):

```
NOME COMPLETO
Cidade, Estado | telefone | email | linkedin.com/in/usuario

RESUMO
2-3 linhas: quem é, principal área/especialidade, 1-2 resultados de destaque.

EXPERIÊNCIA PROFISSIONAL
Cargo — Empresa
mês/ano – mês/ano
- Bullet com verbo de ação + o que fez + resultado quantificado
- Bullet com verbo de ação + o que fez + resultado quantificado

Cargo anterior — Empresa
mês/ano – mês/ano
- Bullet...

FORMAÇÃO ACADÊMICA
Curso — Instituição, ano de conclusão (ou previsão)

HABILIDADES
Lista simples separada por vírgula ou bullets curtos — priorize as que aparecem na vaga-alvo.

IDIOMAS (se aplicável)
Idioma — nível

CERTIFICAÇÕES (se aplicável)
Nome — instituição, ano
```

### 6. Checklist final de compatibilidade ATS
Antes de entregar, revise o currículo final contra esta lista e avise o usuário de qualquer item que não passou:

- [ ] Coluna única, sem tabelas, sem caixas de texto, sem imagens com texto
- [ ] Fonte e bullets padrão, sem símbolos decorativos
- [ ] Cabeçalhos de seção convencionais (Experiência, Formação, Habilidades...)
- [ ] Contato no corpo do documento, não em cabeçalho/rodapé
- [ ] Cada cargo tem pelo menos 1-2 bullets com métrica quantificada (número, %, R$ ou tempo)
- [ ] Palavras-chave da vaga-alvo presentes literalmente no texto (quando houver vaga-alvo)
- [ ] Nenhuma habilidade ou dado inventado
- [ ] Datas em formato consistente, sem lacunas não explicadas óbvias
- [ ] 1 página para quem tem até ~10 anos de experiência; 2 páginas no máximo para sêniors — ATS não se importa, mas recrutador humano sim

Se o usuário quiser uma "nota" de compatibilidade, não finja ter acesso a um ATS real — explique que isso é uma autoavaliação qualitativa baseada na checklist acima (estrutura + densidade de métricas + cobertura de palavras-chave da vaga), não uma pontuação oficial de nenhum sistema específico (cada ATS comercial — Gupy, Workday, Greenhouse etc. — pontua de um jeito proprietário e não documentado publicamente).
