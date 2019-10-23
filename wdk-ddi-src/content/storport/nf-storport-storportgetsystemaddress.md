---
UID: NF:storport.StorPortGetSystemAddress
title: StorPortGetSystemAddress function (storport.h)
description: The StorPortGetSystemAddress routine returns a virtual address in system space for the data buffer of the specified SCSI request block (SRB).
old-location: storage\storportgetsystemaddress.htm
tech.root: storage
ms.assetid: 28bb26bd-7259-4664-8092-6b9a917c1a91
ms.date: 03/29/2018
ms.keywords: StorPortGetSystemAddress, StorPortGetSystemAddress routine [Storage Devices], storage.storportgetsystemaddress, storport/StorPortGetSystemAddress, storprt_6e6713c8-a235-43b8-a325-2d4b8fca8f35.xml
ms.topic: function
f1_keywords:
 - "storport/StorPortGetSystemAddress"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows Server 2003 with SP2.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- storport.h
api_name:
- StorPortGetSystemAddress
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortGetSystemAddress function


## -description


The <b>StorPortGetSystemAddress</b> routine returns a virtual address in system space for the data buffer of the specified SCSI request block (SRB).


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Srb [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a> structure.


### -param SystemAddress [out]

A pointer to receive the virtual address of the data buffer.


## -returns



StorPortGetSystemAddress returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
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
Indicates that the system address was obtained successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
This status code is caused by one of the following conditions:
       

The SRB does not have an associated data buffer.

The pointer to receive the virtual address is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>
</td>
<td width="60%">
The call was made at an invalid IRQL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The attempt to map the data buffer to system space failed.

</td>
</tr>
</table>
 




## -remarks



Starting in Windows 8, the <i>Srb</i> parameter may point to either <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_storage_request_block">STORAGE_REQUEST_BLOCK</a>. If the function identifier in the <b>Function</b> field of <i>Srb</i> is <b>SRB_FUNCTION_STORAGE_REQUEST_BLOCK</b>, the SRB is a <b>STORAGE_REQUEST_BLOCK</b> request structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_scsi_request_block">SCSI_REQUEST_BLOCK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/srb/ns-srb-_storage_request_block">STORAGE_REQUEST_BLOCK</a>
 

 

