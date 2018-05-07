---
UID: NF:ks.KsPinRegisterIrpCompletionCallback
title: KsPinRegisterIrpCompletionCallback function
author: windows-driver-content
description: The KsPinRegisterIrpCompletionCallback function registers a minidriver-defined callback routine for a specified pin.
old-location: stream\kspinregisterirpcompletioncallback.htm
old-project: stream
ms.assetid: d2872ea2-565b-47db-8054-876fd3c8fc4d
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KsPinRegisterIrpCompletionCallback, KsPinRegisterIrpCompletionCallback function [Streaming Media Devices], avfunc_ab906fd4-c863-467e-828e-34316fb65269.xml, ks/KsPinRegisterIrpCompletionCallback, stream.kspinregisterirpcompletioncallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsPinRegisterIrpCompletionCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPinRegisterIrpCompletionCallback function


## -description


The <b>KsPinRegisterIrpCompletionCallback</b> function registers a minidriver-defined callback routine for a specified pin. AVStream calls the minidriver-provided routine when an IRP completes a pass around the circuit and the frame that is associated with the IRP is about to be recycled or retired.


## -parameters




### -param Pin [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> structure for which to register a completion callback.


### -param IrpCompletion [in]

This parameter supplies the address of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff556340">AVStrMiniPinIrpCompletion</a> routine to be called when an IRP completes its traversal of the circuit and is about to be recycled or retired.


## -returns



None




## -remarks



<b>KsPinRegisterIrpCompletionCallback </b>must be called at IRQL=PASSIVE_LEVEL before the pin goes into KSSTATE_ACQUIRE. For more information about pin states, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566856">KSSTATE</a>.

This function is frequently called from the pin creation dispatch. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff563535">KSPIN_DISPATCH</a>.

<b>KsPinRegisterIrpCompletionCallback</b> is only useful on IRP source pins, and is typically used on data source pins. For a data source pin, the callback is made once the IRP is completed back to the pin and is about to be recycled. For a data sink pin, however, the callback is not tied directly to IRP completion. AVStream still makes the callback when the IRP returns for recycling. This return does not occur until that IRP has passed through all the queues that need to use the data that it contains. For information about IRP source/sink pins versus data source/sink pins, see the <b>DataFlow</b> and <b>Communication</b> members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563533">KSPIN_DESCRIPTOR</a> structure.

<b>KsPinRegisterIrpCompletionCallback</b> differs significantly from <a href="https://msdn.microsoft.com/library/windows/hardware/ff563522">KsPinRegisterFrameReturnCallback</a> in that this routine does not place the pin in any new mode; it simply registers a callback routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556334">AVStrMiniPinCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556340">AVStrMiniPinIrpCompletion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563535">KSPIN_DISPATCH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566856">KSSTATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563522">KsPinRegisterFrameReturnCallback</a>
 

 

