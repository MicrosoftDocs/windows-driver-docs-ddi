---
UID: NF:wdfdevice.WdfWdmDeviceGetWdfDeviceHandle
title: WdfWdmDeviceGetWdfDeviceHandle function (wdfdevice.h)
description: The WdfWdmDeviceGetWdfDeviceHandle method returns a handle to the framework device object that is associated with a specified WDM device object.
old-location: wdf\wdfwdmdevicegetwdfdevicehandle.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfWdmDeviceGetWdfDeviceHandle function"]
ms.keywords: DFDeviceObjectGeneralRef_0b05680a-5252-4932-802d-ee24a0092116.xml, WdfWdmDeviceGetWdfDeviceHandle, WdfWdmDeviceGetWdfDeviceHandle method, kmdf.wdfwdmdevicegetwdfdevicehandle, wdf.wdfwdmdevicegetwdfdevicehandle, wdfdevice/WdfWdmDeviceGetWdfDeviceHandle
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfWdmDeviceGetWdfDeviceHandle
 - wdfdevice/WdfWdmDeviceGetWdfDeviceHandle
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfWdmDeviceGetWdfDeviceHandle
---

# WdfWdmDeviceGetWdfDeviceHandle function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfWdmDeviceGetWdfDeviceHandle</b> method returns a handle to the framework device object that is associated with a specified WDM device object.

## -parameters

### -param DeviceObject [in]


A pointer to a WDM <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure that the calling driver created.

## -returns

If the specified WDM device object is valid, <b>WdfWdmDeviceGetWdfDeviceHandle</b> returns a handle to the associated framework device object. Otherwise, the method returns <b>NULL</b>.

## -remarks

The WDM DEVICE_OBJECT structure that the driver specifies for the <i>DeviceObject</i> parameter must represent a device object that the calling driver created. For example, the structure cannot represent any of the WDM device objects that the driver specified in a previous call to <a href="/windows-hardware/drivers/ddi/wdfminiport/nf-wdfminiport-wdfdeviceminiportcreate">WdfDeviceMiniportCreate</a>.


#### Examples

The following code example obtains a handle to the framework device object that is associated with a WDM device object that the calling driver created.

```cpp
WDFDEVICE  device;

device = WdfWdmDeviceGetWdfDeviceHandle(pWdmDeviceObject);
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfminiport/nf-wdfminiport-wdfdeviceminiportcreate">WdfDeviceMiniportCreate</a>
