---
UID: NF:wpprecorder.imp_WppRecorderLogGetDefault
title: imp_WppRecorderLogGetDefault function (wpprecorder.h)
description: The WppRecorderLogGetDefault method gets a handle to the default recorder log.
old-location: devtest\wpprecorderloggetdefault.htm
tech.root: devtest
ms.date: 04/19/2022
keywords: ["imp_WppRecorderLogGetDefault function"]
ms.keywords: WppRecorderLogGetDefault, devtest.wpprecorderloggetdefault, imp_WppRecorderLogGetDefault, imp_WppRecorderLogGetDefault function [Driver Development Tools], wpprecorder/imp_WppRecorderLogGetDefault
req.header: wpprecorder.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
targetos: Windows
req.typenames: 
f1_keywords:
 - imp_WppRecorderLogGetDefault
 - wpprecorder/imp_WppRecorderLogGetDefault
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wpprecorder.h
api_name:
 - imp_WppRecorderLogGetDefault
---

# WppRecorderLogGetDefault function


## -description

The <b>WppRecorderLogGetDefault</b> method gets a handle to the default recorder log.

## -syntax

```cpp
__drv_maxIRQL(DISPATCH_LEVEL)
RECORDER_LOG
WppRecorderLogGetDefault(
    );
```

## -parameters


## -returns

An opaque handle to the default log.

## -see-also

<a href="/previous-versions/windows/hardware/previsioning-framework/dn914614(v=vs.85)">WppRecorderIsDefaultLogAvailable</a>
