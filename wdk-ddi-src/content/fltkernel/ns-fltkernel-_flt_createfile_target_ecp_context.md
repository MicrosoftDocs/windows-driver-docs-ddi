---
UID: NS:fltkernel._FLT_CREATEFILE_TARGET_ECP_CONTEXT
title: _FLT_CREATEFILE_TARGET_ECP_CONTEXT (fltkernel.h)
description: The FLT_CREATEFILE_TARGET_ECP_CONTEXT structure is an extra create parameter (ECP) used to return reparse target information back to the caller of FltCreateFileEx2.
old-location: ifsk\flt_createfile_target_ecp_context.htm
tech.root: ifsk
ms.assetid: 95BDB715-E476-48EF-9867-112CF665B66D
ms.date: 04/16/2018
keywords: ["_FLT_CREATEFILE_TARGET_ECP_CONTEXT structure"]
ms.keywords: "*PFLT_CREATEFILE_TARGET_ECP_CONTEXT, FLTTCFL_AUTO_REPARSE, FLT_CREATEFILE_TARGET_ECP_CONTEXT, FLT_CREATEFILE_TARGET_ECP_CONTEXT structure [Installable File System Drivers], PFLT_CREATEFILE_TARGET_ECP_CONTEXT, PFLT_CREATEFILE_TARGET_ECP_CONTEXT structure pointer [Installable File System Drivers], _FLT_CREATEFILE_TARGET_ECP_CONTEXT, fltkernel/FLT_CREATEFILE_TARGET_ECP_CONTEXT, fltkernel/PFLT_CREATEFILE_TARGET_ECP_CONTEXT, ifsk.flt_createfile_target_ecp_context"
f1_keywords:
 - "fltkernel/FLT_CREATEFILE_TARGET_ECP_CONTEXT"
 - "FLT_CREATEFILE_TARGET_ECP_CONTEXT"
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available starting with Windows 8.
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- fltkernel.h
api_name:
- FLT_CREATEFILE_TARGET_ECP_CONTEXT
product:
- Windows
targetos: Windows
req.typenames: FLT_CREATEFILE_TARGET_ECP_CONTEXT, *PFLT_CREATEFILE_TARGET_ECP_CONTEXT
---

# _FLT_CREATEFILE_TARGET_ECP_CONTEXT structure


## -description


The <b>FLT_CREATEFILE_TARGET_ECP_CONTEXT</b> structure is an extra create parameter (ECP) used to return reparse target information back to the caller of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefileex2">FltCreateFileEx2</a>.


## -struct-fields




### -field Instance

The filter instance attached to the adjusted target.


### -field Volume

The adjusted target volume.


### -field FileNameInformation

The file information for the adjusted target.


### -field Flags

Flags controlling the reparse operation. This value can be either 0 or the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="FLTTCFL_AUTO_REPARSE"></a><a id="flttcfl_auto_reparse"></a><dl>
<dt><b>FLTTCFL_AUTO_REPARSE</b></dt>
</dl>
</td>
<td width="60%">
Request that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefileex2">FltCreateFileEx2</a> attempt a reparse operation when a target is not found with the original file information.

</td>
</tr>
</table>
 


## -remarks



When a caller of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefileex2">FltCreateFileEx2</a> wishes to  enable reparsing for a volume target, a <b>FLT_CREATEFILE_TARGET_ECP_CONTEXT</b> can be included as an ECP to the ECP list in the <i>DriverContext</i> parameter.  If this ECP is present, <b>FltCreateFileEx2</b> will adjust the target device for the create operation and attempt to find a filtered instance  of a volume appropriate for the given file information. If the filter manager does not find a corresponding instance for the caller on the target volume, it will set the <b>Volume</b> and  <b>FileNameInformation</b> members of <b>FLT_CREATEFILE_TARGET_ECP_CONTEXT</b> for the new target. The caller can then use this information to decide how best to proceed.

If the caller of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefileex2">FltCreateFileEx2</a> intends to handle the reparse operation itself, the <b>FLTTCFL_AUTO_REPARSE</b> flag is cleared from the <b>Flags</b> member. In this case, <b>FltCreateFileEx2</b> will place the initial target adjustment information in the ECP and then will return, ending the file create attempt.

 If  the values in <b>Instance</b>, <b>Volume</b>, or <b>FileNameInformation</b> are set in an acknowledged ECP, they are referenced objects. A caller of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefileex2">FltCreateFileEx2</a> is responsible for calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltobjectdereference">FltObjectDereference</a> for <b>Instance</b> and <b>Volume</b>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasefilenameinformation">FltReleaseFileNameInformation</a> for <b>FileNameInformation</b>.

The following example routine demonstrates how a minifilter can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefileex2">FltCreateFileEx2</a> with <b>FLT_CREATEFILE_TARGET_ECP_CONTEXT</b> to handle a reparse to a different volume when required to find a file target.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
CrossVolumeCreate(
    _In_ PUNICODE_STRING FileName,
    _In_ PFLT_FILTER Filter,
    _In_ PFLT_INSTANCE Instance,
    _Inout_ PIO_STATUS_BLOCK IoStatus,
    _Out_ PHANDLE Handle,
    _Outptr_ PFILE_OBJECT *FileObject
    )
/*++

Routine Description:

     Issues a targeted create and handles cross volume reparse.

Arguments:

    FileName - The name of the file to open

    Filter – The filter issuing the create

    Instance - The filter instance for the targeted create

    IoStatus - Receives the operation status

    Handle - Receives the file handle

    FileObject - Receives the file object

Return Value:

    status of the operation

--*/
{
    PFLT_CREATEFILE_TARGET_ECP_CONTEXT ecpContext;
    PECP_LIST ecpList;
    PFLT_FILE_NAME_INFORMATION fileNameInformation;
    IO_DRIVER_CREATE_CONTEXT myCreateContext;
    OBJECT_ATTRIBUTES objAttr;
    NTSTATUS status;

    ecpContext = NULL;
    ecpList = NULL;
    fileNameInformation = NULL;
    status = STATUS_SUCCESS;

    InitializeObjectAttributes( &objAttr,
                                FileName,
                                OBJ_KERNEL_HANDLE,
                                NULL,
                                NULL );

    //
    //  First we optimistically send a targeted create that is not
    //  setup to handle cross-volume reparse.
    //

    status = FltCreateFileEx2( Filter,
                               Instance,
                               Handle,
                               FileObject,
                               FILE_READ_DATA|FILE_WRITE_DATA,
                               &objAttr,
                               IoStatus,
                               NULL,
                               0,
                               FILE_SHARE_READ | FILE_SHARE_WRITE | FILE_SHARE_DELETE,
                               FILE_OPEN_IF,
                               FILE_NON_DIRECTORY_FILE | FILE_SYNCHRONOUS_IO_NONALERT,
                               NULL,
                               0,
                               IO_IGNORE_SHARE_ACCESS_CHECK,
                               NULL );

    if (!NT_SUCCESS(status)) {

        if ((status != STATUS_INVALID_DEVICE_OBJECT_PARAMETER) &&
            (status != STATUS_MOUNT_POINT_NOT_RESOLVED)) {

            goto CrossVolumeCreateExit;
        }

    } else {

        //
        //  The create succeeded. There must not have been a cross-volume
        //  reparse.
        //

        goto CrossVolumeCreateExit;
    }

    //
    //  The create failed traversing a cross-volume link.
    //  Issue another create with a targeting ECP so that
    //  we can handle cross-volume reparse.
    //

    status = FltAllocateExtraCreateParameterList( Filter,
                                                  0,
                                                  &ecpList );
    if (!NT_SUCCESS( status )) {
        goto CrossVolumeCreateExit;
    }

    status = FltAllocateExtraCreateParameter( Filter,
                                              &GUID_ECP_FLT_CREATEFILE_TARGET,
                                              sizeof(FLT_CREATEFILE_TARGET_ECP_CONTEXT),
                                              0,
                                              NULL,
                                              POOL_TAG,
                                              &ecpContext );

    if (!NT_SUCCESS( status )) {
        goto CrossVolumeCreateExit;
    }

    //
    //  Initialize the ECP with the FLTTCFL_AUTO_REPARSE flag which
    //  tells filter manager to handle the cross-volume reparse
    //  internally when possible (when it can find our instance
    //  on the target volume). If this flag is not set, the filter will
    //  be responsible for calling FltCreateFileEx2 with appropriate
    //  Instance parameter.
    //

    ecpContext->Flags = FLTTCFL_AUTO_REPARSE;

    ecpContext->Instance = NULL;
    ecpContext->Volume = NULL;
    ecpContext->FileNameInformation = NULL;

    status = FltInsertExtraCreateParameter( Filter,
                                            ecpList,
                                            ecpContext );
    if (!NT_SUCCESS( status )) {
        goto CrossVolumeCreateExit;
    }

    IoInitializeDriverCreateContext( &myCreateContext );
    myCreateContext.ExtraCreateParameter = ecpList;

    InitializeObjectAttributes( &objAttr,
                                FileName,
                                OBJ_KERNEL_HANDLE,
                                NULL,
                                NULL );

    status = FltCreateFileEx2( Filter,
                               Instance,
                               Handle,
                               FileObject,
                               FILE_READ_DATA|FILE_WRITE_DATA,
                               &objAttr,
                               IoStatus,
                               NULL,
                               0,
                               FILE_SHARE_READ | FILE_SHARE_WRITE | FILE_SHARE_DELETE,
                               FILE_OPEN_IF,
                               FILE_NON_DIRECTORY_FILE | FILE_SYNCHRONOUS_IO_NONALERT,
                               NULL,
                               0,
                               IO_IGNORE_SHARE_ACCESS_CHECK,
                               &myCreateContext );

    if (!NT_SUCCESS(status)) {

        if ((status != STATUS_INVALID_DEVICE_OBJECT_PARAMETER) &&
            (status != STATUS_MOUNT_POINT_NOT_RESOLVED)) {

            goto CrossVolumeCreateExit;
        }

    } else {

        goto CrossVolumeCreateExit;
    }

    //
    //  Filter manager should have acknowledged the ECP. If it
    //  is not acknowledged, it does not contain any cross-volume
    //  targeting information.
    //

    if (!FltIsEcpAcknowledged( Filter, ecpContext)) { 
        goto CrossVolumeCreateExit;
    }

    //
    //  Filter manager could not automatically handle the
    //  cross-volume traversal. We choose to send the create
    //  to the top of the stack on the target volume indicated
    //  in the targeting ECP.
    //

    //
    //  The ECP may contain pointers to referenced objects. We
    //  need to deal with those references before reusing the
    //  ECP.
    //

    if (ecpContext->Volume != NULL) {
        FltObjectDereference( ecpContext->Volume );
        ecpContext->Volume = NULL;
    }

    //
    //  Note:  since we flagged the ECP to automatically handle
    //  cross-volume reparse, the create should have failed after
    //  we traversed a mountpoint only if our filter did not have
    //  an instance on the target volume. In that case we would
    //  expect the Instance field in the ECP to be NULL. We still
    //  demonstrate derefing the instance for the general case.
    //

    if (ecpContext->Instance != NULL) {
        FltObjectDereference( ecpContext->Instance );
        ecpContext->Instance = NULL;
    }

    fileNameInformation = ecpContext->FileNameInformation;
    ecpContext->FileNameInformation = NULL;

    //
    //  Tell filter manager to not handle the cross-volume
    //  reparse itself. Presumably a filter would do this if it
    //  did not want the create automatically targeted at its
    //  instance on another volume.
    //

    ecpContext->Flags = 0;

    //
    //  Reinitialize the targeting ECP to it can be reused.
    //

    FltPrepareToReuseEcp( Filter, ecpContext );

    IoInitializeDriverCreateContext( &myCreateContext );
    myCreateContext.ExtraCreateParameter = ecpList;

    InitializeObjectAttributes( &objAttr,
                                &fileNameInformation->Name,
                                OBJ_KERNEL_HANDLE,
                                NULL,
                                NULL );

    status = FltCreateFileEx2( Filter,
                               NULL,
                               Handle,
                               FileObject,
                               FILE_READ_DATA|FILE_WRITE_DATA,
                               &objAttr,
                               IoStatus,
                               NULL,
                               0,
                               FILE_SHARE_READ | FILE_SHARE_WRITE | FILE_SHARE_DELETE,
                               FILE_OPEN_IF,
                               FILE_NON_DIRECTORY_FILE | FILE_SYNCHRONOUS_IO_NONALERT,
                               NULL,
                               0,
                               IO_IGNORE_SHARE_ACCESS_CHECK,
                               &myCreateContext );

    if (!NT_SUCCESS(status)) {

        if ((status != STATUS_INVALID_DEVICE_OBJECT_PARAMETER) &&
            (status != STATUS_MOUNT_POINT_NOT_RESOLVED)) {

            goto CrossVolumeCreateExit;
        }

        //
        //  We hit another cross-volume link. For the purposes of
        //  this example we are just giving up. An actual filter
        //  would determine the next target instance based on the
        //  information provided in the targeting ECP. Some of the
        //  possibilities are:
        //  1) If the Instance field in the ECP is available, target
        //     the create to this instance.
        //  2) If the Instance field is NULL, attempt to attach
        //     an instance based on the Volume parameter in the ECP
        //     and then target that new instance.
        //  3) Use the FileNameInformation provided in the ECP and a
        //     NULL instance to target the top of the other
        //     volume's stack.
        //

    } else {

        goto CrossVolumeCreateExit;
    }

CrossVolumeCreateExit:

    if (ecpContext != NULL && 
        FltIsEcpAcknowledged( Filter, ecpContext)) {

        FltRemoveExtraCreateParameter( Filter,
                                       ecpList,
                                       &GUID_ECP_FLT_CREATEFILE_TARGET,
                                       &ecpContext,
                                       NULL );

        if (ecpContext->Instance != NULL) {
            FltObjectDereference( ecpContext->Instance );
        }

        if (ecpContext->Volume != NULL) {
            FltObjectDereference( ecpContext->Volume );
        }

        if (ecpContext->FileNameInformation != NULL) {
            FltReleaseFileNameInformation( ecpContext->FileNameInformation );
        }

        FltFreeExtraCreateParameter( Filter, ecpContext );
    }

    if (ecpList != NULL) {
        FltFreeExtraCreateParameterList( Filter, ecpList );
    }

    if (fileNameInformation != NULL) {
        FltReleaseFileNameInformation( fileNameInformation );
    }

    return status;
}
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefileex2">FltCreateFileEx2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltobjectdereference">FltObjectDereference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasefilenameinformation">FltReleaseFileNameInformation</a>
 

 

