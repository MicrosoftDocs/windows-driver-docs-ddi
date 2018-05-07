---
UID: NF:wdfdevice.WdfDeviceInitFree
title: WdfDeviceInitFree function
author: windows-driver-content
description: The WdfDeviceInitFree method deallocates a WDFDEVICE_INIT structure.
old-location: wdf\wdfdeviceinitfree.htm
old-project: wdf
ms.assetid: 61540bd2-8496-4972-854c-968b53c90788
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_c2bdf168-0e3f-40c9-9e88-77faf7241bcb.xml, WdfDeviceInitFree, WdfDeviceInitFree method, kmdf.wdfdeviceinitfree, wdf.wdfdeviceinitfree, wdfdevice/WdfDeviceInitFree
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DoubleDeviceInitFree, DriverCreate, InitFreeDeviceCallback, InitFreeDeviceCreate, InitFreeDeviceCreateType2, InitFreeDeviceCreateType4, InitFreeNull, KmdfIrql, KmdfIrql2, PdoInitFreeDeviceCallback, PdoInitFreeDeviceCreate, PdoInitFreeDeviceCreateType2, PdoInitFreeDeviceCreateType4
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
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
api_name:
-	WdfDeviceInitFree
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceInitFree function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceInitFree</b> method deallocates a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


## -returns



None




## -remarks



If your driver receives a WDFDEVICE_INIT structure from a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548786">WdfPdoInitAllocate</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545841">WdfControlDeviceInitAllocate</a>, and if the driver subsequently encounters an error when it calls a <a href="https://msdn.microsoft.com/38a8d316-6d66-4c1a-bb1c-93e2893542e8">device object initialization method</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>, the driver must call <b>WdfDeviceInitFree</b>. 

Your driver must not call <b>WdfDeviceInitFree</b> after it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a> successfully.

Your driver does not need to call <b>WdfDeviceInitFree</b> if it received the WDFDEVICE_INIT structure as input to its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function, because the framework deletes the structure after the callback function returns.

For more information about calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.


#### Examples

The following code example calls <b>WdfDeviceInitFree</b> if a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548802">WdfPdoInitAssignRawDevice</a> fails.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS  status;

status = WdfPdoInitAssignRawDevice(
                                   pDeviceInit,
                                   &amp;GUID_DEVCLASS_KEYBOARD
                                   );
if (!NT_SUCCESS(status)) {
    WdfDeviceInitFree(pDeviceInit);
    pDeviceInit = NULL;
    return STATUS;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>
 

 

