# PageAnalyze

**Owner** [Hayao-H](https://github.com/Hayao-H)

## Scenarios and User Experience
- 視聴ページに変更があった場合、アプリケーション本体を更新せずに対応できれば、コンフリクト等の問題を避けられる。

## Requirements
- ```Hooks API```を利用することでアドオン開発者がページ解析を代替することができる。

### Goals
- アドオン開発者がページ解析を自由に行うことができる。

### Non-Goals
- ページ解析をアプリケーション本体が担う。

## Stakeholders and Reviewers
- (Owner)[Hayao-H](https://github.com/Hayao-H)

## Design

### API
```TypeScript
application.hooks.registerPageAnalyzeFunction(func: (page: string) => DmcInfo): void;
```
**argments**
- page: 視聴ページのhtml。  

**returns**
- DmcInfo: 動画情報のインターフェース。詳細については、標準ライブラリの[当該ソース](https://github.com/Hayao-H/NiconicomeAddonCoreLib/blob/develop/%40types/net/hooks/types/dmcinfo.d.ts)を参照してください。


## Q & A
None

## Revision
Date | Description
:---:| :---:
2021/08/17 | APIを定義。
2021/08/21 | Target API Versionを明記。
2021/09/20 | APIバージョンの表記を修正。
2022/03/29 | 型についての注記を追加。

## Applies to
Application | Target API Version
:--: | --
Niconicome | >= 1.0