---
UID: NF:storport.StorPortUpdateAdapterMaxIO
title: StorPortUpdateAdapterMaxIO function (storport.h)
description: This function can be called by a miniport to update the maximum IO's supported by an adapter. This function is valid during HwInitialize/HwPassiveInitRoutine callback and has effect only during adapter initialization.
old-location: storage\storportupdateadaptermaxio.htm
tech.root: storage
ms.assetid: BB18925D-ACFA-426D-ADD3-33C1D8A99396
ms.date: 03/29/2018
keywords: ["StorPortUpdateAdapterMaxIO function"]
ms.keywords: StorPortUpdateAdapterMaxIO, StorPortUpdateAdapterMaxIO function [Storage Devices], storage.storportupdateadaptermaxio, storport/StorPortUpdateAdapterMaxIO
req.header: storport.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortUpdateAdapterMaxIO
 - storport/StorPortUpdateAdapterMaxIO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Storport.h
api_name:
 - StorPortUpdateAdapterMaxIO
---

# StorPortUpdateAdapterMaxIO function


## -description

This function can be called by a miniport to update the maximum IO's supported by
    an adapter. This function is valid during HwInitialize/HwPassiveInitRoutine
    callback and has effect only during adapter initialization.

## -parameters

### -param HwDeviceExtension

A pointer to miniport's device extension.

### -param MaxIoCount

Maximum IO's supported by the adapter.

## -returns

This function returns of the following values.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>STOR_STATUS_SUCCESS</td>
<td>The telemetry event was successfully logged.</td>
</tr>
<tr>
<td>STOR_STATUS_NOT_IMPLEMENTED</td>
<td>The function is called on the OS that does not support it.</td>
</tr>
<tr>
<td>STOR_STATUS_INVALID_PARAMETER</td>
<td>There is an invalid parameter.</td>
</tr>
<tr>
<td>STOR_STATUS_INVALID_DEVICE_REQUEST</td>
<td>The function was called outside of <b>HwInitialize</b>/<b>HwPassiveInitRoutine</b>. </td>
</tr>
</table>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_hw_initialization_data">HwInitialize</a>

