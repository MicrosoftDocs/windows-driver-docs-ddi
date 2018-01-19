---
UID: NF:storport.StorPortGetDataInBufferScatterGatherList
title: StorPortGetDataInBufferScatterGatherList function
author: windows-driver-content
description: Returns the scatter-gather list associated with the input data buffer of a SCSI request block (SRB).
old-location: storage\storportgetdatainbufferscattergatherlist.htm
old-project: storage
ms.assetid: 015592AE-4AF6-48C8-BF79-6B22A6FCAB98
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortGetDataInBufferScatterGatherList
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
req.alt-api: StorPortGetDataInBufferScatterGatherList
req.alt-loc: Storport.lib,Storport.dll
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
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortGetDataInBufferScatterGatherList function



## -description
Returns the scatter-gather list associated with the input data buffer  of a SCSI request block (SRB).



## -syntax

````
ULONG StorPortGetDataInBufferScatterGatherList(
  _In_  PVOID                     HwDeviceExtension,
  _In_  PSCSI_REQUEST_BLOCK       Srb,
  _Out_ PSTOR_SCATTER_GATHER_LIST *SgList
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param Srb [in]

The request block to containing the input data buffer for the scatter-gather list.


### -param SgList [out]

A pointer to  an scatter-gather list structure address to receive the scatter-gather list for the input data buffer in <i>Srb</i>.


## -returns
A status value indicating the result of the notification. This can be one of these values:
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>The scatter-gather list for <i>Srb</i> was successfully returned.
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>The pointer value in <i>SgList</i> is NULL.

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\storport\nf-storport-storportgetdatainbuffermdl.md">StorPortGetDataInBufferMdl</a>
</dt>
<dt>
<a href="..\storport\nf-storport-storportgetdatainbuffersystemaddress.md">StorPortGetDataInBufferSystemAddress</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortGetDataInBufferScatterGatherList routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

