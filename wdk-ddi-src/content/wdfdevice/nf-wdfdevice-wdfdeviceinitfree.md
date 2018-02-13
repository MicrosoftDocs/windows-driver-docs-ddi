---
UID: NF:wdfdevice.WdfDeviceInitFree
title: WdfDeviceInitFree function
author: windows-driver-content
description: The WdfDeviceInitFree method deallocates a WDFDEVICE_INIT structure.
old-location: wdf\wdfdeviceinitfree.htm
old-project: wdf
ms.assetid: 61540bd2-8496-4972-854c-968b53c90788
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDeviceInitFree, kmdf.wdfdeviceinitfree, PFN_WDFDEVICEINITFREE, DFDeviceObjectGeneralRef_c2bdf168-0e3f-40c9-9e88-77faf7241bcb.xml, wdfdevice/WdfDeviceInitFree, wdf.wdfdeviceinitfree, WdfDeviceInitFree method
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfDeviceInitFree
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceInitFree function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceInitFree</b> method deallocates a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


## -syntax


````
VOID WdfDeviceInitFree(
  _In_ PWDFDEVICE_INIT DeviceInit
);
````


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


## -returns



None




## -remarks



If your driver receives a WDFDEVICE_INIT structure from a call to <a href="..\wdfpdo\nf-wdfpdo-wdfpdoinitallocate.md">WdfPdoInitAllocate</a> or <a href="..\wdfcontrol\nf-wdfcontrol-wdfcontroldeviceinitallocate.md">WdfControlDeviceInitAllocate</a>, and if the driver subsequently encounters an error when it calls a <a href="https://msdn.microsoft.com/38a8d316-6d66-4c1a-bb1c-93e2893542e8">device object initialization method</a> or <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>, the driver must call <b>WdfDeviceInitFree</b>. 

Your driver must not call <b>WdfDeviceInitFree</b> after it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a> successfully.

Your driver does not need to call <b>WdfDeviceInitFree</b> if it received the WDFDEVICE_INIT structure as input to its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function, because the framework deletes the structure after the callback function returns.

For more information about calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.


#### Examples

The following code example calls <b>WdfDeviceInitFree</b> if a call to <a href="..\wdfpdo\nf-wdfpdo-wdfpdoinitassignrawdevice.md">WdfPdoInitAssignRawDevice</a> fails.

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

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceInitFree method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

