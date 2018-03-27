---
UID: NF:rxprocs.RxPrepareToReparseSymbolicLink
title: RxPrepareToReparseSymbolicLink function
author: windows-driver-content
description: RxPrepareToReparseSymbolicLink sets up the file object name to facilitate a reparse. This routine is used by the network mini-redirectors to traverse symbolic links.
old-location: ifsk\rxpreparetoreparsesymboliclink.htm
old-project: ifsk
ms.assetid: 6a05b25f-e529-469a-8bfc-e75c0f7a9a8a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxPrepareToReparseSymbolicLink, RxPrepareToReparseSymbolicLink routine [Installable File System Drivers], ifsk.rxpreparetoreparsesymboliclink, rxprocs/RxPrepareToReparseSymbolicLink, rxref_6726dffd-ccae-43e0-98da-14dc0d11c7c2.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxprocs.h
req.include-header: Rxprocs.h
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
-	RxPrepareToReparseSymbolicLink
product: Windows
targetos: Windows
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---

# RxPrepareToReparseSymbolicLink function


## -description


<b>RxPrepareToReparseSymbolicLink</b> sets up the file object name to facilitate a reparse. This routine is used by the network mini-redirectors to traverse symbolic links. 


## -parameters




### -param RxContext

A pointer to the RX_CONTEXT structure.


### -param SymbolicLinkEmbeddedInOldPath

A Boolean value that indicates that a symbolic link was encountered. If the value is <b>TRUE</b>, a symbolic link was encountered as part of the traversal of the old path.


### -param NewPath

A pointer to a Unicode string that contains the new path name to be traversed.


### -param NewPathIsAbsolute

A Boolean value that indicates if the new path is absolute. If this value is <b>FALSE</b>, \Device\Mup should be prepended to <i>NewPath</i>. If this value is <b>TRUE</b>, the <i>NewPath</i> parameter is the full path to reparse. In this case, the buffer that contains <i>NewPath</i> is used directly, rather than allocating a new buffer.


### -param ReparseRequired

A pointer to a Boolean value that indicates whether a reparse is required. If this value is <b>TRUE</b>, a reparse is required.


## -returns



<b>RxPrepareToReparseSymbolicLink</b> returns STATUS_SUCCESS on success or one of the following error values on failure: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
A request to delete failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There were insufficient resources available.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was passed to the routine. This error will be returned if the <b>MajorFunction</b> member of <i>RxContext </i>is not IRP_MJ_CREATE. 

</td>
</tr>
</table>
 




## -remarks



The <b>RxPrepareToReparseSymbolicLink</b> routine would only be used by a network mini-redirector that supports symbolic links and uses reparse points to implement symbolic links. The <b>RxPrepareToReparseSymbolicLink</b> routine would normally be called by a network mini-redirector from its <b>MrxCreate</b> callback routine.

The <i>SymbolicLinkEmbeddedInOldPath</i> parameter passed to this routine is very important. To preserve the correct semantics, it should be carefully used. For example, consider the old path \A\B\C\D where C happens to be a symbolic link. In this case, the symbolic link is embedded in the path and <i>SymbolicLinkEmbeddedInOldPath</i> should be set to <b>TRUE</b>. In contrast, this is very different from the case when D happens to be a symbolic link. In the former case, the reparse constitutes an intermediate step. In the second example, the reparse constitutes the final step of the name resolution and <i>SymbolicLinkEmbeddedInOldPath</i> should be set to <b>FALSE</b>.

If DELETE access is specified, the open or create operation is denied for all cases in which the symbolic link is not embedded. It is possible that if DELETE access were the only one specified, then the open attempt must succeed without reparse. This conforms UNIX symbolic link semantics.

As part of this routine, <i>RxContext</i> is also tagged appropriately. This ensures that the return value can be crosschecked with the invocation of this routine. Once <b>RxPrepareToReparseSymbolicLink</b> is invoked, the network mini redirector has to return STATUS_REPARSE.

The value of the <i>ReparseRequired</i> parameter assumes significance only if STATUS_SUCCESS is returned from this routine. If <i>ReparseRequired</i> is <b>FALSE</b>, this implies that no reparse attempt is required and the symbolic link file itself should be manipulated as opposed to the target of the link. If <i>ReparseRequired</i> is <b>TRUE</b>, this implies that a reparse attempt was successfully setup. In such cases, it is imperative that the network mini redirector returns STATUS_REPARSE for the associated <b>MRxCreate</b> call. RDBSS will initiate a check for this condition. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549862">MRxCreate</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxPrepareToReparseSymbolicLink routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

