---
UID: NF:storport.StorPortGetCurrentIrql
tech.root: storage
title: StorPortGetCurrentIrql
ms.date: 05/13/2021
targetos: Windows
description: StorPortGetCurrentIrql retrieves the current interrupt request level (IRQL).
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt:
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortGetCurrentIrql
f1_keywords:
 - StorPortGetCurrentIrql
 - storport/StorPortGetCurrentIrql
dev_langs:
 - c++
---

## -description

**StorPortGetCurrentIrql** retrieves the current interrupt request level (IRQL).

## -parameters

### -param HwDeviceExtension [in]

A pointer to the miniport's device extension.

### -param Irql [out]

Pointer to a KIRQL structure in which the current IRQL will be stored. **Irql** cannot be NULL.

## -returns

This function returns one of the following status codes.

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_SUCCESS | The IRQL was successfully retrieved. |
| STOR_STATUS_INVALID_PARAMETER | **Irql** is a null pointer. |
| STOR_STATUS_UNSUCCESSFUL | Returned for other internal system reasons. |

## -remarks

A miniport can call **StorPortGetCurrentIrql** to query the current IRQL. KIRQL is defined in *miniport.h*. For general information about IRQLs, see [Managing Hardware Priorities](/windows-hardware/drivers/kernel/managing-hardware-priorities).

## -see-also
