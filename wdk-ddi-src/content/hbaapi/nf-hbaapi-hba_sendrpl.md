---
UID: NF:hbaapi.HBA_SendRPL
title: HBA_SendRPL function
author: windows-driver-content
description: The HBA_SendRPL routine sends a read port list (RPL) request to the indicated port or domain controller.
old-location: storage\hba_sendrpl.htm
old-project: storage
ms.assetid: 2c8cb6bb-eb6b-4a2f-8d00-efb309273536
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: hbaapi/HBA_SendRPL, HBA_SendRPL routine [Storage Devices], storage.hba_sendrpl, HBA_SendRPL, fibreHBA_rtns_1b67cd99-3e8b-4667-a795-a3391b73e62c.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Hbaapi.dll
apiname:
-	HBA_SendRPL
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_SendRPL function


## -description


The <b>HBA_SendRPL</b> routine sends a read port list (RPL) request to the indicated port or domain controller. 


## -syntax


````
HBA_STATUS HBA_API HBA_SendRPL(
  _In_    HBA_HANDLE Handle,
  _In_    HBA_WWN    HbaPortWWN,
  _In_    HBA_WWN    AgentWwn,
  _In_    HBA_UINT32 AgentDomain,
  _In_    HBA_UINT32 PortIndex,
  _Out_   void       *pRspBuffer,
  _Inout_ HBA_UINT32 *RspBufferSize
);
````


## -parameters




### -param Handle [in]

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the local HBA through which the request is sent. 


### -param HbaPortWWN [in]

Contains a 64-bit worldwide name (WWN) that uniquely identifies the local port through which the read port list (RPL) command is sent. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification. 


### -param Agent_wwn

TBD


### -param Agent_domain

TBD


### -param PortIndex [in]

Contains the port index of the first port in the retrieved list of ports of type FC_Port. 


### -param pRspBuffer [out]

Pointer to a buffer that receives the results of the read port list (RPL) request, if the request succeeds. If the destination port or domain controller rejects the request, this buffer holds the link service reject (LS_RJT) payload data. If the amount of returned data exceeds the buffer size specified in <i>RspBufferSize</i>, the data is truncated to the buffer size<i>. </i>The payload data is in big-endian format (higher order bytes are in lower addresses). 


### -param pRspBufferSize

TBD




#### - AgentWwn [in]

Contains, when non-<b>NULL</b>, a 64-bit WWN that uniquely identifies the port to query for a list of ports of type FC_Port. If this member is <b>NULL</b>, it is ignored. For a definition of FC_Port, see the T11 committee's <i>Fibre Channel HBA API </i>specification. 


#### - AgentDomain [in]

Contains the domain number for the domain controller to query for a list of ports of type FC_Port. If <i>AgentWwn </i>is non-<b>NULL</b>, this member is ignored.  


#### - RspBufferSize [in, out]

On input, indicates the size, in bytes, of the buffer pointed to by <i>pRspBuffer</i>. On return, this member indicates the size, in bytes, of the response data. 


## -returns



The <b>HBA_SendRPL</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_SendRPL</b> returns one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>
</td>
<td width="60%">
Returned if the complete payload of a reply to the RPL request was successfully retrieved. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_ILLEGAL_WWN</b></dt>
</dl>
</td>
<td width="60%">
Returned if the HBA referenced by <i>handle</i> does not contain a port with a name that matches <i>HbaPortWWN</i>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_ELS_REJECT</b></dt>
</dl>
</td>
<td width="60%">
Returned if the destination port referenced by <i>AgentWwn, </i>or the domain controller referenced by <i>AgentDomain, </i>rejected the request node identification information data (RNID) that identifies the source HBA. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the execution of the RPL request. 

</td>
</tr>
</table>
 




## -see-also

<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_SendRPL routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

