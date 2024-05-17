## REACT-NATIVE-NAVER-MAP Sample Project

이 프로젝트는 [네이버 지도 라이브러리](https://github.com/mym0404/react-native-naver-map)를 테스트하다가 이슈가 발생하여 제보하기 위해 만들어졌습니다.  
AndroidManifest 와 Info.plist 의 apiKey 값은 보안상 제거했습니다.  
React-Native 0.71.1 버전에서 iOS가 빌드에는 성공하지만 실행시 오류가 발생합니다.

### Install
```bash
# 1. 프로젝트 설치 (react-native@0.71.0)
> npx react-native init mapSample --version=0.71.0

# 2. 라이브러리 설치
> yarn add @mj-studio/react-native-naver-map
```

### Result
```bash
> ERROR
Error setting property 'clusters' of RNCNaverMapView with tag #3: JSON value '{
    clusters =     (
    );
    key = "";
}' of type NSMutableDictionary cannot be converted to NSArray
```
