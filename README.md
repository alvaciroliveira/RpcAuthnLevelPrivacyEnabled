#  Gerenciamento da implantação de alterações de associação de Impressora RPC para CVE-2021-1678 (KB4599464)

Erro no compartilhamento de impressora do Windows baixe e execute: https://github.com/alvaciroliveira/RpcAuthnLevelPrivacyEnabled/blob/main/RpcAuthnLevelPrivacyEnabled.reg

CRÉDITOS PARA: https://support.microsoft.com/pt-br/topic/gerenciamento-da-implanta%C3%A7%C3%A3o-de-altera%C3%A7%C3%B5es-de-associa%C3%A7%C3%A3o-de-impressora-rpc-para-cve-2021-1678-kb4599464-12a69652-30b9-3d61-d9f7-7201623a8b25

Windows Server 2008 Service Pack 2 Windows Server 2008 R2 Service Pack 1 Windows Server 2012 Windows Server 2012 R2 Windows Server version 1809 Windows Server version 1903 Windows Server version 1909 Windows Server 2016, all editions Windows Server 2019 Windows Server version 2004 Windows Server version 20H2 Menos
Resumo
Existe uma vulnerabilidade de bypass de segurança na forma como a vinculação RPC (Chamada de Procedimento Remoto) lida com a autenticação para a interface Winspool remota. A atualização do Windows resolve essa vulnerabilidade aumentando o nível de autenticação de RPC e introduzindo uma nova política e chave de registro para permitir que os clientes desabilitem ou habilitem o modo de Imposição no lado do servidor para aumentar o nível de autenticação.   

Para saber mais sobre a vulnerabilidade, consulte CVE-2021-1678 | Vulnerabilidade de Falsificação de Spooler de Impressão do Windows.

#  *Tome medidas para proteger seu ambiente e evitar interrupções, você deve fazer o seguinte:*

Atualize todos os dispositivos de cliente e servidor instalando a atualização do Windows de 12 de janeiro de 2021 ou uma atualização posterior do Windows. Esteja ciente de que instalar a atualização do Windows não atenua totalmente a vulnerabilidade de segurança e pode impactar sua configuração atual de impressão. Você deve realizar a Etapa 2.

Habilite o modo de Imposição no servidor de impressão.  O modo de Imposição será habilitado em todos os dispositivos Windows no futuro.

#  Cronograma das atualizações

Essas atualizações do Windows serão lançadas em duas fases:
A fase de implantação inicial das atualizações do Windows lançadas em ou após 12 de janeiro de 2021.
A fase de imposição das atualizações do Windows será lançada no futuro.
12 de janeiro de 2021: Fase de Implantação Inicial
A fase inicial de implantação começa com a atualização do Windows lançada em 12 de janeiro de 2021, fornecendo a capacidade dos clientes do servidor de permitir esse aumento do nível de segurança por conta própria com base na prontidão de seu ambiente.

#  Esta versão:

Soluciona a CVE-2021-1678 (no modo Implantação definido como Desativado por padrão).

Adiciona suporte ao valor de registro RpcAuthnLevelPrivacyEnabled para permitir o aumento do nível de autorização para proteção IRemoteWinspool da impressora.

A mitigação consiste na instalação das atualizações do Windows em todos os dispositivos de nível do cliente e do servidor.

14 de setembro de 2021: Fase de Imposição
A versão faz a transição para a fase de imposição em 14 de setembro de 2021.  A fase Imposição impõe as alterações para solucionar o CVE-2021-1678, aumentando o nível de autorização sem ter que definir o valor do registro.

#  Orientação de instalação

Antes de instalar esta atualização
Você deve ter as seguintes atualizações necessárias instaladas antes de aplicar esta atualização. Se você usar o Windows Update, essas atualizações necessárias serão oferecidas automaticamente conforme necessário.

Você precisa ter a atualização do SHA-2 (KB4474419) de 23 de setembro de 2019 ou uma atualização do SHA-2 mais recente instalada e reiniciar o dispositivo antes de aplicar esta atualização. Para obter mais informações sobre as atualizações do SHA-2, confira o requisito de Suporte de Assinatura de Código do SHA-2 2019 para Windows e WSUS.

Para o Windows Server 2008 R2 SP1, você deve ter instalado a atualização da pilha de serviços (SSU) (KB4490628) de 12 de março de 2019. Após a instalação da atualização KB4490628, recomendamos a instalação da atualização SSU mais recente. Para obter mais informações sobre a atualização SSU mais recente, consulte ADV990001 | Atualizações mais recentes da pilha de manutenção.

Para o Windows Server 2008 SP2, você deve ter instalado a atualização da pilha de serviços (SSU) (KB4493730) de 9 de abril de 2019. Após a instalação da atualização KB4493730, recomendamos a instalação da atualização SSU mais recente. Para obter mais informações sobre as últimas atualizações SSU, confira ADV990001 | Atualizações mais recentes da pilha de manutenção.

Os clientes devem adquirir a Atualização de Segurança Estendida (ESU) para versões locais do Windows Server 2008 SP2 ou Windows Server 2008 R2 SP1 após o término do suporte estendido em 14 de janeiro de 2020. Os clientes que compraram a ESU devem seguir os procedimentos em KB4522133 para continuar recebendo atualizações de segurança. Para obter mais informações sobre a ESU e quais edições têm suporte, consulte KB4497181.

#  Importante Você deve reiniciar seu dispositivo depois de instalar essas atualizações necessárias.

Instale a atualização

Para resolver a vulnerabilidade de segurança, instale as atualizações do Windows e habilite o modo de Aplicação seguindo estas etapas:

Implante a atualização de 12 de janeiro de 2021 para todos os dispositivos de cliente e de servidor.

Depois que todos os dispositivos de cliente e servidor foram atualizados, a proteção total pode ser ativada definindo o valor do registro como 1.


#  Etapa 1: Instalar o Windows Update

Instale a atualização do Windows de 12 de janeiro de 2021 ou uma atualização posterior do Windows para todos os dispositivos de cliente e de servidor.
Atualizações de 12 de janeiro de 2021

#  Etapa 2: Habilitar o modo de imposição

Importante Esta seção, método ou tarefa contém etapas que descrevem como modificar o Registro. Entretanto, sérios problemas poderão ocorrer caso você modifique o Registro incorretamente. Portanto, siga essas etapas cuidadosamente. Para obter mais proteção, faça backup do Registro antes de modificá-lo. Dessa forma, você poderá restaurar o Registro se ocorrer um problema. Para saber mais sobre como fazer o backup e restaurar o Registro, consulte Como fazer o backup e restaurar o Registro no Windows.

Depois que todos os dispositivos de cliente e servidor tiverem sido atualizados, você pode ativar a proteção total implantando o modo de Imposição. Para fazer isso, siga estas etapas:

Clique com o botão direito em Iniciar, clique em Executar, digite cmd na caixa Executar e pressione Ctrl+Shift+Enter.

No prompt de comando do Administrador, digite regedit e pressione Enter.

Localize a seguinte subchave do Registro:

HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print

Clique com o botão direito em Imprimir, selecione Novo e depois clique em Valor DWORD (32 bits).

Digite RpcAuthnLevelPrivacyEnabled e pressione Enter.

Clique com o botão direito do mouse em RpcAuthnLevelPrivacyEnabled e clique em Modificar.

Na caixa Dados do valor, digite 1 e clique em Ok.

*Observação: Esta atualização introduz suporte para o valor de Registro RpcAuthnLevelPrivacyEnabled para aumentar o nível de autorização para o IRemoteWinspool da impressora.*

Subchave do Registro

HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\Print

Valor

RpcAuthnLevelPrivacyEnabled

Tipo de dados

REG_DWORD

#  Dados

1: habilita o Modo de Imposição. Antes de ativar o modo de Imposição do lado do servidor, certifique-se de que todos os dispositivos clientes instalaram a atualização do Windows lançada em 12 de janeiro de 2021 ou uma atualização posterior do Windows. Essa correção aumenta o nível de autorização para a interface RPC IRemoteWinspool da impressora e adiciona uma nova política e valor de registro no lado do servidor para obrigar o cliente a usar o novo nível de autorização se o modo de Imposição for aplicado. Se o dispositivo cliente não tiver a atualização de segurança de 12 de janeiro de 2021 ou uma atualização posterior do Windows aplicada, a experiência de impressão será quebrada quando o cliente se conectar ao servidor através da interface IRemoteWinspool.

0: não recomendado. Desativa o nível de autenticação de aumento para o IRemoteWinspool da impressora e seus dispositivos não estão protegidos.

#  Padrão

Comportamento padrão após a instalação de atualizações quando a chave do Registro não está definida:

As atualizações de 12 de janeiro de 2021 ou posteriores têm o comportamento padrão de 0 (zero) quando não são definidas.

As atualizações de 14 de setembro de 2021 ou posteriores têm o comportamento padrão de 1 (um) quando não são definidas.

É necessário reiniciar? Sim, uma reinicialização do dispositivo ou uma reinicialização do serviço de spooler é necessária.

Desde já agradeço, estou a disposição mailto:alvacir.oliveira@msn.com
