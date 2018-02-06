---
UID: NF:winddiui.DrvSplStartDoc
title: DrvSplStartDoc function
author: windows-driver-content
description: "."
old-location: print\drvsplstartdoc.htm
old-project: print
ms.assetid: 3bd25a77-bce6-4cd3-808c-6df3b3033dd2
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: DrvSplStartDoc, winddiui/DrvSplStartDoc, print_interface-graphics_c37a0824-d460-4d62-b029-55ec4bc842d2.xml, DrvSplStartDoc function [Print Devices], print.drvsplstartdoc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winddiui.h
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
-	winddiui.h
apiname:
-	DrvSplStartDoc
product: Windows
targetos: Windows
req.typenames: "*PWINBIO_VERSION, WINBIO_VERSION"
req.product: Windows 10 or later.
---

# DrvSplStartDoc function


## -description





## -syntax


````
HANDLE WINAPI DrvSplStartDoc(
   HANDLE hPrinter,
   DWORD  JobId
);
````


## -parameters




### -param hPrinter



### -param JobId


