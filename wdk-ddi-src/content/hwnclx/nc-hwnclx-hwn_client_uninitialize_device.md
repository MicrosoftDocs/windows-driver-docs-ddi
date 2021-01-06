---
UID: NC:hwnclx.HWN_CLIENT_UNINITIALIZE_DEVICE
title: HWN_CLIENT_UNINITIALIZE_DEVICE (hwnclx.h)
description: Implemented by the client driver and invoked as invoked as a result of a call to EVT_WDF_DEVICE_RELEASE_HARDWARE. This callback function uninitializes the hardware notification component.
old-location: gpiobtn\hwn_client_uninitialize_device.htm
tech.root: gpiobtn
ms.date: 02/15/2018
keywords: ["HWN_CLIENT_UNINITIALIZE_DEVICE callback"]
ms.keywords: "*PHWN_CLIENT_UNINITIALIZE_DEVICE, *PHWN_CLIENT_UNINITIALIZE_DEVICE callback function pointer, HWN_CLIENT_UNINITIALIZE_DEVICE, HwnClientUninitializeDevice, HwnClientUninitializeDevice callback function, gpiobtn.hwn_client_uninitialize_device, hwnclx/HwnClientUninitializeDevice"
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: HPMI_QUERY_CAPABILITIES_RESPONSE, *PHPMI_QUERY_CAPABILITIES_RESPONSE
f1_keywords:
 - HWN_CLIENT_UNINITIALIZE_DEVICE
 - hwnclx/HWN_CLIENT_UNINITIALIZE_DEVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Hwnclx.h
api_name:
 - PHWN_CLIENT_UNINITIALIZE_DEVICE
---

# HWN_CLIENT_UNINITIALIZE_DEVICE callback


## -description

Implemented by the client driver and invoked as  invoked as a result of a call to <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EVT_WDF_DEVICE_RELEASE_HARDWARE</a>. This callback function uninitializes the hardware notification component.

## -parameters

### -param Device 

[in]
Handle to the client drivers framework device object.

### -param Context 

[in]
Pointer to the client driver's context information. This memory space is available for use by the client driver. It is allocated as part of the framework object context space by <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. For more information, see <a href="/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_CLIENT_REGISTRATION_PACKET</a> and  <a href="/windows-hardware/drivers/wdf/framework-object-context-space">Framework Object Context Space</a>.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.

## -prototype

```cpp
HWN_CLIENT_UNINITIALIZE_DEVICE HwnClientUninitializeDevice;

NTSTATUS HwnClientUninitializeDevice(
  _In_ WDFDEVICE Device,
  _In_ PVOID     Context
)
{ ... }

typedef HWN_CLIENT_UNINITIALIZE_DEVICE *PHWN_CLIENT_UNINITIALIZE_DEVICE;
```

## -remarks

Register your implementation of this callback function by setting the appropriate member of <a href="/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_CLIENT_REGISTRATION_PACKET</a> and then calling <a href="..\hwnclx\nf-hwnclx-hwnregisterclient.md">HwNRegisterClient</a>.

## -see-also

<a href="/windows-hardware/drivers/gpiobtn/hardware-notifications-support">Hardware notifications support</a>



<a href="/windows-hardware/drivers/ddi/_gpio">Hardware notifications reference</a>
