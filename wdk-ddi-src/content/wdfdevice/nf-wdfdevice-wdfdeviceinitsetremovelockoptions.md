---
UID: NF:wdfdevice.WdfDeviceInitSetRemoveLockOptions
title: WdfDeviceInitSetRemoveLockOptions function (wdfdevice.h)
description: The WdfDeviceInitSetRemoveLockOptions method causes the framework to acquire a remove lock before delivering an IRP of any type to the driver.
old-location: wdf\wdfdeviceinitsetremovelockoptions.htm
tech.root: wdf
ms.assetid: 0BCF4141-BE4E-42C0-8986-BE039B27F5D5
ms.date: 02/26/2018
ms.keywords: WdfDeviceInitSetRemoveLockOptions, WdfDeviceInitSetRemoveLockOptions method, kmdf.wdfdeviceinitsetremovelockoptions, wdf.wdfdeviceinitsetremovelockoptions, wdfdevice/WdfDeviceInitSetRemoveLockOptions
ms.topic: function
f1_keywords:
 - "wdfdevice/WdfDeviceInitSetRemoveLockOptions"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDeviceInitSetRemoveLockOptions
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceInitSetRemoveLockOptions function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>


   The <b>WdfDeviceInitSetRemoveLockOptions</b> method causes the framework to acquire a remove lock before delivering an IRP of any type to the driver.


## -parameters




### -param DeviceInit [in]

A caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure.


### -param Options [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_remove_lock_options">WDF_REMOVE_LOCK_OPTIONS</a> structure.


## -remarks



By default, the framework acquires a remove lock before it delivers IRPs of the following major types to the driver:

<dl>
<dd>IRP_MJ_PNP</dd>
<dd>IRP_MJ_POWER</dd>
<dd>IRP_MJ_SYSTEM_CONTROL</dd>
</dl>

When the IRP completes, the framework releases the remove lock.

Starting in KMDF 1.11, the driver can optionally call <b>WdfDeviceInitSetRemoveLockOptions</b> to cause the framework to acquire a remove lock before delivering all IRP types, not just those listed above.

If your driver has kernel-mode clients that send I/O unsynchronized with the PnP state of your device, you may experience crashes due to I/O IRPs arriving after the framework device object has been removed. In this case, you can call <b>WdfDeviceInitSetRemoveLockOptions</b> to prevent the device object from being removed until I/O has completed.

<div class="alert"><b>Note</b>  <b>WdfDeviceInitSetRemoveLockOptions</b> is not supported on control objects.</div>
<div> </div>
Typically, a driver calls <b>WdfDeviceInitSetRemoveLockOptions</b> from within its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function, just before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>.

After a driver calls <b>WdfDeviceInitSetRemoveLockOptions</b>, the setting remains in effect for the lifetime of the framework device object.

For more information about remove locks, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-remove-locks">Using Remove Locks</a>.


#### Examples

This code example initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_remove_lock_options">WDF_REMOVE_LOCK_OPTIONS</a> structure and calls <b>WdfDeviceInitSetRemoveLockOptions</b>.

```cpp

WDF_REMOVE_LOCK_OPTIONS RemoveLockOptions;

WDF_REMOVE_LOCK_OPTIONS_INIT(
                             &RemoveLockOptions,
                             WDF_REMOVE_LOCK_OPTION_ACQUIRE_FOR_IO
                             );
WdfDeviceInitSetRemoveLockOptions(
                                  DeviceInit,
                                  &RemoveLockOptions
                                  );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_remove_lock_options">WDF_REMOVE_LOCK_OPTIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_remove_lock_options_flags">WDF_REMOVE_LOCK_OPTIONS_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdf_remove_lock_options_init">WDF_REMOVE_LOCK_OPTIONS_INIT</a>
 

 

