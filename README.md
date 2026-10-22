# NEON PULSAR — ネオンパルサー | 霓虹脉冲

一本のHTMLファイルで動く、3レーン形式の3Dリズムアクションゲーム。
A 3-lane 3D rhythm action game in a single HTML file.
单个 HTML 文件即可运行的三轨道 3D 节奏动作游戏。

---

## 日本語

### 概要
ネオンの軌道上に流れてくるノート（キューブ）を、判定ラインで3レーンのいずれかをタップして叩くリズムゲームです。PCとスマートフォンに対応し、画面は縦（9:16）レイアウトです。ステージごとにビートシンクしたBGMがWebAudioで合成され、叩いた音は物理演算で立方体が飛び散ります。

### 起動方法
1. index.html をブラウザ（最新版の Chrome / Edge / Safari 推奨）で開きます。
2. Three.js と cannon-es を CDN（jsDelivr）から読み込むため、インターネット接続が必要です。
3. スマートフォンの場合は index.html を端末にコピーしてブラウザで開くと、縦画面でそのまま遊べます。

### 遊び方
- 奥から手前へ流れてくるノートを、判定ラインに重なった瞬間に該当レーンをタップします。
- 判定は PERFECT / GREAT / GOOD / MISS の4段階で、コンボとスコアが伸びます。
- 精度（PERFECT+GREAT+GOODの割合）により SS〜F のグレードと星1〜3がつき、星1以上でクリア、次のステージが解放されます。
- ステージ開始前に4拍のカウントインが入ります。
- ステージ詳細画面のオーディオオフセットスライダー（-100〜+100ms）で、音と表示のズレを補正できます。

### 操作
- タップ：左 / 中央 / 右の3レーン（画面を3分割した位置をタップ）
- PCキー：← ↓ → または D / F / J キーで各レーン
- P キー / Escキー / 一時停止ボタン：ポーズ
- タイトル画面：言語切り替え（日本語 / English / 中文）、サウンド ON / OFF

### ステージ
全15ステージ。BPM100〜200、難易度1〜7で、ドラムパターンとノート密度が段階的に濃くなります。コード進行は4種類（Am-F-C-G系など）からステージごとに選ばれ、ノート譜面はステージごとの決定論的乱数で毎回同じ並び順に生成されます。クリアすると次のステージが解放されます。

### セーブデータ
ブラウザの localStorage（キー名 neonpulsar_save_v1）に、解放済みステージ・各ステージのベストスコア／精度／最大コンボ／グレード・星・言語・サウンド設定・オーディオオフセットが保存されます。削除する場合はブラウザ設定からこのサイトのデータ（サイト設定 / ストレージ）を消去してください。

### 技術
- Three.js 0.160（描画）と cannon-es 0.20（物理・飛散デブリ）を ES モジュールとして CDN 読み込み
- BGM（キック／スネア／ハイハット／ベース／コード）と効果音は WebAudio API で手続き生成（外部音声ファイルなし）。AC.currentTime をマスタークロックとして譜面と音楽を同期
- 縦長9:16レターボックスフレーム、UIスケールは画面サイズに追従
- 外部アセット不要の単一ファイル構成

---

## English

### Overview
A 3-lane rhythm game where neon note cubes stream toward you along an orbital track — tap the matching lane right on the judgement line. Runs on PC and smartphone in portrait (9:16) layout. Each stage's BGM is synthesized live in sync with the beat, and hits scatter cubes with real physics.

### How to Run
1. Open index.html in a modern browser (latest Chrome / Edge / Safari recommended).
2. Internet access is required because Three.js and cannon-es are loaded from the jsDelivr CDN.
3. On a phone, copy index.html to the device and open it in a mobile browser — it is ready to play in portrait.

### How to Play
- Notes flow from the far end toward the judgement line; tap the correct lane exactly as a note crosses it.
- Judgements: PERFECT / GREAT / GOOD / MISS, building combo and score.
- Accuracy yields a grade SS through F and 1–3 stars; 1 star or more clears the stage and unlocks the next one.
- A four-beat count-in leads into every stage.
- The audio offset slider (-100 to +100 ms) on the stage detail screen lets you correct audio/visual lag.

### Controls
- Tap: left / center / right lane (the screen is split into three vertical thirds)
- PC keys: ← ↓ → or D / F / J for each lane
- P / Esc / pause button: pause

### Stages
15 stages, BPM 100–200, difficulty 1–7 with progressively denser drum patterns and note density. Four chord progressions (Am-F-C-G family and friends) are picked per stage, and each stage's chart is generated from a deterministic per-stage seed — the same note layout every time. Clearing a stage unlocks the next.

### Save Data
Unlocked stages, per-stage best score / accuracy / max combo / grade, stars, language, sound setting and audio offset are stored in browser localStorage under the key neonpulsar_save_v1. To erase them, clear this site's data (site settings / storage) in your browser settings.

### Tech Notes
- Three.js 0.160 (rendering) and cannon-es 0.20 (physics debris) loaded as ES modules from CDN
- BGM (kick / snare / hi-hat / bass / chords) and SFX are procedurally generated with the WebAudio API — no audio files; AC.currentTime is the master clock that keeps the chart and music in sync
- Portrait 9:16 letterboxed frame with a UI scale that follows screen size
- Single-file game with no external assets

---

## 中文

### 简介
霓虹方块音符沿着轨道从远处飞来，在判定线与三条轨道之一精准契合时点击即可。支持电脑和智能手机，采用竖屏（9:16）布局的 3D 节奏动作游戏。每个关卡的 BGM 由 WebAudio 实时合成并与节拍同步，击中时立方体会以物理运算飞散。

### 运行方法
1. 用浏览器（推荐最新版 Chrome / Edge / Safari）打开 index.html。
2. Three.js 和 cannon-es 从 CDN（jsDelivr）加载，需要联网。
3. 手机玩家可将 index.html 复制到设备上，用移动浏览器打开即可竖屏游玩。

### 玩法
- 音符从远处流向判定线，在音符与判定线重合的瞬间点击对应轨道。
- 判定分为 PERFECT / GREAT / GOOD / MISS 四档，累积连击与得分。
- 根据正确率评定 SS〜F 等级并给出 1〜3 星，获得 1 星以上即过关并解锁下一关。
- 每关开始前有 4 拍倒计时。
- 关卡详情页的音频偏移滑块（-100〜+100ms）可校正音画不同步。

### 操作
- 点击：左 / 中 / 右轨道（屏幕纵向三等分）
- 电脑按键：← ↓ → 或 D / F / J 对应各轨道
- P 键 / Esc 键 / 暂停按钮：暂停

### 关卡
共 15 关。BPM 100〜200、难度 1〜7，鼓点型与音符密度逐级加密。和弦进行共 4 种（Am-F-C-G 系等）按关卡选取，每关谱面由该关的固定随机种子生成，每次游玩音符排列完全相同。过关后解锁下一关。

### 存档
已解锁关卡、各关最佳得分／正确率／最大连击／等级、星级、语言、音效开关和音频偏移保存在浏览器的 localStorage（键名 neonpulsar_save_v1）中。如需删除，请在浏览器设置中清除本站点数据（网站设置 / 存储）。

### 技术说明
- Three.js 0.160（渲染）与 cannon-es 0.20（物理飞散碎块）以 ES 模块方式从 CDN 加载
- BGM（底鼓／军鼓／踩镲／贝斯／和弦）与音效由 WebAudio API 程序化生成（无外部音频文件），以 AC.currentTime 作为主时钟实现谱面与音乐同步
- 竖屏 9:16 信箱式画面，UI 缩放随屏幕尺寸自适应
- 无需外部素材的单文件游戏
