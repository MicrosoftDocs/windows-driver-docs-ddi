---
UID: NF:wdfdpc.WdfDpcCancel
title: WdfDpcCancel function
author: windows-driver-content
description: The WdfDpcCancel method attempts to cancel the execution of a DPC object's scheduled EvtDpcFunc callback function.
old-location: wdf\wdfdpccancel.htm
old-project: wdf
ms.assetid: 6eb56c5b-d198-4542-a239-c54b49561196
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wdf.wdfdpccancel, DFDpcObjectRef_4efcdae1-0c0a-4808-a1d8-640dea3555cb.xml, WdfDpcCancel method, WdfDpcCancel, wdfdpc/WdfDpcCancel, kmdf.wdfdpccancel
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
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfDpcCancel
product: Windows
targetos: Windows
req.typenames: "*PWDF_DMA_SYSTEM_PROFILE_CONFIG, WDF_DMA_SYSTEM_PROFILE_CONFIG"
req.product: Windows 10 or later.
---

# WdfDpcCancel function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDpcCancel</b> method attempts to cancel the execution of a DPC object's scheduled <a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a> callback function.


## -syntax


````
BOOLEAN WdfDpcCancel(
  _In_ WDFDPC  Dpc,
  _In_ BOOLEAN Wait
);
````


## -parameters




### -param Dpc [in]

A handle to a framework DPC object.


### -param Wait [in]

A Boolean value that, if <b>TRUE</b>, indicates that the <b>WdfDpcCancel</b> method will not return until the DPC object's <a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a> callback function is either canceled or finishes executing. If <b>FALSE</b>, the <b>WdfDpcCancel</b> method returns immediately.


## -returns



<b>WdfDpcCancel</b> returns <b>TRUE</b> if the specified DPC object's <a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a> callback function was in the system's DPC queue. The method returns <b>FALSE</b> if the callback function was not in the DPC queue, either because the callback function was executing or because it had finished executing.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



If the specified DPC object's <a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a> callback function is in the system's DPC queue, it is removed from the queue. If the <i>EvtDpcFunc</i> function is not in the queue, it is either executing or has finished executing. 

If the <i>Wait</i> parameter is <b>TRUE</b>, <b>WdfDpcCancel</b> must be called at IRQL = PASSIVE_LEVEL. If the <i>Wait</i> parameter is <b>FALSE</b>, <b>WdfDpcCancel</b> can be called at any IRQL.


#### Examples

The following code example cancels the execution of the callback function that is associated with the DPC object that the code example in the <a href="..\wdfdpc\nf-wdfdpc-wdfdpccreate.md">WdfDpcCreate</a> topic created.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfDpcCancel(
             PDevExt-&gt;CompleteWriteDpc,
             TRUE
             );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDpcCancel method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

