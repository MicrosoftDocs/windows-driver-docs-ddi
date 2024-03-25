---
UID: NF:wpprecorder.WppRecorderGetTriageInfo
title: WppRecorderGetTriageInfo macro (wpprecorder.h)
description: Learn about the WppRecorderGetTriageInfo method.
old-location: devtest\wpprecordergettriageinfo.htm
tech.root: devtest
ms.date: 04/19/2022
keywords: ["WppRecorderGetTriageInfo macro"]
ms.keywords: WppRecorderGetTriageInfo
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
targetos: Windows
f1_keywords:
 - WppRecorderGetTriageInfo
 - wpprecorder/WppRecorderGetTriageInfo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Wpprecorder.h
api_name:
 - WppRecorderGetTriageInfo
---

# WppRecorderGetTriageInfo macro


## -description

The <b>WppRecorderGetTriageInfo</b> method returns the WPP log for WER reporting.

## -syntax

```cpp
__drv_maxIRQL(DISPATCH_LEVEL)
NTSTATUS WppRecorderGetTriageInfo(
  _Out_ PWPP_TRIAGE_INFO WppTriageInfo
);
```

## -parameters

### -param WppTriageInfo [out]


Pointer to a <a href="..\wpprecorder\ns-wpprecorder-_wpp_triage_info.md">WPP_TRIAGE_INFO</a> structure.

## -remarks

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, one of appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> values
