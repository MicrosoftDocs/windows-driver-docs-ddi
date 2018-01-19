---
UID: NF:hbaapi.HBA_SendSRL
title: HBA_SendSRL function
author: windows-driver-content
description: The HBA_SendSRL routine issues a scan remote loop (SRL) request through the specified HBA to a specified domain controller.
old-location: storage\hba_sendsrl.htm
old-project: storage
ms.assetid: 455ff9c9-89d5-4c79-8b01-f0d731ac8d5a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: HBA_SendSRL
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
req.alt-api: HBA_SendSRL
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

# HBA_SendSRL function



## -description
The <b>HBA_SendSRL</b> routine issues a scan remote loop (SRL) request through the specified HBA to a specified domain controller. 



## -syntax

````
HBA_STATUS HBA_API HBA_SendSRL(
  _In_    HBA_HANDLE handle,
  _In_    HBA_WWN    hbaPortWWN,
  _In_    HBA_WWN    wwn,
  _In_    HBA_UINT32 domain,
  _Out_   void       *pRspBuffer,
  _Inout_ HBA_UINT32 *pRspBufferSize
);
````


## -parameters

### -param handle [in]

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA through which the request is sent. 


### -param hbaPortWWN [in]

Contains a 64-bit worldwide name (WWN) that uniquely identifies the port through which the SRL request is sent. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification. 


### -param wwn [in]

Contains a 64-bit WWN that uniquely identifies the FL_Port port that is associated with the loop that is scanned. The SRL request is sent to this port. If this member is <b>NULL</b>, it is ignored, and the SRL request is sent to the domain controller that is associated with the loop. The domain controller is identified by the value in <i>domain. </i>


### -param domain [in]

Indicates the number of the domain controller associated with the loops to scan. If <i>wwn</i> is nonzero, this member is ignored.


### -param pRspBuffer [out]

Pointer to a buffer that receives the output data of the SRL request. 


### -param pRspBufferSize [in, out]

On input, indicates the size, in bytes, of the buffer at <i>pRspBuffer</i>. On output, this member contains the number of bytes of data retrieved in <i>pRspBuffer</i>. If the buffer is not large enough to receive all of the response data, the data is truncated to the size of the buffer. Eight bytes is sufficient buffer space for any response. 


## -returns
The <b>HBA_SendSRL</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_SendSRL</b> returns one of the following values.
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>Returned if the complete payload of a reply to the SRL request was successfully retrieved. 
<dl>
<dt><b>HBA_STATUS_ERROR_ILLEGAL_WWN</b></dt>
</dl>Returned if the HBA referenced by <i>handle</i> does not contain a port with a name that matches <i>hbaPortWWN</i>. 
<dl>
<dt><b>HBA_STATUS_ERROR_ELS_REJECT</b></dt>
</dl>Returned if the destination port referenced by <i>wwn, </i>or the domain controller referenced by <i>domain, </i>rejected the request node identification information data (RNID) that identifies the source HBA.
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>Returned if an unspecified error occurred that prevented the execution of the SRL request. 

 


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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_SendSRL routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

