---
UID: NS:fltkernel._FLT_CREATEFILE_TARGET_ECP_CONTEXT
title: "_FLT_CREATEFILE_TARGET_ECP_CONTEXT"
author: windows-driver-content
description: The FLT_CREATEFILE_TARGET_ECP_CONTEXT structure is an extra create parameter (ECP) used to return reparse target information back to the caller of FltCreateFileEx2.
old-location: ifsk\flt_createfile_target_ecp_context.htm
old-project: ifsk
ms.assetid: 95BDB715-E476-48EF-9867-112CF665B66D
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PFLT_CREATEFILE_TARGET_ECP_CONTEXT, FLTTCFL_AUTO_REPARSE, FLT_CREATEFILE_TARGET_ECP_CONTEXT, FLT_CREATEFILE_TARGET_ECP_CONTEXT structure [Installable File System Drivers], PFLT_CREATEFILE_TARGET_ECP_CONTEXT, PFLT_CREATEFILE_TARGET_ECP_CONTEXT structure pointer [Installable File System Drivers], _FLT_CREATEFILE_TARGET_ECP_CONTEXT, fltkernel/FLT_CREATEFILE_TARGET_ECP_CONTEXT, fltkernel/PFLT_CREATEFILE_TARGET_ECP_CONTEXT, ifsk.flt_createfile_target_ecp_context"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fltkernel.h
api_name:
-	FLT_CREATEFILE_TARGET_ECP_CONTEXT
product: Windows
targetos: Windows
req.typenames: FLT_CREATEFILE_TARGET_ECP_CONTEXT, *PFLT_CREATEFILE_TARGET_ECP_CONTEXT
---

# _FLT_CREATEFILE_TARGET_ECP_CONTEXT structure


## -description


The <b>FLT_CREATEFILE_TARGET_ECP_CONTEXT</b> structure is an extra create parameter (ECP) used to return reparse target information back to the caller of <a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a>.


## -syntax


````
typedef struct _FLT_CREATEFILE_TARGET_ECP_CONTEXT {
  PFLT_INSTANCE               Instance;
  PFLT_VOLUME                 Volume;
  PFLT_FILE_NAME_INFORMATION  FileNameInformation;
  FLT_CREATEFILE_TARGET_FLAGS Flags;
} FLT_CREATEFILE_TARGET_ECP_CONTEXT, *PFLT_CREATEFILE_TARGET_ECP_CONTEXT;
````


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
Request that the <a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a> attempt a reparse operation when a target is not found with the original file information.

</td>
</tr>
</table>
 


## -remarks



When a caller of <a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a> wishes to  enable reparsing for a volume target, a <b>FLT_CREATEFILE_TARGET_ECP_CONTEXT</b> can be included as an ECP to the ECP list in the <i>DriverContext</i> parameter.  If this ECP is present, <b>FltCreateFileEx2</b> will adjust the target device for the create operation and attempt for find a filtered instance  of a volume appropriate for the given file information. If filter manager does not find a corresponding instance for the caller on the target volume, it will set the <b>Volume</b> and  <b>FileNameInformation</b> members of <b>FLT_CREATEFILE_TARGET_ECP_CONTEXT</b> for the new target. The caller can then use this information to decide how best to proceed.

If the caller of <a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a> intends to handle the reparse operation itself, the <b>FLTTCFL_AUTO_REPARSE</b> flag is cleared from the <b>Flags</b> member. In this case, <b>FltCreateFileEx2</b> will place the initial target adjustment information in the ECP and then will return, ending the file create attempt.

 If  the values in <b>Instance</b>, <b>Volume</b>, or <b>FileNameInformation</b> are set in an acknowledged ECP, they are referenced objects. A caller of <a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a> is responsible for calling <a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a> for <b>Instance</b> and <b>Volume</b>, and <a href="..\fltkernel\nf-fltkernel-fltreleasefilenameinformation.md">FltReleaseFileNameInformation</a> for <b>FileNameInformation</b>.

The following example routine demonstrates how a minifilter can call <a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a> with <b>FLT_CREATEFILE_TARGET_ECP_CONTEXT</b> to handle a reparse to a different volume when required to find a file target.

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

    InitializeObjectAttributes( &amp;objAttr,
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
                               &amp;objAttr,
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

        if ((status != STATUS_INVALID_DEVICE_OBJECT_PARAMETER) &amp;&amp;
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
                                                  &amp;ecpList );
    if (!NT_SUCCESS( status )) {
        goto CrossVolumeCreateExit;
    }

    status = FltAllocateExtraCreateParameter( Filter,
                                              &amp;GUID_ECP_FLT_CREATEFILE_TARGET,
                                              sizeof(FLT_CREATEFILE_TARGET_ECP_CONTEXT),
                                              0,
                                              NULL,
                                              POOL_TAG,
                                              &amp;ecpContext );

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

    ecpContext-&gt;Flags = FLTTCFL_AUTO_REPARSE;

    ecpContext-&gt;Instance = NULL;
    ecpContext-&gt;Volume = NULL;
    ecpContext-&gt;FileNameInformation = NULL;

    status = FltInsertExtraCreateParameter( Filter,
                                            ecpList,
                                            ecpContext );
    if (!NT_SUCCESS( status )) {
        goto CrossVolumeCreateExit;
    }

    IoInitializeDriverCreateContext( &amp;myCreateContext );
    myCreateContext.ExtraCreateParameter = ecpList;

    InitializeObjectAttributes( &amp;objAttr,
                                FileName,
                                OBJ_KERNEL_HANDLE,
                                NULL,
                                NULL );

    status = FltCreateFileEx2( Filter,
                               Instance,
                               Handle,
                               FileObject,
                               FILE_READ_DATA|FILE_WRITE_DATA,
                               &amp;objAttr,
                               IoStatus,
                               NULL,
                               0,
                               FILE_SHARE_READ | FILE_SHARE_WRITE | FILE_SHARE_DELETE,
                               FILE_OPEN_IF,
                               FILE_NON_DIRECTORY_FILE | FILE_SYNCHRONOUS_IO_NONALERT,
                               NULL,
                               0,
                               IO_IGNORE_SHARE_ACCESS_CHECK,
                               &amp;myCreateContext );

    if (!NT_SUCCESS(status)) {

        if ((status != STATUS_INVALID_DEVICE_OBJECT_PARAMETER) &amp;&amp;
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

    if (ecpContext-&gt;Volume != NULL) {
        FltObjectDereference( ecpContext-&gt;Volume );
        ecpContext-&gt;Volume = NULL;
    }

    //
    //  Note:  since we flagged the ECP to automatically handle
    //  cross-volume reparse, the create should have failed after
    //  we traversed a mountpoint only if our filter did not have
    //  an instance on the target volume. In that case we would
    //  expect the Instance field in the ECP to be NULL. We still
    //  demonstrate derefing the instance for the general case.
    //

    if (ecpContext-&gt;Instance != NULL) {
        FltObjectDereference( ecpContext-&gt;Instance );
        ecpContext-&gt;Instance = NULL;
    }

    fileNameInformation = ecpContext-&gt;FileNameInformation;
    ecpContext-&gt;FileNameInformation = NULL;

    //
    //  Tell filter manager to not handle the cross-volume
    //  reparse itself. Presumably a filter would do this if it
    //  did not want the create automatically targeted at its
    //  instance on another volume.
    //

    ecpContext-&gt;Flags = 0;

    //
    //  Reinitialize the targeting ECP to it can be reused.
    //

    FltPrepareToReuseEcp( Filter, ecpContext );

    IoInitializeDriverCreateContext( &amp;myCreateContext );
    myCreateContext.ExtraCreateParameter = ecpList;

    InitializeObjectAttributes( &amp;objAttr,
                                &amp;fileNameInformation-&gt;Name,
                                OBJ_KERNEL_HANDLE,
                                NULL,
                                NULL );

    status = FltCreateFileEx2( Filter,
                               NULL,
                               Handle,
                               FileObject,
                               FILE_READ_DATA|FILE_WRITE_DATA,
                               &amp;objAttr,
                               IoStatus,
                               NULL,
                               0,
                               FILE_SHARE_READ | FILE_SHARE_WRITE | FILE_SHARE_DELETE,
                               FILE_OPEN_IF,
                               FILE_NON_DIRECTORY_FILE | FILE_SYNCHRONOUS_IO_NONALERT,
                               NULL,
                               0,
                               IO_IGNORE_SHARE_ACCESS_CHECK,
                               &amp;myCreateContext );

    if (!NT_SUCCESS(status)) {

        if ((status != STATUS_INVALID_DEVICE_OBJECT_PARAMETER) &amp;&amp;
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

    if (ecpContext != NULL &amp;&amp; 
        FltIsEcpAcknowledged( Filter, ecpContext)) {

        FltRemoveExtraCreateParameter( Filter,
                                       ecpList,
                                       &amp;GUID_ECP_FLT_CREATEFILE_TARGET,
                                       &amp;ecpContext,
                                       NULL );

        if (ecpContext-&gt;Instance != NULL) {
            FltObjectDereference( ecpContext-&gt;Instance );
        }

        if (ecpContext-&gt;Volume != NULL) {
            FltObjectDereference( ecpContext-&gt;Volume );
        }

        if (ecpContext-&gt;FileNameInformation != NULL) {
            FltReleaseFileNameInformation( ecpContext-&gt;FileNameInformation );
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

<a href="..\fltkernel\nf-fltkernel-fltreleasefilenameinformation.md">FltReleaseFileNameInformation</a>



<a href="..\fltkernel\nf-fltkernel-fltcreatefileex2.md">FltCreateFileEx2</a>



<a href="..\fltkernel\nf-fltkernel-fltobjectdereference.md">FltObjectDereference</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FLT_CREATEFILE_TARGET_ECP_CONTEXT structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

