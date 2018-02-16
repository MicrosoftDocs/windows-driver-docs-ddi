---
UID: NF:wdfdpc.WdfDpcWdmGetDpc
title: WdfDpcWdmGetDpc function
author: windows-driver-content
description: The WdfDpcWdmGetDpc method returns a pointer to the KDPC structure that is associated with a specified framework DPC object.
old-location: wdf\wdfdpcwdmgetdpc.htm
old-project: wdf
ms.assetid: a4ca55f9-0fbd-4969-8807-baa79099cff0
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFDPCWDMGETDPC, kmdf.wdfdpcwdmgetdpc, wdfdpc/WdfDpcWdmGetDpc, WdfDpcWdmGetDpc method, WdfDpcWdmGetDpc, DFDpcObjectRef_26bd69e5-277b-4af4-a5b7-659670b39fbb.xml, wdf.wdfdpcwdmgetdpc
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfDpcWdmGetDpc
product: Windows
targetos: Windows
req.typenames: "*PWDF_DMA_SYSTEM_PROFILE_CONFIG, WDF_DMA_SYSTEM_PROFILE_CONFIG"
req.product: Windows 10 or later.
---

# WdfDpcWdmGetDpc function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDpcWdmGetDpc</b> method returns a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551882">KDPC</a> structure that is associated with a specified framework DPC object.


## -syntax


````
PKDPC WdfDpcWdmGetDpc(
  _In_ WDFDPC Dpc
);
````


## -parameters




### -param Dpc [in]

A handle to a framework DPC object.


## -returns



<b>WdfDpcWdmGetDpc</b> returns a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551882">KDPC</a> structure that is associated with the specified framework DPC object.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The framework creates a KDPC structure when a framework-based driver calls <a href="..\wdfdpc\nf-wdfdpc-wdfdpccreate.md">WdfDpcCreate</a> to create a DPC object. 

A driver might call <b>WdfDpcWdmGetDpc</b> from within its <a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a> callback function.

The pointer that <b>WdfDpcWdmGetDpc</b> returns is valid until the framework DPC object is deleted. If the driver provides an <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> function for the framework DPC object, the pointer is valid until the callback function returns.


#### Examples

The following code example returns a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551882">KDPC</a> structure that is associated with a specified DPC object. The <a href="..\wdfdpc\nf-wdfdpc-wdfdpccreate.md">WdfDpcCreate</a> code example shows how the specified DPC object was created.

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

<a href="..\wdfdpc\nf-wdfdpc-wdfdpccreate.md">WdfDpcCreate</a>



<a href="https://msdn.microsoft.com/b934a0da-0709-4427-bbf2-8d53f9511cf1">EvtDpcFunc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551882">KDPC</a>



<a href="..\wdfdpc\ns-wdfdpc-_wdf_dpc_config.md">WDF_DPC_CONFIG</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDpcWdmGetDpc method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

