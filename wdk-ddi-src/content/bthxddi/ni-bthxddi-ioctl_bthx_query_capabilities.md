---
UID: NI:bthxddi.IOCTL_BTHX_QUERY_CAPABILITIES
title: IOCTL_BTHX_QUERY_CAPABILITIES
author: windows-driver-content
description: IOCTL_BTHX_QUERY_CAPABILITIES is used to query the capabilities of the transport driver.
old-location: bltooth\ioctl_bthx_query_capabilities.htm
old-project: bltooth
ms.assetid: 199C93EC-AB91-47F1-914A-F44BFF1796A6
ms.author: windowsdriverdev
ms.date: 4/27/2018
ms.keywords: IOCTL_BTHX_QUERY_CAPABILITIES, IOCTL_BTHX_QUERY_CAPABILITIES control, IOCTL_BTHX_QUERY_CAPABILITIES control code [Bluetooth Devices], bltooth.ioctl_bthx_query_capabilities, bthxddi/IOCTL_BTHX_QUERY_CAPABILITIES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	BthXDDI.h
api_name:
-	IOCTL_BTHX_QUERY_CAPABILITIES
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_BTHX_QUERY_CAPABILITIES IOCTL


## -description



IOCTL_BTHX_QUERY_CAPABILITIES is used to query the capabilities of the transport driver.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a buffer that holds a <a href="https://msdn.microsoft.com/library/windows/hardware/hh450833">BTHX_CAPABILITIES</a> structure. 


### -output-buffer-length

The length of the buffer is the size of the <b>BTHX_CAPABILITIES</b> structure.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The 
      <b>Information</b> member of the STATUS_BLOCK structure is set to the size of the structure.

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
 


## -remarks



During startup, the Bluetooth stack sends IOCTL_BTHX_QUERY_CAPABILITIES to query the capabilities of the transport driver.

This is a synchrononous call and failure of this IOCTL prevents Windows from loading the Bluetooth stack.

The output buffer of this IOCTL is defined by the BTHX_CAPABILITIES structure.

The <b>MaxScoChannels</b> member must be set to 1. The <b>ScoSupport</b> member must be set to <b>ScoSupportHCIBypass</b>. Failure to do so prevents the stack from being loaded.



