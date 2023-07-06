---
UID: NF:ntifs.PoClearPowerRequest
title: PoClearPowerRequest function (ntifs.h)
description: Learn more about the PoClearPowerRequest routine.
tech.root: kernel
ms.date: 07/06/2023
keywords: ["PoClearPowerRequest function"]
ms.keywords: PoClearPowerRequest, PoClearPowerRequest routine [Kernel-Mode Driver Architecture], kernel.poclearpowerrequest, portn_683a4a08-b6e3-4d6c-adfa-00d075db06f9.xml, wdm/PoClearPowerRequest
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
 - PoClearPowerRequest
 - ntifs/PoClearPowerRequest
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PoClearPowerRequest
---

# PoClearPowerRequest function (ntifs.h)

## -description

The **PoClearPowerRequest** routine decrements the count for the specified power request type.

## -parameters

### -param PowerRequest [in, out]

A pointer to a power request object that was created by the [**PoCreatePowerRequest**](nf-ntifs-pocreatepowerrequest.md) routine.

### -param Type [in]

The type of the power request. Set this parameter to the following [**POWER_REQUEST_TYPE**](../wdm/ne-wdm-_power_request_type.md) enumeration value:

* **PowerRequestSystemRequired**

## -returns

**PoClearPowerRequest** returns STATUS_SUCCESS if the call is successful. If the call fails, possible error return codes include the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_NOT_SUPPORTED | The parameter **Type** is set to an unsupported value. |

## -remarks

A driver can call the [**PoSetPowerRequest**](nf-ntifs-posetpowerrequest.md) routine to request that the [power manager](/windows-hardware/drivers/kernel/power-manager) override several types of default power behavior, which are specified as [**POWER_REQUEST_TYPE**](../wdm/ne-wdm-_power_request_type.md) enumeration values. To restore the default behavior, the driver cancels the request by calling the **PoClearPowerRequest** routine.

The power manager maintains a count of the active requests for each power request type. The **PoSetPowerRequest** routine increments the count for the specified power request type by one. The **PoClearPowerRequest** routine decrements the count by one. A nonzero count indicates that requests from one or more components are active. After the count decrements to zero, the power manager restores the default behavior for the specified power request type.

## -see-also

[**POWER_REQUEST_TYPE**](../wdm/ne-wdm-_power_request_type.md)

[**PoCreatePowerRequest**](nf-ntifs-pocreatepowerrequest.md)

[**PoSetPowerRequest**](nf-ntifs-posetpowerrequest.md)
