---
UID: NS:scsiwmi.__unnamed_struct_0
title: SCSIWMI_REQUEST_CONTEXT (scsiwmi.h)
description: A SCSIWMI_REQUEST_CONTEXT structure contains context information for a WMI SRB.
old-location: storage\scsiwmi_request_context.htm
tech.root: storage
ms.assetid: 524150d8-d4a7-4b61-89c4-0074c938559b
ms.date: 03/29/2018
ms.keywords: "*PSCSIWMI_REQUEST_CONTEXT, PSCSIWMI_REQUEST_CONTEXT, PSCSIWMI_REQUEST_CONTEXT structure pointer [Storage Devices], SCSIWMI_REQUEST_CONTEXT, SCSIWMI_REQUEST_CONTEXT structure [Storage Devices], scsiwmi/PSCSIWMI_REQUEST_CONTEXT, scsiwmi/SCSIWMI_REQUEST_CONTEXT, storage.scsiwmi_request_context, structs-scsibus_3323f388-8dc7-4723-bc2c-7822ed622ccd.xml"
ms.topic: struct
req.header: scsiwmi.h
req.include-header: Scsiwmi.h
req.target-type: Windows
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	scsiwmi.h
api_name:
-	SCSIWMI_REQUEST_CONTEXT
product:
- Windows
targetos: Windows
req.typenames: SCSIWMI_REQUEST_CONTEXT, *PSCSIWMI_REQUEST_CONTEXT
---

# SCSIWMI_REQUEST_CONTEXT structure


## -description


A SCSIWMI_REQUEST_CONTEXT structure contains context information for a WMI SRB. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields




### -field UserContext

Points to a miniport driver buffer that contains any data the miniport driver requires to process the SRB. This can be a pointer to  the miniport driver's HW_DEVICE_EXTENSION structure or some other buffer.


### -field BufferSize

Reserved for system use and not available for use by miniport drivers.


### -field Buffer



###### 



###### 


### -field MinorFunction

Reserved for system use and not available for use by miniport drivers.


### -field ReturnStatus

Indicates the return status of the SRB. This member is not valid until after the miniport driver has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff564796">ScsiPortWmiPostProcess</a> to update the request context.


### -field ReturnSize

Indicates the number of bytes of data transferred for the SRB. This member is not valid until after the miniport driver has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff564796">ScsiPortWmiPostProcess</a> to update the request context.


## -remarks



When the miniport driver receives an SRB in which the <b>Function</b> member is set to SRB_FUNCTION_WMI, it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff564766">ScsiPortWmiDispatchFunction</a> with request parameters, including a pointer to a request context. <b>ScsiPortWmiDispatchFunction</b> passes the request context to the miniport driver's appropriate <b>HwScsiWmi</b><b><i>Xxx</i></b> routine.

When the miniport driver is done processing the SRB and prior to completing the SRB, the miniport driver should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff564796">ScsiPortWmiPostProcess</a> to update the <b>ReturnStatus</b> and <b>ReturnSize</b> members of the request context. The miniport driver updates the SRB's data transfer length and status to these values by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff564789">ScsiPortWmiGetReturnSize</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff564791">ScsiPortWmiGetReturnStatus</a>. respectively.

A request context must remain valid throughout the processing of an SRB. If the SRB can pend, the miniport driver must allocate the SCSIWMI_REQUEST_CONTEXT structure from the SRB extension so it remains valid until the SRB completes. For nonpending SRBs the structure can be allocated from a stack frame that does not go out of scope.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564766">ScsiPortWmiDispatchFunction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564789">ScsiPortWmiGetReturnSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564791">ScsiPortWmiGetReturnStatus</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564796">ScsiPortWmiPostProcess</a>
 

 

