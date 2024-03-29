---
UID: NF:hwnclx.HwNProcessAddDevicePostDeviceCreate
title: HwNProcessAddDevicePostDeviceCreate function (hwnclx.h)
description: Creates I/O queues. It should be called after the client driver’s EVT_WDF_DRIVER_DEVICE_ADD callback function is invoked and the device object has been created.
old-location: gpiobtn\hwnprocessadddevicepostdevicecreate.htm
tech.root: gpiobtn
ms.date: 02/15/2018
keywords: ["HwNProcessAddDevicePostDeviceCreate function"]
ms.keywords: HwNProcessAddDevicePostDeviceCreate, HwNProcessAddDevicePostDeviceCreate function, gpiobtn.hwnprocessadddevicepostdevicecreate, hwnclx/HwNProcessAddDevicePostDeviceCreate
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
 - HwNProcessAddDevicePostDeviceCreate
 - hwnclx/HwNProcessAddDevicePostDeviceCreate
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Mshwnclxstub.lib
 - Mshwnclxstub.dll
api_name:
 - HwNProcessAddDevicePostDeviceCreate
---

# HwNProcessAddDevicePostDeviceCreate function


## -description

             Creates I/O queues. It should be called after the client driver’s <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EVT_WDF_DRIVER_DEVICE_ADD</a> callback function is invoked and the device object has been created.

## -parameters

### -param Driver [in]


Handle to the client drivers framework driver object.

### -param Device [in]


Handle to the framework device object.

### -param DeviceGuid [in]


Pointer to the GUID for the client driver. Valid values are defined in Hwn.h, which ships with Window SDK.

## -returns

Returns STATUS_SUCCESS if function succeeds. Returns STATUS_INVALID_PARAMETER if corresponding client driver can't be found. Otherwise, it returns one of the error status values defined in Ntstatus.h.

## -syntax

```cpp
FORCEINLINE NTSTATUS  HwNProcessAddDevicePostDeviceCreate(
  _In_ WDFDRIVER  Driver,
  _In_ WDFDEVICE  Device,
  _In_ LPGUID     DeviceGuid
);
```

## -see-also

<a href="/windows-hardware/drivers/gpiobtn/hardware-notifications-support">Hardware notifications support</a>



<a href="/windows-hardware/drivers/ddi/_gpio">Hardware notifications reference</a>
