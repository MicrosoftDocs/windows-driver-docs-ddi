---
UID: NF:rxce.RxCeAllocateIrpWithMDL
title: RxCeAllocateIrpWithMDL function
author: windows-driver-content
description: RxCeAllocateIrpWithMDL allocates an IRP and associates it with an existing memory descriptor list.
old-location: ifsk\rxceallocateirpwithmdl.htm
old-project: ifsk
ms.assetid: ffc6332b-7daa-4b23-8cf4-6077f7d1d40a
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RxCeAllocateIrpWithMDL function [Installable File System Drivers], ifsk.rxceallocateirpwithmdl, rxref_8cb4dfd0-5789-4359-ad9f-bd1a9d460eb3.xml, rxce/RxCeAllocateIrpWithMDL, RxCeAllocateIrpWithMDL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxce.h
req.include-header: Rxce.h
req.target-type: Desktop
req.target-min-winverclnt: The RxCeAllocateIrpWithMDL routine is only available on Windows XP.
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
req.irql: <= APC_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	rxce.h
apiname: 
-	RxCeAllocateIrpWithMDL
product: Windows
targetos: Windows
req.typenames: *LPRILWRITEPHONEBOOKENTRYPARAMS, RILWRITEPHONEBOOKENTRYPARAMS
req.product: Windows 10 or later.
---

# RxCeAllocateIrpWithMDL function


## -description


<b>RxCeAllocateIrpWithMDL</b> allocates an IRP and associates it with an existing memory descriptor list. 


## -syntax


````
PIRP RxCeAllocateIrpWithMDL(
  _In_ CCHAR   StackSize,
  _In_ BOOLEAN ChargeQuota,
  _In_ PMDL    Buffer
);
````


## -parameters




### -param StackSize [in]

The stack size to allocate for the IRP. 


### -param ChargeQuota [in]

This parameter should be set to <b>FALSE</b> by intermediate drivers. This can be set to <b>TRUE</b> only by highest-level drivers that are called in the context of the thread that originates the I/O request for which the driver is allocating another IRP. 


### -param Buffer [in]

A pointer to the buffer that contains the memory descriptor list to be associated with this IRP.


## -returns


<b>RxCeAllocateIrpWithMDL</b> returns a pointer to the IRP on success or a <b>NULL</b> pointer on error.



## -remarks


The goal of <b>RxCeAllocateIrpWithMDL</b> is to allow easier debugging of IRPs that are issued to other components and then stall. IRPs issued using <b>RxCeAllocateIrpWithMDL</b> are queued to a global list of IRPs maintained by RDBSS. Thus, when an RX_CONTEXT is waiting for a send completion, it is possible to walk the global list to find the IRP that is waiting in the transport.

An IRP allocated with an associated memory descriptor list allocated with <b>RxCeAllocateIrpWithMDL</b> should be freed when the IRP is completed using <b>RxCeFreeIrp</b>.

<b>IoAllocateIrp</b> automatically initializes the IRP's members and inserts the IRP into a global list of IRPs maintained by RDBSS. If memory for the MDL to be associated with the IRP cannot be allocated, then the IRP that was created is freed and <b>RxCeAllocateIrpWithMDL</b> returns a <b>NULL</b> pointer indicating failure. 



## -see-also

<a href="..\wdm\ns-wdm-_mdl.md">MDL</a>

<a href="..\rxce\nf-rxce-rxcefreeirp.md">RxCeFreeIrp</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCeAllocateIrpWithMDL function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

