---
UID: NF:storport.StorPortEtwLogError
title: StorPortEtwLogError function
author: windows-driver-content
description: A miniport can call StorPortEtwLogError to log an Event Tracing for Windows (ETW) event for a device hardware error.
tech.root: storage
ms.assetid: 02e3820a-c2f3-45bf-87a9-09d00ab8193e
ms.author: windowsdriverdev
ms.date: 03-05-2019
ms.topic: function
f1_keywords:
 - "storport/StorPortEtwLogError"
ms.keywords: StorPortEtwLogError
req.header: storport.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
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
topic_type: 
- apiref
api_type: 
- 
api_location:
- storport.h
api_name: 
- StorPortEtwLogError
product: Windows
targetos: Windows

ms.custom: 19H1
---

# StorPortEtwLogError function

## -description

A miniport can call **StorPortEtwLogError** to log an Event Tracing for Windows (ETW) event for a device hardware error.

## -parameters

### -param HwDeviceExtension

Pointer to the hardware device extension for the host bus adapter (HBA).

### -param Address

The storage unit device address. This parameter is NULL for adapter devices.

### -param Id

A miniport-defined identifier for the ETW event.

### -param Description

The description text for the error. This parameter is required.

### -param DataBufferLength

Size of *DataBuffer*, in bytes.

### -param DataBuffer

A variable-size buffer that contains driver-specific binary data that is useful in identifying the cause of the error. Drivers must specify the size of this buffer in the *DataBufferLength* parameter.

## -returns

This function returns one of the following status codes.

<table>
<tr>
  <th>Return Code</th>   <th>Description</th>
</tr>
<tr>
  <td>STOR_STATUS_INVALID_PARAMETER</td>
  <td><i>Description</i> or <i>DataBuffer</i> are NULL, or <i>DataBufferLength</i> is not greater than zero.</td>
</tr>
<tr>
  <td>STOR_STATUS_SUCCESS</td>
  <td>This function completed successfully.</td>
</tr>
<tr>
  <td>STOR_STATUS_UNSUCCESSFUL</td>
  <td>StorPort was unable to log the ETW event for other reasons, such as ETW logging is not enabled.</td>
</tr></table>

## -remarks

Events generated from this function are published to the "Microsoft-Windows-Storage-Storport/Operational" ETW channel.

## -see-also

[StorPortEtwEvent2](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportetwevent2)

[StorPortEtwEvent4](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportetwevent4)

[StorPortEtwEvent8](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportetwevent8)
