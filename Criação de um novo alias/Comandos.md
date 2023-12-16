### `Comandos`

#### Invocar um script .bat com o Command Precedence
```
.\reiniciaServicoSrv01.bat
```

#### Imprimir a variável de ambiente PATH na console
```
echo $env:path
```

#### Imprimir a variável de ambiente PATH na console (simplificado)
```
$env:path
```

#### Verificar o tipo de dado armazenado dentro da variável 
```
$env:path.GetType()
```

#### Dividir string com o Método Split, com base no caractér escolhido
```
$env:path.Split(';')
```

#### Verificar as propriedades e os métodos disponíveis no objeto
```
$env:path | Get-Member
```

#### Obter todos os apelidos de comandos no PowerShell
```
Get-Alias
```

#### Obter todos os comandos no PowerShell
```
Get-Command
```

#### Filtrar os comandos com o argumento -Name 
```
Get-Command -Name *rename*
```

#### Obter ajuda sobre um comando
```
Get-Help Rename-Item
```

#### simular o que o comando faria sem realmente executá-lo 
```
Rename-Item C:\Scripts\script.bat C:\Scripts\script_migrando.bat -WhatIf
```
#### Atualizar os tópicos de ajuda do PowerShell
```
Update-Help
```

#### Obter todos os scripts que atuam com Alias
```
Get-Command -noun alias
```

#### Criar novos alias
```
new-alias -Name="rename" rename-item
```

#### Podemos verificar nosso alias criado com o comando abaixo
```
get-alias rename
```
#### Alias feito, agora podemos executar!
```
rename C:\Scripts\script.bat C:\Scripts\script_migrando.bat 
```

# Para acessarmos o endereço do profile vigente no contexto do PowerShell, podemos
# usar a variável $profile.
# Note que nem sempre este arquivo existe!
$profile

#### Criação de um novo Profile
New-Item $profile

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







