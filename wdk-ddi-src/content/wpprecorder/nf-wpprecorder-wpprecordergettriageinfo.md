---
UID: NF:wpprecorder.WppRecorderGetTriageInfo
title: WppRecorderGetTriageInfo macro (wpprecorder.h)
description: The WppRecorderGetTriageInfo.
old-location: devtest\wpprecordergettriageinfo.htm
tech.root: devtest
ms.assetid: D2790496-1F86-4EF0-8AFE-77AC0C89EE05
ms.date: 01/10/2018
keywords: ["WppRecorderGetTriageInfo macro"]
ms.keywords: WppRecorderGetTriageInfo
f1_keywords:
 - "wpprecorder/imp_WppRecorderGetTriageInfo"
 - "imp_WppRecorderGetTriageInfo"
req.header: wpprecorder.h
req.include-header:
req.target-type: Desktop
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.alt-api: WppRecorderGetTriageInfo
req.alt-loc: wpprecorder.h
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library:
req.lib:
req.dll:
req.irql:
req.typenames: WNODE_HEADER, *PWNODE_HEADER
req.product: Windows 10 or later.
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Wpprecorder.h
api_name:
- imp_WppRecorderGetTriageInfo
product:
- Windows
targetos: Windows

---

# WppRecorderGetTriageInfo macro



## -description
The <b>WppRecorderGetTriageInfo</b> method



## -syntax

```cpp
NTSTATUS WppRecorderGetTriageInfo(
  _Out_ PWPP_TRIAGE_INFO WppTriageInfo
);
```


## -parameters

### -param WppTriageInfo [out]

Pointer to a <a href="..\wpprecorder\ns-wpprecorder-_wpp_triage_info.md">WPP_TRIAGE_INFO</a> structure.


## -remarks
