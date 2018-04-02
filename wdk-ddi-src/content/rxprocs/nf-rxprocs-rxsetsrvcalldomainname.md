---
UID: NF:rxprocs.RxSetSrvCallDomainName
title: RxSetSrvCallDomainName function
author: windows-driver-content
description: RxSetSrvCallDomainName is called by a network mini-redirector driver to set the domain name associated with any given server (SRV_CALL structure).
old-location: ifsk\rxsetsrvcalldomainname.htm
old-project: ifsk
ms.assetid: 876b3932-780f-4d00-8afc-40960f8fcaaf
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RxSetSrvCallDomainName, RxSetSrvCallDomainName function [Installable File System Drivers], ifsk.rxsetsrvcalldomainname, rxprocs/RxSetSrvCallDomainName, rxref_f6d23374-7565-4922-8f1c-222886e3a90c.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxprocs.h
req.include-header: Mrxfcb.h, Rxprocs.h
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rxprocs.h
api_name:
-	RxSetSrvCallDomainName
product: Windows
targetos: Windows
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---

# RxSetSrvCallDomainName function


## -description


<b>RxSetSrvCallDomainName</b> is called by a network mini-redirector driver to set the domain name associated with any given server (SRV_CALL structure).


## -parameters




### -param SrvCall [in]

A pointer to the SRV_CALL structure. 


### -param DomainName [in]

A pointer to a buffer containing a zero-terminated Unicode string that names the domain to which this server belongs. 


## -returns



<b>RxSetSrvCallDomainName</b> returns STATUS_SUCCESS on success or one of the following error values on failure: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There were insufficient resources to complete this routine. The memory allocation request failed for nonpaged pool memory to store the new domain name.

</td>
</tr>
</table>
 




## -remarks



The domain name may not be known at the beginning of a network redirector request. The <b>RxSetSrvCallDomainName</b> routine allows the domain name to be associated with <i>SrvCall</i> once it is known. This routine would normally be used as part of the creation and initialization of a SRV_CALL structure.

If a domain name is already associated with the <i>SrvCall</i> parameter, then this domain name will be removed and the memory associated with this entry in <i>SrvCall</i> will be freed.

If the <i>DomainName</i> parameter is not a <b>NULL</b> pointer, and the <i>DomainName</i> parameter has a length greater than zero, then <b>RxSetSrvCallDomainName</b> allocates space for the <b>pDomainName</b> member of <i>SrvCall</i> from nonpaged pool with a pool tag of RX_SRVCALL_PARAMS_POOLTAG. The <b>RxSetSrvCallDomainName</b> routine sets the <b>buffer</b>, <b>length</b>, and <b>MaximumLength</b> members of the <b>pDomainName</b> structure. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554370">RxCreateSrvCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554426">RxFinalizeSrvCall</a>
 

 

