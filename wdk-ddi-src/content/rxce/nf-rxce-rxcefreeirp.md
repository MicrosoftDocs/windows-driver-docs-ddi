---
UID: NF:rxce.RxCeFreeIrp
title: RxCeFreeIrp function
author: windows-driver-content
description: RxCeFreeIrp frees an IRP.
old-location: ifsk\rxcefreeirp.htm
old-project: ifsk
ms.assetid: 71e3283c-2dbc-4579-a374-e51e123b852f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxCeFreeIrp, RxCeFreeIrp function [Installable File System Drivers], ifsk.rxcefreeirp, rxce/RxCeFreeIrp, rxref_93b8da8d-d9fe-41e3-8423-5b3d8102f7a7.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxce.h
req.include-header: Rxce.h
req.target-type: Desktop
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rxce.h
apiname:
-	RxCeFreeIrp
product: Windows
targetos: Windows
req.typenames: RILWRITEPHONEBOOKENTRYPARAMS, *LPRILWRITEPHONEBOOKENTRYPARAMS
req.product: Windows 10 or later.
---

# RxCeFreeIrp function


## -description


<b>RxCeFreeIrp</b> frees an IRP.


## -syntax


````
VOID RxCeFreeIrp(
   PIRP pIrp
);
````


## -parameters




### -param pIrp

A pointer to the IRP to be freed.


## -returns



None 




## -remarks



An IRP allocated with an associated memory descriptor list allocated with <b>RxCeAllocateIrpWithMDL</b> should be freed when the IRP is completed using <b>RxCeFreeIrp</b>.




## -see-also

<a href="..\wdm\ns-wdm-_mdl.md">MDL</a>



<a href="..\rxce\nf-rxce-rxceallocateirpwithmdl.md">RxCeAllocateIrpWithMDL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCeFreeIrp function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

