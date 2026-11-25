<div align="center">

![MARFIM](assets/capa.png)

**Um assistente que atende pacientes de clínicas odontológicas pelo WhatsApp.**

![Status](https://img.shields.io/badge/status-pr%C3%A9--lan%C3%A7amento-0B1220?style=for-the-badge&logo=rocket&logoColor=3B82F6)
![Python](https://img.shields.io/badge/Python-0B1220?style=for-the-badge&logo=python&logoColor=3B82F6)
![FastAPI](https://img.shields.io/badge/FastAPI-0B1220?style=for-the-badge&logo=fastapi&logoColor=3B82F6)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-0B1220?style=for-the-badge&logo=postgresql&logoColor=3B82F6)
![Redis](https://img.shields.io/badge/Redis-0B1220?style=for-the-badge&logo=redis&logoColor=3B82F6)
![n8n](https://img.shields.io/badge/n8n-0B1220?style=for-the-badge&logo=n8n&logoColor=3B82F6)
![Docker](https://img.shields.io/badge/Docker-0B1220?style=for-the-badge&logo=docker&logoColor=3B82F6)

</div>

O MARFIM (antes chamado Nexus) é um SaaS em pré-lançamento: um assistente virtual que responde os pacientes no WhatsApp e entrega à clínica um painel com agenda, pacientes e conversas. Ainda não tem clientes.

> O código é privado. Esta página mostra o que foi construído e qual foi o meu papel, só com o que consigo comprovar. As telas abaixo usam dados fictícios.

## O problema e a ideia

Clínica pequena responde WhatsApp à mão, entre um atendimento e outro, e à noite a mensagem fica sem resposta. O paciente que não é respondido a tempo marca em outro lugar.

A ideia: o assistente responde na hora, ajuda a marcar a consulta e só chama uma pessoa quando o caso pede (urgência, dúvida que ele não entendeu, pedido de falar com a equipe).

## Valor para o negócio

- **Menos mensagem perdida.** Quem escreve fora do horário recebe resposta.
- **Agenda organizada.** As consultas marcadas pelo assistente caem direto na agenda da clínica.
- **Equipe focada.** A tela "Hoje" mostra só o que precisa de gente, com o que é urgente primeiro.
- **Cada clínica enxerga só os próprios dados.**

## Telas

<table>
  <tr>
    <td align="center"><img src="assets/hoje.png" width="420" alt="Tela Hoje"><br><b>Hoje</b><br>O que precisa de atenção agora</td>
    <td align="center"><img src="assets/conversas.png" width="420" alt="Tela Conversas"><br><b>Conversas</b><br>Atendimentos do assistente, urgentes primeiro</td>
  </tr>
  <tr>
    <td align="center"><img src="assets/clinica.png" width="420" alt="Tela Clínica"><br><b>Clínica</b><br>Profissionais, consultas e horários</td>
    <td align="center"><img src="assets/equipe.png" width="420" alt="Tela Equipe"><br><b>Equipe</b><br>Cada pessoa vê só a agenda do seu profissional</td>
  </tr>
</table>

O painel também tem as telas Agenda e Pacientes.

## Como funciona

```mermaid
flowchart LR
    P([Paciente escreve no WhatsApp]) --> A[Assistente responde]
    A -->|quer marcar consulta| G[(Agenda da clínica)]
    A -->|caso urgente ou dúvida| E([Equipe da clínica assume])
    G --> E
```

## O que eu fiz neste projeto

- Levantei os requisitos e as regras de negócio com quem conhece a rotina da clínica.
- Desenhei os dados: pacientes, agenda, conversas, profissionais e permissões.
- Defini os critérios de aceite de cada funcionalidade.
- Orientei e revisei o trabalho da IA, que escreveu boa parte do código.

Sou co-fundador e construí todo o sistema, com apoio de IA generativa. Os outros três sócios cuidam de marketing, odontologia e vendas.

> Boa parte do código foi construída com apoio de IA generativa, e os testes automáticos também; eu defino o que o sistema precisa fazer e reviso o resultado.

## O que está provado e o que ainda não

| Provado | Ainda não provado |
|---|---|
| Cerca de 1.980 testes automáticos passando a cada alteração (gerados com apoio de IA e revisados por mim) | Clínica usando de verdade |
| Fluxo de atendimento validado em 41 cenários simulados | Uso real com WhatsApp, n8n e provedor de IA |
| Cada clínica enxerga só os próprios dados | Servidor e domínio contratados |
| Consentimento, histórico de alterações e exclusão de dados de paciente implementados | Revisão jurídica e termo de piloto |
| Uma falha de acesso entre profissionais foi encontrada e corrigida | Dois pontos de risco médio ainda abertos e documentados |
| Site de apresentação com 11 seções | Backup testado no servidor |

## Stack

Python, FastAPI, PostgreSQL, Redis, n8n e Docker. Verificações automáticas rodam a cada alteração no GitHub Actions.

## Estado atual

1. Pré-lançamento interno, sem clientes e sem piloto real.
2. Tudo foi simulado e testado, mas ainda não rodou com pacientes de verdade.
3. Versões `v0.1.0` e `v0.1.1` marcadas no repositório privado.
4. Falta: corrigir os dois riscos médios, contratar servidor e domínio, passar por revisão jurídica e fazer o primeiro piloto com uma clínica.

## Autor

Gabriel Nagatani Campos, estudante de Engenharia de Software (UMC). [Portfólio](https://gabrielnagatanicampos.github.io)
