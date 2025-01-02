## What does "This system cannot execute scripts because the execution policy is restricted" mean?

```Powershell
. : 이 시스템에서 스크립트를 실행할 수 없으므로 C:\Users\sukje\Documents\WindowsPowerShell\profile.ps1 파일을 로드할 수 없습니다. 자세한 내용은 about_Execution_Policies(https://go.microsoft.com/fwlink/?LinkID=135170)를 
참조하십시오.
위치 줄:1 문자:3
+ . 'C:\Users\sukje\Documents\WindowsPowerShell\profile.ps1'
+
``` 
This error message indicates that the PowerShell execution policy is set to Restricted, which prevents any PowerShell scripts, including configuration files like profile.ps1, from being executed. 
By default, Windows client systems use the Restricted policy for security reasons, disallowing all script execution to avoid malicious actions.
```Powershell
Get-ExecutionPolicy
Restricted
```

### How can I solve the problem?
To allow scripts like conda-hook.ps1 to run, you can change the execution policy to RemoteSigned, which permits locally created scripts to execute while requiring a signature for scripts downloaded from the internet.
1. Open PowerShell with administrator privileges.
2. Run the following command to set the execution policy:
```Powershell
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

## Why is python list comprehension needed?
1. Code Simplification
2. Code Readability (list comprehension is used when list creation)
3. Easy to add condition
4. Performance Optimization

### list creation using for loop
```python
lst = []
for i in range(10):
    if i % 2 == 0:
        lst.append(i)
```

### list comprehension
```python
lst = [i for i in ragne(10) if i % 2 == 0]
```
