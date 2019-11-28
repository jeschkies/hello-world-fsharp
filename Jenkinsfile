node('windows') {
  stage("Provision") {
    powershell(returnStatus: true, script:'''
      Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1')) 

      choco install dotnetcore-sdk --confirm
      refreshenv
      echo %PATH%
    ''')
  }
  stage("Build") {
    powerShell "dotnet build"
  }
}
