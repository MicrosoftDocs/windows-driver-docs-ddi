---
UID: NF:wdm.NtPowerInformation
title: NtPowerInformation function (wdm.h)
description: Learn how the ZwPowerInformation routine (wdm.h) sets or retrieves system power information.
old-location: kernel\zwpowerinformation.htm
tech.root: kernel
ms.date: 07/30/2021
keywords: ["NtPowerInformation function"]
ms.keywords: NtPowerInformation, PlatformInformation, ZwPowerInformation, ZwPowerInformation routine [Kernel-Mode Driver Architecture], kernel.zwpowerinformation, wdm/NtPowerInformation, wdm/ZwPowerInformation
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntpoapi.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntoskrnl.lib
req.dll: Ntoskrnl.lib
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NtPowerInformation
 - wdm/NtPowerInformation
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Ntoskrnl.lib
api_name:
 - NtPowerInformation
---

# NtPowerInformation function (wdm.h)

## -description

The **ZwPowerInformation** routine sets or retrieves system power information.

## -parameters

### -param InformationLevel

[in] Specifies the requested information level, which indicates the specific power information to be set or retrieved. Currently, the only supported *POWER_INFORMATION_LEVEL* value is **PlatformInformation**.

| Value | Description |
|--|--|
| **PlatformInformation** | Information represents the currently supported power capabilities of the system. Information may change as drivers are installed. For example, the installation of legacy device drivers that do not support power management might modify the capabilities of the system. |

### -param InputBuffer

[in, optional] Pointer to a caller-allocated input buffer. This parameter must be **NULL**, otherwise **ERROR_INVALID_PARAMETER** is returned.

### -param InputBufferLength

[in] Size, in bytes, of the buffer at *InputBuffer*. The parameter must be set to zero.

### -param OutputBuffer

[out, optional] A pointer to an output buffer. The data type of this buffer depends on the information level requested in the *InformationLevel* parameter. For the **PlatformInformation** level, the only currently supported value, the *OutputBuffer* parameter is required and should be of the [POWER_PLATFORM_INFORMATION](./ns-wdm-_power_platform_information.md) type.

### -param OutputBufferLength

[in] Size, in bytes, of the output buffer. Depending on the information level requested, the buffer may be variably sized. *PlatformInformation*, the only currently supported value, requires a buffer that is the size of a [POWER_PLATFORM_INFORMATION](./ns-wdm-_power_platform_information.md) structure.

## -returns

Returns STATUS_SUCCESS if the call is successful. If the call fails, possible error codes include the following:

| Return code | Description |
|--|--|
| **STATUS_BUFFER_TOO_SMALL** | The output buffer is of insufficient size to contain the data being returned. |
| **STATUS_INVALID_PARAMETER** | The **PlatformInformation** information level, which is the only currently supported value, requires no input buffer and must contain an output buffer. The caller either supplied an input buffer or no output buffer. |
| **STATUS_ACCESS_DENIED** | The caller had insufficient access rights to perform the requested action. |

## -remarks

[NtPowerInformation]() and **ZwPowerInformation** are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

### Examples

This example illustrates a valid function call.

```cpp
POWER_PLATFORM_INFORMATION PlatformInfo = {0};
NTSTATUS Result = NtPowerInformation(PlatformInformation, NULL, 0, &PlatformInfo, sizeof(PlatformInfo));
```

## -see-also

[POWER_PLATFORM_INFORMATION](./ns-wdm-_power_platform_information.md)

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)
