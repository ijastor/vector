-----
# Vector - Linux 설치 가이드


## Vector IDE
***이 프로그램은 [entry-offline](https://github.com/entrylabs/entry-offline) (Entry Labs, Apache 2.0)를 기반으로 제작한 비공식 프로그램 입니다.***  
### **설치 요구사항**
> 4GB의 여유 공간  
> 전원(선택)
-----
### **주요 특징**
- **리소스 제한 해제**: 즉시 업로드 가능한 파일의 용량, 개수를 무제한으로 업데이트 했습니다.
- **확장프로그램 기능(플러그인)** 지원: 아랫 문단에서 설명.

-----
### **설치 방법**
1. [릴리즈 메뉴](https://github.com/ijastor/vector/releases/tag/vector)에 들어가 `Entry-linux-x64_beta-release.tar.gz`를 다운받습니다.
2. 다운로드 한 파일을 원하는 위치에서 압축 해제 합니다.
3. 압축 해제를 완료한 폴더 내 위치에서 터미널을 열고, 아래의 명령어를 입력 합니다.
```bash
chmod +x vector.AppImage
./vector.AppImage --no-sandbox
```
-----
# 확장 프로그램 (플러그인) 가이드
Vector는 **사용자가 직접 플러그인을 제작**하여 **기능을 확장**할 수 있는 구조를 제공합니다. 프로그램 폴더 내 `extension/default/` 경로에 새로운 폴더를 생성해 자신만의 플러그인을 추가해 보세요!

### 플러그인 구조
각 플러그인은 고유한 폴더 내에 `manifest.json` 메타데이터와 `index.js` 실행 스크립트를 포함해야 됩니다. 플러그인은 Entry 객체 인식 후, preload 모듈을 통해 로드됩니다.
- **extension/default/MyPlugin/manifest.json**
```json
{
  "name": "MyPlugin",
  "version": "1.0.0",
  "isExcute": true,
  "description": "Holy Moly Super SUper Powerfu1 Plugin!!!#@!!와우.",
  "developer": "YOURNAME"
}
```
- **extension/default/MyPlugin/index.js**
```javascript
(function() {
    // 원하는 자바스크립트 코드 작성 가능.
    console.log("You complete me.");
})();
```
**기본 플러그인 `EntryTheme`, `vExtensionLoader` 또한 이 작성 구조로 만들어져 있습니다.**

-----
# 당부의 말씀과 TMI
* 참고로 여기서 만들어진 .ent 파일을 **엔트리 공식 웹사이트와 호환**되어서 올릴수 있어요. 이상한 짓만 안해두었다면..
* **메타데이터 편집 기능**이 업데이트 되어질 예정입니다.
* 학업의 문제로 무기한 연기 되어 질 수 있는 부분 양해 부탁드립니다.
* **분명히 윈도우즈에서도 사용 가능하게 배포할 예정입니다.**
* Vector3D(3d 게임 제작에 특화됀 IDE)도 만들거예요. 아주 나중에.
* Andromeda(ai 제작에 특화됀 ide)도 만들거예요. 아아아주 나중에.
* 비공식 런타임 이식도 고려중입니다.
* 커뮤니티 확장 프로그램 (확프라고 부르는것 같던데요.) 확프를 vector 플러그인으로 오토 리빌딩 하는 기능도 고려중인 사안입니다.
* **저를 항상 지켜봐주시고 도와주셨던 분들에게 감사의 말씀을 전합니다.**

-----

## Copyright and License

Entry-Offline Copyright(c) 2018 CONNECT.

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License.  You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
