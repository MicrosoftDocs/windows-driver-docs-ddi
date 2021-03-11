---
UID: NF:storport.StorPortEtwLogError
title: StorPortEtwLogError function
description: StorPortEtwLogError logs an Event Tracing for Windows (ETW) event for a hardware protocol error.
tech.root: storage
ms.date: 03/05/2019
keywords: ["StorPortEtwLogError function"]
ms.keywords: StorPortEtwLogError
req.header: storport.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10 version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - StorPortEtwLogError
 - storport/StorPortEtwLogError
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - storport.h
api_name:
 - StorPortEtwLogError
product:
 - Windows
dev_langs:
 - c++
---

# StorPortEtwLogError function

## -description

**StorPortEtwLogError** logs an Event Tracing for Windows (ETW) event for a hardware protocol error.

## -parameters

### -param HwDeviceExtension

[in] A pointer to the miniport's device extension.

### -param Address

[in, optional] The storage unit device address. This parameter is NULL for adapter devices.

### -param Id

[in] A miniport-defined event ID that uniquely identifies the event.

### -param Description

[in] The description text for the error. This parameter is required.

### -param DataBufferLength

[in] Size of *DataBuffer*, in bytes.

### -param DataBuffer

[in] A variable-size buffer that contains driver-specific binary data that is useful in identifying the cause of the error. Drivers must specify the size of this buffer in the *DataBufferLength* parameter.

## -returns

This function returns one of the following status codes.

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_SUCCESS | The event was successfully logged. |
| STOR_STATUS_INVALID_PARAMETER | *Description* or *DataBuffer* are NULL, or *DataBufferLength* is not greater than zero. |
| STOR_STATUS_UNSUCCESSFUL | StorPort was unable to log the ETW event for other reasons, such as ETW logging is not enabled. |

## -remarks

A miniport can call **StorPortEtwLogError** to log an ETW event for a hardware protocol error. Events generated from this function are published to the "Microsoft-Windows-Storage-Storport/Operational" ETW channel.

## -see-also

[**StorPortEtwEvent2**](./nf-storport-storportetwevent2.md)

[**StorPortEtwEvent4**](./nf-storport-storportetwevent4.md)

[**StorPortEtwEvent8**](./nf-storport-storportetwevent8.md)

[**StorPortEtwLogByteStream**](nf-storport-storportetwlogbytestream.md)
