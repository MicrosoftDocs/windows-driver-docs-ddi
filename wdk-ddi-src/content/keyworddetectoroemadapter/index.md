---
UID: NA:keyworddetectoroemadapter
ms.assetid: bf22e8cc-5ff8-3f48-8afe-2cba51a6d8a9
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Keyworddetectoroemadapter.h header



This header is used by Audio. For more information, see
- [Audio](../_audio/index.md)

Keyworddetectoroemadapter.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [__MIDL_IKeywordDetectorOemAdapter_0003 structure](ns-keyworddetectoroemadapter-__midl_ikeyworddetectoroemadapter_0003.md) | The KEYWORDSELECTOR struct is a triplet of IDs that uniquely select a particular keyword, language, and user combination. |
| [__MIDL___MIDL_itf_keyworddetectoroemadapter_0000_0000_0001 structure](ns-keyworddetectoroemadapter-__midl___midl_itf_keyworddetectoroemadapter_0000_0000_0001.md) | The SOUNDDETECTOR_PATTERNHEADER structure specifies the pattern header for the sound detector in the KSPROPERTY_SOUNDDETECTOR_PATTERNS property. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [__MIDL_IKeywordDetectorOemAdapter_0002 enumeration](ne-keyworddetectoroemadapter-__midl_ikeyworddetectoroemadapter_0002.md) | The KEYWORDID enumeration identifies the phrase text/function of a keyword. The value is also be used in the Windows Biometric Service adapters. |

## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IKeywordDetectorOemAdapter interface](nn-keyworddetectoroemadapter-ikeyworddetectoroemadapter.md) | IKeywordDetectorOemAdapter is a Component Object Model (COM) interface for interacting with the Voice Activation Driver Interface. The IKeywordDetectorOemAdapter interface is supported in Windows 10 and later versions of Windows. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [IKeywordDetectorOemAdapter::BuildArmingPatternData method](nf-keyworddetectoroemadapter-ikeyworddetectoroemadapter-buildarmingpatterndata.md) | The BuildArmingPatternData method is called by the operating system to build OEM-specific pattern data that includes any keyword and user-specific model data for detection. |
| [IKeywordDetectorOemAdapter::ComputeAndAddUserModelData method](nf-keyworddetectoroemadapter-ikeyworddetectoroemadapter-computeandaddusermodeldata.md) | The ComputeAndAddUserModelData method is used by the training user experience to compute the user-specific information relative to the user-independent keyword. |
| [IKeywordDetectorOemAdapter::GetCapabilities method](nf-keyworddetectoroemadapter-ikeyworddetectoroemadapter-getcapabilities.md) | The GetCapabilities method returns the keywords and languages supported by the object. |
| [IKeywordDetectorOemAdapter::ParseDetectionResultData method](nf-keyworddetectoroemadapter-ikeyworddetectoroemadapter-parsedetectionresultdata.md) | The ParseDetectionResultData method is called by the operating system after handling a keyword detection event and after retrieving the result data from KSPROPERTY_SOUNDDETECTOR_MATCHRESULT. |
| [IKeywordDetectorOemAdapter::VerifyUserKeyword method](nf-keyworddetectoroemadapter-ikeyworddetectoroemadapter-verifyuserkeyword.md) | The VerifyUserKeyword method is used by the training user experience to verify that one instance of a spoken utterance, captured during training, matches a predefined keyword within some tolerance. |
