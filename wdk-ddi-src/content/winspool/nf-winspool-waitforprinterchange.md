---
UID: NF:winspool.WaitForPrinterChange
title: WaitForPrinterChange function
author: windows-driver-content
description: "."
old-location: print\waitforprinterchange.htm
old-project: print
ms.assetid: BD9DD9C4-D736-42DC-A55F-7F299351FA65
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WaitForPrinterChange, winspool/WaitForPrinterChange, print.waitforprinterchange, WaitForPrinterChange function [Print Devices]
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
-	WaitForPrinterChange
product: Windows
targetos: Windows
req.typenames: BIDI_TYPE
req.product: Windows 10 or later.
---

# WaitForPrinterChange function


## -description





## -syntax


````
DWORD WINAPI WaitForPrinterChange(
   HANDLE hPrinter,
   DWORD  Flags
);
````


## -parameters




### -param hPrinter



### -param Flags


