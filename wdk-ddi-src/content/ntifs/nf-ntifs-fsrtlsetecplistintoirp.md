---
UID: NF:ntifs.FsRtlSetEcpListIntoIrp
title: FsRtlSetEcpListIntoIrp function
author: windows-driver-content
description: The FsRtlSetEcpListIntoIrp routine attaches an extra create parameter (ECP) context structure list to an IRP_MJ_CREATE operation.
old-location: ifsk\fsrtlsetecplistintoirp.htm
old-project: ifsk
ms.assetid: 370da53a-3c20-4e45-8732-8f08aa2d96ae
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.fsrtlsetecplistintoirp, fsrtlref_b292fe42-cbfa-430d-abca-528482cecbed.xml, ntifs/FsRtlSetEcpListIntoIrp, FsRtlSetEcpListIntoIrp, FsRtlSetEcpListIntoIrp routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	FsRtlSetEcpListIntoIrp
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlSetEcpListIntoIrp function


## -description


The <b>FsRtlSetEcpListIntoIrp</b> routine attaches an extra create parameter (ECP) context structure list to an IRP_MJ_CREATE operation. 


## -syntax


````
NTSTATUS FsRtlSetEcpListIntoIrp(
  _Inout_ PIRP      Irp,
  _In_    PECP_LIST EcpList
);
````


## -parameters




#### - Irp [in, out]

A pointer to the IRP for an IRP_MJ_CREATE operation to which the ECP context structure list is to be attached.


#### - EcpList [in]

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

To retrieve an ECP list that is associated with a given IRP_MJ_CREATE operation, use the <a href="..\ntifs\nf-ntifs-fsrtlgetecplistfromirp.md">FsRtlGetEcpListFromIrp</a> routine.



## -see-also

<a href="..\ntifs\nf-ntifs-fsrtlgetecplistfromirp.md">FsRtlGetEcpListFromIrp</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlSetEcpListIntoIrp routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

