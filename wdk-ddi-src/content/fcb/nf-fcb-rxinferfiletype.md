---
UID: NF:fcb.RxInferFileType
title: RxInferFileType function
author: windows-driver-content
description: RxInferFileType tries to infer the file type (directory or non-directory) from a member in the RX_CONTEXT structure.
old-location: ifsk\rxinferfiletype.htm
old-project: ifsk
ms.assetid: 340b304c-5484-4d98-9ef4-8814c68443a0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: rxref_e020604c-fa08-40f3-895d-425347c73307.xml, ifsk.rxinferfiletype, fcb/RxInferFileType, RxInferFileType function [Installable File System Drivers], RxInferFileType
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	fcb.h
apiname:
-	RxInferFileType
product: Windows
targetos: Windows
req.typenames: FA_ENTRY, *PFA_ENTRY
---

# RxInferFileType function


## -description


<b>RxInferFileType</b> tries to infer the file type (directory or non-directory) from a member in the RX_CONTEXT structure.


## -syntax


````
RX_FILE_TYPE RxInferFileType(
  _In_ PRX_CONTEXT RxContext
);
````


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549862">MRxCreate</a>



<a href="..\rxcontx\ns-rxcontx-_rx_context.md">RX_CONTEXT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxInferFileType function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

