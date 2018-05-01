---
UID: NF:wdfinterrupt.WdfInterruptGetDevice
title: WdfInterruptGetDevice function
author: windows-driver-content
description: The WdfInterruptGetDevice method returns a handle to the framework device object that is associated with a specified framework interrupt object.
old-location: wdf\wdfinterruptgetdevice.htm
old-project: wdf
ms.assetid: c1e7a9ce-5794-4ed0-bb30-e3e68b0251db
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFInterruptObjectRef_9c646459-e17b-434f-b313-d22f3a211c4e.xml, WdfInterruptGetDevice, WdfInterruptGetDevice method, kmdf.wdfinterruptgetdevice, wdf.wdfinterruptgetdevice, wdfinterrupt/WdfInterruptGetDevice
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
req.irql: "<= DIRQL"
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
-	WdfInterruptGetDevice
product: Windows
targetos: Windows
req.typenames: 
---

# WdfInterruptGetDevice function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfInterruptGetDevice</b> method returns a handle to the framework device object that is associated with a specified framework interrupt object.


## -parameters




### -param Interrupt [in]

A handle to a framework interrupt object.


## -returns



<b>WdfInterruptGetDevice</b> returns a handle to a framework device object.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about handling interrupts in framework-based drivers, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.


#### Examples

The following code example shows how an <a href="https://msdn.microsoft.com/6f28a66a-9c17-4020-bfe2-295c22af6ba7">EvtInterruptIsr</a> callback function can obtain a pointer to driver-defined context space for the device object that an interrupt object belongs to.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BOOLEAN
MyEvtInterruptIsr(
    IN WDFINTERRUPT Interrupt,
    IN ULONG  MessageID
    )
{
    PDEVICE_EXTENSION  devExt;

    devExt = GetMyDeviceContext(WdfInterruptGetDevice(Interrupt));
...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/6f28a66a-9c17-4020-bfe2-295c22af6ba7">EvtInterruptIsr</a>
 

 

