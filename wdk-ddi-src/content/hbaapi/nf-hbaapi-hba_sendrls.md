---
UID: NF:hbaapi.HBA_SendRLS
title: HBA_SendRLS function
author: windows-driver-content
description: The HBA_SendRLS WMI routine sends a read link error status block (RLS) request through the indicated local port to the indicated remote port to retrieve a link error status block associated with the remote port.
old-location: storage\hba_sendrls.htm
tech.root: storage
ms.assetid: d2349c45-eb88-4584-bbdd-b7c46601a1bc
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HBA_SendRLS, HBA_SendRLS routine [Storage Devices], fibreHBA_rtns_8a7d150c-eeba-4850-9a93-7a48096d6f22.xml, hbaapi/HBA_SendRLS, storage.hba_sendrls
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hbaapi.dll
api_name:
-	HBA_SendRLS
product:
- Windows
targetos: Windows
req.typenames: 
---

# HBA_SendRLS function


## -description


The <b>HBA_SendRLS</b> WMI routine sends a read link error status block (RLS) request through the indicated local port to the indicated remote port to retrieve a link error status block associated with the remote port.


## -parameters




### -param HbaHandle [in]

Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a> that identifies the HBA through which the request is sent. 


### -param HbaPortWWN [in]

Contains a 64-bit worldwide name (WWN) that uniquely identifies the local port through which the request is sent. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification. 


### -param DestWWN [in]

Contains a 64-bit WWN that uniquely identifies the destination port to which the request is sent. 


### -param pRspBuffer [out]

Pointer to a buffer that receives the output data of the RLS request, if the request succeeds. If the destination port rejects the request, this buffer holds the link service reject (LS_RJT) payload data. If the amount of returned data exceeds the buffer size specified in <i>pRspBufferSize</i>, the data is truncated to the buffer size<i>. </i>The payload data is in big-endian format (higher order bytes are in lower addresses). 


### -param pRspBufferSize [in, out]

Indicates the size, in bytes, of the buffer at <i>pRspBuffer</i>. A size of 28 bytes is sufficient for the largest response.


## -returns



The <b>HBA_SendRLS</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_SendRLS</b> returns one of the following values.

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
Returned if the complete payload of a reply to the RLS request was successfully retrieved. 

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
Returned if the destination port referenced by <i>DestWWN </i>rejected the request node identification information data (RNID) that identifies the source HBA. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the execution of the RLS request. 

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
 

 

