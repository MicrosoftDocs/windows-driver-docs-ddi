---
UID: NF:winsplp.SplDeleteSpoolerPortStart
title: SplDeleteSpoolerPortStart function
author: windows-driver-content
description: "."
old-location: print\spldeletespoolerportstart.htm
old-project: print
ms.assetid: E66C34E2-2540-4BBC-82E4-6B5267D0EA7F
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: SplDeleteSpoolerPortStart function [Print Devices], winsplp/SplDeleteSpoolerPortStart, print.spldeletespoolerportstart, SplDeleteSpoolerPortStart
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winsplp.h
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
-	Winsplp.h
apiname:
-	SplDeleteSpoolerPortStart
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# SplDeleteSpoolerPortStart function


## -description





## -syntax


````
BOOL WINAPI SplDeleteSpoolerPortStart(
  _In_ PCWSTR  pPortName
);
````


## -parameters




### -param pPortName [in]


