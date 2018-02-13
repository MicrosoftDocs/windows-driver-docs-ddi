---
UID: NF:winspool.SetJobNamedProperty
title: SetJobNamedProperty function
author: windows-driver-content
description: "."
old-location: print\setjobnamedproperty.htm
old-project: print
ms.assetid: 6A03B009-21D4-4CD2-9BB5-36F402118270
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: SetJobNamedProperty, SetJobNamedProperty function [Print Devices], winspool/SetJobNamedProperty, print.setjobnamedproperty
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winspool.h
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
-	Winspool.h
apiname:
-	SetJobNamedProperty
product: Windows
targetos: Windows
req.typenames: BIDI_TYPE
req.product: Windows 10 or later.
---

# SetJobNamedProperty function


## -description





## -syntax


````
DWORD WINAPI SetJobNamedProperty(
  _In_       HANDLE                    hPrinter,
  _In_       DWORD                     JobId,
  _In_ const PrintNamedProperty        *pProperty
);
````


## -parameters




### -param hPrinter [in]


### -param JobId [in]

TD


### -param pProperty [in]

