---
UID: NC:hwnclx.HWN_CLIENT_SET_STATE
title: HWN_CLIENT_SET_STATE (hwnclx.h)
description: Implemented by the client driver to set hardware notification component state. It is invoked when a user wants to change the state of a driver.
old-location: gpiobtn\hwn_client_set_state.htm
tech.root: gpiobtn
ms.date: 02/15/2018
keywords: ["HWN_CLIENT_SET_STATE callback"]
ms.keywords: "*PHWN_CLIENT_SET_STATE, *PHWN_CLIENT_SET_STATE callback function pointer, HWN_CLIENT_SET_STATE, HwnClientSetState, HwnClientSetState callback function, gpiobtn.hwn_client_set_state, hwnclx/HwnClientSetState"
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
 - HWN_CLIENT_SET_STATE
 - hwnclx/HWN_CLIENT_SET_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Hwnclx.h
api_name:
 - HWN_CLIENT_SET_STATE
---

# HWN_CLIENT_SET_STATE callback


## -description

Implemented by the client driver to set hardware notification component state. It is invoked when a user wants to change the state of a driver.

## -parameters

### -param Context [in]


Pointer to the client driver's context information. This memory space is available for use by the client driver. It is allocated as part of the framework object context space by <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. For more information, see <a href="/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_CLIENT_REGISTRATION_PACKET</a> and  <a href="/windows-hardware/drivers/wdf/framework-object-context-space">Framework Object Context Space</a>.

### -param Buffer [in]


Buffer of <i>BufferLength</i> bytes containing a <a href="/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_HEADER</a> structure including one or more <a href="/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_SETTINGS</a> structures that specify the hardware notifications to be set.

### -param BufferLength [in]


The size of <i>Buffer</i> in bytes.

### -param BytesWritten [out]


Pointer to a variable that indicates the number of bytes written by the function.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.

## -prototype

```cpp
HWN_CLIENT_SET_STATE HwnClientSetState;

NTSTATUS HwnClientSetState(
  _In_  PVOID  Context,
  _In_  PVOID  Buffer,
  _In_  ULONG  BufferLength,
  _Out_ PULONG BytesWritten
)
{ ... }

typedef HWN_CLIENT_SET_STATE *PHWN_CLIENT_SET_STATE;
```

## -remarks

Register your implementation of this callback function by setting the appropriate member of <a href="/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_CLIENT_REGISTRATION_PACKET</a> and then calling <a href="..\hwnclx\nf-hwnclx-hwnregisterclient.md">HwNRegisterClient</a>.

## -see-also

<a href="/windows-hardware/drivers/gpiobtn/hardware-notifications-support">Hardware notifications support</a>



<a href="/windows-hardware/drivers/ddi/_gpio">Hardware notifications reference</a>

