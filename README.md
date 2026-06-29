# 作品タイトル
Tactical RPG
タクティクRPG

## 作品概要
This project is a 2.5D Tactical RPG heavily inspired by the Disgaea series. It combines strategic, grid-based turn-based combat with high-density progression systems. The game features a distinct visual style where stylized 2D character sprites are placed within a fully 3D, rotatable environment, allowing players to view the tactical battlefield from multiple angles while preserving the charm of classic pixel/2D art.

本作は『ディスガイア』シリーズに強い影響を受けた、2.5DタクティカルRPGです。マス目（グリッド）ベースの戦略的なターン制バトルと、奥深い育成要素を融合させています。完全3Dで構築された回転可能なステージの中に、スタイライズされた2Dキャラクタースプライトを配置する「2.5D」特有の視覚的スタイルを採用しており、クラシックな2Dアートの魅力を活かしつつ、戦況を様々なアングルから見渡せる戦術性を実現しています。

## 使用したUnreal Engine機能
- **Paper 2D / PaperZD:** To be used for managing 2D character sprites, flipbooks, and setting up animation state machines within a 3D world space.
- **Custom Grid-Based Navigation System:** Planned implementation of a custom pathfinding system using arrays and vectors (instead of standard NavMesh) to handle strict grid movement, tile height differences, and attack ranges.
- **Camera System & Spring Arm Components:** To design a 3D rotating camera with fixed 90-degree rotations to allow players to inspect the map without distorting the 2D sprites.
- **Data Tables & Structs:** To be heavily utilized for organizing and scaling massive character stats, class progression tables, and item attributes.

- **Paper 2D / PaperZD:** 3D空間上での2Dキャラクタースプライト、フリップブック、およびアニメーション状態遷移（ステートマシン）の管理に使用予定。
- **グリッドベースのパスファインディング（独自ナビゲーション）:** 通常のNavMeshは使用せず、厳密なグリッド移動、高低差（段差）、攻撃範囲を処理するために、配列とベクトルを用いた独自の経路探索システムを実装予定。
- **カメラシステム ＆ スプリングアームコンポーネント:** 2Dスプライトの見た目を損なうことなく、プレイヤーがマップを自由に見回せるよう、90度ごとの固定回転に対応した3Dカメラシステムを設計予定。
- **マテリアルエディタ（ビルボードシェーダー）:** カメラの回転時に2Dスプライトが「紙のように薄く」見えてしまうのを防ぐため、常にカメラの方向を向く、または特定の軸に固定されるカスタムマテリアルを作成予定。

## 工夫した点
- **Sprite-to-3D Depth Sorting Solution:** Planning to implement custom depth sorting and subtle sprite offsets based on grid positions to prevent 2D character sprites from clipping or intersecting incorrectly with 3D terrain.
- **Height-Dynamic Mechanics:** Intending to factor 3D tile height directly into damage calculations and movement costs, accurately translating 3D environment geometry into 2D gameplay logic.
- **Optimized UI/UX for Grid Selection:** Planning a responsive grid cursor system using Line Traces that translates 3D mouse/controller input into precise 2D grid coordinates for seamless tile selection.

- **スプライトと3D環境の描画順（深度）の最適化:** 2.5Dゲームで頻発する「2Dスプライトが3Dの地形に埋まる」問題を解決するため、グリッド座標に基づいたカスタム深度ソートと、スプライトの微細な位置オフセット処理を実装する予定です。
- **高低差を活かしたゲームメカニクス:** ステージの「高さ（段差）」がダメージ計算や移動コストに影響を与える仕組みを構築し、3D環境の幾何学的な特徴を2Dのゲームロジックへ正確に落とし込むことを目指します。
- **グリッド選択のためのUI/UXの最適化:** ラインベースのトレース（Line Trace）を用いて、3D空間上のマウス/コントローラー入力を正確な2Dグリッド座標に変換し、ストレスのないスムーズなマス目選択カーソルを実現する予定です。