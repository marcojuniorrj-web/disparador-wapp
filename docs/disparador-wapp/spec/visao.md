# Visão
## Objetivo da aplicação
Disparar mensagens de WhatsApp, de forma recorrente e dentro das regras da Meta, para a base de
corretores cadastrados na Unnità Inteligência Imobiliária. Os usos são recrutamento, lançamentos,
treinamentos e avisos. O envio é feito pela API oficial (WhatsApp Cloud API).

## Problema que resolve (hoje, sem o app)
Hoje o contato com os ~300 corretores é feito um a um no WhatsApp. Isso toma horas do gestor,
muita gente fica sem contato e não há registro de quem recebeu, leu ou respondeu.

## Métricas de sucesso
- **Taxa de resposta:** % de corretores que respondem a cada disparo.
- **Tempo economizado:** um disparo para a base inteira em minutos, em vez de horas de envio manual.

## Escopo do MVP
- Importar a lista de corretores (planilha CSV/Excel) com nome, telefone e o registro do opt-in.
- Escolher um template aprovado na Meta e preencher as variáveis (ex.: {{nome}}).
- Disparar para a lista inteira, respeitando o limite diário da conta.
- Ver o status de cada envio: enviado, entregue, lido, respondeu ou falhou.
- Descadastro: quem pedir para sair (botão "Não quero receber" ou a palavra SAIR) deixa de receber.
- Guia passo a passo para configurar a conta Meta Business, o número e o token (a Unnità ainda não tem nada).

## Fica para depois
- Caixa de entrada para responder as conversas pelo app.
- Robô de triagem com respostas automáticas.
- Agendamento de disparos.
- Segmentação da lista (bairro, experiência, status).

## Fora do escopo
- Qualquer envio por WhatsApp comum ou ferramentas não oficiais (automação do WhatsApp Web etc.).
- Envio para contatos sem opt-in, compra de listas e uso por outras imobiliárias (não é produto SaaS).

## Restrições (prazo, orçamento, ferramentas, público/interno)
- **Uso interno:** um único usuário (Marco).
- **Orçamento:** custo zero de infraestrutura (hospedagem no plano gratuito da Cloudflare).
  As **mensagens são cobradas pela Meta** e esse custo não dá para evitar: cada template de
  marketing ou de utilidade enviado tem preço por mensagem. As respostas dentro da janela de 24h são gratuitas.
- **Limite de envio:** conta nova começa com 250 contatos únicos por dia. A base tem 300, então o
  primeiro disparo leva 2 dias, a menos que a empresa seja verificada na Meta (limite de 2.000).
- **Prazo:** sem prazo rígido (assumido).
