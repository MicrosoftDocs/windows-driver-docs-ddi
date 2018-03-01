---
UID: NF:rxprocs.RxMapSystemBuffer
title: RxMapSystemBuffer function
author: windows-driver-content
description: RxMapSystemBuffer returns the system buffer address from the IRP.
old-location: ifsk\rxmapsystembuffer.htm
old-project: ifsk
ms.assetid: dc549e51-2f25-45b5-925f-3481294e0b35
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxMapSystemBuffer, RxMapSystemBuffer function [Installable File System Drivers], ifsk.rxmapsystembuffer, rxprocs/RxMapSystemBuffer, rxref_b9222b0a-25ca-4ad4-95b9-b9651c625a39.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxprocs.h
req.include-header: Rxcontx.h, Rxprocs.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rxprocs.h
api_name:
-	RxMapSystemBuffer
product: Windows
targetos: Windows
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---

# RxMapSystemBuffer function


## -description


<b>RxMapSystemBuffer</b> returns the system buffer address from the IRP. 


## -syntax


````
PVOID RxMapSystemBuffer(
  _In_ PRX_CONTEXT RxContext,
  _In_ PIRP        Irp
);
````


## -parameters




### -param RxContext [in]

A pointer to the RX_CONTEXT structure for this request.


### -param Irp [in]

A pointer to the IRP for this request.


## -returns



<b>RxMapSystemBuffer </b>returns a mapped address pointer. 




## -remarks



The <b>RxMapSystemBuffer</b> routine checks that <b>Irp-&gt;MdlAddress</b> is not <b>NULL</b> and returns the <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> when this is the case. 

On retail builds, <b>RxMapSystemBuffer</b> will call <b>MmGetSystemAddressForMdlSafe</b> to return the MDL from the IRP if <b>Irp-&gt;MdlAddress</b> is <b>NULL</b>. On checked builds, <b>RxMapSystemBuffer</b> causes the system to ASSERT if <b>Irp-&gt;MdlAddress</b> is <b>NULL</b>. 




## -see-also

<a href="..\lowio\nf-lowio-rxlowiocompletion.md">RxLowIoCompletion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554591">RxNewMapUserBuffer</a>



<a href="..\lowio\nf-lowio-rxlowiogetbufferaddress.md">RxLowIoGetBufferAddress</a>



<a href="..\rxcontx\ns-rxcontx-_rx_context.md">RX_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxMapSystemBuffer function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

