# Desafio Criativo: Extraindo Insights do Feedback de Clientes Bancários

> **Tema escolhido:** Saldo parado em conta corrente após o vencimento de aplicações financeiras (CDBs, LCIs, Fundos de Investimento).

---

## 🧱 Passo 1 — Defina a intenção

Quero que a IA analise **reclamações, dúvidas e relatos de insatisfação de clientes sobre saldo parado em conta corrente após o vencimento de aplicações financeiras (CDBs, LCIs, LCAs e Fundos de Investimento)** para identificar **falhas na comunicação de vencimento, ausência de resgate automático, atritos na jornada de reinvestimento e percepção de abandono pela assessoria do banco**.

O resultado será usado por **squads de Produtos de Investimentos (Wealth Management) e equipes de UX/Engajamento** para apoiar **a criação de alertas proativos de vencimento, fluxos de reinvestimento automático em 1 clique e melhoria na assessoria financeira digital e presencial**.

A entrega deve conter **um resumo executivo, uma tabela de atritos mapeados por causa raiz, e uma lista de iniciativas estratégicas priorizadas**.

O resultado será considerado bom se **focar objetivamente na retenção do patrimônio do cliente, apresentar evidências dos dados fornecidos, respeitar o sigilo financeiro e sugerir ações concretas e implementáveis que evitem a perda de rentabilidade por inércia — tanto do cliente quanto do banco**.

---

## 🧱 Passo 2 — Adicione contexto e restrições

**Contexto:** Estou trabalhando com feedbacks de clientes bancários relacionados ao **ciclo de vida de investimentos, especificamente o momento crítico de vencimento de aplicações e a ausência de destinação imediata do saldo, que acaba ficando parado na conta corrente sem rendimento, gerando insatisfação e risco de churn patrimonial para o banco**.

**Dados disponíveis:** A base contém os seguintes campos por feedback:
- `data_feedback` — data em que o comentário foi registrado
- `tipo_aplicacao` — produto financeiro vencido (CDB, LCI, LCA, Fundo)
- `dias_saldo_parado` — quantidade de dias com o saldo sem destinação
- `texto_reclamacao` — relato textual do cliente (campo livre)
- `canal_origem` — canal onde o feedback foi registrado (App, Gerente, SAC, Ouvidoria)
- `perfil_investidor` — segmentação do cliente (Varejo, Alta Renda, Private)
- `nota_satisfacao` — NPS ou CSAT de 1 a 5

**Critérios de análise:** A IA deve classificar os feedbacks por:
- **Causa raiz** do saldo parado: falta de notificação de vencimento, resgate automático não configurado/não ofertado, dificuldade de navegação no app, falta de contato proativo do gerente
- **Sentimento predominante**: frustração, perda financeira percebida, sensação de abandono, confusão
- **Urgência/impacto**: considera a nota de satisfação e o tempo de saldo parado
- **Perfil do investidor**: segmentação para identificar se o problema afeta mais clientes de varejo ou alta renda

**Cuidados e restrições:**
- Use apenas os dados fornecidos. Não invente padrões, taxas ou conclusões.
- Não exponha dados sensíveis, valores exatos de patrimônio ou dados pessoais. Se o cliente mencionar valores no relato, substitua por `[VALOR OMITIDO]`. Respeito rigoroso à **LGPD** e ao **Sigilo Bancário**.
- Se houver informação insuficiente para tirar uma conclusão, indique explicitamente a limitação.
- Use linguagem **executiva, voltada para produto financeiro, retenção de ativos e jornada do investidor**.

---

## 🧱 Passo 3 — Prompt Final (pronto para uso)

> Copie o bloco abaixo e cole diretamente em uma IA. Substitua o campo `[INSERIR BASE DE DADOS]` pelos feedbacks reais ou pelos dados de exemplo ao final deste arquivo.

---

```
Atue como Especialista em Produtos de Investimentos (Wealth Management) e Experiência do Cliente (CX) em um banco de varejo e alta renda.

Sua tarefa é analisar reclamações, dúvidas e relatos de clientes sobre saldo parado em conta corrente após o vencimento de aplicações financeiras (CDBs, LCIs, LCAs e Fundos), com o objetivo de identificar falhas de comunicação, atritos na jornada de resgate e reinvestimento, e oportunidades de retenção patrimonial.

CONTEXTO:
A análise será usada por squads de produtos de investimentos e gestores de relacionamento para reduzir o "cash drag" — dinheiro parado sem render após o vencimento — e melhorar a jornada de pós-vencimento. O objetivo é transformar a inércia do cliente em oportunidades de reinvestimento assessorado ou automático, evitando churn patrimonial e perda de share of wallet para a concorrência.

DADOS DISPONÍVEIS:
Serão fornecidos registros de feedback com os seguintes campos:
- data_feedback, tipo_aplicacao, dias_saldo_parado, texto_reclamacao, canal_origem, perfil_investidor, nota_satisfacao (1–5).

INSTRUÇÕES DE ANÁLISE:
1. Classifique os feedbacks por causa raiz do saldo parado (ex: falta de notificação de vencimento, ausência de oferta de reinvestimento, dificuldade de navegação no app, falta de contato do gerente).
2. Identifique padrões de insatisfação recorrentes, como sensação de abandono pela assessoria, frustração com perda de rentabilidade ou confusão sobre o destino do saldo.
3. Aponte evidências nos dados fornecidos usando trechos curtos e anonimizados dos relatos.
4. Compare os padrões entre perfis de investidor (Varejo vs. Alta Renda) e canais de origem, destacando diferenças relevantes.
5. Sugira ações práticas para melhorar alertas de vencimento, criar fluxos de "reinvestimento em 1 clique" e capacitar a rede de gerentes/agências.

FORMATO DA RESPOSTA:
1. RESUMO EXECUTIVO (até 5 linhas): principal gargalo identificado na retenção de ativos no pós-vencimento.
2. MATRIZ DE ATRITOS (tabela): colunas — Causa Raiz | Sentimento | Evidência (trecho anonimizado) | Ação de Produto/CX Sugerida.
3. ANÁLISE POR SEGMENTO: parágrafo curto comparando o impacto nos perfis Varejo, Alta Renda e Private (se disponível nos dados).
4. TOP 3 INICIATIVAS ESTRATÉGICAS: as três intervenções de maior impacto para evitar fuga de recursos e aumentar o share of wallet.
5. LIMITAÇÕES DA ANÁLISE: informe o que não foi possível concluir com os dados fornecidos.

RESTRIÇÕES:
- Use apenas os dados fornecidos. Não invente números, taxas, causas ou conclusões.
- LGPD e Sigilo Bancário: não exponha valores exatos de patrimônio, saldos ou dados pessoais. Se valores forem citados nos relatos, substitua por [VALOR OMITIDO].
- Informe explicitamente limitações quando os dados forem insuficientes para uma conclusão técnica.
- Use linguagem executiva, focada em retenção de ativos, rentabilidade e jornada do investidor.

[INSERIR BASE DE DADOS / FEEDBACKS AQUI]
```

---

## 📊 Base de Dados de Exemplo (para testar o prompt)

> Use os registros abaixo como entrada ao testar o prompt. São dados fictícios criados apenas para demonstração.

| data_feedback | tipo_aplicacao | dias_saldo_parado | texto_reclamacao | canal_origem | perfil_investidor | nota_satisfacao |
|---|---|---|---|---|---|---|
| 2025-03-10 | CDB | 18 | "Meu CDB venceu e não recebi nenhum aviso. O dinheiro ficou parado na conta por semanas sem render nada. Fui no app e não encontrei nenhuma sugestão de onde aplicar." | App | Varejo | 2 |
| 2025-03-12 | LCI | 5 | "Já é a segunda vez que meu investimento vence e ninguém do banco me liga. Esperava que o gerente me procurasse para orientar." | Gerente | Alta Renda | 1 |
| 2025-03-15 | Fundo | 3 | "Saiu do fundo automaticamente mas o dinheiro foi pra conta corrente. Não entendo por que não reinvestiu direto. Precisei ligar pro SAC." | SAC | Varejo | 3 |
| 2025-03-18 | CDB | 22 | "Perdi quase um mês de rendimento porque o banco não me avisou. Resolvi mover tudo para outra corretora." | Ouvidoria | Alta Renda | 1 |
| 2025-03-20 | LCA | 7 | "Gostei quando o gerente me ligou antes de vencer. Queria que isso fosse padrão sempre." | Gerente | Private | 5 |
| 2025-03-22 | CDB | 12 | "No app não tem nenhuma tela que mostre o que fazer depois que o investimento vence. A experiência é confusa." | App | Varejo | 2 |
| 2025-03-25 | Fundo | 1 | "Recebi notificação no app com sugestão de reinvestimento. Ótimo! Reinvesti em segundos." | App | Alta Renda | 5 |
| 2025-04-01 | CDB | 30 | "Meu dinheiro ficou sem render por um mês inteiro. Quando percebi, já tinha perdido muito em rendimento. O banco deveria ter me avisado." | SAC | Varejo | 1 |

