# credenciamento.ind.br
Sistema de Credenciamento

# Atores
- Administrador: pessoa usuária do sistema - nível de acesso 3
- Operador: pessoa usuária do sistema - nível de acesso 2
- Recepcionista: pessoa usuária do sistema - nível de acesso 1
- Pessoa: pessoas física registrada sob um EMAIL único (chave primária) - nível de acesso 0
- Organização: pessoa jurídica registrada sob um CNPJ único (chave primária)

# REQUISITOS FUNCIONAIS :: Admin
- [ ] Deve ser possível fazer login com email e senha
- [ ] Deve ser possível cadastrar administradores
- [ ] Deve ser possível cadastrar equipe de apoio
- [ ] Deve ser possível recuperar senha esquecida
- [ ] Deve ser possível alterar sua própria senha

# REQUISITOS FUNCIONAIS :: Admin :: Organizações
- [ ] Deve ser possível listar as organizações cadastradas
- [ ] Deve ser possível buscar uma organização pelo nome
- [ ] Deve ser possível filtrar por Empresas Privadas
- [ ] Deve ser possível filtrar por Parceiros e Governo
- [ ] Deve ser possível filtrar por Sistema Indústria
- [ ] Deve ser possível cadastrar uma organização
- [ ] Deve ser possível editar os dados de uma organização
- [ ] Deve ser possível remover uma organização

# REQUISITOS FUNCIONAIS :: Admin :: Pessoas
- [ ] Deve ser possível listar as pessoas cadastradas
- [ ] Deve ser possível buscar uma pessoa pelo nome
- [ ] Deve ser possível filtrar pessoas sem foto
- [ ] Deve ser possível filtrar apenas CEOs
- [ ] Deve ser possível cadastrar uma pessoa
- [ ] Deve ser possível editar os dados de uma pessoa
- [ ] Deve ser possível remover uma pessoa

# REQUISITOS FUNCIONAIS :: Admin :: Eventos
- [ ] Deve ser possível listar os eventos
- [ ] Deve ser possível criar eventos
- [ ] Deve ser possível editar dados de um evento
- [ ] Deve ser possível vincular as pessoas recepcionistas ao evento

# REQUISITOS FUNCIONAIS :: Admin :: Relatórios
- [ ] Gerar relatório de confirmados por evento
- [ ] Gerar relatório do histórico de participação da pessoa
- [ ] Gerar relatório completo por evento

# REQUISITOS FUNCIONAIS :: Recepção
- [ ] Deve ser possível visualizar a lista total de pessoas
- [ ] Deve ser possível visualizar a lista apenas de confirmados
- [ ] Deve ser possível importar XLSX (do CRM) com a lista completa de confirmados
- [ ] Deve ser possível buscar uma pessoa pelo nome
- [ ] Deve ser possível adicionar na lista um convidado não confirmado previamente
- [ ] Deve ser possível registrar a chegada de um convidado
- [ ] Deve ser possível desfazer o registro de chegada de um convidado

# REQUISITOS FUNCIONAIS :: Mapa de Assentos
- [ ] Deve ser possível mover convidados da lista para um assento
- [ ] Deve ser possível mover convidados entre assentos
- [ ] NÃO deve ser possível mover convidados para assentos já ocupados
- [ ] Deve ser possível remover convidados do assento para a lista
- [ ] Deve ser possível exibir a ficha de resumo do convidado ao clicar sobre o nome


#
# REGRAS DE NEGÓCIO

- [ ] Toda pessoa cadastrada deve ter um email válido e único
- [ ] Toda organização cadastrada ter um CNPJ válido e único
- [ ] Não pode ser possível cadastrar duas pessoas com um mesmo email
- [ ] Não pode ser possível cadastrar duas organizações com um mesmo cnpj
- [ ] Toda pessoa deve estar vinculada a uma organização
- [ ] A importação da lista de confirmados sobrescreve a lista atual
- [ ] A importação da lista de confirmados mantém os assentos já definidos
- [ ] Eventos poderão ocorrer em mesma data e horário

# REQUISITOS NÃO FUNCIONAIS

- [ ] A senha do usuário precisa estar criptografada
- [ ] Os dados do sistema precisam estar persistidos em um banco de dados postgres
- [ ] Todas as listas de dados precisam estar paginadas com 20 itens por páginas
- [ ] O usuário deve ser identificado por um JWT (JSON Web Token)
- [ ] As fotos das pessoas devem ser carregadas automaticamente do Linkedin

# NÍVEIS DE ACESSO

- [ ] Usuários de nível 3 podem cadastrar usuários de todos os níveis
- [ ] Usuários de nivel 3 devem ter acesso às recepções de todos os eventos
- [ ] Usuários de nivel 3 devem ter acesso mapas de todos os eventos

- [ ] Usuários de nível 2 podem cadastrar apenas usuários de nível 1
- [ ] Usuários de nivel 2 devem ter acesso às recepções de todos os eventos
- [ ] Usuários de nivel 2 devem ter acesso mapas de todos os eventos

- [ ] Usuários de nível 1 não podem ter acesso ao sistema administrativo
- [ ] Usuários de nível 1 devem acessar apenas recepções dos eventos que foram vinculados
- [ ] Usuários de nivel 1 devem acessar apenas mapas dos eventos que foram vinculadas