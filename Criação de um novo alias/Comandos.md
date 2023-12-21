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

#### Dividir uma string, com base no caractér escolhido
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

#### Simulação da ação do comando 
```
Rename-Item C:\Scripts\script.bat C:\Scripts\script_migrando.bat -WhatIf
```

#### Atualizar os tópicos de ajuda do PowerShell
```
Update-Help
```

#### Obter todos os scripts que atuam com aliases
```
Get-Command -noun alias
```

#### Criar novos aliases
```
new-alias -Name="rename" rename-item
```

#### Verificar todos alias 
```
get-alias rename
```

#### Trocar o nome do arquivo com alias 
```
rename C:\Scripts\script.bat C:\Scripts\script_migrando.bat 
```

#### Criação de um novo arquivo Profile
```
New-Item $profile
```

#### Obter a política de execução corrente
```
Get-ExecutionPolicy
```

#### Mudar o valor da política (powershell como administrador)
```
Set-ExecutionPolicy Unrestricted
```

#### Local de armazenamento do script de profile de todos os usuários e hosts
```
$Profile.AllUsersAllHosts

New-Item $Profile.AllUsersAllHosts
notepad $Profile.AllUsersAllHosts
```






