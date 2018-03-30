---
UID: NF:wdfdpc.WdfDpcEnqueue
title: WdfDpcEnqueue function
author: windows-driver-content
description: The WdfDpcEnqueue method schedules the execution of a DPC object's EvtDpcFunc callback function.
old-location: wdf\wdfdpcenqueue.htm
old-project: wdf
ms.assetid: 08bc78de-ba04-4845-9d22-c06cd5684f7f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDpcObjectRef_76e257ac-ac8b-4724-8a24-6828bfe93e74.xml, WdfDpcEnqueue, WdfDpcEnqueue method, kmdf.wdfdpcenqueue, wdf.wdfdpcenqueue, wdfdpc/WdfDpcEnqueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdpc.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfDpcEnqueue
product: Windows
targetos: Windows
req.typenames: WDF_DMA_SYSTEM_PROFILE_CONFIG, *PWDF_DMA_SYSTEM_PROFILE_CONFIG
req.product: Windows 10 or later.
---

# WdfDpcEnqueue function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDpcEnqueue</b> method schedules the execution of a DPC object's <a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a> callback function.


## -parameters




### -param Dpc [in]

A handle to a framework DPC object.


## -returns



<b>WdfDpcEnqueue</b> returns <b>TRUE</b> if it successfully adds the specified DPC object to the system's DPC queue. Otherwise, the method returns <b>FALSE</b>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The <b>WdfDpcEnqueue</b> method adds the specified DPC object to the system's DPC queue, if it is not already in the queue. (If the DPC object was already in the queue, the method returns <b>FALSE</b>.) When the system is not executing higher-priority tasks, it removes the DPC object from the queue and calls the object's <a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a> callback function. 

After the callback function executes, a subsequent call to <b>WdfDpcEnqueue</b> will add the DPC object back into the DPC queue.

For more information about using DPC objects, see <a href="https://msdn.microsoft.com/b6306d2c-a7be-4fc3-8123-4d2b5c60c988">Servicing an Interrupt</a>.


#### Examples

The following code example schedules the execution of the callback function that is associated with a DPC object. The example uses the <b>WdfDpcEnqueue</b> method's return value as the containing function's return value. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff547140">WdfDpcCreate</a> code example shows how the DPC object was created.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>return WdfDpcEnqueue(PDevExt-&gt;CompleteWriteDpc);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547140">WdfDpcCreate</a>
 

 

