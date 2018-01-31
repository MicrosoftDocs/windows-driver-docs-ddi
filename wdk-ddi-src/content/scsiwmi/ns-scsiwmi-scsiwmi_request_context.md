---
UID: NS:scsiwmi.SCSIWMI_REQUEST_CONTEXT
title: SCSIWMI_REQUEST_CONTEXT
author: windows-driver-content
description: A SCSIWMI_REQUEST_CONTEXT structure contains context information for a WMI SRB.
old-location: storage\scsiwmi_request_context.htm
old-project: storage
ms.assetid: 524150d8-d4a7-4b61-89c4-0074c938559b
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.scsiwmi_request_context, structs-scsibus_3323f388-8dc7-4723-bc2c-7822ed622ccd.xml, *PSCSIWMI_REQUEST_CONTEXT, SCSIWMI_REQUEST_CONTEXT, PSCSIWMI_REQUEST_CONTEXT structure pointer [Storage Devices], PSCSIWMI_REQUEST_CONTEXT, scsiwmi/SCSIWMI_REQUEST_CONTEXT, SCSIWMI_REQUEST_CONTEXT structure [Storage Devices], scsiwmi/PSCSIWMI_REQUEST_CONTEXT
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	scsiwmi.h
apiname:
-	SCSIWMI_REQUEST_CONTEXT
product: Windows
targetos: Windows
req.typenames: "*PSCSIWMI_REQUEST_CONTEXT, SCSIWMI_REQUEST_CONTEXT"
req.product: Windows 10 or later.
---

# SCSIWMI_REQUEST_CONTEXT structure


## -description


A SCSIWMI_REQUEST_CONTEXT structure contains context information for a WMI SRB. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
typedef struct {
  PVOID  UserContext;
  ULONG  BufferSize;
  PUCHAR Buffer;
  UCHAR  MinorFunction;
  UCHAR  ReturnStatus;
  ULONG  ReturnSize;
} SCSIWMI_REQUEST_CONTEXT, *PSCSIWMI_REQUEST_CONTEXT;
````


## -struct-fields




#### - UserContext

Points to a miniport driver buffer that contains any data the miniport driver requires to process the SRB. This can be a pointer to  the miniport driver's HW_DEVICE_EXTENSION structure or some other buffer.


#### - BufferSize

Reserved for system use and not available for use by miniport drivers.


#### - Buffer



#### 



#### 



#### - MinorFunction

Reserved for system use and not available for use by miniport drivers.


#### - ReturnStatus

Indicates the return status of the SRB. This member is not valid until after the miniport driver has called <a href="..\scsiwmi\nf-scsiwmi-scsiportwmipostprocess.md">ScsiPortWmiPostProcess</a> to update the request context.


#### - ReturnSize

Indicates the number of bytes of data transferred for the SRB. This member is not valid until after the miniport driver has called <a href="..\scsiwmi\nf-scsiwmi-scsiportwmipostprocess.md">ScsiPortWmiPostProcess</a> to update the request context.


## -remarks


When the miniport driver receives an SRB in which the <b>Function</b> member is set to SRB_FUNCTION_WMI, it calls <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a> with request parameters, including a pointer to a request context. <b>ScsiPortWmiDispatchFunction</b> passes the request context to the miniport driver's appropriate <b>HwScsiWmi</b><b><i>Xxx</i></b> routine.

When the miniport driver is done processing the SRB and prior to completing the SRB, the miniport driver should call <a href="..\scsiwmi\nf-scsiwmi-scsiportwmipostprocess.md">ScsiPortWmiPostProcess</a> to update the <b>ReturnStatus</b> and <b>ReturnSize</b> members of the request context. The miniport driver updates the SRB's data transfer length and status to these values by calling <a href="..\scsiwmi\nf-scsiwmi-scsiportwmigetreturnsize.md">ScsiPortWmiGetReturnSize</a> and <a href="..\scsiwmi\nf-scsiwmi-scsiportwmigetreturnstatus.md">ScsiPortWmiGetReturnStatus</a>. respectively.

A request context must remain valid throughout the processing of an SRB. If the SRB can pend, the miniport driver must allocate the SCSIWMI_REQUEST_CONTEXT structure from the SRB extension so it remains valid until the SRB completes. For nonpending SRBs the structure can be allocated from a stack frame that does not go out of scope.



## -see-also

<a href="..\scsiwmi\nf-scsiwmi-scsiportwmigetreturnsize.md">ScsiPortWmiGetReturnSize</a>

<a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a>

<a href="..\scsiwmi\nf-scsiwmi-scsiportwmigetreturnstatus.md">ScsiPortWmiGetReturnStatus</a>

<a href="..\scsiwmi\nf-scsiwmi-scsiportwmipostprocess.md">ScsiPortWmiPostProcess</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SCSIWMI_REQUEST_CONTEXT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

