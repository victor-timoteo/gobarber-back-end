# Recuperação de senha

**RF**
  REQUESITOS FUNCIONAIS

- O usuário deve poder recuperar sua senha informando o seu e-mail;

- O usuário deve receber um e-mail com instruções de recuperação de senha;

- O usuário deve poder resetar sua senha;

**RNF**

  REQUESITOS NÃO FUNCIONAIS

- Utilizar Mailtrap para testar envios de e-mail em ambiente de desenvolvimento;
- Utilizar Amazon SES para envios em produção;
- O envio de e-mails deve acontecer em segundo plano (background job);

**RN**

  REGRA DE NEGOCIO

- O link enviado por email para resetar senha deve expirar em 2h;

- O usuário precisa confirmar a nova senha ao recuperar sua senha;

# Atualização do perfil

**RF**
  REQUESITOS FUNCIONAIS

  - O usuário deve poder atualizar seu nome, email e senha;

**RN**
  REGRA DE NEGOCIO

  - O usuário não pode alterar seu email para um email já utilizado;

  - Para atualizar sua senha, o usuário deve informar sua senha antiga;

  - Para atualizar sua senha, o usuário precisa confirmar sua nova senha;

# Painel do Prestador

**RF**
  REQUESITOS FUNCIONAIS

- O usuário deve poder
- O prestador deve receber uma notificação sempre que houver um novo agendamento;
- O prestador deve poder visualizar as notificações não lidas;

**RNF**
  REQUESITOS NÃO FUNCIONAIS

  - Os agendamento do prestador no dia devem ser armazenados em cache;
  - As notificações do prestador devem ser armazenadas no MongoDB;
  - As notificações do prestador devem ser enviadas em tempo-real utilizando Socket.io;

**RN**
  REGRA DE NEGOCIO

  - A notificação deve ter um status de lida ou não-lida para que o prestador possa controlar;

# Agendamento de serviços

**RF**
  REQUESITOS FUNCIONAIS

- O usuário deve poder listar todos prestadores cadastrado;

- O usuário deve poder listar os dias de uma mês com pelo menos um horário disponível de um prestador;

- O usuário deve poder listar horários disponível em um dia específico de um prestador;
- O usuário deve poder realizar um novo agendamento com um prestador;

**RNF**
    REQUESITOS NÃO FUNCIONAIS

- A listagem de prestadores deve ser armazenado em cache;

**RN**
  REGRA DE NEGOCIO

- Cada agendamento deve durar 1h exatamente;
- Os agendamentos devem estar disponível entre 8h ás 18h (Primeiro horário 8h, último horário ás 17h);
- O usuário não pode agendar em um horário já ocupado;
- O usuário não pode agendar em um horário que já passou;
-O usuário não pode agendar serviços consigo mesmo;
