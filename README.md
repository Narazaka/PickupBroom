# Pickup Broom

ホウキやモップ、デッキブラシ等を持つギミック

自身のアバターの胸に当てることが出来ます。

## Install

### VCC用インストーラーunitypackageによる方法（おすすめ）

https://github.com/Narazaka/PickupBroom/releases/latest から `net.narazaka.vrchat.pickup-broom-installer.zip` をダウンロードして解凍し、対象のプロジェクトにインポートする。

### VCCによる方法

1. https://vpm.narazaka.net/ から「Add to VCC」ボタンを押してリポジトリをVCCにインストールします。
2. VCCでSettings→Packages→Installed Repositoriesの一覧中で「Narazaka VPM Listing」にチェックが付いていることを確認します。
3. アバタープロジェクトの「Manage Project」から「Pickup Broom」をインストールします。

## Setup

1. `/Packages/Pickup Broom/PickupBroom` prefabをアバター内に配置します。
2. `PickupBroom/GripPoint/GripOffset/BoneForFloorCollider/End/Model` に、ホウキ等のモデルを配置します。
   - 方向は `Delete and Replace This!` オブジェクトを参考にしてください。
3. `Delete and Replace This!` オブジェクトを非表示にします。
4. `End` の位置とモデルの位置を調整し、`BoneForFloorCollider` と `End` の間にモデルが収まるように設定します。
   - `End`は床との接触判定位置です。
5. `PickupBroom/GripPoint/GripOffset/BoneForFloorCollider/End/BreastCollider` の位置やサイズ調整を、モデルの柄の部分にあうように調整します。
6. `BreastCollider` を左右の胸PhysBoneのCollidersに設定します。（省略可）
7. `PickupBroom/GripPoint/GripOffset/BoneForFloorCollider` のGameObjectのチェックを外して非表示にします。
   - アバターフォールバック対策です。
8. 左利きの場合、 `PickupBroom` オブジェクトルートの MA Parameters で `ShowOnLeft` プロパティの初期値をONにします。

## Usage

- メニューから「表示」をONにすると表示されます。
- 柄の近くで右手または左手をFistにすると柄を掴めます。
  - VRCContactを使っている関係上、周囲にVRCContactが非常に多い場所ではこのジェスチャーによる掴みが上手くいかないときがあります。その場合はメニューから掴み状態を変更出来ます。
- 掴んだ状態でFistを0.5秒間継続したのち、HandOpenを0.5秒間継続すると手が離せます。

## 更新履歴

- 0.1.0: リリース

## License

[Zlib License](LICENSE.txt)
