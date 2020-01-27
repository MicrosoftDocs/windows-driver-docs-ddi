---
UID: NF:ntifs.FsRtlSetEcpListIntoIrp
title: FsRtlSetEcpListIntoIrp function (ntifs.h)
description: The FsRtlSetEcpListIntoIrp routine attaches an extra create parameter (ECP) context structure list to an IRP_MJ_CREATE operation.
old-location: ifsk\fsrtlsetecplistintoirp.htm
tech.root: ifsk
ms.assetid: 370da53a-3c20-4e45-8732-8f08aa2d96ae
ms.date: 04/16/2018
ms.keywords: FsRtlSetEcpListIntoIrp, FsRtlSetEcpListIntoIrp routine [Installable File System Drivers], fsrtlref_b292fe42-cbfa-430d-abca-528482cecbed.xml, ifsk.fsrtlsetecplistintoirp, ntifs/FsRtlSetEcpListIntoIrp
f1_keywords:
 - "ntifs/FsRtlSetEcpListIntoIrp"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: FsRtlSetEcpListIntoIrp is available starting with Windows Vista.
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlSetEcpListIntoIrp
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlSetEcpListIntoIrp function


## -description


The <b>FsRtlSetEcpListIntoIrp</b> routine attaches an extra create parameter (ECP) context structure list to an IRP_MJ_CREATE operation. 


## -parameters




### -param Irp [in, out]

A pointer to the IRP for an IRP_MJ_CREATE operation to which the ECP context structure list is to be attached.


### -param EcpList [in]

Pointer to an ECP list that contains one or more ECP context structures. These structures will be attached to the IRP to which the <i>Irp</i> parameter points. 


## -returns



<b>FsRtlSetEcpListIntoIrp</b> returns one of the following NTSTATUS values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The given ECP list was successfully attached to the given IRP. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
The given IRP was not an IRP-based IRP_MJ_CREATE operation. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_3</b></dt>
</dl>
</td>
<td width="60%">
An ECP list has already been attached to the given IRP. 

</td>
</tr>
</table>
 




## -remarks



The <b>FsRtlSetEcpListIntoIrp</b> routine provides a mechanism for passing extra create parameters down the file system filter stack to underlying filter drivers.

To retrieve an ECP list that is associated with a given IRP_MJ_CREATE operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546015">FsRtlGetEcpListFromIrp</a> routine.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)">ECP_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546015">FsRtlGetEcpListFromIrp</a>
 

 

