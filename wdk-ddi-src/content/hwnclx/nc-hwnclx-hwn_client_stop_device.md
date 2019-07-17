---
UID: NC:hwnclx.HWN_CLIENT_STOP_DEVICE
title: HWN_CLIENT_STOP_DEVICE (hwnclx.h)
description: Implemented by the client driver TO start the hardware notification component. It is invoked as a result of a call to EVT_WDF_DEVICE_D0_EXIT.
old-location: gpiobtn\hwn_client_stop_device.htm
tech.root: gpiobtn
ms.assetid: e481afe8-659a-406d-9574-ffa048ea3c45
ms.date: 02/15/2018
ms.keywords: "*PHWN_CLIENT_STOP_DEVICE, *PHWN_CLIENT_STOP_DEVICE callback function pointer, HWN_CLIENT_STOP_DEVICE, HwnClientStopDevice, HwnClientStopDevice callback function, gpiobtn.hwn_client_stop_device, hwnclx/HwnClientStopDevice"
ms.topic: callback
f1_keywords:
 - "hwnclx/*PHWN_CLIENT_STOP_DEVICE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Hwnclx.h
api_name:
- *PHWN_CLIENT_STOP_DEVICE
product:
- Windows
targetos: Windows
req.typenames: HPMI_QUERY_CAPABILITIES_RESPONSE, *PHPMI_QUERY_CAPABILITIES_RESPONSE
---

# HWN_CLIENT_STOP_DEVICE callback


## -description



Implemented by the client driver TO start the hardware notification component. It is invoked as a result of a call to <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_exit.md">EVT_WDF_DEVICE_D0_EXIT</a>.


## -prototype


```cpp
HWN_CLIENT_STOP_DEVICE HwnClientStopDevice;

NTSTATUS HwnClientStopDevice(
  _In_ PVOID Context
)
{ ... }

typedef HWN_CLIENT_STOP_DEVICE *PHWN_CLIENT_STOP_DEVICE;
```


## -parameters




### -param Context [in]

Pointer to the client driver's context information. This memory space is available for use by the client driver. It is allocated as part of the framework object context space by <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_CLIENT_REGISTRATION_PACKET</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-context-space">Framework Object Context Space</a>.


## -returns




Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.




## -remarks



Register your implementation of this callback function by setting the appropriate member of <a href="https://docs.microsoft.com/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_CLIENT_REGISTRATION_PACKET</a> and then calling <a href="..\hwnclx\nf-hwnclx-hwnregisterclient.md">HwNRegisterClient</a>.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/gpiobtn/hardware-notifications-support">Hardware notifications support</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">Hardware notifications reference</a>



 

 


