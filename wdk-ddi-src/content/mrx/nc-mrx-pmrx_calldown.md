---
UID: NC:mrx.PMRX_CALLDOWN
title: PMRX_CALLDOWN (mrx.h)
description: Learn more about the PMRX_CALLDOWN callback function.
tech.root: ifsk
ms.date: 10/11/2023
keywords: ["PMRX_CALLDOWN callback function"]
ms.keywords: MRxCleanupFobx, MRxCloseSrvOpen, MRxCollapseOpen, MRxCreate, MRxDevFcbXXXControlFile, MRxFlush, MRxLowIOSubmit[LOWIO_OP_EXCLUSIVELOCK], MRxLowIOSubmit[LOWIO_OP_FSCTL], MRxLowIOSubmit[LOWIO_OP_IOCTL], MRxLowIOSubmit[LOWIO_OP_NOTIFY_CHANGE_DIRECTORY], MRxLowIOSubmit[LOWIO_OP_READ], MRxLowIOSubmit[LOWIO_OP_SHAREDLOCK], MRxLowIOSubmit[LOWIO_OP_UNLOCK], MRxLowIOSubmit[LOWIO_OP_UNLOCK_MULTIPLE], MRxLowIOSubmit[LOWIO_OP_WRITE], MRxQueryDirectory, MRxQueryEaInfo, MRxQueryFileInfo, MRxQueryQuotaInfo, MRxQuerySdInfo, MRxQueryVolumeInfo, MRxSetEaInfo, MRxSetFileInfo, MRxSetFileInfoAtCleanup, MRxSetQuotaInfo, MRxSetSdInfo, MRxSetVolumeInfo, MRxShouldTryToCollapseThisOpen, MRxTruncate, MRxZeroExtend, MyCalldown, MyCalldown routine [Installable File System Drivers], PMRX_CALLDOWN, ifsk.mrxclosesrvopen, mrx/MyCalldown, mrxref_e6b5df78-d201-4f9e-9422-089772c04674.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PMRX_CALLDOWN
 - mrx/PMRX_CALLDOWN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - mrx.h
api_name:
 - PMRX_CALLDOWN
---

# PMRX_CALLDOWN callback function

## -description

This callback is called by RDBSS to request that the network mini-redirector perform an action based in the supplied IRP.

## -parameters

### -param RxContext [in, out]

A pointer to the RX_CONTEXT structure. This parameter contains the IRP that is requesting the operation.

## -returns

This callback returns STATUS_SUCCESS on success or an appropriate NTSTATUS value, such as the following:

| Return code | Description |
| ------------- | ------------- |
| STATUS_ACCESS_DENIED | A request was made to stop or start the network mini-redirector, but the caller lacked the proper security for this operation.  |
| STATUS_BUFFER_OVERFLOW | The buffer to receive the extended attribute information was too small. This return value should be considered success and as much valid data as possible should be returned in the **Info.Buffer** member of the RX_CONTEXT structure pointed to by the **RxContext** parameter. |
| STATUS_BUFFER_TOO_SMALL | The buffer is too small to receive the requested data. If this value is returned, the **InformationToReturn** member of the RX_CONTEXT structure pointed to by the **RxContext** parameter should be set to the minimum size of the expected buffer for the call to succeed. |
| STATUS_CONNECTION_DISCONNECTED | The connection was disconnected.  |
| STATUS_EA_CORRUPT_ERROR | Invalid extended attribute information was received from the remote server.  |
| STATUS_EA_TOO_LARGE | The extended attribute information that is passed is larger than the size that is supported by the remote share.  |
| STATUS_FILE_CLOSED | The FCB structure was acquired, but the associated SRV_OPEN structure has been closed.  |
| STATUS_INSUFFICIENT_RESOURCES | There were insufficient resources to complete the operation.  |
| STATUS_INTERNAL_ERROR | An internal error occurred in the network mini-redirector.  |
| STATUS_INVALID_BUFFER_SIZE | The requested buffer size was too large.  |
| STATUS_INVALID_DEVICE_REQUEST | An invalid device request was sent to the network mini-redirector. |
| STATUS_INVALID_NETWORK_RESPONSE | An invalid response was received from the remote server.  |
| STATUS_INVALID_PARAMETER | An invalid parameter was specified in **RxContext**.  |
| STATUS_LINK_FAILED | The attempt to reconnect to a remote server to complete the request failed.  |
| STATUS_MORE_PROCESSING_REQUIRED | A network mini-redirector returns this value to disable collapsing of this open request.  |
| STATUS_NETWORK_ACCESS_DENIED | Network access was denied. This error can be returned if the network mini-redirector was asked to open a new file on a read-only share.  |
| STATUS_NETWORK_NAME_DELETED | A network name was deleted.  |
| STATUS_NONEXISTENT_EA_ENTRY | There are no extended attributes on the file object and the user supplied an extended attribute index.  |
| STATUS_NOT_IMPLEMENTED | A feature that is requested, such as remote boot or a remote page file, is not implemented.  |
| STATUS_NOT_SUPPORTED | A feature that is requested, such as extended attributes, is not supported.  |
| STATUS_OBJECT_NAME_COLLISION | The network mini-redirector was asked to create a file that already exists.  |
| STATUS_OBJECT_NAME_NOT_FOUND | The object name was not found. This error can be returned if the network mini-redirector was asked to open a file that doesn't exist.  |
| STATUS_OBJECT_PATH_NOT_FOUND | The object path was not found. This error can be returned if an NTFS stream object was requested and the remote file system does not support streams.  |
| STATUS_ONLY_IF_CONNECTED | The SRV_OPEN structure is not connected.  |
| STATUS_REDIRECTOR_HAS_OPEN_HANDLES | This was a request to stop the network mini-redirector, but the redirector has open handles that prevent it from stopping at this time. |
| STATUS_REDIRECTOR_NOT_STARTED | This was a request to stop the network mini-redirector, but the redirector was not started. |
| STATUS_REDIRECTOR_STARTED | This was a request to start the network mini-redirector, but the redirector was already started.  |
| STATUS_REPARSE | A reparse is required to handle a symbolic link.  |
| STATUS_REQUEST_ABORTED | The network request was aborted. |
| STATUS_RETRY | The operation should be retried. This error can be returned if the network mini-redirector encountered a sharing violation or an access denied error.  |
| STATUS_SHARING_VIOLATION | A sharing violation occurred.  |
| STATUS_UNSUCCESSFUL | The call was unsuccessful. |

## -remarks

The **MRxCloseSrvOpen** routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that the network mini-redirector close an SRV_OPEN structure.

**MRxCloseSrvOpen** is called by RDBSS as part of cleanup and close operations on a file object. It is assumed that the network mini-redirector will close a file across the network.

Before calling **MRxCloseSrvOpen**, RDBSS modifies the following members in the RX_CONTEXT structure, pointed to by the **RxContext** parameter:

**MajorFunction** is set to IRP_MJ_CLOSE

**pFcb** is set to the FCB structure for which close processing is to be initiated

**pFobx** is set to the FOBX structure for which close processing is to be initiated

RDBSS and a network mini-redirector do not necessarily close the SRV_OPEN structures when the user closes a file. To improve performance in some cases, a network mini-redirector may try to reuse the SRV_OPEN and the cached data without any contact with the server. Some Microsoft Windows applications exhibit behavior that opens, reads, and closes a file and then quickly reopens the same file. In these cases, reusing the SRV_OPEN structures can improve performance.

RDBSS calls **MRxCloseSrvOpen** for delayed close processing while scavenging an FOBX structure. This happens when the close processing was delayed in anticipation of an open request and no open requests were forthcoming.

**MRxCloseSrvOpen** cannot return a value of STATUS_RETRY indicating that the call should be retried. If a retry loop is necessary, it must be handled internally in the **MRxCloseSrvOpen** routine by the network mini-redirector.

The [**MRxCollapseOpen**](/windows-hardware/drivers/ifs/mrxcollapseopen) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that the network mini-redirector collapse an open file system request onto an existing SRV_OPEN structure.

[**MRxCollapseOpen**](/windows-hardware/drivers/ifs/mrxcollapseopen) is called by RDBSS to collapse an SRV_OPEN structure locally. The network mini-redirector is consulted to determine if a collapse is possible so there is no reason to call the network mini-redirector twice. If the network mini-redirector decides to collapse the SRV_OPEN structure, then it will do so and pass back a returnable status. A return value of STATUS_SUCCESS is a terminating return value. A different return value, for example, STATUS_MORE_PROCESSING_REQUIRED, is considered a non-terminating return value.

Before calling [**MRxCollapseOpen**](/windows-hardware/drivers/ifs/mrxcollapseopen), RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

**pRelevantSrvOpen** is set to the SRV_OPEN structure to collapse.

**Create.pSrvCall** is set to the SRV_CALL structure associated with the SRV_OPEN.

If the network mini-redirector decides to collapse the SRV_OPEN structure, then the **SrvOpen** member of the RX_CONTEXT structure must be set to the collapsed SRV_OPEN structure.

The[**MRxCreate**](/windows-hardware/drivers/ifs/mrxcreate) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that the network mini-redirector create a file system object.

[**MRxCreate**](/windows-hardware/drivers/ifs/mrxcreate) is called by RDBSS to request that the network mini-redirector open a file system object across the network. This call is issued by RDBSS in response to receiving an [**IRP_MJ_CREATE**](/windows-hardware/drivers/ifs/irp-mj-create) request.

Before calling [**MRxCreate**](/windows-hardware/drivers/ifs/mrxcreate), RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

**pRelevantSrvOpen** is set to the SRV_OPEN structure.

**Create.pSrvCall** is set to the SRV_CALL structure.

**Create.NtCreateParameters** is set to the requested NT_CREATE_PARAMETERS.

In the context of a network mini-redirector, a file object refers to the associated file control block (FCB) and file object extension (FOBX) structures. There is a one to one correspondence between file objects and FOBXs. Many file objects will refer to the same FCB, which represents a single file on a remote server. A client can have several different open requests (NtCreateFile requests) on the same FCB and each of these will create a new file object. RDBSS and network mini-redirectors can choose to send fewer [**MRxCreate**](/windows-hardware/drivers/ifs/mrxcreate) requests than the NtCreateFile requests received, in effect sharing an SRV_OPEN structure among several FOBXs.

If the [**MRxCreate**](/windows-hardware/drivers/ifs/mrxcreate) request was for a file overwrite and **MRxCreate** returned STATUS_SUCCESS, then RDBSS will acquire the paging I/O resource and truncate the file. If the file is being cached by cache manager, RDBSS will update the sizes the cache manager has with the ones just received from the server.

Before returning,[**MRxCreate**](/windows-hardware/drivers/ifs/mrxcreate) must set the **CurrentIrp->IoStatus.Information** member of the RX_CONTEXT structure pointed to by the **RxContext** parameter.

The [**MRxDevFcbXXXControlFile**](/windows-hardware/drivers/ifs/mrxdevfcbxxxcontrolfile) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to pass a device FCB control request (an IOCTL or FSCTL request) to the network mini-redirector.

[**MRxDevFcbXXXControlFile**](/windows-hardware/drivers/ifs/mrxdevfcbxxxcontrolfile) handles IOCTL and FSCTL requests related to the device FCB that are sent to the network mini-redirector.

Before calling [**MRxDevFcbXXXControlFile**](/windows-hardware/drivers/ifs/mrxdevfcbxxxcontrolfile), RDBSS modifies the following member in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

**MajorFunction** is set to the major function of the IRP

If this was an IRP_MJ_FILE_SYSTEM_CONTROL request, then RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

**LowIoContext.ParamsFor.FsCtl.MinorFunction** is set to the minor function code for the FSCTL code

**LowIoContext.ParamsFor.FsCtl.FsControlCode** is set to the FSCTL code for the IRP

If this was an IRP_MJ_DEVICE_CONTROL or IRP_MJ_INTERNAL_DEVICE_CONTROL request, then RDBSS modifies the following member in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

**LowIoContext.ParamsFor.FsCtl.FsControlCode** is set to the control code for the IRP.

If [**MRxDevFcbXXXControlFile**](/windows-hardware/drivers/ifs/mrxdevfcbxxxcontrolfile) returns STATUS_SUCCESS, then the routine was successful. Any other return value indicates that an error occurred.

The [**MRxFlush**](/windows-hardware/drivers/ifs/mrxflush) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector write the contents of a file system object to storage. RDBSS issues this call in response to receiving an [**IRP_MJ_FLUSH_BUFFERS**](/windows-hardware/drivers/ifs/irp-mj-flush-buffers) request.

[**MRxFlush**](/windows-hardware/drivers/ifs/mrxflush) handles network requests for file flush.

The [**MRxLowIOSubmit[LOWIO_OP_EXCLUSIVELOCK]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-exclusivelock-) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector open an exclusive lock on a file object.

RDBSS calls [**MRxLowIOSubmit[LOWIO_OP_EXCLUSIVELOCK]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-exclusivelock-) in response to receiving an [**IRP_MJ_LOCK_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-lock-control) request with a minor code of IRP_MN_LOCK if **IrpSp->Flags** has the SL_EXCLUSIVE_LOCK bit set.

Before calling [**MRxLowIOSubmit[LOWIO_OP_EXCLUSIVELOCK]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-exclusivelock-), RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

The **LowIoContext.Operation** member is set to LOWIO_OP_EXCLUSIVELOCK.

The **LowIoContext.ResourceThreadId** member is set to the thread of the process that initiated the operation in RDBSS.

The **LowIoContext.ParamsFor.Locks.ByteOffset** member is set to the value of **IrpSp->Parameters.LockControl.ByteOffset.QuadPart**.

The **LowIoContext.ParamsFor.Locks.Key** member is set to the value of **IrpSp->Parameters.LockControl.Key**.

The **LowIoContext.ParamsFor.Locks.Flags** member is set to the value of **IrpSp->Flags**.

The **LowIoContext.ParamsFor.Locks.Length** member is set to the value of **IrpSp->Parameters.LockControl.Length.QuadPart**.

The **LowIoContext.Operation** member of the RX_CONTEXT structure specifies the low I/O operation to perform. It is possible for several of the low I/O routines to point to the same routine in a network mini-redirector because this **LowIoContext.Operation** member can be used to differentiate the low I/O operation that is requested. For example, all the I/O calls related to file locks could call the same low I/O routine in the network mini-redirector and that routine could use the **LowIoContext.Operation** member to differentiate between the lock and unlock operation that is requested.

If the [**MRxLowIOSubmit[LOWIO_OP_EXCLUSIVELOCK]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-exclusivelock-) routine can take a long time to complete, the network mini-redirector driver should release the FCB structure before initiating the network communication. The FCB structure can be released by calling [**RxReleaseFcbResourceForThreadInMRx**](../mrxfcb/nf-mrxfcb-rxreleasefcbresourceforthreadinmrx.md). While the **MRxLowIOSubmit[LOWIO_OP_EXCLUSIVELOCK]** routine is processing, the **LowIoContext.ResourceThreadId** member of RX_CONTEXT is guaranteed to indicate the thread of the process that initiated the operation in RDBSS.

The **LowIoContext.ResourceThreadId** member of RX_CONTEXT can be used to release the FCB structure on behalf of another thread. When an asynchronous routine completes, the FCB structure that was acquired from the initial thread can be released.

The [**MRxLowIOSubmit[LOWIO_OP_FSCTL]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-fsctl-) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector issue file system control request on remote file.

RDBSS calls [**MRxLowIOSubmit[LOWIO_OP_FSCTL]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-fsctl-) in response to receiving an [**IRP_MJ_FILE_SYSTEM_CONTROL**](/windows-hardware/drivers/kernel/irp-mj-file-system-control) request.

Before calling [**MRxLowIOSubmit[LOWIO_OP_FSCTL]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-fsctl-), RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

The **LowIoContext.Operation** member is set to LOWIO_OP_FSCTL.

The **LowIoContext.ResourceThreadId** member is set to the thread of the process that initiated the operation in RDBSS.

The **LowIoContext.ParamsFor.FsCtl.FsControlCode** member is set to the FSCTL major control code.

The **LowIoContext.ParamsFor.FsCtl.MinorFunction** member is set to the FSCTL minor control code.

The **LowIoContext.ParamsFor.FsCtl.pInputBuffer** member is set to the input buffer.

The **LowIoContext.ParamsFor.FsCtl.InputBufferLength** member is set to the input buffer length.

The **LowIoContext.ParamsFor.FsCtl.pOutputBuffer** member is set to the output buffer.

The **LowIoContext.ParamsFor.FsCtl.OutputBufferLength** member is set to the output buffer length.

The file system control code (FSCTL) requests handled by a network mini-redirector can be classified into one of several categories:

* FSCTLs that are implemented and used by RDBSS and the network mini redirector

* FSCTLs that are implemented and used only by the network mini-redirector

* FSCTLs which should never be seen by the network mini-redirector. These FSCTLs are solely intended as a debugging aid.

While the [**MRxLowIOSubmit[LOWIO_OP_FSCTL]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-fsctl-) routine is processing, the **LowIoContext.ResourceThreadId** member of RX_CONTEXT is guaranteed to indicate the thread of the process that initiated the operation in RDBSS. The **LowIoContext.ResourceThreadId** member of RX_CONTEXT can be used to release the input resource on behalf of another thread. When an asynchronous routine completes, the input resource that was acquired from the initial thread can be released.

The [**MRxLowIOSubmit[LOWIO_OP_IOCTL]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-ioctl-) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to issue an I/O system control request to the network mini-redirector.

RDBSS calls [**MRxLowIOSubmit[LOWIO_OP_IOCTL]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-ioctl-) in response to receiving an [**IRP_MJ_DEVICE_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-device-control) or [**IRP_MJ_INTERNAL_DEVICE_CONTROL**](/windows-hardware/drivers/kernel/irp-mj-internal-device-control) requests.

Before calling [**MRxLowIOSubmit[LOWIO_OP_IOCTL]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-ioctl-), RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

The **LowIoContext.Operation** member is set to LOWIO_OP_IOCTL.

The **LowIoContext.ResourceThreadId** member is set to the thread of the process that initiated the operation in RDBSS.

The **LowIoContext.ParamsFor.IoCtl.IoControlCode** member is set to the IOCTL control code.

The **LowIoContext.ParamsFor.IoCtl.pInputBuffer** member is set to the input buffer.

The **LowIoContext.ParamsFor.IoCtl.InputBufferLength** member is set to the input buffer length.

The **LowIoContext.ParamsFor.IoCtl.pOutputBuffer** member is set to the output buffer.

The **LowIoContext.ParamsFor.IoCtl.OutputBufferLength** member is set to the output buffer length.

While the [**MRxLowIOSubmit[LOWIO_OP_IOCTL]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-ioctl-) routine is processing, the **LowIoContext.ResourceThreadId** member of RX_CONTEXT is guaranteed to indicate the thread of the process that initiated the operation in RDBSS. The **LowIoContext.ResourceThreadId** member of RX_CONTEXT can be used to release the input resource on behalf of another thread. When an asynchronous routine completes, the input resource that was acquired from the initial thread can be released.

The [**MRxLowIOSubmit[LOWIO_OP_NOTIFY_CHANGE_DIRECTORY]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-notify-change-directory-) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to issue a request to the network mini-redirector for a directory change notification operation.

RDBSS calls [**MRxLowIOSubmit[LOWIO_OP_NOTIFY_CHANGE_DIRECTORY]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-notify-change-directory-) in response to receiving an [**IRP_MJ_DIRECTORY_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-directory-control) request.

Before calling [**MRxLowIOSubmit[LOWIO_OP_NOTIFY_CHANGE_DIRECTORY]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-notify-change-directory-), RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

The **LowIoContext.Operation** member is set to LOWIO_OP_NOTIFY_CHANGE_DIRECTORY.

The **LowIoContext.ResourceThreadId** member is set to the thread of the process that initiated the operation in RDBSS.

The **LowIoContext.ParamsFor.NotifyChangeDirectory.WatchTree** member is set to **TRUE** if the **IrpSp->Flags** has the SL_WATCH_TREE bit set.

The **LowIoContext.ParamsFor.NotifyChangeDirectory.CompletionFilter** member is set to the value of **IrpSp->Parameters.NotifyDirectory.CompletionFilter**.

The **LowIoContext.ParamsFor.NotifyChangeDirectory.NotificationBufferLength** member is set to the value of **IrpSp->Parameters.NotifyDirectory.Length**.

The **LowIoContext.ParamsFor.NotifyChangeDirectory.pNotificationBuffer** member is set to the value returned by calling **MmGetSystemAddressForMdlSafe** passing in the **Irp->MdlAddress** and NormalPagePriority. The user buffer also is probed and locked for write access.

A directory change notification operation is normally implemented by a network mini-redirector as an asynchronous operation because it can take considerable time. The operation usually consists of sending a network request to the remote server requesting change notification. The response is obtained when the desired change is affected on the server. This is an example of an operation for which the network mini-redirector may need to register a unique context value for handling cancellations initiated locally.

While the [**MRxLowIOSubmit[LOWIO_OP_NOTIFY_CHANGE_DIRECTORY]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-notify-change-directory-) routine is processing, the **LowIoContext.ResourceThreadId** member of RX_CONTEXT is guaranteed to indicate the thread of the process that initiated the operation in RDBSS. The **LowIoContext.ResourceThreadId** member can be used to release the FCB structure on behalf of another thread. When an asynchronous routine completes, the FCB structure that was acquired from the initial thread can be released. The FCB structure can be released by calling [**RxReleaseFcbResourceForThreadInMRx**](../mrxfcb/nf-mrxfcb-rxreleasefcbresourceforthreadinmrx.md).

The [**MRxLowIOSubmit[LOWIO_OP_READ]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-read-) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to issue a read request to the network mini-redirector.

RDBSS calls [**MRxLowIOSubmit[LOWIO_OP_READ]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-read-) in response to receiving an [**IRP_MJ_READ**](/windows-hardware/drivers/ifs/irp-mj-read) request.

Before calling [**MRxLowIOSubmit[LOWIO_OP_READ]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-read-), RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

The **LowIoContext.Operation** member is set to LOWIO_OP_READ.

The **LowIoContext.ResourceThreadId** member is set to the thread of the process that initiated the operation in RDBSS.

The **LowIoContext.ParamsFor.ReadWrite.Key** member is set to the value of **IrpSp->Parameters.Read.Key**.

The **ParamsFor.ReadWrite.Flags** member has the LOWIO_READWRITEFLAG_PAGING_IO bit is set on if **Irp->Flags** has the IRP_PAGING_IO bit on.

The **ParamsFor.ReadWrite.Buffer** member is set to the user buffer locked for IoReadAccess.

The **LowIoContext.ParamsFor.ReadWrite.ByteCount** member is set to the value of IrpSp->Parameters.Read.Length.

A read request is normally implemented by a network mini-redirector as an asynchronous operation because it can take considerable time. The operation usually consists of sending a network request to the remote server. The response is obtained when the read request is completed on the server. This is an example of an operation for which the network mini-redirector may need to register a context for handling cancellations initiated locally.

While the [**MRxLowIOSubmit[LOWIO_OP_READ]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-read-) routine is processing, the **LowIoContext.ResourceThreadId** member of RX_CONTEXT is guaranteed to indicate the thread of the process that initiated the operation in RDBSS. The **LowIoContext.ResourceThreadId** member can be used to release the FCB structure on behalf of another thread. When an asynchronous routine completes, the FCB structure that was acquired from the initial thread can be released. The FCB structure can be released by calling [**RxReleaseFcbResourceForThreadInMRx**](../mrxfcb/nf-mrxfcb-rxreleasefcbresourceforthreadinmrx.md).

The [**MRxLowIOSubmit[LOWIO_OP_SHAREDLOCK]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-sharedlock-) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network redirector open a shared lock on a file object.

RDBSS calls [**MRxLowIOSubmit[LOWIO_OP_SHAREDLOCK]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-sharedlock-) in response to receiving an [**IRP_MJ_LOCK_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-lock-control) request with a minor code of IRP_MN_LOCK if **IrpSp->Flags** does not have the SL_EXCLUSIVE_LOCK bit set.

Before calling [**MRxLowIOSubmit[LOWIO_OP_SHAREDLOCK]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-sharedlock-), RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

The **LowIoContext.Operation** member is set to LOWIO_OP_SHAREDLOCK.

The **LowIoContext.ResourceThreadId** member is set to the thread of the process that initiated the operation in RDBSS.

The **LowIoContext.ParamsFor.Locks.ByteOffset** member is set to the value of **IrpSp->Parameters.LockControl.ByteOffset.QuadPart**.

The **LowIoContext.ParamsFor.Locks.Key** member is set to the value of **IrpSp->Parameters.LockControl.Key**.

The **LowIoContext.ParamsFor.Locks.Flags** member is set to the value of **IrpSp->Flags**.

The **LowIoContext.ParamsFor.Locks.Length** member is set to the value of **IrpSp->Parameters.LockControl.Length.QuadPart**.

The **LowIoContext.Operation** member of the RX_CONTEXT structure specifies the low I/O operation to perform. It is possible for several of the low I/O routines to point to the same routine in a network mini-redirector because the **LowIoContext.Operation** member can be used to differentiate the low I/O operation that is requested. For example, all the I/O calls related to file locks could call the same low I/O routine in the network mini-redirector and this routine could use the **LowIoContext.Operation** member to differentiate between the lock and unlock operation that is requested.

If the [**MRxLowIOSubmit[LOWIO_OP_SHAREDLOCK]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-sharedlock-) routine can take a long time to complete, the network mini-redirector driver should release the FCB structure before initiating the network communication. The FCB structure can be released by calling [**RxReleaseFcbResourceForThreadInMRx**](../mrxfcb/nf-mrxfcb-rxreleasefcbresourceforthreadinmrx.md). While the **MRxLowIOSubmit[LOWIO_OP_SHAREDLOCK]** routine is processing, the **LowIoContext.ResourceThreadId** member of RX_CONTEXT is guaranteed to indicate the thread of the process that initiated the operation in RDBSS.

The **LowIoContext.ResourceThreadId** member of the RX_CONTEXT structure can be used to release the FCB structure on behalf of another thread. When an asynchronous routine completes, the FCB structure that was acquired from the initial thread can be released.

The [**MRxLowIOSubmit[LOWIO_OP_UNLOCK]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-unlock-) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector remove a single lock on a file object.

RDBSS calls [**MRxLowIOSubmit[LOWIO_OP_UNLOCK]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-unlock-) in response to receiving an [**IRP_MJ_LOCK_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-lock-control) request with a minor code of IRP_MN_UNLOCK_SINGLE.

Before calling [**MRxLowIOSubmit[LOWIO_OP_UNLOCK]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-unlock-), RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

The **LowIoContext.Operation** member is set to LOWIO_OP_UNLOCK.

The **LowIoContext.ResourceThreadId** member is set to the thread of the process that initiated the operation in RDBSS.

The **LowIoContext.ParamsFor.Locks.ByteOffset** member is set to the value of **IrpSp->Parameters.LockControl.ByteOffset.QuadPart**.

The **LowIoContext.ParamsFor.Locks.Key** member is set to the value of **IrpSp->Parameters.LockControl.Key**.

The **LowIoContext.ParamsFor.Locks.Length** member is set to the value of **IrpSp->Parameters.LockControl.Length.QuadPart**.

The **LowIoContext.Operation** member of the RX_CONTEXT structure specifies the low I/O operation to perform. It is possible for several of the low I/O routines to point to the same routine in a network mini-redirector because this **LowIoContext.Operation** member can be used to differentiate the low I/O operation that is requested. For example, all the I/O calls related to file locks could call the same low I/O routine in the network mini-redirector and this routine could use the **LowIoContext.Operation** member to differentiate between the lock and unlock operation that is requested.

If the [**MRxLowIOSubmit[LOWIO_OP_UNLOCK]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-unlock-) routine can take a long time to complete, the network mini-redirector driver should release the FCB structure before initiating the network communication. The FCB structure can be released by calling [**RxReleaseFcbResourceForThreadInMRx**](../mrxfcb/nf-mrxfcb-rxreleasefcbresourceforthreadinmrx.md). While the **MRxLowIOSubmit[LOWIO_OP_UNLOCK]** routine is processing, the **LowIoContext.ResourceThreadId** member of RX_CONTEXT is guaranteed to indicate the thread of the process that initiated the operation in RDBSS.

The **LowIoContext.ResourceThreadId** member of RX_CONTEXT can be used to release the FCB structure on behalf of another thread. When an asynchronous routine completes, the FCB structure that was acquired from the initial thread can be released.

The [**MRxLowIOSubmit[LOWIO_OP_UNLOCK_MULTIPLE]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-unlock-multiple-) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that the network mini-redirector remove multiple locks held on a file object.

RDBSS calls [**MRxLowIOSubmit[LOWIO_OP_UNLOCK_MULTIPLE]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-unlock-multiple-) in response to receiving an [**IRP_MJ_LOCK_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-lock-control) request with a minor code of IRP_MN_UNLOCK_ALL or IRP_MN_UNLOCK_ALL_BY_KEY.

Before calling [**MRxLowIOSubmit[LOWIO_OP_UNLOCK_MULTIPLE]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-unlock-multiple-), RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

The **LowIoContext.Operation** member is set to LOWIO_OP_UNLOCK_MULTIPLE.

The **LowIoContext.ResourceThreadId** member is set to the thread of the process that initiated the operation in RDBSS.

The **LowIoContext.ParamsFor.Locks.LockList** member is set to a list of LOWIO_LOCK_LIST elements. Each element specifies a range to be unlocked.

The byte ranges to be unlocked are specified in the **LowIoContext.ParamsFor.Locks.LockList** member of the RX_CONTEXT structure. The LOWIO_LOCK_LIST structure is as follows:

```cpp
typedef struct _LOWIO_LOCK_LIST {
  struct  _LOWIO_LOCK_LIST  *Next;
  ULONG  LockNumber;
  RXVBO  ByteOffset;
  LONGLONG  Length;
  ULONG  Key;
  BOOLEAN  ExclusiveLock;
} LOWIO_LOCK_LIST, *PLOWIO_LOCK_LIST;
```

The **LowIoContext.Operation** member of RX_CONTEXT specifies the low I/O operation to perform. It is possible for several of the low I/O routines to point to the same routine in a network mini-redirector because the **LowIoContext.Operation** member can be used to differentiate the low I/O operation that is requested. For example, all the I/O calls related to file locks could call the same low I/O routine in the network mini-redirector and this routine could use the **LowIoContext.Operation** member to differentiate between the lock and unlock operation that is requested.

If the [**MRxLowIOSubmit[LOWIO_OP_UNLOCK_MULTIPLE]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-unlock-multiple-) routine can take a long time to complete, the network mini-redirector driver should release the FCB structure before initiating the network communication. The FCB structure can be released by calling [**RxReleaseFcbResourceForThreadInMRx**](../mrxfcb/nf-mrxfcb-rxreleasefcbresourceforthreadinmrx.md). While the **MRxLowIOSubmit[LOWIO_OP_UNLOCK_MULTIPLE]** routine is processing, the **LowIoContext.ResourceThreadId** member of RX_CONTEXT is guaranteed to indicate the thread of the process that initiated the operation in RDBSS.

The **LowIoContext.ResourceThreadId** member of RX_CONTEXT can be used to release the FCB structure on behalf of another thread. When an asynchronous routine completes, the FCB structure that was acquired from the initial thread can be released.

The [**MRxLowIOSubmit[LOWIO_OP_WRITE]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-write-) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to issue a write request to the network mini-redirector.

RDBSS calls [**MRxLowIOSubmit[LOWIO_OP_WRITE]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-write-) in response to receiving an [**IRP_MJ_WRITE**](/windows-hardware/drivers/kernel/irp-mj-write) request.

Before calling [**MRxLowIOSubmit[LOWIO_OP_WRITE]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-write-), RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

The **LowIoContext.Operation** member is set to LOWIO_OP_WRITE.

The **LowIoContext.ResourceThreadId** member is set to the thread of the process that initiated the operation in RDBSS.

The **LowIoContext.ParamsFor.ReadWrite.Key** member is set to the value of **IrpSp->Parameters.Read.Key**.

The **ParamsFor.ReadWrite.Flags** member has the LOWIO_READWRITEFLAG_PAGING_IO bit is set on if **Irp->Flags** has the IRP_PAGING_IO bit on.

The **ParamsFor.ReadWrite.Buffer** member is set to the user buffer locked for IoWriteAccess.

The **LowIoContext.ParamsFor.ReadWrite.ByteCount** member is set to the value of **IrpSp->Parameters.Write.Length**.

A write request is normally implemented by a network mini-redirector as an asynchronous operation because it can take considerable time. The operation usually consists of sending a network request to the remote server. The response is obtained when the write request is completed on the server. This is an example of an operation for which the network mini-redirector may need to register a context for handling cancellations initiated locally.

While the [**MRxLowIOSubmit[LOWIO_OP_WRITE]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-write-) routine is processing, the **LowIoContext.ResourceThreadId** member of RX_CONTEXT is guaranteed to indicate the thread of the process that initiated the operation in RDBSS. The **LowIoContext.ResourceThreadId** member can be used to release the FCB structure on behalf of another thread. When an asynchronous routine completes, the FCB structure that was acquired from the initial thread can be released. The FCB structure can be released by calling [**RxReleaseFcbResourceForThreadInMRx**](../mrxfcb/nf-mrxfcb-rxreleasefcbresourceforthreadinmrx.md).

The [**MRxQueryDirectory**](/windows-hardware/drivers/ifs/mrxquerydirectory) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector query information on a file directory.

Before calling [**MRxQueryDirectory**](/windows-hardware/drivers/ifs/mrxquerydirectory), RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

The **Info.FileInformationClass** member is set to **IrpSp->Parameters.QueryDirectory.FileInformationClass**.

The **Info.Buffer** member is set to user buffer from I/O request packet. This buffer has already been locked by RDBSS if needed.

The **Info.LengthRemaining** member is set to **IrpSp->Parameters.QueryDirectory.Length**.

The **QueryDirectory.FileIndex** member is set to **IrpSp->Parameters.QueryDirectory.FileIndex**.

The **QueryDirectory.RestartScan** member is set to nonzero if **IrpSp->Flags** has the SL_RESTART_SCAN bit on.

The **QueryDirectory.ReturnSingleEntry** member is set to nonzero if **IrpSp->Flags** has the SL_RETURN_SINGLE_ENTRY bit on.

The **QueryDirectory.IndexSpecified** member is set to nonzero if **IrpSp->Flags** has the SL_INDEX_SPECIFIED bit on.

The **QueryDirectory.InitialQuery** member is set to nonzero if **UnicodeQueryTemplate.Buffer** member of the associated FOBX is NULL and the **Flags** member of the FOBX does not have the FOBX_FLAG_MATCH_ALL bit on.

For a wild card query ("*.*", for example), RDBSS will set the **UnicodeQueryTemplate.Buffer** member of the associated FOBX to the wild card query passed.

If the **PostRequest** member of the RX_CONTEXT structure is **TRUE** on return from [**MRxQueryDirectory**](/windows-hardware/drivers/ifs/mrxquerydirectory), then RDBSS will call [**RxFsdPostRequest**](../rxprocs/nf-rxprocs-rxfsdpostrequest.md) passing the RX_CONTEXT structure to a worker queue for processing by the file system process (FSP).

The [**MRxQueryEaInfo**](/windows-hardware/drivers/ifs/mrxqueryeainfo) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector query extended attribute information on a file system object.

RDBSS issues a call to [**MRxQueryEaInfo**](/windows-hardware/drivers/ifs/mrxqueryeainfo) in response to receiving an [**IRP_MJ_QUERY_EA**](/windows-hardware/drivers/ifs/irp-mj-query-ea) request.

Before calling [**MRxQueryEaInfo**](/windows-hardware/drivers/ifs/mrxqueryeainfo), RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

The **Info.Buffer** member is set to the user buffer from I/O request packet. This buffer has already been locked by RDBSS if needed.

The **Info.LengthRemaining** member is set to **IrpSp->Parameters.QueryEa.Length**.

The **QueryEa.UserEaList** member is set to **IrpSp->Parameters.QueryEa.EaList**.

The **QueryEa.UserEaListLength** member is set to **IrpSp->Parameters.QueryEa.EaListLength**.

The **QueryEa.UserEaIndex** member is set to **IrpSp->Parameters.QueryEa.EaIndex**.

The **QueryEa.RestartScan** member is set to nonzero if **IrpSp->Flags** has the SL_RESTART_SCAN bit on.

The **QueryEa.ReturnSingleEntry** member is set to nonzero if **IrpSp->Flags** has the SL_RETURN_SINGLE_ENTRY bit on.

The **QueryEa.IndexSpecified** member is set to nonzero if **IrpSp->Flags** has the SL_INDEX_SPECIFIED bit on.

On success, [**MRxQueryEaInfo**](/windows-hardware/drivers/ifs/mrxqueryeainfo) should set the **Info.LengthRemaininging** member of the RX_CONTEXT structure to the length of extended attribute information returned and also update the **Fobx->OffsetOfNextEaToReturn** member. If the call to **MRxQueryEaInfo** was successful, RDBSS sets the **IoStatus.Information** member of the IRP to **IrpSp->Parameters.QueryEa.Length** minus the **Info.LengthRemaining** member of RX_CONTEXT.

The [**MRxQueryFileInfo**](/windows-hardware/drivers/ifs/mrxqueryfileinfo) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector query file information on a file system object.

RDBSS issues a call to [**MRxQueryFileInfo**](/windows-hardware/drivers/ifs/mrxqueryfileinfo) in response to receiving an [**IRP_MJ_QUERY_INFORMATION**](/windows-hardware/drivers/ifs/irp-mj-query-information) request.

Before calling [**MRxQueryFileInfo**](/windows-hardware/drivers/ifs/mrxqueryfileinfo), RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

The **Info.FileInformationClass** member is set to **IrpSp->Parameters.QueryFile.FileInformationClass**, the requested FILE_INFORMATION_CLASS value.

The **Info.Buffer** member is set to the user buffer from the I/O request packet.

The **Info.LengthRemaining** member is set to **IrpSp->Parameters.QueryFile.Length**.

The **QueryDirectory.FileIndex** member is set to **IrpSp->Parameters.QueryDirectory.FileIndex**.

The **QueryDirectory.RestartScan** member is set if **IrpSp->Flags** has the SL_RESTART_SCAN bit set.

The **QueryDirectory.ReturnSingleEntry** member is set if **IrpSp->Flags** has SL_RETURN_SINGLE_ENTRY bit set.

The **QueryDirectory.InitialQuery** member is set if **Fobx->UnicodeQueryTemplate.Buffer** is NULL and **Fobx->Flags** does not have the FOBX_FLAG_MATCH_ALL bit set.

On success, the network mini-redirector should set the **Info.LengthRemaining** member of the RX_CONTEXT structure to **Info.Length** member minus the length of the file information returned. If the call to [**MRxQueryFileInfo**](/windows-hardware/drivers/ifs/mrxqueryfileinfo) was successful, RDBSS sets the **IoStatus.Information** member of the IRP to **IrpSp->Parameters.QueryFile.Length** minus The **Info.LengthRemaining** member of RX_CONTEXT.

RDBSS does not support requests with the SL_INDEX_SPECIFIED bit of the **IrpSp->Flags** set. A network mini-redirector will not receive calls to [**MRxQueryFileInfo**](/windows-hardware/drivers/ifs/mrxqueryfileinfo) with the SL_INDEX_SPECIFIED bit of **IrpSp->Flags** set.

The [**MRxQueryQuotaInfo**](/windows-hardware/drivers/ifs/mrxqueryquotainfo) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector query quota information on a file system object.

RDBSS issues a call to [**MRxQueryQuotaInfo**](/windows-hardware/drivers/ifs/mrxqueryquotainfo) in response to receiving an [**IRP_MJ_QUERY_QUOTA**](/windows-hardware/drivers/ifs/irp-mj-query-quota) request.

Before calling [**MRxQueryQuotaInfo**](/windows-hardware/drivers/ifs/mrxqueryquotainfo), RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

The **Info.Buffer** member is set to user buffer from I/O request packet. This buffer has already been locked by RDBSS if needed.

The **Info.LengthRemaining** member is set to **IrpSp->Parameters.QueryQuota.Length**.

The **QueryQuota.SidList** member is set to **IrpSp->Parameters.QueryQuota.SidList**.

The **QueryQuota.SidListLength** member is set to **IrpSp->Parameters.QueryQuota.SidListLength**.

The **QueryQuota.StartSid** member is set to **IrpSp->Parameters.QueryQuota.StartSid**.

The **QueryQuota.Length** member is set to **IrpSp->Parameters.QueryQuota.Length**.

The **QueryQuota.RestartScan** member is set to nonzero if **IrpSp->Flags** has the SL_RESTART_SCAN bit set.

The **QueryQuota.ReturnSingleEntry** member is set to nonzero if **IrpSp->Flags** has the SL_RETURN_SINGLE_ENTRY bit set.

The **QueryQuota.IndexSpecified** member is set to nonzero if **IrpSp->Flags** has the SL_INDEX_SPECIFIED bit set.

On success, the network mini-redirector should set the **Info.LengthRemaining** member of the RX_CONTEXT structure to the length of the quota information to return. If the call to [**MRxQueryQuotaInfo**](/windows-hardware/drivers/ifs/mrxqueryquotainfo) was successful, RDBSS sets the **IoStatus.Information** member of the IRP to the **Info.LengthRemaining** member of RX_CONTEXT.

If the call to [**MRxQueryQuotaInfo**](/windows-hardware/drivers/ifs/mrxqueryquotainfo) is successful, the **InformationToReturn** member of the RX_CONTEXT structure should be set to the length of quota information returned. If the call is unsuccessful, the **InformationToReturn** member of RX_CONTEXT should be set to zero.

The [**MRxQuerySdInfo**](/windows-hardware/drivers/ifs/mrxquerysdinfo) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector query security descriptor information on a file system object.

RDBSS issues a call to [**MRxQuerySdInfo**](/windows-hardware/drivers/ifs/mrxquerysdinfo) in response to receiving an [**IRP_MJ_QUERY_SECURITY**](/windows-hardware/drivers/ifs/irp-mj-query-security) request.

Before calling [**MRxQuerySdInfo**](/windows-hardware/drivers/ifs/mrxquerysdinfo), RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

The **QuerySecurity.SecurityInformation** member is set to **IrpSp->Parameters.QuerySecurity.SecurityInformation**.

The **Info.Buffer** member is set to user buffer from I/O request packet. This buffer has already been locked by RDBSS if needed.

The **Info.LengthRemaining** member is set to **IrpSp->Parameters.QuerySecurity.Length**.

On success, the network mini-redirector should set the **InformationToReturn** member of the RX_CONTEXT structure to the length of the security information returned. If the call to [**MRxQuerySdInfo**](/windows-hardware/drivers/ifs/mrxquerysdinfo) was successful, RDBSS sets the **IoStatus.Information** member of the IRP to the **InformationToReturn** member of RX_CONTEXT.

The [**MRxQueryVolumeInfo**](/windows-hardware/drivers/ifs/mrxqueryvolumeinfo) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector query volume information.

RDBSS issues a call to [**MRxQueryVolumeInfo**](/windows-hardware/drivers/ifs/mrxqueryvolumeinfo) in either of the following cases:

* RDBSS receives an [**IRP_MJ_QUERY_VOLUME_INFORMATION**](/windows-hardware/drivers/ifs/irp-mj-query-volume-information) request.

* RDBSS receives an [**IRP_MJ_FILE_SYSTEM_CONTROL**](/windows-hardware/drivers/kernel/irp-mj-file-system-control) request for an FSCTL_LMR_GET_LINK_TRACKING_INFORMATION control code.

Before calling [**MRxQueryVolumeInfo**](/windows-hardware/drivers/ifs/mrxqueryvolumeinfo) in the case of an IRP_MJ_QUERY_VOLUME_INFORMATION request, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

The **Info.FsInformationClass** member is set to **IrpSp->Parameters.QueryVolume.FsInformationClass**.

The **Info.Buffer** member is set to **Irp->AssociatedIrp.SystemBuffer**.

The **Info.LengthRemaining** member is set to **IrpSp->Parameters.QueryVolume.Length**.

For an IRP_MJ_QUERY_VOLUME_INFORMATION request, if the **PostRequest** member of the RX_CONTEXT structure is **TRUE** on return from [**MRxQueryVolumeInfo**](/windows-hardware/drivers/ifs/mrxqueryvolumeinfo), RDBSS will call [**RxFsdPostRequest**](../rxprocs/nf-rxprocs-rxfsdpostrequest.md) to post the request. For this case, the IRP_MJ_QUERY_VOLUME_INFORMATION request will pass the RX_CONTEXT structure to queue RX_CONTEXT to a worker queue for processing by the file system process (FSP).

If the **PostRequest** member of the RX_CONTEXT structure is **FALSE** on return from [**MRxQueryVolumeInfo**](/windows-hardware/drivers/ifs/mrxqueryvolumeinfo), the network mini-redirector must set the **Info.LengthRemaining** member of the RX_CONTEXT structure to the length of the volume information returned. RDBSS sets the **IoStatus.Information** member of the IRP to **IrpSp->Parameters.QueryVolume.Length** minus the **Info.LengthRemaining** member of the RX_CONTEXT structure.

If the call to [**MRxQueryVolumeInfo**](/windows-hardware/drivers/ifs/mrxqueryvolumeinfo) is successful, the network mini-redirector should set the **Info.LengthRemaining** member of the RX_CONTEXT structure to the **Info.Length**  member minus the length of the volume information returned. If the call to **MRxQueryVolumeInfo** was successful, RDBSS sets the **IoStatus.Information** member of the IRP to **IrpSp->Parameters.QueryVolume.Length** minus the **Info.LengthRemaining** member of the RX_CONTEXT structure.

For an IRP_MJ_QUERY_VOLUME_INFORMATION request with the **Info.FsInformationClass** member set to **FileFsDeviceInformation**, the network mini-redirector returns the following information in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

The **Info.Buffer** member contains an FILE_FS_DEVICE_INFORMATION structure

The **Info.Buffer.Characteristics** member is set to the characteristics of the volume, which must include FILE_REMOTE_DEVICE as one of the options.

The **Info.Buffer.DeviceType** member is set to the **DeviceType** member of the associated NET_ROOT structure. If the **Type** member of the associated NET_ROOT is NET_ROOT_PIPE, **Info.Buffer.DeviceType** member is set to FILE_DEVICE_NAMED_PIPE.

For an IRP_MJ_QUERY_VOLUME_INFORMATION request with the **Info.FsInformationClass** member set to **FileFsVolumeInformation**, the network mini-redirector returns the following information in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

The **Info.Buffer** member contains a FILE_FS_VOLUME_INFORMATION structure.

The **Info.Buffer** member is set to the **VolumeInfo** member of the associated NET_ROOT structure.

The **Info.LengthRemaining** member is set to the **VolumeInfoLength** member of the associated NET_ROOT structure.

An [**MRxQueryVolumeInfo**](/windows-hardware/drivers/ifs/mrxqueryvolumeinfo) call from RDBSS for [**IRP_MJ_FILE_SYSTEM_CONTROL**](/windows-hardware/drivers/kernel/irp-mj-file-system-control) is a request for the link tracking information. Before calling **MRxQueryVolumeInfo** for IRP_MJ_FILE_SYSTEM_CONTROL, RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

The **Info.FsInformationClass** member is set to **FileFsObjectIdInformation**.

The **Info.Buffer** member is set to a FILE_FS_OBJECTID_INFORMATION structure.

The **Info.LengthRemaining** member is set to **sizeof**(FILE_FS_OBJECTID_INFORMATION).

For this case of an IRP_MJ_FILE_SYSTEM_CONTROL request, the **AssociatedIrp.SystemBuffer** member of the IRP points to a LINK_TRACKING_INFORMATION structure.

If a request is initiated as an IRP_MJ_FILE_SYSTEM_CONTROL to [**MRxQueryVolumeInfo**](/windows-hardware/drivers/ifs/mrxqueryvolumeinfo) with a return value of STATUS_SUCCESS or STATUS_BUFFER_OVERFLOW, RDBSS copies the **ObjectId** member of the FILE_FS_OBJECTID_INFORMATION structure passed in the **Info.Buffer** member of RX_CONTEXT structure to the **NetRoot->DiskParameters.VolumeId** member of the FCB structure and to the **AssociatedIrp.SystemBuffer.VolumeId** member of the IRP. If the call to **MRxQueryVolumeInfo** was successful, RDBSS sets the **Type** member of the LINK_TRACKING_INFORMATION structure. If the **NetRoot->Flags** member of the FCB structure has the NETROOT_FLAG_DFS_AWARE_NETROOT bit set, the **Type** member is set by RDBSS to **DfsLinkTrackingInformation**. If the **NetRoot->Flags** member of the FCB structure does not have the NETROOT_FLAG_DFS_AWARE_NETROOT bit set, the **Type** member is set by RDBSS to **NtfsLinkTrackingInformation**. On success, RDBSS sets the **IoStatus.Information** member of the IRP to the size of a LINK_TRACKING_INFORMATION structure.

The [**MRxSetEaInfo**](/windows-hardware/drivers/ifs/mrxseteainfo) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector set extended attribute information on a file system object.

RDBSS issues a call to [**MRxSetEaInfo**](/windows-hardware/drivers/ifs/mrxseteainfo) in response to receiving an [**IRP_MJ_SET_EA**](/windows-hardware/drivers/ifs/irp-mj-set-ea) request.

Before calling [**MRxSetEaInfo**](/windows-hardware/drivers/ifs/mrxseteainfo), RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

The **Info.Buffer** member is set to the user buffer from I/O request packet. This buffer has already been locked by RDBSS if needed.

The **Info.LengthRemaining** member is set to **IrpSp->Parameters.QueryEa.Length**.

The [**MRxSetFileInfo**](/windows-hardware/drivers/ifs/mrxsetfileinfo) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector set file information on a file system object.

RDBSS issues a call to [**MRxSetFileInfo**](/windows-hardware/drivers/ifs/mrxsetfileinfo) in response to receiving an [**IRP_MJ_SET_INFORMATION**](/windows-hardware/drivers/ifs/irp-mj-set-information) request.

Before calling [**MRxSetFileInfo**](/windows-hardware/drivers/ifs/mrxsetfileinfo), RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

The **Info.FileInformationClass** member is set to **IrpSp->Parameters.SetFile.FileInformationClass**, the specified FILE_INFORMATION_CLASS value.

The **Info.Buffer** member is set to **Irp->AssociatedIrp.SystemBuffer**.

The **Info.Length** member is set to **IrpSp->Parameters.SetFile.Length**.

The [**MRxSetFileInfoAtCleanup**](/windows-hardware/drivers/ifs/mrxsetfileinfoatcleanup) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector set file information on a file system object at cleanup.

RDBSS issues a call to [**MRxSetFileInfoAtCleanup**](/windows-hardware/drivers/ifs/mrxsetfileinfoatcleanup) during cleanup, when the last handle to a file object is closed. This is different than the close operation which is invoked when the last reference to a file object is deleted.

[**MRxSetFileInfoAtCleanup**](/windows-hardware/drivers/ifs/mrxsetfileinfoatcleanup) is called by RDBSS if the timestamps on a file or the size of a file have changed. The calls to **MRxSetFileInfoAtCleanup** by RDBSS are made separately for each of these changes. If both the file size and the timestamps have changed, then RDBSS makes two calls to **MRxSetFileInfoAtCleanup**.

Before calling [**MRxSetFileInfoAtCleanup**](/windows-hardware/drivers/ifs/mrxsetfileinfoatcleanup), RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter if the timestamps on a file have changed:

The **Info.FileInformationClass** member is set to a FILE_INFORMATION_CLASS value of FileBasicInformation.

The **Info.Buffer** member is set to a FILE_BASIC_INFORMATION structure allocated on the stack.

The **Info.Length** member is set to the sizeof a FILE_BASIC_INFORMATION structure.

Before calling [**MRxSetFileInfoAtCleanup**](/windows-hardware/drivers/ifs/mrxsetfileinfoatcleanup), RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter if the size of a file has changed:

The **Info.FileInformationClass** member is set to a FILE_INFORMATION_CLASS value of FileEndOfFileInformation.

The **Info.Buffer** member is set to a FILE_END_OF_FILE_INFORMATION structure allocated on the stack.

The **Info.Length** member is set to **sizeof(**FILE_END_OF_FILE_INFORMATION**)**.

RDBSS ignores the return value from [**MRxSetFileInfoAtCleanup**](/windows-hardware/drivers/ifs/mrxsetfileinfoatcleanup).

A network mini-redirector can choose to do nothing in this routine and return STATUS_SUCCESS. Any changes to the file size or timestamps will be handled during the cleanup operation.

The [**MRxSetQuotaInfo**](/windows-hardware/drivers/ifs/mrxsetquotainfo) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector set quota information on a file system object.

RDBSS issues a call to [**MRxSetQuotaInfo**](/windows-hardware/drivers/ifs/mrxsetquotainfo) in response to receiving an [**IRP_MJ_SET_QUOTA**](/windows-hardware/drivers/ifs/irp-mj-set-quota) request.

Before calling [**MRxSetQuotaInfo**](/windows-hardware/drivers/ifs/mrxsetquotainfo), RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

The **Info.Buffer** member is set to the user buffer from I/O request packet. This buffer has already been locked by RDBSS if needed.

The **Info.LengthRemaining** member is set to **IrpSp->Parameters.SetQuota.Length**.

The [**MRxSetSdInfo**](/windows-hardware/drivers/ifs/mrxsetsdinfo) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector set security descriptor information on a file system object.

RDBSS issues a call to [**MRxSetSdInfo**](/windows-hardware/drivers/ifs/mrxsetsdinfo) in response to receiving an [**IRP_MJ_SET_SECURITY**](/windows-hardware/drivers/ifs/irp-mj-set-security) request.

Before calling [**MRxSetSdInfo**](/windows-hardware/drivers/ifs/mrxsetsdinfo), RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

The **SetSecurity.SecurityInformation** member is set to **IrpSp->Parameters.SetSecurity.SecurityInformation**.

The **SetSecurity.SecurityDescriptor** member is set to **IrpSp->Parameters.SetSecurity.SecurityDescriptor**.

The [**MRxSetVolumeInfo**](/windows-hardware/drivers/ifs/mrxsetvolumeinfo) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector set volume information.

RDBSS issues a call to [**MRxSetVolumeInfo**](/windows-hardware/drivers/ifs/mrxsetvolumeinfo) in response to receiving an [**IRP_MJ_SET_VOLUME_INFORMATION**](/windows-hardware/drivers/ifs/irp-mj-set-volume-information) request.

Before calling [**MRxSetVolumeInfo**](/windows-hardware/drivers/ifs/mrxsetvolumeinfo), RDBSS modifies the following members in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

The **Info.FsInformationClass** member is set to **IrpSp->Parameters.SetVolume.FsInformationClass**.

The **Info.Buffer** member is set to **Irp->AssociatedIrp.SystemBuffer**.

The **Info.LengthRemaining** member is set to **IrpSp->Parameters.SetVolume.Length**.

The [**MRxShouldTryToCollapseThisOpen**](/windows-hardware/drivers/ifs/mrxshouldtrytocollapsethisopen) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector indicate if RDBSS should try and collapse an open request onto an existing file system object.

[**MRxShouldTryToCollapseThisOpen**](/windows-hardware/drivers/ifs/mrxshouldtrytocollapsethisopen) is called to determine if an open request should not be collapsed.

Before calling [**MRxShouldTryToCollapseThisOpen**](/windows-hardware/drivers/ifs/mrxshouldtrytocollapsethisopen), RDBSS modifies the following member in the RX_CONTEXT structure pointed to by the **RxContext** parameter:

The **pRelevantSrvOpen** member is set to the SRV_OPEN.

The call to [**MRxShouldTryToCollapseThisOpen**](/windows-hardware/drivers/ifs/mrxshouldtrytocollapsethisopen) could be a change notify request for a directory. Therefore, the network mini-redirector might not allow collapsing open requests so that change notification works correctly.

RDBSS disallows collapsing opens if the **Create.NtCreateParameters.CreateOptions** member of the RX_CONTEXT structure has the FILE_OPEN_FOR_BACKUP_INTENT option or the FILE_DELETE_ON_CLOSE option set.

The [**MRxTruncate**](/windows-hardware/drivers/ifs/mrxtruncate) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector truncate the contents of a file system object.

[**MRxTruncate**](/windows-hardware/drivers/ifs/mrxtruncate) is called as part of cleanup operations if both of the following conditions are true:

* The file object corresponds to a disk file or directory

* This is the last cleanup call and the file object was marked for truncation.

The file object is marked for truncation if the **fcbstate** member of the FCB structure has the FCB_STATE_TRUNCATE_ON_CLOSE bit set. RDBSS will uninitialize the cache map at some later time.

A call to [**MRxTruncate**](/windows-hardware/drivers/ifs/mrxtruncate) will be followed by a call to [**MRxCleanupFobx**](/previous-versions/windows/hardware/drivers/ff549841(v=vs.85)) as part of the cleanup operation.

RDBSS ignores the return value from [**MRxTruncate**](/windows-hardware/drivers/ifs/mrxtruncate).

The [**MRxZeroExtend**](/windows-hardware/drivers/ifs/mrxzeroextend) routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector truncate the contents of a file system object.

[**MRxZeroExtend**](/windows-hardware/drivers/ifs/mrxzeroextend) is called as part of cleanup operations if the file object was not marked for deletion and the file object is not a paging file. **MRxZeroExtend** is called to ensure that the portion between the valid data length and the file size is zero-extended. After calling **MRxZeroExtend**, RDBSS sets the **Header.ValidDataLength.QuadPart** member of the structure of an FCB structure equal to the **Header.FileSize.QuadPart** member of the FCB structure.

A call to [**MRxZeroExtend**](/windows-hardware/drivers/ifs/mrxzeroextend) will be followed by a call to [**MRxCleanupFobx**](/previous-versions/windows/hardware/drivers/ff549841(v=vs.85)) as part of the cleanup operation.

RDBSS ignores the return value from [**MRxZeroExtend**](/windows-hardware/drivers/ifs/mrxzeroextend).

The MRxCleanupFobx routine is called by RDBSS to request the network mini-redirector to close a file system object extension. RDBSS issues this call in response to receiving an IRP_MJ_CLEANUP request on a file object.

MRxCleanupFobx is called by RDBSS as part of cleanup and close operations on a file object.

MRxCleanupFobx cannot return a value of STATUS_RETRY indicating that the call should be retried. If a retry loop is necessary, it must be handled internally in the MRxCleanupFobx routine by the network mini-redirector.

## -see-also

[**MRxAreFilesAliased**](nc-mrx-pmrx_chkfcb_calldown.md)

[**MRxCleanupFobx**](/previous-versions/windows/hardware/drivers/ff549841(v=vs.85))

[**MRxCollapseOpen**](/windows-hardware/drivers/ifs/mrxcollapseopen)

[**MRxCreate**](/windows-hardware/drivers/ifs/mrxcreate)

[**MRxDeallocateForFobx**](nc-mrx-pmrx_deallocate_for_fobx.md)

[**MRxDeallocateForFobx**](nc-mrx-pmrx_deallocate_for_fobx.md)

[**MRxExtendForCache**](nc-mrx-pmrx_extendfile_calldown.md)

[**MRxExtendForNonCache**](/windows-hardware/drivers/ifs/mrxextendfornoncache)

[**MRxFlush**](/windows-hardware/drivers/ifs/mrxflush)

[**MRxForceClosed**](nc-mrx-pmrx_forceclosed_calldown.md)

[**MRxIsLockRealizable**](nc-mrx-pmrx_is_lock_realizable.md)

[**MRxShouldTryToCollapseThisOpen**](/windows-hardware/drivers/ifs/mrxshouldtrytocollapsethisopen)

[**MRxTruncate**](/windows-hardware/drivers/ifs/mrxtruncate)

[**MRxZeroExtend**](/windows-hardware/drivers/ifs/mrxzeroextend)

[**RxFinalizeNetFCB**](../rxprocs/nf-rxprocs-rxfinalizenetfcb.md)
