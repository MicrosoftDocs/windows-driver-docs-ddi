---
UID: NF:hwnclx.HwNProcessAddDevicePreDeviceCreate
title: HwNProcessAddDevicePreDeviceCreate function (hwnclx.h)
description: Supplies the device prepare/release and entry/exit callbacks to the Windows Driver Foundation (WDF) for transitioning the device into different states.
old-location: gpiobtn\hwnprocessadddevicepredevicecreate.htm
tech.root: gpiobtn
ms.date: 02/15/2018
keywords: ["HwNProcessAddDevicePreDeviceCreate function"]
ms.keywords: HwNProcessAddDevicePreDeviceCreate, HwNProcessAddDevicePreDeviceCreate function, gpiobtn.hwnprocessadddevicepredevicecreate, hwnclx/HwNProcessAddDevicePreDeviceCreate
req.header: hwnclx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Mshwnclxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: HWN_CLX_EXPORT_INDEX, *PHWN_CLX_EXPORT_INDEX
f1_keywords:
 - HwNProcessAddDevicePreDeviceCreate
 - hwnclx/HwNProcessAddDevicePreDeviceCreate
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Mshwnclxstub.lib
 - Mshwnclxstub.dll
api_name:
 - HwNProcessAddDevicePreDeviceCreate
---

# HwNProcessAddDevicePreDeviceCreate function


## -description

Supplies the device prepare/release and entry/exit callbacks to the Windows Driver Foundation (WDF) for transitioning the device into different states. This function should be called by the client driver when the WDF invokes the driver’s <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EVT_WDF_DRIVER_DEVICE_ADD</a> routine, but before creating the device object.

## -parameters

### -param Driver [in]


Handle to the client drivers framework driver object.

### -param DeviceInit [in]


A pointer to a framework-allocated <a href="/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure.

### -param FdoAttributes [out]


Pointer to a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that describes the attributes of the client driver’s device object when it’s created.

## -returns

Returns STATUS_SUCCESS if function succeeds. Returns STATUS_INVALID_PARAMETER if corresponding client driver can't be found. Otherwise, it returns one of the error status values defined in Ntstatus.h.

## -syntax

```cpp
FORCEINLINE NTSTATUS  HwNProcessAddDevicePreDeviceCreate(
  _In_  WDFDRIVER               Driver,
  _In_  PWDFDEVICE_INIT         DeviceInit,
  _Out_ PWDF_OBJECT_ATTRIBUTES  FdoAttributes
);
```

## -see-also

<a href="/windows-hardware/drivers/gpiobtn/hardware-notifications-support">Hardware notifications support</a>



<a href="/windows-hardware/drivers/ddi/_gpio">Hardware notifications reference</a>
