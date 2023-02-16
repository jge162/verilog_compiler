## GitHub Verilog-Compiler:  

![GitHub Workflow Status (with branch)](https://img.shields.io/github/actions/workflow/status/jge162/Action-workflows/python_check.yml)
![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/jge162/verilog-compiler)
![GitHub package.json version](https://img.shields.io/github/package-json/v/jge162/Action-workflows)

<img src="https://user-images.githubusercontent.com/31228460/218295872-1865b4ba-9c3c-4a28-bac8-0fd11c7c37f6.png" width="79%">

## Purpose of Verilog Compiler:
  
To be able to quickly load your .v files to GitHub and run and test them. It will notify you
of errors in your code just like a compiler should. It requires to files to run. First you
need to create a directoy script/sh to run a script. Then you chose which .v files you want to run.

## veriflog_compiler.v 

```yaml
name: Verilog Build and Analysis

on:
  schedule:
  - cron: '0 0,12 * * *' 
    # action will run everyday at 12 am and 12 pm
  workflow_dispatch:

jobs:
  build-and-analyze:
    runs-on: ubuntu-latest

    steps:
    - name: Python Action
      uses: jge162/Action-workflows@1.1.1


    - run: |
        echo "Install required dependencies"
        sudo apt-get update
        sudo apt-get install iverilog
        sudo apt-get install verilator

    - run: |
        echo "Set executable permission on script file"
        chmod +x script/sh
        chmod +x ./verilog_test_case.v
        
    - run: |
        echo "Run, Build Application using script"
        ./script/sh
```

       
## Issues and/or bugs, please create an issue to help me squash them!:

Please report [issues](https://github.com/jge162/verilog_compiler/issues) here for discussion and resolution please.

## License info:
  
jge162/verilog_compiler is licensed under the [GNU General Public License v3.0](https://github.com/jge162/verilog_compiler/blob/main/LICENSE)
