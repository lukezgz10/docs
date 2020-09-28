---
title: Acessar o console de gerenciamento
intro: 'Use o {{ site.data.variables.enterprise.management_console }} para definir e configurar a {{ site.data.variables.product.product_location }}, agendar períodos de manutenção, solucionar problemas e gerenciar a licença.'
redirect_from:
  - /enterprise/admin/articles/about-the-management-console/
  - /enterprise/admin/articles/management-console-for-emergency-recovery/
  - /enterprise/admin/articles/web-based-management-console/
  - /enterprise/admin/categories/management-console/
  - /enterprise/admin/articles/accessing-the-management-console/
  - /enterprise/admin/guides/installation/web-based-management-console/
  - /enterprise/admin/installation/accessing-the-management-console
  - /enterprise/admin/configuration/accessing-the-management-console
versions:
  enterprise-server: '*'
---

### Sobre o {{ site.data.variables.enterprise.management_console }}

Use o {{ site.data.variables.enterprise.management_console }} para atividades administrativas básicas:
- **Configuração inicial**: conheça o processo de configuração inicial ao entrar pela primeira vez na {{ site.data.variables.product.product_location_enterprise }} acessando o endereço IP da {{ site.data.variables.product.product_location_enterprise }} no navegador.
- **Configurações básicas da instância**: configure DNS, nome do host, SSL, autenticação do usuário, e-mail, serviços de monitoramento e encaminhamento de logs na página Settings (Configurações).
- **Agendamento de períodos de manutenção**: deixe a {{ site.data.variables.product.product_location_enterprise }} offline durante a manutenção usando o {{ site.data.variables.enterprise.management_console }} ou o shell administrativo.
- **Solução de problemas**: gere um pacote de suporte ou exiba informações de diagnóstico de alto nível.
- **Gerenciamento de licenças**: exiba ou atualize a licença do {{ site.data.variables.product.prodname_enterprise }}.

É possível chegar ao {{ site.data.variables.enterprise.management_console }} usando o endereço IP da {{ site.data.variables.product.product_location_enterprise }}, mesmo quando a instância estiver em modo de manutenção, ou quando houver uma falha grave de aplicativo ou problema de configuração de SSL.

Para acessar o {{ site.data.variables.enterprise.management_console }}, você deve usar a senha de administrador definida na configuração inicial da {{ site.data.variables.product.product_location_enterprise }}. Você também deve poder se conectar ao host da máquina virtual na porta 8443. Se tiver problemas para chegar ao {{ site.data.variables.enterprise.management_console }}, verifique as configurações intermediárias de firewall e grupo de segurança.

### Acessar o {{ site.data.variables.enterprise.management_console }} como administrador do site

A primeira vez que você acessar o {{ site.data.variables.enterprise.management_console }} como administrador do site, você deve enviar seu arquivo de licença do {{ site.data.variables.product.prodname_enterprise }} para efetuar a autenticação no aplicativo. Para obter mais informações, consulte "[Gerenciar sua licença do {{ site.data.variables.product.prodname_enterprise}}](/enterprise/{{ currentVersion }}/admin/guides/installation/managing-your-github-enterprise-license)".

{{ site.data.reusables.enterprise_site_admin_settings.access-settings }}
{{ site.data.reusables.enterprise_site_admin_settings.management-console }}
{{ site.data.reusables.enterprise_management_console.type-management-console-password }}

### Acessar o {{ site.data.variables.enterprise.management_console }} como usuário não autenticado

1. Acesse esta URL no navegador substituindo `hostname` pelo nome de host ou endereço IP do {{ site.data.variables.product.prodname_ghe_server }}:
  ```shell
  http(s)://HOSTNAME/setup
  ```
{{ site.data.reusables.enterprise_management_console.type-management-console-password }}

### Desbloquear o {{ site.data.variables.enterprise.management_console }} após tentativas de login com falha

O {{ site.data.variables.enterprise.management_console }} trava após dez tentativas de login com falha em um período de dez minutos. Antes de tentar novamente, aguarde o desbloqueio automático da tela de login, que ocorrerá após um período de dez minutos. A contagem é redefinida depois do login bem-sucedido.

Para bloquear o {{ site.data.variables.enterprise.management_console }} imediatamente, use o comando `ghe-reactivate-admin-login` pelo shell administrativo. Para obter mais informações, consulte "[Utilitários da linha de comando](/enterprise/{{ currentVersion }}/admin/guides/installation/command-line-utilities#ghe-reactivate-admin-login)" e "[Acessar o shell administrativo (SSH)](/enterprise/{{ currentVersion }}/admin/guides/installation/accessing-the-administrative-shell-ssh/)".