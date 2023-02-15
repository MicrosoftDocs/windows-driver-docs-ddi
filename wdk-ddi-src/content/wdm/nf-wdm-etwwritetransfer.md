---
UID: NF:wdm.EtwWriteTransfer
title: EtwWriteTransfer function (wdm.h)
description: The EtwWriteTransfer function marks an event that links two activities together; this type of event is referred to as a transfer event.
tech.root: devtest
ms.date: 02/15/2023
keywords: ["EtwWriteTransfer function"]
ms.keywords: EtwWriteTransfer, EtwWriteTransfer function [Driver Development Tools], devtest.etwwritetransfer, etw_km_210cf13d-0f54-4a51-b8f2-7d37b22d8eac.xml, wdm/EtwWriteTransfer
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt:
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
req.dll: NtosKrnl.exe; Ntdll.dll
req.irql: Any level (see Comments section)
targetos: Windows
req.typenames: 
f1_keywords:
 - EtwWriteTransfer
 - wdm/EtwWriteTransfer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
 - Ntdll.dll
api_name:
 - EtwWriteTransfer
---

## -description

The **EtwWriteTransfer** function marks an event that links two activities together; this type of event is referred to as a *transfer event*. A transfer event can contain the same user-defined data, the same fields, and is subject to the same rules as other events.

## -parameters

### -param RegHandle [in]

A pointer to the event provider registration handle, which is returned by the **EtwRegister** function if the event provider registration is successful.

### -param EventDescriptor [in]

A pointer to the EVENT_DESCRIPTOR structure.

### -param ActivityId [in, optional]

The identifier that indicates the activity associated with the event. The *ActivityId* provides a way to group related events and is used in end-to-end tracing. This identifier is optional and can be **NULL**.

### -param RelatedActivityId [in, optional]

The identifier that indicates related activity associated with the event. The *RelatedActivityID* provides a way to group related events and is used in end-to-end tracing.

### -param UserDataCount [in]

The number of elements in an array of EVENT_DATA_DESCRIPTOR structures.

### -param UserData [in, optional]

The pointer to the first element in an array of EVENT_DATA_DESCRIPTOR structures.

## -returns

**EtwWriteTransfer** returns STATUS_SUCCESS if the event was successfully published.

## -remarks

You can call **EtwWriteTransfer** at any IRQL. However, when IRQL is greater than APC_LEVEL, any data passed to the **EtwWrite**, **EtwWriteString**, **EtwWriteTransfer** functions must not be pageable. That is, any kernel-mode routine that is running at IRQL greater than APC_LEVEL cannot access pageable memory. Data passed to the **EtwWrite**, **EtwWriteString**, **EtwWriteTransfer** functions must reside in system-space memory, regardless of what the IRQL is.

## -see-also

[EtwWrite](/windows-hardware/drivers/ddi/wdm/nf-wdm-etwwrite)

[EtwWriteString](/windows-hardware/drivers/ddi/wdm/nf-wdm-etwwritestring)
