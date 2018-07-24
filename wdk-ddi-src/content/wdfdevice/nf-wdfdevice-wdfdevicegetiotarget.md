---
UID: NF:wdfdevice.WdfDeviceGetIoTarget
title: WdfDeviceGetIoTarget function
author: windows-driver-content
description: The WdfDeviceGetIoTarget method returns a handle to a function or filter driver's local I/O target, for a specified device.
old-location: wdf\wdfdevicegetiotarget.htm
tech.root: wdf
ms.assetid: a0749324-8b4e-4b82-8c51-b1b8883d521e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_df48e631-f54d-4985-bc74-05c220b735f5.xml, WdfDeviceGetIoTarget, WdfDeviceGetIoTarget method, kmdf.wdfdevicegetiotarget, wdf.wdfdevicegetiotarget, wdfdevice/WdfDeviceGetIoTarget
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
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
req.irql: "<= DISPATCH_LEVEL"
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
-	WdfDeviceGetIoTarget
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceGetIoTarget function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceGetIoTarget</b> method returns a handle to a function or filter driver's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/general-i-o-targets">local I/O target</a>, for a specified device.


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns



If the operation succeeds, <b>WdfDeviceGetIoTarget</b> returns a handle to a framework I/O target object. If the specified framework device object represents a PDO, the method returns <b>NULL</b>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



When a UMDF driver sends a driver-created request to a local I/O target, the request has no associated file object. Some lower targets, such as a HIDClass-enumerated raw PDO, fail requests that have no associated file object. In this situation, a UMDF driver can specify <b>WdfIoTargetOpenLocalTargetByFile</b> to create an I/O target that represents the lower stack (just like a local target) using a file handle. As a result, any driver-created requests sent to this I/O target are associated with the file object corresponding to the handle opened.

 To do so, call the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265641">WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE</a> function before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548634">WdfIoTargetOpen</a>.

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.


#### Examples

The following code example obtains a handle to a specified device's local I/O target.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDFIOTARGET  ioTargetHandle;

ioTargetHandle = WdfDeviceGetIoTarget(device);</pre>
</td>
</tr>
</table></span></div>


