# Log API

**Owner** [Hayao-H](https://github.com/Hayao-H)

## Scenarios and User Experience
- ```datetime.log```のようなログファイルにエラー出力を書き込むことで永続的なメッセージを残せるようにする。

## Requirements
- ```Log API```を利用することでアドオン開発者がログ出力を行うことができる。

### Goals
- アドオン開発者がログ出力を自由に行うことができる。

### Non-Goals
- アドオン開発者がログ出力を行う手段を持たない。

## Stakeholders and Reviewers
- (Owner)[Hayao-H](https://github.com/Hayao-H)

## Design

### Permission
```log```

### API
```TypeScript
application.log.error(message: string): void;
```
***argments***
- message: 出力する文字列。

### Remarks
- ```error()```メソッドによる出力は **[error]** として出力されるように実装します。


## Q & A
None

## Revision
Date | Description
:---:| :---:
2021/08/17 | Log APIの定義を追加。
2021/09/20 | APIバージョンの表記を修正

## Applies to
Application | Target API Version
:--: | --
Niconicome | >= 1.0