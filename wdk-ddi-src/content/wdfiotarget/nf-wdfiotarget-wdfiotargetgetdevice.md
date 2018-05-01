---
UID: NF:wdfiotarget.WdfIoTargetGetDevice
title: WdfIoTargetGetDevice function
author: windows-driver-content
description: The WdfIoTargetGetDevice method returns a handle to the framework device object that is the parent of the specified local or remote I/O target.
old-location: wdf\wdfiotargetgetdevice.htm
old-project: wdf
ms.assetid: 2e076f2f-59e3-43ca-b83e-3079bbf41df3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFIOTargetRef_796e5254-23b4-4ed1-b02b-66c5c8560769.xml, WdfIoTargetGetDevice, WdfIoTargetGetDevice method, kmdf.wdfiotargetgetdevice, wdf.wdfiotargetgetdevice, wdfiotarget/WdfIoTargetGetDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfiotarget.h
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
-	WdfIoTargetGetDevice
product: Windows
targetos: Windows
req.typenames: 
---

# WdfIoTargetGetDevice function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoTargetGetDevice</b> method returns a handle to the framework device object that is the parent of the specified local or remote I/O target.


## -parameters




### -param IoTarget [in]

A handle to an I/O target object. This handle is obtained from <a href="https://msdn.microsoft.com/library/windows/hardware/ff546017">WdfDeviceGetIoTarget</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548591">WdfIoTargetCreate</a>, or from a method that a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/introduction-to-i-o-targets">specialized I/O target</a> supplies (such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff550093">WdfUsbTargetDeviceGetIoTarget</a>).


## -returns



<b>WdfIoTargetGetDevice</b> returns a handle to a framework device object.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about <b>WdfIoTargetGetDevice</b>, see <a href="https://msdn.microsoft.com/70ae920e-de2d-4014-bae4-74058b26e7c0">Obtaining Information About a General I/O Target</a>. 

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.


#### Examples

The following code example is shows how an <a href="https://msdn.microsoft.com/cb7c97e5-081e-44fc-a759-9a1ae81de41c">EvtIoTargetQueryRemove</a> callback function can call <b>WdfIoTargetGetDevice</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
MyEvtIoTargetQueryRemove(
    WDFIOTARGET IoTarget
)
{
WDFDEVICE device;
...
device = WdfIoTargetGetDevice(IoTarget);
...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546017">WdfDeviceGetIoTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548591">WdfIoTargetCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550093">WdfUsbTargetDeviceGetIoTarget</a>
 

 

