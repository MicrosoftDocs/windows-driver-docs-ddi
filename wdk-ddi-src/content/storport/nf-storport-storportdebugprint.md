---
UID: NF:storport.StorPortDebugPrint
title: StorPortDebugPrint function
author: windows-driver-content
description: The StorPortDebugPrint routine prints a debug string to the kernel debugger, if the debugger is attached.
old-location: storage\storportdebugprint.htm
old-project: storage
ms.assetid: 46845a10-c44b-4d11-b82e-986bfc066b97
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortDebugPrint
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortDebugPrint
req.alt-loc: Storport.lib,Storport.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: 
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortDebugPrint function



## -description
The <b>StorPortDebugPrint</b> routine prints a debug string to the kernel debugger, if the debugger is attached.



## -syntax

````
VOID StorPortDebugPrint(
   IN ULONG  DebugPrintLevel,
   IN PCCHAR DebugMessage
);
````


## -parameters

### -param DebugPrintLevel 

Indicates the amount of debug information that will be displayed. 


### -param DebugMessage 

Pointer to the debug message to be printed. 


## -returns
None 


## -remarks
To see these debug strings, the driver writer must set nt!Kd_STORMINIPORT_Mask. This follows the new system-wide debug print mechanism.</p>