---
UID: NF:wdfdevice.WdfDeviceWdmGetAttachedDevice
title: WdfDeviceWdmGetAttachedDevice function (wdfdevice.h)
description: The WdfDeviceWdmGetAttachedDevice method returns the next-lower WDM device object in the device stack.
old-location: wdf\wdfdevicewdmgetattacheddevice.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfDeviceWdmGetAttachedDevice function"]
ms.keywords: DFDeviceObjectGeneralRef_cfd9610b-28f6-4c5c-a532-9c5fae3576fc.xml, WdfDeviceWdmGetAttachedDevice, WdfDeviceWdmGetAttachedDevice method, kmdf.wdfdevicewdmgetattacheddevice, wdf.wdfdevicewdmgetattacheddevice, wdfdevice/WdfDeviceWdmGetAttachedDevice
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDeviceWdmGetAttachedDevice
 - wdfdevice/WdfDeviceWdmGetAttachedDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfDeviceWdmGetAttachedDevice
---

# WdfDeviceWdmGetAttachedDevice function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceWdmGetAttachedDevice</b> method returns the next-lower WDM device object in the <a href="/windows-hardware/drivers/wdf/wdm-concepts-for-kmdf-drivers">device stack</a>.

## -parameters

### -param Device [in]


A handle to a framework device object.

## -returns

<b>WdfDeviceWdmGetAttachedDevice</b> returns a pointer to a WDM <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure. If the specified object handle represents a physical device object (PDO), the method returns <b>NULL</b>.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

The pointer that the <b>WdfDeviceWdmGetAttachedDevice</b> method returns is valid until the framework device object is deleted. If the driver provides an <a href="/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> function for the framework device object, the pointer is valid until the callback function returns.


#### Examples

The following code example creates a tracing message that contains pointers to the WDM device objects that represent a device's PDO, FDO, and next-lower device.

```cpp
TraceEvents(
            TRACE_LEVEL_INFORMATION,
            DBG_PNP,
            "PDO(0x%p) FDO(0x%p), Lower(0x%p)\n",
            WdfDeviceWdmGetPhysicalDevice(device),
            WdfDeviceWdmGetDeviceObject(device),
            WdfDeviceWdmGetAttachedDevice(device)
            );
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmgetdeviceobject">WdfDeviceWdmGetDeviceObject</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmgetphysicaldevice">WdfDeviceWdmGetPhysicalDevice</a>
