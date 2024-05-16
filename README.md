## REACT-NATIVE-NAVER-MAP Sample Project

이 프로젝트는 [네이버 지도 라이브러리](https://github.com/mym0404/react-native-naver-map)를 테스트하다가 이슈가 발생하여 제보하기 위해 만들어졌습니다.
React-Native 0.71 버전에서 해당 라이브러리를 설치시 안드로이드 실행에 문제가 발생합니다.

### Install
```bash
# 1. 프로젝트 설치 (react-native@0.71.0)
> npx react-native init mapSample --version=0.71.0

# 2. 라이브러리 설치
> yarn add @mj-studio/react-native-naver-map

# 3. 안드로이드 셋팅
# @see : https://github.com/mym0404/react-native-naver-map
# android/build.gradle 및 AndroidManifest.xml 키 삽입(보안상 없앰)
```

### Result
빌드는 성공적으로 수행되지만 앱이 구동되지 않습니다.

다음과 같은 오류가 발생합니다
#### Android LogCat

``` bash
> ERROR
Failed to create NativeModule "UIManager"
    java.lang.UnsupportedOperationException
        at java.util.AbstractMap.put(AbstractMap.java:209)
        at com.facebook.react.uimanager.UIManagerModuleConstantsHelper.recursiveMerge(UIManagerModuleConstantsHelper.java:160)
        at com.facebook.react.uimanager.UIManagerModuleConstantsHelper.recursiveMerge(UIManagerModuleConstantsHelper.java:158)
        at com.facebook.react.uimanager.UIManagerModuleConstantsHelper.createConstantsForViewManager(UIManagerModuleConstantsHelper.java:125)
        at com.facebook.react.uimanager.UIManagerModuleConstantsHelper.createConstants(UIManagerModuleConstantsHelper.java:91)
        at com.facebook.react.uimanager.UIManagerModule.createConstants(UIManagerModule.java:246)
        at com.facebook.react.uimanager.UIManagerModule.<init>(UIManagerModule.java:146)
        at com.facebook.react.CoreModulesPackage.createUIManager(CoreModulesPackage.java:195)
        at com.facebook.react.CoreModulesPackage.getModule(CoreModulesPackage.java:160)
        at com.facebook.react.TurboReactPackage$ModuleHolderProvider.get(TurboReactPackage.java:161)
        at com.facebook.react.TurboReactPackage$ModuleHolderProvider.get(TurboReactPackage.java:149)
        at com.facebook.react.bridge.ModuleHolder.create(ModuleHolder.java:191)
        at com.facebook.react.bridge.ModuleHolder.getModule(ModuleHolder.java:156)
        at com.facebook.react.bridge.NativeModuleRegistry.getModule(NativeModuleRegistry.java:170)
        at com.facebook.react.bridge.CatalystInstanceImpl.getNativeModule(CatalystInstanceImpl.java:493)
        at com.facebook.react.bridge.CatalystInstanceImpl.getNativeModule(CatalystInstanceImpl.java:469)
        at com.facebook.react.uimanager.UIManagerHelper.getUIManager(UIManagerHelper.java:89)
        at com.facebook.react.uimanager.UIManagerHelper.getUIManager(UIManagerHelper.java:47)
        at com.facebook.react.ReactInstanceManager.attachRootViewToInstance(ReactInstanceManager.java:1241)
        at com.facebook.react.ReactInstanceManager.setupReactContext(ReactInstanceManager.java:1183)
        at com.facebook.react.ReactInstanceManager.access$1600(ReactInstanceManager.java:135)
        at com.facebook.react.ReactInstanceManager$5$2.run(ReactInstanceManager.java:1137)
        at android.os.Handler.handleCallback(Handler.java:958)
        at android.os.Handler.dispatchMessage(Handler.java:99)
        at com.facebook.react.bridge.queue.MessageQueueThreadHandler.dispatchMessage(MessageQueueThreadHandler.java:27)
        at android.os.Looper.loopOnce(Looper.java:230)
        at android.os.Looper.loop(Looper.java:319)
        at com.facebook.react.bridge.queue.MessageQueueThreadImpl$4.run(MessageQueueThreadImpl.java:228)

> ERROR
ReactInstanceManager caught exception in setupReactContext
    java.lang.UnsupportedOperationException
        at java.util.AbstractMap.put(AbstractMap.java:209)
        at com.facebook.react.uimanager.UIManagerModuleConstantsHelper.recursiveMerge(UIManagerModuleConstantsHelper.java:160)
        at com.facebook.react.uimanager.UIManagerModuleConstantsHelper.recursiveMerge(UIManagerModuleConstantsHelper.java:158)
        at com.facebook.react.uimanager.UIManagerModuleConstantsHelper.createConstantsForViewManager(UIManagerModuleConstantsHelper.java:125)
        at com.facebook.react.uimanager.UIManagerModuleConstantsHelper.createConstants(UIManagerModuleConstantsHelper.java:91)
        at com.facebook.react.uimanager.UIManagerModule.createConstants(UIManagerModule.java:246)
        at com.facebook.react.uimanager.UIManagerModule.<init>(UIManagerModule.java:146)
        at com.facebook.react.CoreModulesPackage.createUIManager(CoreModulesPackage.java:195)
        at com.facebook.react.CoreModulesPackage.getModule(CoreModulesPackage.java:160)
        at com.facebook.react.TurboReactPackage$ModuleHolderProvider.get(TurboReactPackage.java:161)
        at com.facebook.react.TurboReactPackage$ModuleHolderProvider.get(TurboReactPackage.java:149)
        at com.facebook.react.bridge.ModuleHolder.create(ModuleHolder.java:191)
        at com.facebook.react.bridge.ModuleHolder.getModule(ModuleHolder.java:156)
        at com.facebook.react.bridge.NativeModuleRegistry.getModule(NativeModuleRegistry.java:170)
        at com.facebook.react.bridge.CatalystInstanceImpl.getNativeModule(CatalystInstanceImpl.java:493)
        at com.facebook.react.bridge.CatalystInstanceImpl.getNativeModule(CatalystInstanceImpl.java:469)
        at com.facebook.react.uimanager.UIManagerHelper.getUIManager(UIManagerHelper.java:89)
        at com.facebook.react.uimanager.UIManagerHelper.getUIManager(UIManagerHelper.java:47)
        at com.facebook.react.ReactInstanceManager.attachRootViewToInstance(ReactInstanceManager.java:1241)
        at com.facebook.react.ReactInstanceManager.setupReactContext(ReactInstanceManager.java:1183)
        at com.facebook.react.ReactInstanceManager.access$1600(ReactInstanceManager.java:135)
        at com.facebook.react.ReactInstanceManager$5$2.run(ReactInstanceManager.java:1137)
        at android.os.Handler.handleCallback(Handler.java:958)
        at android.os.Handler.dispatchMessage(Handler.java:99)
        at com.facebook.react.bridge.queue.MessageQueueThreadHandler.dispatchMessage(MessageQueueThreadHandler.java:27)
        at android.os.Looper.loopOnce(Looper.java:230)
        at android.os.Looper.loop(Looper.java:319)
        at com.facebook.react.bridge.queue.MessageQueueThreadImpl$4.run(MessageQueueThreadImpl.java:228)

> ERROR
Exception in native call
    java.lang.UnsupportedOperationException
        at java.util.AbstractMap.put(AbstractMap.java:209)
        at com.facebook.react.uimanager.UIManagerModuleConstantsHelper.recursiveMerge(UIManagerModuleConstantsHelper.java:160)
        at com.facebook.react.uimanager.UIManagerModuleConstantsHelper.recursiveMerge(UIManagerModuleConstantsHelper.java:158)
        at com.facebook.react.uimanager.UIManagerModuleConstantsHelper.createConstantsForViewManager(UIManagerModuleConstantsHelper.java:125)
        at com.facebook.react.uimanager.UIManagerModuleConstantsHelper.createConstants(UIManagerModuleConstantsHelper.java:91)
        at com.facebook.react.uimanager.UIManagerModule.createConstants(UIManagerModule.java:246)
        at com.facebook.react.uimanager.UIManagerModule.<init>(UIManagerModule.java:146)
        at com.facebook.react.CoreModulesPackage.createUIManager(CoreModulesPackage.java:195)
        at com.facebook.react.CoreModulesPackage.getModule(CoreModulesPackage.java:160)
        at com.facebook.react.TurboReactPackage$ModuleHolderProvider.get(TurboReactPackage.java:161)
        at com.facebook.react.TurboReactPackage$ModuleHolderProvider.get(TurboReactPackage.java:149)
        at com.facebook.react.bridge.ModuleHolder.create(ModuleHolder.java:191)
        at com.facebook.react.bridge.ModuleHolder.getModule(ModuleHolder.java:156)
        at com.facebook.react.bridge.NativeModuleRegistry.getModule(NativeModuleRegistry.java:170)
        at com.facebook.react.bridge.CatalystInstanceImpl.getNativeModule(CatalystInstanceImpl.java:493)
        at com.facebook.react.bridge.CatalystInstanceImpl.getNativeModule(CatalystInstanceImpl.java:469)
        at com.facebook.react.uimanager.UIManagerHelper.getUIManager(UIManagerHelper.java:89)
        at com.facebook.react.uimanager.UIManagerHelper.getUIManager(UIManagerHelper.java:47)
        at com.facebook.react.ReactInstanceManager.attachRootViewToInstance(ReactInstanceManager.java:1241)
        at com.facebook.react.ReactInstanceManager.setupReactContext(ReactInstanceManager.java:1183)
        at com.facebook.react.ReactInstanceManager.access$1600(ReactInstanceManager.java:135)
        at com.facebook.react.ReactInstanceManager$5$2.run(ReactInstanceManager.java:1137)
        at android.os.Handler.handleCallback(Handler.java:958)
        at android.os.Handler.dispatchMessage(Handler.java:99)
        at com.facebook.react.bridge.queue.MessageQueueThreadHandler.dispatchMessage(MessageQueueThreadHandler.java:27)
        at android.os.Looper.loopOnce(Looper.java:230)
        at android.os.Looper.loop(Looper.java:319)
        at com.facebook.react.bridge.queue.MessageQueueThreadImpl$4.run(MessageQueueThreadImpl.java:228)
```
