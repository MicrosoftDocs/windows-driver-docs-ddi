---
UID: NF:ntifs.FsRtlGetEcpListFromIrp
title: FsRtlGetEcpListFromIrp function
author: windows-driver-content
description: The FsRtlGetEcpListFromIrp routine returns a pointer to an extra create parameter (ECP) context structure list that is associated with a given IRP_MJ_CREATE operation.
old-location: ifsk\fsrtlgetecplistfromirp.htm
old-project: ifsk
ms.assetid: 9e225f00-f830-488f-8bf0-666290dc40b0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FsRtlGetEcpListFromIrp, FsRtlGetEcpListFromIrp routine [Installable File System Drivers], fsrtlref_85b1fc72-e8ce-4909-a0d4-1eab35b3a0cb.xml, ifsk.fsrtlgetecplistfromirp, ntifs/FsRtlGetEcpListFromIrp
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlGetEcpListFromIrp
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlGetEcpListFromIrp function


## -description


The <b>FsRtlGetEcpListFromIrp </b>routine returns a pointer to an extra create parameter (ECP) context structure list that is associated with a given IRP_MJ_CREATE operation.


## -parameters




### -param Irp [in]

A pointer to the IRP for an IRP_MJ_CREATE operation from which the ECP context structure list is to be extracted.


### -param EcpList [out]

Receives a pointer to the ECP context structure list that is associated with the IRP.


## -returns



<b>FsRtlGetEcpListFromIrp</b> returns STATUS_SUCCESS or an appropriate error status representing the final completion status of the operation. Possible error status codes include the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The given IRP was not an IRP-based IRP_MJ_CREATE operation. In this case, <i>EcpList</i> is undefined. 

</td>
</tr>
</table>
 




## -remarks



To attach an ECP context structure list to an IRP, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547250">FsRtlSetEcpListIntoIrp</a> routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547250">FsRtlSetEcpListIntoIrp</a>
 

 

