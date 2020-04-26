# Linux Fundamentos

## Comandos

* **man** ou **--help** => manual de comandos
* **su** => troca pelo usuário determinado, o padrão sem argumentos é o root
* **apt** => gerenciador de pacotes
	- **install** => instala pacotes
	- **remove** => remove/desinstala pacotes
	- **update** => atualiza o referencial dos repositórios
	- **upgrade** => atualiza pacotes
* **sudo** => concede permissão de administrador a um comando (usuário precisa estar referenciado no arquivo sudoers == **# usermod -aG sudo nomeUsuario**)
* **psswd** => troca senha do usuário determinado, padrão sem argumentos é o user atual
* **useradd** => adiciona novos usuários
* **groupadd** => cria grupos de usuários
* **usermod** => modifica atributos de usuários
* **ls** => lista diretórios
	- **-a** => mostra todos os arquivos, incluindo os ocultos
	- **-l** => lista longa, com informações dos arquivos e diretórios
	- **-h** => abrevia informações para legibilidade humana
* **pwd** => retorna o diretório atual
* **mkdir** => cria diretórios
	- **-p** => permite a criação de diretórios em cascata
* **cd** => muda de diretório
* **cp** => faz cópias de arquivos e diretórios
	- **-r** => recursivo, copia o conteúdo de dentro de um diretório junto com ele
	- **-v** => verbose
	- **-p** => preserva permissões na cópia
* **mv** => move e renomeia arquivos e diretórios
* **rm** => deleta arquivos e diretórios
	- **-r** => recursivo, apaga arquivos dentro de diretórios sendo apagados
* **rmdir** => deleta diretórios vazios
* **cat** => retorna conteúdo de arquivo texto no terminal
* **head** => retorna o cabeçalho de um arquivo texto no terminal
* **tale** => retorna as ultimas linhas de um arquivo texto no terminal
* **less** => navega dentro de um arquivo texto(trava terminal)
* **updatedb** => atualiza o database para o uso do **locate**
* **locate** => (apt install) localiza arquivos
* **grep** => faz buscas por palavras chave
* **wget** => baixa arquivos da internet através da url do mesmo
	- **-c** => continua um downlod interrompido por *ctrl+c*
* **links** => (apt install) navegador em linhas de comando
* **unzip** => descompacta arquivos
	- **-t** => testa os arquivos compactados
* **gzip**//**bzip2** => comprimi arquivos(pode ser preciso empacotar antes com **tar**)
* **tar** => empacota arquivos e diretórios
	- **-c** => compress
	- **-z** => compressão usando gzip
	- **-j** => compressão usando bzip2
	- **-v** => verbose
	- **-f** => nomeia arquivo de saída empacotado
	- **-t** => testa os arquivos empacotados
	- **-x** => desempacota ou descomprime
* **ifconfig** => gerencia as interfaces de rede ativas
* **halt** => gerencia rotas de rede
* **ps** => retorna informações de processos (programas executando)
	- **-a** => mostra todos os processos, incluindo os de outros usuários
	- **-u** => detalha informações dos processos
	- **-x** => mostra processos de outros terminais
* **top** => monitor de processos em tempo real
* **kill** => finaliza ("mata") um processo pelo numero do processo ou PID (adquirido pelo comando *ps*)
	- **-SIGSTOP** => congela o processo determinado
	- **-SIGCONT** => descongela um processo congelado
	- **SIGKILL** => finaliza um processo determinado, utilizado por padrão quando nenhum argumento é passado ao *kill*
* **killall** => finaliza um processo pelo nome do processo, e todos os outros processos de mesmo nome

---

* **Rodar programas por terminal trava a tela do terminal, se o comando for seguido de *&*, o programa inicia em segundo plano e a trava não é feita, além do número do PID ser retornado no terminal**
* **O símbolo | concatena comandos**
* **ctrl+c no terminal permite busca de comandos anteriormente realizados pelo usuário**

---

## Diretórios

* **/bin** => armazena os principais executáveis de comandos
* **/boot** => diretório de bootagem do sistema operacional
* **/dev** => armazena pseudoarquivos
* **/etc** => arquivos de configuração
* **/home** => diretórios de usuários
* **/lib** => bibliotecas de sistema
* **/lost+found** => achados e perdidos de arquivos corrompidos
* **/opt** => diretório opciona de instalação
* **proc** => arquivos do processador
* **/root** => diretório do superusuario
* **/run** => processos dos programas
* **/sbin** => super binários
* **/tmp** => arquivos temporários
* **/usr** => programas instalados
* **/var** => arquivos de tamanhos variáveis

---

## Editor de textos Vi

* **:q** => sair
* **:q!** => sair sem salvar
* **i** => vai para o modo de edição para inserir caracteres
* **a** => vai para o modo de edição para inserir caracteres partindo do caractere seguinte do atual (append)
* **A** => modo de edição para inserir caracteres partindo do final da linha atual
* **o** => modo de edição para inserir caracteres partindo da linha abaixo da atual
* **:set nu** => habilita o número das linhas
* **:_numero_** => vai para alinha determinada
* **G** => vai para a ultima linha do arquivo
* **$** => desloca para o final da linha atual
* **^** => desloca para o inicio da linha atual
* **:w** => salva o arquivo (write)
* **:wq** ou **:x**=> salva e sai do arquivo
* **:_numero1_,_numero2_w nomeDoArquivo.txt** => salva o intervalo de linhas determinado no arquivo informado
* **yy** => copia a linha atual
* **p** => cola a linha copiada abaixo da atual
* **_numero_yy** => copia o numero de linhas determinado a partir da linha atual
* **y$** => copia um trecho de caracteres começando do atual até o final da linha
* **y^** => copia um trecho de caracteres começando do atual até o começo da linha
* **dd** => apaga/recorta linha atual
* **_numero_dd** => apaga um intervalo de linhas determinado começando da atual
* **d$** => apaga um trecho de caracteres começando do atual até o final da linha
* **d^** => apaga um trecho de caracteres começando do atual até o começo da linha
* **U** => desfaz a ultima ação (funciona para apenas um comando)
* **/_palavra_** => localiza a palavra informada
	- **n** => avança pelas ocorrências da palavra informada
	- **N** => retorna pelas ocorrências da palavra informada
* **:%s/_palavraAserSubstituida_/_palavraFinal_/_argumento_** => substitui palavras
	- argumento **g** => substitui todas as ocorrências
	- argumento **c** => exige uma confirmação antes de executar cada substituição