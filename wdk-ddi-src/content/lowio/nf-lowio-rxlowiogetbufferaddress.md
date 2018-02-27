---
UID: NF:lowio.RxLowIoGetBufferAddress
title: RxLowIoGetBufferAddress function
author: windows-driver-content
description: RxLowIoGetBufferAddress returns the buffer corresponding to the MDL from LowIoContext structure of an RX_CONTEXT structure.
old-location: ifsk\rxlowiogetbufferaddress.htm
old-project: ifsk
ms.assetid: a4d78135-38bc-4a34-98ce-d2712829124a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxLowIoGetBufferAddress, RxLowIoGetBufferAddress function [Installable File System Drivers], ifsk.rxlowiogetbufferaddress, lowio/RxLowIoGetBufferAddress, rxref_b45afb50-cf03-4450-9e96-3d8f08392eb6.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: lowio.h
req.include-header: Rxcontx.h, Lowio.h
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
-	lowio.h
apiname:
-	RxLowIoGetBufferAddress
product: Windows
targetos: Windows
req.typenames: LAMP_INTENSITY_WHITE
---

# RxLowIoGetBufferAddress function


## -description


<b>RxLowIoGetBufferAddress</b> returns the buffer corresponding to the MDL from LowIoContext structure of an RX_CONTEXT structure.


## -syntax


````
PVOID RxLowIoGetBufferAddress(
  _In_ PRX_CONTEXT RxContext
);
````


## -parameters




### -param RxContext [in]

A pointer to the RX_CONTEXT structure for this request.


## -returns



<b>RxLowIoGetBufferAddress </b>returns a mapped address pointer on success or a <b>NULL</b> on failure. 




## -remarks



<b>RxLowIoGetBufferAddress</b> checks that the <b>ParamsFor.ReadWrite.ByteCount</b> member of the <b>LowIoContext</b> member of the <i>RxContext</i> variable is greater than zero and returns a <b>NULL</b> pointer if this is not the case. 

<b>RxLowIoGetBufferAddress</b> causes the system to ASSERT on checked builds if the <b>ParamsFor.ReadWrite.Buffer</b> member of the LowIoContext is <b>NULL</b>. 

<b>RxLowIoGetBufferAddress</b> calls <b>MmGetSystemAddressForMdlSafe</b> to retrieve the mapped address.




## -see-also

<a href="..\lowio\nf-lowio-rxlowiocompletion.md">RxLowIoCompletion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>



<a href="..\rxprocs\nf-rxprocs-rxmapsystembuffer.md">RxMapSystemBuffer</a>



<a href="..\rxcontx\ns-rxcontx-_rx_context.md">RX_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554591">RxNewMapUserBuffer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxLowIoGetBufferAddress function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

