# 利用方法 ＆ ビルド方法

```bash
$ git clone https://github.com/dena/PacketProxyPlugin.git
$ cd PacketProxyPlugin/
$ vi src/main/java/packetproxyplugin/EncodeHoge.java # エンコードモジュールを実装してください
$ ./gradlew shadowJar
```

ビルドに成功すると `build/libs/PakcetProxyPlugin-[バージョン]-all.jar` が生成されます。

生成されたjarファイルを `[Home]/.packetproxy/plugins/` にコピーすることで、PacketProxyに読み込ませることができます。

# `lib/PacketProxyLib.jar` の更新方法

`lib/PacketProxyLib.jar` を更新することで、エンコードモジュールで、より新しい PacketProxy 内部のクラスやメソッドが利用できるようになります。

```bash
$ git clone https://github.com/dena/PacketProxy.git
$ cd PacketProxy/
$ ./gradlew assemble
$ cd build/classes/java/main/
$ jar -cf PacketProxyLib.jar packetproxy/
$ cp PacketProxyLib.jar [PacketProxyPluginへのルートパス]/lib/
```

# ライセンス

Apache License 2.0

