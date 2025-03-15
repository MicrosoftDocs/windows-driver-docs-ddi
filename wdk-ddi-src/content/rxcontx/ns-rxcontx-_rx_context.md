---
UID: NS:rxcontx._RX_CONTEXT
title: RX_CONTEXT (rxcontx.h)
description: Learn more about the RX_CONTEXT structure.
tech.root: ifsk
ms.date: 10/29/2024
keywords: ["RX_CONTEXT structure"]
req.header: rxcontx.h
req.include-header: Rx.h, Rxcontx.h
req.target-type: Windows
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
req.typenames: RX_CONTEXT, *PRX_CONTEXT
f1_keywords:
 - _RX_CONTEXT
 - rxcontx/_RX_CONTEXT
 - PRX_CONTEXT
 - rxcontx/PRX_CONTEXT
 - RX_CONTEXT
 - rxcontx/RX_CONTEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rxcontx.h
api_name:
 - _RX_CONTEXT
 - PRX_CONTEXT
 - RX_CONTEXT
---

# RX_CONTEXT structure

## -description

The **RX_CONTEXT** structure encapsulates an IRP for use by RDBSS, network mini-redirectors, and the file system. It describes an IRP while it is being processed by a network mini-redirector and contains state information that allows global resources to be released as the IRP is completed.

## -struct-fields

### -field NodeTypeCode

The unique node type used for an **RX_CONTEXT** structure. RDBSS sets this member to **RDBSS_NTC_RX_CONTEXT** when an **RX_CONTEXT** is initialized in [**RxInitializeContext**](nf-rxcontx-rxinitializecontext.md). If a network mini-redirector driver initializes an **RX_CONTEXT** structure using some other method, this member must be set.

RDBSS defines this member as part of a standard header for all structures used by RDBSS.

All of the major structure types used by RDBSS have a unique two-byte node type code defined in *nodetype.h* that can be used for debugging. These major structure types include the following:

* **RX_CONTEXT**
* [**SRV_CALL**](/windows-hardware/drivers/ifs/the-srv-call-structure)
* [**NET_ROOT**](/windows-hardware/drivers/ifs/the-net-root-structure)
* [**V_NET_ROOT**](/windows-hardware/drivers/ifs/the-v-net-root-structure)
* [**SRV_OPEN**](/windows-hardware/drivers/ifs/the-srv-open-structure)
* [**FCB**](/windows-hardware/drivers/ifs/the-fcb-structure)
* [**FOBX**](/windows-hardware/drivers/ifs/the-fobx-structure)

### -field NodeByteSize

The size, in bytes, of this structure. RDBSS sets this member to sizeof( RX_CONTEXT) when an RX_CONTEXT is initialized in the **RxInitializeContext** routine. If a network mini-redirector driver initializes an RX_CONTEXT structure using some other method, this member must be set.

RDBSS defines this member as part of a standard header for all structures used by RDBSS.

### -field ReferenceCount

The reference count for this structure after it is allocated. RDBSS sets this member to 1 when an RX_CONTEXT is allocated and initialized in the **RxInitializeContext** routine. If a network mini-redirector driver initializes an RX_CONTEXT structure using some other method, this member must be set.

RDBSS defines this member as part of a standard header for all structures used by RDBSS.

### -field ContextListEntry

The list entry to connect this RX_CONTEXT to the list of active RX_CONTEXTS.

### -field MajorFunction

The major function for the IRP encapsulated by this RX_CONTEXT.

### -field MinorFunction

The minor function for the IRP encapsulated by this RX_CONTEXT.

### -field PendingReturned

If set to TRUE, this specifies that RDBSS or a driver has marked the IRP pending. Each [**IoCompletion**](../wdm/nc-wdm-io_completion_routine.md) routine should check the value of this flag. If the flag is TRUE, and if the **IoCompletion** routine will not return STATUS_MORE_PROCESSING_REQUIRED, the routine should call [**IoMarkIrpPending**](../wdm/nf-wdm-iomarkirppending.md) to propagate the pending status to drivers above it in the device stack. This member is similar to the same field in the IRP.

RDBSS always sets this member to TRUE before calling the network mini-redirector driver.

### -field PostRequest

If set to TRUE, this indicates if the associated request is to be posted to a RDBSS worker thread. A network mini-redirector can set this member to TRUE to indicate that it wants to post this request to the file system process (FSP).

### -field RealDevice

A pointer to the device object for the target network mini-redirector driver. RDBSS sets this member to the device object for the network mini-redirector driver when an RX_CONTEXT is allocated in the [**RxInitializeContext**](nf-rxcontx-rxinitializecontext.md) routine. This member is copied from the **FileObject->DeviceObject** member from the IRP stack. The device object for the network mini-redirector is also stored in the **RxDeviceObject** structure member.

The **RealDevice**  member is not currently used by RDBSS, but can be used by network mini-redirectors.

### -field CurrentIrp

A pointer to the originating IRP. This member should not be used by a network mini-redirector driver.

### -field CurrentIrpSp

A pointer to the IRP stack location.

### -field pFcb

A pointer to the associated file control block (FCB) for this IRP.

### -field pFobx

A pointer to the associated file object extension (FOBX) for this IRP.

### -field pRelevantSrvOpen

A pointer to the associated server open(SRV_OPEN) for this IRP.

### -field NonPagedFcb

A pointer to the associated non-paged file control block (FCB) for this IRP.

### -field RxDeviceObject

A pointer to the RDBSS_DEVICE_OBJECT for the target network mini-redirector driver which is required for worker queue algorithms. RDBSS sets this member to the RDBSS_DEVICE_OBJECT for the network mini-redirector when an RX_CONTEXT is initialized in the **RxInitializeContext** routine. The **RxDeviceObject** structure includes a **DeviceObject** member that contains the device object for the network mini-redirector driver which is the same as the **RealDevice** member of the RX_CONTEXT.

### -field OriginalThread

A pointer to the original thread in which the request was initiated.

### -field LastExecutionThread

A pointer to the last thread in which some processing associated with the RX_CONTEXT was done if the thread was posted to the file system process.

### -field LockManagerContext

A pointer to the lock manager context. This member is reserved for internal use.

### -field RdbssDbgExtension

A pointer to the context given to RDBSS for debugging information. This member is reserved for internal use.

### -field ScavengerEntry

A pointer to the list of items to be scavenged. This member is reserved for internal use.

### -field SerialNumber

The serial number for this RX_CONTEXT structure. Every structure initialized by RDBSS has a serial number assigned when the structure is first initialized. This serial number is a number that is incremented by one before the value is set. RDBSS sets this member when an RX_CONTEXT is initialized in the **RxInitializeContext** routine. RDBSS

### -field FobxSerialNumber

The serial number for the associated FOBX structure. Every structure initialized by RDBSS has a serial number assigned when the structure is first initialized. This member can be used by network mini-redirectors to see if multiple calls are part of the same larger operation and are therefore more cacheable.

### -field Flags

A [bitmask of flags](ne-rxcontx-rx_context_flags.md) for this **RX_CONTEXT** structure.

### -field FcbResourceAcquired

If set to TRUE, this member specifies that the FCB resource has been acquired for this operation. The FCB resource is one of the locking mechanisms associated with an operation on an FCB.

### -field FcbPagingIoResourceAcquired

If set to TRUE, this member specifies that the FCB paging I/O resource has been acquired for this operation. The FCB paging I/O resource is one of the locking mechanisms associated with a paging I/O operation on an FCB.

### -field MustSucceedDescriptorNumber

A member initially set to zero in the [**RxCreateRxContext**](nf-rxcontx-rxcreaterxcontext.md) routine. This member is not otherwise used by RDBSS, but it may be used by network mini-redirectors.

### -field StoredStatus

A member of an unnamed union used to return status information by a network mini-redirector driver for low I/O operations. RDBSS also sets this value based on the status returned by the [**MRxQueryFileInfo**](/windows-hardware/drivers/ifs/mrxqueryfileinfo) routine when the file query operation is not understood by RDBSS.

### -field StoredStatusAlignment

A member of an unnamed union used to force proper alignment on the **StoredStatus** member.

### -field InformationToReturn

A member of an unnamed union used to return status information by a network mini-redirector driver for some low I/O (read, write, FSCTL, etc.) and **MrxQueryXXX** operations.

The unique node type used for an RX_CONTEXT structure. All of the major structure types (RX_CONTEXT, SRV_CALL, NET_ROOT, V_NET_ROOT, SRV_OPEN, FCB, and FOBX, for example) used by RDBSS have a unique two-byte node type code defined in the *nodetype.h* include file which can be used for debugging. RDBSS sets this member to RDBSS_NTC_RX_CONTEXT when an RX_CONTEXT is initialized in the [**RxInitializeContext**](nf-rxcontx-rxinitializecontext.md) routine. If a network mini-redirector driver initializes an RX_CONTEXT structure using some other method, this member must be set.

RDBSS defines this member as part of a standard header for all structures used by RDBSS.

### -field IoStatusBlock

The I/O status block use by a network mini-redirector to return status information. The **IoStatusBlock** member is a member of an unnamed union used for returning status information.

### -field ForceLonglongAligmentDummyField

A member of an unnamed union used to force proper alignment on the **MRxContext[MRX_CONTEXT_FIELD_COUNT]** member.

### -field MRxContext[MRX_CONTEXT_FIELD_COUNT]

A member of an unnamed union that contains an array of four pointers for use by a network mini-redirector driver.

### -field WriteOnlyOpenRetryContext

A pointer that can be used to store some state for the network mini-redirector. This member is not used by RDBSS, but it can be used by a network mini-redirector driver to indicate that a file is cached on a write-only handle.

### -field MRxCancelRoutine

A pointer to the cancellation routine that can be set by a network mini-redirector driver.

### -field ResumeRoutine

This member is reserved for internal use.

### -field WorkQueueItem

A pointer to a work queue item that can be used by a network mini-redirector driver while processing the RX_CONTEXT.

### -field OverflowListEntry

A pointer to the list head of operations that are to be released on completion. This member is reserved for internal use.

### -field SyncEvent

A pointer to a kernel EVENT that can be used by a network mini-redirector driver to wait while processing the RX_CONTEXT.

### -field BlockedOperations

A pointer to the list head of blocked operations that are to be released on completion. This member is reserved for internal use.

### -field BlockedOpsMutex

A pointer to a mutex that controls serialization of the blocked operations. This member is reserved for internal use.

### -field RxContextSerializationQLinks

A pointer to the list entry used to serialize pipe operations on a per-file-object basis. This member is reserved for internal use.

### -field Info

A structure member of an unnamed union used for the following routines:

* [**MRxQueryDirectory**](/windows-hardware/drivers/ifs/mrxquerydirectory)
* [**MRxQueryFileInfo**](/windows-hardware/drivers/ifs/mrxqueryfileinfo)  
* [**MRxQueryVolumeInfo**](/windows-hardware/drivers/ifs/mrxqueryvolumeinfo)  
* [**MRxSetFileInfo**](/windows-hardware/drivers/ifs/mrxsetfileinfo)  
* [**MRxSetFileInfoAtCleanup**](/windows-hardware/drivers/ifs/mrxsetfileinfoatcleanup)  
* [**MRxSetVolumeInfo**](/windows-hardware/drivers/ifs/mrxsetvolumeinfo)  

RDBSS passes information in the **Info** structure member to the network mini-redirector and the network mini-redirector returns information to RDBSS in the **Info** structure member.

### -field Info.FsInformationClass

A member of an unnamed union used by RDBSS to pass the type of FS_INFORMATION_CLASS that is requested to the network mini-redirector driver. RDBSS passes information in the **FsInformationClass** member when calling **MrxQueryVolumeInfo** and **MrxSetVolumeInfo**.

### -field Info.FileInformationClass

A member of an unnamed union used by RDBSS to indicate the type of FILE_INFORMATION_CLASS request sent to the network mini-redirector driver. RDBSS passes information in the **FileInformationClass** member when calling **MrxQueryDirectory**, **MrxQueryFileInfo**, and **MrxSetFileInfo**.

### -field Info.Buffer

A buffer used to pass data from RDBSS to the network mini-redirector driver and receive responses from the network mini-redirector driver by RDBSS. The **Buffer** member is used in the **MrxQueryDirectory**, **MrxQueryFileInfo**, **MrxQueryVolumeInfo**, **MrxSetFileInfo**, **MRxSetFileInfoAtCleanup**, and **MrxSetVolumeInfo** routines.

### -field Info.Length

A member of an unnamed union used to pass the length of the **Buffer** member from RDBSS to the network mini-redirector driver. The **Length** member is used in the **MrxQueryDirectory**, **MrxQueryFileInfo**, **MrxQueryVolumeInfo**, **MrxSetFileInfo**, **MRxSetFileInfoAtCleanup**, and **MrxSetVolumeInfo** routines.

### -field Info.LengthRemaining

A member of an unnamed union used to pass the length of information returned in the **Buffer** member from the network mini-redirector driver to RDBSS. The **LengthRemaining** member is used in the **MrxQueryDirectory**, **MrxQueryFileInfo**, **MrxQueryVolumeInfo**, **MrxSetFileInfo**, **MRxSetFileInfoAtCleanup**, and **MrxSetVolumeInfo** routines.

### -field Info.ReplaceIfExists

A Boolean value that indicates if an existing file should be replaced during a rename operation. The **ReplaceIfExists** member is used in the **MrxSetFileInfo** routine.

### -field Info.AdvanceOnly

This member is reserved for internal use.

### -field PrefixClaim

A structure member of an unnamed union used for prefix resolution requests sent from the Multiple UNC Provider (MUP). A prefix claim results from an [**IRP_MJ_DEVICE_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-device-control) request from MUP to RDBSS for [**IOCTL_REDIR_QUERY_PATH**](../ntifs/ni-ntifs-ioctl_redir_query_path.md) or [**IOCTL_REDIR_QUERY_PATH_EX**](../ntifs/ni-ntifs-ioctl_redir_query_path_ex.md). RDBSS passes information in the **PrefixClaim** structure to the network mini-redirector and the network mini-redirector returns information to RDBSS in the **PrefixClaim** structure.

### -field PrefixClaim.SuppliedPathName

A non-NULL terminated Unicode string specifying the UNC path on which to perform the prefix resolution.

### -field PrefixClaim.NetRootType

The type of the NET_ROOT requested. This member is not currently used. RDBSS deduces the type of the NET_ROOT from the **SuppliedPathName** member.

### -field PrefixClaim.pSecurityContext

A pointer to the security context passed in from the request from MUP.

This member is not currently used. The security context is passed in the **Create.NtCreateParameters.SecurityContext** member of the RX_CONTEXT, not in this member.

### -field Create

A structure member of an unnamed union used for handling [**IRP_MJ_CREATE**](/windows-hardware/drivers/ifs/irp-mj-create) requests. This member is used for handling file open requests that result in calls to the [**MRxCreate**](/windows-hardware/drivers/ifs/mrxcreate) routine. This member is also used for prefix resolution requests. RDBSS passes information in the **Create** structure member to the network mini-redirector and the network mini-redirector returns information to RDBSS in the **Create** structure member.

### -field Create.NtCreateParameters

The create parameters passed to the user-mode **NtCreatefile** routine. RDBSS sets the members of the **NtCreateParameters** structure based on the **Parameters.Create** members of the IRP.

### -field Create.ReturnedCreateInformation

A value set by the network mini-redirector on completion of the **MRxCreate** call.

### -field Create.CanonicalNameBuffer

A pointer to the Unicode string representing the name of physical file to open if the canonical name is larger than the available buffer.

### -field Create.NetNamePrefixEntry

A pointer to the NetName table prefix entry. This member is reserved for internal use.

### -field Create.pSrvCall

A pointer to the associated SRV_CALL structure.

### -field Create.pNetRoot

A pointer to the associated NET_ROOT structure.

### -field Create.pVNetRoot

A pointer to the associated V_NET_ROOT structure.

### -field Create.EaBuffer

A pointer to the extended attributes buffer. This member is optional.

### -field Create.EaLength

The length of the extended attributes buffer, **EaBuffer**.

### -field Create.SdLength

The length of the security descriptor. RDBSS sets this based on the value of the **Parameters.Create.SecurityContext** member of the IRP. If the **SdLength** member is nonzero, the security descriptor is passed in the **Info.Buffer** member to the network mini-redirector.

### -field Create.PipeType

The type of a pipe. This member is reserved for internal use.

### -field Create.PipeReadMode

The read mode for a pipe. This member is reserved for internal use.

### -field Create.PipeCompletionMode

The completion mode for a pipe. This member is reserved for internal use.

### -field Create.Flags

The create flags

### -field Create.Type

The type of the associated NET_ROOT structure.

### -field Create.RdrFlags

### -field Create.FcbAcquired

This member is reserved for internal use.

### -field Create.TryForScavengingOnSharingViolation

This member is reserved for internal use.

### -field Create.ScavengingAlreadyTried

This member is reserved for internal use.

### -field Create.ThisIsATreeConnectOpen

A Boolean value that indicates if this call is a tree connect open request with the FILE_CREATE_TREE_CONNECTION option set in the **IrpSp->Parameters.Create.Options** member.

### -field Create.TreeConnectOpenDeferred

A Boolean value that indicates the network mini-redirector can choose to defer the tree connect open request.

### -field Create.TransportName

A Unicode string that represents the transport name. This member is set from the tree connect open parameters.

### -field Create.UserName

A Unicode string that represents the user name responsible for the request. This member is set from the tree connect open parameters.

### -field Create.Password

A Unicode string that contains the password for this **UserName** used for authentication and authorization. This member is set from the tree connect open parameters.

### -field Create.UserDomainName

A Unicode string that contains the domain name for this **UserName**.

### -field QueryDirectory

A structure member of an unnamed union used for handling [**IRP_MJ_DIRECTORY_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-directory-control) requests. This member is used for handling query directory requests that result in calls to the **MrxQueryDirectory** routine. RDBSS passes information in the **QueryDirectory** structure member to the network mini-redirector.

### -field QueryDirectory.FileIndex

The Index of the entry at which to begin scanning the directory if the **IndexSpecified** member is set to TRUE. This parameter is set to the **IrpSp->Parameters.QueryDirectory.FileIndex** member.

### -field QueryDirectory.RestartScan

A Boolean value when set to TRUE indicates that the scan is to start at the first entry in the directory. When this value is set to FALSE, the scan is resuming from a previous call. This parameter must be set to TRUE when calling for the first time. This parameter is set to TRUE if **IrpSp->Flags** has the SL_RESTART_SCAN bit on.

### -field QueryDirectory.ReturnSingleEntry

A Boolean value set to TRUE indicates that only a single entry should be returned. If this parameter is TRUE, **MrxQueryDirectory** should return only the first entry that is found. This parameter is set to TRUE if **IrpSp->Flags** has the SL_RETURN_SINGLE_ENTRY bit on.

### -field QueryDirectory.IndexSpecified

A Boolean value when set to TRUE indicates to begin the scan at the entry in the directory whose index is given by the **FileIndex** member. This parameter is set to TRUE if **IrpSp->Flags** has the SL_INDEX_SPECIFIED bit on.

### -field QueryDirectory.InitialQuery

A Boolean value that is set to TRUE when the query is not a wild card query ("*.*", for example). This member is set to TRUE if the **UnicodeQueryTemplate.Buffer** member of the associated FOBX is NULL and the **Flags** member of the FOBX does not have the FOBX_FLAG_MATCH_ALL bit on. For a wild card query ("*.*", for example), RDBSS will set the **UnicodeQueryTemplate.Buffer** member of the associated FOBX to the wild card query passed.

### -field NotifyChangeDirectory

A structure member of an unnamed union used for handling IRP_MJ_DIRECTORY_CONTROL requests with a minor function of IRP_MN_NOTIFY_CHANGE_DIRECTORY. This member is used for handling directory change requests that result in calls to the [**MRxLowIOSubmit\[LOWIO_OP_NOTIFY_CHANGE_DIRECTORY\]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-notify-change-directory-) routine. RDBSS passes information in the **NotifyChangeDirectory** structure member and the **pLowIoContext->ParamsFor.NotifyChangeDirectory** structure to the network mini-redirector.

### -field NotifyChangeDirectory.pVNetRoot

A pointer to the V_NET_ROOT structure associated with the directory. This parameter is set to the **IrpSp->FileObject->FsContext** member or the **IrpSp->FileObject->FsContext2** member depending on the node type.

### -field QueryEa

A structure member of an unnamed union used for handling [**IRP_MJ_QUERY_EA**](/windows-hardware/drivers/ifs/irp-mj-query-ea) requests. This member is used for handling extended attribute query requests that result in calls to the [**MRxQueryEaInfo**](/windows-hardware/drivers/ifs/mrxqueryeainfo) routine. RDBSS passes information in the **QueryEa** structure member to the network mini-redirector.

### -field QueryEa.UserEaList

A pointer to a caller-supplied input buffer containing a [**FILE_GET_EA_INFORMATION**](../ntifs/ns-ntifs-_file_get_ea_information.md) structure specifying the extended attributes to be queried. This parameter is set to **IrpSp->Parameters.QueryEa.EaList**.

### -field QueryEa.UserEaListLength

The length, in bytes, of the buffer pointed to by **UserEaList** member. This parameter is set to **IrpSp->Parameters.QueryEa.EaListLength**.

### -field QueryEa.UserEaIndex

The Index of the entry at which to begin scanning the extended-attribute list. This parameter should be ignored if the **IndexSpecified** member is not set to TRUE or if **QueryEaList** member points to a nonempty list. This parameter is set to **IrpSp->Parameters.QueryEa.EaIndex**.

### -field QueryEa.RestartScan

A Boolean value when set to TRUE indicates that the query is to start at the first extended attribute entry. When this value is set to FALSE, the scan is resuming from a previous call. This parameter must be set to TRUE when calling for the first time. This parameter is set to **TRUE if IrpSp->Flags** has the SL_RESTART_SCAN bit on.

### -field QueryEa.ReturnSingleEntry

A Boolean value when set to TRUE indicates that only a single entry should be returned. If this parameter is TRUE, MrxQueryEaInfo should return only the first entry that is found. This parameter is set to TRUE if **IrpSp->Flags** has the SL_RETURN_SINGLE_ENTRY bit on.

### -field QueryEa.IndexSpecified

A Boolean value when set to TRUE indicates to begin the scan at the entry in the extended attributes whose index is given by the **UserEaIndex** member. This parameter is set to TRUE if **IrpSp->Flags** has the SL_INDEX_SPECIFIED bit on.

### -field QuerySecurity

A structure member of an unnamed union used for handling [**IRP_MJ_QUERY_SECURITY**](/windows-hardware/drivers/ifs/irp-mj-query-security) requests. This member is used for handling query security requests that result in calls to the [**MRxQuerySdInfo**](/windows-hardware/drivers/ifs/mrxquerysdinfo) routine. RDBSS passes information in the **QuerySecurity** structure member to the network mini-redirector.

### -field QuerySecurity.SecurityInformation

A pointer to a caller-supplied input buffer containing a SECURITY_INFORMATION structure specifying the operation to be queried. This parameter is set to **IrpSp->Parameters.QuerySecurity.SecurityInformation**.

### -field QuerySecurity.Length

The length, in bytes, of the buffer pointed to by **SecurityInformation** member. This parameter is set to **IrpSp->Parameters.QuerySecurity.Length**.

### -field SetSecurity

A structure member of an unnamed union used for handling [**IRP_MJ_SET_SECURITY**](/windows-hardware/drivers/ifs/irp-mj-set-security) requests. This member is used for handling query security requests that result in calls to the [**MRxSetSdInfo**](/windows-hardware/drivers/ifs/mrxsetsdinfo) routine. RDBSS passes information in the **SetSecurity** structure member to the network mini-redirector.

### -field SetSecurity.SecurityInformation

A pointer to a caller-supplied input buffer containing a SECURITY_INFORMATION structure that specifies which security information is to be set in the security descriptor. This parameter is set to **IrpSp->Parameters.SetSecurity.SecurityInformation**.

### -field SetSecurity.SecurityDescriptor

A pointer to a SECURITY_DESCRIPTOR structure that contains the values of the security information to be assigned to the object. This parameter is set to **IrpSp->Parameters.SetSecurity.SecurityDescriptor**.

### -field QueryQuota

A structure member of an unnamed union used for handling [**IRP_MJ_QUERY_QUOTA**](/windows-hardware/drivers/ifs/irp-mj-query-quota) requests. This member is used for handling query security requests that result in calls to the [**MRxQueryQuotaInfo**](/windows-hardware/drivers/ifs/mrxqueryquotainfo) routine. RDBSS passes information in the **QueryQuota** structure member to the network mini-redirector.

### -field QueryQuota.Length

The length, in bytes, of the buffer pointed to by **StartSid** member. This parameter is set to **IrpSp->Parameters.QueryQuota.Length**.

### -field QueryQuota.StartSid

An optional pointer to a SID that indicates that the returned information is to start with an entry other than the first entry. This parameter is ignored if the **SidList** member is specified. This parameter is set to **IrpSp->Parameters.QueryQuota.StartSid**.

### -field QueryQuota.SidList

An optional pointer to a list of SIDs whose quota information is to be returned. Each entry in the list is a FILE_GET_QUOTA_INFORMATION structure. This parameter is set to **IrpSp->Parameters.QueryQuota.SidList**.

### -field QueryQuota.SidListLength

The length, in bytes, of the list of SIDs in the **SidList** member, if one is specified. This parameter is set to **IrpSp->Parameters.QueryQuota.SidListLength**.

### -field QueryQuota.RestartScan

A Boolean value when set to TRUE indicates that the query is to start at the first entry. When this value is set to FALSE, the scan is resuming from a previous call. This parameter must be set to TRUE when calling for the first time. This parameter is set to TRUE if **IrpSp->Flags**has the SL_RESTART_SCAN bit on.

### -field QueryQuota.ReturnSingleEntry

A Boolean value when set to TRUE indicates that only a single entry should be returned. If this parameter is TRUE, MrxQueryQuotaInfo should return only the first entry that is found. This parameter is set to TRUE if **IrpSp->Flags** has the SL_RETURN_SINGLE_ENTRY bit on.

### -field QueryQuota.IndexSpecified

A Boolean value when set to TRUE indicates to begin the scan at the entry in the list whose index is given by the **StartSid** member. This parameter is set to TRUE if **IrpSp->Flags** has the SL_INDEX_SPECIFIED bit on.

### -field SetQuota

A structure member of an unnamed union used for handling [**IRP_MJ_SET_QUOTA**](/windows-hardware/drivers/ifs/irp-mj-set-quota) requests. This structure is not currently used by RDBSS.

### -field SetQuota.Length

An unused member of the **SetQuota** structure.

### -field DosVolumeFunction

A structure member of an unnamed union. This structure is not currently used by RDBSS.

### -field DosVolumeFunction.VNetRoot

An unused member of the **DosVolumeFunction** structure.

### -field DosVolumeFunction.SrvCall

An unused member of the **DosVolumeFunction** structure.

### -field DosVolumeFunction.NetRoot

An unused member of the **DosVolumeFunction** structure.

### -field FlagsForLowIo

A set of [**RX_CONTENT_CREATE_FLAGS**](ne-rxcontx-rx_context_create_flags.md) set by RDBSS and passed to low I/O operations sent to the network mini-redirector. **FlagsForLowIo** is a member of an unnamed structure used for low I/O requests to the network mini-redirector.

### -field LowIoContext

A pointer to a **LOWIO_CONTEXT** structure passed to the network mini-redirector. **LowIoContext** is a member of unnamed structure used for low I/O requests sent to the network mini-redirector.

### -field AlsoCanonicalNameBuffer

A pointer to the Unicode string representing the name of physical file to open if the canonical name is larger than the available buffer.

### -field LoudCompletionString

An unused member of the RX_CONTEXT structure.

### -field AcquireReleaseFcbTrackerX

Reserved for system use.

### -field TrackerHistoryPointer

Reserved for system use.

### -field TrackerHistory[RDBSS_TRACKER_HISTORY_SIZE]

Reserved for system use.

### -field ShadowCritOwner

Reserved for system use.

## -remarks

The **RX_CONTEXT** structure is one of the fundamental data structures used by RDBSS and network mini-redirectors to manage an I/O request packet (IRP). It encapsulates an IRP for use by RDBSS, network mini-redirectors, and the file system. An **RX_CONTEXT** structure includes a pointer to a single IRP and all of the context required to process the IRP.

An **RX_CONTEXT** structure is sometimes referred to as an IRP Context or RxContext in the WDK header files and other resources used for developing network mini-redirector drivers.

The **RX_CONTEXT** is a data structure to which additional information provided by the various network mini redirectors is attached. The **RX_CONTEXT** includes fields for over allocating the size of each **RX_CONTEXT** structure by a pre-specified amount for each network mini redirector, which is then reserved for use by the mini redirector. This approach consists of allocating a pre-specified area, which is the same for all network mini redirectors as part of each RX_CONTEXT. This is an unformatted area on top of which any desired structure can be imposed by the various network mini redirectors. Developers of network mini-redirector drivers should try and define the associated private context to fit into this pre-specified area defined in the RX_CONTEXT data structure. Network mini-redirector drivers that violate this rule will incur a significant performance penalty.

Many RDBSS routines and routines exported by a network mini-redirector make reference to RX_CONTEXT structures in either the initiating thread or in some other thread used by the routine. Thus, allocated RX_CONTEXT structures are reference counted to manage their use for asynchronous operations. When the reference count goes to zero, the allocated RX_CONTEXT structure can be finalized and released on the last dereference operation.

RDBSS provides a number of routines that are used to manipulate an RX_CONTEXT and the associated IRP. These routines are used to allocate, initialize, and delete an RX_CONTEXT. These routines are also used to complete the IRP associated with an RX_CONTEXT and set up a cancel routine for an RX_CONTEXT.

## -see-also

[**FILE_GET_EA_INFORMATION**](../ntifs/ns-ntifs-_file_get_ea_information.md)

[**IOCTL_REDIR_QUERY_PATH**](../ntifs/ni-ntifs-ioctl_redir_query_path.md)
  
[**IOCTL_REDIR_QUERY_PATH_EX**](../ntifs/ni-ntifs-ioctl_redir_query_path_ex.md)  

[**IRP_MJ_CREATE**](/windows-hardware/drivers/ifs/irp-mj-create)

[**IRP_MJ_DEVICE_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-device-control)  

[**IRP_MJ_DIRECTORY_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-directory-control)  

[**IRP_MJ_QUERY_EA**](/windows-hardware/drivers/ifs/irp-mj-query-ea)  

[**IRP_MJ_QUERY_QUOTA**](/windows-hardware/drivers/ifs/irp-mj-query-quota)  

[**IRP_MJ_QUERY_SECURITY**](/windows-hardware/drivers/ifs/irp-mj-query-security)  

[**IRP_MJ_SET_QUOTA**](/windows-hardware/drivers/ifs/irp-mj-set-quota)  

[**IRP_MJ_SET_SECURITY**](/windows-hardware/drivers/ifs/irp-mj-set-security)  

[**IoCompletion**](../wdm/nc-wdm-io_completion_routine.md)  

[**IoMarkIrpPending**](../wdm/nf-wdm-iomarkirppending.md)  

[**MRxCreate**](/windows-hardware/drivers/ifs/mrxcreate)  

[**MRxLowIOSubmit\[LOWIO_OP_NOTIFY_CHANGE_DIRECTORY\]**](/windows-hardware/drivers/ifs/mrxlowiosubmit-lowio-op-notify-change-directory-)  

[**MRxQueryDirectory**](/windows-hardware/drivers/ifs/mrxquerydirectory)  

[**MRxQueryEaInfo**](/windows-hardware/drivers/ifs/mrxqueryeainfo)  

[**MRxQueryFileInfo**](/windows-hardware/drivers/ifs/mrxqueryfileinfo)  

[**MRxQueryQuotaInfo**](/windows-hardware/drivers/ifs/mrxqueryquotainfo)  

[**MRxQuerySdInfo**](/windows-hardware/drivers/ifs/mrxquerysdinfo)  

[**MRxQueryVolumeInfo**](/windows-hardware/drivers/ifs/mrxqueryvolumeinfo)  

[**MRxSetFileInfo**](/windows-hardware/drivers/ifs/mrxsetfileinfo)  

[**MRxSetFileInfoAtCleanup**](/windows-hardware/drivers/ifs/mrxsetfileinfoatcleanup)  

[**MRxSetSdInfo**](/windows-hardware/drivers/ifs/mrxsetsdinfo)  

[**MRxSetVolumeInfo**](/windows-hardware/drivers/ifs/mrxsetvolumeinfo)  

[**RxCreateRxContext**](nf-rxcontx-rxcreaterxcontext.md)  

[**RxInitializeContext**](nf-rxcontx-rxinitializecontext.md)

[**RxStartMinirdr**](../mrx/nf-mrx-rxstartminirdr.md)
