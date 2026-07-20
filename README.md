# 3DS MIDI Player
​
A MIDI/WAV player and lightweight synthesizer for Nintendo 3DS homebrew.
​
**Languages:** [日本語](#日本語) · [English](#english) · [简体中文](#简体中文) · [한국어](#한국어)
​
[Latest Release](https://github.com/yukkurikasutera3/3ds-midi-player/releases/latest) · [All Releases](https://github.com/yukkurikasutera3/3ds-midi-player/releases) · [Report an issue](https://github.com/yukkurikasutera3/3ds-midi-player/issues)
​
> [!IMPORTANT]
> This is an unofficial homebrew project and is not affiliated with or endorsed by Nintendo. A homebrew-capable Nintendo 3DS is required. The project is still experimental; keep backups of important SD card data.
​
---
​
## 日本語
​
### 概要
​
**3DS MIDI Player**は、Nintendo 3DS向けのMIDI/WAVプレイヤー兼軽量シンセサイザーです。Old 3DSでも動作することを重視しつつ、立体視、タッチ操作、テーマ、可視化など3DSらしい機能を搭載しています。
​
### 主な機能
​
- MIDI再生と、PCM 16-bit WAV（mono/stereo・8～48 kHz）の再生
- 最大64 MIDIトラックの読み込み・編集
- トラックごとの音色、音量、パン、MUTE、SOLO
- テンポ変更、トランスポーズ、マスターボリューム
- 通常、ループ、シャッフル再生
- ディレイ、リバーブ、複数のドラムキット
- OSC、METER、STARS、PIANO、CUBE、SPECT、INFOの表示モード
- Old 3DSを考慮したStereo 3D表示
- MIDIから22.05 kHz / 16-bit / stereo WAVへの書き出し
- ファイル検索・並べ替え・フォルダ移動
- 時計、バッテリー、DSP負荷、発音数の表示
- 複数テーマ（Default、Gaming RGB、Classic Night、Aero Glass、Industrial Synth、DMG LCD、Hakodate Chrono）
- GitHub Releasesを利用した更新確認とCIAダウンロード
​
### インストール
​
#### CIA版（推奨）
​
1. Releasesから最新の`midiplayer.cia`を取得します。
2. SDカードの`sdmc:/cias/`へコピーします。
3. FBIでCIAをインストールします。
4. MIDI/WAVファイルを`sdmc:/midi/`へ配置します。
​
#### 3DSX版
​
1. `midiplayer.3dsx`と必要なファイルを`sdmc:/3ds/MIDIPlayer/`へ配置します。
2. Homebrew Launcherから起動します。
3. MIDI/WAVファイルを`sdmc:/midi/`へ配置します。
​
### 基本操作
​
- ファイル画面：`A`で開く/再生、`B`で戻る、`X`で検索、`Y`で解除/並べ替え
- MIDI選択中：`R + X`でWAV書き出し
- ファイル画面：`SELECT`または`[INFO]`でバージョン/更新画面
- 更新画面：`A`で更新確認・ダウンロード、`B`で戻る
- 再生画面：下画面のPREV / PLAY / STOP / NEXT / MODE / VIEWをタッチ
- 再生中：`SELECT`で設定画面
​
### オンライン更新
​
更新画面で`A`を押すと、GitHub Releasesの`version.json`を確認します。新しいバージョンがある場合、CIAはまず次へ保存されます。
​
```text
sdmc:/cias/midiplayer_update.cia.part
```
​
サイズとSHA-256の一致を確認した後、次へ変更されます。
​
```text
sdmc:/cias/midiplayer_update.cia
```
​
ダウンロード後はFBIでCIAをインストールしてください。Old 3DSとのHTTPS互換性を優先した実装のため、更新時は信頼できるネットワークを使用してください。
​
### ビルド
​
必要なもの：devkitPro / devkitARM、libctru、citro2d、citro3d。CIA生成には`makerom`と`bannertool`も必要です。
​
```text
build.bat          3DSXをビルド
build_cia.bat      CIAをビルド
publish_update.bat CIAをビルドしてGitHub Releaseへ公開
```
​
公開前に`source/updater.h`の`APP_VERSION`と`APP_VERSION_CODE`を更新してください。
​
---
​
## English
​
### Overview
​
**3DS MIDI Player** is a MIDI/WAV player and lightweight synthesizer for Nintendo 3DS homebrew. It is designed with Old 3DS performance in mind while using 3DS features such as stereoscopic visuals, touch controls, themes, and visualizers.
​
### Features
​
- MIDI playback and 16-bit PCM WAV playback (mono/stereo, 8–48 kHz)
- Up to 64 editable MIDI tracks
- Per-track waveform, volume, pan, mute, and solo controls
- Tempo, transpose, and master-volume controls
- Normal, loop, and shuffle playback
- Delay, reverb, and multiple drum kits
- OSC, METER, STARS, PIANO, CUBE, SPECT, and INFO views
- Stereo 3D visual modes designed with Old 3DS performance in mind
- MIDI export to 22.05 kHz, 16-bit stereo WAV
- File search, sorting, and folder navigation
- Clock, battery, active-voice, and DSP-load displays
- Multiple themes, including Hakodate Chrono with time-based backgrounds
- GitHub Releases update checking and CIA downloading
​
### Installation
​
#### CIA version (recommended)
​
1. Download `midiplayer.cia` from the latest Release.
2. Copy it to `sdmc:/cias/`.
3. Install it with FBI.
4. Put MIDI/WAV files in `sdmc:/midi/`.
​
#### 3DSX version
​
1. Copy `midiplayer.3dsx` and its required files to `sdmc:/3ds/MIDIPlayer/`.
2. Launch it from the Homebrew Launcher.
3. Put MIDI/WAV files in `sdmc:/midi/`.
​
### Basic controls
​
- File browser: `A` open/play, `B` parent folder, `X` search, `Y` clear/sort
- Selected MIDI: `R + X` export to WAV
- File browser: press `SELECT` or tap `[INFO]` for version/update information
- Update screen: `A` check/download, `B` back
- Player: use the lower-screen PREV / PLAY / STOP / NEXT / MODE / VIEW controls
- While playing: `SELECT` opens Settings
​
### Online updates
​
The updater reads `version.json` from GitHub Releases. A new CIA is first written to:
​
```text
sdmc:/cias/midiplayer_update.cia.part
```
​
After the file size and SHA-256 are checked, it is renamed to:
​
```text
sdmc:/cias/midiplayer_update.cia
```
​
Install the downloaded CIA with FBI. For Old 3DS HTTPS compatibility, use a trusted network when checking for updates.
​
### Building
​
Requirements: devkitPro/devkitARM, libctru, citro2d, and citro3d. CIA packaging also requires `makerom` and `bannertool`.
​
```text
build.bat          Build the 3DSX
build_cia.bat      Build the CIA
publish_update.bat Build and publish a GitHub Release
```
​
Update `APP_VERSION` and `APP_VERSION_CODE` in `source/updater.h` before publishing.
​
---
​
## 简体中文
​
### 简介
​
**3DS MIDI Player** 是面向 Nintendo 3DS 自制软件环境的 MIDI/WAV 播放器和轻量级合成器。项目兼顾 Old 3DS 的性能，并支持立体显示、触摸操作、主题和多种可视化模式。
​
### 主要功能
​
- 播放MIDI以及16-bit PCM WAV（单声道/立体声，8～48 kHz）
- 最多64条可编辑MIDI轨道
- 每轨音色、音量、声像、静音和独奏
- 速度、移调、总音量、循环与随机播放
- 延迟、混响和多种鼓组
- 多种可视化模式与Stereo 3D显示
- 将MIDI导出为22.05 kHz / 16-bit / stereo WAV
- 文件搜索、排序、时钟、电池和DSP负载显示
- 多种主题与GitHub在线更新
​
### 安装
​
**CIA（推荐）：** 从Releases下载`midiplayer.cia`，复制到`sdmc:/cias/`，使用FBI安装。将MIDI/WAV文件放入`sdmc:/midi/`。
​
**3DSX：** 将程序放入`sdmc:/3ds/MIDIPlayer/`，从Homebrew Launcher启动。
​
### 在线更新
​
在文件浏览器按`SELECT`或触摸`[INFO]`，然后按`A`检查更新。下载文件经过大小和SHA-256检查后保存为：
​
```text
sdmc:/cias/midiplayer_update.cia
```
​
随后使用FBI安装。为兼容Old 3DS的HTTPS环境，请在可信网络中更新。
​
### 编译
​
需要devkitPro/devkitARM、libctru、citro2d和citro3d。CIA还需要`makerom`和`bannertool`。发布前请更新`source/updater.h`中的版本号。
​
---
​
## 한국어
​
### 소개
​
**3DS MIDI Player**는 Nintendo 3DS 홈브류용 MIDI/WAV 플레이어이자 경량 신시사��저입니다. Old 3DS 성능을 고려하면서 입체 화면, 터치 조작, 테마와 여러 시각화 모드를 지원합니다.
​
### 주요 기능
​
- MIDI 및 16-bit PCM WAV 재생(mono/stereo, 8~48 kHz)
- 최대 64개의 편집 가능한 MIDI 트랙
- 트랙별 음색, 볼륨, 팬, 음소거 및 솔로
- 템포, 트랜스포즈, 마스터 볼륨, 반복 및 셔플 재생
- 딜레이, 리버브와 여러 드럼 키트
- 다양한 시각화 모드와 Stereo 3D 표시
- MIDI를 22.05 kHz / 16-bit / stereo WAV로 내보내기
- 파일 검색/정렬, 시계, 배터리 및 DSP 부하 표시
- 여러 테마와 GitHub 온라인 업데이트
​
### 설치
​
**CIA(권장):** Releases에서`midiplayer.cia`를 내려받아`sdmc:/cias/`에 복사한 뒤 FBI로 설치합니다. MIDI/WAV 파일은`sdmc:/midi/`에 넣습니다.
​
**3DSX:** 프로그램을`sdmc:/3ds/MIDIPlayer/`에 복사하고 Homebrew Launcher에서 실행합니다.
​
### 온라인 업데이트
​
파일 브라우저에서`SELECT`또는`[INFO]`를 누른 후`A`로 업데이트를 확인합니다. 크기와 SHA-256을 확인한 CIA는 다음 위치에 저장됩니다.
​
```text
sdmc:/cias/midiplayer_update.cia
```
​
그 후 FBI로 설치합니다. Old 3DS HTTPS 호환을 위해 신뢰할 수 있는 네트워크에서 업데이트하세요.
​
### 빌드
​
devkitPro/devkitARM, libctru, citro2d, citro3d가 필요합니다. CIA 생성에는`makerom`과`bannertool`도 필요합니다. 배포하기 전에`source/updater.h`의 버전 번호를 변경하세요.
​
---
​
## Project status / プロジェクト状況
​
This project is under active development. Bug reports should include the console model (Old/New 3DS), app version, build type (CIA/3DSX), and the complete error code.
​
開発中のプロジェクトです。不具合報告には、本体モデル（Old/New 3DS）、アプリのバージョン、CIA/3DSXの別、エラーコード全文を含めてください。
​
## License
​
A license has not been selected yet. Licensing information will be added before a stable public release.
​
