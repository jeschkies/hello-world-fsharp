node('windows') {
  stage("Provision") {
    powershell(returnStatus: true, script:'''
      Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1')) 

      choco install dotnetcore-sdk --confirm
    ''')
  }
  stage("Build") {
    powershell(returnStatus: true, script:'''
      dotnet build
    ''')
  }
}
