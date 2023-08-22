# exercise-codeql-csharp

## create codeql db for csharp

1. execute
```
codeql database create C:\codeql-dbs\exercise-codeql-csharp --language=csharp --source-root C:\src\GitHub\githubdevopsabcs\exercise-codeql-csharp\
```
1. should see output
![image](https://github.com/githubdevopsabcs/exercise-codeql-csharp/assets/48259636/49902dbe-1a9a-457e-a994-7a73097aacac)
1. can inspect output
![image](https://github.com/githubdevopsabcs/exercise-codeql-csharp/assets/48259636/8924ee8f-bd06-4ead-873a-6788432a3839)
1. can also check codeql-database.yml
![image](https://github.com/githubdevopsabcs/exercise-codeql-csharp/assets/48259636/4cd2b3f2-7aa7-44c8-8ee2-70095ab2724a)
1. or
```
---
sourceLocationPrefix: C:\src\GitHub\githubdevopsabcs\exercise-codeql-csharp
baselineLinesOfCode: 49
unicodeNewlines: false
columnKind: utf16
primaryLanguage: csharp
creationMetadata:
  sha: d10d6393a2327cdb3d779d4dce71c626845f4887
  cliVersion: 2.14.2
  creationTime: 2023-08-22T17:17:17.803483200Z
finalised: true
```
