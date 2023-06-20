---
UID: NF:wdm.EtwSetInformation
tech.root: kernel
title: EtwSetInformation
ms.date: 05/25/2023
targetos: Windows
description: The EtwSetInformation provides special-purpose information to modify a kernel-mode ETW provider registration.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: NtosKrnl.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Available in Windows 10 and later versions of Windows.
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - wdm.h
api_name:
 - EtwSetInformation
f1_keywords:
 - EtwSetInformation
 - wdm/EtwSetInformation
dev_langs:
 - c++
helpviewer_keywords:
 - EtwSetInformation
---

## -description

The **EtwSetInformation** provides special-purpose information to modify a kernel-mode ETW provider registration. The **EtwSetInformation** function is the kernel-mode equivalent of the [**EventSetInformation**](/windows/win32/api/evntprov/nf-evntprov-eventsetinformation) function.

## -parameters

### -param RegHandle [in]

The registration handle of the ETW provider to modify. The registration handle is returned by [**EtwRegister**](nf-wdm-etwregister.md).

### -param InformationClass [in]

The type ([**EVENT_INFO_CLASS**](/windows/win32/api/evntprov/ne-evntprov-event_info_class)) of operation to perform on the registration object.

### -param EventInformation [in, optional]

The input buffer.

### -param InformationLength [in]

Size of the input buffer.

## -returns

If the function succeeds, the return value is STATUS_SUCCESS.

| Return code | Description |
|--|--|
| STATUS_INVALID_HANDLE | This error is returned if the *RegHandle* parameter is not a valid registration handle. |
| STATUS_INVALID_PARAMETER | One or more of the parameters is not valid. |
| STATUS_INVALID_DEVICE_REQUEST | The request is not supported. |

## -remarks

## -see-also

[**EventSetInformation**](/windows/win32/api/evntprov/nf-evntprov-eventsetinformation)

[**EVENT_INFO_CLASS**](/windows/win32/api/evntprov/ne-evntprov-event_info_class)
