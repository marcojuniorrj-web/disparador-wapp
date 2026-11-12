# Regras do WhatsApp para envio em massa (pesquisa — 12/11/2026)

Fontes lidas (via Apify):
- WhatsApp Business Messaging Policy — https://business.whatsapp.com/policy (atualizada em 23/09/2026)
- Termos de Serviço — https://www.whatsapp.com/legal/terms-of-service
- FAQ "Uso não autorizado de mensagens automatizadas ou em massa" — https://faq.whatsapp.com/5957850900902049
- Messaging Limits (Meta for Developers, atualizado em 21/05/2026)

## 1. O que é proibido
- **WhatsApp comum e WhatsApp Business App:** os Termos proíbem expressamente "bulk messaging, auto-messaging, auto-dialing" e o uso não pessoal sem autorização. O FAQ diz que os produtos "não foram feitos para mensagens em massa ou automatizadas".
- **Punição:** banimento por machine learning, proibição de criar outra conta e **ação judicial**. Desde 07/12/2019 a Meta processa até empresas que só *anunciam* esse uso, mesmo sem prova dentro da plataforma.
- **Ferramentas não oficiais** (WhatsApp Web automatizado, extensões, APIs de terceiros que emulam o app) violam o item "Harm to WhatsApp" dos Termos (engenharia reversa, acesso automatizado, criar APIs que imitam o serviço).

## 2. O único caminho autorizado: WhatsApp Business Platform (API oficial / Cloud API)
- **Opt-in obrigatório:** só pode contatar quem (a) te deu o número e (b) autorizou receber mensagens suas. Provar o opt-in é responsabilidade da empresa (no Brasil também entra a LGPD).
- **Opt-out:** pedido para parar (dentro ou fora do WhatsApp) tem que ser respeitado, e a pessoa sai da lista.
- **Templates aprovados:** para *iniciar* uma conversa, só com modelo de mensagem aprovado pela Meta, que ela pode pausar ou rejeitar a qualquer momento.
- **Janela de 24h:** depois que o cliente responde, abre-se uma janela de 24h para mensagens livres (inclusive automatizadas). Fora dela, só templates.
- **Chatbot:** permitido dentro da janela, desde que exista escalonamento claro para um humano (atendente, telefone, e-mail, formulário etc.).
- **Cobrança:** por mensagem/template, conforme a tabela de preços da Meta.
- **Perfil comercial:** precisa ter contato de suporte e não pode se passar por outra empresa.

## 3. Limites de envio (por portfólio comercial, a cada 24h móveis, para números únicos fora da janela)
| Nível | Como chegar |
|---|---|
| 250 | conta nova |
| 2.000 | verificar a empresa no Meta Business **ou** enviar 2.000 mensagens com template de boa qualidade em 30 dias |
| 10.000 → 100.000 → ilimitado | automático: boa qualidade + uso de ≥50% do limite nos últimos 7 dias (sobe em até 6h) |

- **Qualidade:** bloqueios e denúncias derrubam a nota e podem *reduzir* os limites ou suspender a conta.

## 4. Restrições de conteúdo relevantes
- **Imóveis não estão na lista proibida**, então o caso do mercado imobiliário é permitido.
- **Proibidos:** empréstimos (payday, P2P), cobrança de dívidas, marketing multinível, apostas (exceto em alguns países), álcool/tabaco, uso político, entre outros.
- **Dados sensíveis:** não pedir número completo de cartão, conta bancária ou documento de identidade pelo chat.
- **Privacidade:** não repassar informações da conversa de um cliente para outro cliente.

## 5. Boas práticas de opt-in (recomendadas pela Meta)
- Fazer o opt-in **por categoria de mensagem** (lançamentos, ofertas, atualizações).
- Deixar claro como sair de cada categoria.
- Mostrar o valor de receber as mensagens e manter os fluxos de entrada e saída simples.

## Conclusão para o projeto
Um disparador **sustentável e legal** só pode ser construído sobre a **API oficial (Cloud API)**:
- base com opt-in registrado e gestão de descadastro;
- templates aprovados;
- respeito aos limites por nível;
- monitoramento da qualidade da conta.

Disparar pelo WhatsApp comum ou com ferramentas não oficiais significa banimento quase certo e risco jurídico.
