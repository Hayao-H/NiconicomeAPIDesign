# Resource API

**Owner** [Hayao-H](https://github.com/Hayao-H)

## Scenarios and User Experience
- ドキュメントをコード外に定義して、Webview2で表示したい。

## Requirements
- 文書をコード外に定義したい。
- 安全にアクセスしたい。

### Goals
- 文書をコード外に定義できる。
- 安全なアクセスが可能である。

### Non-Goals
- 文書をコード外に定義できない。
- 安全なアクセスが可能でない。

## Stakeholders and Reviewers
- (Owner)[Hayao-H](https://github.com/Hayao-H)

## Design

### Permission
```resource```

### Folder
```
- rootDir
    - resource /* MUST */
        - docment1.html
        - docment2.txt
        - img1.jpg
        - special
            - readme.txt
```

### API
```TypeScript

/*
同期的にリソースを取得します。
引数はresourceフォルダーからの相対パスです。
不正なパスが与えられたり、読み込みに失敗した場合はnullを返します。
*/
application.resource.getResource(relativePath: string): string | null;

```

### Example
```TypeScript

    const doc1:string = application.resource.getResource('docment1.html');
    const readme:string = application.resource.getResource('special/readme.txt');

    _output.write(doc1);
    _output.write(readme);

```

## Q & A

## Revision
Date | Description
:---:| :---:
2021/09/20 | 初版作成
2021/09/21 | APIを非同期化。
2021/09/30 | APIを同期化。
2021/10/02 | 取得処理を関数化。

## Applies to
Application | Target API Version
:--: | --
Niconicome | >= v1.2.0