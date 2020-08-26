---
UID: NF:wdffdo.WdfFdoInitSetFilter
title: WdfFdoInitSetFilter function (wdffdo.h)
description: The WdfFdoInitSetFilter method identifies the calling driver as an upper-level or lower-level filter driver, for a specified device.
old-location: wdf\wdffdoinitsetfilter.htm
tech.root: wdf
ms.assetid: 6e195025-4e70-44fa-a12d-0a98417381a0
ms.date: 02/26/2018
keywords: ["WdfFdoInitSetFilter function"]
ms.keywords: DFDeviceObjectFdoPdoRef_d1040c41-d94a-489d-ab74-9b3ae1e900bb.xml, WdfFdoInitSetFilter, WdfFdoInitSetFilter method, kmdf.wdffdoinitsetfilter, wdf.wdffdoinitsetfilter, wdffdo/WdfFdoInitSetFilter
f1_keywords:
 - "wdffdo/WdfFdoInitSetFilter"
 - "WdfFdoInitSetFilter"
req.header: wdffdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DeviceInitAPI, DriverCreate, DrvAckIoStop, KmdfIrql, KmdfIrql2
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfFdoInitSetFilter
targetos: Windows
req.typenames: 
---

# WdfFdoInitSetFilter function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfFdoInitSetFilter</b> method identifies the calling driver as an upper-level or lower-level <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/filter-drivers">filter driver</a>, for a specified device.


## -parameters




### -param DeviceInit 
[in]
A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure that the driver obtained from its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function.


## -remarks



Filter drivers typically process some I/O requests, but they simply pass most requests to the next driver in the driver stack. If the framework receives a request for one of your driver's devices, and if the driver has not created an I/O queue to receive requests that match the request type, the way the framework processes the request depends on whether the driver has called <b>WdfFdoInitSetFilter</b>:

<ul>
<li>
If a driver calls <b>WdfFdoInitSetFilter</b>, the driver framework forwards the request to the next driver.

</li>
<li>
If a driver does not call <b>WdfFdoInitSetFilter</b>, the framework completes the request with a status value of STATUS_INVALID_DEVICE_REQUEST.

</li>
</ul>
If a driver calls <b>WdfFdoInitSetFilter</b>, it should not call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetiotype">WdfDeviceInitSetIoType</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpowerinrush">WdfDeviceInitSetPowerInrush</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpowerpageable">WdfDeviceInitSetPowerPageable</a> because the framework ignores the information provided by these calls. Instead, the framework obtains this information from the next-lower device object in the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdm-concepts-for-kmdf-drivers">device stack</a>.

The driver must call <b>WdfFdoInitSetFilter</b> before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>. In addition, the driver must call <b>WdfFdoInitSetFilter</b> before returning from its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function.

For more information about <b>WdfFdoInitSetFilter</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-device-objects-in-a-filter-driver">Creating Device Objects in a Filter Driver</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-i-o-queues">Creating I/O Queues</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/forwarding-i-o-requests">Forwarding I/O Requests</a>.


#### Examples

The following code example identifies the calling driver as a filter driver for the specified device.

```cpp
WdfFdoInitSetFilter(DeviceInit);
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a>
 

 

