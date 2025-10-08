# Understanding Layers in SDFusion
SDFusion is designed to treat the stacking of Boolean modifications as layers for workflow purposes.<br>
We created this page in response to feedback that this concept was unclear.<br>
We hope it proves helpful to everyone.

## What is the Layer Concept?
SDFusion's layers are a system for managing Boolean operations (adding or subtracting shapes) as distinct “layers”.<br>
This allows you to non-destructively modify the base mesh (the original 3D object) by overlaying other objects, without damaging the original data.

### Basic Role:

Layers are represented as Blender Collections, with each layer functioning as an independent “hierarchy”.<br>
Each layer consists of two parts: ADD (Add/Union operation) and SUB (Subtract/Difference operation).<br>
<br>
ADD: The place to put objects that “add” new shapes to the base. Example: Adding protrusions or extensions.
SUB: Where you place objects to “subtract” shapes from the base. Example: Drilling holes or carving recesses.
Layers are managed by number (e.g., ADD-1/SUB-1, ADD-2/SUB-2), and Boolean operations are applied sequentially starting from the lowest numbered layer. <br>
This allows you to control the order of operations and build complex shapes hierarchically.<br>
<br>
Meaning of non-destructive: Changes made using layers are only temporarily applied as Blender modifiers.
<br>You can move, adjust, or delete objects at any time; the original mesh remains unchanged until you finally “Apply” the changes.


### Understanding with an image:
Imagine baking a cake.<br>
You spread cream on the base cake (base mesh) in Layer 1 (ADD-1) or cut holes with a cookie cutter (SUB-1), then add decorations in Layer 2 (ADD-2). Since each layer is independent, you can easily change the cream thickness later or adjust hole positions.
<br>
<br>
This layer system enables fluid modeling like SDF using Blender's standard features (Collections and Modifiers), accelerating prototyping and experimental workflows. <br>

## Using Layers (Basic Operations)
Main operations are performed via the SDFusion UI panel (sidebar in the 3D Viewport, displayed with N key > SDFusion tab). <br>
<br>

### Preparing Layers:

Select the base mesh object.<br>
Click “Reset Booleans & Collections” in the UI's “Workflow” section.<br>
<br>
This creates a copy of the base and automatically generates the initial layers (ADD-1/SUB-1, ADD-2/SUB-2).<br>
Simultaneously, Boolean modifiers are added, reflecting objects within the layer in real-time.<br>
Finally, a “GeoRemesh” modifier (geometry node-based) is applied, allowing smooth adjustment of the post-Boolean mesh.<br>


### Object Assignment (Layer Assignment Section):

Create or select a cutter object (e.g., cube, sphere).<br>
Click the layer button in the UI to assign the object.<br>
<br>
Example: Press ADD-1 button → Object moves to ADD-1 collection and is added to the base.<br>
Example: Press the SUB-2 button → Object moves to the SUB-2 collection and is subtracted from the base.<br>
<br>

“SDFusion Pool”: A temporary storage area outside layers. Place objects here that you don't need yet.<br>
Auto-adjust display: Objects within layers display as wireframes or bounding boxes to maintain performance.<br>

### Adding Layers:
If you need more hierarchy, click “Add Layer”.<br>
<br>
A new layer (e.g., ADD-3/SUB-3) is created and added to the modifier stack.<br>
You can add an unlimited number, allowing you to build up fine details step by step.<br>
<br>



# SDFusionにおけるレイヤーの考え方について
SDFusionではブーリアンモディファイのスタックの仕方をレイヤーに見立てて作業することを見据えています。<br>
これがわかりにくいということでコメントを頂いているので、このページを作成しています。<br>
少しでも皆様の助けになれば幸いです。

## レイヤーの概念とは？
SDFusionのレイヤーは、ブーリアン操作（形状の追加や削り取り）を「層（レイヤー）」として管理するシステムです。<br>
これにより、ベースとなるメッシュ（元の3Dオブジェクト）に、他のオブジェクトを重ねて形状を変える操作を、非破壊的に（元のデータを壊さずに）行えます。

### 基本的な役割:

レイヤーは、Blenderのコレクション（Collection）として表現され、各レイヤーが独立した「階層」として機能します。<br>
各レイヤーは、ADD（追加/結合: Union操作）とSUB（削り取り: Difference操作）の2つの部分からなります。<br>
<br>
ADD: ベースに新しい形状を「足す」ためのオブジェクトを置く場所。例: 突起や拡張部分を追加。<br>
SUB: ベースから形状を「引く」ためのオブジェクトを置く場所。例: 穴を開けたり、凹みを掘ったり。<br>
<br>
レイヤーは番号付きで管理され（例: ADD-1/SUB-1、ADD-2/SUB-2）、低い番号のレイヤーから順にブーリアンが適用されます。<br>
これにより、操作の順序をコントロールし、複雑な形状を階層的に構築できます。<br>
<br>
非破壊的の意味: レイヤーを使った変更は、Blenderのモディファイア（Modifier）として一時的に適用されるだけ。
<br>いつでもオブジェクトを移動したり、調整したり、削除したりでき、最終的に「適用」するまで元のメッシュは変わりません。


### イメージで理解する:
ケーキ作りを想像してください。<br>
ベースのケーキ（ベースメッシュ）に、レイヤー1でクリームを塗る（ADD-1）や型抜きで穴を開ける（SUB-1）、レイヤー2でデコレーションを追加（ADD-2）するような感じ。各レイヤーは独立しているので、クリームの厚さを後から変えたり、穴の位置を調整したりしやすいです。
<br>
<br>
このレイヤーシステムは、SDFのような流動的なモデリングをBlenderの標準機能（コレクションとモディファイア）で実現し、プロトタイピングを速く、実験的に進められるようにしています。<br>

## レイヤーの使い方（基本操作）
SDFusionのUIパネル（3D Viewportのサイドバー、Nキーで表示 > SDFusionタブ）から主に操作します。<br>
なります。<br>

### レイヤーの準備:

ベースとなるメッシュオブジェクトを選択。<br>
UIの「Workflow」セクションで「Reset Booleans & Collections」をクリック。<br>
<br>
これで、ベースのコピーを作成し、初期レイヤー（ADD-1/SUB-1、ADD-2/SUB-2）が自動生成されます。<br>
同時に、Booleanモディファイアが追加され、レイヤー内のオブジェクトがリアルタイムで反映されます。<br>
最後に「GeoRemesh」モディファイア（ジオメトリノードベース）が加わり、ブーリアン後のメッシュを滑らかに調整可能。<br>


### オブジェクトの割り当て（Layer Assignmentセクション）:

カッターオブジェクト（例: 立方体や球体など）を作成または選択。<br>
UIでレイヤーボタンをクリックして、オブジェクトを割り当て。<br>
<br>
例: ADD-1ボタンを押す → オブジェクトがADD-1コレクションに移動し、ベースに追加される。<br>
例: SUB-2ボタンを押す → オブジェクトがSUB-2コレクションに移動し、ベースから削り取られる。<br>
<br>

「SDFusion Pool」: レイヤー外の一時保管庫。まだ使わないオブジェクトをここに置いておけます。<br>
表示の自動調整: レイヤー内のオブジェクトはワイヤーフレームやバウンド表示になり、パフォーマンスを保ちます。<br>

### レイヤーの追加:
もっと階層が必要なら、「Add Layer」をクリック。<br>
<br>
新しいレイヤー（例: ADD-3/SUB-3）が作成され、モディファイアスタックに追加。<br>
無制限に追加可能なので、細かいディテールを段階的に積み重ねられます。<br>
<br>
「Organize Modifiers」: モディファイアの順序を自動整列（GeoRemeshを最後に）。<br>
<br>
### 調整とプレビュー（Live ControlsとTransform Toolsセクション）:
Live Controls: GeoRemeshのパラメータ（メッシュ密度、滑らかさ、シャープネス、エッジ角度など）をスライダーでリアルタイム調整。形状の変化を即座に確認。<br>
Transform Tools: オブジェクトの回転（90°/45°/30°）、ワールド原点への移動、3Dカーソルへのアラインなど、簡単操作で位置調整。<br>
表示カスタマイズ: オブジェクトの表示タイプ（Solid/Wireframe/Bounds）を切り替えたり、オーバーレイをオン/オフ。<br>
<br>

### 最終化（Finalizeセクション）:

「Apply All」: すべてのモディファイアを適用し、最終メッシュを作成。カッターオブジェクトは「SDFusion Cutters」コレクションに移動（非表示）。<br>
「Cleanup All」: 一時コレクションとオブジェクトを削除し、プロジェクトをクリーンに。<br>
結果は「SDFusion Results」コレクションに保存。<br>
## ワークフローの全体像
典型的な流れは以下の通り。非破壊的なので、何度も試行錯誤できます。<br>
<br>
セットアップ: ベースを選択 → Resetでレイヤー初期化。<br>
構築: カッターを作成 → Layer AssignmentでADD/SUBに割り当て → 追加レイヤーで階層を深く。<br>
微調整: Live Controlsで滑らかさをチューニング → Transform Toolsで位置/回転を最適化。<br>
確認と実験: リアルタイムプレビューで形状を確認。気に入らなければオブジェクトをPoolに移動したり、レイヤーを追加/削除。<br>
完了: Apply Allで最終化 → Cleanupで整理。<br>
<br>
この流れで、迅速なプロトタイピングから詳細な最終メッシュ生成まで対応します。<br>

### 利点と注意点

#### 利点:
<br>
直感的で柔軟: レイヤーごとの管理で、複雑なブーリアンを階層的に扱いやすい。鏡面操作（ミラー）もブーリアンで実現可能。<br>
効率的: リアルタイム調整と自動セットアップで、手作業を減らし、パフォーマンスを維持。<br>
実験向き: 非破壊なので、失敗を恐れず形状を探求。資産ライブラリでプロシージャルカッターを即利用。<br>
<br>

#### 注意点:
<br>
レイヤー順序が重要: 低い番号（例: SUB-1）の操作が先に適用されるので、計画的に配置。<br>
オブジェクト制限: 主にメッシュタイプ。プリミティブ（立方体など）から始めましょう。<br>
Blenderバージョン: 4.5以上必須。初回は資産インストールを忘れずに（GeoRemeshノードが必要）。<br>
パフォーマンス: レイヤーが多すぎると重くなる場合、表示をBoundsに切り替えたり、Cleanupを活用。<br>
<br>
## 簡単な例: 穴あき立方体を作成
<br>
ベースとして大きな立方体を選択 → Resetをクリック（レイヤー1/2作成）。<br>
小さな球体を作成 → Layer AssignmentでSUB-1に割り当て → ベースに穴が開く。<br>
円柱を作成 → Add Layerでレイヤー3追加 → ADD-3に割り当て → ベースに円柱が追加。<br>
Transform Toolsで位置/回転調整 → Live Controlsでメッシュ密度を上げて滑らかに。<br>
Apply Allで最終メッシュ生成 → Cleanupでクリーンアップ。<br>
<br>
このように、レイヤーはモデリングを楽しく効率的にします。特にハードサーフェスモデリング（機械部品など）に便利です。<br>

