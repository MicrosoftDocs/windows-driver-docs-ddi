---
UID: NF:storport.StorPortQueryConfiguration
title: StorPortQueryConfiguration function
author: windows-driver-content
description: A miniport can call StorPortQueryConfiguration to get the specific configuration of the platform. 
tech.root: storage
ms.assetid: f5f37d7a-4171-4273-9076-32d7cce1c508
ms.author: windowsdriverdev
ms.date: 03/06/2019
ms.topic: function
f1_keywords:
 - "storport/StorPortQueryConfiguration"
ms.keywords: StorPortQueryConfiguration
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
- StorPortQueryConfiguration
product: Windows
targetos: Windows

ms.custom: 19H1
---

# StorPortQueryConfiguration function

## -description

A miniport can call **StorPortQueryConfiguration** to query for the specific configuration of the platform.

## -parameters

### -param HwDeviceExtension

Pointer to the hardware device extension for the host bus adapter (HBA).

### -param Type

A [STORPORT_QUERY_CONFIGURATION_TYPE](ne-storport-_storport_query_configuration_type.md) enum value that indicates the type of configuration to query.

### -param Enabled

Pointer to a **BOOLEAN** value in which the Storport driver will return one of the following values.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>TRUE</b></dt>
</dl>
</td>
<td width="60%">
The configuration specified by <i>Type</i> is enabled.
</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>FALSE</b></dt>
</dl>
</td>
<td width="60%">
The configuration specified by <i>Type</i> is not enabled.
</td>
</tr>
</table>

## -returns

**StorPortQueryConfiguration** returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
*Enabled* is NULL or the value specified in *Type* is invalid.
</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This function is not implemented on the active operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The query completed successfully.

</td>
</tr>
</table>

## -remarks

## -see-also

[STORPORT_QUERY_CONFIGURATION_TYPE](ne-storport-_storport_query_configuration_type.md)
