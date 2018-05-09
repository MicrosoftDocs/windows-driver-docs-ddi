---
UID: NF:wdfinterrupt.WdfInterruptGetInfo
title: WdfInterruptGetInfo function
author: windows-driver-content
description: The WdfInterruptGetInfo method retrieves information about a specified interrupt.
old-location: wdf\wdfinterruptgetinfo.htm
old-project: wdf
ms.assetid: 11f086af-bda7-4dab-8c4b-0db2e89588d1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFInterruptObjectRef_eb163aa0-1ba3-491d-b215-85c8773dcfc9.xml, WdfInterruptGetInfo, WdfInterruptGetInfo method, kmdf.wdfinterruptgetinfo, wdf.wdfinterruptgetinfo, wdfinterrupt/WdfInterruptGetInfo
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
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
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
-	WdfInterruptGetInfo
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfInterruptGetInfo function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfInterruptGetInfo</b> method retrieves information about a specified interrupt.


## -parameters




### -param Interrupt [in]

A handle to the interrupt object.


### -param Info [out]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/hh464020">WDF_INTERRUPT_INFO</a> structure that has been initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh464024">WDF_INTERRUPT_INFO_INIT</a>.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The <b>WdfInterruptGetInfo</b> method can obtain interrupt information only if your driver calls it after the framework has called the driver's <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a> callback function and before the framework has called the driver's <a href="https://msdn.microsoft.com/b4c17e57-688c-4c76-892c-5c8abbf83f20">EvtDeviceReleaseHardware</a> callback function. 

After <b>WdfInterruptGetInfo</b> has returned, the driver can identify passive level interrupt objects by examining the <b>Irql</b> member of the  <a href="https://msdn.microsoft.com/library/windows/hardware/hh464020">WDF_INTERRUPT_INFO</a> structure. For passive level interrupt objects, this value is PASSIVE_LEVEL.

For information about the order in which a driver's callback functions are called, see <a href="https://msdn.microsoft.com/9175ce95-196d-44bd-b31c-88386fa0d3d3">PnP and Power Management Scenarios</a>.

For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.


#### Examples

The following code example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/hh464020">WDF_INTERRUPT_INFO</a> structure and calls <b>WdfInterruptGetInfo</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_INTERRUPT_INFO  Info;

WDF_INTERRUPT_INFO_INIT(&amp;Info);
WdfInterruptGetInfo(
                    Interrupt,
                    &amp;Info
                    );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a>



<a href="https://msdn.microsoft.com/b4c17e57-688c-4c76-892c-5c8abbf83f20">EvtDeviceReleaseHardware</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464020">WDF_INTERRUPT_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464024">WDF_INTERRUPT_INFO_INIT</a>
 

 

