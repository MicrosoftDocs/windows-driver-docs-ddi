---
UID: NC:wdfdriver.EVT_WDF_DRIVER_UNLOAD
title: EVT_WDF_DRIVER_UNLOAD
author: windows-driver-content
description: A driver's EvtDriverUnload event callback function performs operations that must take place before the driver is unloaded.
old-location: wdf\evtdriverunload.htm
tech.root: wdf
ms.assetid: 2a2ed215-1b62-4ff1-bea6-e38fafbcf7d0
ms.date: 02/26/2018
ms.keywords: DFDriverObjectRef_4c29e844-1ad7-4d45-b01d-e03f841bb9dd.xml, EVT_WDF_DRIVER_UNLOAD, EVT_WDF_DRIVER_UNLOAD callback, EvtDriverUnload, EvtDriverUnload callback function, kmdf.evtdriverunload, wdf.evtdriverunload, wdfdriver/EvtDriverUnload
ms.topic: callback
req.header: wdfdriver.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdfdriver.h
api_name:
-	EvtDriverUnload
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DRIVER_UNLOAD callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDriverUnload</i> event callback function performs operations that must take place before the driver is unloaded.


## -parameters




### -param Driver [in]

A handle to a framework driver object.


## -returns



None




## -remarks

A driver registers an <i>EvtDriverUnload</i> callback function when it calls [**WdfDriverCreate**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdriver/nf-wdfdriver-wdfdrivercreate).

The <i>EvtDriverUnload</i> callback function must deallocate any non-device-specific system resources that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine allocated.

The framework does not call a driver's 
    <i>EvtDriverUnload</i> callback function if the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine returns an error status value.

You must declare the function by using the EVT_WDF_DRIVER_UNLOAD type. For more information, see the following Example section.


#### Examples

To define an <i>EvtDriverUnload</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDriverUnload</i> callback function that is named <i>MyDriverUnload</i>, use the <b>EVT_WDF_DRIVER_UNLOAD</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DRIVER_UNLOAD  MyDriverUnload;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID 
MyDriverUnload (
    WDFDRIVER Driver
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DRIVER_UNLOAD</b> function type is defined in the WdfDriver.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DRIVER_UNLOAD</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a>
 

 

