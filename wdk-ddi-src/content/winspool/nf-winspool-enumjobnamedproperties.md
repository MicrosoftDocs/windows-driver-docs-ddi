---
UID: NF:winspool.EnumJobNamedProperties
title: EnumJobNamedProperties function
author: windows-driver-content
description: "."
old-location: print\enumjobnamedproperties.htm
old-project: print
ms.assetid: 0C5E2279-79D0-40A2-BA5B-66994A22E963
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: EnumJobNamedProperties function [Print Devices], winspool/EnumJobNamedProperties, print.enumjobnamedproperties, EnumJobNamedProperties
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
-	EnumJobNamedProperties
product: Windows
targetos: Windows
req.typenames: BIDI_TYPE
req.product: Windows 10 or later.
---

# EnumJobNamedProperties function


## -description





## -syntax


````
DWORD WINAPI EnumJobNamedProperties(
  _In_  HANDLE              hPrinter,
  _In_  DWORD               JobId,
  _Out_ DWORD               *pcProperties,
  _Out_ PrintNamedProperty  **ppProperties
);
````


## -parameters




### -param hPrinter [in]



### -param JobId [in]



### -param pcProperties [out]



### -param ppProperties [out]


