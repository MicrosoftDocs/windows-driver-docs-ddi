---
UID: NF:fcb.RxInferFileType
title: RxInferFileType function (fcb.h)
description: RxInferFileType tries to infer the file type (directory or non-directory) from a member in the RX_CONTEXT structure.
old-location: ifsk\rxinferfiletype.htm
tech.root: ifsk
ms.assetid: 340b304c-5484-4d98-9ef4-8814c68443a0
ms.date: 04/16/2018
ms.keywords: RxInferFileType, RxInferFileType function [Installable File System Drivers], fcb/RxInferFileType, ifsk.rxinferfiletype, rxref_e020604c-fa08-40f3-895d-425347c73307.xml
ms.topic: function
req.header: fcb.h
req.include-header: Rxcontx.h, Nodetype.h, Mrxfcb.h, Fcb.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- fcb.h
api_name:
- RxInferFileType
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxInferFileType function


## -description


<b>RxInferFileType</b> tries to infer the file type (directory or non-directory) from a member in the RX_CONTEXT structure.


## -parameters




### -param RxContext [in]

A pointer to the RX_CONTEXT structure.


## -returns



<b>RxInferFileType </b>returns the storage type implied by the open. 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>FileTypeDirectory</b></dt>
</dl>
</td>
<td width="60%">
The file type is a directory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>FileTypeFile</b></dt>
</dl>
</td>
<td width="60%">
The file type is a file.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>FileTypeNotYetKnown</b></dt>
</dl>
</td>
<td width="60%">
The file type could not be determined. 

If RxInferFileType cannot determine the file type, this routine returns this value.

</td>
</tr>
</table>
 




## -remarks



<b>RxInferFileType</b> tries to infer the file type (directory or non-directory) from the <b>Create.NtCreateParameters.CreateOptions</b> member in the RX_CONTEXT structure.

The <b>RxInferFileType</b> routine is not called internally by RDBSS. The <b>RxInferFileType</b> routine might be used as a helper routine by a network mini-redirector driver in the <b>MRxCreate</b> routine provided by the network mini-redirector. <b>MRxCreate</b> would normally be called when an I/O request packet is received for IRP_MJ_CREATE. This IRP is normally received by RDBSS in response to a user-mode application requesting a file open or create operation. It is also possible for another kernel driver to issue such an IRP. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/mrxcreate">MRxCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/rxcontx/ns-rxcontx-_rx_context">RX_CONTEXT</a>
 

 

