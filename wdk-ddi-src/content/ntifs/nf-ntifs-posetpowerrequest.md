---
UID: NF:ntifs.PoSetPowerRequest
title: PoSetPowerRequest function (ntifs.h)
description: Learn more about the PoSetPowerRequest function.
tech.root: kernel
ms.date: 09/27/2023
keywords: ["PoSetPowerRequest function"]
ms.keywords: PoSetPowerRequest, PoSetPowerRequest routine [Kernel-Mode Driver Architecture], kernel.posetpowerrequest, portn_8f3abb03-a324-4841-b630-b62344d656ce.xml, wdm/PoSetPowerRequest
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 7
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PoSetPowerRequest
 - ntifs/PoSetPowerRequest
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PoSetPowerRequest
---

# PoSetPowerRequest function (ntifs.h)

## -description

The **PoSetPowerRequest** routine increments the count for the specified power request type.

## -parameters

### -param PowerRequest [in, out]

A pointer to a power request object that was created by the [**PoCreatePowerRequest**](nf-ntifs-pocreatepowerrequest.md) routine.

### -param Type [in]

The type of power request. Set this parameter to the following [**POWER_REQUEST_TYPE**](../wdm/ne-wdm-_power_request_type.md) enumeration value:

* **PowerRequestSystemRequired**

## -returns

**PoSetPowerRequest** returns STATUS_SUCCESS if the call is successful. If the call fails, possible error return codes include the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_NOT_SUPPORTED | The **Type** parameter is set to an unsupported value. |

## -remarks

A driver can call the **PoSetPowerRequest** routine to request that the [power manager](/windows-hardware/drivers/kernel/power-manager) override several types of default power behavior, which are specified as [**POWER_REQUEST_TYPE**](../wdm/ne-wdm-_power_request_type.md) enumeration values. To restore the default behavior, the driver cancels the request by calling the [**PoClearPowerRequest**](nf-ntifs-poclearpowerrequest.md) routine.

The power manager maintains a count of the active requests for each power request type. The **PoSetPowerRequest** routine increments the count for the specified power request type by one. The **PoClearPowerRequest** routine decrements the count by one. A nonzero count indicates that requests from one or more components are active. After the count decrements to zero, the computer reverts to the default behavior for the specified power request type.

## -see-also

[**POWER_REQUEST_TYPE**](../wdm/ne-wdm-_power_request_type.md)

[**PoClearPowerRequest**](nf-ntifs-poclearpowerrequest.md)

[**PoCreatePowerRequest**](nf-ntifs-pocreatepowerrequest.md)
