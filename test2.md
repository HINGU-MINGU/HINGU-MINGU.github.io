# Playing haptics

Assign: Seokjun Ko
Status: Done
Due: August 16, 2023
VisionOS 추가 여부: 해당없음
대분류: Pattern

Playing haptics can engage people’s sense of touch and bring their familiarity with the physical world into your app or game.

햅틱을 재생하면 사용자의 촉각을 활용하여 물리적 세계의 친숙한 경험을 앱이나 게임으로 가져올 수 있습니다.

![https://docs-assets.developer.apple.com/published/367115f42d7b6235a3087fd140366955/patterns-playing-haptics-intro@2x.png](https://docs-assets.developer.apple.com/published/367115f42d7b6235a3087fd140366955/patterns-playing-haptics-intro@2x.png)

The system can play haptics in addition to visual and auditory feedback to communicate things like the confirmation of an Apple Pay transaction or the arrival of a notification in iOS and watchOS. On a Mac that’s equipped with a Force Touch trackpad, apps can play haptics while people are dragging content or respond to different strengths of a force click to cause different levels of change in an onscreen element. In a tvOS or iPadOS app, game controllers can provide haptic feedback.

시스템은 시각적 및 청각적 피드백과 함께 햅틱을 재생하여 iOS와 watchOS에서 Apple Pay 거래 확인이나 알림 도착과 같은 사항을 전달할 수 있습니다. Mac에서는 Force Touch 트랙패드가 장착된 경우, 앱은 사람들이 콘텐츠를 드래그하는 동안 햅틱스를 재생하거나 강한 클릭의 다른 강도에 반응하여 화면 요소에 다른 수준의 변화를 유발할 수 있습니다. tvOS나 iPadOS 앱에서는 게임 컨트롤러가 햅틱 피드백을 제공할 수 있습니다.

***→ iOS, watchOS: 시청각 피드백 + 햅틱***

***Mac: Force Touch 트랙패드 or tvOS, iPadOS 게임 컨트롤러: 햅틱***

- 역자참조
    
    iPad는 기기 자체에서 Haptics 자체를 제공하지 않는다.
    

Depending on the platform, the system may provide haptic feedback for standard components by default. For example, components like switches, sliders, and pickers automatically play haptic feedback on supported iPhone models; on Apple Watch, the Taptic Engine generates haptics and watchOS combines an audible tone with some of them. In addition, the system may provide built-in haptic patterns you can use in your app or game or even let you design custom ones.

플랫폼에 따라 시스템은 기본적으로 표준 구성 요소에 대해 햅틱 피드백을 제공할 수 있습니다. 예를 들어, 스위치, 슬라이더, 피커와 같은 구성 요소는 지원하는 iPhone 모델에서 자동으로 햅틱 피드백을 재생합니다. Apple Watch의 경우, Taptic 엔진이 햅틱을 생성하며 일부는 watchOS와 함께 가청음을 결합합니다. 또한 시스템은 앱이나 게임에서 사용할 수 있는 내장된 햅틱 패턴을 제공하거나 사용자 정의 햅틱 패턴을 디자인할 수도 있습니다.

→ 스위치, 피커 등 제공되는 components를 사용하면, 기본으로 haptis를 제공한다. Apple에서 제공하는 햅틱 패턴을 사용하거나 직접 햅틱 패턴을 만들어 서비스에 활용할 수 있다.

## [**Best practices**](https://developer.apple.com/design/human-interface-guidelines/playing-haptics#Best-practices)

**Use system-provided haptic patterns according to their documented meanings.** People recognize standard haptics because the system plays them consistently on interactions with standard controls. If the documented use case for a pattern doesn’t make sense in your app, use a generic pattern or create your own, where supported. For guidance, see [Custom haptics](https://developer.apple.com/design/human-interface-guidelines/playing-haptics#Custom-haptics).

**시스템 제공 햅틱 패턴을 문서화 된 의미에 따라 사용하세요.** 시스템이 표준 컨트롤과 상호작용할 때 항상 같은 햅틱을 재생시키기 때문에, 사용자들은 표준적인 햅틱을 일관성 있게 인지한다. 만약 문서화 된 사용 사례가 앱에 맞지 않는다면, 지원되는 경우 일반적인 패턴을 사용하거나 직접 만들어 사용하세요. 자세한 지침은 **[Custom haptics](https://developer.apple.com/design/human-interface-guidelines/playing-haptics#Custom-haptics)**을 참고하세요.

***→ 사용자들은 여러 종류의 햅틱에 해당하는 의미를 대략적으로 파악하고 있음을 인지하고, 햅틱의 일반적인 의미를 따라 사용할지 커스텀 할지 결정하라***

**Use haptics consistently.** It’s important to build a clear, causal relationship between each haptic and the action that causes it so people learn to associate certain haptic patterns with certain experiences. If a haptic doesn’t reinforce a cause-and-effect relationship, it can be confusing and seem gratuitous. For example, if your app plays a specific haptic pattern when a game character fails to finish a mission, people associate that pattern with a negative outcome. If you use the same haptic pattern for a positive outcome like a level completion, people will be confused.

**햅틱을 일관성 있게 사용하세요.** 각 햅틱과 그것을 발생시키는 작업 사이에 명확한 원인과 결과 관계를 구축하는 것이 중요합니다. 이렇게 함으로써 사용자들은 특정 경험과 특정 햅틱 패턴을 연관짓게 됩니다. 원인과 결과 관계를 강조하지 않는 햅틱은 혼란스러울 수 있으며, 불필요해 보일 수 있습니다. 예를 들어, 앱이 게임 캐릭터가 미션을 완료하지 못했을 때 특정 햅틱 패턴을 재생한다면, 사용자들은 그 패턴을 부정적인 결과와 연관짓게 됩니다. 만약 동일한 햅틱 패턴을 레벨 완료와 같은 긍정적인 결과에 사용한다면, 사용자들은 혼란스러워질 것입니다.

***→ 특정 원인 또는 경험에 특정 햅틱 패턴을 발생시키는 관계를 명확히 해라.***

**Use haptics in ways that complement other feedback in your app.** When visual, auditory, and tactile feedback are in harmony — as they generally are in the physical world — the user experience is more coherent and can seem more natural. For example, match the intensity and sharpness of a haptic with the animation you use to accompany it. You can also synchronize sound with haptics; for developer guidance, see [Delivering Rich App Experiences with Haptics](https://developer.apple.com/documentation/corehaptics/delivering_rich_app_experiences_with_haptics).

**햅틱을 다른 피드백과 조화롭게 사용하세요.** 시각적, 청각적, 촉각적 피드백이 조화롭게 조합되는 경우(일반적으로 물리적 세계에서 그렇듯) 사용자 경험은 더 일관되고 자연스러워집니다. 예를 들어, 햅틱의 강도와 선명도를 해당 햅틱과 동반하는 애니메이션과 일치 시키세요. 햅틱과 소리를 동기화할 수도 있습니다. 자세한 개발자 지침은 **[Delivering Rich App Experiences with Haptics](https://developer.apple.com/documentation/corehaptics/delivering_rich_app_experiences_with_haptics)**를 참고하세요.

***→ 햅틱과 다른 피드백(시각, 청각)을 적절하게 조합하여 제공하라.***

**Avoid overusing haptics.** Sometimes a haptic can feel just right when it happens occasionally, but become tiresome when it plays frequently. It’s important to do user testing that can help you discover a balance that most people appreciate. Often, the best haptic experience is one that people may not be conscious of, but miss when it’s turned off.

**햅틱의 과도한 사용은 피하세요.** 때때로 햅틱은 가끔 일어날 때 딱 맞는 것처럼 느껴질 수 있지만, 빈번하게 재생되면 지루함을 유발할 수 있습니다. 대다수의 사용자가 즐거워하는 균형을 찾기 위해 사용자 테스트를 수행하는 것이 중요합니다. 종종, 가장 좋은 햅틱 경험은 사용자들이 의식하지 못하지만, 끄면 그것을 놓치는 경험이 될 수 있습니다.

***→ 햅틱 서비스의 최적의 빈도를 찾기 위해 테스트를 해보라***

**Make haptics optional.** Let people turn off or mute haptics if they wish, and make sure people can still enjoy your app without them.

**햅틱을 선택적으로 사용할 수 있도록 합니다.** 사용자들이 원하는 경우 햅틱을 끄거나 음소거할 수 있도록 해 주세요. 또한 사용자들이 햅틱 없이도 앱을 즐길 수 있도록 해야 합니다.

**Be aware that playing haptics might impact other user experiences.** By design, haptics produce enough physical force for people to feel the vibration. Ensure that haptic vibrations don’t disrupt user experiences involving the camera, gyroscope, or microphone.

**햅틱 재생이 다른 사용자 경험에 영향을 미칠 수 있다는 점을 유의하세요.** 설계적으로, 햅틱은 사용자가 진동을 느낄 수 있을만큼 충분한 물리적인 힘을 생성합니다. 햅틱 진동이 카메라, 자이로스코프 또는 마이크를 포함하는 사용자 경험을 방해하지 않도록 해야 합니다.

***→ 햅틱 진동을 카메라, 자이로스코프, 마이크 등의 사용자 경험을 방해하지 않게 하며 사용해야 한다.***

## **[Custom haptics](https://developer.apple.com/design/human-interface-guidelines/playing-haptics#Custom-haptics)**

Games often use custom haptics to enhance gameplay. Although it’s less common, nongame apps might also use custom haptics to provide a richer, more delightful experience.

게임은 종종 게임플레이를 강화하기 위해 커스텀 햅틱을 사용합니다. 흔하지 않지만, 비게임 앱도 더 풍부하고 즐거운 경험을 제공하기 위해 커스텀 햅틱을 사용할 수 있습니다.

You can design custom haptic patterns that vary dynamically, based on user input or context. For example, the impact players feel when a game character jumps from a tree can be stronger than when the character jumps in place, and substantial experiences — like a collision or a hit — can feel very different from subtle experiences like the approach of footsteps or a looming danger.

사용자 입력이나 문맥에 따라 동적으로 변하는 커스텀 햅틱 패턴을 디자인할 수 있습니다. 예를 들어, 게임 캐릭터가 나무에서 점프할 때 느끼는 충격은 그 캐릭터가 움직이지 않을 때보다 더 세게 느낄 수 있으며, 충돌이나 히트와 같은 큰 경험은 발걸음이 다가오거나 위협적인 상황과 같은 미묘한 경험과 매우 다를 수 있습니다.

***→ 상황에 맞게 커스텀 햅틱을 하는 예시***

There are two basic building blocks you can use to generate custom haptic patterns.

커스텀 햅틱 패턴을 생성하기 위해 사용할 수 있는 두 가지 **기본적인 빌딩 블록**이 있습니다.

- *Transient* events are brief and compact, often feeling like taps or impulses. The experience of tapping the Flashlight button on the Home Screen is an example of a transient event.

Transient events*은 짧고 간결하며 탭이나 임펄스와 같은 느낌을 주로 줍니다. 홈 화면의 플래시라이트 버튼을 탭하는 경험은 일시적 이벤트의 예입니다.

- *Continuous* events feel like sustained vibrations, such as the experience of the lasers effect in a message.

Continuous events*는 지속적인 진동과 같은 느낌입니다. 예를 들어 메시지의 레이저 효과와 같은 경험이 있습니다.

Regardless of the type of haptic event you use to generate a custom haptic, you can also control its *sharpness* and *intensity*. You can think of sharpness as a way to abstract a haptic experience into the waveform that produces the corresponding physical sensations. Specifying sharpness lets you relay to the system your intent for the experience. For example, you might use sharpness values to convey an experience that’s soft, rounded, or organic, or one that’s crisp, precise, or mechanical. As the term implies, intensity means the strength of the haptic.

커스텀 햅틱을 생성하기 위해 사용하는 햅틱 이벤트의 종류에 관계없이 *날카로움(sharpness)*과 *강도(intensity)*를 조절할 수도 있습니다. 날카로움은 해당 햅틱 경험을 생성하는데 사용되는 파형을 추상화하는 방법으로, 시스템에게 경험에 대한 의도를 전달합니다. 예를 들어, 날카로움 값을 사용하여 부드럽고 둥근 경험이나 정밀하고 기계적인 경험과 같은 경험을 전달할 수 있습니다. 강도는 햅틱의 강도를 의미합니다.

***→ 커스텀 햅틱 생성시, sharpness와 intensity를 조절할 수 있다.***

- 역자참조
    
    ```swift
    let intensity = CHHapticEventParameter(parameterID: .hapticIntensity, value: 0.7)
    let sharpness = CHHapticEventParameter(parameterID: .hapticSharpness, value: 0.5)
    let event = CHHapticEvent(eventType: .hapticTransient, parameters: [intensity, sharpness], relativeTime: i, duration: 10)
    ```
    
    sharpness가 높으면, 강하고 정교한 진동을 생성
    
    sharpness가 낮으면, 부드럽고 라운드한 진동 생성
    

By combining transient and continuous events, varying sharpness and intensity, and including optional audio content, you can create a wide range of different haptic experiences. For developer guidance, see [Core Haptics](https://developer.apple.com/documentation/corehaptics).

일시적 이벤트와 연속적 이벤트를 조합하고, 날카로움과 강도를 다양하게 변화시키며, 선택적 오디오 콘텐츠를 포함하여 다양한 햅틱 경험을 만들 수 있습니다. 자세한 개발자 지침은 **[Core Haptics](https://developer.apple.com/documentation/corehaptics)**를 참고하세요.

## **[Platform considerations](https://developer.apple.com/design/human-interface-guidelines/playing-haptics#Platform-considerations)**

### **[iPadOS, tvOS, visionOS](https://developer.apple.com/design/human-interface-guidelines/playing-haptics#iPadOS-tvOS-visionOS)**

Game controllers can play haptics and you can support game controller input in your apps. For developer guidance, see [Playing Haptics on Game Controllers](https://developer.apple.com/documentation/corehaptics/playing_haptics_on_game_controllers).

게임 컨트롤러는 햅틱을 재생할 수 있으며 앱에서 게임 컨트롤러 입력을 지원할 수 있습니다. 자세한 개발자 지침은 **[Playing Haptics on Game Controllers](https://developer.apple.com/documentation/corehaptics/playing_haptics_on_game_controllers)**를 참고하세요.

### **[iOS](https://developer.apple.com/design/human-interface-guidelines/playing-haptics#iOS)**

On supported iPhone models, you can add haptics to your experience in the following ways:

지원되는 iPhone 모델에서는 다음과 같은 방법으로 경험에 햅틱을 추가할 수 있습니다:

- Use standard UI components — like [toggles](https://developer.apple.com/design/human-interface-guidelines/toggles), [sliders](https://developer.apple.com/design/human-interface-guidelines/sliders), and [pickers](https://developer.apple.com/design/human-interface-guidelines/pickers) — that play Apple-designed system haptics by default.

기본적으로 Apple이 디자인한 시스템 햅틱을 재생하는 **[toggles](https://developer.apple.com/design/human-interface-guidelines/toggles)**, **[sliders](https://developer.apple.com/design/human-interface-guidelines/sliders)**, **[pickers](https://developer.apple.com/design/human-interface-guidelines/pickers)** 와 같은 표준 UI 구성 요소를 사용합니다.

- When it makes sense, use a feedback generator to play one of several predefined haptic patterns in the categories of [notification](https://developer.apple.com/design/human-interface-guidelines/playing-haptics#Notification), [impact](https://developer.apple.com/design/human-interface-guidelines/playing-haptics#Impact), and [selection](https://developer.apple.com/design/human-interface-guidelines/playing-haptics#Selection) (for developer guidance, see `[UIFeedbackGenerator](https://developer.apple.com/documentation/uikit/uifeedbackgenerator)`).

의미가 있는 경우, feedback generator를 사용하여 미리 정의된 몇 가지 햅틱 패턴 중 하나를 재생합니다. 이 패턴은 **[notification](https://developer.apple.com/design/human-interface-guidelines/playing-haptics#Notification)**, **[impact](https://developer.apple.com/design/human-interface-guidelines/playing-haptics#Impact)**, **[selection](https://developer.apple.com/design/human-interface-guidelines/playing-haptics#Selection)** 카테고리에 속합니다. (자세한 개발자 지침은 **[UIFeedbackGenerator](https://developer.apple.com/documentation/uikit/uifeedbackgenerator)**를 참고하세요.)

### **[Notification](https://developer.apple.com/design/human-interface-guidelines/playing-haptics#Notification)**

Notification haptics provide feedback about the outcome of a task or action, such as depositing a check or unlocking a vehicle.

알림 햅틱은 작업 또는 동작의 결과에 대한 피드백을 제공합니다. 예를 들어 수표를 입금하거나 차량을 잠금 해제하는 작업에 대한 피드백을 제공합니다.

[https://docs-assets.developer.apple.com/published/0897204a4f1db99e065e44dab6756699/success.mp4](https://docs-assets.developer.apple.com/published/0897204a4f1db99e065e44dab6756699/success.mp4)

**PlaySuccess.** Indicates that a task or action has completed.

**재생성공.** 작업 또는 동작이 완료되었음을 나타냅니다.

[https://docs-assets.developer.apple.com/published/2374d9cd8296f4210027c0a84ff72a33/warning.mp4](https://docs-assets.developer.apple.com/published/2374d9cd8296f4210027c0a84ff72a33/warning.mp4)

**PlayWarning.** Indicates that a task or action has produced a warning of some kind.

**재생경고.** 작업 또는 동작이 어떤 종류의 경고를 발생시켰음을 나타냅니다.

[https://docs-assets.developer.apple.com/published/2819b3e6568828343507b49151c5bbb9/error.mp4](https://docs-assets.developer.apple.com/published/2819b3e6568828343507b49151c5bbb9/error.mp4)

**PlayError.** Indicates that an error has occurred.

**재생오류.** 오류가 발생했음을 나타냅니다.

### **[Impact](https://developer.apple.com/design/human-interface-guidelines/playing-haptics#Impact)**

Impact haptics provide a physical metaphor you can use to complement a visual experience. For example, people might feel a tap when a view snaps into place or a thud when two heavy objects collide.

Impact haptics는 시각적 경험을 보완하기 위해 사용할 수 있는 물리적 은유를 제공합니다. 예를 들어, 사람들은 뷰가 정렬될 때 탭을 느낄 수 있거나 두 개의 무거운 물체가 충돌할 때 덜컹거림을 느낄 수 있습니다.

[https://docs-assets.developer.apple.com/published/207d3bd2880ad0214e9516d354087ad8/impact-light.mp4](https://docs-assets.developer.apple.com/published/207d3bd2880ad0214e9516d354087ad8/impact-light.mp4)

Play**Light.** Indicates a collision between small or lightweight UI objects.

**재생경량.** 작거나 가벼운 UI 요소 간의 충돌을 나타냅니다.

[https://docs-assets.developer.apple.com/published/f7a88b6ba1abf8536df16bf04ccf33aa/impact-medium.mp4](https://docs-assets.developer.apple.com/published/f7a88b6ba1abf8536df16bf04ccf33aa/impact-medium.mp4)

Play**Medium.** Indicates a collision between medium-sized or medium-weight UI objects.

**재생중간.** 중간 크기 또는 중간 무게의 UI 요소 간의 충돌을 나타냅니다.

[https://docs-assets.developer.apple.com/published/e10138e952d7e6924db05491d2e5e136/impact-heavy.mp4](https://docs-assets.developer.apple.com/published/e10138e952d7e6924db05491d2e5e136/impact-heavy.mp4)

Play**Heavy.** Indicates a collision between large or heavyweight UI objects.

**재생무거운.** 큰 크기 또는 무거운 UI 요소 간의 충돌을 나타냅니다.

[https://docs-assets.developer.apple.com/published/5911588179c51c4e54f540397dcd74d4/impact-rigid.mp4](https://docs-assets.developer.apple.com/published/5911588179c51c4e54f540397dcd74d4/impact-rigid.mp4)

Play**Rigid.** Indicates a collision between hard or inflexible UI objects.

**재생경직된.** 단단하거나 유연하지 않은 UI 요소 간의 충돌을 나타냅니다.

[https://docs-assets.developer.apple.com/published/19d8f88b9365b0404c252bf2197683e7/impact-soft.mp4](https://docs-assets.developer.apple.com/published/19d8f88b9365b0404c252bf2197683e7/impact-soft.mp4)

Play**Soft.** Indicates a collision between soft or flexible UI objects.

**재생부드러운.** 부드러운 또는 유연한 UI 요소 간의 충돌을 나타냅니다.

### **[Selection](https://developer.apple.com/design/human-interface-guidelines/playing-haptics#Selection)**

Selection haptics provide feedback while the values of a UI element are changing.

Selection haptics는 UI 요소의 값이 변경되는 동안 피드백을 제공합니다.

[https://docs-assets.developer.apple.com/published/5357fe51284e420e33e0adca4d8ca3a9/retarget.mp4](https://docs-assets.developer.apple.com/published/5357fe51284e420e33e0adca4d8ca3a9/retarget.mp4)

Play**Selection.** Indicates that a UI element’s values are changing.

**재생선택.** UI 요소의 값이 변경되고 있음을 나타냅니다.

### **[macOS](https://developer.apple.com/design/human-interface-guidelines/playing-haptics#macOS)**

When a Magic Trackpad is available, your app can provide one of the three following haptic patterns in response to a drag operation or force click.

Magic Trackpad가 사용 가능한 경우, 앱은 드래그 작업이나 강제 클릭에 대한 다음 세 가지 햅틱 패턴 중 하나를 제공할 수 있습니다.

| Haptic feedback pattern | Description |  |
| --- | --- | --- |
| Alignment | Indicates the alignment of a dragged item. For example, this pattern could be used in a drawing app when the people drag a shape into alignment with another shape. Other scenarios where this type of feedback could be used might include scaling an object to fit within specific dimensions, positioning an object at a preferred location, or reaching the beginning/end or minimum/maximum of something like a scrubber in a video app. | 이 패턴은 드래그된 항목의 정렬을 나타냅니다. 예를 들어, 드로잉 앱에서 사람들이 다른 모양과 정렬하기 위해 모양을 드래그 할 때 이 패턴을 사용할 수 있습니다. 이 유형의 피드백을 사용할 수 있는 다른 시나리오에는 객체를 특정 차원 내에 맞게 조절하는 경우, 객체를 선호하는 위치로 배치하는 경우, 또는 비디오 앱에서 스크러버의 시작/끝 또는 최소/최대 지점에 도달하는 경우 등이 있습니다. |
| Level change | Indicates movement between discrete levels of pressure. For example, as people press a fast-forward button on a video player, playback could increase or decrease and haptic feedback could be provided as different levels of pressure are reached. | 이 패턴은 압력의 분리된 레벨 간의 움직임을 나타냅니다. 예를 들어, 사람들이 비디오 플레이어의 빨리 감기 버튼을 누를 때, 재생 속도가 증가하거나 감소할 수 있으며, 서로 다른 압력 레벨에 도달할 때마다 다른 수준의 햅틱 피드백이 제공될 수 있습니다. |
| Generic | Intended for providing general feedback when the other patterns don’t apply. | 이 패턴은 다른 패턴이 적용되지 않을 때 일반적인 피드백을 제공하는데 사용됩니다. |

For developer guidance, see `[NSHapticFeedbackPerformer](https://developer.apple.com/documentation/appkit/nshapticfeedbackperformer)`.

### **[watchOS](https://developer.apple.com/design/human-interface-guidelines/playing-haptics#watchOS)**

Apple Watch Series 4 and later provides haptic feedback for the Digital Crown, which gives people a more tactile experience as they scroll through content. By default, the system provides linear haptic detents that people can feel as they rotate the Digital Crown. Some system controls, like table views, provide detents as new items scroll onto the screen. For developer guidance, see `[WKHapticType](https://developer.apple.com/documentation/watchkit/wkhaptictype)`.

Apple Watch Series 4 이상은 Digital Crown에 햅틱 피드백을 제공하여 사용자가 콘텐츠를 스크롤하는 동안 더욱 촉각적인 경험을 할 수 있습니다. 기본적으로 시스템은 Digital Crown을 회전시키면 사용자가 느낄 수 있는 선형적인 햅틱 디텐트를 제공합니다. 일부 시스템 컨트롤(예: 테이블 뷰)은 새로운 항목이 화면에 나타날 때 디텐트를 제공합니다. 개발자 가이드는 **[WKHapticType](https://developer.apple.com/documentation/watchkit/wkhaptictype)**를 참조하세요.

***→ Watch Series 4 이상에서의 햅틱 피드백***

watchOS defines the following set of haptics, each of which conveys a specific meaning to people.

watchOS는 다음과 같은 일련의 햅틱을 정의하며, 각각은 사용자에게 특정한 의미를 전달합니다.

• Notification

[https://docs-assets.developer.apple.com/published/d70f96ab594ddd69fed28380de40d81f/haptics-notification.mp4](https://docs-assets.developer.apple.com/published/d70f96ab594ddd69fed28380de40d81f/haptics-notification.mp4)

**Notification.** Tells the person that something significant or out of the ordinary has happened and requires their attention. The system plays this same haptic when a local or remote notification arrives.

Notification. 중요하거나 보통과 다른 사건이 발생 했음을 알리며 사용자의 주의를 요구합니다. 시스템은 로컬 또는 원격 알림이 도착할 때 이 같은 햅틱을 재생합니다.
• Up

[https://docs-assets.developer.apple.com/published/0db71b01ea6497246fa9efeb14ab09c2/haptics-levelup.mp4](https://docs-assets.developer.apple.com/published/0db71b01ea6497246fa9efeb14ab09c2/haptics-levelup.mp4)

**Up.** Tells the person that an important value increased above a significant threshold.

Up. 중요한 값이 유의한 임계값 이상으로 증가했음을 알려줍니다.
• Down

[https://docs-assets.developer.apple.com/published/388748aef65feaa7ca356a33463787c7/haptics-leveldown.mp4](https://docs-assets.developer.apple.com/published/388748aef65feaa7ca356a33463787c7/haptics-leveldown.mp4)

**Down.** Tells the person that an important value decreased below a significant threshold.

Down. 중요한 값이 유의한 임계값 아래로 감소했음을 사용자에게 알려줍니다.
• Success

[https://docs-assets.developer.apple.com/published/dd9bc1ecfdc2f5f1f9cdf66700a622f0/haptics-success.mp4](https://docs-assets.developer.apple.com/published/dd9bc1ecfdc2f5f1f9cdf66700a622f0/haptics-success.mp4)

**Success.** Tells the person that an action completed successfully.

Success. 작업이 성공적으로 완료되었음을 사용자에게 알립니다.
• Failure

[https://docs-assets.developer.apple.com/published/1a90eb65d27672351d5e11585300cfc2/haptics-failure.mp4](https://docs-assets.developer.apple.com/published/1a90eb65d27672351d5e11585300cfc2/haptics-failure.mp4)

**Failure.** Tells the person that an action failed.

Failure. 작업이 실패했음을 사용자에게 알립니다.
• Retry

[https://docs-assets.developer.apple.com/published/1b648d1c5f970a2dc4d4029abcf7d2da/haptics-retry.mp4](https://docs-assets.developer.apple.com/published/1b648d1c5f970a2dc4d4029abcf7d2da/haptics-retry.mp4)

**Retry.** Tells the person that an action failed but they can retry it.

Retry. 작업이 실패했지만 다시 시도할 수 있음을 사용자에게 알립니다.
• Start

[https://docs-assets.developer.apple.com/published/2880c14c5074cc64fb2102d0f97f6d04/haptics-start.mp4](https://docs-assets.developer.apple.com/published/2880c14c5074cc64fb2102d0f97f6d04/haptics-start.mp4)

**Start.** Tells the person that an activity started. Use this haptic when starting a timer or any other activity that a person can explicitly start and stop. The stop haptic usually follows this haptic.
Start. 활동이 시작되었음을 사람에게 알려줍니다. 타이머 또는 사람이 명시적으로 시작하고 중지할 수 있는 다른 활동을 시작할 때 이 햅틱을 사용합니다. 중지 햅틱은 일반적으로 이 햅틱을 따릅니다.

• Stop

[https://docs-assets.developer.apple.com/published/d24f9674a900dd03b6e80f9094e50c4a/haptics-stop.mp4](https://docs-assets.developer.apple.com/published/d24f9674a900dd03b6e80f9094e50c4a/haptics-stop.mp4)

**Stop.** Tells the person that an activity stopped. Use this haptic when stopping a timer or other activity that the person previously started.
Stop. 활동이 중지되었음을 사용자에게 알립니다. 사용자가 이전에 시작한 타이머 또는 기타 활동을 중지할 때 이 햅틱을 사용합니다.

• Click

[https://docs-assets.developer.apple.com/published/f99686f74855b7ec9bd1b1212fd313a1/haptics-click.mp4](https://docs-assets.developer.apple.com/published/f99686f74855b7ec9bd1b1212fd313a1/haptics-click.mp4)

**Click.** Provides the sensation of a dial clicking, helping you communicate progress at predefined increments or intervals. Overusing the click haptic tends to diminish its utility and can even be confusing when clicks overlap each other.

Click. 다이얼 클릭의 감각을 제공하여 미리 정의된 증분 또는 간격으로 진행 상황을 전달하는 데 도움이 됩니다. 클릭 햅틱을 과도하게 사용하면 유용성이 감소하고 클릭이 서로 겹칠 때 혼란스러울 수도 있습니다.