# 🛠️ Especificação Técnica (Tech Spec) - ArenaRank

Este documento detalha arquitetura técnica, o modelo de dados e os contratos de API (via JSON Server) necessárias para o funcionamento da plataforma de torneios e-sports amadores ArenaRank.

## 1. Modelo de Dados (Diagrama ER)

Abaixo está o Diagrama Entidade-Relacionamento (DER) que representa a estrutura do nosso "banco de dados" (`db.json`) e como as informações se conectam.

```mermaid
erDiagram
Usuário ||--o{ Torneio : "se inscreve no torneio"
Usuário ||--o{ Moderador : "cria o torneio"
Usuário {
string id PK "Gerado automaticamente"
string nome
string usuário "Usado para o login"
string senha
string equipe "Se registra/cria"
string torneio "Se registra/cria"
}
Torneio {
string id PK
string equipe "Nome da equipe"
string jogo
string horário "Hora do começo/fim do torneio"
string posição "Colocação da equipe nas chaves"
}
Moderador {
string id PK
string equipes
string chaves "Tipos de chaves do sistema para o jogo escolhido"
string descrição
string regulamento
}

