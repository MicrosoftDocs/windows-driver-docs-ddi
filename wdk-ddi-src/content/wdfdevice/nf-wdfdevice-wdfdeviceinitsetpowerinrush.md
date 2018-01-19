---
UID: NF:wdfdevice.WdfDeviceInitSetPowerInrush
title: WdfDeviceInitSetPowerInrush function
author: windows-driver-content
description: The WdfDeviceInitSetPowerInrush method informs the power manager that the specified device requires an inrush of current when it starts.
old-location: wdf\wdfdeviceinitsetpowerinrush.htm
old-project: wdf
ms.assetid: 91b29a5b-8bc0-44c0-8c48-2d023da12dcb
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDeviceInitSetPowerInrush
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
req.alt-api: WdfDeviceInitSetPowerInrush
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: ChildDeviceInitAPI, DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceInitSetPowerInrush function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceInitSetPowerInrush</b> method informs the power manager that the specified device requires an inrush of current when it starts.



## -syntax

````
VOID WdfDeviceInitSetPowerInrush(
  _In_ PWDFDEVICE_INIT DeviceInit
);
````


## -parameters

### -param DeviceInit [in]

A caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


## -returns
None


## -remarks
To avoid overloading the system's power supply, the system starts devices that require an inrush of current one at a time.

If your driver calls <b>WdfDeviceInitSetPowerInrush</b>, the framework makes it <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-pageable-code-in-a-kmdf-driver">nonpageable</a> during power state transitions and the driver must not call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpowerpageable.md">WdfDeviceInitSetPowerPageable</a>. 

Your driver must call <b>WdfDeviceInitSetPowerInrush</b> before it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

Calling <b>WdfDeviceInitSetPowerInrush</b> from a filter driver has no effect. For filter drivers, the framework uses the setting that the next-lower driver in the driver stack specifies.

The following code example informs the power manager that a device requires an inrush of current when it starts.


## -see-also
<dl>
<dt>
<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceInitSetPowerInrush method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

