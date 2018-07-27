---
UID: NF:lowio.RxLowIoGetBufferAddress
title: RxLowIoGetBufferAddress function
author: windows-driver-content
description: RxLowIoGetBufferAddress returns the buffer corresponding to the MDL from LowIoContext structure of an RX_CONTEXT structure.
old-location: ifsk\rxlowiogetbufferaddress.htm
tech.root: ifsk
ms.assetid: a4d78135-38bc-4a34-98ce-d2712829124a
ms.author: windowsdriverdev
ms.date: 4/16/2018
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
req.lib: 
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	lowio.h
api_name:
-	RxLowIoGetBufferAddress
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxLowIoGetBufferAddress function


## -description


<b>RxLowIoGetBufferAddress</b> returns the buffer corresponding to the MDL from LowIoContext structure of an RX_CONTEXT structure.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554751">RX_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554525">RxLowIoCompletion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554549">RxMapSystemBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554591">RxNewMapUserBuffer</a>
 

 

