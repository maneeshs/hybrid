---

copyright:
  years: 2017
lastupdated: "2017-05-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}


# Relatório Detalhes por Tipo

## Logins de firewall
{: #firewalllogins}

Relata eventos relacionados ao login do administrador para os dispositivos de firewall Vyatta.

### Campos de Dados

<dl>
<dt>Hora de Origem de Log</dt>
<dd>A data na qual o evento ocorreu.</dd>
<dt>Nome do Evento</dt>
<dd>Tipo de evento (O usuário falhou ao efetuar login via SSH - senha incorreta,
Falha de autenticação, Sessão encerrada, Senha aceita para o usuário, Sessão aberta
para o usuário).</dd>
<dt>Categoria de Baixo Nível</dt>
<dd>Detalhes do evento (Login SSH com falha, Sessão encerrada, Login do host
bem-sucedido, Sessão aberta).</dd>
<dt>Username</dt> 
<dd>A credencial (nome do usuário) do usuário que iniciou a sessão.</dd>
<dt>IP de Origem</dt>
<dd>O endereço IP do qual o usuário inicia a sessão.
<dt>IP de Destino</dt>
<dd>O destino da sessão.</dd>
<dt>Origem de Log</dt>
<dd>A origem do Evento (o nome do host do Firewall que gerou o
evento).</dd>
</dl>

## Negações de firewall
{: #firewalldenies}

Relata eventos gerados por dispositivos de firewall Vyatta quando uma solicitação para acesso é negada devido às regras de firewall em vigor.
  
### Campos de Dados

<dl>
<dt>Hora de Origem de Log</dt>
<dd>A data e hora em que o evento ocorreu.</dd>
<dt>Nome do Evento</dt>
<dd>Tipo de evento (O usuário falhou ao efetuar login via SSH - senha incorreta,
Falha de autenticação, Sessão encerrada, Senha aceita para o usuário, Sessão aberta
para o usuário).</dd>
<dt>Categoria de Baixo Nível</dt>
<dd>Detalhes do firewall nega evento</dd>
<dt>IP de Origem</dt> 
<dd>O endereço IP de origem do qual a conexão de rede e/ou ataque
inicia.</dd>
<dt>Porta de origem</dt>
<dd>A porta de destino do protocolo.
<dt>IP de Destino</dt>
<dd>O destino da sessão.</dd>
<dt>Porta de Destino</dt>
<dd>A porta de destino do protocolo.</dd>
<dt>Protocol</dt>
<dd>O protocolo de comunicação (tcp/udp).
<dt>Origem de Log</dt>
<dd>A origem do Evento (nome do host do Firewall que gerou o evento).</dd>
<dt>Contagem de Eventos</dt>
<dd>O número de eventos desse tipo.</dd>
</dl>

## Logins do Sistema Operacional
{: #oslogin}

Relata eventos gerados pelo sistema operacional quando um administrador inicia uma sessão SSH em um sistema Bluemix.

### Campos de Dados

<dl>
<dt>Hora de Origem de Log</dt>
<dd>A data na qual o evento ocorreu.</dd>
<dt>Nome do Evento</dt>
<dd>Tipo de evento (autenticação de espaço do usuário, falha de autenticação de espaço do usuário)/dd>
<dt>Username</dt> 
<dd>O nome de usuário do usuário que iniciou o processo de autenticação.</dd>
<dt>Endereço de origem</dt>
<dd>O endereço IP do qual o usuário inicia a sessão.
<dt>IP de Destino</dt>
<dd>O destino da sessão.</dd>
<dt>Origem de Log</dt>
<dd>A origem do Evento (o nome do host do servidor no qual o evento foi gerado).</dd>
</dl>

## Logins do Servidor de Login 
{: #loginserverlogins}

Relata eventos gerados pelo componente de login da plataforma Bluemix quando um usuário da plataforma Bluemix inicia uma sessão usando a linha de comandos, as APIs de REST ou o console do Bluemix.

### Campos de Dados

<dl>
<dt>Hora de Origem de Log</dt>
<dd>A data em que o evento ocorreu.</dd>
<dt>Nome do Evento</dt>
<dd>Tipo de evento (Autenticação de espaço do usuário, Autenticação de espaço do usuário com falha)/dd>
<dt>Usuário</dt> 
<dd>O ID de usuário do usuário que iniciou o processo de autenticação.</dd>
<dt>Bluemix_Platform_Component</dt>
<dd>O componente que gerou o evento (login_server).
<dt>Tipo de Mensagem</dt>
<dd>O tipo de operação (login, logout).</dd>
<dt>Barra de Status</dt>
<dd>O resultado da operação (sucesso/falha).</dd>
<dt>Origem de Log</dt>
<dd>A origem do evento.</dd>
</dl>

## Administração de banco de dados
{: #dbadmin}

Relata eventos relacionados a operações executadas por um administrador de banco de dados nos bancos de dados internos do Bluemix.

### Campos de Dados

<dl>
<dt>Hora de Origem de Log</dt>
<dd>A data em que o evento ocorreu.</dd>
<dt>Event_Type</dt>
<dd>Tipo de Evento (SECURITY_RUNTIME).
<dt>Usuário</dt> 
<dd>O nome de usuário do usuário que executou a operação. Os usuários a seguir são os usuários definidos para o banco de dados.
<ul>
<li>UAADB: vcap, raiz, backup_user.
<li>CCDB: vcap, ccadmin, backup_user.
<li>O uso fora do acima precisará de investigação sobre quem fez a operação. Isso pode ser feito usando o Relatório de segurança de administração do sistema operacional e o Relatório de segurança de login do sistema operacional.</ul>
</dd>
<dt>Origem</dt> 
<dd>O endereço IP do qual o usuário inicia o comando. Os valores esperados são os seguintes:
<ul>
<li>UAADB – VMs uaa e a VM nfs_WAL_server.
<li>CCDB – VMs api_worker, clock_global,cloud_controller_ng e nsf_WAL_server.
</ul>
</dd>
<dt>DB_Statement</dt>
<dd>Tipo de operação (todas as instruções de definição de dados, como instruções CREATE, ALTER e DROP, além de instruções de modificação de dados, como INSERT, UPDATE, DELETE, TRUNCATE e COPY FROM)</dd>
<dt>DB_Name</dt>
<dd>Nome do BD no qual a operação foi executada</dd>
</dl>

## Gerenciamento de usuário do console do administrador
{: #acusermgmt}

Relata atividades de gerenciamento de usuários executadas no console de administração do Bluemix.

### Campos de Dados

<dl>
<dt>Hora de Origem de Log</dt>
<dd>A data em que o evento ocorreu.</dd>
<dt>Event_Type</dt>
<dd>Tipo de Evento (SECURITY_RUNTIME).
<ul>
<li>SECURITY_MGMT_REGISTRY: Incluir Usuário [ ID do usuário ]
<li>SECURITY_MGMT_REGISTRY: Excluir Usuário [ ID do usuário ]
<li>SECURITY_AUTHN_CREDS_MODIFY: incluir permissão [permissions] para usuários [user ID].
<li>SECURITY_AUTHN_CREDS_MODIFY: remover permissão [permissions] de usuários [user ID].
<li>SECURITY_MGMT_CONFIG: Criar organização [ name ].
<li>SECURITY_MGMT_CONFIG: Alterar gerenciadores de organização, [ ids ].
<li>SECURITY_MGMT_CONFIG: renomear o ID da organização [id] para o novo nome [name].
<li>SECURITY_MGMT_CONFIG: Excluir organização id [ id ].
<li>SECURITY_MGMT_CONFIG: atualizar cota para organização [id] para a cota [quotaPlan].
</ul>
</dd>
<dt>Usuário</dt> 
<dd>O usuário que iniciou a operação (LDAP id).
<dt>Mensagem</dt> 
<dd>Comando executado.
<ul>
<li>Incluir usuário [user ID]: Adds a user with the specified ID.
<li>Excluir usuário [user ID]: Deletes a user with the specified ID.
<li>Incluir permissão [ Permissões ] para usuários [user ID]: Adds permissions to the specified users. Permissions can include:
ops.admin, ops.login, ops.reports.read, ops.reports.write, ops.catalog.read, ops.catalog.write, ops.users.read e ops.user.write.
<li>Remover permissão [ Permissões ] de usuários [user ID]: Remove permission - Remove permissions from the specified users. Permissions can include: ops.admin, ops.login, ops.reports.read, ops.reports.write, ops.catalog.read, ops.catalog.write, ops.users.read, and ops.users.write.
<li>Criar organização [name]: Creates an organization with the specified name.
<li>Alterar Gerenciadores de organização [ids]: Configures the managers of an organization to be the specified users.
<li>Renomear ID da organização [id] para o novo nome [name]: Renames the specified organization.
<li>Excluir usuário [user ID]: Deletes a user with the specified ID.
<li>Excluir ID da organização [id]: Deletes the specified organization.
<li>Atualizar cota para a organização [id] para a cota [quotaPlan]: Updates the quota plan for the specified organization. Plans can include: q2GB, q4GB, q8GB, q16GB, q32GB, q64GB, q128GB, q256GB, q512GB.
</ul>
</dd>
<dt>Origem de Log</dt>
<dd>A origem do evento (o endereço IP/nome do host do servidor que gerou o evento)</dd>
</dl>

## Gerenciamento do catálogo
{: #catalogmgmt}

Relata eventos relacionados às atividades de gerenciamento de catálogo de serviços executadas no console de administração do Bluemix. 

### Campos de Dados

<dl>
<dt>Hora de Origem de Log</dt>
<dd>A data em que o evento ocorreu.</dd>
<dt>SECURITY_MGMT_CONFIG</dt>
<dd>Registrar modelo [ id ]. Permite que um Modelo ou Tempo de execução com o ID especificado apareça como uma opção no Catálogo para todos os usuários.</dd>
<dd>Remover modelo [ id ]. Faz com que o Modelo ou Tempo de execução não apareça mais como uma opção no Catálogo para todos os usuários.</dd>
<dd>Atualizar plano de serviço [id] para público = [ public ] com visibilidades = [ ids ]. Atualiza a visibilidade do plano de serviço especificado. Se public for configurado como true, o plano ficará visível para todas as organizações. Se public for configurado como false, um conjunto de IDs da organização poderá ser fornecido para indicar quais organizações têm visibilidade para esse plano de serviço.</dd>
<dd>Inclua Service Broker [ name ]. Inclui um Broker de Serviço com o nome especificado.</dd>
<dd>BrokerNível Excluir [ name ]. Exclui o broker de serviço com o nome especificado.</dd>
<dd>Atualize o buildpack [ id ]. Atualiza a ordenação de buildpack para o buildpack com o ID especificado.</dd>
<dt>Origem de Log</dt>
<dd>A origem do Evento (o endereço IP/nome do host do Servidor que gerou o evento)</dd>
</dl>

## Gerenciamento de Relatórios de Segurança
{: #securityreportsmgmt}

Relata eventos relacionados às atividades de gerenciamento de relatórios de segurança executadas no console de administração.

### Campos de Dados

<dl>
<dt>Hora de Origem de Log</dt>
<dd>A data em que o evento ocorreu.</dd>
<dd>Tipo de Evento (SECURITY_RUNTIME).
<ul>
<li>SECURITY_DATA_SYNC: fazer upload do relatório [name] para a categoria [name] data [date].
Excluir Relatório com ID [ id ]
<li>SECURITY_RESOURCE_ACCESS: Fazer Download de Relatório [ Nome ].
</ul>
</dd>
<dt>Usuário</dt> 
<dd>O usuário que iniciou a operação.
<dt>Mensagem</dt> 
<dd>Comando executado.
<ul>
<li>Fazer upload do relatório [name] para a categoria [name] data [date]: Upload - Upload a report with the specified file name and date to the specified category. 
<li>Excluir Relatório com ID [id]: Delete - Delete a report with the specified id.
<li>Fazer Download de Relatório [name]: Download - A report was downloaded with the specified name.
</ul>
</dd>
<dt>Origem de Log</dt>
<dd>A origem do Evento (o endereço IP/nome do host do Servidor que gerou o evento)</dd>
</dl>

## Revisões de acesso
{: #accessreviews}

Relata as solicitações para acessos privilegiados ao ambiente Bluemix e seu processamento por administradores do Bluemix. 

### Campos de Dados

<dl>
<dt>Action_name</dt>
<dd>Indica a solicitação de um usuário para fazer de um grupo, para renomear o ID do usuário, para ser revogado em caso de descarte, para ser removido de um grupo (Incluir, Renomear, Revogar, Excluir).</dd>
<dt>Barra de Status</dt>
<dd>Este campo indica o status da solicitação. O aprovador aceita a solicitação ou rejeita isso. O pedido está aguardando aprovação. O usuário cancela a solicitação (Aceito, Rejeitado, Pendente, Cancelado).</dd>
<dt>Id_User</dt>
<dd>Username</dd>
<dt>User_name</dt> 
<dd>Este campo que faz a solicitação. </dd>
<dt>Manager_Approval</dt>
<dd>A data em que a solicitação foi aprovada pelo gerenciador
<dt>Access_Approval</dt>
<dd>A data em que a solicitação foi aprovada pelo Gerenciador de grupo.</dd>
</dl>

## Gerenciamento de Chaves
{: #keymgmt}

Relatórios Key Certificate Management operações.

### Campos de Dados

<dl>
<dt>Hora de Origem de Log</dt>
<dd>A data em que o evento ocorreu.</dd>
<dt>Event_Name</dt>
<dd>O tipo de Evento (Criando chave, Criando certificado, Excluindo certificado).</dd>
<dt>Nome da Chave / Certificado</dt>
<dd>O nome do certificado ou nome da chave utilizado.</dd>
<dt>Key_Mgmt_Message</dt> 
<dd>Comando executado (Criando chave "nome da chave", Criando certificado "nome do certificado", Configuração do certificado "nome do certificado" excluída).</dd>
<dt>IP de Destino</dt>
<dd>O destino da sessão.
<dt>Origem de Log</dt>
<dd>A origem do evento.</dd>
</dl>

## Notificações do Sistema
{: #systemnotifications}

Relata eventos relacionados à configuração das janelas de implementação de atualização de software ou assinaturas de notificação.

### Campos de Dados

<dl>
<dt>Hora de Origem de Log</dt>
<dd>A data em que o evento ocorreu.</dd>
<dt>Event_Type</dt>
<dd>Tipo de Evento (SECURITY_RUNTIME).
<ul>
<li> SECURITY_MGMT_CONFIG: criar janela [id].
<li> SECURITY_MGMT_CONFIG: Atualizar Janela [ id ].
<li> SECURITY_MGMT_CONFIG: Excluir Janela [ id ].
<li> SECURITY_MGMT_CONFIG: Criar Assinatura [ id ].
<li> SECURITY_MGMT_CONFIG: Atualizar Assinatura [ id ].
<li> SECURITY_MGMT_CONFIG: Excluir Susbscription [ id ].
<li> SECURITY_MGMT_CONFIG: Criar Tópico de Resposta [ id ].
</ul>
</dd>
<dt>Usuário</dt> 
<dd>O usuário que iniciou a operação
<dt>Mensagem</dt>
<dd>Comando executado.
<ul>
<li>Criar janela [id]: Creates "creating" as janelas de atualização para um ambiente. As janelas de atualização são as janelas de blecaute e preferenciais para implementações. Isso é quando os clientes estão permitindo/não permitindo que implementações sem interrupção sejam implementadas sem precisar aprovar e planejá-las.<li>Janela de atualização [id]: Updates a maintenance update window. This event is generated when a user is updating the maintenance update windows for an environment.
<li>SECURITY_MGMT_CONFIG: excluir janela de atualização. Este evento é gerado quando um usuário delega as janelas de atualização para um ambiente.
<li>Criar Assinatura [id]: Creates an event subscription. The event subscription audit logs are generated when a user creates a subscription for either update or incident events. This will allow them to be notified when something is going on in their system..
<li>Atualizar Assinatura [id]: Updates an event subscription. The event is generated when a user updates a subscription for either update or incident events.
<li>Excluir Assinatura [id]: Delete Event Subscription. This event is generated when a user deletes a subscription for either update or incident events.
<li>Criar resposta de tópico [id]: Reply to a Topic The topic reply audit log is generated when the customer approves and schedules disruptive update..
</ul>
</dd>
<dt>Origem de Log</dt>
<dd>A origem do Evento (o endereço IP/nome do host do Servidor que gerou o evento).</dd>
</dl>

## Administração da plataforma Bluemix
{: #platformadmin}

Relata eventos relacionados à plataforma Bluemix usando a linha de comandos, as APIs REST ou a interface com o usuário do Bluemix.

### Campos de Dados

<dl>
<dt>Hora de Origem de Log</dt>
<dd>A data na qual o evento ocorreu.</dd>
<dt>Event_Type</dt>
<dd>Tipo de Evento (SECURITY_RUNTIME).
<ul>
<li>SECURITY_AUTH_CREDS_MODIFY: eventos relacionados à modificação de credenciais para uma determinada identidade do usuário.
<li>SECURITY_MGMT_RESOURCE: eventos de gerenciamento de recurso, como criação, exclusão e mudanças nos atributos de um
recurso.
<li>SECURITY_MGMT_POLICY: evento relacionado ao gerenciamento de políticas de segurança, como criação de listas de controle de acesso.
<li>SECURITY_RUNTIME: eventos de tempo de execução, como início e parada de servidores de segurança.
<li>SECURITY_RESOURCE_ACCESS: eventos que registram todos os acessos a um recurso. Exemplos são todos os acessos a um arquivo, todas as solicitações/respostas de HTTP para uma determinada página da web e todos os acessos a uma tabela de banco de dados crítica.</ul>
</dd>
<dt>Usuário</dt> 
<dd>Quem começou a operação
<dt>Destino</dt> 
<dd>Detalhes da operação executada, como o ID da entidade e resultados da operação. Exemplos:
<ul>
<li>UserCreatedEvent ('[ "user_id=ca3a811f-1778-4103-9553-537788ed4c4e", "username=equaranta" ]'). O usuário foi criado com
(username=equaranta and id = ca3a811f-1778-4103-9553-537788ed4c4e).
<li>GroupModifiedEvent ('{0}{6}{2}{5}ff9a-8a59-4cca-a80a-8e3b51f3dd21 "," 5005f0f8-e090-4cabb51d-2ceee70acf0e " } '). O grupo com nome ops.reports.read foi modificado, com associação resultante (id 0625ff9a- 8a59-4ccaa80a- 8e3b51f3dd21","5005f0f8- e090-4cab-b51d- 2ceee70acf0e).
<li>UserDeletedEvent ('[ "UserDeletedEvent (' [" user_id=5cd5f412-4bbb-4c44-b44b, 713a5bc6144d "," username=818811853 "] '):" ]'. O usuário foi excluído com id value=5cd5f412-4bbb- 4c44-b44b-713a5bc6144.
</ul>
</dd>
<dt>Mensagem</dt>
<dd>A entidade em que a operação foi executada (sequência msg) ou o código de retorno HTTP padrão da operação (valor numérico). </dd>
<dt>Bluemix_Platform_Component</dt>
<dd>Nome do componente.</dd>
<dt>Origem de Log</dt>
<dd>Nome do host/endereço IP da origem do evento.</dd>
<dt>Origem</dt>
<dd>A origem do evento e exemplo é o Endereço IP.</dd>
<dt>Data</dt>
<dd>Detalhes adicionais.</dd>
</dl>

## Administração do Sistema Operacional
{: #osadmin}

Relata eventos gerados pelo Bluemix que podem ajudar a diagnosticar falhas (por exemplo, um agente Bosh que falha ao implementar ou um serviço que não está iniciando).

### Campos de Dados

<dl>
<dt>Hora de Origem de Log</dt>
<dd>A data em que o evento ocorreu.</dd>
<dt>Event_Name</dt>
<dd>O tipo de Evento (Criando chave, Criando certificado, Excluindo certificado).</dd>
<dt>BMX_key</dt>
<dd>Tipo de operação (BMX_executed_command, BMX_access_unauthorized, BMX_unsuccessful_delete, BMX_sudoers_folder, BMX_Identity_shadow, BMX_extended_attribute, BMX_sudoers).</dd>
<dt>auid</dt> 
<dd>O ID do usuário de origem do usuário que está com login efetuado (por exemplo, auid=0 é root, auid=1000 é vcap, auid= 55044 é um usuário LDAP).</dd>
<dt>Uid</dt>
<dd>O ID do usuário de destino com o qual o comando é executado (por exemplo, auid=55044 está com login efetuado e executa um “sudo su” (raiz) -> uid=0 antes de executar o comando).
<dt>Exe_key</dt>
<dd>O comando executado.</dd>
<dt>IP de Origem</dt>
<dd>O endereço IP do qual o usuário inicia o comando. </dd>
<dt>Origem de Log</dt>
<dd>A origem do evento.</dd>
</dl>
