---
UID: NC:mrx.PMRX_CALLDOWN
title: PMRX_CALLDOWN
author: windows-driver-content
description: This callback is called by RDBSS to request that the network mini-redirector perform an action based in the supplied IRP.
old-location: ifsk\mrxclosesrvopen.htm
old-project: ifsk
ms.assetid: 6300595e-8cf6-47c4-a6ca-7851dd95576d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: MRxCleanupFobx, MRxCloseSrvOpen, MRxCollapseOpen, MRxCreate, MRxDevFcbXXXControlFile, MRxFlush, MRxLowIOSubmit[LOWIO_OP_EXCLUSIVELOCK], MRxLowIOSubmit[LOWIO_OP_FSCTL], MRxLowIOSubmit[LOWIO_OP_IOCTL], MRxLowIOSubmit[LOWIO_OP_NOTIFY_CHANGE_DIRECTORY], MRxLowIOSubmit[LOWIO_OP_READ], MRxLowIOSubmit[LOWIO_OP_SHAREDLOCK], MRxLowIOSubmit[LOWIO_OP_UNLOCK], MRxLowIOSubmit[LOWIO_OP_UNLOCK_MULTIPLE], MRxLowIOSubmit[LOWIO_OP_WRITE], MRxQueryDirectory, MRxQueryEaInfo, MRxQueryFileInfo, MRxQueryQuotaInfo, MRxQuerySdInfo, MRxQueryVolumeInfo, MRxSetEaInfo, MRxSetFileInfo, MRxSetFileInfoAtCleanup, MRxSetQuotaInfo, MRxSetSdInfo, MRxSetVolumeInfo, MRxShouldTryToCollapseThisOpen, MRxTruncate, MRxZeroExtend, MyCalldown, MyCalldown routine [Installable File System Drivers], PMRX_CALLDOWN, ifsk.mrxclosesrvopen, mrx/MyCalldown, mrxref_e6b5df78-d201-4f9e-9422-089772c04674.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	MyCalldown
product: Windows
targetos: Windows
req.typenames: SetDSMCounters_IN, *PSetDSMCounters_IN
---

# PMRX_CALLDOWN callback


## -description


This callback is called by RDBSS to request that the network mini-redirector perform an action based in the supplied IRP.


## -prototype


````
PMRX_CALLDOWN MyCalldown;

NTSTATUS MyCalldown(
  _Inout_ PRX_CONTEXT RxContext
)
{ ... }
````


## -parameters




### -param RxContext [in, out]

A pointer to the RX_CONTEXT structure. This parameter contains the IRP that is requesting the operation. 


## -returns




            This callback returns STATUS_SUCCESS on success or an appropriate NTSTATUS value, such as the following: 

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
A request was made to stop or start the network mini-redirector, but the caller lacked the proper security for this operation. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The buffer to receive the extended attribute information was too small. 

This return value should be considered success and as much valid data as possible should be returned in the <b>Info.Buffer</b> member of the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer is too small to receive the requested data. 

If this value is returned, the <b>InformationToReturn</b> member of the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter should be set to the minimum size of the expected buffer for the call to succeed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CONNECTION_DISCONNECTED</b></dt>
</dl>
</td>
<td width="60%">
The connection was disconnected. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_EA_CORRUPT_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Invalid extended attribute information was received from the remote server. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_EA_TOO_LARGE</b></dt>
</dl>
</td>
<td width="60%">
The extended attribute information that is passed is larger than the size that is supported by the remote share. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FILE_CLOSED</b></dt>
</dl>
</td>
<td width="60%">
The FCB structure was acquired, but the associated SRV_OPEN structure has been closed. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There were insufficient resources to complete the operation. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INTERNAL_ERROR</b></dt>
</dl>
</td>
<td width="60%">
An internal error occurred in the network mini-redirector. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_BUFFER_SIZE</b></dt>
</dl>
</td>
<td width="60%">
The requested buffer size was too large. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
An invalid device request was sent to the network mini-redirector.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_NETWORK_RESPONSE</b></dt>
</dl>
</td>
<td width="60%">
An invalid response was received from the remote server. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was specified in <i>RxContext</i>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_LINK_FAILED</b></dt>
</dl>
</td>
<td width="60%">
The attempt to reconnect to a remote server to complete the request failed. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_MORE_PROCESSING_REQUIRED</b></dt>
</dl>
</td>
<td width="60%">
A network mini-redirector returns this value to disable collapsing of this open request. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NETWORK_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
Network access was denied. This error can be returned if the network mini-redirector was asked to open a new file on a read-only share. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NETWORK_NAME_DELETED</b></dt>
</dl>
</td>
<td width="60%">
A network name was deleted. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NONEXISTENT_EA_ENTRY</b></dt>
</dl>
</td>
<td width="60%">
There are no extended attributes on the file object and the user supplied an extended attribute index. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
A feature that is requested, such as remote boot or a remote page file, is not implemented. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
A feature that is requested, such as extended attributes, is not supported. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_COLLISION</b></dt>
</dl>
</td>
<td width="60%">
The network mini-redirector was asked to create a file that already exists. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The object name was not found. This error can be returned if the network mini-redirector was asked to open a file that doesn't exist. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_PATH_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The object path was not found. This error can be returned if an NTFS stream object was requested and the remote file system does not support streams. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ONLY_IF_CONNECTED</b></dt>
</dl>
</td>
<td width="60%">
The SRV_OPEN structure is not connected. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_REDIRECTOR_HAS_OPEN_HANDLES</b></dt>
</dl>
</td>
<td width="60%">
This was a request to stop the network mini-redirector, but the redirector has open handles that prevent it from stopping at this time.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_REDIRECTOR_NOT_STARTED</b></dt>
</dl>
</td>
<td width="60%">
This was a request to stop the network mini-redirector, but the redirector was not started.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_REDIRECTOR_STARTED</b></dt>
</dl>
</td>
<td width="60%">
This was a request to start the network mini-redirector, but the redirector was already started. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_REPARSE</b></dt>
</dl>
</td>
<td width="60%">
A reparse is required to handle a symbolic link. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_REQUEST_ABORTED</b></dt>
</dl>
</td>
<td width="60%">
The network request was aborted. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_RETRY</b></dt>
</dl>
</td>
<td width="60%">
The operation should be retried. This error can be returned if the network mini-redirector encountered a sharing violation or an access denied error. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SHARING_VIOLATION</b></dt>
</dl>
</td>
<td width="60%">
A sharing violation occurred. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The call was unsuccessful. 

</td>
</tr>
</table>
 




## -remarks



The<i> MRxCloseSrvOpen</i> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that the network mini-redirector close an SRV_OPEN structure.

<i>MRxCloseSrvOpen</i>
     is called by RDBSS as part of cleanup and close operations on a file object. It is assumed that the network mini-redirector will close a file across the network.

Before calling <i>MRxCloseSrvOpen</i>, RDBSS modifies the following members in the RX_CONTEXT structure, pointed to by the <i>RxContext</i> parameter:

<b>MajorFunction</b> is set to IRP_MJ_CLOSE

<b>pFcb</b> is set to the FCB structure for which close processing is to be initiated

<b>pFobx</b> is set to the FOBX structure for which close processing is to be initiated

RDBSS and a network mini-redirector do not necessarily close the SRV_OPEN structures when the user closes a file. To improve performance in some cases, a network mini-redirector may try to reuse the SRV_OPEN and the cached data without any contact with the server. Some Microsoft Windows applications exhibit behavior that opens, reads, and closes a file and then quickly reopens the same file. In these cases, reusing the SRV_OPEN structures can improve performance.

RDBSS calls<i> MRxCloseSrvOpen </i>for delayed close processing while scavenging an FOBX structure. This happens when the close processing was delayed in anticipation of an open request and no open requests were forthcoming.

<i>MRxCloseSrvOpen</i> cannot return a value of STATUS_RETRY indicating that the call should be retried. If a retry loop is necessary, it must be handled internally in the <i>MRxCloseSrvOpen</i> routine by the network mini-redirector.

The<a href="https://msdn.microsoft.com/1c06b2f4-b44a-4d8a-9205-987be1e497ad"> MRxCollapseOpen</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that the network mini-redirector collapse an open file system request onto an existing SRV_OPEN structure.


<a href="https://msdn.microsoft.com/library/windows/hardware/ff549847">MRxCollapseOpen</a> is called by RDBSS to collapse an SRV_OPEN structure locally. The network mini-redirector is consulted to determine if a collapse is possible so there is no reason to call the network mini-redirector twice. If the network mini-redirector decides to collapse the SRV_OPEN structure, then it will do so and pass back a returnable status. A return value of STATUS_SUCCESS is a terminating return value. A different return value, for example, STATUS_MORE_PROCESSING_REQUIRED, is considered a non-terminating return value. 

Before calling<a href="https://msdn.microsoft.com/1c06b2f4-b44a-4d8a-9205-987be1e497ad"> MRxCollapseOpen</a>, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

<b>pRelevantSrvOpen</b> is set to the SRV_OPEN structure to collapse.

<b>Create.pSrvCall</b> is set to the SRV_CALL structure associated with the SRV_OPEN.

If the network mini-redirector decides to collapse the SRV_OPEN structure, then the <b>SrvOpen</b> member of the RX_CONTEXT structure must be set to the collapsed SRV_OPEN structure.

The<a href="https://msdn.microsoft.com/library/windows/hardware/ff549862">MRxCreate</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that the network mini-redirector create a file system object. 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff549862">MRxCreate</a> is called by RDBSS to request that the network mini-redirector open a file system object across the network. This call is issued by RDBSS in response to receiving an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a> request.

Before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549862">MRxCreate</a>, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

<b>pRelevantSrvOpen</b> is set to the SRV_OPEN structure.

<b>Create.pSrvCall</b> is set to the SRV_CALL structure.

<b>Create.NtCreateParameters</b> is set to the requested NT_CREATE_PARAMETERS.

In the context of a network mini-redirector, a file object refers to the associated file control block (FCB) and file object extension (FOBX) structures. There is a one to one correspondence between file objects and FOBXs. Many file objects will refer to the same FCB, which represents a single file on a remote server. A client can have several different open requests (NtCreateFile requests) on the same FCB and each of these will create a new file object. RDBSS and network mini-redirectors can choose to send fewer <a href="https://msdn.microsoft.com/library/windows/hardware/ff549862">MRxCreate</a> requests than the NtCreateFile requests received, in effect sharing an SRV_OPEN structure among several FOBXs.

If the<a href="https://msdn.microsoft.com/d1b664cf-37b6-4c65-8634-21695af2db21"> MRxCreate</a> request was for a file overwrite and <i>MRxCreate</i> returned STATUS_SUCCESS, then RDBSS will acquire the paging I/O resource and truncate the file. If the file is being cached by cache manager, RDBSS will update the sizes the cache manager has with the ones just received from the server. 

Before returning,<a href="https://msdn.microsoft.com/d1b664cf-37b6-4c65-8634-21695af2db21"> MRxCreate</a> must set the <b>CurrentIrp-&gt;IoStatus.Information</b> member of the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter.

The<a href="https://msdn.microsoft.com/d60449d0-17d0-4303-8d0d-cba091de2b07"> MRxDevFcbXXXControlFile</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to pass a device FCB control request (an IOCTL or FSCTL request) to the network mini-redirector.


<a href="https://msdn.microsoft.com/library/windows/hardware/ff549876">MRxDevFcbXXXControlFile</a> handles IOCTL and FSCTL requests related to the device FCB that are sent to the network mini-redirector. 

Before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549876">MRxDevFcbXXXControlFile</a>, RDBSS modifies the following member in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

<b>MajorFunction</b> is set to the major function of the IRP

If this was an IRP_MJ_FILE_SYSTEM_CONTROL request, then RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

<b>LowIoContext.ParamsFor.FsCtl.MinorFunction</b> is set to the minor function code for the FSCTL code

<b>LowIoContext.ParamsFor.FsCtl.FsControlCode</b> is set to the FSCTL code for the IRP

If this was an IRP_MJ_DEVICE_CONTROL or IRP_MJ_INTERNAL_DEVICE_CONTROL request, then RDBSS modifies the following member in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

<b>LowIoContext.ParamsFor.FsCtl.FsControlCode</b> is set to the control code for the IRP.

If <a href="https://msdn.microsoft.com/library/windows/hardware/ff549876">MRxDevFcbXXXControlFile</a> returns STATUS_SUCCESS, then the routine was successful. Any other return value indicates that an error occurred.

The<a href="https://msdn.microsoft.com/b133a91f-3f8c-45af-a02c-58d894a2fa2e"> MRxFlush</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector write the contents of a file system object to storage. RDBSS issues this call in response to receiving an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549235">IRP_MJ_FLUSH_BUFFERS</a> request.


<a href="https://msdn.microsoft.com/library/windows/hardware/ff550669">MRxFlush</a> handles network requests for file flush.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff550703">MRxLowIOSubmit[LOWIO_OP_EXCLUSIVELOCK]</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector open an exclusive lock on a file object.

RDBSS calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550703">MRxLowIOSubmit[LOWIO_OP_EXCLUSIVELOCK]</a> in response to receiving an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a> request with a minor code of IRP_MN_LOCK if <b>IrpSp-&gt;Flags</b> has the SL_EXCLUSIVE_LOCK bit set.

Before calling<a href="https://msdn.microsoft.com/7f6613d1-63fb-4505-966d-155dc2b80ffe"> MRxLowIOSubmit[LOWIO_OP_EXCLUSIVELOCK]</a>, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

The <b>LowIoContext.Operation</b> member is set to LOWIO_OP_EXCLUSIVELOCK.

The <b>LowIoContext.ResourceThreadId</b> member is set to the thread of the process that initiated the operation in RDBSS.

The <b>LowIoContext.ParamsFor.Locks.ByteOffset</b> member is set to the value of <b>IrpSp-&gt;Parameters.LockControl.ByteOffset.QuadPart</b>.

The <b>LowIoContext.ParamsFor.Locks.Key</b> member is set to the value of <b>IrpSp-&gt;Parameters.LockControl.Key</b>.

The <b>LowIoContext.ParamsFor.Locks.Flags</b> member is set to the value of <b>IrpSp-&gt;Flags</b>.

The <b>LowIoContext.ParamsFor.Locks.Length</b> member is set to the value of <b>IrpSp-&gt;Parameters.LockControl.Length.QuadPart</b>.

The <b>LowIoContext.Operation</b> member of the RX_CONTEXT structure specifies the low I/O operation to perform. It is possible for several of the low I/O routines to point to the same routine in a network mini-redirector because this <b>LowIoContext.Operation</b> member can be used to differentiate the low I/O operation that is requested. For example, all the I/O calls related to file locks could call the same low I/O routine in the network mini-redirector and that routine could use the <b>LowIoContext.Operation</b> member to differentiate between the lock and unlock operation that is requested.

If the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550703">MRxLowIOSubmit[LOWIO_OP_EXCLUSIVELOCK]</a> routine can take a long time to complete, the network mini-redirector driver should release the FCB structure before initiating the network communication. The FCB structure can be released by calling <a href="..\mrxfcb\nf-mrxfcb-rxreleasefcbresourceforthreadinmrx.md">RxReleaseFcbResourceForThreadInMRx</a>. While the <i>MRxLowIOSubmit[LOWIO_OP_EXCLUSIVELOCK]</i> routine is processing, the <b>LowIoContext.ResourceThreadId</b> member of RX_CONTEXT is guaranteed to indicate the thread of the process that initiated the operation in RDBSS. 

The <b>LowIoContext.ResourceThreadId</b> member of RX_CONTEXT can be used to release the FCB structure on behalf of another thread. When an asynchronous routine completes, the FCB structure that was acquired from the initial thread can be released. 

The<a href="https://msdn.microsoft.com/6bbb4b65-c447-47d8-9d05-f2adfb607099"> MRxLowIOSubmit[LOWIO_OP_FSCTL]</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector issue file system control request on remote file.

RDBSS calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550709">MRxLowIOSubmit[LOWIO_OP_FSCTL]</a> in response to receiving an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550751">IRP_MJ_FILE_SYSTEM_CONTROL</a> request.

Before calling<a href="https://msdn.microsoft.com/6bbb4b65-c447-47d8-9d05-f2adfb607099"> MRxLowIOSubmit[LOWIO_OP_FSCTL]</a>, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

The <b>LowIoContext.Operation</b> member is set to LOWIO_OP_FSCTL.

The <b>LowIoContext.ResourceThreadId</b> member is set to the thread of the process that initiated the operation in RDBSS.

The <b>LowIoContext.ParamsFor.FsCtl.FsControlCode</b> member is set to the FSCTL major control code.

The <b>LowIoContext.ParamsFor.FsCtl.MinorFunction</b> member is set to the FSCTL minor control code.

The <b>LowIoContext.ParamsFor.FsCtl.pInputBuffer</b> member is set to the input buffer.

The <b>LowIoContext.ParamsFor.FsCtl.InputBufferLength</b> member is set to the input buffer length.

The <b>LowIoContext.ParamsFor.FsCtl.pOutputBuffer</b> member is set to the output buffer.

The <b>LowIoContext.ParamsFor.FsCtl.OutputBufferLength</b> member is set to the output buffer length.

The file system control code (FSCTL) requests handled by a network mini-redirector can be classified into one of several categories:

<ul>
<li>
FSCTLs that are implemented and used by RDBSS and the network mini redirector

</li>
<li>
FSCTLs that are implemented and used only by the network mini-redirector

</li>
<li>
FSCTLs which should never be seen by the network mini-redirector. These FSCTLs are solely intended as a debugging aid.

</li>
</ul>
While the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550709">MRxLowIOSubmit[LOWIO_OP_FSCTL]</a> routine is processing, the <b>LowIoContext.ResourceThreadId</b> member of RX_CONTEXT is guaranteed to indicate the thread of the process that initiated the operation in RDBSS. The <b>LowIoContext.ResourceThreadId</b> member of RX_CONTEXT can be used to release the input resource on behalf of another thread. When an asynchronous routine completes, the input resource that was acquired from the initial thread can be released. 

The<a href="https://msdn.microsoft.com/b416e2b4-6024-45ec-adf5-90743d417ad5"> MRxLowIOSubmit[LOWIO_OP_IOCTL]</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to issue an I/O system control request to the network mini-redirector.

RDBSS calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550715">MRxLowIOSubmit[LOWIO_OP_IOCTL]</a> in response to receiving an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a> requests.

Before calling<a href="https://msdn.microsoft.com/b416e2b4-6024-45ec-adf5-90743d417ad5"> MRxLowIOSubmit[LOWIO_OP_IOCTL]</a>, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

The <b>LowIoContext.Operation</b> member is set to LOWIO_OP_IOCTL.

The <b>LowIoContext.ResourceThreadId</b> member is set to the thread of the process that initiated the operation in RDBSS.

The <b>LowIoContext.ParamsFor.IoCtl.IoControlCode</b> member is set to the IOCTL control code.

The <b>LowIoContext.ParamsFor.IoCtl.pInputBuffer</b> member is set to the input buffer.

The <b>LowIoContext.ParamsFor.IoCtl.InputBufferLength</b> member is set to the input buffer length.

The <b>LowIoContext.ParamsFor.IoCtl.pOutputBuffer</b> member is set to the output buffer.

The <b>LowIoContext.ParamsFor.IoCtl.OutputBufferLength</b> member is set to the output buffer length.

While the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550715">MRxLowIOSubmit[LOWIO_OP_IOCTL]</a> routine is processing, the <b>LowIoContext.ResourceThreadId</b> member of RX_CONTEXT is guaranteed to indicate the thread of the process that initiated the operation in RDBSS. The <b>LowIoContext.ResourceThreadId</b> member of RX_CONTEXT can be used to release the input resource on behalf of another thread. When an asynchronous routine completes, the input resource that was acquired from the initial thread can be released. 

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff550721">MRxLowIOSubmit[LOWIO_OP_NOTIFY_CHANGE_DIRECTORY]</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to issue a request to the network mini-redirector for a directory change notification operation. 

RDBSS calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550721">MRxLowIOSubmit[LOWIO_OP_NOTIFY_CHANGE_DIRECTORY]</a> in response to receiving an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548658">IRP_MJ_DIRECTORY_CONTROL</a> request.

Before calling<a href="https://msdn.microsoft.com/a3ac7936-7c46-4e46-929a-dc495187a01b"> MRxLowIOSubmit[LOWIO_OP_NOTIFY_CHANGE_DIRECTORY]</a>, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

The <b>LowIoContext.Operation</b> member is set to LOWIO_OP_NOTIFY_CHANGE_DIRECTORY.

The <b>LowIoContext.ResourceThreadId</b> member is set to the thread of the process that initiated the operation in RDBSS.

The <b>LowIoContext.ParamsFor.NotifyChangeDirectory.WatchTree</b> member is set to <b>TRUE</b> if the <b>IrpSp-&gt;Flags</b> has the SL_WATCH_TREE bit set. 

The <b>LowIoContext.ParamsFor.NotifyChangeDirectory.CompletionFilter</b> member is set to the value of <b>IrpSp-&gt;Parameters.NotifyDirectory.CompletionFilter</b>.

The <b>LowIoContext.ParamsFor.NotifyChangeDirectory.NotificationBufferLength</b> member is set to the value of <b>IrpSp-&gt;Parameters.NotifyDirectory.Length</b>.

The <b>LowIoContext.ParamsFor.NotifyChangeDirectory.pNotificationBuffer</b> member is set to the value returned by calling <b>MmGetSystemAddressForMdlSafe</b> passing in the <b>Irp-&gt;MdlAddress</b> and NormalPagePriority. The user buffer also is probed and locked for write access. 

A directory change notification operation is normally implemented by a network mini-redirector as an asynchronous operation because it can take considerable time. The operation usually consists of sending a network request to the remote server requesting change notification. The response is obtained when the desired change is affected on the server. This is an example of an operation for which the network mini-redirector may need to register a unique context value for handling cancellations initiated locally.

While the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550721">MRxLowIOSubmit[LOWIO_OP_NOTIFY_CHANGE_DIRECTORY]</a> routine is processing, the <b>LowIoContext.ResourceThreadId</b> member of RX_CONTEXT is guaranteed to indicate the thread of the process that initiated the operation in RDBSS. The <b>LowIoContext.ResourceThreadId</b> member can be used to release the FCB structure on behalf of another thread. When an asynchronous routine completes, the FCB structure that was acquired from the initial thread can be released. The FCB structure can be released by calling <a href="..\mrxfcb\nf-mrxfcb-rxreleasefcbresourceforthreadinmrx.md">RxReleaseFcbResourceForThreadInMRx</a>. 

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff550724">MRxLowIOSubmit[LOWIO_OP_READ]</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to issue a read request to the network mini-redirector. 

RDBSS calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550724">MRxLowIOSubmit[LOWIO_OP_READ]</a> in response to receiving an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a> request.

Before calling<a href="https://msdn.microsoft.com/26a173d8-e3ab-4c63-8390-133afd35b51a"> MRxLowIOSubmit[LOWIO_OP_READ]</a>, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

The <b>LowIoContext.Operation</b> member is set to LOWIO_OP_READ.

The <b>LowIoContext.ResourceThreadId</b> member is set to the thread of the process that initiated the operation in RDBSS.

The <b>LowIoContext.ParamsFor.ReadWrite.Key</b> member is set to the value of <b>IrpSp-&gt;Parameters.Read.Key</b>.

The <b>ParamsFor.ReadWrite.Flags</b> member has the LOWIO_READWRITEFLAG_PAGING_IO bit is set on if <b>Irp-&gt;Flags</b> has the IRP_PAGING_IO bit on.

The <b>ParamsFor.ReadWrite.Buffer</b> member is set to the user buffer locked for IoReadAccess.

The <b>LowIoContext.ParamsFor.ReadWrite.ByteCount</b> member is set to the value of IrpSp-&gt;Parameters.Read.Length.

A read request is normally implemented by a network mini-redirector as an asynchronous operation because it can take considerable time. The operation usually consists of sending a network request to the remote server. The response is obtained when the read request is completed on the server. This is an example of an operation for which the network mini-redirector may need to register a context for handling cancellations initiated locally.

While the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550724">MRxLowIOSubmit[LOWIO_OP_READ]</a> routine is processing, the <b>LowIoContext.ResourceThreadId</b> member of RX_CONTEXT is guaranteed to indicate the thread of the process that initiated the operation in RDBSS. The <b>LowIoContext.ResourceThreadId</b> member can be used to release the FCB structure on behalf of another thread. When an asynchronous routine completes, the FCB structure that was acquired from the initial thread can be released. The FCB structure can be released by calling <a href="..\mrxfcb\nf-mrxfcb-rxreleasefcbresourceforthreadinmrx.md">RxReleaseFcbResourceForThreadInMRx</a>. 

The<a href="https://msdn.microsoft.com/963ec2d1-5e24-4002-a8c9-44faf1515b9f"> MRxLowIOSubmit[LOWIO_OP_SHAREDLOCK]</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network redirector open a shared lock on a file object. 

RDBSS calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550734">MRxLowIOSubmit[LOWIO_OP_SHAREDLOCK]</a> in response to receiving an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a> request with a minor code of IRP_MN_LOCK if <b>IrpSp-&gt;Flags</b> does not have the SL_EXCLUSIVE_LOCK bit set.

Before calling<a href="https://msdn.microsoft.com/963ec2d1-5e24-4002-a8c9-44faf1515b9f"> MRxLowIOSubmit[LOWIO_OP_SHAREDLOCK]</a>, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

The <b>LowIoContext.Operation</b> member is set to LOWIO_OP_SHAREDLOCK.

The <b>LowIoContext.ResourceThreadId</b> member is set to the thread of the process that initiated the operation in RDBSS.

The <b>LowIoContext.ParamsFor.Locks.ByteOffset</b> member is set to the value of <b>IrpSp-&gt;Parameters.LockControl.ByteOffset.QuadPart</b>.

The <b>LowIoContext.ParamsFor.Locks.Key</b> member is set to the value of <b>IrpSp-&gt;Parameters.LockControl.Key</b>.

The <b>LowIoContext.ParamsFor.Locks.Flags</b> member is set to the value of <b>IrpSp-&gt;Flags</b>.

The <b>LowIoContext.ParamsFor.Locks.Length</b> member is set to the value of <b>IrpSp-&gt;Parameters.LockControl.Length.QuadPart</b>.

The <b>LowIoContext.Operation</b> member of the RX_CONTEXT structure specifies the low I/O operation to perform. It is possible for several of the low I/O routines to point to the same routine in a network mini-redirector because the <b>LowIoContext.Operation</b> member can be used to differentiate the low I/O operation that is requested. For example, all the I/O calls related to file locks could call the same low I/O routine in the network mini-redirector and this routine could use the <b>LowIoContext.Operation</b> member to differentiate between the lock and unlock operation that is requested.

If the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550734">MRxLowIOSubmit[LOWIO_OP_SHAREDLOCK]</a> routine can take a long time to complete, the network mini-redirector driver should release the FCB structure before initiating the network communication. The FCB structure can be released by calling <a href="..\mrxfcb\nf-mrxfcb-rxreleasefcbresourceforthreadinmrx.md">RxReleaseFcbResourceForThreadInMRx</a>. While the <i>MRxLowIOSubmit[LOWIO_OP_SHAREDLOCK]</i> routine is processing, the <b>LowIoContext.ResourceThreadId</b> member of RX_CONTEXT is guaranteed to indicate the thread of the process that initiated the operation in RDBSS. 

The <b>LowIoContext.ResourceThreadId</b> member of the RX_CONTEXT structure can be used to release the FCB structure on behalf of another thread. When an asynchronous routine completes, the FCB structure that was acquired from the initial thread can be released. 

The<a href="https://msdn.microsoft.com/2985ae12-965d-4871-b56e-2589898932e1"> MRxLowIOSubmit[LOWIO_OP_UNLOCK]</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector remove a single lock on a file object.

RDBSS calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550740">MRxLowIOSubmit[LOWIO_OP_UNLOCK]</a> in response to receiving an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a> request with a minor code of IRP_MN_UNLOCK_SINGLE.

Before calling<a href="https://msdn.microsoft.com/2985ae12-965d-4871-b56e-2589898932e1"> MRxLowIOSubmit[LOWIO_OP_UNLOCK]</a>, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

The <b>LowIoContext.Operation</b> member is set to LOWIO_OP_UNLOCK.

The <b>LowIoContext.ResourceThreadId</b> member is set to the thread of the process that initiated the operation in RDBSS.

The <b>LowIoContext.ParamsFor.Locks.ByteOffset</b> member is set to the value of <b>IrpSp-&gt;Parameters.LockControl.ByteOffset.QuadPart</b>.

The <b>LowIoContext.ParamsFor.Locks.Key</b> member is set to the value of <b>IrpSp-&gt;Parameters.LockControl.Key</b>.

The <b>LowIoContext.ParamsFor.Locks.Length</b> member is set to the value of <b>IrpSp-&gt;Parameters.LockControl.Length.QuadPart</b>.

The <b>LowIoContext.Operation</b> member of the RX_CONTEXT structure specifies the low I/O operation to perform. It is possible for several of the low I/O routines to point to the same routine in a network mini-redirector because this <b>LowIoContext.Operation</b> member can be used to differentiate the low I/O operation that is requested. For example, all the I/O calls related to file locks could call the same low I/O routine in the network mini-redirector and this routine could use the <b>LowIoContext.Operation</b> member to differentiate between the lock and unlock operation that is requested.

If the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550740">MRxLowIOSubmit[LOWIO_OP_UNLOCK]</a> routine can take a long time to complete, the network mini-redirector driver should release the FCB structure before initiating the network communication. The FCB structure can be released by calling <a href="..\mrxfcb\nf-mrxfcb-rxreleasefcbresourceforthreadinmrx.md">RxReleaseFcbResourceForThreadInMRx</a>. While the <i>MRxLowIOSubmit[LOWIO_OP_UNLOCK]</i> routine is processing, the <b>LowIoContext.ResourceThreadId</b> member of RX_CONTEXT is guaranteed to indicate the thread of the process that initiated the operation in RDBSS. 

The <b>LowIoContext.ResourceThreadId</b> member of RX_CONTEXT can be used to release the FCB structure on behalf of another thread. When an asynchronous routine completes, the FCB structure that was acquired from the initial thread can be released. 

The<a href="https://msdn.microsoft.com/50f7abdf-a3f7-4625-ac54-75e80807d05e"> MRxLowIOSubmit[LOWIO_OP_UNLOCK_MULTIPLE]</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that the network mini-redirector remove multiple locks held on a file object.

RDBSS calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550745">MRxLowIOSubmit[LOWIO_OP_UNLOCK_MULTIPLE]</a> in response to receiving an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549251">IRP_MJ_LOCK_CONTROL</a> request with a minor code of IRP_MN_UNLOCK_ALL or IRP_MN_UNLOCK_ALL_BY_KEY.

Before calling<a href="https://msdn.microsoft.com/50f7abdf-a3f7-4625-ac54-75e80807d05e"> MRxLowIOSubmit[LOWIO_OP_UNLOCK_MULTIPLE]</a>, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

The <b>LowIoContext.Operation</b> member is set to LOWIO_OP_UNLOCK_MULTIPLE.

The <b>LowIoContext.ResourceThreadId</b> member is set to the thread of the process that initiated the operation in RDBSS.

The <b>LowIoContext.ParamsFor.Locks.LockList</b> member is set to a list of LOWIO_LOCK_LIST elements. Each element specifies a range to be unlocked.

The byte ranges to be unlocked are specified in the <b>LowIoContext.ParamsFor.Locks.LockList</b> member of the RX_CONTEXT structure. The LOWIO_LOCK_LIST structure is as follows: 

<pre class="syntax" xml:space="preserve"><code>typedef struct _LOWIO_LOCK_LIST {
  struct  _LOWIO_LOCK_LIST  *Next;
  ULONG  LockNumber;
  RXVBO  ByteOffset;
  LONGLONG  Length;
  ULONG  Key;
  BOOLEAN  ExclusiveLock;
} LOWIO_LOCK_LIST, *PLOWIO_LOCK_LIST;</code></pre>
The <b>LowIoContext.Operation</b> member of RX_CONTEXT specifies the low I/O operation to perform. It is possible for several of the low I/O routines to point to the same routine in a network mini-redirector because the <b>LowIoContext.Operation</b> member can be used to differentiate the low I/O operation that is requested. For example, all the I/O calls related to file locks could call the same low I/O routine in the network mini-redirector and this routine could use the <b>LowIoContext.Operation</b> member to differentiate between the lock and unlock operation that is requested.

If the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550745">MRxLowIOSubmit[LOWIO_OP_UNLOCK_MULTIPLE]</a> routine can take a long time to complete, the network mini-redirector driver should release the FCB structure before initiating the network communication. The FCB structure can be released by calling <a href="..\mrxfcb\nf-mrxfcb-rxreleasefcbresourceforthreadinmrx.md">RxReleaseFcbResourceForThreadInMRx</a>. While the <i>MRxLowIOSubmit[LOWIO_OP_UNLOCK_MULTIPLE]</i> routine is processing, the <b>LowIoContext.ResourceThreadId</b> member of RX_CONTEXT is guaranteed to indicate the thread of the process that initiated the operation in RDBSS. 

The <b>LowIoContext.ResourceThreadId</b> member of RX_CONTEXT can be used to release the FCB structure on behalf of another thread. When an asynchronous routine completes, the FCB structure that was acquired from the initial thread can be released. 

The<a href="https://msdn.microsoft.com/b70838e3-4e80-4ec9-88ba-0f608a1af78e"> MRxLowIOSubmit[LOWIO_OP_WRITE]</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to issue a write request to the network mini-redirector.

RDBSS calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550746">MRxLowIOSubmit[LOWIO_OP_WRITE]</a> in response to receiving an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a> request.

Before calling<a href="https://msdn.microsoft.com/b70838e3-4e80-4ec9-88ba-0f608a1af78e"> MRxLowIOSubmit[LOWIO_OP_WRITE]</a>, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

The <b>LowIoContext.Operation</b> member is set to LOWIO_OP_WRITE.

The <b>LowIoContext.ResourceThreadId</b> member is set to the thread of the process that initiated the operation in RDBSS.

The <b>LowIoContext.ParamsFor.ReadWrite.Key</b> member is set to the value of <b>IrpSp-&gt;Parameters.Read.Key</b>.

The <b>ParamsFor.ReadWrite.Flags</b> member has the LOWIO_READWRITEFLAG_PAGING_IO bit is set on if <b>Irp-&gt;Flags</b> has the IRP_PAGING_IO bit on.

The <b>ParamsFor.ReadWrite.Buffer</b> member is set to the user buffer locked for IoWriteAccess.

The <b>LowIoContext.ParamsFor.ReadWrite.ByteCount</b> member is set to the value of <b>IrpSp-&gt;Parameters.Write.Length</b>.

A write request is normally implemented by a network mini-redirector as an asynchronous operation because it can take considerable time. The operation usually consists of sending a network request to the remote server. The response is obtained when the write request is completed on the server. This is an example of an operation for which the network mini-redirector may need to register a context for handling cancellations initiated locally.

While the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550746">MRxLowIOSubmit[LOWIO_OP_WRITE]</a> routine is processing, the <b>LowIoContext.ResourceThreadId</b> member of RX_CONTEXT is guaranteed to indicate the thread of the process that initiated the operation in RDBSS. The <b>LowIoContext.ResourceThreadId</b> member can be used to release the FCB structure on behalf of another thread. When an asynchronous routine completes, the FCB structure that was acquired from the initial thread can be released. The FCB structure can be released by calling <a href="..\mrxfcb\nf-mrxfcb-rxreleasefcbresourceforthreadinmrx.md">RxReleaseFcbResourceForThreadInMRx</a>. 

The<a href="https://msdn.microsoft.com/26c7c7fa-7dfa-43fb-a1db-cfc2fc40b969"> MRxQueryDirectory</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector query information on a file directory.

Before calling<a href="https://msdn.microsoft.com/26c7c7fa-7dfa-43fb-a1db-cfc2fc40b969"> MRxQueryDirectory</a>, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

The <b>Info.FileInformationClass</b> member is set to <b>IrpSp-&gt;Parameters.QueryDirectory.FileInformationClass</b>.

The <b>Info.Buffer</b> member is set to user buffer from I/O request packet. This buffer has already been locked by RDBSS if needed.

The <b>Info.LengthRemaining</b> member is set to <b>IrpSp-&gt;Parameters.QueryDirectory.Length</b>.

The <b>QueryDirectory.FileIndex</b> member is set to <b>IrpSp-&gt;Parameters.QueryDirectory.FileIndex</b>.

The <b>QueryDirectory.RestartScan</b> member is set to nonzero if <b>IrpSp-&gt;Flags</b> has the SL_RESTART_SCAN bit on.

The <b>QueryDirectory.ReturnSingleEntry</b> member is set to nonzero if <b>IrpSp-&gt;Flags</b> has the SL_RETURN_SINGLE_ENTRY bit on.

The <b>QueryDirectory.IndexSpecified</b> member is set to nonzero if <b>IrpSp-&gt;Flags</b> has the SL_INDEX_SPECIFIED bit on.

The <b>QueryDirectory.InitialQuery</b> member is set to nonzero if <b>UnicodeQueryTemplate.Buffer</b> member of the associated FOBX is <b>NULL</b> and the <b>Flags</b> member of the FOBX does not have the FOBX_FLAG_MATCH_ALL bit on.

For a wild card query ("*.*", for example), RDBSS will set the <b>UnicodeQueryTemplate.Buffer</b> member of the associated FOBX to the wild card query passed.

If the <b>PostRequest</b> member of the RX_CONTEXT structure is <b>TRUE</b> on return from <a href="https://msdn.microsoft.com/library/windows/hardware/ff550755">MRxQueryDirectory</a>, then RDBSS will call <a href="..\rxprocs\nf-rxprocs-rxfsdpostrequest.md">RxFsdPostRequest</a> passing the RX_CONTEXT structure to a worker queue for processing by the file system process (FSP). 

The<a href="https://msdn.microsoft.com/4471eb82-c176-4976-b722-5a6e067a7e69"> MRxQueryEaInfo</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector query extended attribute information on a file system object.

RDBSS issues a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550759">MRxQueryEaInfo</a> in response to receiving an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549279">IRP_MJ_QUERY_EA</a> request. 

Before calling<a href="https://msdn.microsoft.com/4471eb82-c176-4976-b722-5a6e067a7e69"> MRxQueryEaInfo</a>, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

The <b>Info.Buffer</b> member is set to the user buffer from I/O request packet. This buffer has already been locked by RDBSS if needed.

The <b>Info.LengthRemaining</b> member is set to <b>IrpSp-&gt;Parameters.QueryEa.Length</b>.

The <b>QueryEa.UserEaList</b> member is set to <b>IrpSp-&gt;Parameters.QueryEa.EaList</b>.

The <b>QueryEa.UserEaListLength</b> member is set to <b>IrpSp-&gt;Parameters.QueryEa.EaListLength</b>.

The <b>QueryEa.UserEaIndex</b> member is set to <b>IrpSp-&gt;Parameters.QueryEa.EaIndex</b>.

The <b>QueryEa.RestartScan</b> member is set to nonzero if <b>IrpSp-&gt;Flags</b> has the SL_RESTART_SCAN bit on.

The <b>QueryEa.ReturnSingleEntry</b> member is set to nonzero if <b>IrpSp-&gt;Flags</b> has the SL_RETURN_SINGLE_ENTRY bit on.

The <b>QueryEa.IndexSpecified</b> member is set to nonzero if <b>IrpSp-&gt;Flags</b> has the SL_INDEX_SPECIFIED bit on.

On success, <a href="https://msdn.microsoft.com/library/windows/hardware/ff550759">MRxQueryEaInfo</a> should set the <b>Info.LengthRemaininging</b> member of the RX_CONTEXT structure to the length of extended attribute information returned and also update the <b>Fobx-&gt;OffsetOfNextEaToReturn</b> member. If the call to <i>MRxQueryEaInfo</i> was successful, RDBSS sets the <b>IoStatus.Information</b> member of the IRP to <b>IrpSp-&gt;Parameters.QueryEa.Length</b> minus the <b>Info.LengthRemaining</b> member of RX_CONTEXT. 

The<a href="https://msdn.microsoft.com/library/windows/hardware/ff550770">MRxQueryFileInfo</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector query file information on a file system object.

RDBSS issues a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550770">MRxQueryFileInfo</a> in response to receiving an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549283">IRP_MJ_QUERY_INFORMATION</a> request. 

Before calling<a href="https://msdn.microsoft.com/201b749c-527b-4c02-a860-d2f54777dc32"> MRxQueryFileInfo</a>, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

The <b>Info.FileInformationClass</b> member is set to <b>IrpSp-&gt;Parameters.QueryFile.FileInformationClass</b>, the requested FILE_INFORMATION_CLASS value.

The <b>Info.Buffer</b> member is set to the user buffer from the I/O request packet.

The <b>Info.LengthRemaining</b> member is set to <b>IrpSp-&gt;Parameters.QueryFile.Length</b>.

The <b>QueryDirectory.FileIndex</b> member is set to <b>IrpSp-&gt;Parameters.QueryDirectory.FileIndex</b>.

The <b>QueryDirectory.RestartScan</b> member is set if <b>IrpSp-&gt;Flags</b> has the SL_RESTART_SCAN bit set.

The <b>QueryDirectory.ReturnSingleEntry</b> member is set if <b>IrpSp-&gt;Flags</b> has SL_RETURN_SINGLE_ENTRY bit set.

The <b>QueryDirectory.InitialQuery</b> member is set if <b>Fobx-&gt;UnicodeQueryTemplate.Buffer</b> is <b>NULL</b> and <b>Fobx-&gt;Flags</b> does not have the FOBX_FLAG_MATCH_ALL bit set.

On success, the network mini-redirector should set the <b>Info.LengthRemaining</b> member of the RX_CONTEXT structure to <b>Info.Length</b> member minus the length of the file information returned. If the call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550770">MRxQueryFileInfo</a> was successful, RDBSS sets the <b>IoStatus.Information</b> member of the IRP to <b>IrpSp-&gt;Parameters.QueryFile.Length</b> minus the<b> Info.LengthRemaining</b> member of RX_CONTEXT. 

RDBSS does not support requests with the SL_INDEX_SPECIFIED bit of the <b>IrpSp-&gt;Flags</b> set. A network mini-redirector will not receive calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550770">MRxQueryFileInfo</a> with the SL_INDEX_SPECIFIED bit of <b>IrpSp-&gt;Flags</b> set.

The<a href="https://msdn.microsoft.com/44bf976b-09bc-4270-8c2e-8e55784aaa38"> MRxQueryQuotaInfo</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector query quota information on a file system object. 

RDBSS issues a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550773">MRxQueryQuotaInfo</a> in response to receiving an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549293">IRP_MJ_QUERY_QUOTA</a> request. 

Before calling<a href="https://msdn.microsoft.com/44bf976b-09bc-4270-8c2e-8e55784aaa38"> MRxQueryQuotaInfo</a>, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

The <b>Info.Buffer</b> member is set to user buffer from I/O request packet. This buffer has already been locked by RDBSS if needed.

The <b>Info.LengthRemaining</b> member is set to <b>IrpSp-&gt;Parameters.QueryQuota.Length</b>. 

The <b>QueryQuota.SidList</b> member is set to <b>IrpSp-&gt;Parameters.QueryQuota.SidList</b>. 

The <b>QueryQuota.SidListLength</b> member is set to <b>IrpSp-&gt;Parameters.QueryQuota.SidListLength</b>.

The <b>QueryQuota.StartSid</b> member is set to <b>IrpSp-&gt;Parameters.QueryQuota.StartSid</b>.

The <b>QueryQuota.Length</b> member is set to <b>IrpSp-&gt;Parameters.QueryQuota.Length</b>.

The <b>QueryQuota.RestartScan</b> member is set to nonzero if <b>IrpSp-&gt;Flags</b> has the SL_RESTART_SCAN bit set. 

The <b>QueryQuota.ReturnSingleEntry</b> member is set to nonzero if <b>IrpSp-&gt;Flags</b> has the SL_RETURN_SINGLE_ENTRY bit set. 

The <b>QueryQuota.IndexSpecified</b> member is set to nonzero if <b>IrpSp-&gt;Flags</b> has the SL_INDEX_SPECIFIED bit set. 

On success, the network mini-redirector should set the <b>Info.LengthRemaining</b> member of the RX_CONTEXT structure to the length of the quota information to return. If the call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550773">MRxQueryQuotaInfo</a> was successful, RDBSS sets the <b>IoStatus.Information</b> member of the IRP to the <b>Info.LengthRemaining</b> member of RX_CONTEXT. 

If the call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550773">MRxQueryQuotaInfo</a> is successful, the <b>InformationToReturn</b> member of the RX_CONTEXT structure should be set to the length of quota information returned. If the call is unsuccessful, the <b>InformationToReturn</b> member of RX_CONTEXT should be set to zero.

The<a href="https://msdn.microsoft.com/library/windows/hardware/ff550776">MRxQuerySdInfo</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector query security descriptor information on a file system object. 

RDBSS issues a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550776">MRxQuerySdInfo</a> in response to receiving an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549298">IRP_MJ_QUERY_SECURITY</a> request. 

Before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550776">MRxQuerySdInfo</a>, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

The <b>QuerySecurity.SecurityInformation</b> member is set to <b>IrpSp-&gt;Parameters.QuerySecurity.SecurityInformation</b>.

The <b>Info.Buffer</b> member is set to user buffer from I/O request packet. This buffer has already been locked by RDBSS if needed.

The <b>Info.LengthRemaining</b> member is set to <b>IrpSp-&gt;Parameters.QuerySecurity.Length</b>.

On success, the network mini-redirector should set the <b>InformationToReturn</b> member of the RX_CONTEXT structure to the length of the security information returned. If the call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550776">MRxQuerySdInfo</a> was successful, RDBSS sets the <b>IoStatus.Information</b> member of the IRP to the <b>InformationToReturn</b> member of RX_CONTEXT. 

The<a href="https://msdn.microsoft.com/28e36992-2b6b-4484-9e7e-2cea7a2953e9"> MRxQueryVolumeInfo</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector query volume information. 

RDBSS issues a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550782">MRxQueryVolumeInfo</a> in either of the following cases:

<ul>
<li>
RDBSS receives an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549318">IRP_MJ_QUERY_VOLUME_INFORMATION</a> request.

</li>
<li>
RDBSS receives an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550751">IRP_MJ_FILE_SYSTEM_CONTROL</a> request for an FSCTL_LMR_GET_LINK_TRACKING_INFORMATION control code. 

</li>
</ul>
Before calling<a href="https://msdn.microsoft.com/28e36992-2b6b-4484-9e7e-2cea7a2953e9"> MRxQueryVolumeInfo</a> in the case of an IRP_MJ_QUERY_VOLUME_INFORMATION request, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

The <b>Info.FsInformationClass</b> member is set to <b>IrpSp-&gt;Parameters.QueryVolume.FsInformationClass</b>. 

The <b>Info.Buffer</b> member is set to <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.

The <b>Info.LengthRemaining</b> member is set to <b>IrpSp-&gt;Parameters.QueryVolume.Length</b>.

For an IRP_MJ_QUERY_VOLUME_INFORMATION request, if the <b>PostRequest</b> member of the RX_CONTEXT structure is <b>TRUE</b> on return from <a href="https://msdn.microsoft.com/library/windows/hardware/ff550782">MRxQueryVolumeInfo</a>, RDBSS will call <a href="..\rxprocs\nf-rxprocs-rxfsdpostrequest.md">RxFsdPostRequest</a> to post the request. For this case, the IRP_MJ_QUERY_VOLUME_INFORMATION request will pass the RX_CONTEXT structure to queue RX_CONTEXT to a worker queue for processing by the file system process (FSP). 

If the <b>PostRequest</b> member of the RX_CONTEXT structure is <b>FALSE</b> on return from <a href="https://msdn.microsoft.com/library/windows/hardware/ff550782">MRxQueryVolumeInfo</a>, the network mini-redirector must set the <b>Info.LengthRemaining</b> member of the RX_CONTEXT structure to the length of the volume information returned. RDBSS sets the <b>IoStatus.Information</b> member of the IRP to <b>IrpSp-&gt;Parameters.QueryVolume.Length</b> minus the <b>Info.LengthRemaining</b> member of the RX_CONTEXT structure. 

If the call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550782">MRxQueryVolumeInfo</a> is successful, the network mini-redirector should set the <b>Info.LengthRemaining</b> member of the RX_CONTEXT structure to the <b>Info.Length</b>  member minus the length of the volume information returned. If the call to <i>MRxQueryVolumeInfo</i> was successful, RDBSS sets the <b>IoStatus.Information</b> member of the IRP to <b>IrpSp-&gt;Parameters.QueryVolume.Length</b> minus the <b>Info.LengthRemaining</b> member of the RX_CONTEXT structure. 

For an IRP_MJ_QUERY_VOLUME_INFORMATION request with the <b>Info.FsInformationClass</b> member set to <b>FileFsDeviceInformation</b>, the network mini-redirector returns the following information in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

The<b> Info.Buffer</b> member contains an FILE_FS_DEVICE_INFORMATION structure

The<b> Info.Buffer.Characteristics</b> member is set to the characteristics of the volume, which must include FILE_REMOTE_DEVICE as one of the options.

The<b> Info.Buffer.DeviceType</b> member is set to the <b>DeviceType</b> member of the associated NET_ROOT structure. If the <b>Type</b> member of the associated NET_ROOT is NET_ROOT_PIPE, <b>Info.Buffer.DeviceType</b> member is set to FILE_DEVICE_NAMED_PIPE.

For an IRP_MJ_QUERY_VOLUME_INFORMATION request with the <b>Info.FsInformationClass</b> member set to <b>FileFsVolumeInformation</b>, the network mini-redirector returns the following information in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

The<b> Info.Buffer</b> member contains a FILE_FS_VOLUME_INFORMATION structure.

The<b> Info.Buffer</b> member is set to the <b>VolumeInfo</b> member of the associated NET_ROOT structure.

The <b>Info.LengthRemaining</b> member is set to the <b>VolumeInfoLength</b> member of the associated NET_ROOT structure.

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff550782">MRxQueryVolumeInfo</a> call from RDBSS for <a href="https://msdn.microsoft.com/library/windows/hardware/ff550751">IRP_MJ_FILE_SYSTEM_CONTROL</a> is a request for the link tracking information. Before calling<i> MRxQueryVolumeInfo</i> for IRP_MJ_FILE_SYSTEM_CONTROL, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

The <b>Info.FsInformationClass</b> member is set to<b> FileFsObjectIdInformation</b>. 

The <b>Info.Buffer</b> member is set to a FILE_FS_OBJECTID_INFORMATION structure.

The <b>Info.LengthRemaining</b> member is set to <b>sizeof</b>(FILE_FS_OBJECTID_INFORMATION).

For this case of an IRP_MJ_FILE_SYSTEM_CONTROL request, the <b>AssociatedIrp.SystemBuffer</b> member of the IRP points to a LINK_TRACKING_INFORMATION structure. 

If a request is initiated as an IRP_MJ_FILE_SYSTEM_CONTROL to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550782">MRxQueryVolumeInfo</a> with a return value of STATUS_SUCCESS or STATUS_BUFFER_OVERFLOW, RDBSS copies the <b>ObjectId</b> member of the FILE_FS_OBJECTID_INFORMATION structure passed in the <b>Info.Buffer</b> member of RX_CONTEXT structure to the <b>NetRoot-&gt;DiskParameters.VolumeId</b> member of the FCB structure and to the <b>AssociatedIrp.SystemBuffer.VolumeId</b> member of the IRP. If the call to <i>MRxQueryVolumeInfo</i> was successful, RDBSS sets the <b>Type</b> member of the LINK_TRACKING_INFORMATION structure. If the <b>NetRoot-&gt;Flags</b> member of the FCB structure has the NETROOT_FLAG_DFS_AWARE_NETROOT bit set, the <b>Type</b> member is set by RDBSS to <b>DfsLinkTrackingInformation</b>. If the <b>NetRoot-&gt;Flags</b> member of the FCB structure does not have the NETROOT_FLAG_DFS_AWARE_NETROOT bit set, the <b>Type</b> member is set by RDBSS to <b>NtfsLinkTrackingInformation</b>. On success, RDBSS sets the <b>IoStatus.Information</b> member of the IRP to the size of a LINK_TRACKING_INFORMATION structure. 

The<a href="https://msdn.microsoft.com/library/windows/hardware/ff550786">MRxSetEaInfo</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector set extended attribute information on a file system object. 

RDBSS issues a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550786">MRxSetEaInfo</a> in response to receiving an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549346">IRP_MJ_SET_EA</a> request.

Before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550786">MRxSetEaInfo</a>, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

The <b>Info.Buffer</b> member is set to the user buffer from I/O request packet. This buffer has already been locked by RDBSS if needed.

The <b>Info.LengthRemaining</b> member is set to <b>IrpSp-&gt;Parameters.QueryEa.Length</b>.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff550790">MRxSetFileInfo</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector set file information on a file system object. 

RDBSS issues a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550790">MRxSetFileInfo</a> in response to receiving an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549366">IRP_MJ_SET_INFORMATION</a> request.

Before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550790">MRxSetFileInfo</a>, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

The <b>Info.FileInformationClass</b> member is set to <b>IrpSp-&gt;Parameters.SetFile.FileInformationClass</b>, the specified FILE_INFORMATION_CLASS value.

The <b>Info.Buffer</b> member is set to <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.

The <b>Info.Length</b> member is set to <b>IrpSp-&gt;Parameters.SetFile.Length</b>.

The<a href="https://msdn.microsoft.com/099244ee-cc66-4500-9fee-a10238aaa66c"> MRxSetFileInfoAtCleanup</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector set file information on a file system object at cleanup.

RDBSS issues a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550796">MRxSetFileInfoAtCleanup</a> during cleanup, when the last handle to a file object is closed. This is different than the close operation which is invoked when the last reference to a file object is deleted. 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff550796">MRxSetFileInfoAtCleanup</a> is called by RDBSS if the timestamps on a file or the size of a file have changed. The calls to <i>MRxSetFileInfoAtCleanup</i> by RDBSS are made separately for each of these changes. If both the file size and the timestamps have changed, then RDBSS makes two calls to <i>MRxSetFileInfoAtCleanup</i>. 

Before calling<a href="https://msdn.microsoft.com/099244ee-cc66-4500-9fee-a10238aaa66c"> MRxSetFileInfoAtCleanup</a>, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter if the timestamps on a file have changed:

The <b>Info.FileInformationClass</b> member is set to a FILE_INFORMATION_CLASS value of FileBasicInformation. 

The <b>Info.Buffer</b> member is set to a FILE_BASIC_INFORMATION structure allocated on the stack.

The <b>Info.Length</b> member is set to the sizeof a FILE_BASIC_INFORMATION structure.

Before calling<a href="https://msdn.microsoft.com/099244ee-cc66-4500-9fee-a10238aaa66c"> MRxSetFileInfoAtCleanup</a>, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter if the size of a file has changed:

The <b>Info.FileInformationClass</b> member is set to a FILE_INFORMATION_CLASS value of FileEndOfFileInformation.

The <b>Info.Buffer</b> member is set to a FILE_END_OF_FILE_INFORMATION structure allocated on the stack.

The <b>Info.Length</b> member is set to <b>sizeof(</b>FILE_END_OF_FILE_INFORMATION<b>)</b>.

RDBSS ignores the return value from <a href="https://msdn.microsoft.com/library/windows/hardware/ff550796">MRxSetFileInfoAtCleanup</a>. 

A network mini-redirector can choose to do nothing in this routine and return STATUS_SUCCESS. Any changes to the file size or timestamps will be handled during the cleanup operation. 

The<a href="https://msdn.microsoft.com/library/windows/hardware/ff550800">MRxSetQuotaInfo</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector set quota information on a file system object. 

RDBSS issues a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550800">MRxSetQuotaInfo</a> in response to receiving an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549401">IRP_MJ_SET_QUOTA</a> request. 

Before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550800">MRxSetQuotaInfo</a>, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

The <i>Info.Buffer</i> member is set to the user buffer from I/O request packet. This buffer has already been locked by RDBSS if needed.

The <b>Info.LengthRemaining</b> member is set to <b>IrpSp-&gt;Parameters.SetQuota.Length</b>. 

The<a href="https://msdn.microsoft.com/library/windows/hardware/ff550805">MRxSetSdInfo</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector set security descriptor information on a file system object. 

RDBSS issues a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550805">MRxSetSdInfo</a> in response to receiving an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549407">IRP_MJ_SET_SECURITY</a> request. 

Before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550805">MRxSetSdInfo</a>, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

The <b>SetSecurity.SecurityInformation</b> member is set to <b>IrpSp-&gt;Parameters.SetSecurity.SecurityInformation</b>.

The <b>SetSecurity.SecurityDescriptor</b> member is set to <b>IrpSp-&gt;Parameters.SetSecurity.SecurityDescriptor</b>.

The<a href="https://msdn.microsoft.com/library/windows/hardware/ff550810">MRxSetVolumeInfo</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector set volume information. 

RDBSS issues a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550810">MRxSetVolumeInfo</a> in response to receiving an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549415">IRP_MJ_SET_VOLUME_INFORMATION</a> request. 

Before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550810">MRxSetVolumeInfo</a>, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

The <b>Info.FsInformationClass</b> member is set to <b>IrpSp-&gt;Parameters.SetVolume.FsInformationClass</b>. 

The <b>Info.Buffer</b> member is set to <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.

The <b>Info.LengthRemaining</b> member is set to <b>IrpSp-&gt;Parameters.SetVolume.Length</b>.

The<a href="https://msdn.microsoft.com/a68755c1-73f5-4134-b506-2a0163637a13"> MRxShouldTryToCollapseThisOpen</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector indicate if RDBSS should try and collapse an open request onto an existing file system object.


<a href="https://msdn.microsoft.com/library/windows/hardware/ff550817">MRxShouldTryToCollapseThisOpen</a> is called to determine if an open request should not be collapsed. 

Before calling<a href="https://msdn.microsoft.com/a68755c1-73f5-4134-b506-2a0163637a13"> MRxShouldTryToCollapseThisOpen</a>, RDBSS modifies the following member in the RX_CONTEXT structure pointed to by the <i>RxContext</i> parameter:

The <b>pRelevantSrvOpen</b> member is set to the SRV_OPEN. 

The call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550817">MRxShouldTryToCollapseThisOpen</a> could be a change notify request for a directory. Therefore, the network mini-redirector might not allow collapsing open requests so that change notification works correctly. 

RDBSS disallows collapsing opens if the <b>Create.NtCreateParameters.CreateOptions</b> member of the RX_CONTEXT structure has the FILE_OPEN_FOR_BACKUP_INTENT option or the FILE_DELETE_ON_CLOSE option set. 

The<a href="https://msdn.microsoft.com/d60ec8ef-2ccf-42ad-97d2-1aaf9d60acfb"> MRxTruncate</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector truncate the contents of a file system object. 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff550839">MRxTruncate</a> is called as part of cleanup operations if both of the following conditions are true: 

<ul>
<li>
The file object corresponds to a disk file or directory

</li>
<li>
This is the last cleanup call and the file object was marked for truncation. 

</li>
</ul>
The file object is marked for truncation if the <b>fcbstate</b> member of the FCB structure has the FCB_STATE_TRUNCATE_ON_CLOSE bit set. RDBSS will uninitialize the cache map at some later time.

A call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550839">MRxTruncate</a> will be followed by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549841">MRxCleanupFobx</a> as part of the cleanup operation.

RDBSS ignores the return value from <a href="https://msdn.microsoft.com/library/windows/hardware/ff550839">MRxTruncate</a>. 

The<a href="https://msdn.microsoft.com/d4a7c201-3c7d-40e9-a7da-17f40862c258"> MRxZeroExtend</a> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that a network mini-redirector truncate the contents of a file system object. 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff550844">MRxZeroExtend</a> is called as part of cleanup operations if the file object was not marked for deletion and the file object is not a paging file. <i>MRxZeroExtend</i> is called to ensure that the portion between the valid data length and the file size is zero-extended. After calling <i>MRxZeroExtend</i>, RDBSS sets the <b>Header.ValidDataLength.QuadPart</b> member of the structure of an FCB structure equal to the <b>Header.FileSize.QuadPart</b> member of the FCB structure.

A call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550844">MRxZeroExtend</a> will be followed by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549841">MRxCleanupFobx</a> as part of the cleanup operation.

RDBSS ignores the return value from <a href="https://msdn.microsoft.com/library/windows/hardware/ff550844">MRxZeroExtend</a>. 

The MRxCleanupFobx routine is called by RDBSS to request the network mini-redirector to close a file system object extension. RDBSS issues this call in response to receiving an IRP_MJ_CLEANUP request on a file object.

MRxCleanupFobx is called by RDBSS as part of cleanup and close operations on a file object. 

MRxCleanupFobx cannot return a value of STATUS_RETRY indicating that the call should be retried. If a retry loop is necessary, it must be handled internally in the MRxCleanupFobx routine by the network mini-redirector.





## -see-also

<a href="..\mrx\nc-mrx-pmrx_deallocate_for_fcb.md">MRxDeallocateForFcb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550844">MRxZeroExtend</a>



<a href="..\mrx\nc-mrx-pmrx_chkfcb_calldown.md">MRxAreFilesAliased</a>



<a href="..\mrx\nc-mrx-pmrx_forceclosed_calldown.md">MRxForceClosed</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550817">MRxShouldTryToCollapseThisOpen</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549879">MRxExtendForNonCache</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549862">MRxCreate</a>



<a href="..\mrx\nc-mrx-pmrx_deallocate_for_fobx.md">MRxDeallocateForFobx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550669">MRxFlush</a>



<a href="..\mrx\nc-mrx-pmrx_is_lock_realizable.md">MRxIsLockRealizable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549841">MRxCleanupFobx</a>



<a href="..\mrx\nc-mrx-pmrx_extendfile_calldown.md">MRxExtendForCache</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550839">MRxTruncate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549847">MRxCollapseOpen</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PMRX_CALLDOWN routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

