---
UID: NC:mrx.PMRX_GET_CONNECTION_ID
title: PMRX_GET_CONNECTION_ID
author: windows-driver-content
description: TheMRxGetConnectionId routine is called by RDBSS to request that a network mini-redirector return a connection ID, which can be used for handling multiple sessions.
old-location: ifsk\mrxgetconnectionid.htm
tech.root: ifsk
ms.assetid: c994060c-d8b3-4daa-a0dd-a734ffe34229
ms.date: 04/16/2018
ms.keywords: MRxGetConnectionId, MRxGetConnectionId routine [Installable File System Drivers], PMRX_GET_CONNECTION_ID, ifsk.mrxgetconnectionid, mrx/MRxGetConnectionId, mrxref_14943242-5da1-4404-bc5b-b86c2a88b347.xml
ms.topic: callback
req.header: mrx.h
req.include-header: Mrx.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	mrx.h
api_name:
-	MRxGetConnectionId
product:
- Windows
targetos: Windows
req.typenames: 
---

# PMRX_GET_CONNECTION_ID callback function


## -description


The<i>MRxGetConnectionId</i> routine is called by <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector return a connection ID, which can be used for handling multiple sessions. 


## -parameters




### -param RxContext [in, out]

A pointer to the RX_CONTEXT structure. This parameter contains the IRP that is requesting the operation. 


### -param UniqueId [in, out]

A pointer to the connection ID when the routine returns. 


## -returns



<i>MRxGetConnectionId</i> returns STATUS_SUCCESS on success or an appropriate NTSTATUS value, such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
This routine is not implemented. 

</td>
</tr>
</table>
 




## -remarks



<i>MRxGetConnectionId</i> is called by RDBSS when trying to find or construct a V_NET_ROOT structure. 

If connection IDs are supported by the network mini-redirector, then the returned connection ID is appended to the NET_ROOT structure name stored in the NetName table used by RDBSS for storing network names. RDBSS considers the connection ID as an opaque blob, and does a byte-by-byte comparison of the connection ID blob while looking up the NetName table for a given name with a connection ID. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549850">MRxCompleteBufferingStateChangeRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549856">MRxComputeNewBufferingState</a>
 

 

