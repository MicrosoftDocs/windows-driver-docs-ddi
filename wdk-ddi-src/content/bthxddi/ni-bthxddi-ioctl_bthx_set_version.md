---
UID: NI:bthxddi.IOCTL_BTHX_SET_VERSION
title: IOCTL_BTHX_SET_VERSION (bthxddi.h)
description: IOCTL_BTHX_SET_VERSION is used to inform the transport driver of the version of the extensibility interface being used.
old-location: bltooth\ioctl_bthx_set_version.htm
tech.root: bltooth
ms.assetid: FE572606-8F47-4C40-BF74-24D5F667D2EC
ms.date: 04/27/2018
keywords: ["IOCTL_BTHX_SET_VERSION IOCTL"]
ms.keywords: IOCTL_BTHX_SET_VERSION, IOCTL_BTHX_SET_VERSION control, IOCTL_BTHX_SET_VERSION control code [Bluetooth Devices], bltooth.ioctl_bthx_set_version, bthxddi/IOCTL_BTHX_SET_VERSION
req.header: bthxddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
req.irql: <= PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_BTHX_SET_VERSION
 - bthxddi/IOCTL_BTHX_SET_VERSION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - BthXDDI.h
api_name:
 - IOCTL_BTHX_SET_VERSION
---

# IOCTL_BTHX_SET_VERSION IOCTL


## -description

IOCTL_BTHX_SET_VERSION is used to inform the transport driver of the version of the extensibility interface being used.

## -ioctlparameters

### -input-buffer

Profile drivers should use KMDF and its <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveinputmemory">WdfRequestRetrieveInputMemory</a> method to retrieve input parameters.  For example, to get the input buffer:

<code>Status = WdfRequestRetrieveInputMemory(_Request, &ReqInMemory);</code>

The buffer describes a <a href="/windows-hardware/drivers/ddi/bthxddi/ns-bthxddi-_bthx_version">BTHX_VERSION</a> structure. 

Refer to the WDK Bluetooth samples for more information.

### -input-buffer-length

The length of the buffer is the size of the <b>BTHX_VERSION</b> structure.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The 
      <b>Information</b> member of the STATUS_BLOCK structure is set to zero because the Bluetooth driver
      stack returns no data with this IOCTL.

The 
      <b>Status</b> member is set to one of the values in the following table.

<table>
<tr>
<th>Status value</th>
<th>Description</th>
</tr>
<tr>
<td>
STATUS_SUCCESS

</td>
<td>
The IOCTL completed successfully.

</td>
</tr>
</table>
 

Any unsuccessful NT status code prevents the driver from loading.

## -remarks

IOCTL_BTHX_SET_VERSION is a synchronous operation.

Only one version will be selected and set.