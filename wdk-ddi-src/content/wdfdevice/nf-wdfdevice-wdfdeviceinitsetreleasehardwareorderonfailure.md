---
UID: NF:wdfdevice.WdfDeviceInitSetReleaseHardwareOrderOnFailure
title: WdfDeviceInitSetReleaseHardwareOrderOnFailure function
author: windows-driver-content
description: The WdfDeviceInitSetReleaseHardwareOrderOnFailure method specifies whether the framework calls the driver's EvtDeviceReleaseHardware callback function immediately after device failure, or waits until all child devices have been removed.
old-location: wdf\wdfdeviceinitsetreleasehardwareorderonfailure.htm
old-project: wdf
ms.assetid: 5DC3C7C8-E7D1-4874-AF8D-8E6FD48DF046
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.wdfdeviceinitsetreleasehardwareorderonfailure, kmdf.wdfdeviceinitsetreleasehardwareorderonfailure, WdfDeviceInitSetReleaseHardwareOrderOnFailure method, wdfdevice/WdfDeviceInitSetReleaseHardwareOrderOnFailure, PFN_WDFDEVICEINITSETRELEASEHARDWAREORDERONFAILURE, WdfDeviceInitSetReleaseHardwareOrderOnFailure
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfDeviceInitSetReleaseHardwareOrderOnFailure
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceInitSetReleaseHardwareOrderOnFailure function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]


   The <b>WdfDeviceInitSetReleaseHardwareOrderOnFailure</b> method specifies whether the framework calls the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a> callback function immediately after device failure, or waits until all child devices have been removed.


## -syntax


````
void WdfDeviceInitSetReleaseHardwareOrderOnFailure(
  _In_ PWDFDEVICE_INIT                       DeviceInit,
  _In_ WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE ReleaseHardwareOrderOnFailure
);
````


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param ReleaseHardwareOrderOnFailure [in]

A <a href="..\wdfdevice\ne-wdfdevice-_wdf_release_hardware_order_on_failure.md">WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE</a>-typed enumerator that specifies when the framework calls the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a> callback function.


## -returns



This method does not return a value.




## -remarks



Typically, the framework calls a driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a> callback function after it has called the <i>EvtDeviceReleaseHardware</i> function for all child devices that the driver enumerates.

In the event of a device power-up or power-down failure, however, the framework might call the  driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a> before it has called the <i>EvtDeviceReleaseHardware</i> functions for all child devices.

To override this default behavior, a driver can call <b>WdfDeviceInitSetReleaseHardwareOrderOnFailure</b> to specify that, even in device failure scenarios, the framework should always wait to call its <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a> function until it has called the <i>EvtDeviceReleaseHardware</i> functions of the child devices.

 For example, a bus driver that performs hardware access on behalf of its child devices could use this technique to ensure that its child devices do not request access to hardware after the framework has called the bus driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a> callback function.

If a driver calls <b>WdfDeviceInitSetReleaseHardwareOrderOnFailure</b>, it must do so before it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.


#### Examples

The following code example shows how a bus driver can request that the framework wait to call its <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a> callback function until all of its child devices have been removed.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfDeviceInitSetReleaseHardwareOrderOnFailure(
                       DeviceInit,
                       WdfReleaseHardwareOrderOnFailureAfterDescendants
                       );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a>



<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a>



<a href="..\wdfdevice\ne-wdfdevice-_wdf_release_hardware_order_on_failure.md">WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceInitSetReleaseHardwareOrderOnFailure method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

