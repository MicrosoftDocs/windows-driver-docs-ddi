---
UID: NF:wpprecorder.imp_WppRecorderGetCounterHandle
title: imp_WppRecorderGetCounterHandle function
author: windows-driver-content
description: The WppRecorderGetCounterHandle method.
old-location: devtest\wpprecordergetcounterhandle.htm
old-project: devtest
ms.assetid: 389A4F90-9C81-4C03-A2F9-ACF0E597018C
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , C, G, H, R, W, WppRecorderGetCounterHandle, _, a, c, d, devtest.wpprecordergetcounterhandle, e, i, imp_WppRecorderGetCounterHandle, imp_WppRecorderGetCounterHandle function [Driver Development Tools], l, m, n, o, p, r, t, u, wpprecorder/imp_WppRecorderGetCounterHandle"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wpprecorder.h
apiname:
-	imp_WppRecorderGetCounterHandle
product: Windows
targetos: Windows
req.typenames: WNODE_HEADER, *PWNODE_HEADER
req.product: Windows 10 or later.
---

# imp_WppRecorderGetCounterHandle function


## -description


The <b>WppRecorderGetCounterHandle</b> method gets the ID of the counter whose current value is to be read.


## -syntax


````
WPP_RECORDER_COUNTER imp_WppRecorderGetCounterHandle(void);
````


## -parameters




### -param WppCb

TBD




## -returns



ID of the counter whose current value is to be read.



