---
UID: NC:hwnclx.HWN_CLIENT_GET_STATE
title: HWN_CLIENT_GET_STATE (hwnclx.h)
description: Implemented by the client driver to get hardware notification component state. It is invoked when a user requests status information.
old-location: gpiobtn\hwn_client_get_state.htm
tech.root: gpiobtn
ms.date: 02/15/2018
keywords: ["HWN_CLIENT_GET_STATE callback"]
ms.keywords: "*PHWN_CLIENT_GET_STATE, *PHWN_CLIENT_GET_STATE callback function pointer, HWN_CLIENT_GET_STATE, HwnClientGetState, HwnClientGetState callback function, gpiobtn.hwn_client_get_state, hwnclx/HwnClientGetState"
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
 - HWN_CLIENT_GET_STATE
 - hwnclx/HWN_CLIENT_GET_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Hwnclx.h
api_name:
 - HWN_CLIENT_GET_STATE
---

# HWN_CLIENT_GET_STATE callback


## -description

Implemented by the client driver to get hardware notification component state. It is invoked when a user requests status information.

## -parameters

### -param Context [in]


Pointer to the client driver's context information. This memory space is available for use by the client driver. It is allocated as part of the framework object context space by <b>WdfDeviceCreate</b>. For more information, see <a href="/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_CLIENT_REGISTRATION_PACKET</a> and  <a href="/windows-hardware/drivers/wdf/framework-object-context-space">Framework Object Context Space</a>.

### -param OutputBuffer [out]


Buffer of <i>OutputBufferLength</i> bytes for writing hardware notification status. If the function succeeds, the buffer will contain a <a href="/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_HEADER</a> structure including one or more <a href="/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_SETTINGS</a> structures.

<div class="alert"><b>Note</b>  <p class="note"><b>OutputBufferLength</b> must be large enough to contain all of the requested settings. For more information, see Remarks.

</div>
<div> </div>

### -param OutputBufferLength [in]


The size of <i>OutputBuffer</i> in bytes.

### -param InputBuffer [in]


Buffer of <i>InputBufferLength</i> bytes containing a <a href="/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_HEADER</a> holding one or more <a href="/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_SETTINGS</a> structures where the IDs for the requested hardware notification components are stored in the <b>HwNId</b> field. This buffer can be NULL.

### -param InputBufferLength [in]


The size of <i>InputBuffer</i> in bytes.

### -param BytesRead [out]


Pointer to a variable that indicates the number of bytes read by the function.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.

## -prototype

```cpp
HWN_CLIENT_GET_STATE HwnClientGetState;

NTSTATUS HwnClientGetState(
  _In_  PVOID  Context,
  _Out_ PVOID  OutputBuffer,
  _In_  ULONG  OutputBufferLength,
  _In_  PVOID  InputBuffer,
  _In_  ULONG  InputBufferLength,
  _Out_ PULONG BytesRead
)
{ ... }

typedef HWN_CLIENT_GET_STATE *PHWN_CLIENT_GET_STATE;
```

## -remarks

Register your implementation of this callback function by setting the appropriate member of <a href="/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_CLIENT_REGISTRATION_PACKET</a> and then calling <a href="..\hwnclx\nf-hwnclx-hwnregisterclient.md">HwNRegisterClient</a>.

<ul>
<li>
If <i>InputBuffer</i> is NULL, the output buffer will be used to store a <a href="/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_HEADER</a> structure that contains all of the settings for the hardware notifications implemented by the driver.

The Settings for a hardware notification component are stored in a <a href="/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_SETTINGS</a> structure. The <b>HwNSettingsInfo</b> field of the <a href="/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_HEADER</a> structure contains an array of <b>HWN_SETTINGS</b> structures.

</li>
<li>
If <i>InputBuffer</i> is not null and is correctly formatted, it will contain a <a href="/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_HEADER</a> with one or more <a href="/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_SETTINGS</a> structures. The IDs for the requested hardware notification components are stored in the <b>HwNId</b> field of the <b>HWN_SETTINGS</b> structure. The remaining settings should be valid settings or zero.

</li>
<li>
If <i>OutputBuffer</i> is not large enough to contain all of the settings requested, this function should not write anything to <i>OutputBuffer</i>. Additionally, it should set <i>BytesRead</i> to 0 and return an error.

</li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/gpiobtn/hardware-notifications-support">Hardware notifications support</a>



<a href="/windows-hardware/drivers/ddi/_gpio">Hardware notifications reference</a>

