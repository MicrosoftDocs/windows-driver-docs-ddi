---
UID: NF:ntifs.PoCreatePowerRequest
title: PoCreatePowerRequest function (ntifs.h)
description: Learn more about the PoCreatePowerRequest routine.
tech.root: kernel
ms.date: 07/06/2023
keywords: ["PoCreatePowerRequest function"]
ms.keywords: PoCreatePowerRequest, PoCreatePowerRequest routine [Kernel-Mode Driver Architecture], kernel.pocreatepowerrequest, portn_059f00e2-74ea-4c61-8fcd-6b257c084161.xml, wdm/PoCreatePowerRequest
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PoCreatePowerRequest
 - ntifs/PoCreatePowerRequest
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PoCreatePowerRequest
---

# PoCreatePowerRequest function (ntifs.h)

## -description

The **PoCreatePowerRequest** routine creates a power request object.

## -parameters

### -param PowerRequest [out]

A pointer to a location into which the routine writes a pointer to the newly created power request object. If the call fails, the routine writes NULL to this location.

### -param DeviceObject [in]

A pointer to the device object of the caller (a [**DEVICE_OBJECT**](../wdm/ns-wdm-_device_object.md) structure).

### -param Context [in]

A pointer to a [**COUNTED_REASON_CONTEXT**](../wdm/ns-wdm-_counted_reason_context.md) structure that describes why the caller is creating the power request object. This parameter is optional and can be set to NULL.

## -returns

**PoCreatePowerRequest** returns STATUS_SUCCESS if the call is successful. If the call fails, possible error return codes include the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_INVALID_PARAMETER | The **DeviceObject** parameter is NULL. |
| STATUS_INSUFFICIENT_RESOURCES | There is not enough memory available to create a power request object. |

## -remarks

This routine creates a power request object. To enable power requests, the caller should create one power request object and use that object for all calls to the [**PoSetPowerRequest**](nf-ntifs-posetpowerrequest.md) and [**PoClearPowerRequest**](nf-ntifs-poclearpowerrequest.md) routines.

A driver can use power requests to override certain aspects of the computer's default power behavior. For example, a driver for a TV receiver device can use power requests to prevent the [power manager](/windows-hardware/drivers/kernel/power-manager) from automatically blanking the display during extended periods of time in which no user interaction occurs.

When the power request object is no longer needed, the caller must delete the object by calling the [**PoDeletePowerRequest**](nf-ntifs-podeletepowerrequest.md) routine. The driver must delete the power request object before it deletes the device object that was used to create the power request object.

## -see-also

[**PoClearPowerRequest**](nf-ntifs-poclearpowerrequest.md)

[**PoDeletePowerRequest**](nf-ntifs-podeletepowerrequest.md)

[**PoSetPowerRequest**](nf-ntifs-posetpowerrequest.md)
