---
UID: NF:storport.StorPortGetCurrentProcessorNumber
title: StorPortGetCurrentProcessorNumber function (storport.h)
description: Learn more about the StorPortGetCurrentProcessorNumber function.
tech.root: storage
ms.date: 07/26/2024
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Windows 7
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: StorPortIrql
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortGetCurrentProcessorNumber
 - storport/StorPortGetCurrentProcessorNumber
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortGetCurrentProcessorNumber
---

# StorPortGetCurrentProcessorNumber function

## -description

The **StorPortGetCurrentProcessorNumber** routine retrieves the current processor number from the kernel.

## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).

### -param ProcNumber [out]

Pointer to a [**PROCESSOR_NUMBER**](../miniport/ns-miniport-_processor_number.md) structure that holds the return data.

## -returns

The **StorPortGetCurrentProcessorNumber** routine returns one of the following status codes:

| Return code | Description |
| ----------- | ----------- |
| **STOR_STATUS_NOT_IMPLEMENTED** | This function is not implemented on the active operating system.                                 |
| **STOR_STATUS_SUCCESS**         | The operation was successful.                                                                   |
| **STOR_STATUS_INVALID_PARAMETER** | The operation fails with this return value if one or more of the parameters are invalid, for example, if **ProcNumber** is set to **NULL**. |

## -see-also

[**PROCESSOR_NUMBER**](../miniport/ns-miniport-_processor_number.md)

[**StorPortGetProcessorCount**](nf-storport-storportgetprocessorcount.md)
