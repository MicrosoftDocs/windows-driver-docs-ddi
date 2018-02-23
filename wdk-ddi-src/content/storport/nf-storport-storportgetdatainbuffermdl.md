---
UID: NF:storport.StorPortGetDataInBufferMdl
title: StorPortGetDataInBufferMdl function
author: windows-driver-content
description: Returns an MDL associated with the input data buffer of a SCSI request block (SRB).
old-location: storage\storportgetdatainbuffermdl.htm
old-project: storage
ms.assetid: 9D41810A-7698-4462-802D-79EF793C9A9D
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.storportgetdatainbuffermdl, StorPortGetDataInBufferMdl routine [Storage Devices], StorPortGetDataInBufferMdl, storport/StorPortGetDataInBufferMdl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: Storport.lib
req.dll: 
req.irql: Any
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Storport.lib
-	Storport.dll
apiname:
-	StorPortGetDataInBufferMdl
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortGetDataInBufferMdl function


## -description


Returns an MDL associated with the input data buffer  of a SCSI request block (SRB).


## -syntax


````
ULONG StorPortGetDataInBufferMdl(
  _In_  PVOID               HwDeviceExtension,
  _In_  PSCSI_REQUEST_BLOCK Srb,
  _Out_ PVOID               *Mdl
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Srb [in]

The request block to containing the data described by the MDL pointed to by <i>Mdl</i>.


### -param Mdl [out]

A pointer to  an MDL address to receive the MDL for <i>Srb</i>.


## -returns



A status value indicating the result of the notification. This can be one of these values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The MDL for <i>Srb</i> was successfully returned.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The pointer value in <i>Mdl</i> is NULL.

</td>
</tr>
</table>
 




## -see-also

<a href="..\storport\nf-storport-storportgetdatainbuffersystemaddress.md">StorPortGetDataInBufferSystemAddress</a>



<a href="..\storport\nf-storport-storportgetdatainbufferscattergatherlist.md">StorPortGetDataInBufferScatterGatherList</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortGetDataInBufferMdl routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

