#### Invocando um script .bat com o Command Precedence
.\reiniciaServicoSrv01.bat

#### Imprimindo a variável de ambiente PATH na console
echo $env:path
# Também podemos simplesmente executar a expressão 
$env:path

# Como o PowerShell é orientado a objetos com .NET, podemos invocar o método GetType()(verifica o tipo de dado armazenado dentro da variavel) em qualquer variável 
$env:path.GetType()

# Podemos invocar o método Split da classe string na variável PATH! (Split() divida uma string)
$env:path.Split(';')

# Podemos usar o comando Get-Member para verificarmos as propriedades e os métodos dsponíveis no objeto
$env:path | Get-Member

# Conseguimos obter todos os apelidos de comandos (ALIAS) no PowerShell com o comando Get-Alias
Get-Alias

# Conseguimos obter todos os comandos no PowerShell com o comando Get-Command
Get-Command

# Com o argumento -Name, nós conseguimos filtrar os comandos que possuem rename no nome. (O asterisco atua como coringa para qualquer quantidade de caractere)
Get-Command -Name *rename*

# Obtendo ajuda do comando rename-item
Get-Help Name rename-item

# Com o SwitchArgument -WhatIf podemos saber o que o comando faria antes de executarmos-o
Rename-Item C:\Scripts\script.bat C:\Scripts\script_migrando.bat -WhatIf

# Sem o SwitchArgument, tudo funciona normalmente
Rename-Item C:\Scripts\script.bat C:\Scripts\script_migrando.bat 

# Atualizamos os tópicos de ajuda do PowerShell com o comando Update-Help
Update-Help

# Obtemos todos os scripts que atuam com Aliases, com o comando "Get-Command -noun alias"
Get-Command -noun alias

# O Get-Help retorna a ajuda ou a sintaxe de um comando, quando um documento de ajuda não estiver disponível
Get-Help new-alias

# Com new-alias podemos criar novos aliases
new-alias -Name="rename" rename-item

#Podemos verificar nosso alias criado com o comando abaixo
get-alias rename

#Alias feito, agora podemos executar!
rename C:\Scripts\script.bat C:\Scripts\script_migrando.bat 



# Para acessarmos o endereço do profile vigente no contexto do PowerShell, podemos
# usar a variável $profile.
# Note que nem sempre este arquivo existe!
$profile

# Podemos criar um novo Profile com o comando
New-Item $profile

# Sem nenhuma configuração inicial, não poderemos executar um script do PowerShell
# por conta das políticas de execução. Podemos saber mais sobre isso executando:
Get-Help about_ExecutionPolicy

# Para obtermos a política de execução corrente, usamos...
Get-ExecutionPolicy

# ...e para mudarmos seu valor (é necessário rodas o powershell como administrador)
Set-ExecutionPolicy Unrestricted

# Coringas também funcionam no comando Get-Help!
Get-Help about_*

Get-Help about_profiles

# Verificando o local onde deve ser armazenado o script de profile para todos os usuários e todos os hosts
$Profile.AllUsersAllHosts

New-Item $Profile.AllUsersAllHosts
notepad $Profile.AllUsersAllHosts







