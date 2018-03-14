---
UID: NC:wdm.KSTART_ROUTINE
title: KSTART_ROUTINE
author: windows-driver-content
description: The ThreadStart routine provides an entry point for a driver-created system thread.
old-location: kernel\threadstart.htm
old-project: kernel
ms.assetid: 4a4e4e0f-fadf-4f4c-9759-6d52ef9f663d
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: DrvrRtns_913b72f4-9f6b-4967-879d-c4e565d219dd.xml, KSTART_ROUTINE, ThreadStart, ThreadStart routine [Kernel-Mode Driver Architecture], kernel.threadstart, wdm/ThreadStart
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows 2000.
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
req.irql: Called at PASSIVE_LEVEL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdm.h
api_name:
-	ThreadStart
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# KSTART_ROUTINE callback


## -description


The <i>ThreadStart</i> routine provides an entry point for a driver-created system thread.


## -prototype


````
KSTART_ROUTINE ThreadStart;

VOID ThreadStart(
  _In_ PVOID StartContext
)
{ ... }
````


## -parameters




### -param StartContext [in]

A caller-supplied pointer to driver-defined context information that is specified in the <i>StartContext</i> parameter a previous call to <a href="..\wdm\nf-wdm-pscreatesystemthread.md">PsCreateSystemThread</a>.


## -returns



None




## -see-also

<a href="..\wdm\nf-wdm-pscreatesystemthread.md">PsCreateSystemThread</a>



 

 


