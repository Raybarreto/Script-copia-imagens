# Script de Cópia de Imagens e Criação de Log
Este script em lote (batch script) foi desenvolvido para copiar arquivos de imagem (.jpg e .png) de uma pasta de origem para uma pasta de destino, e gerar um arquivo de log com informações sobre o processo. O script foi projetado para copiar as imagens de todas as subpastas dentro da pasta de origem, e registrar no log a primeira e a última imagem encontrada em cada subpasta, juntamente com o número total de imagens copiadas.

## Funcionalidades

*   **Cópia de Arquivos:* Copia todos os arquivos .jpg e .png encontrados nas subpastas da pasta de origem para a pasta de destino.
*   **Geração de Log:* Cria um arquivo de log com o nome DER_AAAA-MM-DD_HHMMSS.txt (onde AAAA-MM-DD é a data e HHMMSS é a hora da execução) contendo as seguintes 

informações para cada subpasta:
Data e hora da operação
Nome da pasta
Nome do primeiro arquivo de imagem encontrado
Nome do último arquivo de imagem encontrado
Número total de arquivos copiados da pasta

## Instruções de Uso
1. Salve o script:* Salve o código do script em um arquivo com extensão .bat, por exemplo, copiar_imagens.bat.
2. *Ajuste as pastas:
3. Abra o arquivo .bat com um editor de texto (como o Bloco de Notas).
4. Modifique as variáveis pasta_origem e pasta_destino para os caminhos corretos das suas pastas.
5. Execute o script: Dê dois cliques no arquivo .bat para executá-lo.

## Requisitos
Windows XP ou superior
Permissões de leitura na pasta de origem e permissões de escrita na pasta de destino.

## Observações
1. O script irá copiar todos os arquivos .jpg e .png que encontrar nas subpastas da pasta de origem.
2. O arquivo de log será criado na mesma pasta onde o script está localizado.
3. O script não sobrescreve arquivos existentes na pasta de destino. Se um arquivo com o mesmo nome já existir, ele não será copiado novamente.
4. O formato do nome do arquivo de log é *DER_AAAA-MM-DD_HHMMSS.txt* para evitar que logs sejam sobrescritos.
5. O script inclui tratamento de erros para evitar a exibição de mensagens de erro na tela durante a cópia dos arquivos (>nul 2>&1).
6. Exemplo de Log

Em 2024-07-26 103000 - Pasta1^- imagem1.jpg a imagem5.png Total: 5
Em 2024-07-26 103000 - Pasta2^- foto1.png a foto3.jpg Total: 3


## Autor
Este script foi desenvolvido por Raylaine Barreto.
