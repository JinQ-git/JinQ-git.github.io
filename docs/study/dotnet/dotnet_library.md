# Library 빌드 & 참조

> 어느 쪽이든 보통 한번 세팅해 놓으면 더 손댈 일은 없을 것이다.

1. `dll`로 빌드 후, 강제 링크
1. `nuget package`로 빌드 후, 일반적인 방법으로 추가

> `nuget package`를 이용하는 방법을 추천합니다

## 1. `dll`로 빌드 후, 강제 링크

1. Build Project

```sh
dotnet publish --configuration Release
```

2. Update target project configuration file (`.csproj`) like below:

`TestRun.csproj`: 
```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net8.0</TargetFramework>
    <ImplicitUsings>enable</ImplicitUsings>
    <Nullable>enable</Nullable>
  </PropertyGroup>

<!-- dll begin-->
  <ItemGroup>
    <Reference Include="MyAssembly"> <!-- "MyAssembly" 부분은 원하는 이름으로 -->
      <!-- <HintPath> 에 dll 경로를 적어주자 -->
      <HintPath>..\Library\bin\Release\netstandard2.1\Library.dll</HintPath>
    </Reference>
  </ItemGroup>
<!-- dll end-->

</Project>
```

## 2. `nuget package`로 빌드 후 이용하는 방법

1. Build Project

```sh
dotnet pack --configuration Release -p:PackageVersion=0.1.0
```

> **참조**: <br/>
> `-o` | `--output` 옵션: Places the built packages in the directory specified.
> 
> ```sh
> dotnet pack --configuration Release -p:PackageVersion=0.1.0 --output "C:\Library\dotnet"
> ```
>
> target platform을 처리하고 싶다면
>
> ```sh
> dotnet pack --configuration Release -p:PackageVersion=0.1.0 -p:TargetFrameworks="netstandard2.1" --output "C:\Library\dotnet"
> ```


결과적으로, `${Library_이름}.${version}.nupkt` 파일이 생성

2. `nuget` _source_ 에 `.nupkt` 파일이 위치한 local directory를 추가

```sh
dotnet nuget add source "C:\Library\dotnet" --name "LOCAL_DOTNET_LIBRARY"
```

> **주의**: 경로는 가급적 절대경로로 지정하자. <br/>
> `dotnet add package ...` 명령을 실행할 때, source 경로를 상대경로로 입력하면, <br/>
> nuget 홈 디렉토리로부터의 상대경로를 참조하므로, 예상과 다른 결과를 도출한다.

> **Tip:** `--name` 옵션을 통해 지정한 이름으로 _source_ 삭제도 가능
> 
> ```sh
> dotnet nuget remove source "LOCAL_DOTNET_LIBRARY"
> ```

3. 프로젝트에 `package` 를 추가한다

```sh
dotnet add package "${Library_이름}"
```

또는 버전 지정

```sh
dotnet add package "${Library_이름}" --version "0.1.0"
```

## Reference

[NuGet.Config 이용? 좀 옛날 방법](https://stackoverflow.com/questions/43400069/add-a-package-with-a-local-package-file-in-dotnet)
