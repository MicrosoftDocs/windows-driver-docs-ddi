---
UID: NF:winddiui.DrvSplClose
title: DrvSplClose function
author: windows-driver-content
description: "."
old-location: print\drvsplclose.htm
old-project: print
ms.assetid: bd5f0bf2-ccb8-446c-b1e5-2e32538ebfbd
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: DrvSplClose function [Print Devices], print.drvsplclose, print_interface-graphics_e43f66ed-0e5e-4a27-ad52-0faebe549ac5.xml, winddiui/DrvSplClose, DrvSplClose
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
-	DrvSplClose
product: Windows
targetos: Windows
req.typenames: "*PWINBIO_VERSION, WINBIO_VERSION"
req.product: Windows 10 or later.
---

# DrvSplClose function


## -description





## -syntax


````
VOID WINAPI DrvSplClose(
   HANDLE hDriver
);
````


## -parameters




### -param hDriver



## -returns


This function does not return a value.
<h2><a id="ddk_drvsplclose_gg"></a><a id="DDK_DRVSPLCLOSE_GG"></a></h2>The <b>DrvSplClose</b> function is obsolete, and is supported only so that user-mode rendering DLLs, optionally supplied with Windows NT 4.0 drivers, will execute under Windows 2000 and later. Use <a href="..\winddiui\nf-winddiui-drvdocumentevent.md">DrvDocumentEvent</a> instead of this function.

The <b>DrvSplClose</b> function enables a user-mode rendering DLL to deallocate resources.
<h3><a id="comments"></a><a id="COMMENTS"></a>Comments</h3>To supply user-mode image-rendering code for printers, see <a href="https://msdn.microsoft.com/1e63d01e-8cf2-488a-89e8-d4a3ff5cfe19">Choosing User Mode or Kernel Mode</a>.


