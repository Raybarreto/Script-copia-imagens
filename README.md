README do Script
Descrição
Este script [nome do script] foi desenvolvido para [finalidade do script]. Ele utiliza a linguagem [linguagem de programação] e [outras tecnologias ou bibliotecas utilizadas].

Funcionalidades
O script [nome do script] executa as seguintes funcionalidades:

[Listar as funcionalidades do script]
Instruções de Uso
Para utilizar o script, siga os seguintes passos:

Clone este repositório:
Você interrompeu esta resposta





@echo off

setlocal enabledelayedexpansion



:: Definir as pastas de origem (nível superior) e destino

set "pasta_origem=C:\7-Raylaine\Teste1"

set "pasta_destino=C:\7-Raylaine\Teste2"



:: Obter a data e hora atuais no formato desejado para o nome do arquivo de log

for /f "tokens=2 delims==." %%a in ('wmic OS Get LocalDateTime /VALUE ^| findstr LocalDateTime') do set "dataHora=%%a"

set "data=%dataHora:~6,2%-%dataHora:~4,2%-%dataHora:~0,4%"

set "hora=%dataHora:~8,2%%dataHora:~10,2%%dataHora:~12,2%"



:: Criar o nome do arquivo de log com data, hora, minuto e segundo para evitar sobrescrever

set "arquivoLog=DER_%data%_%hora%.txt"



:: Criar o arquivo de log

echo Criando arquivo de log...

(

  for %%a in ("%pasta_origem%") do (

    for /d %%b in ("%%a\*") do (

      set "primeira_imagem="

      set "ultima_imagem="

      set /a contador=0



      for %%i in ("%%b\*.jpg" "%%b\*.png") do (

        if not defined primeira_imagem set "primeira_imagem=%%~nxi"

        set "ultima_imagem=%%~nxi"

        copy "%%i" "%pasta_destino%" >nul 2>&1

        set /a contador+=1

      )



      :: Extraindo apenas o nome da pasta atual

      for %%n in ("%%~nxb") do set "nome_pasta=%%~n"



      :: Ajustando o formato da linha de log para exibir apenas o nome dos arquivos

      echo Em %data% %hora% - !nome_pasta!^- !primeira_imagem! a !ultima_imagem!  Total: !contador!

    )

  )

) > "%arquivoLog%"



echo Tarefa concluída!



README do Script de Cópia de Imagens e Criação de Log
Descrição
Este script em lote (batch script) foi desenvolvido para copiar arquivos de imagem (.jpg e .png) de uma pasta de origem para uma pasta de destino, e gerar um arquivo de log com informações sobre o processo. O script foi projetado para copiar as imagens de todas as subpastas dentro da pasta de origem, e registrar no log a primeira e a última imagem encontrada em cada subpasta, juntamente com o número total de imagens copiadas.

Funcionalidades
Cópia de Arquivos: Copia todos os arquivos .jpg e .png encontrados nas subpastas da pasta de origem para a pasta de destino.
Geração de Log: Cria um arquivo de log com o nome DER_AAAA-MM-DD_HHMMSS.txt (onde AAAA-MM-DD é a data e HHMMSS é a hora da execução) contendo as seguintes informações para cada subpasta:
Data e hora da operação
Nome da pasta
Nome do primeiro arquivo de imagem encontrado
Nome do último arquivo de imagem encontrado
Número total de arquivos copiados da pasta
Instruções de Uso
Salve o script: Salve o código do script em um arquivo com extensão .bat, por exemplo, copiar_imagens.bat.
Ajuste as pastas:
Abra o arquivo .bat com um editor de texto (como o Bloco de Notas).
Modifique as variáveis pasta_origem e pasta_destino para os caminhos corretos das suas pastas.
Execute o script: Dê dois cliques no arquivo .bat para executá-lo.
Requisitos
Windows XP ou superior
Permissões de leitura na pasta de origem e permissões de escrita na pasta de destino.
Observações
O script irá copiar todos os arquivos .jpg e .png que encontrar nas subpastas da pasta de origem.
O arquivo de log será criado na mesma pasta onde o script está localizado.
O script não sobrescreve arquivos existentes na pasta de destino. Se um arquivo com o mesmo nome já existir, ele não será copiado novamente.
O formato do nome do arquivo de log é DER_AAAA-MM-DD_HHMMSS.txt para evitar que logs sejam sobrescritos.
O script inclui tratamento de erros para evitar a exibição de mensagens de erro na tela durante a cópia dos arquivos (>nul 2>&1).
Exemplo de Log
Em 2024-07-26 103000 - Pasta1^- imagem1.jpg a imagem5.png Total: 5
Em 2024-07-26 103000 - Pasta2^- foto1.png a foto3.jpg Total: 3
Autor
Este script foi desenvolvido por Raylaine Barreto.
