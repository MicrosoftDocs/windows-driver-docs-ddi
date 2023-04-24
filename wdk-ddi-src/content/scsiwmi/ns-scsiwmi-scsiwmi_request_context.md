---
UID: NS:scsiwmi.SCSIWMI_REQUEST_CONTEXT
title: SCSIWMI_REQUEST_CONTEXT (scsiwmi.h)
description: A SCSIWMI_REQUEST_CONTEXT structure contains context information for a WMI SRB.
old-location: storage\scsiwmi_request_context.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["SCSIWMI_REQUEST_CONTEXT structure"]
ms.keywords: "*PSCSIWMI_REQUEST_CONTEXT, PSCSIWMI_REQUEST_CONTEXT, PSCSIWMI_REQUEST_CONTEXT structure pointer [Storage Devices], SCSIWMI_REQUEST_CONTEXT, SCSIWMI_REQUEST_CONTEXT structure [Storage Devices], scsiwmi/PSCSIWMI_REQUEST_CONTEXT, scsiwmi/SCSIWMI_REQUEST_CONTEXT, storage.scsiwmi_request_context, structs-scsibus_3323f388-8dc7-4723-bc2c-7822ed622ccd.xml"
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
targetos: Windows
req.typenames: SCSIWMI_REQUEST_CONTEXT, *PSCSIWMI_REQUEST_CONTEXT
f1_keywords:
 - PSCSIWMI_REQUEST_CONTEXT
 - scsiwmi/PSCSIWMI_REQUEST_CONTEXT
 - SCSIWMI_REQUEST_CONTEXT
 - scsiwmi/SCSIWMI_REQUEST_CONTEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - scsiwmi.h
api_name:
 - PSCSIWMI_REQUEST_CONTEXT
 - SCSIWMI_REQUEST_CONTEXT
---

# SCSIWMI_REQUEST_CONTEXT structure


## -description

A SCSIWMI_REQUEST_CONTEXT structure contains context information for a WMI SRB.

> [!NOTE]
> The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the [Storport driver](/windows-hardware/drivers/storage/storport-driver) and [Storport miniport](/windows-hardware/drivers/storage/storport-miniport-drivers) driver models.

## -struct-fields

### -field UserContext

Points to a miniport driver buffer that contains any data the miniport driver requires to process the SRB. This can be a pointer to the miniport driver's HW_DEVICE_EXTENSION structure or some other buffer.

### -field BufferSize

Reserved for system use and not available for use by miniport drivers.

### -field Buffer

Reserved for system use and not available for use by miniport drivers.

### -field MinorFunction

Reserved for system use and not available for use by miniport drivers.

### -field ReturnStatus

Indicates the return status of the SRB. This member is not valid until after the miniport driver has called [**ScsiPortWmiPostProcess**](nf-scsiwmi-scsiportwmipostprocess.md) to update the request context.

### -field ReturnSize

Indicates the number of bytes of data transferred for the SRB. This member is not valid until after the miniport driver has called [**ScsiPortWmiPostProcess**](nf-scsiwmi-scsiportwmipostprocess.md) to update the request context.

## -remarks

When the miniport driver receives an SRB in which the **Function** member is set to SRB_FUNCTION_WMI, it calls [**ScsiPortWmiDispatchFunction**](nf-scsiwmi-scsiportwmidispatchfunction.md) with request parameters, including a pointer to a request context. **ScsiPortWmiDispatchFunction** passes the request context to the miniport driver's appropriate **HwScsiWmi*****Xxx*** routine.

When the miniport driver is done processing the SRB and prior to completing the SRB, the miniport driver should call [**ScsiPortWmiPostProcess**](nf-scsiwmi-scsiportwmipostprocess.md) to update the **ReturnStatus** and **ReturnSize** members of the request context. The miniport driver updates the SRB's data transfer length and status to these values by calling [**ScsiPortWmiGetReturnSize**](nf-scsiwmi-scsiportwmigetreturnsize.md) and [**ScsiPortWmiGetReturnStatus**](nf-scsiwmi-scsiportwmigetreturnstatus.md). respectively.

A request context must remain valid throughout the processing of an SRB. If the SRB can pend, the miniport driver must allocate the SCSIWMI_REQUEST_CONTEXT structure from the SRB extension so it remains valid until the SRB completes. For nonpending SRBs the structure can be allocated from a stack frame that does not go out of scope.

## -see-also

[**ScsiPortWmiDispatchFunction**](nf-scsiwmi-scsiportwmidispatchfunction.md)

[**ScsiPortWmiGetReturnSize**](nf-scsiwmi-scsiportwmigetreturnsize.md)

[**ScsiPortWmiGetReturnStatus**](nf-scsiwmi-scsiportwmigetreturnstatus.md)

[**ScsiPortWmiPostProcess**](nf-scsiwmi-scsiportwmipostprocess.md)

