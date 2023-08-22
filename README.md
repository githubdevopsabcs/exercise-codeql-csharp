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
1. download needed packs
```
codeql pack download codeql/csharp-queries
```
![image](https://github.com/githubdevopsabcs/exercise-codeql-csharp/assets/48259636/a4452052-62a5-4bf5-bd58-4791a0350777)
1. double check folder:
![image](https://github.com/githubdevopsabcs/exercise-codeql-csharp/assets/48259636/31d48c77-89fe-436d-af6e-a046751ae2c4)
1. now analyze
```
codeql database analyze C:\codeql-dbs\exercise-codeql-csharp\ --sarif-category=csharp --format=sarif-latest --output=C:\src\GitHub\githubdevopsabcs\exercise-codeql-csharp\temp\exercise-codeql-csharp.sarif
```
1. alternatively add --download
```
codeql database analyze C:\codeql-dbs\exercise-codeql-csharp\ --download --sarif-category=csharp --format=sarif-latest --output=C:\src\GitHub\githubdevopsabcs\exercise-codeql-csharp\temp\exercise-codeql-csharp.sarif
```
1. you will see a bunch of queries run
![image](https://github.com/githubdevopsabcs/exercise-codeql-csharp/assets/48259636/89011537-dfb5-4aa7-af95-fe736bf95dea)
1. then interpret results
![image](https://github.com/githubdevopsabcs/exercise-codeql-csharp/assets/48259636/1f632183-cb06-4649-a389-c67ed96aaae9)
1. make sure output folder exists
```
mkdir C:\src\GitHub\githubdevopsabcs\exercise-codeql-csharp\temp
```
1. or you will get error writing output
![image](https://github.com/githubdevopsabcs/exercise-codeql-csharp/assets/48259636/86f12a4c-cb32-42bc-a85d-057c52ddef15)
1. try again - observe not re-running queries
![image](https://github.com/githubdevopsabcs/exercise-codeql-csharp/assets/48259636/17daacf4-2b58-4ea7-a92d-1ebfafc0e036)
1. most likely due to fingerprints
![image](https://github.com/githubdevopsabcs/exercise-codeql-csharp/assets/48259636/46926f17-11fa-4c91-aea9-e7e746a0f04c)
1. upload el sarif
```
codeql github upload-results --repository=githubdevopsabcs/exercise-codeql-csharp --ref=refs/heads/main --commit=1ee18b3170340110cb5977249da911a326205595 --sarif=C:\src\GitHub\githubdevopsabcs\exercise-codeql-csharp\temp\exercise-codeql-csharp.sarif --github-auth-stdin
```
![image](https://github.com/githubdevopsabcs/exercise-codeql-csharp/assets/48259636/818d1be9-fc67-43c2-a3b6-cb83fecce19f)
1. verify for good measure
![image](https://github.com/githubdevopsabcs/exercise-codeql-csharp/assets/48259636/4ea50fc5-d02b-4ae1-b432-944baaf0ede4)








