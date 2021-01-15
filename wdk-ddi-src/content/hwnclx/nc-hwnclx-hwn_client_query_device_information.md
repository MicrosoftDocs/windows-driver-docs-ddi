---
UID: NC:hwnclx.HWN_CLIENT_QUERY_DEVICE_INFORMATION
title: HWN_CLIENT_QUERY_DEVICE_INFORMATION (hwnclx.h)
description: Implemented by the client driver to retrieve hardware notification component attributes.
old-location: gpiobtn\hwn_client_query_device_information.htm
tech.root: gpiobtn
ms.date: 02/15/2018
keywords: ["HWN_CLIENT_QUERY_DEVICE_INFORMATION callback"]
ms.keywords: HWN_CLIENT_QUERY_DEVICE_INFORMATION, HwnClientQueryDeviceInformation, HwnClientQueryDeviceInformation callback function, PHWN_CLIENT_QUERY_DEVICE_INFORMATION, PHWN_CLIENT_QUERY_DEVICE_INFORMATION callback function pointer, gpiobtn.hwn_client_query_device_information, hwnclx/HwnClientQueryDeviceInformation
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
 - HWN_CLIENT_QUERY_DEVICE_INFORMATION
 - hwnclx/HWN_CLIENT_QUERY_DEVICE_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Hwnclx.h
api_name:
 - HWN_CLIENT_QUERY_DEVICE_INFORMATION
---

# HWN_CLIENT_QUERY_DEVICE_INFORMATION callback


## -description

Implemented by the client driver to retrieve hardware notification component attributes.

## -parameters

### -param Context 

[in]
Pointer to the client driver's context information. This memory space is available for use by the client driver. It is allocated as part of the framework object context space by <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. For more information, see <a href="/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_CLIENT_REGISTRATION_PACKET</a> and <a href="/windows-hardware/drivers/wdf/framework-object-context-space">Framework Object Context Space</a>.

### -param Information 

[out]
Pointer to a buffer that receives the controller’s attributes.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.

## -prototype

```cpp
HWN_CLIENT_QUERY_DEVICE_INFORMATION HwnClientQueryDeviceInformation;

NTSTATUS HwnClientQueryDeviceInformation(
  _In_  PVOID                      Context,
  _Out_ PCLIENT_DEVICE_INFORMATION Information
)
{ ... }

typedef HWN_CLIENT_QUERY_DEVICE_INFORMATION PHWN_CLIENT_QUERY_DEVICE_INFORMATION;
```

## -remarks

Register your implementation of this callback function by setting the appropriate member of <a href="/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_CLIENT_REGISTRATION_PACKET</a> and then calling <a href="..\hwnclx\nf-hwnclx-hwnregisterclient.md">HwNRegisterClient</a>.

## -see-also

<a href="/windows-hardware/drivers/gpiobtn/hardware-notifications-support">Hardware notifications support</a>



<a href="/windows-hardware/drivers/ddi/_gpio">Hardware notifications reference</a>

