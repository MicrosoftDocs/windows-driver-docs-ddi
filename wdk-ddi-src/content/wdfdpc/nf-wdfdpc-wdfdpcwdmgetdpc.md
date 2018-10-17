---
UID: NF:wdfdpc.WdfDpcWdmGetDpc
title: WdfDpcWdmGetDpc function
author: windows-driver-content
description: The WdfDpcWdmGetDpc method returns a pointer to the KDPC structure that is associated with a specified framework DPC object.
old-location: wdf\wdfdpcwdmgetdpc.htm
tech.root: wdf
ms.assetid: a4ca55f9-0fbd-4969-8807-baa79099cff0
ms.date: 2/26/2018
ms.keywords: DFDpcObjectRef_26bd69e5-277b-4af4-a5b7-659670b39fbb.xml, WdfDpcWdmGetDpc, WdfDpcWdmGetDpc method, kmdf.wdfdpcwdmgetdpc, wdf.wdfdpcwdmgetdpc, wdfdpc/WdfDpcWdmGetDpc
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
-	WdfDpcWdmGetDpc
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDpcWdmGetDpc function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDpcWdmGetDpc</b> method returns a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551882">KDPC</a> structure that is associated with a specified framework DPC object.


## -parameters




### -param Dpc [in]

A handle to a framework DPC object.


## -returns



<b>WdfDpcWdmGetDpc</b> returns a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551882">KDPC</a> structure that is associated with the specified framework DPC object.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The framework creates a KDPC structure when a framework-based driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547140">WdfDpcCreate</a> to create a DPC object. 

A driver might call <b>WdfDpcWdmGetDpc</b> from within its <a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a> callback function.

The pointer that <b>WdfDpcWdmGetDpc</b> returns is valid until the framework DPC object is deleted. If the driver provides an <a href="https://msdn.microsoft.com/aba2efca-7d1f-4594-af65-13356f0e3f8b">EvtCleanupCallback</a> function for the framework DPC object, the pointer is valid until the callback function returns.


#### Examples

The following code example returns a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551882">KDPC</a> structure that is associated with a specified DPC object. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff547140">WdfDpcCreate</a> code example shows how the specified DPC object was created.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PKDPC pWdmDpc;

pWdmDpc = WdfDpcWdmGetDpc(PDevExt-&gt;CompleteWriteDpc);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551882">KDPC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551296">WDF_DPC_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547140">WdfDpcCreate</a>
 

 

