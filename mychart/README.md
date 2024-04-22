# Guia de Uso do Helm

Este guia fornece instruções para instalar, atualizar e desinstalar seu aplicativo usando o Helm.

## Instalação

Para instalar o aplicativo pela primeira vez, execute o seguinte comando:
```
helm install nome-do-release . --values values.yaml
```
Substitua nome-do-release pelo nome que deseja atribuir à sua instalação e values.yaml pelo caminho para o arquivo de valores personalizados, se aplicável.

## Atualização

Para atualizar o aplicativo após fazer alterações nos valores ou nos arquivos de manifesto, use o seguinte comando:
```
helm upgrade nome-do-release . --values values.yaml
```
Isso aplicará as alterações nos arquivos de manifesto e nos valores definidos no arquivo values.yaml.


## Rollback

Para dar rollback de um release do Helm, você pode usar o comando helm rollback. Aqui está a sintaxe básica:

```
helm rollback [RELEASE] [REVISION]
```

Onde:

[RELEASE] é o nome do release que você deseja fazer o rollback.
[REVISION] é o número da revisão para a qual você deseja fazer o rollback. Você pode ver as revisões disponíveis usando helm history [RELEASE].
Por exemplo, se o nome do seu release for nome-do-release e você deseja fazer rollback para a revisão 1, o comando seria assim:

```
helm rollback nome-do-release 1
```
Isso irá reverter seu release para o estado da revisão 1. Certifique-se de revisar as mudanças antes de confirmar o rollback.


## Desinstalação

Para desinstalar o aplicativo e liberar os recursos do Kubernetes associados, execute o seguinte comando:
```
helm uninstall nome-do-release
```
Isso removerá todos os recursos associados ao release do Helm especificado.
