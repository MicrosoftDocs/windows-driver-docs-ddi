---
UID: NF:storport.StorPortGetLogicalProcessorRelationship
title: StorPortGetLogicalProcessorRelationship function (storport.h)
description: The StorPortGetLogicalProcessorRelationship routine returns relationship information for one or more specified types.
old-location: storage\storportgetlogicalprocessorrelationship.htm
tech.root: storage
ms.date: 02/17/2022
keywords: ["StorPortGetLogicalProcessorRelationship function"]
ms.keywords: StorPortGetLogicalProcessorRelationship, StorPortGetLogicalProcessorRelationship routine [Storage Devices], storage.storportgetlogicalprocessorrelationship, storport/StorPortGetLogicalProcessorRelationship, storprt_65b00469-41a4-446b-aaa5-fee877aaff3c.xml
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Windows 7
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
 - StorPortGetLogicalProcessorRelationship
 - storport/StorPortGetLogicalProcessorRelationship
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortGetLogicalProcessorRelationship
---

# StorPortGetLogicalProcessorRelationship function

## -description

The **StorPortGetLogicalProcessorRelationship** routine gets information about the relationships of one or more processors to the other processors in a multiprocessor system. See [**KeQueryLogicalProcessorRelationship**](../wdm/nf-wdm-kequerylogicalprocessorrelationship.md) for additional details.

## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).

### -param ProcessorNumber [in, optional]

An optional pointer to a [processor number](../miniport/ns-miniport-_processor_number.md) for which relationships are to be returned. To request information about all logical processors in the system, set this parameter to NULL.

### -param RelationshipType [in]

Indicates the type of relationship to be returned. See [**KeQueryLogicalProcessorRelationship**](../wdm/nf-wdm-kequerylogicalprocessorrelationship.md) for details.

### -param Information [out]

A pointer to a caller-allocated buffer that receives an array of one or more [**SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX**](/windows/win32/api/winnt/ns-winnt-system_logical_processor_information_ex) structures that contain the information requested by the caller. If the function fails, the contents of this buffer are undefined. Set **Information** to NULL to obtain the required buffer length before you allocate the buffer. See [**KeQueryLogicalProcessorRelationship**](../wdm/nf-wdm-kequerylogicalprocessorrelationship.md) for additional details.

### -param Length [in, out]

A pointer to the size of the information buffer, in bytes. On entry, **Length** contains the size of the caller-allocated buffer that **Information** points to. On return, this value receives the number of bytes that are populated with relationship information.

## -returns

The **StorPortGetLogicalProcessorRelationship**routine returns STOR_STATUS_SUCCESS if the call is successful. Possible error return values include the following.

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_BUFFER_TOO_SMALL  | The supplied buffer is not large enough to hold the requested information. |
| STOR_STATUS_INVALID_PARAMETER | One or more of the parameters are invalid; for example, **ProcessNumber** points to invalid information. |
| STOR_STATUS_NOT_IMPLEMENTED   | This function is not implemented on the active operating system. |

## -remarks

 The information that is returned includes processor affinity masks that are composed of the logical processors in the host system. These logical processors share the specified relationship types.

See [**KeQueryLogicalProcessorRelationship**](../wdm/nf-wdm-kequerylogicalprocessorrelationship.md) for additional details.
