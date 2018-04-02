---
UID: NA:wdm
ms.assetid: 8462c1fe-6be6-3c3a-88f8-fb7aba330515
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wdm.h header



This header is used by Windows kernel, Installable file system, PCI, Driver test tools, Benchmark, Windows Driver Framework, Battery. For more information, see
- [Windows kernel](../_kernel/index.md)
- [Installable file system](../_ifsk/index.md)
- [PCI](../_PCI/index.md)
- [Driver test tools](../_devtest/index.md)
- [Benchmark](../_Benchmark/index.md)
- [Windows Driver Framework](../_wdf/index.md)
- [Battery](../_battery/index.md)

Wdm.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [AppendTailList function](nf-wdm-appendtaillist.md) | The AppendTailList routine appends a doubly linked list of LIST_ENTRY structures to the tail of another doubly linked list of LIST_ENTRY structures. |
| [ClfsAddLogContainer function](nf-wdm-clfsaddlogcontainer.md) | The ClfsAddLogContainer routine adds a container to a CLFS log. |
| [ClfsAddLogContainerSet function](nf-wdm-clfsaddlogcontainerset.md) | The ClfsAddLogContainerSet routine atomically adds a set of containers to a CLFS log. |
| [ClfsAdvanceLogBase function](nf-wdm-clfsadvancelogbase.md) | The ClfsAdvanceLogBase routine sets the base LSN of a CLFS stream. |
| [ClfsAlignReservedLog function](nf-wdm-clfsalignreservedlog.md) | The ClfsAlignReservedLog routine calculates the size of the space that must be reserved for a specified set of records. The size calculation includes the space required for headers and the space required for sector alignment. |
| [ClfsAllocReservedLog function](nf-wdm-clfsallocreservedlog.md) | The ClfsAllocReservedLog routine reserves space in a marshalling area for a set of records. |
| [ClfsCloseAndResetLogFile function](nf-wdm-clfscloseandresetlogfile.md) | The ClfsCloseAndResetLogFile routine releases all references to a specified log file object and marks its associated stream for reset. |
| [ClfsCloseLogFileObject function](nf-wdm-clfscloselogfileobject.md) | The ClfsCloseLogFileObject routine releases all references to a log file object. |
| [ClfsCreateLogFile function](nf-wdm-clfscreatelogfile.md) | The ClfsCreateLogFile routine creates or opens a CLFS stream. If necessary, ClfsCreateLogFile also creates the underlying physical log that holds the stream's records. |
| [ClfsCreateMarshallingArea function](nf-wdm-clfscreatemarshallingarea.md) | The ClfsCreateMarshallingArea routine creates a marshalling area for a CLFS stream and returns a pointer to an opaque context that represents the new marshalling area. |
| [ClfsCreateScanContext function](nf-wdm-clfscreatescancontext.md) | The ClfsCreateScanContext routine creates a scan context that can be used to iterate over the containers of a specified CLFS log. |
| [ClfsDeleteLogByPointer function](nf-wdm-clfsdeletelogbypointer.md) | The ClfsDeleteLogByPointer routine marks a CLFS stream for deletion. |
| [ClfsDeleteLogFile function](nf-wdm-clfsdeletelogfile.md) | The ClfsDeleteLogFile routine marks a CLFS stream for deletion. |
| [ClfsDeleteMarshallingArea function](nf-wdm-clfsdeletemarshallingarea.md) | The ClfsDeleteMarshallingArea routine deletes a marshalling area. |
| [ClfsFlushBuffers function](nf-wdm-clfsflushbuffers.md) | The ClfsFlushBuffers routine forces all log I/O blocks in a specified marshalling area to stable storage. |
| [ClfsFlushToLsn function](nf-wdm-clfsflushtolsn.md) | The ClfsFlushToLsn routine forces, to stable storage, all records that have an LSN less than or equal to a specified LSN. |
| [ClfsGetContainerName function](nf-wdm-clfsgetcontainername.md) | The ClfsGetContainerName routine returns the path name of a specified container. |
| [ClfsGetIoStatistics function](nf-wdm-clfsgetiostatistics.md) | The ClfsGetIoStatistics routine returns I/O statistics for a specified CLFS log. |
| [ClfsLsnBlockOffset function](nf-wdm-clfslsnblockoffset.md) | The ClfsLsnBlockOffset routine returns the sector-aligned block offset contained in a specified LSN. |
| [ClfsLsnContainer function](nf-wdm-clfslsncontainer.md) | The ClfsLsnContainer routine returns the logical container identifier contained in a specified LSN. |
| [ClfsLsnCreate function](nf-wdm-clfslsncreate.md) | The ClfsLsnCreate routine creates a log sequence number (LSN), given a container identifier, a block offset, and a record sequence number. |
| [ClfsLsnEqual function](nf-wdm-clfslsnequal.md) | The ClfsLsnEqual routine determines whether two LSNs from the same stream are equal. |
| [ClfsLsnGreater function](nf-wdm-clfslsngreater.md) | The ClfsLsnGreater routine determines whether one LSN is greater than another LSN. The two LSNs must be from the same stream. |
| [ClfsLsnLess function](nf-wdm-clfslsnless.md) | The ClfsLsnLess routine determines whether one LSN is less than another LSN. The two LSNs must be from the same stream. |
| [ClfsLsnNull function](nf-wdm-clfslsnnull.md) | The ClfsLsnNull routine determines whether a specified LSN is equal to the smallest possible LSN, CLFS_LSN_NULL. |
| [ClfsLsnRecordSequence function](nf-wdm-clfslsnrecordsequence.md) | The ClfsLsnRecordSequence routine returns the record sequence number contained in a specified LSN. |
| [ClfsMgmtDeregisterManagedClient function](nf-wdm-clfsmgmtderegistermanagedclient.md) | The ClfsMgmtDeregisterManagedClient routine removes the connection between a client and a log, so that the client no longer manages the log. |
| [ClfsMgmtHandleLogFileFull function](nf-wdm-clfsmgmthandlelogfilefull.md) | The ClfsMgmtHandleLogFileFull routine attempts to make more space available in a log. It might make more space available by adding containers to the log, or it might ask clients to move their log tails. |
| [ClfsMgmtInstallPolicy function](nf-wdm-clfsmgmtinstallpolicy.md) | The ClfsMgmtInstallPolicy routine adds a CLFS_MGMT_POLICY structure to a physical log. |
| [ClfsMgmtQueryPolicy function](nf-wdm-clfsmgmtquerypolicy.md) | The ClfsMgmtQueryPolicy routine retrieves a specific CLFS_MGMT_POLICY structure for a log. |
| [ClfsMgmtRegisterManagedClient function](nf-wdm-clfsmgmtregistermanagedclient.md) | The ClfsMgmtRegisterManagedClient routine creates a client that will manage a CLFS log. |
| [ClfsMgmtRemovePolicy function](nf-wdm-clfsmgmtremovepolicy.md) | The ClfsMgmtRemovePolicy routine resets a log's CLFS_MGMT_POLICY structure to its default value. |
| [ClfsMgmtSetLogFileSize function](nf-wdm-clfsmgmtsetlogfilesize.md) | The ClfsMgmtSetLogFileSize routine adds containers to a log or deletes containers from a log. |
| [ClfsMgmtSetLogFileSizeAsClient function](nf-wdm-clfsmgmtsetlogfilesizeasclient.md) | The ClfsMgmtSetLogFileSizeAsClient routine sets the log file size by adding containers to a client log or deleting containers from a client log. |
| [ClfsMgmtTailAdvanceFailure function](nf-wdm-clfsmgmttailadvancefailure.md) | The ClfsMgmtTailAdvanceFailure routine notifies CLFS management that the client could not advance the log's tail. |
| [ClfsQueryLogFileInformation function](nf-wdm-clfsquerylogfileinformation.md) | The ClfsQueryLogFileInformation routine returns metadata and state information for a specified CLFS stream or its underlying physical log or both. |
| [ClfsReadLogRecord function](nf-wdm-clfsreadlogrecord.md) | The ClfsReadLogRecord routine reads a target record in a CLFS stream and returns a read context that the caller can use to read the records preceding or following it in the stream. |
| [ClfsReadNextLogRecord function](nf-wdm-clfsreadnextlogrecord.md) | The ClfsReadNextLogRecord routine reads the next record in a sequence, relative to the current record in a read context. |
| [ClfsReadPreviousRestartArea function](nf-wdm-clfsreadpreviousrestartarea.md) | The ClfsReadPreviousRestartArea routine reads the previous restart record relative to the current record in a read context. |
| [ClfsReadRestartArea function](nf-wdm-clfsreadrestartarea.md) | The ClfsReadRestartArea routine reads the restart record that was most recently written to a specified CLFS stream. |
| [ClfsRemoveLogContainer function](nf-wdm-clfsremovelogcontainer.md) | The ClfsRemoveLogContainer routine removes a container from a CLFS log. |
| [ClfsRemoveLogContainerSet function](nf-wdm-clfsremovelogcontainerset.md) | The ClfsRemoveLogContainerSet routine atomically removes a set of containers from a CLFS log. |
| [ClfsReserveAndAppendLog function](nf-wdm-clfsreserveandappendlog.md) | The ClfsReserveAndAppendLog routine reserves space in a marshalling area or appends a record to a marshalling area or does both atomically. |
| [ClfsReserveAndAppendLogAligned function](nf-wdm-clfsreserveandappendlogaligned.md) | The ClfsReserveAndAppendLogAligned routine reserves space in a marshalling area or appends a record to a marshalling area or does both atomically. The record's data is aligned on specified boundaries. |
| [ClfsScanLogContainers function](nf-wdm-clfsscanlogcontainers.md) | The ClfsScanLogContainers routine retrieves descriptive information for a sequence of containers that belong to a particular CLFS log. |
| [ClfsSetArchiveTail function](nf-wdm-clfssetarchivetail.md) | The ClfsSetArchiveTail routine sets the archive tail of a CLFS log to a specified LSN. |
| [ClfsSetEndOfLog function](nf-wdm-clfssetendoflog.md) | The ClfsSetEndOfLog routine truncates a CLFS stream. |
| [ClfsSetLogFileInformation function](nf-wdm-clfssetlogfileinformation.md) | The ClfsSetLogFileInformation routine sets metadata and state information for a specified stream and its underlying physical log. |
| [ClfsTerminateReadLog function](nf-wdm-clfsterminatereadlog.md) | The ClfsTerminateReadLog routine invalidates a specified read context after freeing resources associated with the context. |
| [ClfsWriteRestartArea function](nf-wdm-clfswriterestartarea.md) | The ClfsWriteRestartArea routine atomically appends a new restart record to a CLFS stream, flushes the restart record to stable storage, and optionally updates the base LSN of the stream. |
| [CmCallbackGetKeyObjectID function](nf-wdm-cmcallbackgetkeyobjectid.md) | The CmCallbackGetKeyObjectID routine retrieves the unique identifier and object name that are associated with a specified registry key object. |
| [CmCallbackGetKeyObjectIDEx function](nf-wdm-cmcallbackgetkeyobjectidex.md) | The CmCallbackGetKeyObjectIDEx routine retrieves the unique identifier and object name that are associated with a specified registry key object. |
| [CmCallbackReleaseKeyObjectIDEx function](nf-wdm-cmcallbackreleasekeyobjectidex.md) | The CmCallbackReleaseKeyObjectIDEx routine frees an object name string obtained from the CmCallbackGetKeyObjectIDEx routine. |
| [CmGetBoundTransaction function](nf-wdm-cmgetboundtransaction.md) | The CmGetBoundTransaction routine returns a pointer to the transaction object that represents the transaction, if any, that is associated with a specified registry key object. |
| [CmGetCallbackVersion function](nf-wdm-cmgetcallbackversion.md) | The CmGetCallbackVersion routine retrieves the major and minor version numbers for the current version of the configuration manager's registry callback feature. |
| [CmRegisterCallback function](nf-wdm-cmregistercallback.md) | The CmRegisterCallback routine is obsolete for Windows Vista and later operating system versions. Use CmRegisterCallbackEx instead.The CmRegisterCallback routine registers a RegistryCallback routine. |
| [CmRegisterCallbackEx function](nf-wdm-cmregistercallbackex.md) | The CmRegisterCallbackEx routine registers a RegistryCallback routine. |
| [CmSetCallbackObjectContext function](nf-wdm-cmsetcallbackobjectcontext.md) | The CmSetCallbackObjectContext routine associates specified context information with a specified registry object. |
| [CmUnRegisterCallback function](nf-wdm-cmunregistercallback.md) | The CmUnRegisterCallback routine unregisters a RegistryCallback routine that a CmRegisterCallback or CmRegisterCallbackEx routine previously registered. |
| [DbgBreakPoint function](nf-wdm-dbgbreakpoint.md) | The DbgBreakPoint routine breaks into the kernel debugger. |
| [DbgBreakPointWithStatus function](nf-wdm-dbgbreakpointwithstatus.md) | The DbgBreakPointWithStatus routine breaks into the kernel debugger and sends the value of Status to the debugger. |
| [DbgPrint function](nf-wdm-dbgprint.md) | The DbgPrint routine sends a message to the kernel debugger. |
| [DbgPrintEx function](nf-wdm-dbgprintex.md) | The DbgPrintEx routine sends a string to the kernel debugger if the conditions you specify are met. |
| [EtwActivityIdControl function](nf-wdm-etwactivityidcontrol.md) | The EtwActivityIdControl function creates, queries, and sets the current activity identifier. |
| [EtwEventEnabled function](nf-wdm-etweventenabled.md) | The EtwEventEnabled function verifies whether an event is enabled. |
| [EtwProviderEnabled function](nf-wdm-etwproviderenabled.md) | The EtwProviderEnabled function verifies that a provider is enabled for event logging at a specified level and keyword. |
| [EtwRegister function](nf-wdm-etwregister.md) | The EtwRegister function registers the event provider and must be called before a provider can start tracing. |
| [EtwUnregister function](nf-wdm-etwunregister.md) | The EtwUnregister function unregisters the event provider and must be called before the provider exits. |
| [EtwWrite function](nf-wdm-etwwrite.md) | The EtwWrite function is a tracing function for publishing events in your kernel-mode driver code. |
| [EtwWriteEx function](nf-wdm-etwwriteex.md) | The EtwWriteEx function is a tracing function for publishing events that support filtering in your kernel-mode driver code. |
| [EtwWriteString function](nf-wdm-etwwritestring.md) | The EventWriteString function is a tracing function that you can use when no sophisticated data is required. This function is similar to a debug print statement. |
| [EtwWriteTransfer function](nf-wdm-etwwritetransfer.md) | The EtwWriteTransfer function marks an event that links two activities together; this type of event is referred to as a transfer event. |
| [ExAcquireResourceExclusiveLite function](nf-wdm-exacquireresourceexclusivelite.md) | The ExAcquireResourceExclusiveLite routine acquires the given resource for exclusive access by the calling thread. |
| [ExAcquireResourceSharedLite function](nf-wdm-exacquireresourcesharedlite.md) | The ExAcquireResourceSharedLite routine acquires the given resource for shared access by the calling thread. |
| [ExAcquireRundownProtection function](nf-wdm-exacquirerundownprotection.md) | The ExAcquireRundownProtection routine tries to acquire run-down protection on a shared object so the caller can safely access the object. |
| [ExAcquireRundownProtectionEx function](nf-wdm-exacquirerundownprotectionex.md) | The ExAcquireRundownProtectionEx routine tries to acquire run-down protection on a shared object so the caller can safely access the object. |
| [ExAcquireSharedStarveExclusive function](nf-wdm-exacquiresharedstarveexclusive.md) | The ExAcquireSharedStarveExclusive routine acquires a given resource for shared access without waiting for any pending attempts to acquire exclusive access to the same resource. |
| [ExAcquireSharedWaitForExclusive function](nf-wdm-exacquiresharedwaitforexclusive.md) | The ExAcquireSharedWaitForExclusive routine acquires the given resource for shared access if shared access can be granted and there are no exclusive waiters. |
| [ExAllocateFromLookasideListEx function](nf-wdm-exallocatefromlookasidelistex.md) | The ExAllocateFromLookasideListEx routine removes the first entry from the specified lookaside list, or, if the list is empty, dynamically allocates the storage for a new entry. |
| [ExAllocateFromNPagedLookasideList function](nf-wdm-exallocatefromnpagedlookasidelist.md) | The ExAllocateFromNPagedLookasideList routine returns a pointer to a nonpaged entry from the given lookaside list, or it returns a pointer to a newly allocated nonpaged entry. |
| [ExAllocateFromPagedLookasideList function](nf-wdm-exallocatefrompagedlookasidelist.md) | The ExAllocateFromPagedLookasideList routine returns a pointer to a paged entry from the given lookaside list, or it returns a pointer to a newly allocated paged entry. |
| [ExAllocatePool function](nf-wdm-exallocatepool.md) | The ExAllocatePool routine is obsolete, and is exported only for existing binaries. Use ExAllocatePoolWithTag instead.ExAllocatePool allocates pool memory of the specified type and returns a pointer to the allocated block. |
| [ExAllocatePoolWithQuota function](nf-wdm-exallocatepoolwithquota.md) | The ExAllocatePoolWithQuota routine is obsolete, and is exported only for existing driver binaries. Use ExAllocatePoolWithQuotaTag instead.ExAllocatePoolWithQuota allocates pool memory, charging quota against the current process. |
| [ExAllocatePoolWithQuotaTag function](nf-wdm-exallocatepoolwithquotatag.md) | The ExAllocatePoolWithQuotaTag routine allocates pool memory, charging the quota against the current process. |
| [ExAllocatePoolWithTag function](nf-wdm-exallocatepoolwithtag.md) | The ExAllocatePoolWithTag routine allocates pool memory of the specified type and returns a pointer to the allocated block. |
| [ExAllocatePoolWithTagPriority function](nf-wdm-exallocatepoolwithtagpriority.md) | The ExAllocatePoolWithTagPriority routine allocates pool memory of the specified type. |
| [ExAllocateTimer function](nf-wdm-exallocatetimer.md) | The ExAllocateTimer routine allocates and initializes a timer object. |
| [ExCancelTimer function](nf-wdm-excanceltimer.md) | The ExCancelTimer routine cancels a timer that was set by a previous call to the ExSetTimer routine. |
| [ExConvertExclusiveToSharedLite function](nf-wdm-exconvertexclusivetosharedlite.md) | The ExConvertExclusiveToSharedLite routine converts a given resource from acquired for exclusive access to acquired for shared access. |
| [ExCreateCallback function](nf-wdm-excreatecallback.md) | The ExCreateCallback routine either creates a new callback object or opens an existing callback object on behalf of the caller. |
| [ExDeleteLookasideListEx function](nf-wdm-exdeletelookasidelistex.md) | The ExDeleteLookasideListEx routine deletes a lookaside list. |
| [ExDeleteNPagedLookasideList function](nf-wdm-exdeletenpagedlookasidelist.md) | The ExDeleteNPagedLookasideList routine destroys a nonpaged lookaside list. |
| [ExDeletePagedLookasideList function](nf-wdm-exdeletepagedlookasidelist.md) | The ExDeletePagedLookasideList routine destroys a paged lookaside list. |
| [ExDeleteResourceLite function](nf-wdm-exdeleteresourcelite.md) | The ExDeleteResourceLite routine deletes a given resource from the system's resource list. |
| [ExDeleteTimer function](nf-wdm-exdeletetimer.md) | The ExDeleteTimer routine deletes a timer object that was previously allocated by the ExAllocateTimer routine. |
| [ExFlushLookasideListEx function](nf-wdm-exflushlookasidelistex.md) | The ExFlushLookasideListEx routine flushes all entries from the specified lookaside list and frees the allocated storage for each entry. |
| [ExFreePool function](nf-wdm-exfreepool.md) | The ExFreePool routine deallocates a block of pool memory. |
| [ExFreePoolWithTag function](nf-wdm-exfreepoolwithtag.md) | The ExFreePoolWithTag routine deallocates a block of pool memory allocated with the specified tag. |
| [ExFreeToLookasideListEx function](nf-wdm-exfreetolookasidelistex.md) | The ExFreeToLookasideListEx routine inserts an entry into a lookaside list, or, if the list is full, frees the allocated storage for the entry. |
| [ExFreeToNPagedLookasideList function](nf-wdm-exfreetonpagedlookasidelist.md) | The ExFreeToNPagedLookasideList routine returns a nonpaged entry to the given lookaside list or to nonpaged pool. |
| [ExFreeToPagedLookasideList function](nf-wdm-exfreetopagedlookasidelist.md) | The ExFreeToPagedLookasideList routine returns a pageable entry to the given lookaside list or to paged pool. |
| [ExGetExclusiveWaiterCount function](nf-wdm-exgetexclusivewaitercount.md) | The ExGetExclusiveWaiterCount routine returns the number of waiters on exclusive access to a given resource. |
| [ExGetFirmwareEnvironmentVariable function](nf-wdm-exgetfirmwareenvironmentvariable.md) | The ExGetFirmwareEnvironmentVariable routine gets the value of the specified system firmware environment variable. |
| [ExGetFirmwareType function](nf-wdm-exgetfirmwaretype.md) | Returns the system firmware type. |
| [ExGetPreviousMode function](nf-wdm-exgetpreviousmode.md) | The ExGetPreviousMode routine returns the previous processor mode for the current thread. |
| [ExGetSharedWaiterCount function](nf-wdm-exgetsharedwaitercount.md) | The ExGetSharedWaiterCount routine returns the number of waiters on shared access to a given resource. |
| [ExInitializeDeleteTimerParameters function](nf-wdm-exinitializedeletetimerparameters.md) | The ExInitializeDeleteTimerParameters routine initializes an EXT_DELETE_PARAMETERS structure. |
| [ExInitializeFastMutex function](nf-wdm-exinitializefastmutex.md) | The ExInitializeFastMutex routine initializes a fast mutex variable, used to synchronize mutually exclusive access by a set of threads to a shared resource. |
| [ExInitializeLookasideListEx function](nf-wdm-exinitializelookasidelistex.md) | The ExInitializeLookasideListEx routine initializes a lookaside list. |
| [ExInitializeNPagedLookasideList function](nf-wdm-exinitializenpagedlookasidelist.md) | The ExInitializeNPagedLookasideList routine initializes a lookaside list for nonpaged entries of the specified size. |
| [ExInitializePagedLookasideList function](nf-wdm-exinitializepagedlookasidelist.md) | The ExInitializePagedLookasideList routine initializes a lookaside list for pageable entries of the specified size. |
| [ExInitializeResourceLite function](nf-wdm-exinitializeresourcelite.md) | The ExInitializeResourceLite routine initializes a resource variable. |
| [ExInitializeRundownProtection function](nf-wdm-exinitializerundownprotection.md) | The ExInitializeRundownProtection routine initializes run-down protection on a shared object. |
| [ExInitializeSetTimerParameters function](nf-wdm-exinitializesettimerparameters.md) | The ExInitializeSetTimerParameters routine initializes an EXT_SET_PARAMETERS structure. |
| [ExInitializeWorkItem function](nf-wdm-exinitializeworkitem.md) | ExInitializeWorkItem initializes a work-queue item with a caller-supplied context and callback routine to be queued for execution when a system worker thread is given control. |
| [ExInterlockedAddLargeInteger function](nf-wdm-exinterlockedaddlargeinteger.md) | The ExInterlockedAddLargeInteger routine adds a large integer value to the specified variable as an atomic operation. |
| [ExInterlockedAddUlong function](nf-wdm-exinterlockedaddulong.md) | The ExInterlockedAddUlong routine adds an unsigned long value to a given unsigned integer as an atomic operation. |
| [ExInterlockedInsertHeadList function](nf-wdm-exinterlockedinsertheadlist.md) | The ExInterlockedInsertHeadList routine atomically inserts an entry at the beginning of a doubly linked list of LIST_ENTRY structures. |
| [ExInterlockedInsertTailList function](nf-wdm-exinterlockedinserttaillist.md) | The ExInterlockedInsertTailList routine atomically inserts an entry at the end of a doubly linked list of LIST_ENTRY structures. |
| [ExInterlockedPopEntryList function](nf-wdm-exinterlockedpopentrylist.md) | The ExInterlockedPopEntryList routine atomically removes an entry from the beginning of a singly linked list of SINGLE_LIST_ENTRY structures. |
| [ExInterlockedPushEntryList function](nf-wdm-exinterlockedpushentrylist.md) | The ExInterlockedPushEntryList routine atomically inserts an entry at the beginning of a singly linked list of SINGLE_LIST_ENTRY structures. |
| [ExInterlockedRemoveHeadList function](nf-wdm-exinterlockedremoveheadlist.md) | The ExInterlockedRemoveHeadList routine removes an entry from the beginning of a doubly linked list of LIST_ENTRY structures. |
| [ExIsProcessorFeaturePresent function](nf-wdm-exisprocessorfeaturepresent.md) | The ExIsProcessorFeaturePresent routine queries for the existence of a specified processor feature. |
| [ExIsResourceAcquiredExclusiveLite function](nf-wdm-exisresourceacquiredexclusivelite.md) | The ExIsResourceAcquiredExclusiveLite routine returns whether the current thread has exclusive access to a given resource. |
| [ExIsResourceAcquiredSharedLite function](nf-wdm-exisresourceacquiredsharedlite.md) | The ExIsResourceAcquiredSharedLite routine returns whether the current thread has access (either shared or exclusive) to a given resource. |
| [ExIsSoftBoot function](nf-wdm-exissoftboot.md) | Determines whether the system has gone through a soft restart. |
| [ExLocalTimeToSystemTime function](nf-wdm-exlocaltimetosystemtime.md) | The ExLocalTimeToSystemTime routine converts a system time value for the current time zone to an unbiased, GreenGMT value. |
| [ExNotifyCallback function](nf-wdm-exnotifycallback.md) | The ExNotifyCallback routine causes all callback routines registered for the given object to be called. |
| [ExQueryDepthSList function](nf-wdm-exquerydepthslist.md) | The ExQueryDepthSList routine returns the number of entries currently in a given sequenced singly linked list. |
| [ExQueryTimerResolution function](nf-wdm-exquerytimerresolution.md) | The ExQueryTimerResolution routine reports the range of timer resolutions that are supported by the system clock. |
| [ExQueueWorkItem function](nf-wdm-exqueueworkitem.md) | ExQueueWorkItem inserts a given work item into a queue from which a system worker thread removes the item and gives control to the routine that the caller supplied to ExInitializeWorkItem. |
| [ExRaiseStatus function](nf-wdm-exraisestatus.md) | The ExRaiseStatus routine is called by drivers that supply structured exception handlers to handle particular errors that occur while they are processing I/O requests. |
| [ExReInitializeRundownProtection function](nf-wdm-exreinitializerundownprotection.md) | The ExReInitializeRundownProtection routine reinitializes an EX_RUNDOWN_REF structure after the associated object is run down. |
| [ExRegisterCallback function](nf-wdm-exregistercallback.md) | The ExRegisterCallback routine registers a given callback routine with a given callback object. |
| [ExReinitializeResourceLite function](nf-wdm-exreinitializeresourcelite.md) | The ExReinitializeResourceLite routine reinitializes an existing resource variable. |
| [ExReleaseResourceForThreadLite function](nf-wdm-exreleaseresourceforthreadlite.md) | The ExReleaseResourceForThreadLite routine releases the input resource of the indicated thread. |
| [ExReleaseRundownProtection function](nf-wdm-exreleaserundownprotection.md) | The ExReleaseRundownProtection routine releases run-down protection that the caller previously acquired by calling the ExAcquireRundownProtection routine. |
| [ExReleaseRundownProtectionEx function](nf-wdm-exreleaserundownprotectionex.md) | The ExReleaseRundownProtectionEx routine releases run-down protection that the caller previously acquired by calling the ExAcquireRundownProtectionEx routine. |
| [ExReleaseSpinLockExclusive function](nf-wdm-exreleasespinlockexclusive.md) | The ExReleaseSpinLockExclusive routine releases a spin lock that the caller previously acquired for exclusive access, and restores the IRQL to its original value. |
| [ExReleaseSpinLockShared function](nf-wdm-exreleasespinlockshared.md) | The ExReleaseSpinLockShared routine releases ownership of a spin lock that the caller previously acquired for shared access, and restores the IRQL to its original value. |
| [ExRundownCompleted function](nf-wdm-exrundowncompleted.md) | The ExRundownCompleted routine updates the run-down status of a shared object to indicate that the run down of the object has completed. |
| [ExSetFirmwareEnvironmentVariable function](nf-wdm-exsetfirmwareenvironmentvariable.md) | The ExSetFirmwareEnvironmentVariable routine sets the value of the specified system firmware environment variable. |
| [ExSetResourceOwnerPointer function](nf-wdm-exsetresourceownerpointer.md) | The ExSetResourceOwnerPointer routine sets the owner thread pointer for an executive resource. |
| [ExSetResourceOwnerPointerEx function](nf-wdm-exsetresourceownerpointerex.md) | The ExSetResourceOwnerPointerEx routine transfers the ownership of an executive resource from the calling thread to an owner pointer, which is a system address that identifies the resource owner. |
| [ExSetTimer function](nf-wdm-exsettimer.md) | The ExSetTimer routine starts a timer operation and sets the timer to expire at the specified due time. |
| [ExSetTimerResolution function](nf-wdm-exsettimerresolution.md) | The ExSetTimerResolution routine modifies the frequency at which the system clock interrupts. Use this routine with extreme caution (see the following Remarks section). |
| [ExSystemTimeToLocalTime function](nf-wdm-exsystemtimetolocaltime.md) | The ExSystemTimeToLocalTime routine converts a GMT system time value to the local system time for the current time zone. |
| [ExTryConvertSharedSpinLockExclusive function](nf-wdm-extryconvertsharedspinlockexclusive.md) | The ExTryConvertSharedSpinLockExclusive routine attempts to convert the access state of a spin lock from acquired for shared access to exclusive access. |
| [ExUnregisterCallback function](nf-wdm-exunregistercallback.md) | The ExUnregisterCallback routine removes a callback routine previously registered with a callback object from the list of routines to be called during the notification process. |
| [ExWaitForRundownProtectionRelease function](nf-wdm-exwaitforrundownprotectionrelease.md) | The ExWaitForRundownProtectionRelease routine waits until all drivers that have already been granted run-down protection complete their accesses of the shared object. |
| [FirstEntrySList function](nf-wdm-firstentryslist.md) | The FirstEntrySList routine returns the first entry in a sequenced singly linked list. |
| [InitializeListHead function](nf-wdm-initializelisthead.md) | The InitializeListHead routine initializes a LIST_ENTRY structure that represents the head of a doubly linked list. |
| [InitializeSListHead function](nf-wdm-initializeslisthead.md) | The InitializeSListHead routine (or ExInitializeSListHead) initializes an SLIST_HEADER structure that represents the head of a sequenced singly linked list. |
| [InsertHeadList function](nf-wdm-insertheadlist.md) | The InsertHeadList routine inserts an entry at the head of a doubly linked list of LIST_ENTRY structures. |
| [InsertTailList function](nf-wdm-inserttaillist.md) | The InsertTailList routine inserts an entry at the tail of a doubly linked list of LIST_ENTRY structures. |
| [InterlockedAnd function](nf-wdm-interlockedand.md) | The InterlockedAnd macro atomically computes a bitwise AND operation. |
| [InterlockedCompareExchange function](nf-wdm-interlockedcompareexchange.md) | The InterlockedCompareExchange routine performs an atomic operation that compares the input value pointed to by Destination with the value of Comparand. |
| [InterlockedCompareExchangePointer function](nf-wdm-interlockedcompareexchangepointer.md) | The InterlockedCompareExchangePointer routine performs an atomic operation that compares the input pointer value pointed to by Destination with the pointer value Comparand. |
| [InterlockedDecrement function](nf-wdm-interlockeddecrement.md) | The InterlockedDecrement routine decrements a caller-supplied variable of type LONG as an atomic operation. |
| [InterlockedExchange function](nf-wdm-interlockedexchange.md) | The InterlockedExchange routine sets an integer variable to a given value as an atomic operation. |
| [InterlockedExchangeAdd function](nf-wdm-interlockedexchangeadd.md) | The InterlockedExchangeAdd routine adds a value to a given integer as an atomic operation and returns the original value of the given integer. |
| [InterlockedExchangePointer function](nf-wdm-interlockedexchangepointer.md) | The InterlockedExchangePointer routine performs an atomic operation that sets a pointer to a new value. |
| [InterlockedIncrement function](nf-wdm-interlockedincrement.md) | The InterlockedIncrement routine increments a caller-supplied variable as an atomic operation. |
| [InterlockedOr function](nf-wdm-interlockedor.md) | The InterlockedOr routine atomically computes a bitwise OR operation. |
| [InterlockedXor function](nf-wdm-interlockedxor.md) | The InterlockedOr routine atomically computes a bitwise exclusive OR operation. |
| [IoAllocateDriverObjectExtension function](nf-wdm-ioallocatedriverobjectextension.md) | The IoAllocateDriverObjectExtension routine allocates a per-driver context area, called a driver object extension, and assigns a unique identifier to it. |
| [IoAllocateErrorLogEntry function](nf-wdm-ioallocateerrorlogentry.md) | The IoAllocateErrorLogEntry routine allocates an error log entry, and returns a pointer to the packet that the caller uses to supply information about an I/O error. |
| [IoAllocateIrp function](nf-wdm-ioallocateirp.md) | The IoAllocateIrp routine allocates an IRP, given the number of I/O stack locations for each driver layered under the caller, and, optionally, for the caller. |
| [IoAllocateMdl function](nf-wdm-ioallocatemdl.md) | The IoAllocateMdl routine allocates a memory descriptor list (MDL) large enough to map a buffer, given the buffer's starting address and length. Optionally, this routine associates the MDL with an IRP. |
| [IoAllocateWorkItem function](nf-wdm-ioallocateworkitem.md) | The IoAllocateWorkItem routine allocates a work item. |
| [IoAttachDevice function](nf-wdm-ioattachdevice.md) | The IoAttachDevice routine attaches the caller's device object to a named target device object, so that I/O requests bound for the target device are routed first to the caller. |
| [IoAttachDeviceToDeviceStack function](nf-wdm-ioattachdevicetodevicestack.md) | The IoAttachDeviceToDeviceStack routine attaches the caller's device object to the highest device object in the chain and returns a pointer to the previously highest device object. |
| [IoBuildAsynchronousFsdRequest function](nf-wdm-iobuildasynchronousfsdrequest.md) | The IoBuildAsynchronousFsdRequest routine allocates and sets up an IRP to be sent to lower-level drivers. |
| [IoBuildDeviceIoControlRequest function](nf-wdm-iobuilddeviceiocontrolrequest.md) | The IoBuildDeviceIoControlRequest routine allocates and sets up an IRP for a synchronously processed device control request. |
| [IoBuildPartialMdl function](nf-wdm-iobuildpartialmdl.md) | The IoBuildPartialMdl routine builds a new memory descriptor list (MDL) that represents part of a buffer that is described by an existing MDL. |
| [IoBuildSynchronousFsdRequest function](nf-wdm-iobuildsynchronousfsdrequest.md) | The IoBuildSynchronousFsdRequest routine allocates and sets up an IRP for a synchronously processed I/O request. |
| [IoCancelIrp function](nf-wdm-iocancelirp.md) | The IoCancelIrp routine sets the cancel bit in a given IRP and calls the cancel routine for the IRP if there is one. |
| [IoCheckLinkShareAccess function](nf-wdm-iochecklinkshareaccess.md) | The IoCheckLinkShareAccess routine is called by file system drivers (FSDs) or other highest-level drivers to check whether link shared access to a file object is permitted. |
| [IoCheckShareAccess function](nf-wdm-iocheckshareaccess.md) | The IoCheckShareAccess routine is called by file system drivers (FSDs) or other highest-level drivers to check whether shared access to a file object is permitted. |
| [IoCheckShareAccessEx function](nf-wdm-iocheckshareaccessex.md) | The IoCheckShareAccessEx routine is called by file system drivers (FSDs) or other highest-level drivers to check whether shared access to a file object is permitted. |
| [IoConnectInterrupt function](nf-wdm-ioconnectinterrupt.md) | The IoConnectInterrupt routine registers a device driver's InterruptService routine (ISR), so that it will be called when a device interrupts on any of a specified set of processors. |
| [IoConnectInterruptEx function](nf-wdm-ioconnectinterruptex.md) | For more information, see the WdmlibIoConnectInterruptEx function.#define IoConnectInterruptEx WdmlibIoConnectInterruptEx |
| [IoCopyCurrentIrpStackLocationToNext function](nf-wdm-iocopycurrentirpstacklocationtonext.md) | The IoCopyCurrentIrpStackLocationToNext routine copies the IRP stack parameters from the current I/O stack location to the stack location of the next-lower driver. |
| [IoCreateDevice function](nf-wdm-iocreatedevice.md) | The IoCreateDevice routine creates a device object for use by a driver. |
| [IoCreateFile function](nf-wdm-iocreatefile.md) | The IoCreateFile routine either causes a new file or directory to be created, or it opens an existing file, device, directory, or volume, giving the caller a handle for the file object. |
| [IoCreateNotificationEvent function](nf-wdm-iocreatenotificationevent.md) | The IoCreateNotificationEvent routine creates or opens a named notification event used to notify one or more threads of execution that an event has occurred. |
| [IoCreateSymbolicLink function](nf-wdm-iocreatesymboliclink.md) | The IoCreateSymbolicLink routine sets up a symbolic link between a device object name and a user-visible name for the device. |
| [IoCreateSynchronizationEvent function](nf-wdm-iocreatesynchronizationevent.md) | The IoCreateSynchronizationEvent routine creates or opens a named synchronization event for use in serialization of access to hardware between two otherwise unrelated drivers. |
| [IoCreateSystemThread function](nf-wdm-iocreatesystemthread.md) | The IoCreateSystemThread routine creates a system thread that executes in kernel mode, and supplies a handle for the thread. |
| [IoCreateUnprotectedSymbolicLink function](nf-wdm-iocreateunprotectedsymboliclink.md) | The IoCreateUnprotectedSymbolicLink routine sets up an unprotected symbolic link between a device object name and a corresponding Win32-visible name. |
| [IoCsqInitialize function](nf-wdm-iocsqinitialize.md) | The IoCsqInitialize routine initializes the driver's cancel-safe IRP queue dispatch table. |
| [IoCsqInitializeEx function](nf-wdm-iocsqinitializeex.md) | The IoCsqInitializeEx routine initializes the dispatch table for a cancel-safe IRP queue. |
| [IoCsqInsertIrp function](nf-wdm-iocsqinsertirp.md) | The IoCsqInsertIrp routine inserts an IRP in the driver's cancel-safe IRP queue. |
| [IoCsqInsertIrpEx function](nf-wdm-iocsqinsertirpex.md) | The IoCsqInsertIrpEx routine inserts an IRP into the driver's cancel-safe IRP queue. |
| [IoCsqRemoveIrp function](nf-wdm-iocsqremoveirp.md) | The IoCsqRemoveIrp routine removes a particular IRP from the queue. |
| [IoCsqRemoveNextIrp function](nf-wdm-iocsqremovenextirp.md) | The IoCsqRemoveNextIrp routine removes the next matching IRP in the queue. |
| [IoDeleteDevice function](nf-wdm-iodeletedevice.md) | The IoDeleteDevice routine removes a device object from the system, for example, when the underlying device is removed from the system. |
| [IoDeleteSymbolicLink function](nf-wdm-iodeletesymboliclink.md) | The IoDeleteSymbolicLink routine removes a symbolic link from the system. |
| [IoDetachDevice function](nf-wdm-iodetachdevice.md) | The IoDetachDevice routine releases an attachment between the caller's device object and a lower driver's device object. |
| [IoDisconnectInterrupt function](nf-wdm-iodisconnectinterrupt.md) | The IoDisconnectInterrupt routine releases a device driver's set of interrupt object(s) when the device is paused or removed, or when the driver is being unloaded. |
| [IoDisconnectInterruptEx function](nf-wdm-iodisconnectinterruptex.md) | For more information, see the WdmlibIoDisconnectInterruptEx function.#define IoDisconnectInterruptEx WdmlibIoDisconnectInterruptEx |
| [IoForwardIrpSynchronously function](nf-wdm-ioforwardirpsynchronously.md) | The IoForwardIrpSynchronously routine sends an IRP to a specified driver and waits for that driver to complete the IRP. |
| [IoFreeErrorLogEntry function](nf-wdm-iofreeerrorlogentry.md) | The IoFreeErrorLogEntry routine frees an unused error log entry. |
| [IoFreeIrp function](nf-wdm-iofreeirp.md) | The IoFreeIrp routine releases a caller-allocated IRP from the caller's IoCompletion routine. |
| [IoFreeMdl function](nf-wdm-iofreemdl.md) | The IoFreeMdl routine releases a caller-allocated memory descriptor list (MDL). |
| [IoFreeWorkItem function](nf-wdm-iofreeworkitem.md) | The IoFreeWorkItem routine frees a work item that was allocated by IoAllocateWorkItem. |
| [IoGetAffinityInterrupt function](nf-wdm-iogetaffinityinterrupt.md) | For more information, see the WdmlibIoGetAffinityInterrupt function.#define IoGetAffinityInterrupt WdmlibIoGetAffinityInterrupt |
| [IoGetAttachedDeviceReference function](nf-wdm-iogetattacheddevicereference.md) | The IoGetAttachedDeviceReference routine returns a pointer to the highest level device object in a driver stack and increments the reference count on that object. |
| [IoGetBootDiskInformation function](nf-wdm-iogetbootdiskinformation.md) | The IoGetBootDiskInformation routine returns information describing the boot and system disks. |
| [IoGetContainerInformation function](nf-wdm-iogetcontainerinformation.md) | The IoGetContainerInformation routine provides information about the current state of a user session. |
| [IoGetCurrentIrpStackLocation function](nf-wdm-iogetcurrentirpstacklocation.md) | The IoGetCurrentIrpStackLocation routine returns a pointer to the caller's I/O stack location in the specified IRP. |
| [IoGetCurrentProcess function](nf-wdm-iogetcurrentprocess.md) | The IoGetCurrentProcess routine returns a pointer to the current process. |
| [IoGetDeviceInterfaceAlias function](nf-wdm-iogetdeviceinterfacealias.md) | The IoGetDeviceInterfaceAlias routine returns the alias device interface of the specified device interface instance, if the alias exists. |
| [IoGetDeviceInterfacePropertyData function](nf-wdm-iogetdeviceinterfacepropertydata.md) | The IoGetDeviceInterfacePropertyData routine retrieves the current value of a device interface property. |
| [IoGetDeviceInterfaces function](nf-wdm-iogetdeviceinterfaces.md) | The IoGetDeviceInterfaces routine returns a list of device interface instances of a particular device interface class (such as all devices on the system that support a HID interface). |
| [IoGetDeviceNumaNode function](nf-wdm-iogetdevicenumanode.md) | The IoGetDeviceNumaNode routine gets the node number of a device. |
| [IoGetDeviceObjectPointer function](nf-wdm-iogetdeviceobjectpointer.md) | The IoGetDeviceObjectPointer routine returns a pointer to the top object in the named device object's stack and a pointer to the corresponding file object, if the requested access to the objects can be granted. |
| [IoGetDeviceProperty function](nf-wdm-iogetdeviceproperty.md) | The IoGetDeviceProperty routine retrieves information about a device such as configuration information and the name of its PDO. |
| [IoGetDevicePropertyData function](nf-wdm-iogetdevicepropertydata.md) | The IoGetDevicePropertyData routine retrieves the current setting for a device property. |
| [IoGetDmaAdapter function](nf-wdm-iogetdmaadapter.md) | The IoGetDmaAdapter routine returns a pointer to the DMA adapter structure for a physical device object. |
| [IoGetDriverObjectExtension function](nf-wdm-iogetdriverobjectextension.md) | The IoGetDriverObjectExtension routine retrieves a previously allocated per-driver context area. |
| [IoGetInitialStack function](nf-wdm-iogetinitialstack.md) | The IoGetInitialStack routine returns the base address of the current thread's stack. |
| [IoGetIoPriorityHint function](nf-wdm-iogetiopriorityhint.md) | The IoGetIoPriorityHint routine gets the priority hint value from an IRP. |
| [IoGetNextIrpStackLocation function](nf-wdm-iogetnextirpstacklocation.md) | The IoGetNextIrpStackLocation routine gives a higher level driver access to the next-lower driver's I/O stack location in an IRP so the caller can set it up for the lower driver. |
| [IoGetRelatedDeviceObject function](nf-wdm-iogetrelateddeviceobject.md) | Given a file object, the IoGetRelatedDeviceObject routine returns a pointer to the corresponding device object. |
| [IoGetRemainingStackSize function](nf-wdm-iogetremainingstacksize.md) | The IoGetRemainingStackSize routine returns the current amount of available kernel-mode stack space. |
| [IoGetStackLimits function](nf-wdm-iogetstacklimits.md) | The IoGetStackLimits routine returns the boundaries of the current thread's stack frame. |
| [IoGetTopLevelIrp function](nf-wdm-iogettoplevelirp.md) | The IoGetTopLevelIrp routine returns the value of the TopLevelIrp field of the current thread. |
| [IoInitializeDpcRequest function](nf-wdm-ioinitializedpcrequest.md) | The IoInitializeDpcRequest routine registers a driver-supplied DpcForIsr routine. |
| [IoInitializeIrp function](nf-wdm-ioinitializeirp.md) | The IoInitializeIrp routine initializes a given IRP that was allocated by the caller. |
| [IoInitializeTimer function](nf-wdm-ioinitializetimer.md) | The IoInitializeTimer routine sets up a driver-supplied IoTimer routine associated with a given device object. |
| [IoInitializeWorkItem function](nf-wdm-ioinitializeworkitem.md) | The IoInitializeWorkItem routine initializes a work item that the caller has already allocated. |
| [IoInvalidateDeviceRelations function](nf-wdm-ioinvalidatedevicerelations.md) | The IoInvalidateDeviceRelations routine notifies the PnP manager that the relations for a device (such as bus relations, ejection relations, removal relations, and the target device relation) have changed. |
| [IoInvalidateDeviceState function](nf-wdm-ioinvalidatedevicestate.md) | The IoInvalidateDeviceState routine notifies the PnP manager that some aspect of the PnP state of a device has changed. |
| [IoIs32bitProcess function](nf-wdm-iois32bitprocess.md) | The IoIs32bitProcess routine checks whether the originator of the current I/O request is a 32-bit user-mode application. |
| [IoIsWdmVersionAvailable function](nf-wdm-ioiswdmversionavailable.md) | The IoIsWdmVersionAvailable routine checks whether a given WDM version is supported by the operating system. |
| [IoMarkIrpPending function](nf-wdm-iomarkirppending.md) | The IoMarkIrpPending routine marks the specified IRP, indicating that a driver's dispatch routine subsequently returned STATUS_PENDING because further processing is required by other driver routines. |
| [IoOpenDeviceInterfaceRegistryKey function](nf-wdm-ioopendeviceinterfaceregistrykey.md) | The IoOpenDeviceInterfaceRegistryKey routine returns a handle to a registry key for storing information about a particular device interface instance. |
| [IoOpenDeviceRegistryKey function](nf-wdm-ioopendeviceregistrykey.md) | The IoOpenDeviceRegistryKey routine returns a handle to a device-specific or a driver-specific registry key for a particular device instance. |
| [IoQueueWorkItem function](nf-wdm-ioqueueworkitem.md) | The IoQueueWorkItem routine associates a WorkItem routine with a work item, and it inserts the work item into a queue for later processing by a system worker thread. |
| [IoQueueWorkItemEx function](nf-wdm-ioqueueworkitemex.md) | The IoQueueWorkItemEx routine associates a WorkItemEx routine with a work item, and it inserts the work item into a queue for later processing by a system worker thread. |
| [IoRegisterContainerNotification function](nf-wdm-ioregistercontainernotification.md) | The IoRegisterContainerNotification routine registers a kernel-mode driver to receive notifications about a specified class of events. |
| [IoRegisterDeviceInterface function](nf-wdm-ioregisterdeviceinterface.md) | The IoRegisterDeviceInterface routine registers a device interface class, if it has not been previously registered, and creates a new instance of the interface class, which a driver can subsequently enable for use by applications or other system components. |
| [IoRegisterLastChanceShutdownNotification function](nf-wdm-ioregisterlastchanceshutdownnotification.md) | The IoRegisterLastChanceShutdownNotification routine registers a driver to receive an IRP_MJ_SHUTDOWN IRP when the system is shut down, after all file systems have been flushed. |
| [IoRegisterPlugPlayNotification function](nf-wdm-ioregisterplugplaynotification.md) | The IoRegisterPlugPlayNotification routine registers a Plug and Play (PnP) notification callback routine to be called when a PnP event of the specified category occurs. |
| [IoRegisterShutdownNotification function](nf-wdm-ioregistershutdownnotification.md) | The IoRegisterShutdownNotification routine registers the driver to receive an IRP_MJ_SHUTDOWN IRP when the system is shut down. |
| [IoRemoveLinkShareAccess function](nf-wdm-ioremovelinkshareaccess.md) | The IoRemoveLinkShareAccess routine removes the access and link share-access information for a given open instance of a file object. |
| [IoRemoveShareAccess function](nf-wdm-ioremoveshareaccess.md) | The IoRemoveShareAccess routine removes the access and share-access information for a given open instance of a file object. |
| [IoReportInterruptActive function](nf-wdm-ioreportinterruptactive.md) | The IoReportInterruptActive routine informs the operating system that a registered interrupt service routine (ISR) is active and ready to handle interrupt requests. |
| [IoReportInterruptInactive function](nf-wdm-ioreportinterruptinactive.md) | The IoReportInterruptInactive routine informs the operating system that a registered interrupt service routine (ISR) is inactive and is not expecting interrupt requests. |
| [IoReportTargetDeviceChange function](nf-wdm-ioreporttargetdevicechange.md) | The IoReportTargetDeviceChange routine notifies the PnP manager that a custom event has occurred on a device. |
| [IoReportTargetDeviceChangeAsynchronous function](nf-wdm-ioreporttargetdevicechangeasynchronous.md) | The IoReportTargetDeviceChangeAsynchronous routine notifies the PnP manager that a custom event has occurred on a device. |
| [IoRequestDeviceEject function](nf-wdm-iorequestdeviceeject.md) | The IoRequestDeviceEject routine notifies the PnP manager that the device eject button was pressed. |
| [IoRequestDpc function](nf-wdm-iorequestdpc.md) | The IoRequestDpc routine queues a driver-supplied DpcForIsr routine to complete interrupt-driven I/O processing at a lower IRQL. |
| [IoReuseIrp function](nf-wdm-ioreuseirp.md) | The IoReuseIrp routine reinitializes an IRP so that it can be reused. |
| [IoSetCancelRoutine function](nf-wdm-iosetcancelroutine.md) | The IoSetCancelRoutine routine sets up a driver-supplied Cancel routine to be called if a given IRP is canceled. |
| [IoSetCompletionRoutine function](nf-wdm-iosetcompletionroutine.md) | The IoSetCompletionRoutine routine registers an IoCompletion routine, which will be called when the next-lower-level driver has completed the requested operation for the given IRP. |
| [IoSetCompletionRoutineEx function](nf-wdm-iosetcompletionroutineex.md) | The IoSetCompletionRoutineEx routine registers an IoCompletion routine, which is called when the next-lower-level driver has completed the requested operation for the given IRP. |
| [IoSetDeviceInterfacePropertyData function](nf-wdm-iosetdeviceinterfacepropertydata.md) | The IoSetDeviceInterfacePropertyData routine modifies the current value of a device interface property. |
| [IoSetDeviceInterfaceState function](nf-wdm-iosetdeviceinterfacestate.md) | The IoSetDeviceInterfaceState routine enables or disables an instance of a previously registered device interface class. |
| [IoSetDevicePropertyData function](nf-wdm-iosetdevicepropertydata.md) | The IoSetDevicePropertyData routine modifies the current setting for a device property. |
| [IoSetIoPriorityHint function](nf-wdm-iosetiopriorityhint.md) | The IoSetIoPriorityHint routine sets the priority hint value for an IRP. |
| [IoSetLinkShareAccess function](nf-wdm-iosetlinkshareaccess.md) | The IoSetLinkShareAccess routine sets the access rights for link sharing the specified file object. |
| [IoSetNextIrpStackLocation function](nf-wdm-iosetnextirpstacklocation.md) | The IoSetNextIrpStackLocation routine sets the IRP stack location in a driver-allocated IRP to that of the caller. |
| [IoSetShareAccess function](nf-wdm-iosetshareaccess.md) | The IoSetShareAccess routine sets the access rights for sharing the given file object. |
| [IoSetShareAccessEx function](nf-wdm-iosetshareaccessex.md) | The IoSetShareAccessEx routine sets the access rights for sharing the specified file object. |
| [IoSetStartIoAttributes function](nf-wdm-iosetstartioattributes.md) | The IoSetStartIoAttributes routine sets attributes for the driver's StartIo routine. |
| [IoSetTopLevelIrp function](nf-wdm-iosettoplevelirp.md) | The IoSetTopLevelIrp routine sets the value of the TopLevelIrp field of the current thread. |
| [IoSizeofWorkItem function](nf-wdm-iosizeofworkitem.md) | The IoSizeofWorkItem routine returns the size, in bytes, of an IO_WORKITEM structure. |
| [IoStartNextPacket function](nf-wdm-iostartnextpacket.md) | The IoStartNextPacket routine dequeues the next IRP, if any, from the given device object's associated device queue and calls the driver's StartIo routine. |
| [IoStartNextPacketByKey function](nf-wdm-iostartnextpacketbykey.md) | The IoStartNextPacketByKey routine dequeues the next I/O request packet from the specified device object's associated device queue according to a specified sort-key value and calls the driver's StartIo routine with that IRP. |
| [IoStartPacket function](nf-wdm-iostartpacket.md) | The IoStartPacket routine calls the driver's StartIo routine with the given IRP or inserts the IRP into the device queue associated with the given device object if the device is already busy. |
| [IoStartTimer function](nf-wdm-iostarttimer.md) | The IoStartTimer routine enables the timer associated with a given device object so the driver-supplied IoTimer routine is called once per second. |
| [IoStopTimer function](nf-wdm-iostoptimer.md) | The IoStopTimer routine disables the timer for a specified device object so the driver-supplied IoTimer routine is not called. |
| [IoUninitializeWorkItem function](nf-wdm-iouninitializeworkitem.md) | The IoUninitializeWorkItem routine uninitializes a work item that was initialized by IoInitializeWorkItem. |
| [IoUnregisterContainerNotification function](nf-wdm-iounregistercontainernotification.md) | The IoUnregisterContainerNotification routine cancels a container notification registration that was previously created by the IoRegisterContainerNotification routine. |
| [IoUnregisterPlugPlayNotification function](nf-wdm-iounregisterplugplaynotification.md) | This routine is obsolete in Windows 7 and later versions of Windows. For more information, see the following Remarks section.The IoUnregisterPlugPlayNotification routine removes the registration of a driver's callback routine for a PnP event. |
| [IoUnregisterPlugPlayNotificationEx function](nf-wdm-iounregisterplugplaynotificationex.md) | The IoUnregisterPlugPlayNotificationEx routine cancels the registration of a driver's callback routine for notifications of Plug and Play (PnP) events. |
| [IoUnregisterShutdownNotification function](nf-wdm-iounregistershutdownnotification.md) | The IoUnregisterShutdownNotification routine removes a registered driver from the shutdown notification queue. |
| [IoUpdateLinkShareAccess function](nf-wdm-ioupdatelinkshareaccess.md) | The IoUpdateLinkShareAccess routine updates the share access for the given file object, usually when the file is being opened. |
| [IoUpdateShareAccess function](nf-wdm-ioupdateshareaccess.md) | The IoUpdateShareAccess routine updates the share access for the given file object, usually when the file is being opened. |
| [IoValidateDeviceIoControlAccess function](nf-wdm-iovalidatedeviceiocontrolaccess.md) | For more information, see the WdmlibIoValidateDeviceIoControlAccess function. |
| [IoWMIAllocateInstanceIds function](nf-wdm-iowmiallocateinstanceids.md) | The IoWMIAllocateInstanceIds routine allocates one or more instance IDs that are unique to the GUID. |
| [IoWMIDeviceObjectToInstanceName function](nf-wdm-iowmideviceobjecttoinstancename.md) | The IoWMIDeviceObjectToInstanceName routine determines the instance name for the WMI class instance implemented by the driver that is specified by a device object. |
| [IoWMIDeviceObjectToProviderId function](nf-wdm-iowmideviceobjecttoproviderid.md) | The IoWMIDeviceObjectToProviderId routine translates the specified device object into the corresponding WMI Provider ID. |
| [IoWMIExecuteMethod function](nf-wdm-iowmiexecutemethod.md) | The IoWMIExecuteMethod routine runs a WMI class method on the specified WMI data block instance. |
| [IoWMIHandleToInstanceName function](nf-wdm-iowmihandletoinstancename.md) | The IoWMIHandleToInstanceName routine determines the instance name for the WMI class instance implemented by the driver that is specified by a file handle. |
| [IoWMIOpenBlock function](nf-wdm-iowmiopenblock.md) | The IoWMIOpenBlock routine opens the WMI data block object for the specified WMI class. |
| [IoWMIQueryAllData function](nf-wdm-iowmiqueryalldata.md) | The IoWMIQueryAllData routine returns all WMI data blocks that implement a given WMI class. |
| [IoWMIQueryAllDataMultiple function](nf-wdm-iowmiqueryalldatamultiple.md) | The IoWMIQueryAllDataMultiple routine returns all WMI data blocks that implement one of a set of WMI classes. |
| [IoWMIQuerySingleInstance function](nf-wdm-iowmiquerysingleinstance.md) | The IoWMIQuerySingleInstance routine returns the specified instance of a WMI data block. |
| [IoWMIQuerySingleInstanceMultiple function](nf-wdm-iowmiquerysingleinstancemultiple.md) | The IoWMIQuerySingleInstanceMultiple routine returns all WMI data block instances that implement the specified WMI classes with the specified instance names. |
| [IoWMIRegistrationControl function](nf-wdm-iowmiregistrationcontrol.md) | The IoWMIRegistrationControl routine registers or unregisters the caller as a WMI data provider for a specified device object. |
| [IoWMISetNotificationCallback function](nf-wdm-iowmisetnotificationcallback.md) | The IoWMISetNotificationCallback routine registers a notification callback for a WMI event. |
| [IoWMISetSingleInstance function](nf-wdm-iowmisetsingleinstance.md) | The IoWMISetSingleInstance routine sets the values for properties within the data block instance that matches the specified WMI class and instance name. |
| [IoWMISetSingleItem function](nf-wdm-iowmisetsingleitem.md) | The IoWMISetSingleItem routine sets a single property in the data block instance that matches the specified WMI class and instance name. |
| [IoWMISuggestInstanceName function](nf-wdm-iowmisuggestinstancename.md) | The IoWMISuggestInstanceName routine is used to request that WMI suggest a base name which a driver can use to build WMI instance names for the device. |
| [IoWMIWriteEvent function](nf-wdm-iowmiwriteevent.md) | The IoWMIWriteEvent routine delivers a given event to the user-mode WMI components for notification. |
| [IoWithinStackLimits function](nf-wdm-iowithinstacklimits.md) | The IoWithinStackLimits routine determines whether a region of memory is within the stack limit of the current thread. |
| [IoWriteErrorLogEntry function](nf-wdm-iowriteerrorlogentry.md) | The IoWriteErrorLogEntry routine queues a given error log packet to the system error logging thread. |
| [IsListEmpty function](nf-wdm-islistempty.md) | The IsListEmpty routine indicates whether a doubly linked list of LIST_ENTRY structures is empty. |
| [KdChangeOption function](nf-wdm-kdchangeoption.md) | The KdChangeOption routine accesses and changes state in the kernel that is related to kernel debugging. |
| [KdDisableDebugger function](nf-wdm-kddisabledebugger.md) | The KdDisableDebugger routine disables the kernel debugger. |
| [KdEnableDebugger function](nf-wdm-kdenabledebugger.md) | The KdEnableDebugger routine re-enables the kernel debugger after a call to the KdDisableDebugger routine disables the kernel debugger. |
| [KdRefreshDebuggerNotPresent function](nf-wdm-kdrefreshdebuggernotpresent.md) | The KdRefreshDebuggerNotPresent macro refreshes the value of the KD_DEBUGGER_NOT_PRESENT global kernel variable. |
| [KeAreAllApcsDisabled function](nf-wdm-keareallapcsdisabled.md) | The KeAreAllApcsDisabled routine indicates whether the calling thread is inside a guarded region or running at IRQL &gt;= APC_LEVEL, which disables all APC delivery. |
| [KeAreApcsDisabled function](nf-wdm-keareapcsdisabled.md) | The KeAreApcsDisabled routine returns whether the calling thread is within a critical region or a guarded region, which disables normal kernel APC delivery. |
| [KeBugCheckEx function](nf-wdm-kebugcheckex.md) | The KeBugCheckEx routine brings down the system in a controlled manner when the caller discovers an unrecoverable inconsistency that would corrupt the system if the caller continued to run. |
| [KeCancelTimer function](nf-wdm-kecanceltimer.md) | The KeCancelTimer routine dequeues a timer object before the timer interval, if any was set, expires. |
| [KeClearEvent function](nf-wdm-keclearevent.md) | The KeClearEvent routine sets an event to a not-signaled state. |
| [KeConvertAuxiliaryCounterToPerformanceCounter function](nf-wdm-keconvertauxiliarycountertoperformancecounter.md) | The KeConvertAuxiliaryCounterToPerformanceCounter routine converts the specified auxiliary counter value into a performance counter value. |
| [KeConvertPerformanceCounterToAuxiliaryCounter function](nf-wdm-keconvertperformancecountertoauxiliarycounter.md) | The KeConvertPerformanceCounterToAuxiliaryCounter routine converts the specified performance counter value into an auxiliary counter value. |
| [KeDelayExecutionThread function](nf-wdm-kedelayexecutionthread.md) | The KeDelayExecutionThread routine puts the current thread into an alertable or nonalertable wait state for a specified interval. |
| [KeDeregisterBoundCallback function](nf-wdm-kederegisterboundcallback.md) | The KeDeregisterBoundCallback routine deregisters a user-mode bound exception callback registered by KeRegisterBoundCallback. |
| [KeDeregisterBugCheckCallback function](nf-wdm-kederegisterbugcheckcallback.md) | The KeDeregisterBugCheckCallback routine removes a callback routine that was registered by KeRegisterBugCheckCallback. |
| [KeDeregisterBugCheckReasonCallback function](nf-wdm-kederegisterbugcheckreasoncallback.md) | The KeDeregisterBugCheckReasonCallback routine removes a callback routine that was registered by KeRegisterBugCheckReasonCallback. |
| [KeDeregisterNmiCallback function](nf-wdm-kederegisternmicallback.md) | The KeDeregisterNmiCallback routine deregisters a nonmaskable interrupt (NMI) callback registered by KeRegisterNmiCallback. |
| [KeDeregisterProcessorChangeCallback function](nf-wdm-kederegisterprocessorchangecallback.md) | The KeDeregisterProcessorChangeCallback routine unregisters a callback function that was previously registered with the operating system by calling the KeRegisterProcessorChangeCallback routine. |
| [KeEnterCriticalRegion function](nf-wdm-keentercriticalregion.md) | The KeEnterCriticalRegion routine temporarily disables the execution of normal kernel APCs, but does not prevent special kernel APCs from running. |
| [KeEnterGuardedRegion function](nf-wdm-keenterguardedregion.md) | The KeEnterGuardedRegion routine enters a guarded region, which disables all kernel-mode APC delivery to the current thread. |
| [KeFlushIoBuffers function](nf-wdm-keflushiobuffers.md) | The KeFlushIoBuffers routine flushes the memory region described by an MDL from caches of all processors. |
| [KeFlushQueuedDpcs function](nf-wdm-keflushqueueddpcs.md) | The KeFlushQueuedDpcs routine returns after all queued DPCs on all processors have executed. |
| [KeGetCurrentIrql function](nf-wdm-kegetcurrentirql.md) | The KeGetCurrentIrql routine returns the current IRQL. |
| [KeGetCurrentNodeNumber function](nf-wdm-kegetcurrentnodenumber.md) | The KeGetCurrentNodeNumber routine gets the NUMA node number for the logical processor that the caller is running on. |
| [KeGetCurrentProcessorNumberEx function](nf-wdm-kegetcurrentprocessornumberex.md) | The KeGetCurrentProcessorNumberEx routine gets the processor number of the logical processor that the caller is running on. |
| [KeGetCurrentThread function](nf-wdm-kegetcurrentthread.md) | The KeGetCurrentThread routine identifies the current thread. |
| [KeGetProcessorIndexFromNumber function](nf-wdm-kegetprocessorindexfromnumber.md) | The KeGetProcessorIndexFromNumber routine converts a group number and a group-relative processor number to a systemwide processor index. |
| [KeGetProcessorNumberFromIndex function](nf-wdm-kegetprocessornumberfromindex.md) | The KeGetProcessorNumberFromIndex routine converts a systemwide processor index to a group number and a group-relative processor number. |
| [KeGetRecommendedSharedDataAlignment function](nf-wdm-kegetrecommendedshareddataalignment.md) | The KeGetRecommendedSharedDataAlignment routine returns the preferred alignment for memory structures that can be accessed by more than one processor. |
| [KeInitializeCrashDumpHeader function](nf-wdm-keinitializecrashdumpheader.md) | The KeInitializeCrashDumpHeader routine supplies the header information the system requires for a crash dump file. |
| [KeInitializeDeviceQueue function](nf-wdm-keinitializedevicequeue.md) | The KeInitializeDeviceQueue routine initializes a device queue object to a not-busy state. |
| [KeInitializeDpc function](nf-wdm-keinitializedpc.md) | The KeInitializeDpc routine initializes a DPC object, and registers a CustomDpc routine for that object. |
| [KeInitializeEvent function](nf-wdm-keinitializeevent.md) | The KeInitializeEvent routine initializes an event object as a synchronization (single waiter) or notification type event and sets it to a signaled or not-signaled state. |
| [KeInitializeGuardedMutex function](nf-wdm-keinitializeguardedmutex.md) | The KeInitializeGuardedMutex routine initializes a guarded mutex. |
| [KeInitializeMutex function](nf-wdm-keinitializemutex.md) | The KeInitializeMutex routine initializes a mutex object, setting it to a signaled state. |
| [KeInitializeSemaphore function](nf-wdm-keinitializesemaphore.md) | The KeInitializeSemaphore routine initializes a semaphore object with a specified count and specifies an upper limit that the count can attain. |
| [KeInitializeSpinLock function](nf-wdm-keinitializespinlock.md) | The KeInitializeSpinLock routine initializes a variable of type KSPIN_LOCK. |
| [KeInitializeThreadedDpc function](nf-wdm-keinitializethreadeddpc.md) | The KeInitializeThreadedDpc routine initializes a threaded DPC object, and registers a CustomThreadedDpc routine for that object. |
| [KeInitializeTimer function](nf-wdm-keinitializetimer.md) | The KeInitializeTimer routine initializes a timer object. |
| [KeInitializeTimerEx function](nf-wdm-keinitializetimerex.md) | The KeInitializeTimerEx routine initializes an extended kernel timer object. |
| [KeInsertByKeyDeviceQueue function](nf-wdm-keinsertbykeydevicequeue.md) | The KeInsertByKeyDeviceQueue routine acquires the spin lock for the specified DeviceQueue and queues an entry according to the specified sort-key value if the device queue is set to a busy state. |
| [KeInsertDeviceQueue function](nf-wdm-keinsertdevicequeue.md) | The KeInsertDeviceQueue routine acquires the spin lock for the specified device queue object and, if the device queue is set to a busy state, queues the specified entry. |
| [KeInsertQueueDpc function](nf-wdm-keinsertqueuedpc.md) | The KeInsertQueueDpc routine queues a DPC for execution. |
| [KeIpiGenericCall function](nf-wdm-keipigenericcall.md) | The KeIpiGenericCall routine causes the specified routine to run on all processors simultaneously. |
| [KeLeaveCriticalRegion function](nf-wdm-keleavecriticalregion.md) | The KeLeaveCriticalRegion routine reenables the delivery of normal kernel-mode APCs that were disabled by a preceding call to KeEnterCriticalRegion. |
| [KeLeaveGuardedRegion function](nf-wdm-keleaveguardedregion.md) | The KeLeaveGuardedRegion routine exits a guarded region entered by KeEnterGuardedRegion. |
| [KeMemoryBarrier function](nf-wdm-kememorybarrier.md) | The KeMemoryBarrier routine creates a barrier at its position in the code&#8212;across which the compiler and the processor cannot move any operations. |
| [KeQueryActiveGroupCount function](nf-wdm-kequeryactivegroupcount.md) | The KeQueryActiveGroupCount routine returns the number of active processor groups in a multiprocessor system. |
| [KeQueryActiveProcessorCount function](nf-wdm-kequeryactiveprocessorcount.md) | The KeQueryActiveProcessorCount routine returns the number of currently active processors. |
| [KeQueryActiveProcessorCountEx function](nf-wdm-kequeryactiveprocessorcountex.md) | The KeQueryActiveProcessorCountEx routine returns the number of active logical processors in a specified group in a multiprocessor system or in the entire system. |
| [KeQueryActiveProcessors function](nf-wdm-kequeryactiveprocessors.md) | The KeQueryActiveProcessors routine returns a bitmask of the currently active processors. |
| [KeQueryAuxiliaryCounterFrequency function](nf-wdm-kequeryauxiliarycounterfrequency.md) | The KeQueryAuxiliaryCounterFrequency routine returns frequency of the auxiliary counter in units of Hz. |
| [KeQueryDpcWatchdogInformation function](nf-wdm-kequerydpcwatchdoginformation.md) | The KeQueryDpcWatchdogInformation routine returns the deferred procedure call (DPC) watchdog timer values for the current processor. |
| [KeQueryGroupAffinity function](nf-wdm-kequerygroupaffinity.md) | The KeQueryGroupAffinity routine returns an affinity mask that identifies the active logical processors in a specified group in a multiprocessor system. |
| [KeQueryHighestNodeNumber function](nf-wdm-kequeryhighestnodenumber.md) | The KeQueryHighestNodeNumber routine returns the highest node number in a multiprocessor system that has a non-uniform memory access (NUMA) architecture. |
| [KeQueryInterruptTime function](nf-wdm-kequeryinterrupttime.md) | The KeQueryInterruptTime routine returns the current value of the system interrupt time count, with accuracy to within system clock tick. |
| [KeQueryInterruptTimePrecise function](nf-wdm-kequeryinterrupttimeprecise.md) | The KeQueryInterruptTimePrecise routine returns the current value of the system interrupt time count, with accuracy to within a microsecond. |
| [KeQueryLogicalProcessorRelationship function](nf-wdm-kequerylogicalprocessorrelationship.md) | The KeQueryLogicalProcessorRelationship routine gets information about the relationships of one or more processors to the other processors in a multiprocessor system. |
| [KeQueryMaximumGroupCount function](nf-wdm-kequerymaximumgroupcount.md) | The KeQueryMaximumGroupCount routine returns the maximum number of groups in a multiprocessor system. |
| [KeQueryMaximumProcessorCount function](nf-wdm-kequerymaximumprocessorcount.md) | The KeQueryMaximumProcessorCount routine returns the maximum number of processors. |
| [KeQueryMaximumProcessorCountEx function](nf-wdm-kequerymaximumprocessorcountex.md) | The KeQueryMaximumProcessorCountEx routine returns the maximum number of logical processors in a specified group in a multiprocessor system. |
| [KeQueryNodeActiveAffinity function](nf-wdm-kequerynodeactiveaffinity.md) | The KeQueryNodeActiveAffinity routine gets the current processor affinity of a specified node in a multiprocessor system that has a non-uniform memory access (NUMA) architecture. |
| [KeQueryNodeMaximumProcessorCount function](nf-wdm-kequerynodemaximumprocessorcount.md) | The KeQueryNodeMaximumProcessorCount routine returns the maximum number of logical processors that a specified node in a non-uniform memory access (NUMA) multiprocessor system can contain. |
| [KeQueryPerformanceCounter function](nf-wdm-kequeryperformancecounter.md) | The KeQueryPerformanceCounter routine retrieves the current value and frequency of the performance counter.Use KeQueryPerformanceCounter to acquire high resolution (&lt;1us) time stamps for time interval measurements. |
| [KeQueryPriorityThread function](nf-wdm-kequeryprioritythread.md) | The KeQueryPriorityThread routine returns the current priority of a particular thread. |
| [KeQueryRuntimeThread function](nf-wdm-kequeryruntimethread.md) | The KeQueryRuntimeThread routine reports the accumulated kernel-mode and user-mode run time of a thread, in clock ticks. |
| [KeQuerySystemTimePrecise function](nf-wdm-kequerysystemtimeprecise.md) | The KeQuerySystemTimePrecise routine retrieves the current system time, and is more precise than the KeQuerySystemTime routine. |
| [KeQueryTimeIncrement function](nf-wdm-kequerytimeincrement.md) | The KeQueryTimeIncrement routine returns the number of 100-nanosecond units that are added to the system time each time the interval clock interrupts. |
| [KeQueryTotalCycleTimeThread function](nf-wdm-kequerytotalcycletimethread.md) | The KeQueryTotalCycleTimeThread routine returns the accumulated cycle time for the specified thread. |
| [KeQueryUnbiasedInterruptTime function](nf-wdm-kequeryunbiasedinterrupttime.md) | The KeQueryUnbiasedInterruptTime routine returns the current value of the system interrupt time count. |
| [KeRaiseIrqlToDpcLevel function](nf-wdm-keraiseirqltodpclevel.md) | The KeRaiseIrqlToDpcLevel routine raises the hardware priority to IRQL = DISPATCH_LEVEL, thereby masking off interrupts of equivalent or lower IRQL on the current processor. |
| [KeReadStateEvent function](nf-wdm-kereadstateevent.md) | The KeReadStateEvent routine returns the current state, signaled or not-signaled, of an event object. |
| [KeReadStateMutex function](nf-wdm-kereadstatemutex.md) | The KeReadStateMutex routine returns the current state, signaled or not-signaled, of the specified mutex object. |
| [KeReadStateSemaphore function](nf-wdm-kereadstatesemaphore.md) | The KeReadStateSemaphore routine returns the current state, signaled or not-signaled, of the specified semaphore object. |
| [KeReadStateTimer function](nf-wdm-kereadstatetimer.md) | The KeReadStateTimer routine reads the current state of a timer object. |
| [KeRegisterBoundCallback function](nf-wdm-keregisterboundcallback.md) | The KeRegisterBoundCallback routine registers a routine to be called whenever a user-mode bound exception occurs. |
| [KeRegisterBugCheckCallback function](nf-wdm-keregisterbugcheckcallback.md) | The KeRegisterBugCheckCallback routine registers a BugCheckCallback routine, which executes when the operating system issues a bug check. |
| [KeRegisterBugCheckReasonCallback function](nf-wdm-keregisterbugcheckreasoncallback.md) | The KeRegisterBugCheckReasonCallback routine registers a BugCheckDumpIoCallback, BugCheckSecondaryDumpDataCallback, or BugCheckAddPagesCallback routine, which executes when the operating system issues a bug check. |
| [KeRegisterNmiCallback function](nf-wdm-keregisternmicallback.md) | The KeRegisterNmiCallback routine registers a routine to be called whenever a nonmaskable interrupt (NMI) occurs. |
| [KeRegisterProcessorChangeCallback function](nf-wdm-keregisterprocessorchangecallback.md) | The KeRegisterProcessorChangeCallback routine registers a callback function with the operating system so that the operating system will notify the driver when a new processor is added to the hardware partition. |
| [KeReleaseMutex function](nf-wdm-kereleasemutex.md) | The KeReleaseMutex routine releases a mutex object, and specifies whether the caller is to call one of the KeWaitXxx routines as soon as KeReleaseMutex returns control. |
| [KeReleaseSemaphore function](nf-wdm-kereleasesemaphore.md) | The KeReleaseSemaphore routine releases the specified semaphore object. |
| [KeRemoveByKeyDeviceQueue function](nf-wdm-keremovebykeydevicequeue.md) | The KeRemoveByKeyDeviceQueue routine removes an entry, selected according to a sort key value, from the specified device queue. |
| [KeRemoveDeviceQueue function](nf-wdm-keremovedevicequeue.md) | The KeRemoveDeviceQueue routine removes an entry from the head of a specified device queue. |
| [KeRemoveEntryDeviceQueue function](nf-wdm-keremoveentrydevicequeue.md) | The KeRemoveEntryDeviceQueue routine returns whether the specified entry is in the device queue and removes it, if it was queued, from the device queue. |
| [KeRemoveQueueDpc function](nf-wdm-keremovequeuedpc.md) | The KeRemoveQueueDpc routine removes the specified DPC object from the system DPC queue. |
| [KeResetEvent function](nf-wdm-keresetevent.md) | The KeResetEvent routine resets a specified event object to a not-signaled state and returns the previous state of that event object. |
| [KeRestoreExtendedProcessorState function](nf-wdm-kerestoreextendedprocessorstate.md) | The KeRestoreExtendedProcessorState routine restores extended processor state information that was previously saved. |
| [KeRestoreFloatingPointState function](nf-wdm-kerestorefloatingpointstate.md) | The KeRestoreFloatingPointState routine restores the nonvolatile floating-point context saved by the preceding call to KeSaveFloatingPointState. |
| [KeRevertToUserAffinityThreadEx function](nf-wdm-kereverttouseraffinitythreadex.md) | The KeRevertToUserAffinityThreadEx routine restores the previous affinity of the current thread. |
| [KeRevertToUserGroupAffinityThread function](nf-wdm-kereverttousergroupaffinitythread.md) | The KeRevertToUserGroupAffinityThread routine restores the group affinity of the calling thread to its original value at the time that the thread was created. |
| [KeSaveExtendedProcessorState function](nf-wdm-kesaveextendedprocessorstate.md) | The KeSaveExtendedProcessorState routine saves extended processor state information. |
| [KeSaveFloatingPointState function](nf-wdm-kesavefloatingpointstate.md) | The KeSaveFloatingPointState routine saves the nonvolatile floating-point context so the caller can carry out floating-point operations. |
| [KeSetCoalescableTimer function](nf-wdm-kesetcoalescabletimer.md) | The KeSetCoalescableTimer routine sets the initial expiration time and period of a timer object and specifies how much delay can be tolerated in the expiration times. |
| [KeSetEvent function](nf-wdm-kesetevent.md) | The KeSetEvent routine sets an event object to a signaled state if the event was not already signaled, and returns the previous state of the event object. |
| [KeSetImportanceDpc function](nf-wdm-kesetimportancedpc.md) | The KeSetImportanceDpc routine specifies how soon the DPC routine is run. |
| [KeSetPriorityThread function](nf-wdm-kesetprioritythread.md) | The KeSetPriorityThread routine sets the run-time priority of a driver-created thread. |
| [KeSetSystemAffinityThread function](nf-wdm-kesetsystemaffinitythread.md) | The KeSetSystemAffinityThread routine sets the system affinity of the current thread. |
| [KeSetSystemAffinityThreadEx function](nf-wdm-kesetsystemaffinitythreadex.md) | The KeSetSystemAffinityThreadEx routine sets the system affinity of the current thread. |
| [KeSetSystemGroupAffinityThread function](nf-wdm-kesetsystemgroupaffinitythread.md) | The KeSetSystemGroupAffinityThread routine changes the group number and affinity mask of the calling thread. |
| [KeSetTargetProcessorDpc function](nf-wdm-kesettargetprocessordpc.md) | The KeSetTargetProcessorDpc routine specifies the processor that a DPC routine will be run on. |
| [KeSetTargetProcessorDpcEx function](nf-wdm-kesettargetprocessordpcex.md) | The KeSetTargetProcessorDpcEx routine specifies the processor that a DPC routine will run on. |
| [KeSetTimer function](nf-wdm-kesettimer.md) | The KeSetTimer routine sets the absolute or relative interval at which a timer object is to be set to a signaled state and, optionally, supplies a CustomTimerDpc routine to be executed when that interval expires. |
| [KeSetTimerEx function](nf-wdm-kesettimerex.md) | The KeSetTimerEx routine sets the absolute or relative interval at which a timer object is to be set to a signaled state, optionally supplies a CustomTimerDpc routine to be executed when that interval expires, and optionally supplies a recurring interval for the timer. |
| [KeStallExecutionProcessor function](nf-wdm-kestallexecutionprocessor.md) | The KeStallExecutionProcessor routine stalls the caller on the current processor for a specified time interval. |
| [KeSynchronizeExecution function](nf-wdm-kesynchronizeexecution.md) | The KeSynchronizeExecution routine synchronizes the execution of the specified routine with the interrupt service routine (ISR) that is assigned to a set of one or more interrupt objects. |
| [KeTestSpinLock function](nf-wdm-ketestspinlock.md) | The KeTestSpinLock routine tests for the availability of a spin lock. |
| [KeTryToAcquireGuardedMutex function](nf-wdm-ketrytoacquireguardedmutex.md) | The KeTryToAcquireGuardedMutex routine acquires a guarded mutex, if available. |
| [KeTryToAcquireSpinLockAtDpcLevel function](nf-wdm-ketrytoacquirespinlockatdpclevel.md) | The KeTryToAcquireSpinLockAtDpcLevel routine attempts to acquire a spin lock at DISPATCH_LEVEL. |
| [KeWaitForMultipleObjects function](nf-wdm-kewaitformultipleobjects.md) | The KeWaitForMultipleObjects routine puts the current thread into an alertable or nonalertable wait state until any or all of a number of dispatcher objects are set to a signaled state or (optionally) until the wait times out. |
| [KeWaitForSingleObject function](nf-wdm-kewaitforsingleobject.md) | The KeWaitForSingleObject routine puts the current thread into a wait state until the given dispatcher object is set to a signaled state or (optionally) until the wait times out. |
| [MmAdvanceMdl function](nf-wdm-mmadvancemdl.md) | The MmAdvanceMdl routine advances the beginning of an MDL's virtual memory range by the specified number of bytes. |
| [MmAllocateContiguousMemory function](nf-wdm-mmallocatecontiguousmemory.md) | The MmAllocateContiguousMemory routine allocates a range of contiguous, nonpaged physical memory and maps it to the system address space. |
| [MmAllocateContiguousMemorySpecifyCache function](nf-wdm-mmallocatecontiguousmemoryspecifycache.md) | The MmAllocateContiguousMemorySpecifyCache routine allocates a range of contiguous, nonpaged physical memory and maps it to the system address space. |
| [MmAllocateContiguousMemorySpecifyCacheNode function](nf-wdm-mmallocatecontiguousmemoryspecifycachenode.md) | The MmAllocateContiguousMemorySpecifyCacheNode routine allocates a range of contiguous, nonpaged physical memory and maps it to the system address space. |
| [MmAllocateContiguousNodeMemory function](nf-wdm-mmallocatecontiguousnodememory.md) | The MmAllocateContiguousNodeMemory routine allocates a range of contiguous, nonpaged physical memory and maps it to the system address space. |
| [MmAllocateMappingAddress function](nf-wdm-mmallocatemappingaddress.md) | The MmAllocateMappingAddress routine reserves a range of system virtual address space of the specified size. |
| [MmAllocateMdlForIoSpace function](nf-wdm-mmallocatemdlforiospace.md) | The MmAllocateMdlForIoSpace routine allocates an MDL and initializes this MDL to describe a set of physical address ranges in I/O address space. |
| [MmAllocateNodePagesForMdlEx function](nf-wdm-mmallocatenodepagesformdlex.md) | The MmAllocateNodePagesForMdlEx routine allocates nonpaged physical memory from an ideal node, and allocates an MDL structure to describe this memory. |
| [MmAllocatePagesForMdl function](nf-wdm-mmallocatepagesformdl.md) | The MmAllocatePagesForMdl routine allocates zero-filled, nonpaged, physical memory pages to an MDL. |
| [MmAllocatePagesForMdlEx function](nf-wdm-mmallocatepagesformdlex.md) | The MmAllocatePagesForMdlEx routine allocates nonpaged, physical memory pages to an MDL. |
| [MmBuildMdlForNonPagedPool function](nf-wdm-mmbuildmdlfornonpagedpool.md) | The MmBuildMdlForNonPagedPool routine receives an MDL that specifies a nonpaged virtual memory buffer, and updates it to describe the underlying physical pages. |
| [MmFreeContiguousMemory function](nf-wdm-mmfreecontiguousmemory.md) | The MmFreeContiguousMemory routine releases a range of physically contiguous memory that was allocated by an MmAllocateContiguousMemoryXxx routine. |
| [MmFreeContiguousMemorySpecifyCache function](nf-wdm-mmfreecontiguousmemoryspecifycache.md) | The MmFreeContiguousMemorySpecifyCache routine frees a buffer that was allocated by an MmAllocateContiguousMemorySpecifyCacheXxx routine. |
| [MmFreeMappingAddress function](nf-wdm-mmfreemappingaddress.md) | The MmFreeMappingAddress routine frees a range of virtual memory reserved by the MmAllocateMappingAddress routine. |
| [MmFreePagesFromMdl function](nf-wdm-mmfreepagesfrommdl.md) | The MmFreePagesFromMdl routine frees all the physical pages that are described by an MDL that was created by the MmAllocatePagesForMdl routine. |
| [MmGetSystemRoutineAddress function](nf-wdm-mmgetsystemroutineaddress.md) | The MmGetSystemRoutineAddress routine returns a pointer to a function specified by SystemRoutineName. |
| [MmIsDriverSuspectForVerifier function](nf-wdm-mmisdriversuspectforverifier.md) | The MmIsDriverSuspectForVerifier routine indicates whether the driver represented by the specified driver object is in the list of drivers that are selected to be verified by Driver Verifier. |
| [MmIsDriverVerifying function](nf-wdm-mmisdriververifying.md) | The MmIsDriverVerifying routine indicates whether the kernel-mode driver that is identified by the specified driver object is being verified or calls a driver that is being verified by Driver Verifier. |
| [MmIsDriverVerifyingByAddress function](nf-wdm-mmisdriververifyingbyaddress.md) | The MmIsDriverVerifyingByAddress routine checks whether the kernel-mode driver that is identified by the specified image address is being verified or calls a driver that is being verified by Driver Verifier. |
| [MmLockPagableDataSection function](nf-wdm-mmlockpagabledatasection.md) | The MmLockPagableDataSection routine locks an entire section of driver data into system space. |
| [MmMapIoSpace function](nf-wdm-mmmapiospace.md) | The MmMapIoSpace routine maps the given physical address range to nonpaged system space. |
| [MmMapIoSpaceEx function](nf-wdm-mmmapiospaceex.md) | The MmMapIoSpaceEx routine maps the given physical address range to non-paged system space using the specified page protection. |
| [MmMapLockedPages function](nf-wdm-mmmaplockedpages.md) | The MmMapLockedPages routine is obsolete for Windows 2000 and later versions of Windows, and for Windows Me. |
| [MmMapLockedPagesSpecifyCache function](nf-wdm-mmmaplockedpagesspecifycache.md) | The MmMapLockedPagesSpecifyCache routine maps the physical pages that are described by an MDL to a virtual address, and enables the caller to specify the cache attribute that is used to create the mapping. |
| [MmMapLockedPagesWithReservedMapping function](nf-wdm-mmmaplockedpageswithreservedmapping.md) | The MmMapLockedPagesWithReservedMapping routine maps all or part of an address range that was previously reserved by the MmAllocateMappingAddress routine. |
| [MmMapMdl function](nf-wdm-mmmapmdl.md) | This function maps physical pages described by a memory descriptor list (MDL) into the system virtual address space. |
| [MmPageEntireDriver function](nf-wdm-mmpageentiredriver.md) | The MmPageEntireDriver routine causes all of a driver's code and data to be made pageable, overriding the attributes of the various sections that make up the driver's image. |
| [MmProbeAndLockPages function](nf-wdm-mmprobeandlockpages.md) | The MmProbeAndLockPages routine probes the specified virtual memory pages, makes them resident, and locks them in memory. |
| [MmProbeAndLockSelectedPages function](nf-wdm-mmprobeandlockselectedpages.md) | The MmProbeAndLockSelectedPages routine probes the selected virtual memory pages, makes them resident, and locks them in memory. |
| [MmProtectMdlSystemAddress function](nf-wdm-mmprotectmdlsystemaddress.md) | The MmProtectMdlSystemAddress routine sets the protection type for a memory address range. |
| [MmQuerySystemSize function](nf-wdm-mmquerysystemsize.md) | The MmQuerySystemSize routine returns an estimate of the amount of memory in the system. |
| [MmResetDriverPaging function](nf-wdm-mmresetdriverpaging.md) | The MmResetDriverPaging routine resets the pageable status of a driver's sections to that specified when the driver was compiled. |
| [MmSizeOfMdl function](nf-wdm-mmsizeofmdl.md) | The MmSizeOfMdl routine returns the number of bytes to allocate for an MDL describing a given address range. |
| [MmUnlockPagableImageSection function](nf-wdm-mmunlockpagableimagesection.md) | The MmUnlockPagableImageSection routine releases a section of driver code or driver data, previously locked into system space with MmLockPagableCodeSection, MmLockPagableDataSection or MmLockPagableSectionByHandle, so the section can be paged out again. |
| [MmUnlockPages function](nf-wdm-mmunlockpages.md) | The MmUnlockPages routine unlocks the physical pages that are described by the specified memory descriptor list (MDL). |
| [MmUnmapIoSpace function](nf-wdm-mmunmapiospace.md) | The MmUnmapIoSpace routine unmaps a specified range of physical addresses previously mapped by MmMapIoSpace. |
| [MmUnmapLockedPages function](nf-wdm-mmunmaplockedpages.md) | The MmUnmapLockedPages routine releases a mapping that was set up by a preceding call to the MmMapLockedPages or MmMapLockedPagesSpecifyCache routine. |
| [MmUnmapReservedMapping function](nf-wdm-mmunmapreservedmapping.md) | The MmUnmapReservedMapping routine unmaps a memory buffer that was mapped by the MmMapLockedPagesWithReservedMapping routine. |
| [NtCommitComplete function](nf-wdm-ntcommitcomplete.md) | The ZwCommitComplete routine notifies KTM that the calling resource manager has finished committing a transaction's data. |
| [NtCommitEnlistment function](nf-wdm-ntcommitenlistment.md) | The ZwCommitEnlistment routine initiates the commit operation for a specified enlistment's transaction. |
| [NtCommitTransaction function](nf-wdm-ntcommittransaction.md) | The ZwCommitTransaction routine initiates a commit operation for a specified transaction. |
| [NtCreateEnlistment function](nf-wdm-ntcreateenlistment.md) | The ZwCreateEnlistment routine creates a new enlistment object for a transaction. |
| [NtCreateResourceManager function](nf-wdm-ntcreateresourcemanager.md) | The ZwCreateResourceManager routine creates a resource manager object. |
| [NtCreateTransaction function](nf-wdm-ntcreatetransaction.md) | The ZwCreateTransaction routine creates a transaction object. |
| [NtCreateTransactionManager function](nf-wdm-ntcreatetransactionmanager.md) | The ZwCreateTransactionManager routine creates a new transaction manager object. |
| [NtEnumerateTransactionObject function](nf-wdm-ntenumeratetransactionobject.md) | The ZwEnumerateTransactionObject routine enumerates the KTM objects on a computer. |
| [NtGetNotificationResourceManager function](nf-wdm-ntgetnotificationresourcemanager.md) | The ZwGetNotificationResourceManager routine retrieves the next transaction notification from a specified resource manager's notification queue. |
| [NtOpenEnlistment function](nf-wdm-ntopenenlistment.md) | The ZwOpenEnlistment routine obtains a handle to an existing enlistment object. |
| [NtOpenResourceManager function](nf-wdm-ntopenresourcemanager.md) | The ZwOpenResourceManager routine returns a handle to an existing resource manager object. |
| [NtOpenTransaction function](nf-wdm-ntopentransaction.md) | The ZwOpenTransaction routine obtains a handle to an existing transaction object. |
| [NtOpenTransactionManager function](nf-wdm-ntopentransactionmanager.md) | The ZwOpenTransactionManager routine obtains a handle to an existing transaction manager object. |
| [NtPowerInformation function](nf-wdm-ntpowerinformation.md) | The ZwPowerInformation routine sets or retrieves system power information. |
| [NtPrePrepareComplete function](nf-wdm-ntprepreparecomplete.md) | The ZwPrePrepareComplete routine notifies KTM that the calling resource manager has finished preliminary preparation of a transaction's data. |
| [NtPrePrepareEnlistment function](nf-wdm-ntpreprepareenlistment.md) | The ZwPrePrepareEnlistment routine initiates the pre-prepare operation for a specified enlistment's transaction. |
| [NtPrepareComplete function](nf-wdm-ntpreparecomplete.md) | The ZwPrepareComplete routine notifies KTM that the calling resource manager has finished preparing a transaction's data. |
| [NtPrepareEnlistment function](nf-wdm-ntprepareenlistment.md) | The ZwPrepareEnlistment routine initiates the prepare operation for a specified enlistment's transaction. |
| [NtQueryInformationEnlistment function](nf-wdm-ntqueryinformationenlistment.md) | The ZwQueryInformationEnlistment routine retrieves information about a specified enlistment object. |
| [NtQueryInformationResourceManager function](nf-wdm-ntqueryinformationresourcemanager.md) | The ZwQueryInformationResourceManager routine retrieves information about a specified resource manager object. |
| [NtQueryInformationTransaction function](nf-wdm-ntqueryinformationtransaction.md) | The ZwQueryInformationTransaction routine retrieves information about a specified transaction. |
| [NtQueryInformationTransactionManager function](nf-wdm-ntqueryinformationtransactionmanager.md) | The ZwQueryInformationTransactionManager routine retrieves information about a specified transaction manager object. |
| [NtReadOnlyEnlistment function](nf-wdm-ntreadonlyenlistment.md) | The ZwReadOnlyEnlistment routine sets a specified enlistment to be read-only. |
| [NtRecoverEnlistment function](nf-wdm-ntrecoverenlistment.md) | The ZwRecoverEnlistment routine initiates a recovery operation for the transaction that is associated with a specified enlistment. |
| [NtRecoverResourceManager function](nf-wdm-ntrecoverresourcemanager.md) | The ZwRecoverResourceManager routine tries to recover the transaction that is associated with each enlistment of a specified resource manager object. |
| [NtRecoverTransactionManager function](nf-wdm-ntrecovertransactionmanager.md) | The ZwRecoverTransactionManager routine reconstructs the state of the transaction manager object (including all transactions, enlistments, and resource managers) from the recovery information that is in the log stream. |
| [NtRenameTransactionManager function](nf-wdm-ntrenametransactionmanager.md) | The NtRenameTransactionManager routine changes the identity of the transaction manager object that is stored in the CLFS log file stream contained in the log file name. |
| [NtRollbackComplete function](nf-wdm-ntrollbackcomplete.md) | The ZwRollbackComplete routine notifies KTM that the calling resource manager has finished rolling back a transaction's data. |
| [NtRollbackEnlistment function](nf-wdm-ntrollbackenlistment.md) | The ZwRollbackEnlistment routine rolls back the transaction that is associated with a specified enlistment. |
| [NtRollbackTransaction function](nf-wdm-ntrollbacktransaction.md) | The ZwRollbackTransaction routine initiates a rollback operation for a specified transaction. |
| [NtRollforwardTransactionManager function](nf-wdm-ntrollforwardtransactionmanager.md) | The ZwRollforwardTransactionManager routine initiates recovery operations for all of the in-progress transactions that are assigned to a specified transaction manager. |
| [NtSetInformationEnlistment function](nf-wdm-ntsetinformationenlistment.md) | The ZwSetInformationEnlistment routine sets information for a specified enlistment object. |
| [NtSetInformationResourceManager function](nf-wdm-ntsetinformationresourcemanager.md) | The ZwSetInformationResourceManager routine is not used. |
| [NtSetInformationTransaction function](nf-wdm-ntsetinformationtransaction.md) | The ZwSetInformationTransaction routine sets information for a specified transaction. |
| [NtSetInformationTransactionManager function](nf-wdm-ntsetinformationtransactionmanager.md) | Do not call this routine from kernel-mode code. |
| [NtSinglePhaseReject function](nf-wdm-ntsinglephasereject.md) | The ZwSinglePhaseReject routine informs KTM that the calling resource manager will not support single-phase commit operations for a specified enlistment. |
| [ObCloseHandle function](nf-wdm-obclosehandle.md) | The ObCloseHandle routine closes an object handle. |
| [ObDereferenceObjectDeferDelete function](nf-wdm-obdereferenceobjectdeferdelete.md) | The ObDereferenceObjectDeferDelete routine decrements the reference count for the given object, checks for object retention, and avoids deadlocks. |
| [ObDereferenceObjectDeferDeleteWithTag function](nf-wdm-obdereferenceobjectdeferdeletewithtag.md) | The ObDereferenceObjectDeferDeleteWithTag routine decrements the reference count for the specified object, defers deletion of the object to avoid deadlocks, and writes a four-byte tag value to the object to support object reference tracing. |
| [ObGetObjectSecurity function](nf-wdm-obgetobjectsecurity.md) | The ObGetObjectSecurity routine gets the security descriptor for a given object. |
| [ObReferenceObjectByHandle function](nf-wdm-obreferenceobjectbyhandle.md) | The ObReferenceObjectByHandle routine provides access validation on the object handle, and, if access can be granted, returns the corresponding pointer to the object's body. |
| [ObReferenceObjectByHandleWithTag function](nf-wdm-obreferenceobjectbyhandlewithtag.md) | The ObReferenceObjectByHandleWithTag routine increments the reference count of the object that is identified by the specified handle, and writes a four-byte tag value to the object to support object reference tracing. |
| [ObReferenceObjectByPointer function](nf-wdm-obreferenceobjectbypointer.md) | The ObReferenceObjectByPointer routine increments the pointer reference count for a given object. |
| [ObReferenceObjectByPointerWithTag function](nf-wdm-obreferenceobjectbypointerwithtag.md) | The ObReferenceObjectByPointerWithTag routine increments the reference count of the specified object, and writes a four-byte tag value to the object to support object reference tracing. |
| [ObRegisterCallbacks function](nf-wdm-obregistercallbacks.md) | The ObRegisterCallbacks routine registers a list of callback routines for thread, process, and desktop handle operations. |
| [ObReleaseObjectSecurity function](nf-wdm-obreleaseobjectsecurity.md) | The ObReleaseObjectSecurity routine is the reciprocal to ObGetObjectSecurity. |
| [ObUnRegisterCallbacks function](nf-wdm-obunregistercallbacks.md) | The ObUnRegisterCallbacks routine unregisters a set of callback routines that were registered with the ObRegisterCallbacks routine. |
| [ObfReferenceObject function](nf-wdm-obfreferenceobject.md) | The ObReferenceObject routine increments the reference count to the given object. |
| [PcwAddInstance function](nf-wdm-pcwaddinstance.md) | The PcwAddInstance function adds the specified instance of the counter set to the consumer buffer. |
| [PcwCloseInstance function](nf-wdm-pcwcloseinstance.md) | The PcwCloseInstance function closes the specified instance of the counter set. |
| [PcwCreateInstance function](nf-wdm-pcwcreateinstance.md) | The PcwCreateInstance function creates a new instance for the specified registered counter set. |
| [PcwRegister function](nf-wdm-pcwregister.md) | The PcwRegister function registers the caller as a provider of the specified counter set. |
| [PcwUnregister function](nf-wdm-pcwunregister.md) | The PcwUnregister function unregisters the provider of the specified counter set. |
| [PoCallDriver function](nf-wdm-pocalldriver.md) | The PoCallDriver routine passes a power IRP to the next-lower driver in the device stack. (Windows Server 2003, Windows XP, and Windows 2000 only.). |
| [PoClearPowerRequest function](nf-wdm-poclearpowerrequest.md) | The PoClearPowerRequest routine decrements the count for the specified power request type. |
| [PoCreatePowerRequest function](nf-wdm-pocreatepowerrequest.md) | The PoCreatePowerRequest routine creates a power request object. |
| [PoDeletePowerRequest function](nf-wdm-podeletepowerrequest.md) | The PoDeletePowerRequest routine deletes a power request object. |
| [PoEndDeviceBusy function](nf-wdm-poenddevicebusy.md) | The PoEndDeviceBusy routine marks the end of a period of time in which the device is busy. |
| [PoFxActivateComponent function](nf-wdm-pofxactivatecomponent.md) | The PoFxActivateComponent routine increments the activation reference count on the specified component. |
| [PoFxCompleteDevicePowerNotRequired function](nf-wdm-pofxcompletedevicepowernotrequired.md) | The PoFxCompleteDevicePowerNotRequired routine notifies the power management framework (PoFx) that the calling driver has completed its response to a call to the driver's DevicePowerNotRequiredCallback callback routine. |
| [PoFxCompleteIdleCondition function](nf-wdm-pofxcompleteidlecondition.md) | The PoFxCompleteIdleCondition routine informs the power management framework (PoFx) that the specified component has completed a pending change to the idle condition. |
| [PoFxCompleteIdleState function](nf-wdm-pofxcompleteidlestate.md) | The PoFxCompleteIdleState routine informs the power management framework (PoFx) that the specified component has completed a pending change to an Fx state. |
| [PoFxIdleComponent function](nf-wdm-pofxidlecomponent.md) | The PoFxIdleComponent routine decrements the activation reference count on the specified component. |
| [PoFxIssueComponentPerfStateChange function](nf-wdm-pofxissuecomponentperfstatechange.md) | The PoFxIssueComponentPerfStateChange routine submits a request to place a device component in a particular performance state. |
| [PoFxIssueComponentPerfStateChangeMultiple function](nf-wdm-pofxissuecomponentperfstatechangemultiple.md) | The PoFxIssueComponentPerfStateChangeMultiple routine submits a request to change the performance states in multiple performance state sets simultaneously for a device component. |
| [PoFxNotifySurprisePowerOn function](nf-wdm-pofxnotifysurprisepoweron.md) | The PoFxNotifySurprisePowerOn routine notifies the power management framework (PoFx) that a device was turned on as a side effect of supplying power to some other device. |
| [PoFxPowerControl function](nf-wdm-pofxpowercontrol.md) | The PoFxPowerControl routine sends a power control request to the power management framework (PoFx). |
| [PoFxPowerOnCrashdumpDevice function](nf-wdm-pofxpoweroncrashdumpdevice.md) | The PoFxPowerOnCrashdumpDevice routine requests that a crash-dump device be turned on. |
| [PoFxQueryCurrentComponentPerfState function](nf-wdm-pofxquerycurrentcomponentperfstate.md) | The PoFxQueryCurrentComponentPerfState routine retrieves the active performance state in a component's performance state set. |
| [PoFxRegisterComponentPerfStates function](nf-wdm-pofxregistercomponentperfstates.md) | The PoFxRegisterComponentPerfStates routine registers a device component for performance state management by the power management framework (PoFx). |
| [PoFxRegisterCrashdumpDevice function](nf-wdm-pofxregistercrashdumpdevice.md) | The PoFxRegisterCrashdumpDevice routine registers a crash-dump device. |
| [PoFxRegisterDevice function](nf-wdm-pofxregisterdevice.md) | The PoFxRegisterDevice routine registers a device with the power management framework (PoFx). |
| [PoFxReportDevicePoweredOn function](nf-wdm-pofxreportdevicepoweredon.md) | The PoFxReportDevicePoweredOn routine notifies the power management framework (PoFx) that the device completed the requested transition to the D0 (fully on) power state. |
| [PoFxSetComponentLatency function](nf-wdm-pofxsetcomponentlatency.md) | The PoFxSetComponentLatency routine specifies the maximum latency that can be tolerated in the transition from the idle condition to the active condition in the specified component. |
| [PoFxSetComponentResidency function](nf-wdm-pofxsetcomponentresidency.md) | The PoFxSetComponentResidency routine sets the estimated time for how long a component is likely to remain idle after the component enters the idle condition. |
| [PoFxSetComponentWake function](nf-wdm-pofxsetcomponentwake.md) | The PoFxSetComponentWake routine indicates whether the driver arms the specified component to wake whenever the component enters the idle condition. |
| [PoFxSetDeviceIdleTimeout function](nf-wdm-pofxsetdeviceidletimeout.md) | The PoFxSetDeviceIdleTimeout routine specifies the minimum time interval from when the last component of the device enters the idle condition to when the power management framework (PoFx) calls the driver's DevicePowerNotRequiredCallback routine. |
| [PoFxSetTargetDripsDevicePowerState function](nf-wdm-pofxsettargetdripsdevicepowerstate.md) | This routine is called to notify the power manager of the device's target device power state for DRIPS. The driver can override the DRIPS constraint provided by the PEP. |
| [PoFxStartDevicePowerManagement function](nf-wdm-pofxstartdevicepowermanagement.md) | The PoFxStartDevicePowerManagement routine completes the registration of a device with the power management framework (PoFx) and starts device power management. |
| [PoFxUnregisterDevice function](nf-wdm-pofxunregisterdevice.md) | The PoFxUnregisterDevice routine removes the registration of a device from the power management framework (PoFx). |
| [PoGetSystemWake function](nf-wdm-pogetsystemwake.md) | The PoGetSystemWake routine determines whether a specified IRP has been marked as waking the system from a sleeping state. |
| [PoQueryWatchdogTime function](nf-wdm-poquerywatchdogtime.md) | The PoQueryWatchdogTime routine indicates whether the power manager has enabled a watchdog time-out counter for any power IRP that is currently assigned to the device stack. |
| [PoRegisterDeviceForIdleDetection function](nf-wdm-poregisterdeviceforidledetection.md) | The PoRegisterDeviceForIdleDetection routine enables or cancels idle detection and sets idle time-out values for a device. |
| [PoRegisterPowerSettingCallback function](nf-wdm-poregisterpowersettingcallback.md) | The PoRegisterPowerSettingCallback routine registers a power-setting callback routine to receive notifications of changes in the specified power setting. |
| [PoRegisterSystemState function](nf-wdm-poregistersystemstate.md) | The PoRegisterSystemState routine registers the system as busy due to certain activity. |
| [PoRequestPowerIrp function](nf-wdm-porequestpowerirp.md) | The PoRequestPowerIrp routine allocates a power IRP and sends it to the top driver in the device stack for the specified device. |
| [PoSetDeviceBusyEx function](nf-wdm-posetdevicebusyex.md) | The PoSetDeviceBusyEx routine notifies the power manager that the device associated with the specified idle counter is busy. |
| [PoSetPowerRequest function](nf-wdm-posetpowerrequest.md) | The PoSetPowerRequest routine increments the count for the specified power request type. |
| [PoSetPowerState function](nf-wdm-posetpowerstate.md) | The PoSetPowerState routine notifies the system of a change in the device power state for a device. |
| [PoSetSystemState function](nf-wdm-posetsystemstate.md) | Drivers call the PoSetSystemState routine to indicate that the system is active. |
| [PoSetSystemWake function](nf-wdm-posetsystemwake.md) | The PoSetSystemWake routine marks the specified IRP as one that contributed to waking the system from a sleep state. |
| [PoStartDeviceBusy function](nf-wdm-postartdevicebusy.md) | The PoStartDeviceBusy routine marks the start of a period of time in which the device is busy. |
| [PoStartNextPowerIrp function](nf-wdm-postartnextpowerirp.md) | The PoStartNextPowerIrp routine signals the power manager that the driver is ready to handle the next power IRP. (Windows Server 2003, Windows XP, and Windows 2000 only.). |
| [PoUnregisterPowerSettingCallback function](nf-wdm-pounregisterpowersettingcallback.md) | The PoUnregisterPowerSettingCallback routine unregisters a power-setting callback routine that a driver previously registered by calling the PoRegisterPowerSettingCallback routine. |
| [PoUnregisterSystemState function](nf-wdm-pounregistersystemstate.md) | The PoUnregisterSystemState routine cancels a system state registration created by PoRegisterSystemState. |
| [PopEntryList function](nf-wdm-popentrylist.md) | The PopEntryList routine removes the first entry from a singly linked list of SINGLE_LIST_ENTRY structures. |
| [ProbeForRead function](nf-wdm-probeforread.md) | The ProbeForRead routine checks that a user-mode buffer actually resides in the user portion of the address space, and is correctly aligned. |
| [ProbeForWrite function](nf-wdm-probeforwrite.md) | The ProbeForWrite routine checks that a user-mode buffer actually resides in the user-mode portion of the address space, is writable, and is correctly aligned. |
| [PsCreateSystemThread function](nf-wdm-pscreatesystemthread.md) | The PsCreateSystemThread routine creates a system thread that executes in kernel mode and returns a handle for the thread. |
| [PsGetCurrentThread function](nf-wdm-psgetcurrentthread.md) | The PsGetCurrentThread routine identifies the current thread. |
| [PsGetVersion function](nf-wdm-psgetversion.md) | This function is obsolete in Windows XP and later versions of the Windows operating system. Use RtlGetVersion instead.PsGetVersion returns caller-selected information about the current version of the NT-based operating system. |
| [PsQueryTotalCycleTimeProcess function](nf-wdm-psquerytotalcycletimeprocess.md) | The PsQueryTotalCycleTimeProcess routine returns the accumulated cycle time for the specified process. |
| [PsTerminateSystemThread function](nf-wdm-psterminatesystemthread.md) | The PsTerminateSystemThread routine terminates the current system thread. |
| [PushEntryList function](nf-wdm-pushentrylist.md) | The PushEntryList routine inserts an entry at the beginning of a singly linked list of SINGLE_LIST_ENTRY structures. |
| [READ_PORT_BUFFER_UCHAR function](nf-wdm-read_port_buffer_uchar.md) | The READ_PORT_BUFFER_UCHAR routine reads a number of bytes from the specified port address into a buffer. |
| [READ_PORT_BUFFER_ULONG function](nf-wdm-read_port_buffer_ulong.md) | The READ_PORT_BUFFER_ULONG routine reads a number of ULONG values from the specified port address into a buffer. |
| [READ_PORT_BUFFER_USHORT function](nf-wdm-read_port_buffer_ushort.md) | The READ_PORT_BUFFER_USHORT routine reads a number of USHORT values from the specified port address into a buffer. |
| [READ_PORT_UCHAR function](nf-wdm-read_port_uchar.md) | The READ_PORT_UCHAR routine reads a byte from the specified port address. |
| [READ_PORT_ULONG function](nf-wdm-read_port_ulong.md) | The READ_PORT_ULONG routine reads a ULONG value from the specified port address. |
| [READ_PORT_USHORT function](nf-wdm-read_port_ushort.md) | The READ_PORT_USHORT routine reads a USHORT value from the specified port address. |
| [READ_REGISTER_BUFFER_UCHAR function](nf-wdm-read_register_buffer_uchar.md) | The READ_REGISTER_BUFFER_UCHAR routine reads a number of bytes from the specified register address into a buffer. |
| [READ_REGISTER_BUFFER_ULONG function](nf-wdm-read_register_buffer_ulong.md) | The READ_REGISTER_BUFFER_ULONG routine reads a number of ULONG values from the specified register address into a buffer. |
| [READ_REGISTER_BUFFER_ULONG64 function](nf-wdm-read_register_buffer_ulong64.md) | The READ_REGISTER_BUFFER_ULONG64 function reads a number of ULONG64 values from the specified register address into a buffer. |
| [READ_REGISTER_BUFFER_USHORT function](nf-wdm-read_register_buffer_ushort.md) | The READ_REGISTER_BUFFER_USHORT routine reads a number of USHORT values from the specified register address into a buffer. |
| [READ_REGISTER_UCHAR function](nf-wdm-read_register_uchar.md) | The READ_REGISTER_UCHAR routine reads a byte from the specified register address. |
| [READ_REGISTER_ULONG function](nf-wdm-read_register_ulong.md) | The READ_REGISTER_ULONG routine reads a ULONG value from the specified register address. |
| [READ_REGISTER_ULONG64 function](nf-wdm-read_register_ulong64.md) | The READ_REGISTER_ULONG64 function reads a ULONG64 value from the specified register address. |
| [READ_REGISTER_USHORT function](nf-wdm-read_register_ushort.md) | The READ_REGISTER_USHORT routine reads a USHORT value from the specified register address. |
| [RemoveEntryList function](nf-wdm-removeentrylist.md) | The RemoveEntryList routine removes an entry from a doubly linked list of LIST_ENTRY structures. |
| [RemoveHeadList function](nf-wdm-removeheadlist.md) | The RemoveHeadList routine removes an entry from the beginning of a doubly linked list of LIST_ENTRY structures. |
| [RemoveTailList function](nf-wdm-removetaillist.md) | The RemoveTailList routine removes an entry from the end of a doubly linked list of LIST_ENTRY structures. |
| [RtlAnsiStringToUnicodeString function](nf-wdm-rtlansistringtounicodestring.md) | RtlAnsiStringToUnicodeString converts the given ANSI source string into a Unicode string. |
| [RtlAppendUnicodeStringToString function](nf-wdm-rtlappendunicodestringtostring.md) | The RtlAppendUnicodeStringToString routine concatenates two Unicode strings. |
| [RtlAppendUnicodeToString function](nf-wdm-rtlappendunicodetostring.md) | The RtlAppendUnicodeToString routine concatenates the supplied Unicode string to a buffered Unicode string. |
| [RtlAreBitsClear function](nf-wdm-rtlarebitsclear.md) | The RtlAreBitsClear routine determines whether a given range of bits within a bitmap variable is clear. |
| [RtlAreBitsSet function](nf-wdm-rtlarebitsset.md) | The RtlAreBitsSet routine determines whether a given range of bits within a bitmap variable is set. |
| [RtlCheckRegistryKey function](nf-wdm-rtlcheckregistrykey.md) | The RtlCheckRegistryKey routine checks for the existence of a given named key in the registry. |
| [RtlClearAllBits function](nf-wdm-rtlclearallbits.md) | The RtlClearAllBits routine sets all bits in a given bitmap variable to zero. |
| [RtlClearBit function](nf-wdm-rtlclearbit.md) | The RtlClearBit routine sets the specified bit in a bitmap to zero. |
| [RtlClearBits function](nf-wdm-rtlclearbits.md) | The RtlClearBits routine sets all bits in the specified range of bits in the bitmap to zero. |
| [RtlCmDecodeMemIoResource function](nf-wdm-rtlcmdecodememioresource.md) | The RtlCmDecodeMemIoResource routine provides the starting address and length of a CM_PARTIAL_RESOURCE_DESCRIPTOR structure that describes a range of memory or I/O port addresses. |
| [RtlCmEncodeMemIoResource function](nf-wdm-rtlcmencodememioresource.md) | The RtlCmEncodeMemIoResource routine updates a CM_PARTIAL_RESOURCE_DESCRIPTOR structure to describe a range of memory or I/O port addresses. |
| [RtlCompareMemory function](nf-wdm-rtlcomparememory.md) | The RtlCompareMemory routine compares two blocks of memory and returns the number of bytes that match. |
| [RtlCompareUnicodeString function](nf-wdm-rtlcompareunicodestring.md) | The RtlCompareUnicodeString routine compares two Unicode strings. |
| [RtlConvertLongToLargeInteger function](nf-wdm-rtlconvertlongtolargeinteger.md) | The RtlConvertLongToLargeInteger routine converts the input signed integer to a signed large integer. |
| [RtlConvertUlongToLargeInteger function](nf-wdm-rtlconvertulongtolargeinteger.md) | The RtlConvertUlongToLargeInteger routine converts the input unsigned integer to a signed large integer. For Windows XP and later versions of Windows, do not use this routine; use the native support for __int64. |
| [RtlCopyUnicodeString function](nf-wdm-rtlcopyunicodestring.md) | The RtlCopyUnicodeString routine copies a source string to a destination string. |
| [RtlCreateRegistryKey function](nf-wdm-rtlcreateregistrykey.md) | The RtlCreateRegistryKey routine adds a key object in the registry along a given relative path. |
| [RtlCreateSecurityDescriptor function](nf-wdm-rtlcreatesecuritydescriptor.md) | The RtlCreateSecurityDescriptor routine initializes a new absolute-format security descriptor. On return, the security descriptor is initialized with no system ACL, no discretionary ACL, no owner, no primary group, and all control flags set to zero. |
| [RtlDeleteRegistryValue function](nf-wdm-rtldeleteregistryvalue.md) | The RtlDeleteRegistryValue routine removes the specified entry name and the associated values from the registry along the given relative path. |
| [RtlDowncaseUnicodeChar function](nf-wdm-rtldowncaseunicodechar.md) | The RtlDowncaseUnicodeChar routine converts the specified Unicode character to lowercase. |
| [RtlEqualUnicodeString function](nf-wdm-rtlequalunicodestring.md) | The RtlEqualUnicodeString routine compares two Unicode strings to determine whether they are equal. |
| [RtlFindClearBits function](nf-wdm-rtlfindclearbits.md) | The RtlFindClearBits routine searches for a range of clear bits of a requested size within a bitmap. |
| [RtlFindClearBitsAndSet function](nf-wdm-rtlfindclearbitsandset.md) | The RtlFindClearBitsAndSet routine searches for a range of clear bits of a requested size within a bitmap and sets all bits in the range when it has been located. |
| [RtlFindClearRuns function](nf-wdm-rtlfindclearruns.md) | The RtlFindClearRuns routine finds the specified number of runs of clear bits within a given bitmap. |
| [RtlFindFirstRunClear function](nf-wdm-rtlfindfirstrunclear.md) | The RtlFindFirstRunClear routine searches for the initial contiguous range of clear bits within a given bitmap. |
| [RtlFindLastBackwardRunClear function](nf-wdm-rtlfindlastbackwardrunclear.md) | The RtlFindLastBackwardRunClear routine searches a given bitmap for the preceding clear run of bits, starting from the specified index position. |
| [RtlFindLeastSignificantBit function](nf-wdm-rtlfindleastsignificantbit.md) | The RtlFindLeastSignificantBit routine returns the zero-based position of the least significant nonzero bit in its parameter. |
| [RtlFindLongestRunClear function](nf-wdm-rtlfindlongestrunclear.md) | The RtlFindLongestRunClear routine searches for the largest contiguous range of clear bits within a given bitmap. |
| [RtlFindMostSignificantBit function](nf-wdm-rtlfindmostsignificantbit.md) | The RtlFindMostSignificantBit routine returns the zero-based position of the most significant nonzero bit in its parameter. |
| [RtlFindNextForwardRunClear function](nf-wdm-rtlfindnextforwardrunclear.md) | The RtlFindNextForwardRunClear routine searches a given bitmap variable for the next clear run of bits, starting from the specified index position. |
| [RtlFindSetBits function](nf-wdm-rtlfindsetbits.md) | The RtlFindSetBits routine searches for a range of set bits of a requested size within a bitmap. |
| [RtlFindSetBitsAndClear function](nf-wdm-rtlfindsetbitsandclear.md) | The RtlFindSetBitsAndClear routine searches for a range of set bits of a requested size within a bitmap and clears all bits in the range when it has been located. |
| [RtlFreeAnsiString function](nf-wdm-rtlfreeansistring.md) | The RtlFreeAnsiString routine releases storage that was allocated by RtlUnicodeStringToAnsiString. |
| [RtlFreeUnicodeString function](nf-wdm-rtlfreeunicodestring.md) | The RtlFreeUnicodeString routine releases storage that was allocated by RtlAnsiStringToUnicodeString or RtlUpcaseUnicodeString. |
| [RtlGUIDFromString function](nf-wdm-rtlguidfromstring.md) | The RtlGUIDFromString routine converts the given Unicode string to a GUID in binary format. |
| [RtlGetVersion function](nf-wdm-rtlgetversion.md) | The RtlGetVersion routine returns version information about the currently running operating system. |
| [RtlHashUnicodeString function](nf-wdm-rtlhashunicodestring.md) | The RtlHashUnicodeString routine creates a hash value from a given Unicode string and hash algorithm. |
| [RtlInitAnsiString function](nf-wdm-rtlinitansistring.md) | The RtlInitAnsiString routine initializes a counted string of ANSI characters. |
| [RtlInitString function](nf-wdm-rtlinitstring.md) | The RtlInitString routine initializes a counted string of 8-bit characters. |
| [RtlInitStringEx function](nf-wdm-rtlinitstringex.md) | The RtlInitStringEx routine initializes a counted string of 8-bit characters. |
| [RtlInitUnicodeString function](nf-wdm-rtlinitunicodestring.md) | For more information, see the WdmlibRtlInitUnicodeStringEx function. |
| [RtlInitializeBitMap function](nf-wdm-rtlinitializebitmap.md) | The RtlInitializeBitMap routine initializes the header of a bitmap variable. |
| [RtlInt64ToUnicodeString function](nf-wdm-rtlint64tounicodestring.md) | The RtlInt64ToUnicodeString routine converts a specified unsigned 64-bit integer value to a Unicode string that represents the value in a specified base. |
| [RtlIntegerToUnicodeString function](nf-wdm-rtlintegertounicodestring.md) | The RtlIntegerToUnicodeString routine converts an unsigned integer value to a null-terminated string of one or more Unicode characters in the specified base. |
| [RtlIoDecodeMemIoResource function](nf-wdm-rtliodecodememioresource.md) | The RtlIoDecodeMemIoResource routine provides the address information that is contained in an IO_RESOURCE_DESCRIPTOR structure that describes a range of memory or I/O port addresses. |
| [RtlIoEncodeMemIoResource function](nf-wdm-rtlioencodememioresource.md) | The RtlIoEncodeMemIoResource routine updates an IO_RESOURCE_DESCRIPTOR structure to describe a range of memory or I/O port addresses. |
| [RtlIsNtDdiVersionAvailable function](nf-wdm-rtlisntddiversionavailable.md) | The RtlIsNtDdiVersionAvailable routine determines if a specified version of the Microsoft Windows device driver interface (DDI) is available. |
| [RtlIsServicePackVersionInstalled function](nf-wdm-rtlisservicepackversioninstalled.md) | The RtlIsServicePackVersionInstalled routine determines if a specified service pack version of the Microsoft Windows device driver interface (DDI) is installed. |
| [RtlLengthSecurityDescriptor function](nf-wdm-rtllengthsecuritydescriptor.md) | The RtlLengthSecurityDescriptor routine returns the size of a given security descriptor. |
| [RtlNumberOfClearBits function](nf-wdm-rtlnumberofclearbits.md) | The RtlNumberOfClearBits routine returns a count of the clear bits in a given bitmap variable. |
| [RtlNumberOfSetBits function](nf-wdm-rtlnumberofsetbits.md) | The RtlNumberOfSetBits routine returns a count of the set bits in a given bitmap variable. |
| [RtlNumberOfSetBitsUlongPtr function](nf-wdm-rtlnumberofsetbitsulongptr.md) | The RtlNumberOfSetBitsUlongPtr routine returns the number of bits in the specified ULONG_PTR integer value that are set to one. |
| [RtlPrefetchMemoryNonTemporal function](nf-wdm-rtlprefetchmemorynontemporal.md) | The RtlPrefetchMemoryNonTemporal routine provides a hint to the processor that a buffer should be temporarily moved into the processor cache. |
| [RtlQueryRegistryValues function](nf-wdm-rtlqueryregistryvalues.md) | The RtlQueryRegistryValues routine allows the caller to query several values from the registry subtree with a single call. |
| [RtlSecureZeroMemory function](nf-wdm-rtlsecurezeromemory.md) | The RtlSecureZeroMemory routine fills a block of memory with zeros in a way that is guaranteed to be secure. |
| [RtlSetAllBits function](nf-wdm-rtlsetallbits.md) | The RtlSetAllBits routine sets all bits in a given bitmap variable. |
| [RtlSetBit function](nf-wdm-rtlsetbit.md) | The RtlSetBit routine sets the specified bit in a bitmap to one. |
| [RtlSetBits function](nf-wdm-rtlsetbits.md) | The RtlSetBits routine sets all bits in a given range of a given bitmap variable. |
| [RtlSetDaclSecurityDescriptor function](nf-wdm-rtlsetdaclsecuritydescriptor.md) | The RtlSetDaclSecurityDescriptor routine sets the DACL information of an absolute-format security descriptor, or if there is already a DACL present in the security descriptor, it is superseded. |
| [RtlStringFromGUID function](nf-wdm-rtlstringfromguid.md) | The RtlStringFromGUID routine converts a given GUID from binary format into a Unicode string. |
| [RtlTestBit function](nf-wdm-rtltestbit.md) | The RtlTestBit routine returns the value of a bit in a bitmap. |
| [RtlTimeFieldsToTime function](nf-wdm-rtltimefieldstotime.md) | The RtlTimeFieldsToTime routine converts TIME_FIELDS information to a system time value. |
| [RtlTimeToTimeFields function](nf-wdm-rtltimetotimefields.md) | The RtlTimeToTimeFields routine converts system time into a TIME_FIELDS structure. |
| [RtlUTF8ToUnicodeN function](nf-wdm-rtlutf8tounicoden.md) | The RtlUTF8ToUnicodeN routine converts a UTF-8 string to a Unicode string. |
| [RtlUnicodeStringToAnsiString function](nf-wdm-rtlunicodestringtoansistring.md) | The RtlUnicodeStringToAnsiString routine converts a given Unicode string into an ANSI string. |
| [RtlUnicodeStringToInteger function](nf-wdm-rtlunicodestringtointeger.md) | The RtlUnicodeStringToInteger routine converts a Unicode string representation of a number to the equivalent integer value. |
| [RtlUnicodeToUTF8N function](nf-wdm-rtlunicodetoutf8n.md) | The RtlUnicodeToUTF8N routine converts a Unicode string to a UTF-8 string. |
| [RtlUpcaseUnicodeChar function](nf-wdm-rtlupcaseunicodechar.md) | The RtlUpcaseUnicodeChar routine converts the specified Unicode character to uppercase. |
| [RtlValidRelativeSecurityDescriptor function](nf-wdm-rtlvalidrelativesecuritydescriptor.md) | The RtlValidRelativeSecurityDescriptor routine checks the validity of a self-relative security descriptor. |
| [RtlValidSecurityDescriptor function](nf-wdm-rtlvalidsecuritydescriptor.md) | The RtlValidSecurityDescriptor routine checks a given security descriptor's validity. |
| [RtlVerifyVersionInfo function](nf-wdm-rtlverifyversioninfo.md) | The RtlVerifyVersionInfo routine compares a specified set of operating system version requirements to the corresponding attributes of the currently running version of the operating system. |
| [RtlWriteRegistryValue function](nf-wdm-rtlwriteregistryvalue.md) | The RtlWriteRegistryValue routine writes caller-supplied data into the registry along the specified relative path at the given value name. |
| [RtlxAnsiStringToUnicodeSize function](nf-wdm-rtlxansistringtounicodesize.md) | The RtlxAnsiStringToUnicodeSize routine returns the number of bytes that are required for a null-terminated Unicode string that is equivalent to a specified ANSI string. |
| [RtlxUnicodeStringToAnsiSize function](nf-wdm-rtlxunicodestringtoansisize.md) | The RtlxUnicodeStringToAnsiSize routine returns the number of bytes required for a null-terminated ANSI string that is equivalent to a specified Unicode string. |
| [SeAccessCheck function](nf-wdm-seaccesscheck.md) | The SeAccessCheck routine determines whether the requested access rights can be granted to an object protected by a security descriptor and an object owner. |
| [SeAssignSecurity function](nf-wdm-seassignsecurity.md) | The SeAssignSecurity routine builds a self-relative security descriptor for a new object, given the security descriptor of its parent directory and any originally requested security for the object. |
| [SeAssignSecurityEx function](nf-wdm-seassignsecurityex.md) | The SeAssignSecurityEx routine builds a self-relative security descriptor for a new object given the following optional parameters |
| [SeCaptureSubjectContext function](nf-wdm-secapturesubjectcontext.md) | The SeCaptureSubjectContext routine captures the security context of the calling thread for access validation and auditing. |
| [SeDeassignSecurity function](nf-wdm-sedeassignsecurity.md) | The SeDeassignSecurity routine deallocates the memory associated with a security descriptor that was assigned using SeAssignSecurity. |
| [SeEtwWriteKMCveEvent function](nf-wdm-seetwwritekmcveevent.md) | The SeEtwWriteKMCveEvent function is a tracing function for publishing events when an attempted security vulnerability exploit is detected in your kernel-mode drivers. |
| [SeLockSubjectContext function](nf-wdm-selocksubjectcontext.md) | The SeLockSubjectContext routine locks the primary and impersonation tokens of a captured subject context. |
| [SeReleaseSubjectContext function](nf-wdm-sereleasesubjectcontext.md) | The SeReleaseSubjectContext routine releases a subject security context captured by an earlier call to SeCaptureSubjectContext. |
| [SeUnlockSubjectContext function](nf-wdm-seunlocksubjectcontext.md) | The SeUnlockSubjectContext routine unlocks the tokens of a captured subject context that were locked by a call to SeLockSubjectContext. |
| [SeValidSecurityDescriptor function](nf-wdm-sevalidsecuritydescriptor.md) | The SeValidSecurityDescriptor routine returns whether a given security descriptor is structurally valid. |
| [TmCommitComplete function](nf-wdm-tmcommitcomplete.md) | The TmCommitComplete routine notifies KTM that the calling resource manager has finished committing a transaction. |
| [TmCommitEnlistment function](nf-wdm-tmcommitenlistment.md) | The TmCommitEnlistment routine initiates the commit operation for a specified enlistment's transaction. |
| [TmCommitTransaction function](nf-wdm-tmcommittransaction.md) | The TmCommitTransaction routine initiates a commit operation for a specified transaction. |
| [TmCreateEnlistment function](nf-wdm-tmcreateenlistment.md) | The TmCreateEnlistment routine creates a new enlistment object for a transaction. |
| [TmDereferenceEnlistmentKey function](nf-wdm-tmdereferenceenlistmentkey.md) | The TmDereferenceEnlistmentKey routine decrements the reference count for the key of a specified enlistment object. |
| [TmEnableCallbacks function](nf-wdm-tmenablecallbacks.md) | The TmEnableCallbacks routine enables a callback routine that receives transaction notifications. |
| [TmGetTransactionId function](nf-wdm-tmgettransactionid.md) | The TmGetTransactionId routine retrieves a transaction object's unit of work (UOW) identifier. |
| [TmInitializeTransactionManager function](nf-wdm-tminitializetransactionmanager.md) | The TmInitializeTransactionManager routine initializes a transaction manager object. |
| [TmIsTransactionActive function](nf-wdm-tmistransactionactive.md) | The TmIsTransactionActive routine indicates whether a specified transaction is in its active state. |
| [TmPrePrepareComplete function](nf-wdm-tmprepreparecomplete.md) | The TmPrePrepareComplete routine notifies KTM that the calling resource manager has finished preliminary preparation of a transaction's data. |
| [TmPrePrepareEnlistment function](nf-wdm-tmpreprepareenlistment.md) | The TmPrePrepareEnlistment routine initiates the pre-prepare operation for a specified enlistment's transaction. |
| [TmPrepareComplete function](nf-wdm-tmpreparecomplete.md) | The TmPrepareComplete routine notifies KTM that the calling resource manager has finished preparing a transaction's data. |
| [TmPrepareEnlistment function](nf-wdm-tmprepareenlistment.md) | The TmPrepareEnlistment routine initiates the prepare operation for a specified enlistment's transaction. |
| [TmReadOnlyEnlistment function](nf-wdm-tmreadonlyenlistment.md) | The TmReadOnlyEnlistment routine sets a specified enlistment to be read-only. |
| [TmRecoverEnlistment function](nf-wdm-tmrecoverenlistment.md) | The TmRecoverEnlistment routine initiates a recovery operation for the transaction that is associated with a specified enlistment. |
| [TmRecoverResourceManager function](nf-wdm-tmrecoverresourcemanager.md) | The TmRecoverResourceManager routine tries to recover the transaction that is associated with each enlistment of a specified resource manager object. |
| [TmRecoverTransactionManager function](nf-wdm-tmrecovertransactionmanager.md) | The TmRecoverTransactionManager routine reconstructs the state of the transaction manager object (including all transactions, enlistments, and resource managers) from the recovery information that is in the log stream. |
| [TmReferenceEnlistmentKey function](nf-wdm-tmreferenceenlistmentkey.md) | The TmReferenceEnlistmentKey routine increments the reference count for the key of a specified enlistment object and retrieves the key. |
| [TmRenameTransactionManager function](nf-wdm-tmrenametransactionmanager.md) | The TmRenameTransactionManager routine changes the identity of the transaction manager object that is stored in the CLFS log file stream contained in the log file name. |
| [TmRequestOutcomeEnlistment function](nf-wdm-tmrequestoutcomeenlistment.md) | The TmRequestOutcomeEnlistment routine asks KTM to try to provide an immediate outcome (commit or rollback) for the transaction that is associated with a specified enlistment. |
| [TmRollbackComplete function](nf-wdm-tmrollbackcomplete.md) | The TmRollbackComplete routine notifies KTM that the calling resource manager has finished rolling back a transaction's data. |
| [TmRollbackEnlistment function](nf-wdm-tmrollbackenlistment.md) | The TmRollbackEnlistment routine rolls back a specified enlistment. |
| [TmRollbackTransaction function](nf-wdm-tmrollbacktransaction.md) | The TmRollbackTransaction routine initiates a rollback operation for a specified transaction. |
| [TmSinglePhaseReject function](nf-wdm-tmsinglephasereject.md) | The TmSinglePhaseReject routine informs KTM that the calling resource manager will not support a single-phase commit operation for a specified enlistment. |
| [VslCreateSecureSection function](nf-wdm-vslcreatesecuresection.md) | This material is not yet available. This placeholder topic is provided as an example of documentation that may be included in a later release. |
| [WRITE_PORT_BUFFER_UCHAR function](nf-wdm-write_port_buffer_uchar.md) | The WRITE_PORT_BUFFER_UCHAR routine writes a number of bytes from a buffer to the specified port. |
| [WRITE_PORT_BUFFER_ULONG function](nf-wdm-write_port_buffer_ulong.md) | The WRITE_PORT_BUFFER_ULONG routine writes a number of ULONG values from a buffer to the specified port address. |
| [WRITE_PORT_BUFFER_USHORT function](nf-wdm-write_port_buffer_ushort.md) | The WRITE_PORT_BUFFER_USHORT routine writes a number of USHORT values from a buffer to the specified port address. |
| [WRITE_PORT_UCHAR function](nf-wdm-write_port_uchar.md) | The WRITE_PORT_UCHAR routine writes a byte to the specified port address. |
| [WRITE_PORT_ULONG function](nf-wdm-write_port_ulong.md) | The WRITE_PORT_ULONG routine writes a ULONG value to the specified port address. |
| [WRITE_PORT_USHORT function](nf-wdm-write_port_ushort.md) | The WRITE_PORT_USHORT routine writes a USHORT value to the specified port address. |
| [WRITE_REGISTER_BUFFER_UCHAR function](nf-wdm-write_register_buffer_uchar.md) | The WRITE_REGISTER_BUFFER_UCHAR routine writes a number of bytes from a buffer to the specified register. |
| [WRITE_REGISTER_BUFFER_ULONG function](nf-wdm-write_register_buffer_ulong.md) | The WRITE_REGISTER_BUFFER_ULONG routine writes a number of ULONG values from a buffer to the specified register. |
| [WRITE_REGISTER_BUFFER_ULONG64 function](nf-wdm-write_register_buffer_ulong64.md) | The WRITE_REGISTER_BUFFER_ULONG64 function writes a number of ULONG64 values from a buffer to the specified register. |
| [WRITE_REGISTER_BUFFER_USHORT function](nf-wdm-write_register_buffer_ushort.md) | The WRITE_REGISTER_BUFFER_USHORT routine writes a number of USHORT values from a buffer to the specified register. |
| [WRITE_REGISTER_UCHAR function](nf-wdm-write_register_uchar.md) | The WRITE_REGISTER_UCHAR routine writes a byte to the specified address. |
| [WRITE_REGISTER_ULONG function](nf-wdm-write_register_ulong.md) | The WRITE_REGISTER_ULONG routine writes a ULONG value to the specified address. |
| [WRITE_REGISTER_ULONG64 function](nf-wdm-write_register_ulong64.md) | The WRITE_REGISTER_ULONG64 function writes a ULONG64 value to the specified address. |
| [WRITE_REGISTER_USHORT function](nf-wdm-write_register_ushort.md) | The WRITE_REGISTER_USHORT routine writes a USHORT value to the specified address. |
| [WmiQueryTraceInformation function](nf-wdm-wmiquerytraceinformation.md) | The WmiQueryTraceInformation routine returns information about a WMI event trace. |
| [WmiTraceMessage function](nf-wdm-wmitracemessage.md) | The WmiTraceMessage routine adds a message to the output log of a WPP software tracing session. |
| [WmiTraceMessageVa function](nf-wdm-wmitracemessageva.md) | The WmiTraceMessageVa routine adds a message to the output log of a WPP software tracing session. |
| [ZwClose function](nf-wdm-zwclose.md) | The ZwClose routine closes an object handle. |
| [ZwCommitComplete function](nf-wdm-zwcommitcomplete.md) | The ZwCommitComplete routine notifies KTM that the calling resource manager has finished committing a transaction's data. |
| [ZwCommitEnlistment function](nf-wdm-zwcommitenlistment.md) | The ZwCommitEnlistment routine initiates the commit operation for a specified enlistment's transaction. |
| [ZwCommitTransaction function](nf-wdm-zwcommittransaction.md) | The ZwCommitTransaction routine initiates a commit operation for a specified transaction. |
| [ZwCreateDirectoryObject function](nf-wdm-zwcreatedirectoryobject.md) | The ZwCreateDirectoryObject routine creates or opens an object-directory object. |
| [ZwCreateEnlistment function](nf-wdm-zwcreateenlistment.md) | The ZwCreateEnlistment routine creates a new enlistment object for a transaction. |
| [ZwCreateFile function](nf-wdm-zwcreatefile.md) | The ZwCreateFile routine creates a new file or opens an existing file. |
| [ZwCreateKey function](nf-wdm-zwcreatekey.md) | The ZwCreateKey routine creates a new registry key or opens an existing one. |
| [ZwCreateKeyTransacted function](nf-wdm-zwcreatekeytransacted.md) | The ZwCreateKeyTransacted routine creates a new registry key or opens an existing one, and it associates the key with a transaction. |
| [ZwCreateResourceManager function](nf-wdm-zwcreateresourcemanager.md) | The ZwCreateResourceManager routine creates a resource manager object. |
| [ZwCreateSection function](nf-wdm-zwcreatesection.md) | The ZwCreateSection routine creates a section object. |
| [ZwCreateTransaction function](nf-wdm-zwcreatetransaction.md) | The ZwCreateTransaction routine creates a transaction object. |
| [ZwCreateTransactionManager function](nf-wdm-zwcreatetransactionmanager.md) | The ZwCreateTransactionManager routine creates a new transaction manager object. |
| [ZwDeleteKey function](nf-wdm-zwdeletekey.md) | The ZwDeleteKey routine deletes an open key from the registry. |
| [ZwDeleteValueKey function](nf-wdm-zwdeletevaluekey.md) | The ZwDeleteValueKey routine deletes a value entry matching a name from an open key in the registry. If no such entry exists, an error is returned. |
| [ZwEnumerateKey function](nf-wdm-zwenumeratekey.md) | The ZwEnumerateKey routine returns information about a subkey of an open registry key. |
| [ZwEnumerateTransactionObject function](nf-wdm-zwenumeratetransactionobject.md) | The ZwEnumerateTransactionObject routine enumerates the KTM objects on a computer. |
| [ZwEnumerateValueKey function](nf-wdm-zwenumeratevaluekey.md) | The ZwEnumerateValueKey routine gets information about the value entries of an open key. |
| [ZwFlushKey function](nf-wdm-zwflushkey.md) | The ZwFlushKey routine forces a registry key to be committed to disk. |
| [ZwGetNotificationResourceManager function](nf-wdm-zwgetnotificationresourcemanager.md) | The ZwGetNotificationResourceManager routine retrieves the next transaction notification from a specified resource manager's notification queue. |
| [ZwLoadDriver function](nf-wdm-zwloaddriver.md) | The ZwLoadDriver routine loads a driver into the system. |
| [ZwMakeTemporaryObject function](nf-wdm-zwmaketemporaryobject.md) | The ZwMakeTemporaryObject routine changes the attributes of an object to make it temporary. |
| [ZwMapViewOfSection function](nf-wdm-zwmapviewofsection.md) | The ZwMapViewOfSection routine maps a view of a section into the virtual address space of a subject process. |
| [ZwOpenEnlistment function](nf-wdm-zwopenenlistment.md) | The ZwOpenEnlistment routine obtains a handle to an existing enlistment object. |
| [ZwOpenEvent function](nf-wdm-zwopenevent.md) | The ZwOpenEvent routine opens a handle to an existing named event object with the specified desired access. |
| [ZwOpenFile function](nf-wdm-zwopenfile.md) | The ZwOpenFile routine opens an existing file, directory, device, or volume. |
| [ZwOpenKey function](nf-wdm-zwopenkey.md) | The ZwOpenKey routine opens an existing registry key. |
| [ZwOpenKeyEx function](nf-wdm-zwopenkeyex.md) | The ZwOpenKeyEx routine opens an existing registry key. |
| [ZwOpenKeyTransacted function](nf-wdm-zwopenkeytransacted.md) | The ZwOpenKeyTransacted routine opens an existing registry key and associates the key with a transaction. |
| [ZwOpenKeyTransactedEx function](nf-wdm-zwopenkeytransactedex.md) | The ZwOpenKeyTransactedEx routine opens an existing registry key and associates the key with a transaction. |
| [ZwOpenResourceManager function](nf-wdm-zwopenresourcemanager.md) | The ZwOpenResourceManager routine returns a handle to an existing resource manager object. |
| [ZwOpenSection function](nf-wdm-zwopensection.md) | The ZwOpenSection routine opens a handle for an existing section object. |
| [ZwOpenSymbolicLinkObject function](nf-wdm-zwopensymboliclinkobject.md) | The ZwOpenSymbolicLinkObject routine opens an existing symbolic link. |
| [ZwOpenTransaction function](nf-wdm-zwopentransaction.md) | The ZwOpenTransaction routine obtains a handle to an existing transaction object. |
| [ZwOpenTransactionManager function](nf-wdm-zwopentransactionmanager.md) | The ZwOpenTransactionManager routine obtains a handle to an existing transaction manager object. |
| [ZwPrePrepareComplete function](nf-wdm-zwprepreparecomplete.md) | The ZwPrePrepareComplete routine notifies KTM that the calling resource manager has finished preliminary preparation of a transaction's data. |
| [ZwPrePrepareEnlistment function](nf-wdm-zwpreprepareenlistment.md) | The ZwPrePrepareEnlistment routine initiates the pre-prepare operation for a specified enlistment's transaction. |
| [ZwPrepareComplete function](nf-wdm-zwpreparecomplete.md) | The ZwPrepareComplete routine notifies KTM that the calling resource manager has finished preparing a transaction's data. |
| [ZwPrepareEnlistment function](nf-wdm-zwprepareenlistment.md) | The ZwPrepareEnlistment routine initiates the prepare operation for a specified enlistment's transaction. |
| [ZwQueryFullAttributesFile function](nf-wdm-zwqueryfullattributesfile.md) | The ZwQueryFullAttributesFile routine supplies network open information for the specified file. |
| [ZwQueryInformationEnlistment function](nf-wdm-zwqueryinformationenlistment.md) | The ZwQueryInformationEnlistment routine retrieves information about a specified enlistment object. |
| [ZwQueryInformationFile function](nf-wdm-zwqueryinformationfile.md) | The ZwQueryInformationFile routine returns various kinds of information about a file object. |
| [ZwQueryInformationResourceManager function](nf-wdm-zwqueryinformationresourcemanager.md) | The ZwQueryInformationResourceManager routine retrieves information about a specified resource manager object. |
| [ZwQueryInformationTransaction function](nf-wdm-zwqueryinformationtransaction.md) | The ZwQueryInformationTransaction routine retrieves information about a specified transaction. |
| [ZwQueryInformationTransactionManager function](nf-wdm-zwqueryinformationtransactionmanager.md) | The ZwQueryInformationTransactionManager routine retrieves information about a specified transaction manager object. |
| [ZwQueryKey function](nf-wdm-zwquerykey.md) | The ZwQueryKey routine provides information about the class of a registry key, and the number and sizes of its subkeys. |
| [ZwQuerySymbolicLinkObject function](nf-wdm-zwquerysymboliclinkobject.md) | The ZwQuerySymbolicLinkObject routine returns a Unicode string that contains the target of a symbolic link. |
| [ZwQueryValueKey function](nf-wdm-zwqueryvaluekey.md) | The ZwQueryValueKey routine returns a value entry for a registry key. |
| [ZwReadFile function](nf-wdm-zwreadfile.md) | The ZwReadFile routine reads data from an open file. |
| [ZwReadOnlyEnlistment function](nf-wdm-zwreadonlyenlistment.md) | The ZwReadOnlyEnlistment routine sets a specified enlistment to be read-only. |
| [ZwRecoverEnlistment function](nf-wdm-zwrecoverenlistment.md) | The ZwRecoverEnlistment routine initiates a recovery operation for the transaction that is associated with a specified enlistment. |
| [ZwRecoverResourceManager function](nf-wdm-zwrecoverresourcemanager.md) | The ZwRecoverResourceManager routine tries to recover the transaction that is associated with each enlistment of a specified resource manager object. |
| [ZwRecoverTransactionManager function](nf-wdm-zwrecovertransactionmanager.md) | The ZwRecoverTransactionManager routine reconstructs the state of the transaction manager object (including all transactions, enlistments, and resource managers) from the recovery information that is in the log stream. |
| [ZwRollbackComplete function](nf-wdm-zwrollbackcomplete.md) | The ZwRollbackComplete routine notifies KTM that the calling resource manager has finished rolling back a transaction's data. |
| [ZwRollbackEnlistment function](nf-wdm-zwrollbackenlistment.md) | The ZwRollbackEnlistment routine rolls back the transaction that is associated with a specified enlistment. |
| [ZwRollbackTransaction function](nf-wdm-zwrollbacktransaction.md) | The ZwRollbackTransaction routine initiates a rollback operation for a specified transaction. |
| [ZwRollforwardTransactionManager function](nf-wdm-zwrollforwardtransactionmanager.md) | The ZwRollforwardTransactionManager routine initiates recovery operations for all of the in-progress transactions that are assigned to a specified transaction manager. |
| [ZwSetInformationEnlistment function](nf-wdm-zwsetinformationenlistment.md) | The ZwSetInformationEnlistment routine sets information for a specified enlistment object. |
| [ZwSetInformationFile function](nf-wdm-zwsetinformationfile.md) | The ZwSetInformationFile routine changes various kinds of information about a file object. |
| [ZwSetInformationResourceManager function](nf-wdm-zwsetinformationresourcemanager.md) | The ZwSetInformationResourceManager routine is not used. |
| [ZwSetInformationTransaction function](nf-wdm-zwsetinformationtransaction.md) | The ZwSetInformationTransaction routine sets information for a specified transaction. |
| [ZwSetValueKey function](nf-wdm-zwsetvaluekey.md) | The ZwSetValueKey routine creates or replaces a registry key's value entry. |
| [ZwSinglePhaseReject function](nf-wdm-zwsinglephasereject.md) | The ZwSinglePhaseReject routine informs KTM that the calling resource manager will not support single-phase commit operations for a specified enlistment. |
| [ZwUnloadDriver function](nf-wdm-zwunloaddriver.md) | The ZwUnloadDriver routine unloads a driver from the system. |
| [ZwUnmapViewOfSection function](nf-wdm-zwunmapviewofsection.md) | The ZwUnmapViewOfSection routine unmaps a view of a section from the virtual address space of a subject process. |
| [ZwWriteFile function](nf-wdm-zwwritefile.md) | The ZwWriteFile routine writes data to an open file. |
| [vDbgPrintEx function](nf-wdm-vdbgprintex.md) | The vDbgPrintEx routine sends a string to the kernel debugger if certain conditions are met. |
| [vDbgPrintExWithPrefix function](nf-wdm-vdbgprintexwithprefix.md) | The vDbgPrintExWithPrefix routine sends a string to the kernel debugger if certain conditions that you specify are met. This routine can append a prefix to debugger output to help organize debugging results. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [ALLOCATE_FUNCTION_EX callback](nc-wdm-allocate_function_ex.md) | The LookasideListAllocateEx routine allocates the storage for a new lookaside-list entry when a client requests an entry from a lookaside list that is empty. |
| [BOUND_CALLBACK callback](nc-wdm-bound_callback.md) | The BoundCallback routine is executed whenever the system issues a bounds exception for a user-mode thread. |
| [DRIVER_CONTROL callback](nc-wdm-driver_control.md) | This routine starts a DMA data-transfer or a data transfer operation. |
| [DRIVER_INITIALIZE callback](nc-wdm-driver_initialize.md) | DriverEntry is the first routine called after a driver is loaded, and is responsible for initializing the driver. |
| [DRIVER_LIST_CONTROL callback](nc-wdm-driver_list_control.md) | The AdapterListControl routine starts a direct memory access (DMA) scatter/gather operation. |
| [ENABLE_VIRTUALIZATION callback](nc-wdm-enable_virtualization.md) | The EnableVirtualization routine enables or disables virtualization for a PCI Express (PCIe) device that supports the single root I/O virtualization (SR-IOV) interface. |
| [ETWENABLECALLBACK callback](nc-wdm-etwenablecallback.md) | The EtwEnableCallback function is an optional driver-supplied callback function that is used to receive enable or disable notifications. |
| [EX_CALLBACK_FUNCTION callback](nc-wdm-ex_callback_function.md) | A filter driver's RegistryCallback routine can monitor, block, or modify a registry operation. |
| [FREE_FUNCTION_EX callback](nc-wdm-free_function_ex.md) | The LookasideListFreeEx routine frees the storage for a lookaside-list entry when a client tries to insert the entry into a lookaside list that is full. |
| [GET_D3COLD_CAPABILITY callback](nc-wdm-get_d3cold_capability.md) | The GetBusDriverD3ColdSupport routine enables the driver for a device to query whether the enumerating bus driver supports the D3cold device power state. |
| [GET_D3COLD_LAST_TRANSITION_STATUS callback](nc-wdm-get_d3cold_last_transition_status.md) | The GetLastTransitionStatus routine enables the driver for a device to query whether the most recent transition to the D3hot substate was followed by a transition to the D3cold substate. |
| [GET_DMA_ADAPTER callback](nc-wdm-get_dma_adapter.md) | The GetDmaAdapter routine returns a DMA_ADAPTER structure for the target device. |
| [GET_IDLE_WAKE_INFO callback](nc-wdm-get_idle_wake_info.md) | The GetIdleWakeInfo routine enables the driver for a device to discover the device power states from which the device can signal a wake event. |
| [GET_SDEV_IDENTIFIER callback](nc-wdm-get_sdev_identifier.md) | This material is not yet available. This placeholder topic is provided as an example of documentation that may be included in a later release. |
| [GET_SET_DEVICE_DATA callback](nc-wdm-get_set_device_data.md) | The GetBusData routine reads data from the device's configuration space. |
| [GET_VIRTUAL_DEVICE_DATA callback](nc-wdm-get_virtual_device_data.md) | The GetVirtualFunctionData routine reads data from the PCI Express (PCIe) configuration space of a virtual function (VF) on a device that supports the single root I/O virtualization (SR-IOV) interface. |
| [GET_VIRTUAL_DEVICE_LOCATION callback](nc-wdm-get_virtual_device_location.md) | The GetLocation routine returns the device location of a PCI Express (PCIe) virtual function (VF) on a PCI bus. A device that supports the single root I/O virtualization (SR-IOV) interface can expose one or more VFs on the PCI bus. |
| [GET_VIRTUAL_DEVICE_RESOURCES callback](nc-wdm-get_virtual_device_resources.md) | The GetResources routine returns the resources that the PCI Express (PCIe) physical function (PF) requires in order to enable virtualization on a device that supports the single root I/O virtualization (SR-IOV) interface. |
| [GET_VIRTUAL_FUNCTION_PROBED_BARS callback](nc-wdm-get_virtual_function_probed_bars.md) | The GetVirtualFunctionProbedBars routine returns the values of the PCI Express (PCIe) Base Address Registers (BARs) of a device that supports the single root I/O virtualization (SR-IOV) interface. |
| [IO_COMPLETION_ROUTINE callback](nc-wdm-io_completion_routine.md) | The IoCompletion routine completes the processing of I/O operations. |
| [IO_CSQ_ACQUIRE_LOCK callback](nc-wdm-io_csq_acquire_lock.md) | The CsqAcquireLock routine is used by the system to acquire the lock for a driver-implemented, cancel-safe IRP queue. |
| [IO_CSQ_COMPLETE_CANCELED_IRP callback](nc-wdm-io_csq_complete_canceled_irp.md) | The CsqCompleteCanceledIrp routine is used by the system to signal to the driver that it can complete a canceled IRP. |
| [IO_CSQ_INSERT_IRP callback](nc-wdm-io_csq_insert_irp.md) | The CsqInsertIrp routine is used by the system to insert an IRP into a driver-implemented, cancel-safe IRP queue. |
| [IO_CSQ_INSERT_IRP_EX callback](nc-wdm-io_csq_insert_irp_ex.md) | The CsqInsertIrpEx routine is used by the system to insert an IRP into a driver-implemented, cancel-safe IRP queue. |
| [IO_CSQ_PEEK_NEXT_IRP callback](nc-wdm-io_csq_peek_next_irp.md) | The CsqPeekNextIrp routine is used by the system to find the next matching IRP in a driver-implemented, cancel-safe IRP queue. |
| [IO_CSQ_RELEASE_LOCK callback](nc-wdm-io_csq_release_lock.md) | The CsqReleaseLock routine is used by the system to release the lock that was acquired using CsqAcquireLock. |
| [IO_CSQ_REMOVE_IRP callback](nc-wdm-io_csq_remove_irp.md) | The CsqRemoveIrp routine is used by the system to remove the specified IRP from a driver-implemented, cancel-safe IRP queue. |
| [IO_SESSION_NOTIFICATION_FUNCTION callback](nc-wdm-io_session_notification_function.md) | The IO_SESSION_NOTIFICATION_FUNCTION function type defines a callback routine through which a driver receives notifications of changes in the state of user sessions that the driver is interested in. |
| [IO_TIMER_ROUTINE callback](nc-wdm-io_timer_routine.md) | The IoTimer routine is a DPC that, if registered, is called once per second. |
| [KBUGCHECK_CALLBACK_ROUTINE callback](nc-wdm-kbugcheck_callback_routine.md) | The BugCheckCallback routine is executed whenever the system issues a bug check. |
| [KBUGCHECK_REASON_CALLBACK_ROUTINE callback](nc-wdm-kbugcheck_reason_callback_routine.md) | Driver-implemented callback functions that the system executes when it issues a bug check. |
| [KIPI_BROADCAST_WORKER callback](nc-wdm-kipi_broadcast_worker.md) | The IpiGenericCall routine runs simultaneously on all processors. |
| [KMESSAGE_SERVICE_ROUTINE callback](nc-wdm-kmessage_service_routine.md) | An InterruptMessageService routine services a message-signaled interrupt. |
| [KSERVICE_ROUTINE callback](nc-wdm-kservice_routine.md) | The InterruptService routine (ISR) quickly services a device interrupt and schedules post-interrupt processing of received data, if necessary. |
| [KSTART_ROUTINE callback](nc-wdm-kstart_routine.md) | The ThreadStart routine provides an entry point for a driver-created system thread. |
| [KSYNCHRONIZE_ROUTINE callback](nc-wdm-ksynchronize_routine.md) | The SynchCritSection routine is used to access hardware resources or driver data that are shared with a driver's InterruptService routine. |
| [MM_MDL_ROUTINE callback](nc-wdm-mm_mdl_routine.md) | A driver-supplied callback routine that is invoked after a memory descriptor list (MDL) is mapped by calling the MmMapMdl function. |
| [PALLOCATE_ADAPTER_CHANNEL callback](nc-wdm-pallocate_adapter_channel.md) | The AllocateAdapterChannel routine prepares the system for a DMA operation on behalf of the target device object, and then calls the driver-supplied AdapterControl routine to carry out the DMA operation. |
| [PALLOCATE_ADAPTER_CHANNEL_EX callback](nc-wdm-pallocate_adapter_channel_ex.md) | The AllocateAdapterChannelEx routine allocates the resources that are needed to perform a DMA transfer, and then calls the driver-supplied AdapterControl routine to initiate the DMA transfer. |
| [PALLOCATE_COMMON_BUFFER callback](nc-wdm-pallocate_common_buffer.md) | The AllocateCommonBuffer routine allocates memory and maps it so that it is simultaneously accessible from both the processor and a device for DMA operations. |
| [PALLOCATE_COMMON_BUFFER_EX callback](nc-wdm-pallocate_common_buffer_ex.md) | The AllocateCommonBufferEx routine allocates memory for a common buffer and maps this memory so that it can be accessed both by the processor and by a device that performs DMA operations. |
| [PBUILD_MDL_FROM_SCATTER_GATHER_LIST callback](nc-wdm-pbuild_mdl_from_scatter_gather_list.md) | The BuildMdlFromScatterGatherList routine builds an MDL from a scatter/gather list allocated by the system.Note  This routine is reserved for system use. |
| [PBUILD_SCATTER_GATHER_LIST callback](nc-wdm-pbuild_scatter_gather_list.md) | The BuildScatterGatherList routine prepares the system for a DMA operation, using a driver-supplied buffer to build the scatter/gather list. |
| [PBUILD_SCATTER_GATHER_LIST_EX callback](nc-wdm-pbuild_scatter_gather_list_ex.md) | The BuildScatterGatherListEx routine allocates the resources that are required for a DMA transfer, builds a scatter/gather list, and calls the driver-supplied AdapterListControl routine to initiate the DMA transfer. |
| [PCALCULATE_SCATTER_GATHER_LIST_SIZE callback](nc-wdm-pcalculate_scatter_gather_list_size.md) | The CalculateScatterGatherList routine calculates the size, in bytes, of scatter/gather list necessary to hold a given buffer. |
| [PCANCEL_ADAPTER_CHANNEL callback](nc-wdm-pcancel_adapter_channel.md) | The CancelAdapterChannel routine tries to cancel a pending request to allocate a DMA channel. |
| [PCANCEL_MAPPED_TRANSFER callback](nc-wdm-pcancel_mapped_transfer.md) | The CancelMappedTransfer routine cancels a system DMA transfer that is currently mapped to an adapter. |
| [PCI_MSIX_MASKUNMASK_ENTRY callback](nc-wdm-pci_msix_maskunmask_entry.md) | The MaskTableEntry routine masks an interrupt in the MSI-X hardware interrupt table. |
| [PCI_MSIX_SET_ENTRY callback](nc-wdm-pci_msix_set_entry.md) | The SetTableEntry routine sets the message ID for a table entry in the MSI-X hardware interrupt table. |
| [PCLFS_CLIENT_ADVANCE_TAIL_CALLBACK callback](nc-wdm-pclfs_client_advance_tail_callback.md) | The ClfsAdvanceTailCallback function advances the base log sequence number (LSN) of the client's log. |
| [PCLFS_CLIENT_LFF_HANDLER_COMPLETE_CALLBACK callback](nc-wdm-pclfs_client_lff_handler_complete_callback.md) | The ClfsLogGrowthCompleteCallback function implements the actions that the client will take when space is freed in a log that had previously been full. |
| [PCLFS_CLIENT_LOG_UNPINNED_CALLBACK callback](nc-wdm-pclfs_client_log_unpinned_callback.md) | The ClfsLogUnpinnedCallback function implements any actions that the client will take when a log that had previously been pinned becomes unpinned. |
| [PCONFIGURE_ADAPTER_CHANNEL callback](nc-wdm-pconfigure_adapter_channel.md) | The ConfigureAdapterChannel routine invokes a custom function that is implemented by the DMA controller represented by an adapter object. |
| [PCW_CALLBACK callback](nc-wdm-pcw_callback.md) | Providers can implement a PCW_CALLBACK function to receive notification when consumers perform certain actions, such as adding or removing counters from a query. |
| [PDEVICE_RESET_HANDLER callback](nc-wdm-pdevice_reset_handler.md) | The DeviceReset routine is used to reset and recover a malfunctioning device. |
| [PFLUSH_ADAPTER_BUFFERS callback](nc-wdm-pflush_adapter_buffers.md) | The FlushAdapterBuffers routine flushes any data remaining in the system DMA controller's internal cache or in a bus-master adapter's internal cache at the end of a DMA transfer operation. |
| [PFLUSH_ADAPTER_BUFFERS_EX callback](nc-wdm-pflush_adapter_buffers_ex.md) | The FlushAdapterBuffersEx routine flushes any data that remains in the data cache at the end of a DMA transfer operation performed by a system DMA controller or bus-master device. |
| [PFREE_ADAPTER_CHANNEL callback](nc-wdm-pfree_adapter_channel.md) | The FreeAdapterChannel routine releases the system DMA controller when a driver has completed all DMA operations necessary to satisfy the current IRP. |
| [PFREE_ADAPTER_OBJECT callback](nc-wdm-pfree_adapter_object.md) | The FreeAdapterObject routine releases the specified adapter object after a driver has completed all DMA operations. |
| [PFREE_COMMON_BUFFER callback](nc-wdm-pfree_common_buffer.md) | The FreeCommonBuffer routine frees a common buffer allocated by AllocateCommonBuffer, along with all resources the buffer uses. |
| [PFREE_MAP_REGISTERS callback](nc-wdm-pfree_map_registers.md) | The FreeMapRegisters routine releases a set of map registers that were saved from a call to AllocateAdapterChannel. |
| [PGET_DMA_ADAPTER_INFO callback](nc-wdm-pget_dma_adapter_info.md) | The GetDmaAdapterInfo routine retrieves information about the hardware capabilities of a system DMA channel. |
| [PGET_DMA_ALIGNMENT callback](nc-wdm-pget_dma_alignment.md) | The GetDmaAlignment routine returns the alignment requirements of the DMA system. |
| [PGET_DMA_TRANSFER_INFO callback](nc-wdm-pget_dma_transfer_info.md) | The GetDmaTransferInfo routine calculates the allocation requirements for a scatter/gather DMA transfer. |
| [PGET_SCATTER_GATHER_LIST callback](nc-wdm-pget_scatter_gather_list.md) | The GetScatterGatherList routine prepares the system for a DMA scatter/gather operation on behalf of the target device object, through either the system DMA controller or a bus-master adapter. |
| [PGET_SCATTER_GATHER_LIST_EX callback](nc-wdm-pget_scatter_gather_list_ex.md) | The GetScatterGatherListEx routine allocates the resources that are required for a DMA transfer, builds a scatter/gather list, and calls the driver-supplied AdapterListControl routine to initiate the DMA transfer. |
| [PINITIALIZE_DMA_TRANSFER_CONTEXT callback](nc-wdm-pinitialize_dma_transfer_context.md) | The InitializeDmaTransferContext routine initializes an opaque DMA transfer context that is used to track pending allocations of DMA resources. |
| [PINTERFACE_DEREFERENCE callback](nc-wdm-pinterface_dereference.md) | The InterfaceDereference routine decrements the reference count on a driver-defined interface. |
| [PINTERFACE_REFERENCE callback](nc-wdm-pinterface_reference.md) | The InterfaceReference routine increments the reference count on a driver-defined interface. |
| [PMAP_TRANSFER callback](nc-wdm-pmap_transfer.md) | The MapTransfer routine sets up map registers for an adapter object to map a DMA transfer from a locked-down buffer. |
| [PMAP_TRANSFER_EX callback](nc-wdm-pmap_transfer_ex.md) | The MapTransferEx routine sets up map registers to map the physical addresses in a scatter/gather list to the logical addresses that are required to do a DMA transfer. |
| [POB_POST_OPERATION_CALLBACK callback](nc-wdm-pob_post_operation_callback.md) | The ObjectPostCallback routine is called by the operating system after a process or thread handle operation occurs. |
| [POB_PRE_OPERATION_CALLBACK callback](nc-wdm-pob_pre_operation_callback.md) | The ObjectPreCallback routine is called by the operating system when a process or thread handle operation occurs. |
| [PO_FX_COMPONENT_ACTIVE_CONDITION_CALLBACK callback](nc-wdm-po_fx_component_active_condition_callback.md) | The ComponentActiveConditionCallback callback routine notifies the driver that the specified component completed a transition from the idle condition to the active condition. |
| [PO_FX_COMPONENT_CRITICAL_TRANSITION_CALLBACK callback](nc-wdm-po_fx_component_critical_transition_callback.md) | The ComponentCriticalTransitionCallback callback routine handles a transition of the specified component between the F0 (fully on) and low-power Fx component power states. |
| [PO_FX_COMPONENT_IDLE_CONDITION_CALLBACK callback](nc-wdm-po_fx_component_idle_condition_callback.md) | The ComponentIdleConditionCallback callback routine notifies the driver that the specified component completed a transition from the active condition to the idle condition. |
| [PO_FX_COMPONENT_IDLE_STATE_CALLBACK callback](nc-wdm-po_fx_component_idle_state_callback.md) | The ComponentIdleStateCallback callback routine notifies the driver of a pending change to the Fx power state of the specified component. |
| [PO_FX_COMPONENT_PERF_STATE_CALLBACK callback](nc-wdm-po_fx_component_perf_state_callback.md) | The ComponentPerfStateCallback callback routine notifies the driver that its request to change the performance state of a component is complete. |
| [PO_FX_DEVICE_POWER_NOT_REQUIRED_CALLBACK callback](nc-wdm-po_fx_device_power_not_required_callback.md) | The DevicePowerNotRequiredCallback callback routine notifies the device driver that the device is not required to stay in the D0 power state. |
| [PO_FX_DEVICE_POWER_REQUIRED_CALLBACK callback](nc-wdm-po_fx_device_power_required_callback.md) | The DevicePowerRequiredCallback callback routine notifies the device driver that the device must enter and remain in the D0 power state. |
| [PO_FX_POWER_CONTROL_CALLBACK callback](nc-wdm-po_fx_power_control_callback.md) | The PowerControlCallback callback routine performs a power control operation that is requested by the power management framework (PoFx). |
| [PPUT_DMA_ADAPTER callback](nc-wdm-pput_dma_adapter.md) | The PutDmaAdapter routine frees a DMA_ADAPTER structure previously allocated by IoGetDmaAdapter. |
| [PPUT_SCATTER_GATHER_LIST callback](nc-wdm-pput_scatter_gather_list.md) | The PutScatterGatherList routine frees the previously allocated map registers and scatter/gather list used in scatter/gather DMA. |
| [PREAD_DMA_COUNTER callback](nc-wdm-pread_dma_counter.md) | The ReadDmaCounter routine returns the number of bytes remaining to be transferred during the current subordinate DMA operation. |
| [PREENUMERATE_SELF callback](nc-wdm-preenumerate_self.md) | A ReenumerateSelf routine requests that a bus driver reenumerate a child device. |
| [PROCESSOR_HALT_ROUTINE callback](nc-wdm-processor_halt_routine.md) | A Halt callback routine transitions the processor to an idle state. |
| [PTM_RM_NOTIFICATION callback](nc-wdm-ptm_rm_notification.md) | A resource manager's ResourceManagerNotification callback routine receives and handles transaction notifications. |
| [REQUEST_POWER_COMPLETE callback](nc-wdm-request_power_complete.md) | The PowerCompletion callback routine completes the processing of a power IRP. |
| [RTL_QUERY_REGISTRY_ROUTINE callback](nc-wdm-rtl_query_registry_routine.md) | The QueryRoutine routine provides information about a registry value that was requested in a preceding call to the RtlQueryRegistryValues routine. |
| [SET_D3COLD_SUPPORT callback](nc-wdm-set_d3cold_support.md) | The SetD3ColdSupport routine enables or disables transitions to the D3cold device power state. |
| [SET_VIRTUAL_DEVICE_DATA callback](nc-wdm-set_virtual_device_data.md) | The SetVirtualFunctionData routine writes data to the PCI Express (PCIe) configuration space of a virtual function (VF) on a device that supports the single root I/O virtualization (SR-IOV) interface. |
| [TRANSLATE_BUS_ADDRESS callback](nc-wdm-translate_bus_address.md) | The TranslateBusAddress routine translates addresses on the parent bus to logical addresses. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [BATTERY_REPORTING_SCALE structure](ns-wdm-battery_reporting_scale.md) | Battery miniclass drivers fill in this structure in response to certain BatteryMiniQueryInformation requests. |
| [CM_Power_Data_s structure](ns-wdm-cm_power_data_s.md) | The CM_POWER_DATA structure contains information about a device's power management state and capabilities. |
| [PCI_X_CAPABILITY structure](ns-wdm-pci_x_capability.md) | The PCI_X_CAPABILITY structure reports the contents of the command and status registers of a device that is compliant with the PCI-X Addendum to the PCI Local Bus Specification. |
| [_ACCESS_STATE structure](ns-wdm-_access_state.md) | The ACCESS_STATE structure describes the state of an access in progress. |
| [_ACL structure](ns-wdm-_acl.md) | The ACL structure is the header of an access-control list (ACL). A complete ACL consists of an ACL structure followed by an ordered list of zero or more access-control entries (ACE). |
| [_BOOTDISK_INFORMATION structure](ns-wdm-_bootdisk_information.md) | The BOOTDISK_INFORMATION structure contains basic information describing the boot and system disks. |
| [_BOOTDISK_INFORMATION_EX structure](ns-wdm-_bootdisk_information_ex.md) | The BOOTDISK_INFORMATION_EX structure contains extended information describing the boot and system disks. |
| [_BUS_INTERFACE_STANDARD structure](ns-wdm-_bus_interface_standard.md) | The BUS_INTERFACE_STANDARD interface structure enables device drivers to make direct calls to parent bus driver routines. This structure defines the GUID_BUS_INTERFACE_STANDARD interface. |
| [_CLFS_LOG_NAME_INFORMATION structure](ns-wdm-_clfs_log_name_information.md) | The CLFS_LOG_NAME_INFORMATION structure holds the name of a Common Log File System (CLFS) stream or log. |
| [_CLFS_MGMT_CLIENT_REGISTRATION structure](ns-wdm-_clfs_mgmt_client_registration.md) | The CLFS_MGMT_CLIENT_REGISTRATION structure is given to CLFS management by clients who manage their own logs. |
| [_CLFS_MGMT_POLICY structure](ns-wdm-_clfs_mgmt_policy.md) | The CLFS_MGMT_POLICY structure holds a description of a policy for managing a CLFS log. |
| [_CLFS_STREAM_ID_INFORMATION structure](ns-wdm-_clfs_stream_id_information.md) | The CLFS_STREAM_ID_INFORMATION structure holds a value that identifies a stream in a Common Log File System (CLFS) log. |
| [_CLS_CONTAINER_INFORMATION structure](ns-wdm-_cls_container_information.md) | The CLFS_CONTAINER_INFORMATION structure holds descriptive information for an individual container in a Common Log File System (CLFS) log. |
| [_CLS_INFORMATION structure](ns-wdm-_cls_information.md) | The CLFS_INFORMATION structure holds metadata and state information for a Common Log File System (CLFS) stream and/or its underlying physical log. |
| [_CLS_IO_STATISTICS structure](ns-wdm-_cls_io_statistics.md) | The CLFS_IO_STATISTICS structure holds I/O statistics data for a Common Log File System (CLFS) log. |
| [_CLS_IO_STATISTICS_HEADER structure](ns-wdm-_cls_io_statistics_header.md) | The CLFS_IO_STATISTICS_HEADER structure holds the header portion of a CLFS_IO_STATISTICS structure. |
| [_CLS_LSN structure](ns-wdm-_cls_lsn.md) | The CLFS_LSN structure identifies an individual record in a Common Log File System (CLFS) stream. |
| [_CLS_SCAN_CONTEXT structure](ns-wdm-_cls_scan_context.md) | The CLFS_SCAN_CONTEXT structure holds context information to support a scan of the containers in a Common Log File System (CLFS) log. |
| [_CLS_WRITE_ENTRY structure](ns-wdm-_cls_write_entry.md) | The CLFS_WRITE_ENTRY structure holds the address and size of a buffer that contains one unit of data to be written to a Common Log File System (CLFS) stream. |
| [_CM_EISA_FUNCTION_INFORMATION structure](ns-wdm-_cm_eisa_function_information.md) | The CM_EISA_FUNCTION_INFORMATION structure defines detailed EISA configuration information returned by HalGetBusData for the input BusDataType EisaConfiguration, or by HalGetBusDataByOffset for the input BusDataType EisaConfiguration and the Offset zero, assuming the caller-allocated Buffer is of sufficient Length. |
| [_CM_EISA_SLOT_INFORMATION structure](ns-wdm-_cm_eisa_slot_information.md) | The CM_EISA_SLOT_INFORMATION structure defines EISA configuration header information returned by HalGetBusData for the input BusDataType = EisaConfiguration, or by HalGetBusDataByOffset for the inputs BusDataType = EisaConfiguration and Offset = 0, assuming the caller-allocated Buffer is of sufficient Length. |
| [_CM_FLOPPY_DEVICE_DATA structure](ns-wdm-_cm_floppy_device_data.md) | The CM_FLOPPY_DEVICE_DATA structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a floppy controller if the system can collect this information during the boot process. |
| [_CM_FULL_RESOURCE_DESCRIPTOR structure](ns-wdm-_cm_full_resource_descriptor.md) | The CM_FULL_RESOURCE_DESCRIPTOR structure specifies a set of system hardware resources of various types, assigned to a device that is connected to a specific bus. This structure is contained within a CM_RESOURCE_LIST structure. |
| [_CM_INT13_DRIVE_PARAMETER structure](ns-wdm-_cm_int13_drive_parameter.md) | The CM_INT13_DRIVE_PARAMETER structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a disk controller if the system can collect this information during the boot process. |
| [_CM_KEYBOARD_DEVICE_DATA structure](ns-wdm-_cm_keyboard_device_data.md) | The CM_KEYBOARD_DEVICE_DATA structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a keyboard peripheral if the system can collect this information during the boot process. |
| [_CM_MCA_POS_DATA structure](ns-wdm-_cm_mca_pos_data.md) | The CM_MCA_POS_DATA structure is obsolete. It defines IBM-compatible MCA POS configuration information for a slot. |
| [_CM_PARTIAL_RESOURCE_DESCRIPTOR structure](ns-wdm-_cm_partial_resource_descriptor.md) | The CM_PARTIAL_RESOURCE_DESCRIPTOR structure specifies one or more system hardware resources, of a single type, assigned to a device. |
| [_CM_PARTIAL_RESOURCE_LIST structure](ns-wdm-_cm_partial_resource_list.md) | The CM_PARTIAL_RESOURCE_LIST structure specifies a set of system hardware resources, of various types, assigned to a device. This structure is contained within a CM_FULL_RESOURCE_DESCRIPTOR structure. |
| [_CM_RESOURCE_LIST structure](ns-wdm-_cm_resource_list.md) | The CM_RESOURCE_LIST structure specifies all of the system hardware resources assigned to a device. |
| [_CM_SCSI_DEVICE_DATA structure](ns-wdm-_cm_scsi_device_data.md) | The CM_SCSI_DEVICE_DATA structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a SCSI HBA if the system can collect this information during the boot process. |
| [_CM_SERIAL_DEVICE_DATA structure](ns-wdm-_cm_serial_device_data.md) | The CM_SERIAL_DEVICE_DATA structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a serial controller if the system can collect this information during the boot process. |
| [_COUNTED_REASON_CONTEXT structure](ns-wdm-_counted_reason_context.md) | The COUNTED_REASON_CONTEXT structure contains one or more strings that give reasons for a power request. |
| [_D3COLD_SUPPORT_INTERFACE structure](ns-wdm-_d3cold_support_interface.md) | The D3COLD_SUPPORT_INTERFACE interface structure contains pointers to the routines in the GUID_D3COLD_SUPPORT_INTERFACE driver interface. |
| [_DEVICE_CAPABILITIES structure](ns-wdm-_device_capabilities.md) | A DEVICE_CAPABILITIES structure describes PnP and power capabilities of a device. This structure is returned in response to an IRP_MN_QUERY_CAPABILITIES IRP. |
| [_DEVICE_DESCRIPTION structure](ns-wdm-_device_description.md) | The DEVICE_DESCRIPTION structure describes the attributes of the physical device for which a driver is requesting a DMA adapter. |
| [_DEVICE_INTERFACE_CHANGE_NOTIFICATION structure](ns-wdm-_device_interface_change_notification.md) | The DEVICE_INTERFACE_CHANGE_NOTIFICATION structure describes a device interface that has been enabled (arrived) or disabled (removed). |
| [_DEVICE_OBJECT structure](ns-wdm-_device_object.md) | A device object represents a logical, virtual, or physical device for which a driver handles I/O requests. |
| [_DEVICE_RESET_INTERFACE_STANDARD structure](ns-wdm-_device_reset_interface_standard.md) | The DEVICE_RESET_INTERFACE_STANDARD structure enables function drivers to reset and recover malfunctioning devices. This structure describes the GUID_DEVICE_RESET_INTERFACE_STANDARD interface. |
| [_DMA_ADAPTER structure](ns-wdm-_dma_adapter.md) | The DMA_ADAPTER structure describes a system-defined interface to a DMA controller for a given device. A driver calls IoGetDmaAdapter to obtain this structure. |
| [_DMA_ADAPTER_INFO structure](ns-wdm-_dma_adapter_info.md) | The DMA_ADAPTER_INFO structure is a container for a DMA_ADAPTER_INFO_XXX structure that describes the capabilities of a system DMA controller. |
| [_DMA_ADAPTER_INFO_V1 structure](ns-wdm-_dma_adapter_info_v1.md) | The DMA_ADAPTER_INFO_V1 structure describes the capabilities of the system DMA controller that is represented by an adapter object. |
| [_DMA_OPERATIONS structure](ns-wdm-_dma_operations.md) | The DMA_OPERATIONS structure provides a table of pointers to functions that control the operation of a DMA controller. |
| [_DMA_TRANSFER_INFO structure](ns-wdm-_dma_transfer_info.md) | The DMA_TRANSFER_INFO structure is a container for a DMA_TRANSFER_INFO_XXX structure that describes the allocation requirements for a scatter/gather list. |
| [_DMA_TRANSFER_INFO_V1 structure](ns-wdm-_dma_transfer_info_v1.md) | The DMA_TRANSFER_INFO_V1 structure contains the allocation requirements for a scatter/gather list that describes the I/O data buffer for a DMA transfer. |
| [_DRIVER_OBJECT structure](ns-wdm-_driver_object.md) | Each driver object represents the image of a loaded kernel-mode driver. |
| [_ENLISTMENT_BASIC_INFORMATION structure](ns-wdm-_enlistment_basic_information.md) | The ENLISTMENT_BASIC_INFORMATION structure contains information about an enlistment object. |
| [_EXT_DELETE_PARAMETERS structure](ns-wdm-_ext_delete_parameters.md) | The EXT_DELETE_PARAMETERS structure contains an extended set of parameters for the ExDeleteTimer routine. |
| [_EXT_SET_PARAMETERS_V0 structure](ns-wdm-_ext_set_parameters_v0.md) | The EXT_SET_PARAMETERS structure contains an extended set of parameters for the ExSetTimer routine. |
| [_FAST_IO_DISPATCH structure](ns-wdm-_fast_io_dispatch.md) | Contains a set of callback routines that a file system driver or file system filter driver (legacy) provides for fast I/O processing. |
| [_FILE_BASIC_INFORMATION structure](ns-wdm-_file_basic_information.md) | The FILE_BASIC_INFORMATION structure is used as an argument to routines that query or set file information. |
| [_FILE_FS_DEVICE_INFORMATION structure](ns-wdm-_file_fs_device_information.md) | The FILE_FS_DEVICE_INFORMATION structure provides file system device information about the type of device object associated with a file object. |
| [_FILE_FULL_EA_INFORMATION structure](ns-wdm-_file_full_ea_information.md) | The FILE_FULL_EA_INFORMATION structure provides extended attribute (EA) information. This structure is used primarily by network drivers. |
| [_FILE_IO_PRIORITY_HINT_INFORMATION structure](ns-wdm-_file_io_priority_hint_information.md) | The FILE_IO_PRIORITY_HINT_INFORMATION structure is used by the ZwQueryInformationFile and ZwSetInformationFile routines to query and set the default IRP priority hint for requests on the specified file handle. |
| [_FILE_IS_REMOTE_DEVICE_INFORMATION structure](ns-wdm-_file_is_remote_device_information.md) | The FILE_IS_REMOTE_DEVICE_INFORMATION structure is used as an argument to the ZwQueryInformationFile routine. |
| [_FILE_MEMORY_PARTITION_INFORMATION structure](ns-wdm-_file_memory_partition_information.md) | Stores information about memory partition. This structure is used by the ZwSetInformationFile function. |
| [_FILE_NETWORK_OPEN_INFORMATION structure](ns-wdm-_file_network_open_information.md) | The FILE_NETWORK_OPEN_INFORMATION structure is used as an argument to ZwQueryInformationFile. |
| [_FILE_OBJECT structure](ns-wdm-_file_object.md) | The FILE_OBJECT structure is used by the system to represent a file object. |
| [_FILE_POSITION_INFORMATION structure](ns-wdm-_file_position_information.md) | The FILE_POSITION_INFORMATION structure is used as an argument to routines that query or set file information. |
| [_FILE_STANDARD_INFORMATION structure](ns-wdm-_file_standard_information.md) | The FILE_STANDARD_INFORMATION structure is used as an argument to routines that query or set file information. |
| [_FILE_STANDARD_INFORMATION_EX structure](ns-wdm-_file_standard_information_ex.md) | The FILE_STANDARD_INFORMATION_EX structure is used as an argument to routines that query or set file information. |
| [_FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS structure](ns-wdm-_function_level_device_reset_parameters.md) | The FUNCTION_LEVEL_DEVICE_RESET_PARAMETER structure is used as an argument to the DeviceReset routine of the GUID_DEVICE_RESET_INTERFACE_STANDARD interface. |
| [_GENERIC_MAPPING structure](ns-wdm-_generic_mapping.md) | The GENERIC_MAPPING structure describes the ACCESS_MASK value of specific access rights associated with each type of generic access right. |
| [_HWPROFILE_CHANGE_NOTIFICATION structure](ns-wdm-_hwprofile_change_notification.md) | The HWPROFILE_CHANGE_NOTIFICATION structure describes an event related to a hardware profile configuration change. |
| [_IMAGE_POLICY_ENTRY structure](ns-wdm-_image_policy_entry.md) | This structure is not supported. |
| [_IMAGE_POLICY_METADATA structure](ns-wdm-_image_policy_metadata.md) | This structure is not supported. |
| [_INTERFACE structure](ns-wdm-_interface.md) | The INTERFACE structure describes an interface that is exported by a driver for use by other drivers. |
| [_IO_CONNECT_INTERRUPT_PARAMETERS structure](ns-wdm-_io_connect_interrupt_parameters.md) | The IO_CONNECT_INTERRUPT_PARAMETERS structure contains the parameters that a driver supplies to the IoConnectInterruptEx routine to register an interrupt service routine (ISR). |
| [_IO_DISCONNECT_INTERRUPT_PARAMETERS structure](ns-wdm-_io_disconnect_interrupt_parameters.md) | The IO_DISCONNECT_INTERRUPT_PARAMETERS structure describes the parameters when unregistering an interrupt-handling routine with IoDisconnectInterruptEx. |
| [_IO_ERROR_LOG_PACKET structure](ns-wdm-_io_error_log_packet.md) | The IO_ERROR_LOG_PACKET structure serves as the header for an error log entry. |
| [_IO_INTERRUPT_MESSAGE_INFO structure](ns-wdm-_io_interrupt_message_info.md) | The IO_INTERRUPT_MESSAGE_INFO structure describes the driver's message-signaled interrupts. |
| [_IO_INTERRUPT_MESSAGE_INFO_ENTRY structure](ns-wdm-_io_interrupt_message_info_entry.md) | The IO_INTERRUPT_MESSAGE_INFO_ENTRY structure describes the properties of a single message-signaled interrupt. |
| [_IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS structure](ns-wdm-_io_report_interrupt_active_state_parameters.md) | The IO_REPORT_INTERRUPT_ACTIVE_STATE_PARAMETERS structure contains the connection context for a registered interrupt service routine (ISR) that was connected to an interrupt or interrupts by a previous call to the IoConnectInterruptEx routine. |
| [_IO_RESOURCE_DESCRIPTOR structure](ns-wdm-_io_resource_descriptor.md) | The IO_RESOURCE_DESCRIPTOR structure describes a range of raw hardware resources, of one type, that can be used by a device. An array of IO_RESOURCE_DESCRIPTOR structures is contained within each IO_RESOURCE_LIST structure. |
| [_IO_RESOURCE_LIST structure](ns-wdm-_io_resource_list.md) | The IO_RESOURCE_LIST structure describes a range of raw hardware resources, of various types, that can be used by a device. |
| [_IO_RESOURCE_REQUIREMENTS_LIST structure](ns-wdm-_io_resource_requirements_list.md) | The IO_RESOURCE_REQUIREMENTS_LIST structure describes sets of resource configurations that can be used by a device. Each configuration represents a range of raw resources, of various types, that can be used by a device. |
| [_IO_SECURITY_CONTEXT structure](ns-wdm-_io_security_context.md) | The IO_SECURITY_CONTEXT structure represents the security context of an IRP_MJ_CREATE request. |
| [_IO_SESSION_CONNECT_INFO structure](ns-wdm-_io_session_connect_info.md) | The IO_SESSION_CONNECT_INFO structure provides information about a user session. |
| [_IO_SESSION_STATE_INFORMATION structure](ns-wdm-_io_session_state_information.md) | The IO_SESSION_STATE_INFORMATION structure contains information about the state of a user session. |
| [_IO_SESSION_STATE_NOTIFICATION structure](ns-wdm-_io_session_state_notification.md) | The IO_SESSION_STATE_NOTIFICATION structure contains information that a kernel-mode driver supplies to the IoRegisterContainerNotification routine when the driver registers to receive notifications of session events. |
| [_IO_STACK_LOCATION structure](ns-wdm-_io_stack_location.md) | The IO_STACK_LOCATION structure defines an I/O stack location, which is an entry in the I/O stack that is associated with each IRP. |
| [_IO_STATUS_BLOCK structure](ns-wdm-_io_status_block.md) | A driver sets an IRP's I/O status block to indicate the final status of an I/O request, before calling IoCompleteRequest for the IRP. |
| [_IRP structure](ns-wdm-_irp.md) | The IRP structure is a partially opaque structure that represents an I/O request packet. Drivers can use the following members of the IRP structure. |
| [_KBUGCHECK_ADD_PAGES structure](ns-wdm-_kbugcheck_add_pages.md) | The KBUGCHECK_ADD_PAGES structure describes one or more pages of driver-supplied data to be written by a BugCheckAddPagesCallback callback routine to the crash dump file. |
| [_KBUGCHECK_DUMP_IO structure](ns-wdm-_kbugcheck_dump_io.md) | The KBUGCHECK_DUMP_IO structure describes an I/O operation on the crash dump file. |
| [_KBUGCHECK_SECONDARY_DUMP_DATA structure](ns-wdm-_kbugcheck_secondary_dump_data.md) | The KBUGCHECK_SECONDARY_DUMP_DATA structure describes a section of driver-supplied data to be written by BugCheckSecondaryDumpDataCallback to the crash dump file. |
| [_KDPC_WATCHDOG_INFORMATION structure](ns-wdm-_kdpc_watchdog_information.md) | The KDPC_WATCHDOG_INFORMATION structure holds time-out information about the current deferred procedure call (DPC). |
| [_KEY_BASIC_INFORMATION structure](ns-wdm-_key_basic_information.md) | The KEY_BASIC_INFORMATION structure defines a subset of the full information that is available for a registry key. |
| [_KEY_FULL_INFORMATION structure](ns-wdm-_key_full_information.md) | The KEY_FULL_INFORMATION structure defines the information available for a registry key, including information about its subkeys and the maximum length for their names and value entries. |
| [_KEY_NODE_INFORMATION structure](ns-wdm-_key_node_information.md) | The KEY_NODE_INFORMATION structure defines the basic information available for a registry (sub)key. |
| [_KEY_VALUE_BASIC_INFORMATION structure](ns-wdm-_key_value_basic_information.md) | The KEY_VALUE_BASIC_INFORMATION structure defines a subset of the full information available for a value entry of a registry key. |
| [_KEY_VALUE_ENTRY structure](ns-wdm-_key_value_entry.md) | The KEY_VALUE_ENTRY structure is used by the REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION structure to describe a single value entry for a registry key. |
| [_KEY_VALUE_FULL_INFORMATION structure](ns-wdm-_key_value_full_information.md) | The KEY_VALUE_FULL_INFORMATION structure defines information available for a value entry of a registry key. |
| [_KEY_VALUE_PARTIAL_INFORMATION structure](ns-wdm-_key_value_partial_information.md) | The KEY_VALUE_PARTIAL_INFORMATION structure defines a subset of the value information available for a value entry of a registry key. |
| [_KEY_WRITE_TIME_INFORMATION structure](ns-wdm-_key_write_time_information.md) | The KEY_WRITE_TIME_INFORMATION structure is used by the system to set the last write time for a registry key. |
| [_KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT structure](ns-wdm-_ke_processor_change_notify_context.md) | The KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT structure describes the notification context that is passed to a registered callback function when a new processor is dynamically added to a hardware partition. |
| [_KTMOBJECT_CURSOR structure](ns-wdm-_ktmobject_cursor.md) | The KTMOBJECT_CURSOR structure receives enumeration information about KTM objects when a component calls ZwEnumerateTransactionObject. |
| [_LINK_SHARE_ACCESS structure](ns-wdm-_link_share_access.md) | The share access structure used by file systems for only link files. |
| [_LUID_AND_ATTRIBUTES structure](ns-wdm-_luid_and_attributes.md) | LUID_AND_ATTRIBUTES represents a locally unique identifier (LUID) and its attributes. |
| [_MDL structure](ns-wdm-_mdl.md) | An MDL structure is a partially opaque structure that represents a memory descriptor list (MDL). |
| [_MM_PHYSICAL_ADDRESS_LIST structure](ns-wdm-_mm_physical_address_list.md) | The MM_PHYSICAL_ADDRESS_LIST structure specifies a range of physical addresses. |
| [_OB_CALLBACK_REGISTRATION structure](ns-wdm-_ob_callback_registration.md) | The OB_CALLBACK_REGISTRATION structure specifies the parameters when the ObRegisterCallbacks routine registers ObjectPreCallback and ObjectPostCallback callback routines. |
| [_OB_OPERATION_REGISTRATION structure](ns-wdm-_ob_operation_registration.md) | The OB_OPERATION_REGISTRATION structure specifies ObjectPreCallback and ObjectPostCallback callback routines and the types of operations that the routines are called for. |
| [_OB_POST_CREATE_HANDLE_INFORMATION structure](ns-wdm-_ob_post_create_handle_information.md) | The OB_POST_CREATE_HANDLE_INFORMATION structure provides information to a ObjectPostCallback routine about a thread or process handle that has been opened. |
| [_OB_POST_DUPLICATE_HANDLE_INFORMATION structure](ns-wdm-_ob_post_duplicate_handle_information.md) | The OB_POST_DUPLICATE_HANDLE_INFORMATION structure provides information to an ObjectPostCallback routine about a thread or process handle that has been duplicated. |
| [_OB_POST_OPERATION_INFORMATION structure](ns-wdm-_ob_post_operation_information.md) | The OB_POST_OPERATION_INFORMATION structure provides information about a process or thread handle operation to an ObjectPostCallback routine. |
| [_OB_POST_OPERATION_PARAMETERS structure](ns-wdm-_ob_post_operation_parameters.md) | The OB_POST_OPERATION_PARAMETERS union describes the operation-specific parameters for an ObjectPostCallback routine. |
| [_OB_PRE_CREATE_HANDLE_INFORMATION structure](ns-wdm-_ob_pre_create_handle_information.md) | The OB_PRE_CREATE_HANDLE_INFORMATION structure provides information to an ObjectPreCallback routine about a thread or process handle that is being opened. |
| [_OB_PRE_DUPLICATE_HANDLE_INFORMATION structure](ns-wdm-_ob_pre_duplicate_handle_information.md) | The OB_PRE_DUPLICATE_HANDLE_INFORMATION structure provides information to an ObjectPreCallback routine about a thread or process handle that is being duplicated. |
| [_OB_PRE_OPERATION_INFORMATION structure](ns-wdm-_ob_pre_operation_information.md) | The OB_PRE_OPERATION_INFORMATION structure provides information about a process or thread handle operation to an ObjectPreCallback routine. |
| [_OB_PRE_OPERATION_PARAMETERS structure](ns-wdm-_ob_pre_operation_parameters.md) | The OB_PRE_OPERATION_PARAMETERS union describes the operation-specific parameters for an ObjectPreCallback routine. |
| [_OSVERSIONINFOEXW structure](ns-wdm-_osversioninfoexw.md) | The RTL_OSVERSIONINFOEXW structure contains operating system version information. |
| [_OSVERSIONINFOW structure](ns-wdm-_osversioninfow.md) | The RTL_OSVERSIONINFOW structure contains operating system version information. |
| [_PCI_CAPABILITIES_HEADER structure](ns-wdm-_pci_capabilities_header.md) | The PCI_CAPABILITIES_HEADER structure defines a header that is present in every PCI capability structure. |
| [_PCI_COMMON_CONFIG structure](ns-wdm-_pci_common_config.md) | The PCI_COMMON_CONFIG structure is obsolete. |
| [_PCI_DEVICE_PRESENT_INTERFACE structure](ns-wdm-_pci_device_present_interface.md) | The PCI_DEVICE_PRESENT_INTERFACE structure is reserved for system use. |
| [_PCI_EXPRESS_AER_CAPABILITIES structure](ns-wdm-_pci_express_aer_capabilities.md) | The PCI_EXPRESS_AER_CAPABILITIES structure describes a PCI Express (PCIe) advanced error capabilities and control register of a PCIe advanced error reporting capability structure. |
| [_PCI_EXPRESS_AER_CAPABILITY structure](ns-wdm-_pci_express_aer_capability.md) | The PCI_EXPRESS_AER_CAPABILITY structure describes a PCI Express (PCIe) advanced error reporting capability structure. |
| [_PCI_EXPRESS_BRIDGE_AER_CAPABILITY structure](ns-wdm-_pci_express_bridge_aer_capability.md) | The PCI_EXPRESS_BRIDGE_AER_CAPABILITY structure describes a PCI Express (PCIe) advanced error reporting capability structure for a PCIe bridge device. |
| [_PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure](ns-wdm-_pci_express_correctable_error_mask.md) | The PCI_EXPRESS_CORRECTABLE_ERROR_MASK structure describes a PCI Express (PCIe) correctable error mask register of a PCIe advanced error reporting capability structure. |
| [_PCI_EXPRESS_CORRECTABLE_ERROR_STATUS structure](ns-wdm-_pci_express_correctable_error_status.md) | The PCI_EXPRESS_CORRECTABLE_ERROR_STATUS structure describes a PCI Express (PCIe) correctable error status register of a PCIe advanced error reporting capability structure. |
| [_PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER structure](ns-wdm-_pci_express_enhanced_capability_header.md) | The PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER structure describes the header for a PCI Express (PCIe) extended capability structure. |
| [_PCI_EXPRESS_ERROR_SOURCE_ID structure](ns-wdm-_pci_express_error_source_id.md) | The PCI_EXPRESS_ERROR_SOURCE_ID structure describes the identifiers of the first correctable error and the first uncorrectable error that are reported in the PCI Express (PCIe) root error status register. |
| [_PCI_EXPRESS_LINK_QUIESCENT_INTERFACE structure](ns-wdm-_pci_express_link_quiescent_interface.md) | The PCI_EXPRESS_LINK_QUIESCENT_INTERFACE structure is reserved for system use. |
| [_PCI_EXPRESS_ROOTPORT_AER_CAPABILITY structure](ns-wdm-_pci_express_rootport_aer_capability.md) | The PCI_EXPRESS_ROOTPORT_AER_CAPABILITY structure describes a PCI Express (PCIe) advanced error reporting capability structure for a root port or a root complex event collector. |
| [_PCI_EXPRESS_ROOT_ERROR_COMMAND structure](ns-wdm-_pci_express_root_error_command.md) | The PCI_EXPRESS_ROOT_ERROR_COMMAND structure describes a PCI Express (PCIe) root error command register of a PCIe advanced error reporting capability structure. |
| [_PCI_EXPRESS_ROOT_ERROR_STATUS structure](ns-wdm-_pci_express_root_error_status.md) | The PCI_EXPRESS_ROOT_ERROR_STATUS structure describes a PCI Express (PCIe) root error status register of a PCIe advanced error reporting capability structure. |
| [_PCI_EXPRESS_ROOT_PORT_INTERFACE structure](ns-wdm-_pci_express_root_port_interface.md) | The PCI_EXPRESS_ROOT_PORT_INTERFACE structure is reserved for system use. |
| [_PCI_EXPRESS_SEC_AER_CAPABILITIES structure](ns-wdm-_pci_express_sec_aer_capabilities.md) | The PCI_EXPRESS_SEC_AER_CAPABILITIES structure describes a PCI Express (PCIe) secondary error capabilities and control register of a PCIe advanced error reporting capability structure. |
| [_PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK structure](ns-wdm-_pci_express_sec_uncorrectable_error_mask.md) | The PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_MASK structure describes a PCI Express (PCIe) secondary uncorrectable error mask register of a PCIe advanced error reporting capability structure. |
| [_PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY structure](ns-wdm-_pci_express_sec_uncorrectable_error_severity.md) | The PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_SEVERITY structure describes a PCI Express (PCIe) secondary uncorrectable error severity register of a PCIe advanced error reporting capability structure. |
| [_PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS structure](ns-wdm-_pci_express_sec_uncorrectable_error_status.md) | The PCI_EXPRESS_SEC_UNCORRECTABLE_ERROR_STATUS structure describes a PCI Express (PCIe) secondary uncorrectable error status register of a PCIe advanced error reporting capability structure. |
| [_PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY structure](ns-wdm-_pci_express_serial_number_capability.md) | The PCI_EXPRESS_SERIAL_NUMBER_CAPABILITY structure describes a serial number for a PCI Express (PCIe) device. |
| [_PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK structure](ns-wdm-_pci_express_uncorrectable_error_mask.md) | The PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK structure describes a PCI Express (PCIe) uncorrectable error mask register of a PCIe advanced error reporting capability structure. |
| [_PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY structure](ns-wdm-_pci_express_uncorrectable_error_severity.md) | The PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY structure describes a PCI Express (PCIe) uncorrectable error severity register of a PCIe advanced error reporting capability structure. |
| [_PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS structure](ns-wdm-_pci_express_uncorrectable_error_status.md) | The PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS structure describes a PCI Express (PCIe) uncorrectable error status register of a PCIe advanced error reporting capability structure. |
| [_PCI_MSIX_TABLE_CONFIG_INTERFACE structure](ns-wdm-_pci_msix_table_config_interface.md) | The PCI_MSIX_TABLE_CONFIG_INTERFACE structure enables device drivers to modify their MSI-X interrupt settings. This structure describes the GUID_MSIX_TABLE_CONFIG_INTERFACE interface. |
| [_PCI_PMC structure](ns-wdm-_pci_pmc.md) | The PCI_PMC structure is used to report the contents of the power management capabilities register. |
| [_PCI_PMCSR structure](ns-wdm-_pci_pmcsr.md) | The PCI_PMCSR structure is used to report the contents of the device's power management control status register. |
| [_PCI_PMCSR_BSE structure](ns-wdm-_pci_pmcsr_bse.md) | The PCI_PMCSR_BSE structure is used to report the contents of the power management control status register for PCI bridge support extensions. |
| [_PCI_PM_CAPABILITY structure](ns-wdm-_pci_pm_capability.md) | The PCI_PM_CAPABILITY structure reports the power management capabilities of the device. |
| [_PCI_SLOT_NUMBER structure](ns-wdm-_pci_slot_number.md) | The PCI_SLOT_NUMBER structure is obsolete. |
| [_PCW_CALLBACK_INFORMATION structure](ns-wdm-_pcw_callback_information.md) | The PCW_CALLBACK_INFORMATION union supplies details about the notification to send. A provider passes a pointer to this union as a parameter to the PcwCallback function. |
| [_PCW_COUNTER_DESCRIPTOR structure](ns-wdm-_pcw_counter_descriptor.md) | The PCW_COUNTER_DESCRIPTOR structure supplies details about the notification to send. |
| [_PCW_COUNTER_INFORMATION structure](ns-wdm-_pcw_counter_information.md) | The PCW_COUNTER_INFORMATION structure describes attributes that identify a specific instance of a counter set. |
| [_PCW_DATA structure](ns-wdm-_pcw_data.md) | The PCW_DATA structure describes the array of data blocks that are associated with an instance. |
| [_PCW_MASK_INFORMATION structure](ns-wdm-_pcw_mask_information.md) | The PCW_MASK_INFORMATION structure supplies details about the notification to send to the provider. This information is passed as part of the Info parameter to the PcwCallback function. This mask information is included in PCW_CALLBACK_INFORMATION. |
| [_PCW_REGISTRATION_INFORMATION structure](ns-wdm-_pcw_registration_information.md) | The PCW_REGISTRATION_INFORMATION structure supplies details about the provider and the counter set. |
| [_PLUGPLAY_NOTIFICATION_HEADER structure](ns-wdm-_plugplay_notification_header.md) | A PLUGPLAY_NOTIFICATION_HEADER structure is included at the beginning of each PnP notification structure, such as a DEVICE_INTERFACE_CHANGE_NOTIFICATION structure. |
| [_PNP_BUS_INFORMATION structure](ns-wdm-_pnp_bus_information.md) | The PNP_BUS_INFORMATION structure describes a bus. |
| [_POWER_PLATFORM_INFORMATION structure](ns-wdm-_power_platform_information.md) | The POWER_PLATFORM_INFORMATION structure contains information about the power capabilities of the system. |
| [_POWER_STATE structure](ns-wdm-_power_state.md) | The POWER_STATE union specifies a system power state value or a device power state value. |
| [_PO_FX_COMPONENT_IDLE_STATE structure](ns-wdm-_po_fx_component_idle_state.md) | The PO_FX_COMPONENT_IDLE_STATE structure specifies the attributes of an Fx power state of a component in a device. |
| [_PO_FX_COMPONENT_PERF_INFO structure](ns-wdm-_po_fx_component_perf_info.md) | The PO_FX_COMPONENT_PERF_INFO structure describes all the sets of performance states for a single component within a device. |
| [_PO_FX_COMPONENT_PERF_SET structure](ns-wdm-_po_fx_component_perf_set.md) | The PO_FX_COMPONENT_PERF_SET structure represents a set of performance states for a single component within a device. |
| [_PO_FX_COMPONENT_V1 structure](ns-wdm-_po_fx_component_v1.md) | The PO_FX_COMPONENT structure describes the power state attributes of a component in a device. |
| [_PO_FX_COMPONENT_V2 structure](ns-wdm-_po_fx_component_v2.md) | The PO_FX_COMPONENT structure describes the power state attributes of a component in a device. |
| [_PO_FX_DEVICE_V1 structure](ns-wdm-_po_fx_device_v1.md) | The PO_FX_DEVICE structure describes the power attributes of a device to the power management framework (PoFx). |
| [_PO_FX_DEVICE_V2 structure](ns-wdm-_po_fx_device_v2.md) | The PO_FX_DEVICE structure describes the power attributes of a device to the power management framework (PoFx). |
| [_PO_FX_PERF_STATE structure](ns-wdm-_po_fx_perf_state.md) | The PO_FX_PERF_STATE structure represents a performance state for a single component within a device. |
| [_PO_FX_PERF_STATE_CHANGE structure](ns-wdm-_po_fx_perf_state_change.md) | The PO_FX_PERF_STATE_CHANGE structure contains information about a change to a performance state that is being requested by calling the PoFxIssueComponentPerfStateChange or PoFxIssueComponentPerfStateChangeMultiple routine. |
| [_PRIVILEGE_SET structure](ns-wdm-_privilege_set.md) | The PRIVILEGE_SET structure specifies a set of security privileges. For more information, see the reference page for PRIVILEGE_SET in the Microsoft Windows SDK documentation. |
| [_REENUMERATE_SELF_INTERFACE_STANDARD structure](ns-wdm-_reenumerate_self_interface_standard.md) | The REENUMERATE_SELF_INTERFACE_STANDARD interface structure enables a driver to request that its parent bus driver reenumerate the driver's device. This structure defines the GUID_REENUMERATE_SELF_INTERFACE_STANDARD interface. |
| [_REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION structure](ns-wdm-_reg_callback_context_cleanup_information.md) | The REG_CALLBACK_CONTEXT_CLEANUP_INFORMATION structure contains information that a driver's RegistryCallback routine can use to free resources that the driver previously allocated for the context that is associated with a registry object. |
| [_REG_CREATE_KEY_INFORMATION structure](ns-wdm-_reg_create_key_information.md) | The REG_CREATE_KEY_INFORMATION structure contains information that a driver's RegistryCallback routine can use when a registry key that is being created. |
| [_REG_CREATE_KEY_INFORMATION_V1 structure](ns-wdm-_reg_create_key_information_v1.md) | The REG_CREATE_KEY_INFORMATION_V1 structure contains information that a filter driver's RegistryCallback routine can use when a registry key is being created. |
| [_REG_DELETE_KEY_INFORMATION structure](ns-wdm-_reg_delete_key_information.md) | The REG_DELETE_KEY_INFORMATION structure contains information that a driver's RegistryCallback routine can use when a registry key is being deleted. |
| [_REG_DELETE_VALUE_KEY_INFORMATION structure](ns-wdm-_reg_delete_value_key_information.md) | The REG_DELETE_VALUE_KEY_INFORMATION structure contains information that a driver's RegistryCallback routine can use when a registry key's value is being deleted. |
| [_REG_ENUMERATE_KEY_INFORMATION structure](ns-wdm-_reg_enumerate_key_information.md) | The REG_ENUMERATE_KEY_INFORMATION structure describes one subkey of a key whose subkeys are being enumerated. |
| [_REG_ENUMERATE_VALUE_KEY_INFORMATION structure](ns-wdm-_reg_enumerate_value_key_information.md) | The REG_ENUMERATE_VALUE_KEY_INFORMATION structure describes one value entry of a key whose value entries are being enumerated. |
| [_REG_KEY_HANDLE_CLOSE_INFORMATION structure](ns-wdm-_reg_key_handle_close_information.md) | The REG_KEY_HANDLE_CLOSE_INFORMATION structure contains information about a registry key whose handle is about to be closed. |
| [_REG_LOAD_KEY_INFORMATION structure](ns-wdm-_reg_load_key_information.md) | The REG_LOAD_KEY_INFORMATION structure contains information about a registry hive that is being loaded. |
| [_REG_POST_CREATE_KEY_INFORMATION structure](ns-wdm-_reg_post_create_key_information.md) | The REG_POST_CREATE_KEY_INFORMATION structure contains the result of an attempt to create a registry key. |
| [_REG_POST_OPERATION_INFORMATION structure](ns-wdm-_reg_post_operation_information.md) | The REG_POST_OPERATION_INFORMATION structure contains information about a completed registry operation that a RegistryCallback routine can use. |
| [_REG_PRE_CREATE_KEY_INFORMATION structure](ns-wdm-_reg_pre_create_key_information.md) | The REG_PRE_OPEN_KEY_INFORMATION structure contains the name of a registry key that is about to be opened. |
| [_REG_QUERY_KEY_INFORMATION structure](ns-wdm-_reg_query_key_information.md) | The REG_QUERY_KEY_INFORMATION structure describes the metadata that is about to be queried for a key. |
| [_REG_QUERY_KEY_NAME structure](ns-wdm-_reg_query_key_name.md) | The REG_QUERY_KEY_NAME structure describes the full registry key name of an object being queried. |
| [_REG_QUERY_KEY_SECURITY_INFORMATION structure](ns-wdm-_reg_query_key_security_information.md) | The REG_QUERY_KEY_SECURITY_INFORMATION structure receives security information for a registry key object. |
| [_REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION structure](ns-wdm-_reg_query_multiple_value_key_information.md) | The REG_QUERY_MULTIPLE_VALUE_KEY_INFORMATION structure describes the multiple value entries that are being retrieved for a key. |
| [_REG_QUERY_VALUE_KEY_INFORMATION structure](ns-wdm-_reg_query_value_key_information.md) | The REG_QUERY_VALUE_KEY_INFORMATION structure contains information about a registry key's value entry that is being queried. |
| [_REG_RENAME_KEY_INFORMATION structure](ns-wdm-_reg_rename_key_information.md) | The REG_RENAME_KEY_INFORMATION structure contains the new name for a registry key whose name is about to be changed. |
| [_REG_REPLACE_KEY_INFORMATION structure](ns-wdm-_reg_replace_key_information.md) | The REG_REPLACE_KEY_INFORMATION structure describes the metadata that is about to be replaced for a key. |
| [_REG_RESTORE_KEY_INFORMATION structure](ns-wdm-_reg_restore_key_information.md) | The REG_RESTORE_KEY_INFORMATION structure contains the information for a registry key that is about to be restored. |
| [_REG_SAVE_KEY_INFORMATION structure](ns-wdm-_reg_save_key_information.md) | The REG_SAVE_KEY_INFORMATION structure contains the information for a registry key that is about to be saved. |
| [_REG_SET_INFORMATION_KEY_INFORMATION structure](ns-wdm-_reg_set_information_key_information.md) | The REG_SET_INFORMATION_KEY_INFORMATION structure describes a new setting for a key's metadata. |
| [_REG_SET_KEY_SECURITY_INFORMATION structure](ns-wdm-_reg_set_key_security_information.md) | The REG_SET_KEY_SECURITY_INFORMATION structure specifies security information for a registry key object. |
| [_REG_SET_VALUE_KEY_INFORMATION structure](ns-wdm-_reg_set_value_key_information.md) | The REG_SET_VALUE_INFORMATION structure describes a new setting for a registry key's value entry. |
| [_REG_UNLOAD_KEY_INFORMATION structure](ns-wdm-_reg_unload_key_information.md) | The REG_UNLOAD_KEY_INFORMATION structure contains information that a driver's RegistryCallback routine can use when a registry hive is unloaded. |
| [_RESOURCEMANAGER_BASIC_INFORMATION structure](ns-wdm-_resourcemanager_basic_information.md) | The RESOURCEMANAGER_BASIC INFORMATION structure contains information about a resource manager object. |
| [_RESOURCEMANAGER_COMPLETION_INFORMATION structure](ns-wdm-_resourcemanager_completion_information.md) | The RESOURCEMANAGER_COMPLETION_INFORMATION structure is not used. |
| [_SCATTER_GATHER_LIST structure](ns-wdm-_scatter_gather_list.md) | The SCATTER_GATHER_LIST structure describes the scatter/gather list for a DMA operation. |
| [_SDEV_IDENTIFIER_INTERFACE structure](ns-wdm-_sdev_identifier_interface.md) | This material is not yet available. This placeholder topic is provided as an example of documentation that may be included in a later release. |
| [_SECTION_OBJECT_POINTERS structure](ns-wdm-_section_object_pointers.md) | The SECTION_OBJECT_POINTERS structure, allocated by a file system or a redirector driver, is used by the memory manager and cache manager to store file-mapping and cache-related information for a file stream. |
| [_SECURITY_SUBJECT_CONTEXT structure](ns-wdm-_security_subject_context.md) | The SECURITY_SUBJECT_CONTEXT structure is used to capture subject security context for access validation and auditing. |
| [_SLIST_ENTRY structure](ns-wdm-_slist_entry.md) | An SLIST_ENTRY structure describes an entry in a sequenced singly linked list. |
| [_SYSTEM_POWER_STATE_CONTEXT structure](ns-wdm-_system_power_state_context.md) | The SYSTEM_POWER_STATE_CONTEXT structure is a partially opaque system structure that contains information about the previous system power states of a computer. |
| [_TARGET_DEVICE_CUSTOM_NOTIFICATION structure](ns-wdm-_target_device_custom_notification.md) | The TARGET_DEVICE_CUSTOM_NOTIFICATION structure describes a custom device event. |
| [_TARGET_DEVICE_REMOVAL_NOTIFICATION structure](ns-wdm-_target_device_removal_notification.md) | The TARGET_DEVICE_REMOVAL_NOTIFICATION structure describes a device-removal event. The PnP manager sends this structure to a driver that registered a callback routine for notification of EventCategoryTargetDeviceChange events. |
| [_TRANSACTIONMANAGER_BASIC_INFORMATION structure](ns-wdm-_transactionmanager_basic_information.md) | The TRANSACTIONMANAGER_BASIC_INFORMATION structure contains information about a transaction manager object. |
| [_TRANSACTIONMANAGER_LOGPATH_INFORMATION structure](ns-wdm-_transactionmanager_logpath_information.md) | The TRANSACTIONMANAGER_LOGPATH_INFORMATION structure contains information about a transaction manager object. |
| [_TRANSACTIONMANAGER_LOG_INFORMATION structure](ns-wdm-_transactionmanager_log_information.md) | The TRANSACTIONMANAGER_LOG_INFORMATION structure contains information about a transaction manager object. |
| [_TRANSACTIONMANAGER_RECOVERY_INFORMATION structure](ns-wdm-_transactionmanager_recovery_information.md) | The TRANSACTIONMANAGER_RECOVERY_INFORMATION structure contains information about a transaction manager object. |
| [_TRANSACTION_BASIC_INFORMATION structure](ns-wdm-_transaction_basic_information.md) | The TRANSACTION_BASIC_INFORMATION structure contains information about a transaction object. |
| [_TRANSACTION_ENLISTMENTS_INFORMATION structure](ns-wdm-_transaction_enlistments_information.md) | The TRANSACTION_ENLISTMENTS_INFORMATION structure contains information about the enlistments that are associated with a transaction object. |
| [_TRANSACTION_ENLISTMENT_PAIR structure](ns-wdm-_transaction_enlistment_pair.md) | The TRANSACTION_ENLISTMENT_PAIR structure contains information about an enlistment that is associated with a transaction object. |
| [_TRANSACTION_PROPERTIES_INFORMATION structure](ns-wdm-_transaction_properties_information.md) | The TRANSACTION_PROPERTIES_INFORMATION structure contains a transaction object's properties. |
| [_VPB structure](ns-wdm-_vpb.md) | The volume parameter block (VPB) structure is used to map a device object that represents a mounted file system volume to a device object that represents a physical or virtual disk device. |
| [_WORK_QUEUE_ITEM structure](ns-wdm-_work_queue_item.md) | The WORK_QUEUE_ITEM structure is used to post a work items to a system work queue. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [*PPOWER_ACTION enumeration](ne-wdm-ppower_action.md) | The POWER_ACTION enumeration identifies the system power actions that can occur on a computer. |
| [DEVICE_REGISTRY_PROPERTY enumeration](ne-wdm-device_registry_property.md) | The DEVICE_REGISTRY_PROPERTY enumeration identifies device properties that are stored in the registry. |
| [DMA_COMPLETION_STATUS enumeration](ne-wdm-dma_completion_status.md) | The DMA_COMPLETION_STATUS enumeration describes the completion status of a DMA transfer. |
| [POWER_INFORMATION_LEVEL enumeration](ne-wdm-power_information_level.md) | Indicates power level information. |
| [_BOUND_CALLBACK_STATUS enumeration](ne-wdm-_bound_callback_status.md) | The BOUND_CALLBACK_STATUS enumeration indicates how a user-mode bounds exception was processed by the BoundCallback function. |
| [_CLFS_CONTEXT_MODE enumeration](ne-wdm-_clfs_context_mode.md) | The CLFS_CONTEXT_MODE enumeration indicates the type of sequence that the Common Log File System (CLFS) driver follows when it reads a set of records from a stream. |
| [_CLFS_MGMT_POLICY_TYPE enumeration](ne-wdm-_clfs_mgmt_policy_type.md) | The CLFS_MGMT_POLICY_TYPE enumeration type identifies the type of a CLFS management policy. |
| [_CLS_LOG_INFORMATION_CLASS enumeration](ne-wdm-_cls_log_information_class.md) | The CLFS_LOG_INFORMATION_CLASS enumeration indicates the type of information that is requested by a call to ClfsQueryLogFileInformation. |
| [_D3COLD_LAST_TRANSITION_STATUS enumeration](ne-wdm-_d3cold_last_transition_status.md) | The D3COLD_LAST_TRANSITION_STATUS enumeration indicates whether the most recent transition to the D3hot device power state was followed by a transition to the D3cold device power state. |
| [_DEVICE_INSTALL_STATE enumeration](ne-wdm-_device_install_state.md) | The DEVICE_INSTALL_STATE enumeration describes a device's installation state. |
| [_DEVICE_POWER_STATE enumeration](ne-wdm-_device_power_state.md) | The DEVICE_POWER_STATE enumeration type indicates a device power state. |
| [_DEVICE_REMOVAL_POLICY enumeration](ne-wdm-_device_removal_policy.md) | The DEVICE_REMOVAL_POLICY enumeration describes a device's removal policy. |
| [_DEVICE_RESET_TYPE enumeration](ne-wdm-_device_reset_type.md) | The DEVICE_RESET_TYPE enumeration specifies the type of device reset that is being requested by a call to the DeviceReset routine of the GUID_DEVICE_RESET_INTERFACE_STANDARD interface. |
| [_DEVICE_WAKE_DEPTH enumeration](ne-wdm-_device_wake_depth.md) | The DEVICE_WAKE_DEPTH enumeration specifies the deepest device power state from which a device can trigger a wake signal. |
| [_DIRECTORY_NOTIFY_INFORMATION_CLASS enumeration](ne-wdm-_directory_notify_information_class.md) | A value that specifies which structure to use to query or set information for a files in a directory. |
| [_ENLISTMENT_INFORMATION_CLASS enumeration](ne-wdm-_enlistment_information_class.md) | The ENLISTMENT_INFORMATION_CLASS enumeration identifies the type of information that the ZwSetInformationEnlistment routine can set and that the ZwQueryInformationEnlistment routine can retrieve for an enlistment object. |
| [_FILE_INFORMATION_CLASS enumeration](ne-wdm-_file_information_class.md) | A value that specifies which structure to use to query or set information for a file object. |
| [_FSINFOCLASS enumeration](ne-wdm-_fsinfoclass.md) | The FS_INFORMATION_CLASS enumeration contains the information class constants that specify what type of information structure is present for a set or a query operation. |
| [_IMAGE_POLICY_ENTRY_TYPE enumeration](ne-wdm-_image_policy_entry_type.md) | This enumeration is not supported. |
| [_IMAGE_POLICY_ID enumeration](ne-wdm-_image_policy_id.md) | This enumeration is not supported. |
| [_INTERFACE_TYPE enumeration](ne-wdm-_interface_type.md) | The INTERFACE_TYPE enumeration indicates the bus type. |
| [_IO_ACCESS_MODE enumeration](ne-wdm-_io_access_mode.md) | Defines the types of access mode for Scheduled File I/O (SFIO). |
| [_IO_ACCESS_TYPE enumeration](ne-wdm-_io_access_type.md) | Defines the access rights for Scheduled File I/O (SFIO). |
| [_IO_ALLOCATION_ACTION enumeration](ne-wdm-_io_allocation_action.md) | The IO_ALLOCATION_ACTION enumerated type is used to specify return values for AdapterControl and ControllerControl routines. |
| [_IO_CONTAINER_INFORMATION_CLASS enumeration](ne-wdm-_io_container_information_class.md) | The IO_CONTAINER_INFORMATION_CLASS enumeration contains constants that indicate the classes of system information that a kernel-mode driver can request. |
| [_IO_CONTAINER_NOTIFICATION_CLASS enumeration](ne-wdm-_io_container_notification_class.md) | The IO_CONTAINER_NOTIFICATION_CLASS enumeration contains constants that indicate the classes of events for which a kernel-mode driver can register to receive notifications. |
| [_IO_PAGING_PRIORITY enumeration](ne-wdm-_io_paging_priority.md) | The IO_PAGING_PRIORITY enumeration describes the priority value for a paging I/O IRP. |
| [_IO_PRIORITY_HINT enumeration](ne-wdm-_io_priority_hint.md) | The IO_PRIORITY_HINT enumeration type specifies the priority hint for an IRP. |
| [_IO_SESSION_EVENT enumeration](ne-wdm-_io_session_event.md) | The IO_SESSION_EVENT enumeration indicates the type of session event for which a driver is receiving notification. |
| [_IO_SESSION_STATE enumeration](ne-wdm-_io_session_state.md) | The IO_SESSION_STATE enumeration contains constants that indicate the current state of a user session. |
| [_IRQ_DEVICE_POLICY enumeration](ne-wdm-_irq_device_policy.md) | The IRQ_DEVICE_POLICY enumeration type indicates the policy the operating system can use to assign the interrupts from a device to different processors. |
| [_IRQ_PRIORITY enumeration](ne-wdm-_irq_priority.md) | The IRQ_PRIORITY enumeration type indicates the priority the system should give to servicing a device's interrupts. |
| [_KBUGCHECK_CALLBACK_REASON enumeration](ne-wdm-_kbugcheck_callback_reason.md) | The KBUGCHECK_CALLBACK_REASON enumeration type specifies the situations in which a bug-check callback executes. |
| [_KBUGCHECK_DUMP_IO_TYPE enumeration](ne-wdm-_kbugcheck_dump_io_type.md) | The KBUGCHECK_DUMP_IO_TYPE enumeration type identifies the type of a section of data within a crash dump file. |
| [_KEY_INFORMATION_CLASS enumeration](ne-wdm-_key_information_class.md) | The KEY_INFORMATION_CLASS enumeration type represents the type of information to supply about a registry key. |
| [_KEY_SET_INFORMATION_CLASS enumeration](ne-wdm-_key_set_information_class.md) | The KEY_SET_INFORMATION_CLASS enumeration type represents the type of information to set for a registry key. |
| [_KEY_VALUE_INFORMATION_CLASS enumeration](ne-wdm-_key_value_information_class.md) | The KEY_VALUE_INFORMATION_CLASS enumeration type specifies the type of information to supply about the value of a registry key. |
| [_KINTERRUPT_MODE enumeration](ne-wdm-_kinterrupt_mode.md) | The KINTERRUPT_MODE enumeration type indicates whether an interrupt is level-triggered or edge-triggered. |
| [_KINTERRUPT_POLARITY enumeration](ne-wdm-_kinterrupt_polarity.md) | The KINTERRUPT_POLARITY enumeration indicates how a device signals an interrupt request on an interrupt line. |
| [_KTMOBJECT_TYPE enumeration](ne-wdm-_ktmobject_type.md) | The KTMOBJECT_TYPE enumeration identifies the types of objects that KTM supports. |
| [_LOCK_OPERATION enumeration](ne-wdm-_lock_operation.md) | The LOCK_OPERATION enumeration specifies the type of access that is appropriate for a type of I/O operation. |
| [_MEMORY_CACHING_TYPE enumeration](ne-wdm-_memory_caching_type.md) | The MEMORY_CACHING_TYPE enumeration type specifies the permitted caching behavior when allocating or mapping memory. |
| [_MONITOR_DISPLAY_STATE enumeration](ne-wdm-_monitor_display_state.md) | Indicates the power state of the monitor being displayed on. |
| [_PCW_CALLBACK_TYPE enumeration](ne-wdm-_pcw_callback_type.md) | The PCW_CALLBACK_TYPE enumeration defines the notification type to send to the registered provider of the counter set. A provider passes a pointer to this enumeration as a parameter to the PcwCallback function. |
| [_POOL_TYPE enumeration](ne-wdm-_pool_type.md) | The POOL_TYPE enumeration type specifies the type of system memory to allocate. |
| [_POWER_REQUEST_TYPE enumeration](ne-wdm-_power_request_type.md) | The POWER_REQUEST_TYPE enumeration indicates the power request type. |
| [_POWER_STATE_TYPE enumeration](ne-wdm-_power_state_type.md) | The POWER_STATE_TYPE enumeration type indicates that a power state value is a system power state or a device power state. |
| [_PO_FX_PERF_STATE_TYPE enumeration](ne-wdm-_po_fx_perf_state_type.md) | The PO_FX_PERF_STATE_TYPE enumeration contains values that describe the type of performance states in a PO_FX_COMPONENT_PERF_SET. |
| [_PO_FX_PERF_STATE_UNIT enumeration](ne-wdm-_po_fx_perf_state_unit.md) | The PO_FX_PERF_STATE_UNIT enumeration contains values that describe the type of unit that is controlled by the performance states in a PO_FX_COMPONENT_PERF_SET. |
| [_REG_NOTIFY_CLASS enumeration](ne-wdm-_reg_notify_class.md) | The REG_NOTIFY_CLASS enumeration type specifies the type of registry operation that the configuration manager is passing to a RegistryCallback routine. |
| [_RESOURCEMANAGER_INFORMATION_CLASS enumeration](ne-wdm-_resourcemanager_information_class.md) | The RESOURCEMANAGER_INFORMATION_CLASS enumeration identifies the type of information that the ZwQueryInformationResourceManager routine can retrieve for a resource manager object. |
| [_SECURITY_IMPERSONATION_LEVEL enumeration](ne-wdm-_security_impersonation_level.md) | The SECURITY_IMPERSONATION_LEVEL enumeration type contains values that specify security impersonation levels. Security impersonation levels govern the degree to which a server process can act on behalf of a client process. |
| [_SYSTEM_POWER_STATE enumeration](ne-wdm-_system_power_state.md) | The SYSTEM_POWER_STATE enumeration type is used to indicate a system power state. |
| [_TRACE_INFORMATION_CLASS enumeration](ne-wdm-_trace_information_class.md) | The TRACE_INFORMATION_CLASS enumeration type is used to indicate types of information associated with a WMI event tracing session. |
| [_TRANSACTIONMANAGER_INFORMATION_CLASS enumeration](ne-wdm-_transactionmanager_information_class.md) | The TRANSACTIONMANAGER_INFORMATION_CLASS enumeration specifies the type of information that the ZwQueryInformationTransactionManager routine can retrieve for a transaction manager object. |
| [_TRANSACTION_INFORMATION_CLASS enumeration](ne-wdm-_transaction_information_class.md) | The TRANSACTION_INFORMATION_CLASS enumeration specifies the type of information that ZwSetInformationTransaction can set and ZwQueryInformationTransaction can retrieve for a transaction manager object. |
| [_TRANSACTION_OUTCOME enumeration](ne-wdm-_transaction_outcome.md) | The TRANSACTION_OUTCOME enumeration defines the outcomes (results) that KTM can assign to a transaction. |
| [_TRANSACTION_STATE enumeration](ne-wdm-_transaction_state.md) | The TRANSACTION_STATE enumeration defines the states that KTM can assign to a transaction. |
| [_WORK_QUEUE_TYPE enumeration](ne-wdm-_work_queue_type.md) | The WORK_QUEUE_TYPE enumeration type indicates the type of system worker thread that handles a work item. |

## Macros

| Title   | Description   |
| ---- |:---- |
| [ASSERTMSG macro](nf-wdm-assertmsg.md) | ASSERTMSG tests an expression. If the expression is false, it breaks into the kernel debugger and sends it the specified message. |
| [ExInterlockedAddLargeStatistic macro](nf-wdm-exinterlockedaddlargestatistic.md) | The ExInterlockedAddLargeStatistic routine performs an interlocked addition of a ULONG increment value to a LARGE_INTEGER variable. |
| [ExInterlockedCompareExchange64 macro](nf-wdm-exinterlockedcompareexchange64.md) | The ExInterlockedCompareExchange64 routine compares one integer variable to another and, if they are equal, sets the first variable to a caller-supplied value. |
| [ExInterlockedFlushSList macro](nf-wdm-exinterlockedflushslist.md) | The ExInterlockedFlushSList routine atomically removes all entries from a sequenced singly linked list. |
| [ExInterlockedPopEntrySList macro](nf-wdm-exinterlockedpopentryslist.md) | The ExInterlockedPopEntrySList routine atomically removes the first entry from a sequenced singly linked list. |
| [ExInterlockedPushEntrySList macro](nf-wdm-exinterlockedpushentryslist.md) | The ExInterlockedPushEntrySList routine atomically inserts an entry at the beginning of a sequenced singly linked list. |
| [FIELD_OFFSET macro](nf-wdm-field_offset.md) | The FIELD_OFFSET macro returns the byte offset of a named field in a known structure type. |
| [IoAcquireRemoveLock macro](nf-wdm-ioacquireremovelock.md) | The IoAcquireRemoveLock routine increments the count for a remove lock, indicating that the associated device object should not be detached from the device stack or deleted. |
| [IoAdjustPagingPathCount macro](nf-wdm-ioadjustpagingpathcount.md) | The IoAdjustPagingPathCount routine increments or decrements a caller-supplied page-file counter as an atomic operation. |
| [IoCallDriver macro](nf-wdm-iocalldriver.md) | The IoCallDriver routine sends an IRP to the driver associated with a specified device object. |
| [IoCompleteRequest macro](nf-wdm-iocompleterequest.md) | The IoCompleteRequest routine indicates that the caller has completed all processing for a given I/O request and is returning the given IRP to the I/O manager. |
| [IoGetFunctionCodeFromCtlCode macro](nf-wdm-iogetfunctioncodefromctlcode.md) | The IoGetFunctionCodeFromCtlCode macro returns the value of the function code contained in an I/O control code. |
| [IoInitializeRemoveLock macro](nf-wdm-ioinitializeremovelock.md) | The IoInitializeRemoveLock routine initializes a remove lock for a device object. |
| [IoIsErrorUserInduced macro](nf-wdm-ioiserroruserinduced.md) | The IoIsErrorUserInduced routine determines whether an I/O error encountered while processing a request to a removable-media device was caused by the user. |
| [IoReleaseRemoveLock macro](nf-wdm-ioreleaseremovelock.md) | The IoReleaseRemoveLock routine releases a remove lock acquired with a previous call to IoAcquireRemoveLock. |
| [IoReleaseRemoveLockAndWait macro](nf-wdm-ioreleaseremovelockandwait.md) | The IoReleaseRemoveLockAndWait routine releases a remove lock that the driver acquired in a previous call to IoAcquireRemoveLock, and waits until all acquisitions of the lock have been released. |
| [IoSizeOfIrp macro](nf-wdm-iosizeofirp.md) | The IoSizeOfIrp routine determines the size in bytes for an IRP, given the number of stack locations in the IRP. |
| [KdBreakPointWithStatus macro](nf-wdm-kdbreakpointwithstatus.md) | The KdBreakPointWithStatus macro breaks into the kernel debugger and sends the value of Status to the debugger. |
| [KdPrint macro](nf-wdm-kdprint.md) | The KdPrint macro sends a message to the kernel debugger. |
| [KdPrintEx macro](nf-wdm-kdprintex.md) | The KdPrintEx macro sends a string to the kernel debugger if the conditions you specify are met.A call to KdPrintEx requires double parentheses. |
| [KeAcquireSpinLock macro](nf-wdm-keacquirespinlock.md) | The KeAcquireSpinLock routine acquires a spin lock so the caller can synchronize access to shared data in a multiprocessor-safe way by raising IRQL. |
| [KeAcquireSpinLockAtDpcLevel macro](nf-wdm-keacquirespinlockatdpclevel.md) | The KeAcquireSpinLockAtDpcLevel routine acquires a spin lock when the caller is already running at IRQL &gt;= DISPATCH_LEVEL. |
| [KeLowerIrql macro](nf-wdm-kelowerirql.md) | The KeLowerIrql routine restores the IRQL on the current processor to its original value. |
| [KeQuerySystemTime macro](nf-wdm-kequerysystemtime.md) | The KeQuerySystemTime routine obtains the current system time. |
| [KeQueryTickCount macro](nf-wdm-kequerytickcount.md) | The KeQueryTickCount routine maintains a count of the interval timer interrupts that have occurred since the system was booted. |
| [KeRaiseIrql macro](nf-wdm-keraiseirql.md) | The KeRaiseIrql routine raises the hardware priority to the specified IRQL value, thereby masking off interrupts of equivalent or lower IRQL on the current processor. |
| [KeReleaseSpinLock macro](nf-wdm-kereleasespinlock.md) | The KeReleaseSpinLock routine releases a spin lock and restores the original IRQL at which the caller was running. |
| [KeReleaseSpinLockFromDpcLevel macro](nf-wdm-kereleasespinlockfromdpclevel.md) | The KeReleaseSpinLockFromDpcLevel routine releases an executive spin lock without changing the IRQL. |
| [MmGetMdlByteCount macro](nf-wdm-mmgetmdlbytecount.md) | The MmGetMdlByteCount macro returns the length, in bytes, of the buffer described by the specified MDL. |
| [MmGetSystemAddressForMdl macro](nf-wdm-mmgetsystemaddressformdl.md) | The MmGetSystemAddressForMdl routine is obsolete for Windows 2000 and later versions of Windows, and for Windows Me. |
| [MmLockPagableCodeSection macro](nf-wdm-mmlockpagablecodesection.md) | The MmLockPagableCodeSection routine locks a section of driver code, containing a set of driver routines marked with a special compiler directive, into system space. |
| [ObDereferenceObject macro](nf-wdm-obdereferenceobject.md) | The ObDereferenceObject routine decrements the given object's reference count and performs retention checks. |
| [ObDereferenceObjectWithTag macro](nf-wdm-obdereferenceobjectwithtag.md) | The ObDereferenceObjectWithTag routine decrements the reference count of the specified object, and writes a four-byte tag value to the object to support object reference tracing. |
| [ObReferenceObject macro](nf-wdm-obreferenceobject.md) | The ObReferenceObject routine increments the reference count to the given object. |
| [ObReferenceObjectWithTag macro](nf-wdm-obreferenceobjectwithtag.md) | The ObReferenceObjectWithTag routine increments the reference count of the specified object, and writes a four-byte tag value to the object to support object reference tracing. |
| [RtlAnsiStringToUnicodeSize macro](nf-wdm-rtlansistringtounicodesize.md) | The RtlAnsiStringToUnicodeSize routine returns the number of bytes required to hold an ANSI string converted into a Unicode string. |
| [RtlCheckBit macro](nf-wdm-rtlcheckbit.md) | The RtlCheckBit routine determines whether a particular bit in a given bitmap variable is clear or set. |
| [RtlCopyMemory macro](nf-wdm-rtlcopymemory.md) | The RtlCopyMemory routine copies the contents of a source memory block to a destination memory block. |
| [RtlEqualMemory macro](nf-wdm-rtlequalmemory.md) | The RtlEqualMemory routine compares two blocks of memory to determine whether the specified number of bytes are identical. |
| [RtlFillMemory macro](nf-wdm-rtlfillmemory.md) | The RtlFillMemory routine fills a block of memory with the specified fill value. |
| [RtlIntPtrToUnicodeString macro](nf-wdm-rtlintptrtounicodestring.md) | The RtlIntPtrToUnicodeString routine converts a specified ULONG_PTR value to a Unicode string that represents the value in a specified base. |
| [RtlMoveMemory macro](nf-wdm-rtlmovememory.md) | The RtlMoveMemory routine copies the contents of a source memory block to a destination memory block, and supports overlapping source and destination memory blocks. |
| [RtlUlongByteSwap macro](nf-wdm-rtlulongbyteswap.md) | The RtlUlongByteSwap routine reverses the ordering of the four bytes in a 32-bit unsigned integer value. |
| [RtlUlonglongByteSwap macro](nf-wdm-rtlulonglongbyteswap.md) | The RtlUlonglongByteSwap routine reverses the ordering of the eight bytes in a 64-bit unsigned integer value. |
| [RtlUnicodeStringToAnsiSize macro](nf-wdm-rtlunicodestringtoansisize.md) | The RtlUnicodeStringToAnsiSize routine returns the number of bytes required for a null-terminated ANSI string that is equivalent to a specified Unicode string. |
| [RtlUshortByteSwap macro](nf-wdm-rtlushortbyteswap.md) | The RtlUshortByteSwap routine reverses the ordering of the two bytes in a 16-bit unsigned integer value. |
| [RtlZeroMemory macro](nf-wdm-rtlzeromemory.md) | The RtlZeroMemory routine fills a block of memory with zeros, given a pointer to the block and the length, in bytes, to be filled. |
