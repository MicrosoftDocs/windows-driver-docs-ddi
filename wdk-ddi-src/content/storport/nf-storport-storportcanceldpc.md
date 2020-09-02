---
UID: NF:storport.StorPortCancelDpc
title: StorPortCancelDpc function
author: windows-driver-content
description: StorPortCancelDpc attempts to cancel the execution of a StorPort deferred procedure call (DPC).
tech.root: storage
ms.assetid: e40dd10a-adae-480c-a820-6a9b0b3b776e
ms.author: windowsdriverdev
ms.date: 03/19/2019
keywords: ["StorPortCancelDpc function"]
ms.keywords: StorPortCancelDpc
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
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - StorPortCancelDpc
 - storport/StorPortCancelDpc
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - storport.h
api_name:
 - StorPortCancelDpc
dev_langs:
 - c++
---

# StorPortCancelDpc function


## -description

**StorPortCancelDpc** attempts to cancel the execution of a StorPort deferred procedure call (DPC).

## -parameters

### -param HwDeviceExtension

Pointer to the hardware device extension for the host bus adapter (HBA).

### -param Dpc

Pointer to the [STOR_DPC](https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_stor_dpc) DPC object to be cancelled.

### -param ReturnValue

Pointer to a **BOOLEAN** in which this function will return one of the following values.

<table>
<tr>
  <th>Return Value</th>   <th>Description</th>
</tr>
<tr>
  <td>TRUE</td>
  <td>The specified <i>Dpc</i> was successfully removed from the system's DPC queue.</td>
</tr>
<tr>
  <td>FALSE</td>
  <td>The specified <i>Dpc</i> was not removed from the system's DPC queue.</td>
</tr>
</table>

## -returns

This function returns one of the following status codes.
<table>
<tr>
  <th>Return Code</th>   <th>Description</th>
</tr>
<tr>
  <td>STOR_STATUS_INVALID_PARAMETER</td>
  <td><i>Dpc</i> or <i>ReturnValue</i> are NULL.</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt>STOR_STATUS_NOT_IMPLEMENTED</dt>
</dl>
</td>
<td width="60%">
This function is not implemented on the active operating system.
</td>
</tr>

<tr>
<td>STOR_STATUS_SUCCESS</td>
<td>This function completed successfully. Use the value returned in <i>ReturnValue</i> to determine whether the Dpc was removed from the queue.</td>
</tr>
</table>

## -remarks

If the specified StorPort DPC is in the DPC queue, **StorPortCancelDpc** removes it from the queue, canceling a call to the associated DPC routine. If it is not in the queue, it was either executing or had finished executing, and therefore could not be removed.

This routine is implemented using inline function definitions, so that miniport drivers that use it do not have to link to libraries that are dependent on the version of the operating system. Miniport drivers can use this routine without sacrificing backward compatibility with versions of the operating system that do not support DPCs in storage miniport drivers.

## -see-also

[STOR_DPC](https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_stor_dpc)

[StorPortInitializeDpc](https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitializedpc)

[StorPortIssueDpc](https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportissuedpc)

