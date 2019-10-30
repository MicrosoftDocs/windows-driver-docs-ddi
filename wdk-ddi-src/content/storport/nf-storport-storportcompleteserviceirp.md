---
UID: NF:storport.StorPortCompleteServiceIrp
title: StorPortCompleteServiceIrp function (storport.h)
description: The StorPortCompleteServiceIrp routine is called by a Storport virtual miniport driver when it needs to complete a request that it received in its HwStorProcessServiceRequest callback routine.
old-location: storage\storportcompleteserviceirp.htm
tech.root: storage
ms.assetid: 359b1096-f987-4884-ab67-2290bf5196b5
ms.date: 03/29/2018
ms.keywords: StorPortCompleteServiceIrp, StorPortCompleteServiceIrp routine [Storage Devices], storage.storportcompleteserviceirp, storport/StorPortCompleteServiceIrp, storprt_439990ea-8133-4114-b417-1c88e53cce14.xml
ms.topic: function
f1_keywords:
 - "storport/StorPortCompleteServiceIrp"
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- storport.h
api_name:
- StorPortCompleteServiceIrp
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortCompleteServiceIrp function


## -description


The <b>StorPortCompleteServiceIrp</b> routine is called by a Storport virtual miniport driver when it needs to complete a request that it received in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_process_service_request">HwStorProcessServiceRequest</a> callback routine.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the  mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitialize">StorPortInitialize</a>. The port driver frees this memory when it removes the device. 


### -param Irp [in]

A pointer to the I/O request.


## -returns



<b>StorPortCompleteServiceIrp</b> returns one of the following values:

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
Indicates that the routine completed the request successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The Irp that was passed was <b>NULL</b>.

</td>
</tr>
</table>
 




## -remarks



The Storport virtual miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_process_service_request">HwStorProcessServiceRequest</a> callback routine receives an IRP that is produced by an IOCTL when a caller, such as a user-mode application or kernel-mode driver, requires a reverse callback operation. The I/O is completed by the miniport driver by calling the <b>StorPortCompleteServiceIrp</b> routine when it needs to tell the caller of something or needs the caller to do something.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_process_service_request">HwStorProcessServiceRequest</a>
 

 

