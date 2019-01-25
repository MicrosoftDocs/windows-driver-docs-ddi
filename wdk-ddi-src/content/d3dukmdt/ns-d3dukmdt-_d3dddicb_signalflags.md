---
UID: NS:d3dukmdt._D3DDDICB_SIGNALFLAGS
title: "_D3DDDICB_SIGNALFLAGS" (d3dukmdt.h)
description: The D3DDDICB_SIGNALFLAGS structure describes signaling behavior in a call to the pfnSignalSynchronizationObjectCb or pfnSignalSynchronizationObject2Cb functions.
old-location: display\d3dddicb_signalflags.htm
tech.root: display
ms.assetid: 1efe98c4-021b-4312-bbcc-52267e528b5f
ms.date: 05/10/2018
ms.keywords: D3DDDICB_SIGNALFLAGS, D3DDDICB_SIGNALFLAGS structure [Display Devices], D3D_other_Structs_3165168a-bcae-409c-8ca2-741675016ba8.xml, _D3DDDICB_SIGNALFLAGS, d3dukmdt/D3DDDICB_SIGNALFLAGS, display.d3dddicb_signalflags
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dukmdt.h
api_name:
-	D3DDDICB_SIGNALFLAGS
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_SIGNALFLAGS
---

# _D3DDDICB_SIGNALFLAGS structure


## -description


The D3DDDICB_SIGNALFLAGS structure describes signaling behavior in a call to the <a href="https://msdn.microsoft.com/12ffa230-2c26-4cd3-ae83-f753a0b6ba38">pfnSignalSynchronizationObjectCb</a> or <a href="https://msdn.microsoft.com/01B5E793-D075-42B5-9ADF-D033249AEE9F">pfnSignalSynchronizationObject2Cb</a> functions.


## -struct-fields




### -field SignalAtSubmission

A UINT value that specifies whether a context should signal synchronization objects when the previously queued packet is submitted rather than completed (which is the default behavior).

Setting this member is equivalent to setting the first bit of the 32-bit  <b>Value</b> member (0x00000001).


### -field EnqueueCpuEvent

A UINT value that modifies the behavior of the <a href="https://msdn.microsoft.com/01B5E793-D075-42B5-9ADF-D033249AEE9F">pfnSignalSynchronizationObject2Cb</a> function. When this member is set,  the event specified by the <b>CpuEventHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451164">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2</a> structure is signaled when all contexts specified in  <b>D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2</b>  process the signal command.

If this member is set,  members of  the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451164">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2</a>  structure that the <a href="https://msdn.microsoft.com/01B5E793-D075-42B5-9ADF-D033249AEE9F">pfnSignalSynchronizationObject2Cb</a> function's <i>pData</i> parameter points to are restricted as follows:

<ul>
<li><b>ObjectCount</b> must be zero.</li>
<li><b>CpuEventHandle</b> must be a valid event handle.</li>
</ul>
Setting this member is equivalent to setting the second bit of the 32-bit  <b>Value</b> member (0x00000002).

Supported starting with Windows 8.


### -field AllowFenceRewind

 


### -field DXGK_SIGNAL_FLAG_INTERNAL0

 


### -field Reserved

This member is reserved and should be set to zero.

Setting this member to zero is equivalent to setting the remaining 30 bits (0xFFFFFFFC) of the 32-bit <b>Value</b> member to zeros.

Supported starting with Windows 8.

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.


### -field Value

A member in the union that is contained in D3DDDICB_SIGNALFLAGS that can hold one 32-bit value that identifies signaling behavior.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544274">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451164">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECT2</a>



<a href="https://msdn.microsoft.com/01B5E793-D075-42B5-9ADF-D033249AEE9F">pfnSignalSynchronizationObject2Cb</a>



<a href="https://msdn.microsoft.com/12ffa230-2c26-4cd3-ae83-f753a0b6ba38">pfnSignalSynchronizationObjectCb</a>
 

 

