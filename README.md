Descrição Detalhada do Pipeline Configurado
O pipeline configurado no arquivo .github/workflows/jellyfin-ci.yml é um fluxo de trabalho para automação de CI/CD utilizando GitHub Actions para o projeto Jellyfin, que é uma aplicação em .NET Core. O pipeline é composto pelas seguintes etapas:
setup_environment: Configura o ambiente necessário para executar o pipeline, incluindo a instalação do .NET SDK.
build_project: Realiza o build do projeto .NET, restaurando as dependências e compilando o código.
run_tests: Executa os testes automatizados e faz o upload dos resultados dos testes como artefato.
publish_artifacts: Publica os artefatos construídos e faz o upload desses artefatos como artefato final.
Análise das Etapas do Pipeline
Setup do Ambiente (setup_environment):
Justificativa: Esta etapa é fundamental para garantir que o ambiente tenha o .NET SDK necessário para o projeto. É uma boa prática começar o pipeline configurando o ambiente, o que ajuda a evitar problemas em etapas posteriores.
Escolha: Utiliza uma imagem Docker do .NET Core SDK fornecida pela Microsoft para garantir a consistência do ambiente.
Build do Projeto (build_project):
Justificativa: Compilar o projeto é uma etapa crucial em qualquer pipeline de CI/CD. Restaurar dependências e construir o projeto ajuda a garantir que o código está em um estado compilável e que todas as dependências estão presentes.
Escolha: Utiliza a imagem Docker do .NET Core SDK para manter o ambiente de build consistente com o utilizado no setup.
Testes Automatizados (run_tests):
Justificativa: Executar testes automatizados é essencial para verificar a funcionalidade e a integridade do código. A inclusão do upload dos resultados dos testes permite que esses resultados sejam acessados em etapas posteriores do pipeline.
Escolha: Utiliza actions/upload-artifact para compartilhar os resultados dos testes com outras etapas do pipeline.
Publicação de Artefatos (publish_artifacts):
Justificativa: Publicar os artefatos construídos é importante para que eles possam ser usados em estágios posteriores, como em ambientes de staging ou produção.
Escolha: Utiliza actions/upload-artifact para garantir que os artefatos estejam disponíveis para download e uso posterior.
