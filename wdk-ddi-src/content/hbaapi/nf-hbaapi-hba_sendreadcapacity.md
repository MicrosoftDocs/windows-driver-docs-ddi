---
UID: NF:hbaapi.HBA_SendReadCapacity
title: HBA_SendReadCapacity function
author: windows-driver-content
description: The HBA_SendReadCapacity routine sends a SCSI read capacity command to the indicated remote port.
old-location: storage\hba_sendreadcapacity.htm
old-project: storage
ms.assetid: 642a085f-03d4-438a-8584-c1f420161e94
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: HBA_SendReadCapacity
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HBA_SendReadCapacity
req.alt-loc: Hbaapi.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
req.typenames: HBA_WWNTYPE
---

# HBA_SendReadCapacity function



## -description
The <b>HBA_SendReadCapacity</b> routine sends a SCSI read capacity command to the indicated remote port. 



## -syntax

````
HBA_STATUS HBA_API HBA_SendReadCapacity(
  _In_  HBA_HANDLE handle,
  _In_  HBA_WWN    portWWN,
  _In_  HBA_UINT64 fcLUN,
  _Out_ void       *pRspBuffer,
  _In_  HBA_UINT32 RspBufferSize,
  _Out_ void       *pSenseBuffer,
  _In_  HBA_UINT32 SenseBufferSize
);
````


## -parameters

### -param handle [in]

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA through which the SCSI read capacity command is sent.


### -param portWWN [in]

Contains a 64-bit worldwide name (WWN) that uniquely identifies the remote target port to which the SCSI read capacity command is sent. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification. 


### -param fcLUN [in]

Indicates the fibre channel logical unit number of the logical unit to which the SCSI read capacity command will be sent. 


### -param pRspBuffer [out]

Pointer to a buffer that receives the output data of the SCSI read capacity command.


### -param RspBufferSize [in]

Indicates the size, in bytes, of the buffer at <i>pRspBuffer</i>.


### -param pSenseBuffer [out]

Pointer to a buffer that receives the SCSI sense data.


### -param SenseBufferSize [in]

On input, indicates on input the size, in bytes, of the buffer at <i>pSenseBuffer</i>. On output, this member indicates the number of bytes of sense data returned. 


## -returns
The <b>HBA_ScsiReadCapacity</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_ScsiReadCapacity</b> returns one of the following values.
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>Returned if the complete payload of a reply to the SCSI read capacity command was successfully retrieved. 
<dl>
<dt><b>HBA_STATUS_ERROR_ILLEGAL_WWN</b></dt>
</dl>Returned if the HBA referenced by <i>handle</i> does not contain a port with a name that matches <i>HbaPortWWN</i>. 
<dl>
<dt><b>HBA_STATUS_ERROR_NOT_A_TARGET</b></dt>
</dl>Returned if the specified remote port specified by <i>portWWN </i>does not have SCSI target functionality.
<dl>
<dt><b>HBA_STATUS_ERROR_TARGET_BUSY</b></dt>
</dl>Returned if the SCSI read capacity command could not be delivered without causing a SCSI overlapped command condition.
<dl>
<dt><b>HBA_STATUS_SCSI_CHECK_CONDITION</b></dt>
</dl>Returned if a SCSI check condition occurred and SCSI send data is provided in the buffer at <i>pSenseBuffer</i>.
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>Returned if an unspecified error occurred that prevented the execution of the SCSI inquiry command. 

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_SendReadCapacity routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

