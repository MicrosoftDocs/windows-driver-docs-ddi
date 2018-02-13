---
UID: NF:storport.StorPortGetOriginalMdl
title: StorPortGetOriginalMdl function
author: windows-driver-content
description: The StorPortGetOriginalMdl routine returns the MDL associated with the given SRB.
old-location: storage\storportgetoriginalmdl.htm
old-project: storage
ms.assetid: 48042e9d-ed83-4326-931d-ded753deb1a7
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortGetOriginalMdl routine [Storage Devices], storport/StorPortGetOriginalMdl, storprt_4617200d-18b4-4ee2-aa43-92fc5f3a7b66.xml, StorPortGetOriginalMdl, storage.storportgetoriginalmdl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	storport.h
apiname:
-	StorPortGetOriginalMdl
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortGetOriginalMdl function


## -description


The <b>StorPortGetOriginalMdl</b> routine returns the MDL associated with the given SRB.


## -syntax


````
ULONG StorPortGetOriginalMdl(
  _In_  PVOID               HwDeviceExtension,
  _In_  PSCSI_REQUEST_BLOCK Srb,
  _Out_ PVOID               *Mdl
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Srb [in]

A pointer to a <a href="..\srb\ns-srb-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a> structure.


### -param Mdl [out]

A pointer to receive the MDL.


## -returns



StorPortGetOriginalMdl returns one of the following status codes:

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
Indicates that the MDL was obtained successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The pointer in <i>Mdl</i> receiving the SRB's MDL  is <b>NULL</b>.

</td>
</tr>
</table>
 




## -remarks



Starting in Windows 8, the <i>Srb</i> parameter may point to either <a href="..\srb\ns-srb-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a> or <a href="..\srb\ns-srb-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a>. If the function identifier in the <b>Function</b> field of <i>Srb</i> is <b>SRB_FUNCTION_STORAGE_REQUEST_BLOCK</b>, the SRB is a <b>STORAGE_REQUEST_BLOCK</b> request structure.




## -see-also

<a href="..\storport\nf-storport-storportgetsystemaddress.md">StorPortGetSystemAddress</a>



<a href="..\srb\ns-srb-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a>



<a href="..\srb\ns-srb-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortGetOriginalMdl routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

