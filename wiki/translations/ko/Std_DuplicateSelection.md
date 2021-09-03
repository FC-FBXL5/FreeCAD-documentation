---
- GuiCommand:/ko
   Name:Std DuplicateSelection
   Name/ko:표준 개체 복제
   MenuLocation:편집 → 개체 복제
   Workbenches:모두
   SeeAlso:[표준 잘라내기](Std_Cut/ko.md), [표준 복사](Std_Copy/ko.md), [표준 붙여넣기](Std_Paste/ko.md)
---


</div>

## 설명

**표준 개체 복제(Std DuplicateSelection)** 명령은 활성 문서의 개체를 복제합니다.

## 용법


<div class="mw-translate-fuzzy">

1.  하나 이상의 개체를 선택합니다..
2.  메뉴에서 {{MenuCommand|편집 → 개체 복제}} 옵션을 선택합니다.
3.  개체에 선택하지 않은 의존성이 있는 경우 포함 할 항목을 지정하라는 대화 상자가 나타납니다.


</div>

## 비고

-   FreeCAD는 이름 충돌을 피하기 위해 환경 설정 값에 따라 개체의 내부 이름과 레이블을 자동으로 변경합니다.

## 환경 설정 {#환경_설정}

-    {{MenuCommand|도구 → 파라미터 편집... → BaseApp → Preferences → Document → DuplicateLabels}}값이 `True`면 중복 레이블이 허용됩니다. 이 설정은 [환경 설정 편집기에서도](Preferences_Editor/ko#문서.md) 변경할 수 있습니다.

## Scripting

The **Std DuplicateSelection** command can be applied after selecting one or more objects in the [Tree view](Tree_view.md):


```python
FreeCADGui.runCommand('Std_DuplicateSelection')
```

The selection can be manual (by using the mouse), or via the [Python console](Python_console.md).
To know more about selecting objects programmatically, refer to [Selection methods](Selection_methods.md).





{{Std Base navi

}}  