# Angularのチュートリアルの写経

写経元
[Angular - チュートリアル: ツアー・オブ・ヒーローズ](https://angular-ja.firebaseapp.com/tutorial)

このコードはオリジナルで作ったものではなく、移したものです。

## 起動方法

```
ng serve --open
```

## つまずいたところ

[8章](https://angular-ja.firebaseapp.com/tutorial/toh-pt6#%E3%83%92%E3%83%BC%E3%83%AD%E3%83%BC%E3%81%A8http)の下記のコードを実装したらエラーを505エラーを吐き、データが表示されない。

```
getHeroes (): Observable<Hero[]> {
  return this.http.get<Hero[]>(this.heroesUrl)
}
```

### 原因
angular-in-memory-web-api(インメモリWeb API)のバージョンが合わない為、古いバージョンを使えば良い。

参考サイト
[javascript - angular-in-memory-web-api internal server error - Stack Overflow](https://stackoverflow.com/questions/49474048/angular-in-memory-web-api-internal-server-error)

インストールし直し
```
npm install angular-in-memory-web-api@0.5.4 --save
```
package.jsonは下記の通りに書く。
```
"angular-in-memory-web-api": "~0.5.0",
```