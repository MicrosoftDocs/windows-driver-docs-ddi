---
UID: NF:winsplp.SplDeleteSpoolerPortEnd
title: SplDeleteSpoolerPortEnd function
author: windows-driver-content
description: "."
old-location: print\spldeletespoolerportend.htm
old-project: print
ms.assetid: 947391B5-5355-4ADB-B26E-A51FE0B0B85F
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , D, E, P, S, SplDeleteSpoolerPortEnd, SplDeleteSpoolerPortEnd function [Print Devices], d, e, l, n, o, p, print.spldeletespoolerportend, r, t, winsplp/SplDeleteSpoolerPortEnd"
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
-	SplDeleteSpoolerPortEnd
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# SplDeleteSpoolerPortEnd function


## -description





## -syntax


````
BOOL WINAPI SplDeleteSpoolerPortEnd(
  _In_ PCWSTR  pName,
  _In_ BOOL    bDeletePort
);
````


## -parameters




### -param pName [in]


### -param bDeletePort [in]

