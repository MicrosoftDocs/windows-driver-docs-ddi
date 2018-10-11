---
UID: NF:wdfinterrupt.WdfInterruptEnable
title: WdfInterruptEnable function
author: windows-driver-content
description: The WdfInterruptEnable method enables a specified device interrupt by calling the driver's EvtInterruptEnable callback function.
old-location: wdf\wdfinterruptenable.htm
tech.root: wdf
ms.assetid: e2ffab7f-b6bf-4707-9a3d-9619330b2af1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFInterruptObjectRef_4fa737c9-fae4-4d3c-9a27-165f5348c66c.xml, WdfInterruptEnable, WdfInterruptEnable method, kmdf.wdfinterruptenable, wdf.wdfinterruptenable, wdfinterrupt/WdfInterruptEnable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfInterruptEnable
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfInterruptEnable function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfInterruptEnable</b> method enables a specified device interrupt by calling the driver's <a href="https://msdn.microsoft.com/981195e6-6f62-4a6f-9c84-d98f6cd7bab3">EvtInterruptEnable</a> callback function.


## -parameters




### -param Interrupt [in]

A handle to a framework interrupt object.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Most framework-based drivers don't need to call <b>WdfInterruptEnable</b>, because the framework calls the driver's <a href="https://msdn.microsoft.com/981195e6-6f62-4a6f-9c84-d98f6cd7bab3">EvtInterruptEnable</a> callback function each time the device enters its working (D0) state.

For <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-passive-level-interrupts">passive-level interrupt objects</a>, the framework calls <b>WdfInterruptEnable</b> at PASSIVE_LEVEL.

Do not call <b>WdfInterruptEnable</b> from an arbitrary thread context,  such as a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-handlers">request handler</a>.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.


#### Examples

The following code example enables the device interrupt that is associated with a specified interrupt object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfInterruptEnable(Interrupt);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/981195e6-6f62-4a6f-9c84-d98f6cd7bab3">EvtInterruptEnable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547351">WdfInterruptDisable</a>
 

 

