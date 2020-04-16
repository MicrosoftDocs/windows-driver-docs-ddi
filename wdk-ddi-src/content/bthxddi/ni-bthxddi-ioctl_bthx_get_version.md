---
UID: NI:bthxddi.IOCTL_BTHX_GET_VERSION
title: IOCTL_BTHX_GET_VERSION (bthxddi.h)
description: Profile drivers use IOCTL_BTHX_GET_VERSION to get the version supported by the transport driver.
old-location: bltooth\ioctl_bthx_get_version.htm
tech.root: bltooth
ms.assetid: F4FD760B-551C-4738-A13D-444E08215D59
ms.date: 04/27/2018
keywords: ["IOCTL_BTHX_GET_VERSION IOCTL"]
ms.keywords: IOCTL_BTHX_GET_VERSION, IOCTL_BTHX_GET_VERSION control, IOCTL_BTHX_GET_VERSION control code [Bluetooth Devices], bltooth.ioctl_bthx_get_version, bthxddi/IOCTL_BTHX_GET_VERSION
f1_keywords:
 - "bthxddi/IOCTL_BTHX_GET_VERSION"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- BthXDDI.h
api_name:
- IOCTL_BTHX_GET_VERSION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_BTHX_GET_VERSION IOCTL


## -description



Profile drivers use IOCTL_BTHX_GET_VERSION to get the version supported by the transport driver.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

Profile drivers should use KMDF and its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveoutputmemory">WdfRequestRetrieveOutputMemory</a> method to retrieve output parameters.  For example, to get the output buffer:

<code>Status = WdfRequestRetrieveOutputMemory(_Request, &ReqOutMemory);</code>

The buffer describes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthxddi/ns-bthxddi-_bthx_version">BTHX_VERSION</a> structure. 

Refer to the WDK Bluetooth samples for more information.


### -output-buffer-length

The length of the buffer is the size of the <b>BTHX_VERSION</b> structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The 
      <b>Information</b> member of the STATUS_BLOCK structure is set to the size, in bytes, of the buffer that holds the BTHX_VERSION structure.

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



IOCTL_BTHX_GET_VERSION is a synchronous operation.

A transport driver can return one or more versions that it supports in BTHX_VERSION structure.  If no version is set,  Windows unloads the Bluetooth stack.



