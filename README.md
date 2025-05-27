Tutorial: Vincular o Git do DevOps para Versionamento e Backups no Data Factory (Fabric)
Neste tutorial, você aprenderá a integrar um repositório Git do Azure DevOps (ou GitHub) ao Data Factory (Fabric) para versionamento, histórico de alterações e backups automatizados.

Pré-requisitos
✅ Uma conta no Azure DevOps (dev.azure.com) ou GitHub.
✅ Um projeto no Azure DevOps com um repositório Git configurado.
✅ Acesso a um workspace do Microsoft Fabric com o Data Factory.

Passo 1: Configurar o Repositório Git no Azure DevOps
Acesse o Azure DevOps (https://dev.azure.com/).

Crie um novo projeto (ou use um existente).

No projeto, vá para Repos > Files e verifique se há um repositório Git configurado.

Se não existir, crie um novo repositório.

Passo 2: Vincular o Git ao Data Factory (Fabric)
Acesse o Microsoft Fabric (https://app.fabric.microsoft.com).

Navegue até o Data Factory dentro do seu workspace.

No canto inferior direito, clique no ícone de engrenagem (⚙) > Git configuration.

Git Configuration no Fabric

Na janela de configuração, preencha os campos:

Git provider: Azure DevOps (ou GitHub).

Azure DevOps account: Sua organização (ex: https://dev.azure.com/sua-organizacao).

Project name: Nome do projeto no DevOps.

Repository name: Nome do repositório Git.

Collaboration branch: main (ou outra branch principal).

Publish branch: adf_publish (usada para implantações automatizadas).

Clique em Apply para salvar.

Passo 3: Trabalhando com Versionamento no Data Factory
Agora, todas as alterações no Data Factory serão rastreadas no Git.

Fazendo Commit das Alterações
Ao modificar pipelines, conjuntos de dados ou fluxos de dados, o Fabric mostrará alterações pendentes.

Clique no ícone Git (✔) no canto superior direito.

Adicione uma mensagem de commit e selecione Commit.

Se desejar enviar para o repositório remoto, clique em Push.

Sincronizando com a Branch Principal
Use Pull para trazer alterações da branch remota.

Em caso de conflitos, resolva antes de fazer commit.

Passo 4: Backups Automatizados
Como o Data Factory está vinculado ao Git, todo o código-fonte (JSON dos pipelines, datasets, etc.) é armazenado no repositório, funcionando como backup.

Recuperando uma Versão Anterior
No Azure DevOps, vá para Repos > Commits.

Encontre o commit desejado e clique em Browse files.

Você pode reverter ou copiar os arquivos necessários.

Dicas Importantes
🔹 Branch adf_publish: É automaticamente criada para armazenar artefatos publicados (usada em CI/CD).
🔹 Conflitos: Sempre faça Pull antes de começar a trabalhar para evitar divergências.
🔹 Backup adicional: Exporte periodicamente o .zip do Data Factory (⚙ > Export ARM template).
