---
UID: NF:hwnclx.HwNRegisterClient
title: HwNRegisterClient function (hwnclx.h)
description: Registers the hardware notification client driver and its callback functions with the class extension.
old-location: gpiobtn\hwnregisterclient.htm
tech.root: gpiobtn
ms.date: 02/15/2018
keywords: ["HwNRegisterClient function"]
ms.keywords: HwNRegisterClient, HwNRegisterClient function, gpiobtn.hwnregisterclient, hwnclx/HwNRegisterClient
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
 - HwNRegisterClient
 - hwnclx/HwNRegisterClient
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Mshwnclxstub.lib
 - Mshwnclxstub.dll
api_name:
 - HwNRegisterClient
---

# HwNRegisterClient function


## -description

Registers the hardware notification client driver and its callback functions with the class extension. This function should be invoked when the client driver is loaded and the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_initialize">DriverEntry</a> routine is called for initialization.

## -parameters

### -param Driver 

[in]
Handle to the client drivers framework driver object.

### -param RegistrationPacket 

[in, out]
Pointer to the <a href="/windows-hardware/drivers/gpiobtn/create-a-hardware-notification-client-driver">HWN_CLIENT_REGISTRATION_PACKET</a> structure that contains function pointers to the callback functions defined in the client driver implementation and required by the class extension.

### -param RegistryPath 

[in]
Pointer to a <a href="/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the path to the client driver’s registry key.

## -returns

Returns STATUS_SUCCESS if function succeeds. Returns STATUS_INVALID_PARAMETER if corresponding client driver can't be found. Otherwise, it returns one of the error status values defined in Ntstatus.h.

## -syntax

```cpp
FORCEINLINE NTSTATUS  HwNRegisterClient(
  _In_    WDFDRIVER                        Driver,
  _Inout_ PHWN_CLIENT_REGISTRATION_PACKET  RegistrationPacket,
  _In_    PUNICODE_STRING                  RegistryPath
);
```

## -see-also

<a href="/windows-hardware/drivers/gpiobtn/hardware-notifications-support">Hardware notifications support</a>



<a href="/windows-hardware/drivers/ddi/_gpio">Hardware notifications reference</a>
