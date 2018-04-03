---
UID: TP:ifsk
ms.assetid: c842e40c-3483-3721-b6bf-4da6e333af1a
ms.author: windowsdriverdev
ms.date: 04/03/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Installable file system

## -description

Overview of the Installable file system technology.

To develop Installable file system, you need these headers:

 * [fcb.h](..\fcb\index.md)
 * [fcbtable.h](..\fcbtable\index.md)
 * [fltkernel.h](..\fltkernel\index.md)
 * [fltsafe.h](..\fltsafe\index.md)
 * [fltuserstructures.h](..\fltuserstructures\index.md)
 * [lowio.h](..\lowio\index.md)
 * [midatlax.h](..\midatlax\index.md)
 * [mrx.h](..\mrx\index.md)
 * [mrxfcb.h](..\mrxfcb\index.md)
 * [namcache.h](..\namcache\index.md)
 * [nodetype.h](..\nodetype\index.md)
 * [ntifs.h](..\ntifs\index.md)
 * [ntrxdef.h](..\ntrxdef\index.md)
 * [prefix.h](..\prefix\index.md)
 * [rx.h](..\rx\index.md)
 * [rxce.h](..\rxce\index.md)
 * [rxcehdlr.h](..\rxcehdlr\index.md)
 * [rxcontx.h](..\rxcontx\index.md)
 * [rxdata.h](..\rxdata\index.md)
 * [rxexcept.h](..\rxexcept\index.md)
 * [rxlog.h](..\rxlog\index.md)
 * [rxpooltg.h](..\rxpooltg\index.md)
 * [rxprocs.h](..\rxprocs\index.md)
 * [rxstruc.h](..\rxstruc\index.md)
 * [rxtimer.h](..\rxtimer\index.md)
 * [rxtrace.h](..\rxtrace\index.md)
 * [rxtypes.h](..\rxtypes\index.md)
 * [rxworkq.h](..\rxworkq\index.md)
 * [scavengr.h](..\scavengr\index.md)
 * [struchdr.h](..\struchdr\index.md)
 * [tdi.h](..\tdi\index.md)

For the programming guide, see [Installable file system](===404===https://docs.microsoft.com/en-us/windows-hardware/drivers/ifsk).

## Functions

| Title   | Description   |
| ---- |:---- |
| [CcCanIWrite function](..\ntifs\nf-ntifs-cccaniwrite.md) | The CcCanIWrite routine determines whether the caller can write to a cached file. |
| [CcCoherencyFlushAndPurgeCache function](..\ntifs\nf-ntifs-cccoherencyflushandpurgecache.md) | The CcCoherencyFlushAndPurgeCache routine flushes and/or purges the cache to ensure cache coherency. |
| [CcCopyRead function](..\ntifs\nf-ntifs-cccopyread.md) | The CcCopyRead routine copies data from a cached file to a user buffer. |
| [CcCopyReadEx function](..\ntifs\nf-ntifs-cccopyreadex.md) | The CcCopyReadEx routine copies data from a cached file to a user buffer. The I/O byte count for the operation is charged to the issuing thread. |
| [CcCopyWrite function](..\ntifs\nf-ntifs-cccopywrite.md) | The CcCopyWrite routine copies data from a user buffer to a cached file. |
| [CcCopyWriteEx function](..\ntifs\nf-ntifs-cccopywriteex.md) | The CcCopyWriteEx routine copies data from a user buffer to a cached file. The I/O byte count for the operation is charged to the issuing thread. |
| [CcCopyWriteWontFlush function](..\ntifs\nf-ntifs-cccopywritewontflush.md) | The CcCopyWriteWontFlush macro determines whether the amount of data to be copied in a call to CcCopyWrite is small enough not to require immediate flushing to disk if CcCopyWrite is called with Wait set to FALSE. |
| [CcDeferWrite function](..\ntifs\nf-ntifs-ccdeferwrite.md) | The CcDeferWrite routine defers writing to a cached file. |
| [CcFastCopyRead function](..\ntifs\nf-ntifs-ccfastcopyread.md) | The CcFastCopyRead routine performs a fast copy read from a cached file to a buffer in memory. |
| [CcFastCopyWrite function](..\ntifs\nf-ntifs-ccfastcopywrite.md) | The CcFastCopyWrite routine performs a fast copy write from a buffer in memory to a cached file. |
| [CcFlushCache function](..\ntifs\nf-ntifs-ccflushcache.md) | The CcFlushCache routine flushes all or a portion of a cached file to disk. |
| [CcGetDirtyPages function](..\ntifs\nf-ntifs-ccgetdirtypages.md) | The CcGetDirtyPages routine searches for dirty pages in all files that match a given log handle. |
| [CcGetFileObjectFromBcb function](..\ntifs\nf-ntifs-ccgetfileobjectfrombcb.md) | Given a pointer to a pinned buffer control block (BCB) for a file, the CcGetFileObjectFromBcb routine returns a pointer to the file object that the cache manager is using for that file. |
| [CcGetFileObjectFromSectionPtrs function](..\ntifs\nf-ntifs-ccgetfileobjectfromsectionptrs.md) | Given a pointer to the section object pointers for a cached file, the CcGetFileObjectFromSectionPtrs routine returns a pointer to the file object that the cache manager is using for the file. |
| [CcGetFileObjectFromSectionPtrsRef function](..\ntifs\nf-ntifs-ccgetfileobjectfromsectionptrsref.md) | When passed a pointer to a SECTION_OBJECT_POINTERS structure for a cached file, the CcGetFileObjectFromSectionPtrsRef routine returns a pointer to the file object that the cache manager is using for the cached file. |
| [CcGetFlushedValidData function](..\ntifs\nf-ntifs-ccgetflushedvaliddata.md) | The CcGetFlushedValidData routine determines how much of a cached file has been flushed to disk. |
| [CcInitializeCacheMap function](..\ntifs\nf-ntifs-ccinitializecachemap.md) | File systems call the CcInitializeCacheMap routine to cache a file. |
| [CcIsThereDirtyData function](..\ntifs\nf-ntifs-ccistheredirtydata.md) | The CcIsThereDirtyData routine determines whether a mounted volume contains any files that have dirty data in the system cache. |
| [CcIsThereDirtyDataEx function](..\ntifs\nf-ntifs-ccistheredirtydataex.md) | The CcIsThereDirtyDataEx routine determines whether a volume contains any files that have dirty data in the system cache. |
| [CcMapData function](..\ntifs\nf-ntifs-ccmapdata.md) | The CcMapData routine maps a specified byte range of a cached file to a buffer in memory. |
| [CcMdlReadComplete function](..\ntifs\nf-ntifs-ccmdlreadcomplete.md) | The CcMdlReadComplete routine frees the memory descriptor lists (MDL) created by CcMdlRead for a cached file. |
| [CcMdlWriteAbort function](..\ntifs\nf-ntifs-ccmdlwriteabort.md) | The CcMdlWriteAbort routine frees memory descriptor lists (MDL) created by an earlier call to CcPrepareMdlWrite. |
| [CcMdlWriteComplete function](..\ntifs\nf-ntifs-ccmdlwritecomplete.md) | The CcMdlWriteComplete routine frees the memory descriptor lists (MDL) created by CcPrepareMdlWrite for a cached file. |
| [CcPinMappedData function](..\ntifs\nf-ntifs-ccpinmappeddata.md) | The CcPinMappedData routine pins the specified byte range of a cached file. |
| [CcPinRead function](..\ntifs\nf-ntifs-ccpinread.md) | The CcPinRead routine pins the specified byte range of a cached file and reads the pinned data into a buffer in memory. |
| [CcPrepareMdlWrite function](..\ntifs\nf-ntifs-ccpreparemdlwrite.md) | The CcPrepareMdlWrite routine provides direct access to cached file memory so that the caller can write data to the file. |
| [CcPreparePinWrite function](..\ntifs\nf-ntifs-ccpreparepinwrite.md) | The CcPreparePinWrite routine pins the specified byte range of a cached file for write access. |
| [CcPurgeCacheSection function](..\ntifs\nf-ntifs-ccpurgecachesection.md) | The CcPurgeCacheSection routine purges all or a portion of a cached file from the system cache. |
| [CcRemapBcb function](..\ntifs\nf-ntifs-ccremapbcb.md) | The CcRemapBcb routine maps a buffer control block (BCB) an additional time to preserve it through several calls that perform additional maps and unpins. |
| [CcRepinBcb function](..\ntifs\nf-ntifs-ccrepinbcb.md) | The CcRepinBcb routine pins a buffer control block (BCB) an additional time to prevent it from being freed by a subsequent call to CcUnpinData. |
| [CcScheduleReadAhead function](..\ntifs\nf-ntifs-ccschedulereadahead.md) | The CcScheduleReadAhead routine performs read-ahead (also called &#0034;lazy read&#0034;) on a cached file. CcScheduleReadAhead should never be called directly. The CcReadAhead macro should be called instead. |
| [CcScheduleReadAheadEx function](..\ntifs\nf-ntifs-ccschedulereadaheadex.md) | The CcScheduleReadAheadEx routine performs read-ahead (also called &#0034;lazy read&#0034;) on a cached file. The I/O byte count for the operation is charged to the issuing thread. |
| [CcSetAdditionalCacheAttributes function](..\ntifs\nf-ntifs-ccsetadditionalcacheattributes.md) | Call the CcSetAdditionalCacheAttributes routine to enable or disable read-ahead (also called &#0034;lazy read&#0034;) or write-behind (also called &#0034;lazy write&#0034;) on a cached file. |
| [CcSetAdditionalCacheAttributesEx function](..\ntifs\nf-ntifs-ccsetadditionalcacheattributesex.md) | Call the CcSetAdditionalCacheAttributesEx routine to enable extended cache behavior on a cached file. |
| [CcSetBcbOwnerPointer function](..\ntifs\nf-ntifs-ccsetbcbownerpointer.md) | The CcSetBcbOwnerPointer routine sets the owner thread pointer for a pinned buffer control block (BCB). |
| [CcSetDirtyPageThreshold function](..\ntifs\nf-ntifs-ccsetdirtypagethreshold.md) | The CcSetDirtyPageThreshold routine sets a per-file dirty page threshold on a cached file. |
| [CcSetDirtyPinnedData function](..\ntifs\nf-ntifs-ccsetdirtypinneddata.md) | The CcSetDirtyPinnedData routine marks as dirty the buffer control block (BCB) for a pinned buffer whose contents have been modified. |
| [CcSetFileSizes function](..\ntifs\nf-ntifs-ccsetfilesizes.md) | The CcSetFileSizes routine updates the cache maps and section object for a cached file whose size has changed. |
| [CcSetLogHandleForFile function](..\ntifs\nf-ntifs-ccsetloghandleforfile.md) | The CcSetLogHandleForFile routine sets a log handle for a file. |
| [CcSetReadAheadGranularity function](..\ntifs\nf-ntifs-ccsetreadaheadgranularity.md) | The CcSetReadAheadGranularity routine sets the read-ahead granularity for a cached file. |
| [CcUninitializeCacheMap function](..\ntifs\nf-ntifs-ccuninitializecachemap.md) | The CcUninitializeCacheMap routine stops the caching of a cached file. |
| [CcUnpinData function](..\ntifs\nf-ntifs-ccunpindata.md) | The CcUnpinData routine releases cached file data that was mapped or pinned by an earlier call to CcMapData, CcPinRead, or CcPreparePinWrite. |
| [CcUnpinDataForThread function](..\ntifs\nf-ntifs-ccunpindataforthread.md) | The CcUnpinDataForThread routine releases pages of a cached file whose buffer control block (BCB) was modified by an earlier call to CcSetBcbOwnerPointer. |
| [CcUnpinRepinnedBcb function](..\ntifs\nf-ntifs-ccunpinrepinnedbcb.md) | The CcUnpinRepinnedBcb routine unpins a repinned buffer control block (BCB). |
| [CcWaitForCurrentLazyWriterActivity function](..\ntifs\nf-ntifs-ccwaitforcurrentlazywriteractivity.md) | The CcWaitForCurrentLazyWriterActivity routine puts the caller into a wait state until the current batch of lazy writer activity is completed. |
| [CcZeroData function](..\ntifs\nf-ntifs-cczerodata.md) | The CcZeroData routine zeros the specified range of bytes in a cached or noncached file. |
| [ExAdjustLookasideDepth function](..\ntifs\nf-ntifs-exadjustlookasidedepth.md) | Reserved for system use. |
| [ExDisableResourceBoostLite function](..\ntifs\nf-ntifs-exdisableresourceboostlite.md) | Reserved for system use. |
| [ExQueryPoolBlockSize function](..\ntifs\nf-ntifs-exquerypoolblocksize.md) | Obsolete. |
| [FltAcknowledgeEcp function](..\fltkernel\nf-fltkernel-fltacknowledgeecp.md) | The FltAcknowledgeEcp routine is used to mark an extra create parameter context structure (ECP) as acknowledged. |
| [FltAddOpenReparseEntry function](..\fltkernel\nf-fltkernel-fltaddopenreparseentry.md) | This routine adds a caller allocated open reparse structure, OPEN_REPARSE_LIST_ENTRY, into a create operation. |
| [FltAdjustDeviceStackSizeForIoRedirection function](..\fltkernel\nf-fltkernel-fltadjustdevicestacksizeforioredirection.md) | The FltAdjustDeviceStackSizeForIoRedirection routine increases the size of the source device stack to allow a minifilter to redirect I/O from a specified source instance to a specified target instance when the target stack is deeper than the source stack. |
| [FltAllocateCallbackData function](..\fltkernel\nf-fltkernel-fltallocatecallbackdata.md) | FltAllocateCallbackData allocates a callback data structure that a minifilter driver can use to initiate an I/O request. |
| [FltAllocateCallbackDataEx function](..\fltkernel\nf-fltkernel-fltallocatecallbackdataex.md) | The FltAllocateCallbackDataEx routine allocates a callback data structure and can preallocate memory for additional structures that a minifilter driver can use to initiate an I/O request. |
| [FltAllocateContext function](..\fltkernel\nf-fltkernel-fltallocatecontext.md) | The FltAllocateContext routine allocates a context structure for a specified context type. |
| [FltAllocateDeferredIoWorkItem function](..\fltkernel\nf-fltkernel-fltallocatedeferredioworkitem.md) | FltAllocateDeferredIoWorkItem allocates a deferred-I/O work item. |
| [FltAllocateExtraCreateParameter function](..\fltkernel\nf-fltkernel-fltallocateextracreateparameter.md) | The FltAllocateExtraCreateParameter routine allocates paged memory pool for a user-defined extra create parameter (ECP) context structure and generates a pointer to that structure. |
| [FltAllocateExtraCreateParameterFromLookasideList function](..\fltkernel\nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md) | The FltAllocateExtraCreateParameterFromLookasideList routine allocates memory pool from a given lookaside list for an extra create parameter (ECP) context structure and generates a pointer to that structure. |
| [FltAllocateExtraCreateParameterList function](..\fltkernel\nf-fltkernel-fltallocateextracreateparameterlist.md) | The FltAllocateExtraCreateParameterList routine allocates paged pool memory for an extra create parameter (ECP) list structure and generates a pointer to that structure. |
| [FltAllocateFileLock function](..\fltkernel\nf-fltkernel-fltallocatefilelock.md) | The FltAllocateFileLock routine allocates and initializes a new FILE_LOCK structure. |
| [FltAllocateGenericWorkItem function](..\fltkernel\nf-fltkernel-fltallocategenericworkitem.md) | FltAllocateGenericWorkItem allocates a generic work item. |
| [FltAllocatePoolAlignedWithTag function](..\fltkernel\nf-fltkernel-fltallocatepoolalignedwithtag.md) | FltAllocatePoolAlignedWithTag allocates a device-aligned buffer for use in a noncached I/O operation. |
| [FltApplyPriorityInfoThread function](..\fltkernel\nf-fltkernel-fltapplypriorityinfothread.md) | The FltApplyPriorityInfoThread routine is used by a minifilter driver to apply priority information to a thread. |
| [FltAttachVolume function](..\fltkernel\nf-fltkernel-fltattachvolume.md) | FltAttachVolume creates a new minifilter driver instance and attaches it to the given volume. |
| [FltAttachVolumeAtAltitude function](..\fltkernel\nf-fltkernel-fltattachvolumeataltitude.md) | FltAttachVolumeAtAltitude is a debugging support routine that attaches a minifilter driver instance to a volume at a specified altitude, overriding any settings in the minifilter driver's INF file. |
| [FltBuildDefaultSecurityDescriptor function](..\fltkernel\nf-fltkernel-fltbuilddefaultsecuritydescriptor.md) | FltBuildDefaultSecurityDescriptor builds a default security descriptor for use with FltCreateCommunicationPort. |
| [FltCancelFileOpen function](..\fltkernel\nf-fltkernel-fltcancelfileopen.md) | A minifilter driver can use the FltCancelFileOpen routine to close a newly opened or created file. |
| [FltCancelIo function](..\fltkernel\nf-fltkernel-fltcancelio.md) | The FltCancelIo routine cancels an I/O operation. |
| [FltCancellableWaitForMultipleObjects function](..\fltkernel\nf-fltkernel-fltcancellablewaitformultipleobjects.md) | The FltCancellableWaitForMultipleObjects executes a cancelable wait operation (a wait that can be terminated) on one or more dispatcher objects. |
| [FltCancellableWaitForSingleObject function](..\fltkernel\nf-fltkernel-fltcancellablewaitforsingleobject.md) | The FltCancellableWaitForSingleObject routine executes a cancelable wait operation (a wait that can be terminated) on a dispatcher object. |
| [FltCbdqDisable function](..\fltkernel\nf-fltkernel-fltcbdqdisable.md) | FltCbdqDisable disables a minifilter driver's callback data queue. |
| [FltCbdqEnable function](..\fltkernel\nf-fltkernel-fltcbdqenable.md) | FltCbdqEnable enables a callback data queue that was disabled by a previous call to FltCbdqDisable. |
| [FltCbdqInitialize function](..\fltkernel\nf-fltkernel-fltcbdqinitialize.md) | FltCbdqInitialize initializes a minifilter driver's callback data queue dispatch table. |
| [FltCbdqInsertIo function](..\fltkernel\nf-fltkernel-fltcbdqinsertio.md) | FltCbdqInsertIo inserts the callback data structure for an I/O operation into a minifilter driver's callback data queue. |
| [FltCbdqRemoveIo function](..\fltkernel\nf-fltkernel-fltcbdqremoveio.md) | FltCbdqRemoveIo removes a particular item from a minifilter driver's callback data queue. |
| [FltCbdqRemoveNextIo function](..\fltkernel\nf-fltkernel-fltcbdqremovenextio.md) | FltCbdqRemoveNextIo removes the next matching item in a minifilter driver's callback data queue. |
| [FltCheckAndGrowNameControl function](..\fltkernel\nf-fltkernel-fltcheckandgrownamecontrol.md) | The FltCheckAndGrowNameControl routine checks whether the buffer in a FLT_NAME_CONTROL structure is large enough to hold the specified number of bytes. If not, FltCheckAndGrowNameControl replaces it with a larger system-allocated buffer. |
| [FltCheckLockForReadAccess function](..\fltkernel\nf-fltkernel-fltchecklockforreadaccess.md) | The FltCheckLockForReadAccess routine determines whether the caller has read access to a locked byte range of a file. |
| [FltCheckLockForWriteAccess function](..\fltkernel\nf-fltkernel-fltchecklockforwriteaccess.md) | The FltCheckLockForWriteAccess routine determines whether the caller has write access to a locked byte range of a file. |
| [FltCheckOplock function](..\fltkernel\nf-fltkernel-fltcheckoplock.md) | A minifilter driver calls FltCheckOplock to synchronize the callback data structure for an IRP-based file I/O operation with the file's current opportunistic lock (oplock) state. |
| [FltCheckOplockEx function](..\fltkernel\nf-fltkernel-fltcheckoplockex.md) | A minifilter driver calls the FltCheckOplockEx routine to synchronize the callback data structure for an IRP-based file I/O operation that has the current opportunistic lock (oplock) state of the file. |
| [FltClearCallbackDataDirty function](..\fltkernel\nf-fltkernel-fltclearcallbackdatadirty.md) | The FltClearCallbackDataDirty routine clears the callback dirty flag in a callback data structure. |
| [FltClearCancelCompletion function](..\fltkernel\nf-fltkernel-fltclearcancelcompletion.md) | FltClearCancelCompletion clears a cancel routine that was specified for an I/O operation. |
| [FltClose function](..\fltkernel\nf-fltkernel-fltclose.md) | FltClose closes a file handle that was opened by FltCreateFile or FltCreateFileEx. |
| [FltCloseClientPort function](..\fltkernel\nf-fltkernel-fltcloseclientport.md) | FltCloseClientPort closes a communication client port. |
| [FltCloseCommunicationPort function](..\fltkernel\nf-fltkernel-fltclosecommunicationport.md) | FltCloseCommunicationPort closes a minifilter driver's communication server port. |
| [FltCloseSectionForDataScan function](..\fltkernel\nf-fltkernel-fltclosesectionfordatascan.md) | The FltCloseSectionForDataScan routine closes a section object associated with a file stream. |
| [FltCommitComplete function](..\fltkernel\nf-fltkernel-fltcommitcomplete.md) | The FltCommitComplete routine acknowledges a TRANSACTION_NOTIFY_COMMIT notification. |
| [FltCommitFinalizeComplete function](..\fltkernel\nf-fltkernel-fltcommitfinalizecomplete.md) | The FltCommitFinalizeComplete routine acknowledges a TRANSACTION_NOTIFY_COMMIT_FINALIZE notification. |
| [FltCompareInstanceAltitudes function](..\fltkernel\nf-fltkernel-fltcompareinstancealtitudes.md) | FltCompareInstanceAltitudes compares the altitudes of two minifilter driver instances. |
| [FltCompletePendedPostOperation function](..\fltkernel\nf-fltkernel-fltcompletependedpostoperation.md) | FltCompletePendedPostOperation resumes completion processing for an I/O operation that was pended in a minifilter driver's postoperation callback routine. |
| [FltCompletePendedPreOperation function](..\fltkernel\nf-fltkernel-fltcompletependedpreoperation.md) | FltCompletePendedPreOperation resumes processing for an I/O operation that was pended in a minifilter driver's preoperation callback (PFLT_PRE_OPERATION_CALLBACK) routine. |
| [FltCopyOpenReparseList function](..\fltkernel\nf-fltkernel-fltcopyopenreparselist.md) | This routine copies any open reparse information from a previous create into a new ECP list that can be used to issue a second create. |
| [FltCreateCommunicationPort function](..\fltkernel\nf-fltkernel-fltcreatecommunicationport.md) | FltCreateCommunicationPort creates a communication server port on which a minifilter driver can receive connection requests from user-mode applications. |
| [FltCreateFile function](..\fltkernel\nf-fltkernel-fltcreatefile.md) | Minifilter drivers call FltCreateFile to create a new file or open an existing file. |
| [FltCreateFileEx function](..\fltkernel\nf-fltkernel-fltcreatefileex.md) | Minifilter drivers call FltCreateFileEx to create a new file or open an existing file. |
| [FltCreateFileEx2 function](..\fltkernel\nf-fltkernel-fltcreatefileex2.md) | Minifilter drivers call FltCreateFileEx2 to create a new file or open an existing file. This routine also includes an optional create context parameter. |
| [FltCreateMailslotFile function](..\fltkernel\nf-fltkernel-fltcreatemailslotfile.md) | Minifilter drivers call FltCreateMailslotFile to create a new pipe or open an existing mailslot. |
| [FltCreateNamedPipeFile function](..\fltkernel\nf-fltkernel-fltcreatenamedpipefile.md) | Minifilter drivers call FltCreateNamedPipeFile to create a new pipe or open an existing pipe. |
| [FltCreateSectionForDataScan function](..\fltkernel\nf-fltkernel-fltcreatesectionfordatascan.md) | The FltCreateSectionForDataScan routine creates a section object for a file. The filter manager can optionally synchronize I/O with the section created. |
| [FltCreateSystemVolumeInformationFolder function](..\fltkernel\nf-fltkernel-fltcreatesystemvolumeinformationfolder.md) | FltCreateSystemVolumeInformationFolder verifies the existence of the &#0034;System Volume Information&#0034; folder on a file system volume. If the folder is not present, then the folder is created. |
| [FltCurrentBatchOplock function](..\fltkernel\nf-fltkernel-fltcurrentbatchoplock.md) | A minifilter driver calls FltCurrentBatchOplock to determine whether there are any batch or filter opportunistic locks (oplocks) on a file. |
| [FltCurrentOplock function](..\fltkernel\nf-fltkernel-fltcurrentoplock.md) | A minifilter driver calls the FltCurrentOplock routine to determine whether there are any opportunistic locks (oplocks) on a file. |
| [FltCurrentOplockH function](..\fltkernel\nf-fltkernel-fltcurrentoplockh.md) | A minifilter driver calls the FltCurrentOplockH routine to determine whether there are any CACHE_HANDLE_LEVEL opportunistic locks (oplocks) on a file. |
| [FltDecodeParameters function](..\fltkernel\nf-fltkernel-fltdecodeparameters.md) | FltDecodeParameters returns pointers to the memory descriptor list (MDL) address, buffer pointer, buffer length, and desired access parameters for an I/O operation. |
| [FltDeleteContext function](..\fltkernel\nf-fltkernel-fltdeletecontext.md) | FltDeleteContext marks a specified context for deletion. |
| [FltDeleteExtraCreateParameterLookasideList function](..\fltkernel\nf-fltkernel-fltdeleteextracreateparameterlookasidelist.md) | The FltDeleteExtraCreateParameterLookasideList routine frees an extra create parameter (ECP) lookaside list. |
| [FltDeleteFileContext function](..\fltkernel\nf-fltkernel-fltdeletefilecontext.md) | The FltDeleteFileContext routine retrieves and deletes a file context that a given minifilter driver has set for a given file. |
| [FltDeleteInstanceContext function](..\fltkernel\nf-fltkernel-fltdeleteinstancecontext.md) | FltDeleteInstanceContext removes a context from a given instance and marks the context for deletion. |
| [FltDeletePushLock function](..\fltkernel\nf-fltkernel-fltdeletepushlock.md) | The FltDeletePushLock routine deletes a given push lock. |
| [FltDeleteStreamContext function](..\fltkernel\nf-fltkernel-fltdeletestreamcontext.md) | FltDeleteStreamContext removes a context that a given minifilter driver instance has set for a given stream and marks the context for deletion. |
| [FltDeleteStreamHandleContext function](..\fltkernel\nf-fltkernel-fltdeletestreamhandlecontext.md) | FltDeleteStreamHandleContext removes a context that a given minifilter driver instance has set for a given stream handle and marks the context for deletion. |
| [FltDeleteTransactionContext function](..\fltkernel\nf-fltkernel-fltdeletetransactioncontext.md) | The FltDeleteTransactionContext routine removes a context from a given transaction and marks the context for deletion. |
| [FltDeleteVolumeContext function](..\fltkernel\nf-fltkernel-fltdeletevolumecontext.md) | FltDeleteVolumeContext removes a context that a given minifilter driver has set for a given volume and marks the context for deletion. |
| [FltDetachVolume function](..\fltkernel\nf-fltkernel-fltdetachvolume.md) | FltDetachVolume detaches a minifilter driver instance from a volume. |
| [FltDeviceIoControlFile function](..\fltkernel\nf-fltkernel-fltdeviceiocontrolfile.md) | FltDeviceIoControlFile sends a control code directly to a specified device driver, causing the corresponding driver to perform the specified action. |
| [FltDoCompletionProcessingWhenSafe function](..\fltkernel\nf-fltkernel-fltdocompletionprocessingwhensafe.md) | If it is safe to do so, the FltDoCompletionProcessingWhenSafe function executes a minifilter driver postoperation callback routine. |
| [FltEnlistInTransaction function](..\fltkernel\nf-fltkernel-fltenlistintransaction.md) | The FltEnlistInTransaction routine enlists a minifilter driver in a given transaction. |
| [FltEnumerateFilterInformation function](..\fltkernel\nf-fltkernel-fltenumeratefilterinformation.md) | The FltEnumerateFilterInformation routine provides information about all the registered filter drivers (including minifilter and legacy filter drivers) in the system. |
| [FltEnumerateFilters function](..\fltkernel\nf-fltkernel-fltenumeratefilters.md) | The FltEnumerateFilters routine enumerates all registered minifilter drivers in the system. |
| [FltEnumerateInstanceInformationByDeviceObject function](..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbydeviceobject.md) | The FltEnumerateInstanceInformationByDeviceObject routine provides information about minifilter driver instances and legacy filter drivers that are attached to the volume related to a specified device object. |
| [FltEnumerateInstanceInformationByFilter function](..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyfilter.md) | The FltEnumerateInstanceInformationByFilter routine provides information about instances of a given minifilter driver. |
| [FltEnumerateInstanceInformationByVolume function](..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyvolume.md) | The FltEnumerateInstanceInformationByVolume routine provides information about minifilter driver instances and legacy filter drivers (Windows Vista only) that are attached to a given volume. |
| [FltEnumerateInstanceInformationByVolumeName function](..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyvolumename.md) | The FltEnumerateInstanceInformationByVolumeName routine provides information about minifilter driver instances and legacy filter drivers that are attached to the volume with the specified name. |
| [FltEnumerateInstances function](..\fltkernel\nf-fltkernel-fltenumerateinstances.md) | The FltEnumerateInstances routine enumerates minifilter driver instances for a given minifilter driver or volume. |
| [FltEnumerateVolumeInformation function](..\fltkernel\nf-fltkernel-fltenumeratevolumeinformation.md) | The FltEnumerateVolumeInformation routine provides information about volumes that are known to the filter manager. |
| [FltEnumerateVolumes function](..\fltkernel\nf-fltkernel-fltenumeratevolumes.md) | The FltEnumerateVolumes routine enumerates all volumes in the system. |
| [FltFastIoMdlRead function](..\fltkernel\nf-fltkernel-fltfastiomdlread.md) | The FltFastIoMdlRead routine returns a memory descriptor list (MDL) that points directly to the specified byte range in the file cache. |
| [FltFastIoMdlReadComplete function](..\fltkernel\nf-fltkernel-fltfastiomdlreadcomplete.md) | The FltFastIoMdlReadComplete routine completes the read operation that the FltFastIoMdlRead routine initiated. |
| [FltFastIoMdlWriteComplete function](..\fltkernel\nf-fltkernel-fltfastiomdlwritecomplete.md) | The FltFastIoMdlWriteComplete routine frees the resources that FltFastIoPrepareMdlWrite allocated. |
| [FltFastIoPrepareMdlWrite function](..\fltkernel\nf-fltkernel-fltfastiopreparemdlwrite.md) | The FltFastIoPrepareMdlWrite routine returns a linked list of memory descriptor lists (MDLs) that point to the specified range of cached file data to write data directly to the cache. |
| [FltFindExtraCreateParameter function](..\fltkernel\nf-fltkernel-fltfindextracreateparameter.md) | The FltFindExtraCreateParameter routine searches a given ECP list for an ECP context structure of a given type and returns a pointer to this structure if it is found. |
| [FltFlushBuffers function](..\fltkernel\nf-fltkernel-fltflushbuffers.md) | The FltFlushBuffers routine is used by the minifilter driver to send a flush request for a given file to the file system. |
| [FltFreeCallbackData function](..\fltkernel\nf-fltkernel-fltfreecallbackdata.md) | The FltFreeCallbackData routine frees a callback data structure allocated by the FltAllocateCallbackData routine. |
| [FltFreeDeferredIoWorkItem function](..\fltkernel\nf-fltkernel-fltfreedeferredioworkitem.md) | The FltFreeDeferredIoWorkItem routine frees a work item allocated by the FltAllocateDeferredIoWorkItem routine. |
| [FltFreeExtraCreateParameter function](..\fltkernel\nf-fltkernel-fltfreeextracreateparameter.md) | The FltFreeExtraCreateParameter routine frees the memory for an ECP context structure. |
| [FltFreeExtraCreateParameterList function](..\fltkernel\nf-fltkernel-fltfreeextracreateparameterlist.md) | The FltFreeExtraCreateParameterList routine frees an extra create parameter (ECP) list structure. |
| [FltFreeFileLock function](..\fltkernel\nf-fltkernel-fltfreefilelock.md) | The FltFreeFileLock routine uninitializes and frees an initialized FILE_LOCK structure. |
| [FltFreeGenericWorkItem function](..\fltkernel\nf-fltkernel-fltfreegenericworkitem.md) | The FltFreeGenericWorkItem routine frees a work item allocated by the FltAllocateGenericWorkItem routine. |
| [FltFreeOpenReparseList function](..\fltkernel\nf-fltkernel-fltfreeopenreparselist.md) | This routine deallocates any information copied into a create operation by a previous call to FltCopyOpenReparseList. |
| [FltFreePoolAlignedWithTag function](..\fltkernel\nf-fltkernel-fltfreepoolalignedwithtag.md) | The FltFreePoolAlignedWithTag routine frees a cache-aligned buffer that was allocated by a previous call to FltAllocatePoolAlignedWithTag. |
| [FltFreeSecurityDescriptor function](..\fltkernel\nf-fltkernel-fltfreesecuritydescriptor.md) | FltFreeSecurityDescriptor frees a security descriptor allocated by the FltBuildDefaultSecurityDescriptor routine. |
| [FltFsControlFile function](..\fltkernel\nf-fltkernel-fltfscontrolfile.md) | The FltFsControlFile routine sends a control code directly to a specified file system or file system filter driver, causing the corresponding driver to perform the specified action. |
| [FltGetActivityIdCallbackData function](..\fltkernel\nf-fltkernel-fltgetactivityidcallbackdata.md) | The FltGetActivityIdCallbackData routine retrieves the current activity ID associated with a request in a minifilter's callback data. |
| [FltGetBottomInstance function](..\fltkernel\nf-fltkernel-fltgetbottominstance.md) | FltGetBottomInstance returns an opaque instance pointer for the minifilter driver instance, if there is one, that is attached at the bottom of the instance stack for a given volume. |
| [FltGetContexts function](..\fltkernel\nf-fltkernel-fltgetcontexts.md) | The FltGetContexts routine retrieves a minifilter driver's contexts for the objects related to the current operation. |
| [FltGetContextsEx function](..\fltkernel\nf-fltkernel-fltgetcontextsex.md) | The FltGetContextsEx routine retrieves a minifilter driver's contexts for the objects related to the current operation. |
| [FltGetDestinationFileNameInformation function](..\fltkernel\nf-fltkernel-fltgetdestinationfilenameinformation.md) | The FltGetDestinationFileNameInformation routine constructs a full destination path name for a file or directory that is being renamed or for which an NTFS hard link is being created. |
| [FltGetDeviceObject function](..\fltkernel\nf-fltkernel-fltgetdeviceobject.md) | The FltGetDeviceObject routine returns a pointer to the Filter Manager's volume device object (VDO) for a given volume. |
| [FltGetDiskDeviceObject function](..\fltkernel\nf-fltkernel-fltgetdiskdeviceobject.md) | The FltGetDiskDeviceObject routine returns a pointer to the disk device object associated with a given volume. |
| [FltGetEcpListFromCallbackData function](..\fltkernel\nf-fltkernel-fltgetecplistfromcallbackdata.md) | The FltGetEcpListFromCallbackData routine returns a pointer to an extra create parameter context structure (ECP) list that is associated with a given create operation callback-data object. |
| [FltGetFileContext function](..\fltkernel\nf-fltkernel-fltgetfilecontext.md) | The FltGetFileContext routine retrieves a context that was set for a file by a given minifilter driver instance. |
| [FltGetFileNameInformation function](..\fltkernel\nf-fltkernel-fltgetfilenameinformation.md) | The FltGetFileNameInformation routine returns name information for a file or directory. |
| [FltGetFileNameInformationUnsafe function](..\fltkernel\nf-fltkernel-fltgetfilenameinformationunsafe.md) | The FltGetFileNameInformationUnsafe routine returns name information for an open file or directory. |
| [FltGetFileSystemType function](..\fltkernel\nf-fltkernel-fltgetfilesystemtype.md) | The FltGetFileSystemType function takes a volume or instance object and provides the file system type of the volume. |
| [FltGetFilterFromInstance function](..\fltkernel\nf-fltkernel-fltgetfilterfrominstance.md) | The FltGetFilterFromInstance routine returns an opaque filter pointer for the minifilter driver that created the given instance. |
| [FltGetFilterFromName function](..\fltkernel\nf-fltkernel-fltgetfilterfromname.md) | The FltGetFilterFromName routine returns an opaque filter pointer for a registered minifilter driver whose name matches the value in the FilterName parameter. |
| [FltGetFilterInformation function](..\fltkernel\nf-fltkernel-fltgetfilterinformation.md) | The FltGetFilterInformation routine provides information about a minifilter driver. |
| [FltGetInstanceContext function](..\fltkernel\nf-fltkernel-fltgetinstancecontext.md) | The FltGetInstanceContext routine retrieves a context that was set for an instance by a given minifilter driver. |
| [FltGetInstanceInformation function](..\fltkernel\nf-fltkernel-fltgetinstanceinformation.md) | The FltGetInstanceInformation routine returns information about a minifilter driver instance. |
| [FltGetIoPriorityHint function](..\fltkernel\nf-fltkernel-fltgetiopriorityhint.md) | The FltGetIoPriorityHint routine is used by a minifilter driver to get IO priority information from Callback Data. |
| [FltGetIoPriorityHintFromCallbackData function](..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromcallbackdata.md) | The FltGetIoPriorityHintFromCallbackData routine is used by a minifilter driver to get IO priority information from callback data. |
| [FltGetIoPriorityHintFromFileObject function](..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromfileobject.md) | The FltGetIoPriorityHintFromFileObject routine is used by a minifilter driver to get IO priority information from a file object. |
| [FltGetIoPriorityHintFromThread function](..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromthread.md) | The FltGetIoPriorityHintFromThread routine is used by a minifilter driver to get IO priority information from a thread. |
| [FltGetIrpName function](..\fltkernel\nf-fltkernel-fltgetirpname.md) | The FltGetIrpName routine returns the name for a major function code as a printable string. |
| [FltGetLowerInstance function](..\fltkernel\nf-fltkernel-fltgetlowerinstance.md) | The FltGetLowerInstance routine returns an opaque instance pointer for the next lower minifilter driver instance, if there is one, that is attached below a given minifilter driver instance on the same volume. |
| [FltGetNewSystemBufferAddress function](..\fltkernel\nf-fltkernel-fltgetnewsystembufferaddress.md) | The FltGetNewSystemBufferAddress function retrieves the AssociatedIrp.SystemBuffer buffer, which the file system has allocated. A minifilter driver's post-callback routine calls this function. |
| [FltGetNextExtraCreateParameter function](..\fltkernel\nf-fltkernel-fltgetnextextracreateparameter.md) | The FltGetNextExtraCreateParameter routine returns a pointer to the next (or first) extra create parameter context structure (ECP) in a given ECP list. |
| [FltGetRequestorProcess function](..\fltkernel\nf-fltkernel-fltgetrequestorprocess.md) | The FltGetRequestorProcess routine returns a process pointer for the thread that requested a given I/O operation. |
| [FltGetRequestorProcessId function](..\fltkernel\nf-fltkernel-fltgetrequestorprocessid.md) | The FltGetRequestorProcessId routine returns the unique 32-bit process ID for the process associated with the thread that requested a given I/O operation. |
| [FltGetRequestorProcessIdEx function](..\fltkernel\nf-fltkernel-fltgetrequestorprocessidex.md) | The FltGetRequestorProcessIdEx routine returns the kernel-mode handle for the process that is associated with the thread that requested a given I/O operation. |
| [FltGetRequestorSessionId function](..\fltkernel\nf-fltkernel-fltgetrequestorsessionid.md) | The FltGetRequestorSessionId routine returns the session ID of the process that originally requested the specified I/O operation. |
| [FltGetRoutineAddress function](..\fltkernel\nf-fltkernel-fltgetroutineaddress.md) | The FltGetRoutineAddress routine returns a pointer to a routine specified by the FltMgrRoutineName parameter. |
| [FltGetSectionContext function](..\fltkernel\nf-fltkernel-fltgetsectioncontext.md) | The FltGetSectionContext routine retrieves a section context that was created for a file stream by a specified minifilter driver instance. |
| [FltGetStreamContext function](..\fltkernel\nf-fltkernel-fltgetstreamcontext.md) | The FltGetStreamContext routine retrieves a context that was set for a file stream by a given minifilter driver instance. |
| [FltGetStreamHandleContext function](..\fltkernel\nf-fltkernel-fltgetstreamhandlecontext.md) | The FltGetStreamHandleContext routine retrieves a context that was set for a stream handle by a given minifilter driver instance. |
| [FltGetSwappedBufferMdlAddress function](..\fltkernel\nf-fltkernel-fltgetswappedbuffermdladdress.md) | The FltGetSwappedBufferMdlAddress routine returns the memory descriptor list (MDL) address for a buffer that was swapped in by a minifilter driver. |
| [FltGetTopInstance function](..\fltkernel\nf-fltkernel-fltgettopinstance.md) | The FltGetTopInstance routine returns an opaque instance pointer for the minifilter driver instance that is attached at the top of the instance stack for a given volume. |
| [FltGetTransactionContext function](..\fltkernel\nf-fltkernel-fltgettransactioncontext.md) | The FltGetTransactionContext routine retrieves a context that was set for a transaction by a given minifilter driver. |
| [FltGetTunneledName function](..\fltkernel\nf-fltkernel-fltgettunneledname.md) | The FltGetTunneledName routine retrieves the tunneled name for a file, given the normalized name returned for the file by a previous call to FltGetFileNameInformation, FltGetFileNameInformationUnsafe, or FltGetDestinationFileNameInformation. |
| [FltGetUpperInstance function](..\fltkernel\nf-fltkernel-fltgetupperinstance.md) | The FltGetUpperInstance routine returns an opaque instance pointer for the next higher minifilter driver instance, if there is one, that is attached above a given minifilter driver instance on the same volume. |
| [FltGetVolumeContext function](..\fltkernel\nf-fltkernel-fltgetvolumecontext.md) | The FltGetVolumeContext routine retrieves a context that was set for a volume by a given minifilter driver. |
| [FltGetVolumeFromDeviceObject function](..\fltkernel\nf-fltkernel-fltgetvolumefromdeviceobject.md) | The FltGetVolumeFromDeviceObject routine returns an opaque pointer for the volume represented by a volume device object (VDO). |
| [FltGetVolumeFromFileObject function](..\fltkernel\nf-fltkernel-fltgetvolumefromfileobject.md) | The FltGetVolumeFromFileObject routine returns an opaque pointer for the volume that a given file stream resides on. |
| [FltGetVolumeFromInstance function](..\fltkernel\nf-fltkernel-fltgetvolumefrominstance.md) | The FltGetVolumeFromInstance routine returns an opaque pointer for the volume that a given minifilter driver instance is attached to. |
| [FltGetVolumeFromName function](..\fltkernel\nf-fltkernel-fltgetvolumefromname.md) | The FltGetVolumeFromName routine returns an opaque pointer for the volume whose name matches the value of the VolumeName parameter. |
| [FltGetVolumeGuidName function](..\fltkernel\nf-fltkernel-fltgetvolumeguidname.md) | The FltGetVolumeGuidName routine returns the volume name for a given volume, in volume globally unique identifier (GUID) format. |
| [FltGetVolumeInformation function](..\fltkernel\nf-fltkernel-fltgetvolumeinformation.md) | The FltGetVolumeInformation routine provides information about a given volume. |
| [FltGetVolumeInstanceFromName function](..\fltkernel\nf-fltkernel-fltgetvolumeinstancefromname.md) | The FltGetVolumeInstanceFromName routine returns an opaque instance pointer for the given minifilter driver instance on the given volume. |
| [FltGetVolumeName function](..\fltkernel\nf-fltkernel-fltgetvolumename.md) | The FltGetVolumeName routine gets the volume name for a given volume. |
| [FltGetVolumeProperties function](..\fltkernel\nf-fltkernel-fltgetvolumeproperties.md) | The FltGetVolumeProperties routine returns volume property information for the given volume. |
| [FltInitExtraCreateParameterLookasideList function](..\fltkernel\nf-fltkernel-fltinitextracreateparameterlookasidelist.md) | The FltInitExtraCreateParameterLookasideList routine initializes a paged or non-paged pool lookaside list used for the allocation of one or more extra create parameter context structures (ECPs) of fixed size. |
| [FltInitializeFileLock function](..\fltkernel\nf-fltkernel-fltinitializefilelock.md) | The FltInitializeFileLock routine initializes an opaque FILE_LOCK structure that the caller has allocated from paged pool. |
| [FltInitializeOplock function](..\fltkernel\nf-fltkernel-fltinitializeoplock.md) | The FltInitializeOplock routine initializes an opportunistic lock (oplock) pointer. |
| [FltInitializePushLock function](..\fltkernel\nf-fltkernel-fltinitializepushlock.md) | The FltInitializePushLock routine initializes a push lock variable. |
| [FltInsertExtraCreateParameter function](..\fltkernel\nf-fltkernel-fltinsertextracreateparameter.md) | The FltInsertExtraCreateParameter routine inserts an extra create parameter (ECP) context structure into an ECP list. |
| [FltIs32bitProcess function](..\fltkernel\nf-fltkernel-fltis32bitprocess.md) | The FltIs32bitProcess routine checks whether the originator of the current I/O operation is a 32-bit user-mode application. |
| [FltIsCallbackDataDirty function](..\fltkernel\nf-fltkernel-fltiscallbackdatadirty.md) | The FltIsCallbackDataDirty routine tests the FLTFL_CALLBACK_DATA_DIRTY flag in a callback data structure. |
| [FltIsDirectory function](..\fltkernel\nf-fltkernel-fltisdirectory.md) | A minifilter driver calls the FltIsDirectory routine to determine whether a given file object represents a directory. |
| [FltIsEcpAcknowledged function](..\fltkernel\nf-fltkernel-fltisecpacknowledged.md) | The FltIsEcpAcknowledged routine is used to determine if a given extra create parameter context structure (ECP) has been marked as acknowledged. |
| [FltIsEcpFromUserMode function](..\fltkernel\nf-fltkernel-fltisecpfromusermode.md) | The FltIsEcpFromUserMode routine is used to determine if an extra create parameter context structure (ECP) originated from user mode. |
| [FltIsFltMgrVolumeDeviceObject function](..\fltkernel\nf-fltkernel-fltisfltmgrvolumedeviceobject.md) | The FltIsFltMgrVolumeDeviceObject routine determines whether the given device object belongs to filter manager and if the device object is a volume device object. |
| [FltIsIoCanceled function](..\fltkernel\nf-fltkernel-fltisiocanceled.md) | The FltIsIoCanceled routine checks if an IRP-based operation has been canceled. |
| [FltIsIoRedirectionAllowed function](..\fltkernel\nf-fltkernel-fltisioredirectionallowed.md) | The FltIsIoRedirectionAllowed routine determines whether I/O can be redirected from the specified source filter instance to another specified filter instance. |
| [FltIsIoRedirectionAllowedForOperation function](..\fltkernel\nf-fltkernel-fltisioredirectionallowedforoperation.md) | The FltIsIoRedirectionAllowedForOperation routine determines whether I/O can be redirected from the filter instance associated with the specified FLT_CALLBACK_DATA structure to the specified filter instance. |
| [FltIsOperationSynchronous function](..\fltkernel\nf-fltkernel-fltisoperationsynchronous.md) | The FltIsOperationSynchronous routine determines whether a given callback data structure (FLT_CALLBACK_DATA) represents a synchronous or asynchronous I/O operation. |
| [FltIsVolumeSnapshot function](..\fltkernel\nf-fltkernel-fltisvolumesnapshot.md) | The FltIsVolumeSnapshot routine determines whether a volume or minifilter driver instance is attached to a snapshot volume. |
| [FltIsVolumeWritable function](..\fltkernel\nf-fltkernel-fltisvolumewritable.md) | The FltIsVolumeWritable routine determines whether the disk device that corresponds to a volume or minifilter driver instance is writable. |
| [FltLoadFilter function](..\fltkernel\nf-fltkernel-fltloadfilter.md) | The FltLoadFilter routine dynamically loads a minifilter driver into the currently running system. |
| [FltLockUserBuffer function](..\fltkernel\nf-fltkernel-fltlockuserbuffer.md) | The FltLockUserBuffer routine locks the user buffer for a given I/O operation. |
| [FltNotifyFilterChangeDirectory function](..\fltkernel\nf-fltkernel-fltnotifyfilterchangedirectory.md) | The FltNotifyFilterChangeDirectory routine creates a notify structure for an IRP_MN_NOTIFY_CHANGE_DIRECTORY operation and adds it to the specified notify list. |
| [FltObjectDereference function](..\fltkernel\nf-fltkernel-fltobjectdereference.md) | The FltObjectDereference routine removes a rundown reference from an opaque filter, instance, or volume pointer. |
| [FltObjectReference function](..\fltkernel\nf-fltkernel-fltobjectreference.md) | The FltObjectReference routine adds a rundown reference to an opaque filter, instance, or volume pointer. |
| [FltOpenVolume function](..\fltkernel\nf-fltkernel-fltopenvolume.md) | The FltOpenVolume routine returns a handle and a file object pointer for the file system volume that a given minifilter driver instance is attached to. |
| [FltOplockBreakH function](..\fltkernel\nf-fltkernel-fltoplockbreakh.md) | The FltOplockBreakH routine breaks CACHE_HANDLE_LEVEL opportunistic locks (oplocks). |
| [FltOplockBreakToNone function](..\fltkernel\nf-fltkernel-fltoplockbreaktonone.md) | The FltOplockBreakToNone routine breaks all opportunistic locks (oplocks) immediately without regard for any oplock key. |
| [FltOplockBreakToNoneEx function](..\fltkernel\nf-fltkernel-fltoplockbreaktononeex.md) | The FltOplockBreakToNoneEx routine breaks all opportunistic locks (oplocks) immediately without regard for any oplock key. |
| [FltOplockFsctrl function](..\fltkernel\nf-fltkernel-fltoplockfsctrl.md) | The FltOplockFsctrl routine performs various opportunistic lock (oplock) operations on behalf of a minifilter driver. |
| [FltOplockFsctrlEx function](..\fltkernel\nf-fltkernel-fltoplockfsctrlex.md) | The FltOplockFsctrlEx routine performs various opportunistic lock (oplock) operations on behalf of a minifilter driver. |
| [FltOplockIsFastIoPossible function](..\fltkernel\nf-fltkernel-fltoplockisfastiopossible.md) | The FltOplockIsFastIoPossible routine checks a file's opportunistic lock (oplock) state to determine whether fast I/O can be performed on the file. |
| [FltOplockIsSharedRequest function](..\fltkernel\nf-fltkernel-fltoplockissharedrequest.md) | The FltOplockIsSharedRequest routine determines if a request for an opportunistic lock (oplock) wants a shared oplock. |
| [FltOplockKeysEqual function](..\fltkernel\nf-fltkernel-fltoplockkeysequal.md) | The FltOplockKeysEqual routine compares the opportunistic lock (oplock) keys that are stored in the file object extensions of two file objects. |
| [FltParseFileName function](..\fltkernel\nf-fltkernel-fltparsefilename.md) | FltParseFileName parses the extension, stream, and final component from a file name string. |
| [FltParseFileNameInformation function](..\fltkernel\nf-fltkernel-fltparsefilenameinformation.md) | FltParseFileNameInformation parses the contents of a FLT_FILE_NAME_INFORMATION structure. |
| [FltPerformAsynchronousIo function](..\fltkernel\nf-fltkernel-fltperformasynchronousio.md) | A minifilter driver calls FltPerformAsynchronousIo to initiate an asynchronous I/O operation. |
| [FltPerformSynchronousIo function](..\fltkernel\nf-fltkernel-fltperformsynchronousio.md) | A minifilter driver calls FltPerformSynchronousIo to initiate a synchronous I/O operation after calling FltAllocateCallbackData to allocate a callback data structure for the operation. |
| [FltPrePrepareComplete function](..\fltkernel\nf-fltkernel-fltprepreparecomplete.md) | The FltPrePrepareComplete routine acknowledges a TRANSACTION_NOTIFY_PREPREPARE notification. |
| [FltPrepareComplete function](..\fltkernel\nf-fltkernel-fltpreparecomplete.md) | The FltPrepareComplete routine acknowledges a TRANSACTION_NOTIFY_PREPARE notification. |
| [FltPrepareToReuseEcp function](..\fltkernel\nf-fltkernel-fltpreparetoreuseecp.md) | The FltPrepareToReuseEcp routine resets an extra create parameter (ECP) context structure, which prepares it for reuse. |
| [FltProcessFileLock function](..\fltkernel\nf-fltkernel-fltprocessfilelock.md) | The FltProcessFileLock routine processes and completes a file lock operation. |
| [FltPropagateActivityIdToThread function](..\fltkernel\nf-fltkernel-fltpropagateactivityidtothread.md) | The FltPropagateActivityIdToThread routine associates the activity ID from the IRP in the minifilter's callback data with the current thread. |
| [FltPurgeFileNameInformationCache function](..\fltkernel\nf-fltkernel-fltpurgefilenameinformationcache.md) | FltPurgeFileNameInformationCache purges from the Filter Manager's name cache all file name information structures that were generated from names provided by the given minifilter driver instance. |
| [FltQueryDirectoryFile function](..\fltkernel\nf-fltkernel-fltquerydirectoryfile.md) | The FltQueryDirectoryFile routine returns various kinds of information about files in the directory specified by a given file object. |
| [FltQueryEaFile function](..\fltkernel\nf-fltkernel-fltqueryeafile.md) | FltQueryEaFile returns information about extended-attribute (EA) values for a file. |
| [FltQueryInformationFile function](..\fltkernel\nf-fltkernel-fltqueryinformationfile.md) | FltQueryInformationFile retrieves information for a given file. |
| [FltQueryQuotaInformationFile function](..\fltkernel\nf-fltkernel-fltqueryquotainformationfile.md) | The FltQueryQuotaInformationFile routine retrieves quota entries associated with a file object. |
| [FltQuerySecurityObject function](..\fltkernel\nf-fltkernel-fltquerysecurityobject.md) | FltQuerySecurityObject retrieves a copy of an object's security descriptor. |
| [FltQueryVolumeInformation function](..\fltkernel\nf-fltkernel-fltqueryvolumeinformation.md) | The FltQueryVolumeInformation routine retrieves information about the volume that the given instance is attached to. |
| [FltQueryVolumeInformationFile function](..\fltkernel\nf-fltkernel-fltqueryvolumeinformationfile.md) | FltQueryVolumeInformationFile retrieves volume information for a given file, directory, storage device, or volume. |
| [FltQueueDeferredIoWorkItem function](..\fltkernel\nf-fltkernel-fltqueuedeferredioworkitem.md) | The FltQueueDeferredIoWorkItem routine posts an IRP-based I/O operation to a work queue. |
| [FltQueueGenericWorkItem function](..\fltkernel\nf-fltkernel-fltqueuegenericworkitem.md) | FltQueueGenericWorkItem posts a work item that is not associated with a specific I/O operation to a work queue. |
| [FltReadFile function](..\fltkernel\nf-fltkernel-fltreadfile.md) | FltReadFile reads data from an open file, stream, or device. |
| [FltReadFileEx function](..\fltkernel\nf-fltkernel-fltreadfileex.md) | FltReadFileEx reads data from an open file, stream, or device. This function extends FltReadFile to allow the optional use of an MDL for read data instead of a mapped buffer address. |
| [FltReferenceContext function](..\fltkernel\nf-fltkernel-fltreferencecontext.md) | FltReferenceContext increments the reference count on a context structure. |
| [FltReferenceFileNameInformation function](..\fltkernel\nf-fltkernel-fltreferencefilenameinformation.md) | FltReferenceFileNameInformation increments the reference count on a file name information structure. |
| [FltRegisterFilter function](..\fltkernel\nf-fltkernel-fltregisterfilter.md) | FltRegisterFilter registers a minifilter driver. |
| [FltRegisterForDataScan function](..\fltkernel\nf-fltkernel-fltregisterfordatascan.md) | The FltRegisterForDataScan routine enables data scanning for the volume attached to the minifilter instance. |
| [FltReissueSynchronousIo function](..\fltkernel\nf-fltkernel-fltreissuesynchronousio.md) | FltReissueSynchronousIo initiates a new synchronous I/O operation that uses the parameters from a previously synchronized I/O operation. |
| [FltReleaseContext function](..\fltkernel\nf-fltkernel-fltreleasecontext.md) | FltReleaseContext decrements the reference count on a context. |
| [FltReleaseContexts function](..\fltkernel\nf-fltkernel-fltreleasecontexts.md) | FltReleaseContexts releases each context in a given FLT_RELATED_CONTEXTS structure. |
| [FltReleaseContextsEx function](..\fltkernel\nf-fltkernel-fltreleasecontextsex.md) | FltReleaseContextsEx releases each context in a given FLT_RELATED_CONTEXTS_EX structure. |
| [FltReleaseFileNameInformation function](..\fltkernel\nf-fltkernel-fltreleasefilenameinformation.md) | FltReleaseFileNameInformation releases a file name information structure. |
| [FltRemoveExtraCreateParameter function](..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md) | The FltRemoveExtraCreateParameter routine searches an ECP list for an ECP context structure and, if found, detaches it from the ECP list. |
| [FltRemoveOpenReparseEntry function](..\fltkernel\nf-fltkernel-fltremoveopenreparseentry.md) | This routine removes an OPEN_REPARSE_LIST_ENTRY structure (added by FltAddOpenReparseEntry) from a create operation. |
| [FltRequestOperationStatusCallback function](..\fltkernel\nf-fltkernel-fltrequestoperationstatuscallback.md) | FltRequestOperationStatusCallback returns status information for the given I/O operation. |
| [FltRetainSwappedBufferMdlAddress function](..\fltkernel\nf-fltkernel-fltretainswappedbuffermdladdress.md) | FltRetainSwappedBufferMdlAddress prevents the Filter Manager from freeing the memory descriptor list (MDL) for a buffer that was swapped in by a minifilter driver. |
| [FltRetrieveIoPriorityInfo function](..\fltkernel\nf-fltkernel-fltretrieveiopriorityinfo.md) | The FltRetrieveIoPriorityInfo routine is used by a minifilter driver to retrieve priority information from a thread. |
| [FltReuseCallbackData function](..\fltkernel\nf-fltkernel-fltreusecallbackdata.md) | The FltReuseCallbackData routine reinitializes a callback data structure so that it can be reused. |
| [FltRollbackComplete function](..\fltkernel\nf-fltkernel-fltrollbackcomplete.md) | The FltRollbackComplete routine acknowledges a TRANSACTION_NOTIFY_ROLLBACK notification. |
| [FltRollbackEnlistment function](..\fltkernel\nf-fltkernel-fltrollbackenlistment.md) | The FltRollbackEnlistment routine rolls back or aborts a transaction on behalf of a minifilter driver. |
| [FltSendMessage function](..\fltkernel\nf-fltkernel-fltsendmessage.md) | FltSendMessage sends a message to a waiting user-mode application on behalf of a minifilter driver or a minifilter driver instance. |
| [FltSetActivityIdCallbackData function](..\fltkernel\nf-fltkernel-fltsetactivityidcallbackdata.md) | The FltSetActivityIdCallbackData routine sets the a activity ID for an IRP in a minifilter's callback data. |
| [FltSetCallbackDataDirty function](..\fltkernel\nf-fltkernel-fltsetcallbackdatadirty.md) | A minifilter driver's preoperation or postoperation callback routine calls FltSetCallbackDataDirty to indicate that it has modified the contents of the callback data structure. |
| [FltSetCancelCompletion function](..\fltkernel\nf-fltkernel-fltsetcancelcompletion.md) | A minifilter driver calls FltSetCancelCompletion to specify a cancel routine to be called if a given I/O operation is canceled. |
| [FltSetEaFile function](..\fltkernel\nf-fltkernel-fltseteafile.md) | FltSetEaFile sets extended-attribute (EA) values for a file. |
| [FltSetEcpListIntoCallbackData function](..\fltkernel\nf-fltkernel-fltsetecplistintocallbackdata.md) | The FltSetEcpListIntoCallbackData routine attaches an extra create parameter context structure (ECP) list to a create operation callback-data object. |
| [FltSetFileContext function](..\fltkernel\nf-fltkernel-fltsetfilecontext.md) | The FltSetFileContext routine sets a context for a file. |
| [FltSetInformationFile function](..\fltkernel\nf-fltkernel-fltsetinformationfile.md) | FltSetInformationFile sets information for a given file. |
| [FltSetInstanceContext function](..\fltkernel\nf-fltkernel-fltsetinstancecontext.md) | FltSetInstanceContext sets a context for a minifilter driver instance. |
| [FltSetIoPriorityHintIntoCallbackData function](..\fltkernel\nf-fltkernel-fltsetiopriorityhintintocallbackdata.md) | The FltSetIoPriorityHintIntoCallbackData routine is used by a minifilter driver to set the I/O priority information in callback data. |
| [FltSetIoPriorityHintIntoFileObject function](..\fltkernel\nf-fltkernel-fltsetiopriorityhintintofileobject.md) | The FltSetIoPriorityHintIntoFileObject routine is used by a minifilter driver to set the I/O priority information in a file object. |
| [FltSetIoPriorityHintIntoThread function](..\fltkernel\nf-fltkernel-fltsetiopriorityhintintothread.md) | The FltSetIoPriorityHintIntoThread routine is used by a minifilter driver to set the IO priority information in a thread. |
| [FltSetQuotaInformationFile function](..\fltkernel\nf-fltkernel-fltsetquotainformationfile.md) | The FltSetQuotaInformationFile routine modifies quota entries for a file object. |
| [FltSetSecurityObject function](..\fltkernel\nf-fltkernel-fltsetsecurityobject.md) | FltSetSecurityObject sets an object's security state. |
| [FltSetStreamContext function](..\fltkernel\nf-fltkernel-fltsetstreamcontext.md) | The FltSetStreamContext routine sets a context for a file stream. |
| [FltSetStreamHandleContext function](..\fltkernel\nf-fltkernel-fltsetstreamhandlecontext.md) | The FltSetStreamHandleContext routine sets a context for a stream handle. |
| [FltSetTransactionContext function](..\fltkernel\nf-fltkernel-fltsettransactioncontext.md) | The FltSetTransactionContext routine sets a context on a transaction. |
| [FltSetVolumeContext function](..\fltkernel\nf-fltkernel-fltsetvolumecontext.md) | FltSetVolumeContext sets a context for a volume. |
| [FltSetVolumeInformation function](..\fltkernel\nf-fltkernel-fltsetvolumeinformation.md) | FltSetVolumeInformation changes various kinds of information about the volume that the given instance is attached to. |
| [FltStartFiltering function](..\fltkernel\nf-fltkernel-fltstartfiltering.md) | FltStartFiltering starts filtering for a registered minifilter driver. |
| [FltSupportsFileContexts function](..\fltkernel\nf-fltkernel-fltsupportsfilecontexts.md) | The FltSupportsFileContexts routine determines whether the file system supports file contexts for a given file. |
| [FltSupportsFileContextsEx function](..\fltkernel\nf-fltkernel-fltsupportsfilecontextsex.md) | The FltSupportsFileContextsEx routine determines whether the file system or the filter manager support file contexts for a given file. |
| [FltSupportsStreamContexts function](..\fltkernel\nf-fltkernel-fltsupportsstreamcontexts.md) | FltSupportsStreamContexts determines whether stream contexts are supported on a given file object. |
| [FltSupportsStreamHandleContexts function](..\fltkernel\nf-fltkernel-fltsupportsstreamhandlecontexts.md) | FltSupportsStreamHandleContexts determines whether stream handle contexts are supported on a given file object. |
| [FltTagFile function](..\fltkernel\nf-fltkernel-flttagfile.md) | FltTagFile sets a reparse tag on a file or directory. |
| [FltUninitializeFileLock function](..\fltkernel\nf-fltkernel-fltuninitializefilelock.md) | The FltUninitializeFileLock routine uninitializes a FILE_LOCK structure. |
| [FltUninitializeOplock function](..\fltkernel\nf-fltkernel-fltuninitializeoplock.md) | FltUninitializeOplock uninitializes an opportunistic lock (oplock) pointer. |
| [FltUnloadFilter function](..\fltkernel\nf-fltkernel-fltunloadfilter.md) | A minifilter driver that has loaded a supporting minifilter driver by calling FltLoadFilter can unload the minifilter driver by calling FltUnloadFilter. |
| [FltUnregisterFilter function](..\fltkernel\nf-fltkernel-fltunregisterfilter.md) | A registered minifilter driver calls FltUnregisterFilter to unregister itself so that the Filter Manager no longer calls it to process I/O operations. |
| [FltUntagFile function](..\fltkernel\nf-fltkernel-fltuntagfile.md) | FltUntagFile removes a reparse point from a file or directory. |
| [FltWriteFile function](..\fltkernel\nf-fltkernel-fltwritefile.md) | FltWriteFile is used to write data to an open file, stream, or device. |
| [FltWriteFileEx function](..\fltkernel\nf-fltkernel-fltwritefileex.md) | FltWriteFileEx is used to write data to an open file, stream, or device. This function extends FltWriteFile to allow the optional use of an MDL for write data instead of a mapped buffer address. |
| [FsRtlAcknowledgeEcp function](..\ntifs\nf-ntifs-fsrtlacknowledgeecp.md) | The FsRtlAcknowledgeEcp routine marks an extra create parameter (ECP) context structure as acknowledged. |
| [FsRtlAcquireFileExclusive function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlacquirefileexclusive.md) | Reserved for system use. |
| [FsRtlAddLargeMcbEntry function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtladdlargemcbentry~r3.md) | The FsRtlAddLargeMcbEntry routine adds a new mapping to an existing map control block (MCB). |
| [FsRtlAddMcbEntry function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtladdmcbentry~r3.md) | Obsolete. |
| [FsRtlAddToTunnelCache function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtladdtotunnelcache~r6.md) | The FsRtlAddToTunnelCache routine caches a file name that is removed from a directory when a file is renamed or deleted. |
| [FsRtlAllocateExtraCreateParameter function](..\ntifs\nf-ntifs-fsrtlallocateextracreateparameter.md) | The FsRtlAllocateExtraCreateParameter routine allocates memory for a user-defined extra create parameter (ECP) context structure and generates a pointer to that structure. |
| [FsRtlAllocateExtraCreateParameterFromLookasideList function](..\ntifs\nf-ntifs-fsrtlallocateextracreateparameterfromlookasidelist.md) | The FsRtlAllocateExtraCreateParameterFromLookasideList routine allocates memory pool from a given lookaside list for an extra create parameter (ECP) context structure, and generates a pointer to that structure. |
| [FsRtlAllocateExtraCreateParameterList function](..\ntifs\nf-ntifs-fsrtlallocateextracreateparameterlist.md) | The FsRtlAllocateExtraCreateParameterList routine allocates paged pool memory for an ECP_LIST structure and generates a pointer to that structure. |
| [FsRtlAllocateFileLock function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock~r1.md) | The FsRtlAllocateFileLock routine allocates and initializes a new FILE_LOCK structure. |
| [FsRtlAllocateResource function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocateresource.md) | Obsolete. |
| [FsRtlAreNamesEqual function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlarenamesequal~r3.md) | The FsRtlAreNamesEqual routine determines whether two Unicode strings are equal. |
| [FsRtlAreThereCurrentOrInProgressFileLocks function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlaretherecurrentorinprogressfilelocks.md) | TheFsRtlAreThereCurrentOrInProgressFileLocks routine determines if there are byte range locks assigned to a file or any lock operations in progress for that file. |
| [FsRtlAreThereWaitingFileLocks function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlaretherewaitingfilelocks.md) | The FsRtlAreThereWaitingFileLocks routine checks a file lock queue for any waiting file locks. |
| [FsRtlAreVolumeStartupApplicationsComplete function](..\ntifs\nf-ntifs-fsrtlarevolumestartupapplicationscomplete.md) | The FsRtlAreVolumeStartupApplicationsComplete function determines whether volume startup applications have completed processing. |
| [FsRtlBalanceReads function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlbalancereads.md) | The FsRtlBalanceReads routine signals to a fault-tolerant disk driver that it is now safe to start balancing reads from a mirrored drive. |
| [FsRtlCancellableWaitForMultipleObjects function](..\ntifs\nf-ntifs-fsrtlcancellablewaitformultipleobjects.md) | The FsRtlCancellableWaitForMultipleObjects routine executes a cancelable wait operation (a wait that can be terminated) on one or more dispatcher objects. |
| [FsRtlCancellableWaitForSingleObject function](..\ntifs\nf-ntifs-fsrtlcancellablewaitforsingleobject.md) | The FsRtlCancellableWaitForSingleObject routine executes a cancelable wait operation (a wait that can be terminated) on a dispatcher object. |
| [FsRtlChangeBackingFileObject function](..\ntifs\nf-ntifs-fsrtlchangebackingfileobject.md) | The FsRtlChangeBackingFileObject routine replaces the current file object with a new file object. |
| [FsRtlCheckLockForOplockRequest function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlchecklockforoplockrequest~r1.md) | The FsRtlCheckLockForOplockRequest routine checks for locks within the allocation size of a file. The file lock object is checked for the presence of byte range locks that would prevent an oplock request from being granted. |
| [FsRtlCheckLockForReadAccess function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlchecklockforreadaccess~r1.md) | The FsRtlCheckLockForReadAccess routine determines whether the process associated with a given IRP has read access to a locked region of a file. |
| [FsRtlCheckLockForWriteAccess function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlchecklockforwriteaccess~r1.md) | The FsRtlCheckLockForWriteAccess routine determines whether the process associated with a given IRP has write access to a locked region of a file. |
| [FsRtlCheckOplock function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcheckoplock~r4.md) | The FsRtlCheckOplock routine synchronizes the IRP for a file I/O operation with the file's current opportunistic lock (oplock) state. |
| [FsRtlCheckOplockEx function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcheckoplockex~r5.md) | The FsRtlCheckOplockEx routine synchronizes the IRP for a file I/O operation with the current opportunistic lock (oplock) state of the file. |
| [FsRtlCheckUpperOplock function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcheckupperoplock~r5.md) | The FsRtlCheckUpperOplock routine provides opportunistic lock (oplock) checking in secondary, or layered, file systems when the oplocks they hold change state. |
| [FsRtlCopyRead function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopyread~r7.md) | The FsRtlCopyRead routine copies data from a cached file to a user buffer. |
| [FsRtlCopyWrite function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopywrite~r7.md) | The FsRtlCopyWrite routine copies data from a user buffer to a cached file. |
| [FsRtlCreateSectionForDataScan function](..\ntifs\nf-ntifs-fsrtlcreatesectionfordatascan.md) | The FsRtlCreateSectionForDataScan routine creates a section object. |
| [FsRtlCurrentBatchOplock function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcurrentbatchoplock.md) | A file system or filter driver calls FsRtlCurrentBatchOplock to determine whether there are any batch or filter opportunistic locks (oplocks) on a file. |
| [FsRtlCurrentOplock function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcurrentoplock.md) | A file system or filter driver calls FsRtlCurrentOplock to determine whether there are any opportunistic locks (oplocks) on a file. |
| [FsRtlCurrentOplockH function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcurrentoplockh.md) | A file system or filter driver calls FsRtlCurrentOplockH to determine whether there are any CACHE_HANDLE_LEVEL opportunistic locks (oplocks) on a file. |
| [FsRtlDeleteExtraCreateParameterLookasideList function](..\ntifs\nf-ntifs-fsrtldeleteextracreateparameterlookasidelist.md) | The FsRtlDeleteExtraCreateParameterLookasideList routine frees an extra create parameter (ECP) lookaside list. |
| [FsRtlDeleteKeyFromTunnelCache function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtldeletekeyfromtunnelcache~r1.md) | The FsRtlDeleteKeyFromTunnelCache routine deletes any tunnel cache entries for files in a directory that is being deleted. |
| [FsRtlDeleteTunnelCache function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtldeletetunnelcache.md) | The FsRtlDeleteTunnelCache routine deletes a tunnel cache. |
| [FsRtlDeregisterUncProvider function](..\ntifs\nf-ntifs-fsrtlderegisteruncprovider.md) | The FsRtlDeregisterUncProvider routine deregisters a redirector that was registered as a Universal Naming Convention (UNC) provider with the multiple UNC provider (MUP). |
| [FsRtlDissectDbcs function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtldissectdbcs~r2.md) | Given an ANSI or double-byte character set (DBCS) pathname string, the FsRtlDissectDbcs routine returns two strings |
| [FsRtlDissectName function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtldissectname~r2.md) | Given a Unicode pathname string, the FsRtlDissectName routine returns two strings, one containing the first file name found in the string, the other containing the remaining unparsed portion of the pathname string. |
| [FsRtlDoesDbcsContainWildCards function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtldoesdbcscontainwildcards.md) | The FsRtlDoesDbcsContainWildCards routine determines whether an ANSI or double-byte character set (DBCS) string contains wildcard characters. |
| [FsRtlDoesNameContainWildCards function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtldoesnamecontainwildcards.md) | The FsRtlDoesNameContainWildCards routine determines whether a Unicode string contains wildcard characters. |
| [FsRtlFastCheckLockForRead function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastchecklockforread~r5.md) | The FsRtlFastCheckLockForRead routine determines whether the specified process has read access to a locked byte range of a file. |
| [FsRtlFastCheckLockForWrite function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastchecklockforwrite~r5.md) | The FsRtlFastCheckLockForWrite routine determines whether the specified process has write access to a locked byte range of a file. |
| [FsRtlFastUnlockAll function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastunlockall~r3.md) | The FsRtlFastUnlockAll routine releases all byte-range locks that were acquired by the specified process for a file. |
| [FsRtlFastUnlockAllByKey function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastunlockallbykey~r4.md) | The FsRtlFastUnlockAllByKey routine releases all byte-range locks that were acquired by the specified process, with the specified key value, for a file. |
| [FsRtlFastUnlockSingle function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfastunlocksingle~r7.md) | The FsRtlFastUnlockSingle routine releases a byte-range lock that was acquired by the specified process, with the specified key value, file offset, and length, for a file. |
| [FsRtlFindExtraCreateParameter function](..\ntifs\nf-ntifs-fsrtlfindextracreateparameter.md) | The FsRtlFindExtraCreateParameter routine searches a given ECP list for an ECP context structure of a given type and returns a pointer to this structure if it is found. |
| [FsRtlFindInTunnelCache function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfindintunnelcache~r6.md) | The FsRtlFindInTunnelCache routine searches for a matching entry in the tunnel cache that matches the specified name. |
| [FsRtlFreeExtraCreateParameter function](..\ntifs\nf-ntifs-fsrtlfreeextracreateparameter.md) | The FsRtlFreeExtraCreateParameter routine frees the memory for an ECP context structure. |
| [FsRtlFreeExtraCreateParameterList function](..\ntifs\nf-ntifs-fsrtlfreeextracreateparameterlist.md) | The FsRtlFreeExtraCreateParameterList routine frees an extra create parameter (ECP) list structure. |
| [FsRtlFreeFileLock function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlfreefilelock.md) | The FsRtlFreeFileLock routine uninitializes and frees a file lock structure. |
| [FsRtlGetEcpListFromIrp function](..\ntifs\nf-ntifs-fsrtlgetecplistfromirp.md) | The FsRtlGetEcpListFromIrp routine returns a pointer to an extra create parameter (ECP) context structure list that is associated with a given IRP_MJ_CREATE operation. |
| [FsRtlGetFileSize function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetfilesize~r1.md) | The FsRtlGetFileSize routine is used to get the size of a file. |
| [FsRtlGetNextExtraCreateParameter function](..\ntifs\nf-ntifs-fsrtlgetnextextracreateparameter.md) | The FsRtlGetNextExtraCreateParameter routine returns a pointer to the next (or first) extra create parameter (ECP) context structure in a given ECP list. |
| [FsRtlGetNextFileLock function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextfilelock~r1.md) | The FsRtlGetNextFileLock routine is used to enumerate the byte-range locks that currently exist for a specified file. |
| [FsRtlGetNextLargeMcbEntry function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextlargemcbentry~r4.md) | The FsRtlGetNextLargeMcbEntry routine retrieves a mapping run from a map control block (MCB). |
| [FsRtlGetNextMcbEntry function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextmcbentry~r4.md) | Obsolete. |
| [FsRtlGetSectorSizeInformation function](..\ntifs\nf-ntifs-fsrtlgetsectorsizeinformation.md) | The FsRtlGetSectorSizeInformation routine retrieves the physical and logical sector size information for a storage volume. |
| [FsRtlGetSupportedFeatures function](..\ntifs\nf-ntifs-fsrtlgetsupportedfeatures.md) | The FsRtlGetSupportedFeatures routine returns the supported features of a volume attached to the specified device object. |
| [FsRtlIncrementCcFastMdlReadWait function](..\ntifs\nf-ntifs-fsrtlincrementccfastmdlreadwait.md) | The FsRtlIncrementCcFastMdlReadWait routine increments the cache manager's CcFastMdlReadWait performance counter member in a processor control block (PRCB) object. |
| [FsRtlIncrementCcFastReadNoWait function](..\ntifs\nf-ntifs-fsrtlincrementccfastreadnowait.md) | The FsRtlIncrementCcFastReadNoWait routine increments the CcFastReadNoWait performance counter in a per processor control block of cache manager system counters. |
| [FsRtlIncrementCcFastReadNotPossible function](..\ntifs\nf-ntifs-fsrtlincrementccfastreadnotpossible.md) | The FsRtlIncrementCcFastReadNotPossible routine increments the CcFastReadNotPossible performance counter in a per processor control block of cache manager system counters. |
| [FsRtlIncrementCcFastReadResourceMiss function](..\ntifs\nf-ntifs-fsrtlincrementccfastreadresourcemiss.md) | The FsRtlIncrementCcFastReadResourceMiss routine increments the CcFastReadNotPossible performance counter in a per processor control block of cache manager system counters. |
| [FsRtlIncrementCcFastReadWait function](..\ntifs\nf-ntifs-fsrtlincrementccfastreadwait.md) | The FsRtlIncrementCcFastReadWait routine increments the CcFastReadWait performance counter in a per processor control block of cache manager system counters. |
| [FsRtlInitExtraCreateParameterLookasideList function](..\ntifs\nf-ntifs-fsrtlinitextracreateparameterlookasidelist.md) | The FsRtlInitExtraCreateParameterLookasideList routine initializes a paged or nonpaged pool lookaside list used for the allocation of one or more extra create parameter context structures (ECPs) of fixed size. |
| [FsRtlInitializeExtraCreateParameter function](..\ntifs\nf-ntifs-fsrtlinitializeextracreateparameter.md) | The FsRtlInitializeExtraCreateParameter routine initializes an extra create parameter (ECP) context structure. |
| [FsRtlInitializeExtraCreateParameterList function](..\ntifs\nf-ntifs-fsrtlinitializeextracreateparameterlist.md) | The FsRtlInitializeExtraCreateParameterList routine initializes an extra create parameter (ECP) context structure list. |
| [FsRtlInitializeFileLock function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock~r2.md) | The FsRtlInitializeFileLock routine initializes a FILE_LOCK structure. |
| [FsRtlInitializeLargeMcb function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializelargemcb~r1.md) | The FsRtlInitializeLargeMcb routine initializes a map control block (MCB) structure. |
| [FsRtlInitializeMcb function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializemcb~r1.md) | Obsolete. |
| [FsRtlInitializeOplock function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md) | FsRtlInitializeOplock initializes an opportunistic lock (oplock) pointer. |
| [FsRtlInitializeTunnelCache function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializetunnelcache.md) | The FsRtlInitializeTunnelCache routine initializes a new tunnel cache for a volume. |
| [FsRtlInsertExtraCreateParameter function](..\ntifs\nf-ntifs-fsrtlinsertextracreateparameter.md) | The FsRtlInsertExtraCreateParameter routine inserts an extra create parameter (ECP) context structure into an ECP list. |
| [FsRtlInsertPerFileContext function](..\ntifs\nf-ntifs-fsrtlinsertperfilecontext.md) | The FsRtlInsertPerFileContext routine associates a FSRTL_PER_FILE_CONTEXT object with a driver-specified context object for a file. |
| [FsRtlInsertPerFileObjectContext function](..\ntifs\nf-ntifs-fsrtlinsertperfileobjectcontext.md) | For a &#0034;legacy&#0034; file system filter driver, the FsRtlInsertPerFileObjectContext function associates context information with a file object. |
| [FsRtlInsertPerStreamContext function](..\ntifs\nf-ntifs-fsrtlinsertperstreamcontext.md) | The FsRtlInsertPerStreamContext routine associates a file system filter driver's per-stream context structure with a file stream. |
| [FsRtlIsDaxVolume function](..\ntifs\nf-ntifs-fsrtlisdaxvolume.md) | This routine queries if the specified file is on a direct access (DAX) volume. |
| [FsRtlIsDbcsInExpression function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlisdbcsinexpression~r1.md) | The FsRtlIsDbcsInExpression routine determines whether an ANSI or double-byte character set (DBCS) string matches the specified pattern. |
| [FsRtlIsEcpAcknowledged function](..\ntifs\nf-ntifs-fsrtlisecpacknowledged.md) | The FsRtlIsEcpAcknowledged routine is used to determine if a given extra create parameter (ECP) context structure has been marked as acknowledged. |
| [FsRtlIsEcpFromUserMode function](..\ntifs\nf-ntifs-fsrtlisecpfromusermode.md) | The FsRtlIsEcpFromUserMode routine determines whether an extra create parameter (ECP) context structure originated from user mode. |
| [FsRtlIsFatDbcsLegal function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlisfatdbcslegal~r3.md) | The FsRtlIsFatDbcsLegal routine determines whether the specified ANSI or double-byte character set (DBCS) string is a legal FAT file name. |
| [FsRtlIsHpfsDbcsLegal function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlishpfsdbcslegal~r3.md) | The FsRtlIsHpfsDbcsLegal routine determines whether the specified ANSI or double-byte character set (DBCS) string is a legal HPFS file name. |
| [FsRtlIsNameInExpression function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlisnameinexpression~r3.md) | The FsRtlIsNameInExpression routine determines whether a Unicode string matches the specified pattern. |
| [FsRtlIsNtstatusExpected function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlisntstatusexpected.md) | The FsRtlIsNtstatusExpected routine determines whether the specified exception is handled by the exception filter. |
| [FsRtlIsPagingFile function](..\ntifs\nf-ntifs-fsrtlispagingfile.md) | The FsRtlIsPagingFile routine determines whether a given file is a paging file. |
| [FsRtlIsSystemPagingFile function](..\ntifs\nf-ntifs-fsrtlissystempagingfile.md) | The FsRtlIsSystemPagingFile routine determines whether a given file is currently a system paging file. |
| [FsRtlIsTotalDeviceFailure function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlistotaldevicefailure.md) | The FsRtlIsTotalDeviceFailure routine determines whether a media or other hardware failure has occurred. |
| [FsRtlIssueDeviceIoControl function](..\ntifs\nf-ntifs-fsrtlissuedeviceiocontrol.md) | The FsRtlIssueDeviceIoControl routine sends a synchronous device I/O control request to a target device object. |
| [FsRtlLogCcFlushError function](..\ntifs\nf-ntifs-fsrtllogccflusherror.md) | The FsRtlLogCcFlushError routine logs a lost delayed-write error and displays a dialog box to the user. |
| [FsRtlLookupLargeMcbEntry function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplargemcbentry~r6.md) | Given a virtual block number (VBN) and a map control block (MCB), the FsRtlLookupLargeMcbEntry routine searches the MCB for mapping information corresponding to the specified VBN. |
| [FsRtlLookupLastLargeMcbEntry function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentry~r2.md) | The FsRtlLookupLastLargeMcbEntry routine retrieves the last mapping entry stored in the map control block (MCB). |
| [FsRtlLookupLastLargeMcbEntryAndIndex function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastlargemcbentryandindex~r3.md) | The FsRtlLookupLastLargeMcbEntryAndIndex routine retrieves the last mapping entry stored in a given map control block (MCB). |
| [FsRtlLookupLastMcbEntry function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookuplastmcbentry~r2.md) | Obsolete. |
| [FsRtlLookupMcbEntry function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtllookupmcbentry~r4.md) | Obsolete. |
| [FsRtlLookupPerFileContext function](..\ntifs\nf-ntifs-fsrtllookupperfilecontext.md) | The FsRtlLookupPerFileContext routine returns a pointer to a FSRTL_PER_FILE_CONTEXT object that is associated with a specified file. |
| [FsRtlLookupPerFileObjectContext function](..\ntifs\nf-ntifs-fsrtllookupperfileobjectcontext.md) | For a &#0034;legacy&#0034; file system filter driver, the FsRtlLookupPerFileObjectContext function retrieves context information previously associated with a file object. |
| [FsRtlLookupPerStreamContextInternal function](..\ntifs\nf-ntifs-fsrtllookupperstreamcontextinternal.md) | Reserved for system use. |
| [FsRtlMdlReadCompleteDev function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlmdlreadcompletedev~r2.md) | The FltFastIoMdlReadComplete routine completes the read operation that the FltFastIoMdlRead routine initiated. |
| [FsRtlMdlReadDev function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlmdlreaddev~r6.md) | The FltFastIoMdlRead routine returns a memory descriptor list (MDL) that points directly to the specified byte range in the file cache. |
| [FsRtlMdlReadEx function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlmdlreadex~r5.md) | The FsRtlMdlReadEx routine performs a fast cached MDL read. If the requested data is not cached, the routine reverts to an IRP based MDL read operation. |
| [FsRtlMdlWriteCompleteDev function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlmdlwritecompletedev~r3.md) | The FltFastIoMdlWriteComplete routine frees the resources that FltFastIoPrepareMdlWrite allocated. |
| [FsRtlMupGetProviderIdFromName function](..\ntifs\nf-ntifs-fsrtlmupgetprovideridfromname.md) | The FsRtlMupGetProviderIdFromName routine gets the provider identifier of a network redirector that is registered with the multiple UNC provider (MUP) from the device name of the network redirector. |
| [FsRtlMupGetProviderInfoFromFileObject function](..\ntifs\nf-ntifs-fsrtlmupgetproviderinfofromfileobject.md) | The FsRtlMupGetProviderInfoFromFileObject routine gets information about a network redirector that is registered with the multiple UNC provider (MUP) from a file object for a file that is located on a remote file system. |
| [FsRtlNormalizeNtstatus function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnormalizentstatus~r1.md) | The FsRtlNormalizeNtstatus routine translates an arbitrary exception into a status value that is handled by the exception filter. |
| [FsRtlNotifyCleanup function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifycleanup~r2.md) | When the last handle to a file object is released, the FsRtlNotifyCleanup routine removes the file object's notify structure, if present, from the specified notify list. |
| [FsRtlNotifyCleanupAll function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifycleanupall~r1.md) | The FsRtlNotifyCleanupAll routine removes all members of the specified notification list. |
| [FsRtlNotifyFilterChangeDirectory function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterchangedirectory~r10.md) | The FsRtlNotifyFilterChangeDirectory routine creates a notify structure for an IRP_MN_NOTIFY_CHANGE_DIRECTORY request and adds it to the specified notify list. |
| [FsRtlNotifyFilterReportChange function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterreportchange~r9.md) | FsRtlNotifyFilterReportChange completes IRP_MN_NOTIFY_CHANGE_DIRECTORY requests that are pending in the specified notify list. |
| [FsRtlNotifyFullChangeDirectory function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullchangedirectory~r9.md) | The FsRtlNotifyFullChangeDirectory routine creates a notify structure for a notification request and adds it to the specified notify list. |
| [FsRtlNotifyFullReportChange function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullreportchange~r8.md) | The FsRtlNotifyFullReportChange routine completes pending notify change IRPs. |
| [FsRtlNotifyInitializeSync function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyinitializesync.md) | The FsRtlNotifyInitializeSync routine allocates and initializes a synchronization object for a notify list. |
| [FsRtlNotifyUninitializeSync function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyuninitializesync.md) | The FsRtlNotifyUninitializeSync routine deallocates the synchronization object for a notify list. |
| [FsRtlNotifyVolumeEvent function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyvolumeevent~r1.md) | The FsRtlNotifyVolumeEvent routine notifies any registered applications that a volume event is occurring. |
| [FsRtlNotifyVolumeEventEx function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyvolumeeventex~r2.md) | The FsRtlNotifyVolumeEventEx routine notifies any registered applications that a volume event is occurring. Volume events include the volume being locked, unlocked, mounted, or made read-only. |
| [FsRtlNumberOfRunsInLargeMcb function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnumberofrunsinlargemcb.md) | The FsRtlNumberOfRunsInLargeMcb routine returns the number of runs in a map control block (MCB). |
| [FsRtlNumberOfRunsInMcb function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnumberofrunsinmcb.md) | Obsolete. |
| [FsRtlOplockBreakH function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockbreakh~r5.md) | The FsRtlOplockBreakH routine breaks CACHE_HANDLE_LEVEL opportunistic locks (oplocks). |
| [FsRtlOplockBreakToNone function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockbreaktonone~r5.md) | Obsolete. |
| [FsRtlOplockBreakToNoneEx function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockbreaktononeex~r5.md) | The FsRtlOplockBreakToNoneEx routine breaks all opportunistic locks (oplocks) immediately without regard for any oplock key. |
| [FsRtlOplockFsctrl function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockfsctrl~r2.md) | FsRtlOplockFsctrl performs various opportunistic lock (oplock) operations on behalf of a file system or filter driver. |
| [FsRtlOplockFsctrlEx function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockfsctrlex~r3.md) | The FsRtlOplockFsctrlEx routine performs various opportunistic lock (oplock) operations on behalf of a file system or filter driver. |
| [FsRtlOplockIsFastIoPossible function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockisfastiopossible.md) | FsRtlOplockIsFastIoPossible checks a file's opportunistic lock (oplock) state to determine whether fast I/O can be performed on the file. |
| [FsRtlOplockIsSharedRequest function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockissharedrequest.md) | The FsRtlOplockIsSharedRequest routine determines if a request for an opportunistic lock (oplock) wants a shared oplock. |
| [FsRtlOplockKeysEqual function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockkeysequal~r1.md) | The FsRtlOplockKeysEqual routine compares the opportunistic lock (oplock) keys that are stored in the file object extensions of two file objects. |
| [FsRtlPostPagingFileStackOverflow function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlpostpagingfilestackoverflow~r2.md) | The FsRtlPostPagingFileStackOverflow routine posts a paging file stack overflow item to the stack overflow thread. |
| [FsRtlPostStackOverflow function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlpoststackoverflow~r2.md) | The FsRtlPostStackOverflow routine posts a stack overflow item to the stack overflow thread. |
| [FsRtlPrepareMdlWriteDev function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlpreparemdlwritedev~r6.md) | The FltFastIoPrepareMdlWrite routine returns a linked list of memory descriptor lists (MDLs) that point to the specified range of cached file data to write data directly to the cache. |
| [FsRtlPrepareMdlWriteEx function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlpreparemdlwriteex~r5.md) | The FsRtlPrepareMdlWriteEx routine returns a linked list of memory descriptor lists (MDLs) that point to the specified range of cached file data to write data directly to the cache. |
| [FsRtlPrepareToReuseEcp function](..\ntifs\nf-ntifs-fsrtlpreparetoreuseecp.md) | The FsRtlPrepareToReuseEcp routine resets an extra create parameter (ECP) context structure, which prepares it for reuse. |
| [FsRtlPrivateLock function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlprivatelock~r11.md) | Obsolete. |
| [FsRtlProcessFileLock function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlprocessfilelock~r2.md) | The FsRtlProcessFileLock routine processes and completes an IRP for a file lock operation. |
| [FsRtlQueryCachedVdl function](..\ntifs\nf-ntifs-fsrtlquerycachedvdl.md) | The current valid data length (VDL) for a cached file is retrieved with the FsRtlQueryCachedVdl routine. |
| [FsRtlQueryKernelEaFile function](..\ntifs\nf-ntifs-fsrtlquerykerneleafile.md) | The routine FsRtlQueryKernelEaFile is used to build an explicit QueryEA request and synchronously wait for it to complete, returning the result. This allows the caller to do this by FileObject instead of a handle. |
| [FsRtlRegisterFileSystemFilterCallbacks function](..\ntifs\nf-ntifs-fsrtlregisterfilesystemfiltercallbacks.md) | File system filter drivers and file systems call the FsRtlRegisterFileSystemFilterCallbacks routine to register notification callback routines to be invoked when the underlying file system performs certain operations. |
| [FsRtlRegisterUncProvider function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncprovider~r2.md) | The FsRtlRegisterUncProvider routine registers a network redirector as a universal naming convention (UNC) provider with the system multiple UNC provider (MUP). |
| [FsRtlRegisterUncProviderEx function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlregisteruncproviderex~r3.md) | The FsRtlRegisterUncProviderEx routine registers a network redirector as a universal naming convention (UNC) provider with the system multiple UNC provider (MUP). |
| [FsRtlReleaseFile function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlreleasefile.md) | Reserved for system use. |
| [FsRtlRemoveDotsFromPath function](..\ntifs\nf-ntifs-fsrtlremovedotsfrompath.md) | The FsRtlRemoveDotsFromPath routine removes unnecessary occurrences of '.' and '..' from the specified path. |
| [FsRtlRemoveExtraCreateParameter function](..\ntifs\nf-ntifs-fsrtlremoveextracreateparameter.md) | The FsRtlRemoveExtraCreateParameter routine searches an ECP list for an ECP context structure and, if found, detaches it from the ECP list. |
| [FsRtlRemoveLargeMcbEntry function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlremovelargemcbentry~r2.md) | The FsRtlRemoveLargeMcbEntry routine removes one or more mappings from a map control block (MCB). |
| [FsRtlRemoveMcbEntry function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlremovemcbentry~r2.md) | Obsolete. |
| [FsRtlRemovePerFileContext function](..\ntifs\nf-ntifs-fsrtlremoveperfilecontext.md) | The FsRtlRemovePerFileContext routine returns a pointer to a FSRTL_PER_FILE_CONTEXT object that is associated with a file. |
| [FsRtlRemovePerFileObjectContext function](..\ntifs\nf-ntifs-fsrtlremoveperfileobjectcontext.md) | For a &#0034;legacy&#0034; file system filter driver, the FsRtlRemovePerFileObjectContext function unlinks a per-file-object context information structure from the list of per-file-object contexts previously associated with a file object. |
| [FsRtlRemovePerStreamContext function](..\ntifs\nf-ntifs-fsrtlremoveperstreamcontext.md) | FsRtlRemovePerStreamContext removes a per-stream context structure from the list of per-stream contexts associated with a file stream. |
| [FsRtlResetLargeMcb function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlresetlargemcb~r1.md) | The FsRtlResetLargeMcb routine truncates a map control block (MCB) structure to contain zero mapping pairs. It does not shrink the mapping pairs array. |
| [FsRtlSetEcpListIntoIrp function](..\ntifs\nf-ntifs-fsrtlsetecplistintoirp.md) | The FsRtlSetEcpListIntoIrp routine attaches an extra create parameter (ECP) context structure list to an IRP_MJ_CREATE operation. |
| [FsRtlSetKernelEaFile function](..\ntifs\nf-ntifs-fsrtlsetkerneleafile.md) | The routine FsRtlQueryKernelEaFile is used to set, modify and/or delete extended attribute (EA) values for a file and synchronously wait for it to complete, returning a result. |
| [FsRtlSetupAdvancedHeader function](..\ntifs\nf-ntifs-fsrtlsetupadvancedheader.md) | The FsRtlSetupAdvancedHeader macro is used by file systems to initialize an FSRTL_ADVANCED_FCB_HEADER structure for use with filter contexts. |
| [FsRtlSplitLargeMcb function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlsplitlargemcb~r2.md) | The FsRtlSplitLargeMcb routine inserts a hole into the mappings in a map control block (MCB). |
| [FsRtlTeardownPerFileContexts function](..\ntifs\nf-ntifs-fsrtlteardownperfilecontexts.md) | File systems call theFsRtlTeardownPerFileContexts routine to free FSRTL_PER_FILE_CONTEXT objects that are associated with a file control block (FCB) structure. |
| [FsRtlTeardownPerStreamContexts function](..\ntifs\nf-ntifs-fsrtlteardownperstreamcontexts.md) | The FsRtlTeardownPerStreamContexts routine frees all per-stream context structures associated with a given FSRTL_ADVANCED_FCB_HEADER structure. |
| [FsRtlTruncateLargeMcb function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtltruncatelargemcb~r1.md) | The FsRtlTruncateLargeMcb routine truncates a large map control block (MCB). |
| [FsRtlTruncateMcb function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtltruncatemcb~r1.md) | Obsolete. |
| [FsRtlUninitializeFileLock function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializefilelock.md) | The FsRtlUninitializeFileLock routine uninitializes a FILE_LOCK structure. |
| [FsRtlUninitializeLargeMcb function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializelargemcb.md) | The FsRtlUninitializeLargeMcb routine uninitializes a large map-control block (MCB). |
| [FsRtlUninitializeMcb function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializemcb.md) | Obsolete. |
| [FsRtlUninitializeOplock function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializeoplock.md) | FsRtlUninitializeOplock uninitializes an opportunistic lock (oplock) pointer. |
| [FsRtlUpperOplockFsctrl function](..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlupperoplockfsctrl~r4.md) | The FsRtlUpperOplockFsctrl routine processes opportunistic lock (oplock) requests and acknowledgments for secondary, or layered, file systems. |
| [FsRtlValidateReparsePointBuffer function](..\ntifs\nf-ntifs-fsrtlvalidatereparsepointbuffer.md) | The FsRtlValidateReparsePointBuffer routine verifies that the specified reparse point buffer is valid. |
| [GetSecurityUserInfo function](..\ntifs\nf-ntifs-getsecurityuserinfo.md) | The GetSecurityUserInfo function retrieves information about a logon session. |
| [IoAcquireVpbSpinLock function](..\ntifs\nf-ntifs-ioacquirevpbspinlock.md) | The IoAcquireVpbSpinLock routine acquires the Volume Parameter Block (VPB) spin lock. |
| [IoCheckDesiredAccess function](..\ntifs\nf-ntifs-iocheckdesiredaccess.md) | Reserved for system use. |
| [IoCheckEaBufferValidity function](..\ntifs\nf-ntifs-iocheckeabuffervalidity.md) | The IoCheckEaBufferValidity routine checks whether the specified extended attribute (EA) buffer is valid. |
| [IoCheckFunctionAccess function](..\ntifs\nf-ntifs-iocheckfunctionaccess.md) | Reserved for system use. |
| [IoCheckQuerySetFileInformation function](..\ntifs\nf-ntifs-iocheckquerysetfileinformation.md) | Reserved for system use. |
| [IoCheckQuerySetVolumeInformation function](..\ntifs\nf-ntifs-iocheckquerysetvolumeinformation.md) | Reserved for system use. |
| [IoCheckQuotaBufferValidity function](..\ntifs\nf-ntifs-iocheckquotabuffervalidity.md) | The IoCheckQuotaBufferValidity routine checks whether the specified quota buffer is valid. |
| [IoCreateStreamFileObject function](..\ntifs\nf-ntifs-iocreatestreamfileobject.md) | The IoCreateStreamFileObject routine creates a new stream file object. |
| [IoCreateStreamFileObjectEx function](..\ntifs\nf-ntifs-iocreatestreamfileobjectex.md) | The IoCreateStreamFileObjectEx routine creates a new stream file object. |
| [IoCreateStreamFileObjectEx2 function](..\ntifs\nf-ntifs-iocreatestreamfileobjectex2.md) | The IoCreateStreamFileObjectEx2 routine creates a new stream file object with create options for a target device object. |
| [IoCreateStreamFileObjectLite function](..\ntifs\nf-ntifs-iocreatestreamfileobjectlite.md) | The IoCreateStreamFileObjectLite routine creates a new stream file object, but does not cause an IRP_MJ_CLEANUP request to be sent to the file system driver stack. |
| [IoEnumerateDeviceObjectList function](..\ntifs\nf-ntifs-ioenumeratedeviceobjectlist.md) | The IoEnumerateDeviceObjectList routine enumerates a driver's device object list. |
| [IoEnumerateRegisteredFiltersList function](..\ntifs\nf-ntifs-ioenumerateregisteredfilterslist.md) | The IoEnumerateRegisteredFiltersList routine enumerates the file system filter drivers that have registered with the system. |
| [IoFastQueryNetworkAttributes function](..\ntifs\nf-ntifs-iofastquerynetworkattributes.md) | Reserved for system use. |
| [IoGetAttachedDevice function](..\ntifs\nf-ntifs-iogetattacheddevice.md) | The IoGetAttachedDevice routine returns a pointer to the highest-level device object associated with the specified device. |
| [IoGetBaseFileSystemDeviceObject function](..\ntifs\nf-ntifs-iogetbasefilesystemdeviceobject.md) | Reserved for system use. |
| [IoGetDeviceAttachmentBaseRef function](..\ntifs\nf-ntifs-iogetdeviceattachmentbaseref.md) | The IoGetDeviceAttachmentBaseRef routine returns a pointer to the lowest-level device object in a file system or device driver stack. |
| [IoGetDeviceToVerify function](..\ntifs\nf-ntifs-iogetdevicetoverify.md) | The IoGetDeviceToVerify routine returns a pointer to the device object, representing a removable-media device, that is the target of the given thread's I/O request. |
| [IoGetDiskDeviceObject function](..\ntifs\nf-ntifs-iogetdiskdeviceobject.md) | The IoGetDiskDeviceObject routine retrieves a pointer to the disk device object associated with a given file system volume device object. |
| [IoGetLowerDeviceObject function](..\ntifs\nf-ntifs-iogetlowerdeviceobject.md) | The IoGetLowerDeviceObject routine returns a pointer to the next-lower-level device object on the driver stack. |
| [IoGetRequestorProcess function](..\ntifs\nf-ntifs-iogetrequestorprocess.md) | The IoGetRequestorProcess routine returns a process pointer for the thread that originally requested a given I/O operation. |
| [IoGetRequestorProcessId function](..\ntifs\nf-ntifs-iogetrequestorprocessid.md) | The IoGetRequestorProcessId routine returns the unique 32-bit process ID for the thread that originally requested a given I/O operation. |
| [IoGetRequestorSessionId function](..\ntifs\nf-ntifs-iogetrequestorsessionid.md) | The IoGetRequestorSessionId routine returns the session ID for the process that originally requested a given I/O operation. |
| [IoGetTopLevelIrp function](..\ntifs\nf-ntifs-iogettoplevelirp.md) | The IoGetTopLevelIrp routine returns the value of the TopLevelIrp field of the current thread. |
| [IoInitializePriorityInfo function](..\ntifs\nf-ntifs-ioinitializepriorityinfo.md) | The IoInitializePriorityInfo routine initializes a structure of type IO_PRIORITY_INFO. |
| [IoIsOperationSynchronous function](..\ntifs\nf-ntifs-ioisoperationsynchronous.md) | The IoIsOperationSynchronous routine determines whether a given IRP represents a synchronous or asynchronous I/O request. |
| [IoIsSystemThread function](..\ntifs\nf-ntifs-ioissystemthread.md) | The IoIsSystemThread routine checks whether a given thread is a system thread. |
| [IoIsValidNameGraftingBuffer function](..\ntifs\nf-ntifs-ioisvalidnamegraftingbuffer.md) | Reserved for system use. |
| [IoPageRead function](..\ntifs\nf-ntifs-iopageread.md) | Reserved for system use. |
| [IoQueryFileDosDeviceName function](..\ntifs\nf-ntifs-ioqueryfiledosdevicename.md) | The IoQueryFileDosDeviceName routine retrieves an MS-DOS device name for a file. |
| [IoQueryFileInformation function](..\ntifs\nf-ntifs-ioqueryfileinformation.md) | Reserved for system use. |
| [IoQueryVolumeInformation function](..\ntifs\nf-ntifs-ioqueryvolumeinformation.md) | Reserved for system use. |
| [IoQueueThreadIrp function](..\ntifs\nf-ntifs-ioqueuethreadirp.md) | Reserved for system use. |
| [IoRegisterFileSystem function](..\ntifs\nf-ntifs-ioregisterfilesystem.md) | The IoRegisterFileSystem routine adds a file system's control device object to the global file system queue. |
| [IoRegisterFsRegistrationChange function](..\ntifs\nf-ntifs-ioregisterfsregistrationchange.md) | The IoRegisterFsRegistrationChange routine registers a file system filter driver's notification routine to be called whenever a file system registers or unregisters itself as an active file system. |
| [IoRegisterFsRegistrationChangeEx function](..\ntifs\nf-ntifs-ioregisterfsregistrationchangeex.md) | The IoRegisterFsRegistrationChangeEx routine registers a file system filter driver's notification routine to be called whenever a file system registers or unregisters itself as an active file system. |
| [IoRegisterFsRegistrationChangeMountAware function](..\ntifs\nf-ntifs-ioregisterfsregistrationchangemountaware.md) | The IoRegisterFsRegistrationChangeMountAware routine registers a file system filter driver's notification routine. This notification routine is called whenever a file system registers or unregisters itself as an active file system. |
| [IoReleaseVpbSpinLock function](..\ntifs\nf-ntifs-ioreleasevpbspinlock.md) | The IoReleaseVpbSpinLock routine releases the Volume Parameter Block (VPB) spin lock. |
| [IoReplaceFileObjectName function](..\ntifs\nf-ntifs-ioreplacefileobjectname.md) | The IoReplaceFileObjectName routine replaces the name of a file object. |
| [IoSetDeviceToVerify function](..\ntifs\nf-ntifs-iosetdevicetoverify.md) | The IoSetDeviceToVerify routine specifies a device object to be verified. The specified device object represents a removable media device. |
| [IoSetInformation function](..\ntifs\nf-ntifs-iosetinformation.md) | Reserved for system use. |
| [IoSetTopLevelIrp function](..\ntifs\nf-ntifs-iosettoplevelirp.md) | The IoSetTopLevelIrp routine sets the value of the TopLevelIrp field of the current thread. |
| [IoSynchronousPageWrite function](..\ntifs\nf-ntifs-iosynchronouspagewrite.md) | Reserved for system use. |
| [IoThreadToProcess function](..\ntifs\nf-ntifs-iothreadtoprocess.md) | The IoThreadToProcess routine returns a pointer to the process for the specified thread. |
| [IoUnregisterFileSystem function](..\ntifs\nf-ntifs-iounregisterfilesystem.md) | The IoUnregisterFileSystem routine removes a file system's control device object from the global file system queue. |
| [IoUnregisterFsRegistrationChange function](..\ntifs\nf-ntifs-iounregisterfsregistrationchange.md) | The IoUnregisterFsRegistrationChange routine unregisters file system filter driver's file system registration change notification routine. |
| [IoVerifyVolume function](..\ntifs\nf-ntifs-ioverifyvolume.md) | The IoVerifyVolume routine sends a volume verify request to the given removable-media device. |
| [KeAttachProcess function](..\ntifs\nf-ntifs-keattachprocess.md) | Obsolete. |
| [KeDetachProcess function](..\ntifs\nf-ntifs-kedetachprocess.md) | Obsolete. |
| [KeInitializeMutant function](..\ntifs\nf-ntifs-keinitializemutant.md) | Reserved for system use. |
| [KeInitializeQueue function](..\ntifs\nf-ntifs-keinitializequeue.md) | The KeInitializeQueue routine initializes a queue object on which threads can wait for entries. |
| [KeInsertHeadQueue function](..\ntifs\nf-ntifs-keinsertheadqueue.md) | The KeInsertHeadQueue routine inserts an entry at the head of the given queue if it cannot immediately use the entry to satisfy a thread wait. |
| [KeInsertQueue function](..\ntifs\nf-ntifs-keinsertqueue.md) | The KeInsertQueue routine inserts an entry at the tail of the given queue if it cannot immediately use the entry to satisfy a thread wait. |
| [KeReadStateMutant function](..\ntifs\nf-ntifs-kereadstatemutant.md) | Reserved for system use. |
| [KeReadStateQueue function](..\ntifs\nf-ntifs-kereadstatequeue.md) | Reserved for system use. |
| [KeReleaseMutant function](..\ntifs\nf-ntifs-kereleasemutant.md) | Reserved for system use. |
| [KeReleaseQueuedSpinLock function](..\ntifs\nf-ntifs-kereleasequeuedspinlock.md) | Reserved for system use. |
| [KeRemoveQueue function](..\ntifs\nf-ntifs-keremovequeue.md) | The KeRemoveQueue routine gives the calling thread a pointer to a dequeued entry from the given queue object or allows the caller to wait, up to an optional timeout interval, on the queue object. |
| [KeRundownQueue function](..\ntifs\nf-ntifs-kerundownqueue.md) | The KeRundownQueue routine cleans up a queue object, flushing any queued entries. |
| [KeSetIdealProcessorThread function](..\ntifs\nf-ntifs-kesetidealprocessorthread.md) | Reserved for system use. |
| [KeStackAttachProcess function](..\ntifs\nf-ntifs-kestackattachprocess.md) | The KeStackAttachProcess routine attaches the current thread to the address space of the target process. |
| [KeTryToAcquireQueuedSpinLock function](..\ntifs\nf-ntifs-ketrytoacquirequeuedspinlock.md) | Reserved for system use. |
| [KeUnstackDetachProcess function](..\ntifs\nf-ntifs-keunstackdetachprocess.md) | The KeUnstackDetachProcess routine detaches the current thread from the address space of a process and restores the previous attach state. |
| [MapSecurityError function](..\ntifs\nf-ntifs-mapsecurityerror.md) | The MapSecurityError function maps a security interface SECURITY_STATUS status code to a corresponding NSTATUS status code. |
| [MmCanFileBeTruncated function](..\ntifs\nf-ntifs-mmcanfilebetruncated.md) | The MmCanFileBeTruncated routine checks whether a file can be truncated. |
| [MmDoesFileHaveUserWritableReferences function](..\ntifs\nf-ntifs-mmdoesfilehaveuserwritablereferences.md) | The MmDoesFileHaveUserWritableReferences function returns the number of writable references for a file object. |
| [MmFlushImageSection function](..\ntifs\nf-ntifs-mmflushimagesection.md) | The MmFlushImageSection routine flushes the image section for a file. |
| [MmForceSectionClosed function](..\ntifs\nf-ntifs-mmforcesectionclosed.md) | The MmForceSectionClosed routine deletes the data and image sections for a file that is no longer in use. |
| [MmGetMaximumFileSectionSize function](..\ntifs\nf-ntifs-mmgetmaximumfilesectionsize.md) | The MmGetMaximumFileSectionSize returns the maximum possible size of a file section for the current version of Windows. |
| [MmIsRecursiveIoFault function](..\ntifs\nf-ntifs-mmisrecursiveiofault.md) | The MmIsRecursiveIoFault routine determines whether the current page fault is occurring during an I/O operation. |
| [MmPrefetchPages function](..\ntifs\nf-ntifs-mmprefetchpages.md) | The MmPrefetchPages routine reads groups of pages from secondary storage in the optimal fashion. |
| [MmSetAddressRangeModified function](..\ntifs\nf-ntifs-mmsetaddressrangemodified.md) | The MmSetAddressRangeModified routine marks currently valid pages in the specified range of the system cache as modified. |
| [ObInsertObject function](..\ntifs\nf-ntifs-obinsertobject.md) | Reserved for system use. |
| [ObIsKernelHandle function](..\ntifs\nf-ntifs-obiskernelhandle.md) | The ObIsKernelHandle routine determines whether the specified handle is a kernel handle. |
| [ObMakeTemporaryObject function](..\ntifs\nf-ntifs-obmaketemporaryobject.md) | Reserved for system use. |
| [ObOpenObjectByPointer function](..\ntifs\nf-ntifs-obopenobjectbypointer.md) | The ObOpenObjectByPointer function opens an object referenced by a pointer and returns a handle to the object. |
| [ObQueryNameString function](..\ntifs\nf-ntifs-obquerynamestring.md) | The ObQueryNameString routine supplies the name, if there is one, of a given object to which the caller has a pointer. |
| [ObQueryObjectAuditingByHandle function](..\ntifs\nf-ntifs-obqueryobjectauditingbyhandle.md) | Reserved for system use. |
| [PsChargePoolQuota function](..\ntifs\nf-ntifs-pschargepoolquota.md) | The PsChargePoolQuota routine charges pool quota of the specified pool type to the specified process. |
| [PsDereferenceImpersonationToken function](..\ntifs\nf-ntifs-psdereferenceimpersonationtoken.md) | The PsDereferenceImpersonationToken routine decrements the reference count of an impersonation token. |
| [PsDereferencePrimaryToken function](..\ntifs\nf-ntifs-psdereferenceprimarytoken.md) | The PsDereferencePrimaryToken routine decrements the reference count of a primary token. |
| [PsGetProcessExitTime function](..\ntifs\nf-ntifs-psgetprocessexittime.md) | The PsGetProcessExitTime routine returns the exit time for the current process. |
| [PsImpersonateClient function](..\ntifs\nf-ntifs-psimpersonateclient.md) | The PsImpersonateClient routine causes a server thread to impersonate a client. |
| [PsIsDiskCountersEnabled function](..\ntifs\nf-ntifs-psisdiskcountersenabled.md) | The enabled state of the per process disk I/O counters is returned by the PsIsDiskCountersEnabled routine. |
| [PsIsThreadTerminating function](..\ntifs\nf-ntifs-psisthreadterminating.md) | The PsIsThreadTerminating routine checks whether a thread is terminating. |
| [PsLookupProcessByProcessId function](..\ntifs\nf-ntifs-pslookupprocessbyprocessid.md) | The PsLookupProcessByProcessId routine accepts the process ID of a process and returns a referenced pointer to EPROCESS structure of the process. |
| [PsLookupThreadByThreadId function](..\ntifs\nf-ntifs-pslookupthreadbythreadid.md) | The PsLookupThreadByThreadId routine accepts the thread ID of a thread and returns a referenced pointer to the ETHREAD structure of the thread. |
| [PsReferenceImpersonationToken function](..\ntifs\nf-ntifs-psreferenceimpersonationtoken.md) | The PsReferenceImpersonationToken routine increments the reference count of the impersonation token for the specified thread. |
| [PsReferencePrimaryToken function](..\ntifs\nf-ntifs-psreferenceprimarytoken.md) | The PsReferencePrimaryToken routine increments the reference count of the primary token for the specified process. |
| [PsReturnPoolQuota function](..\ntifs\nf-ntifs-psreturnpoolquota.md) | The PsReturnPoolQuota routine returns pool quota of the specified pool type to the specified process. |
| [PsRevertToSelf function](..\ntifs\nf-ntifs-psreverttoself.md) | The PsRevertToSelf routine ends the calling thread's impersonation of a client. |
| [PsUpdateDiskCounters function](..\ntifs\nf-ntifs-psupdatediskcounters.md) | The PsUpdateDiskCounters routine updates the disk I/O counters of a given process. |
| [RtlAbsoluteToSelfRelativeSD function](..\ntifs\nf-ntifs-rtlabsolutetoselfrelativesd.md) | The RtlAbsoluteToSelfRelativeSD routine creates a new security descriptor in self-relative format by using a security descriptor in absolute format as a template. |
| [RtlAddAccessAllowedAce function](..\ntifs\nf-ntifs-rtladdaccessallowedace.md) | The RtlAddAccessAllowedAce routine adds an access-allowed access control entry (ACE) to an access control list (ACL). The access is granted to the specified security identifier (SID). |
| [RtlAddAccessAllowedAceEx function](..\ntifs\nf-ntifs-rtladdaccessallowedaceex.md) | The RtlAddAccessAllowedAceEx routine adds an access-allowed access control entry (ACE) with inheritance ACE flags to an access control list (ACL). The access is granted to the specified security identifier (SID). |
| [RtlAddAce function](..\ntifs\nf-ntifs-rtladdace.md) | The RtlAddAce routine adds one or more access control entries (ACEs) to a specified access control list (ACL). |
| [RtlAllocateAndInitializeSid function](..\ntifs\nf-ntifs-rtlallocateandinitializesid.md) | Reserved for system use. |
| [RtlAllocateHeap function](..\ntifs\nf-ntifs-rtlallocateheap.md) | The RtlAllocateHeap routine allocates a block of memory from a heap. |
| [RtlAppendStringToString function](..\ntifs\nf-ntifs-rtlappendstringtostring.md) | The RtlAppendStringToString routine concatenates two counted strings. It copies bytes from the source up to the length of the destination buffer. |
| [RtlCaptureContext function](..\ntifs\nf-ntifs-rtlcapturecontext.md) | The RtlCaptureContext function retrieves a context record in the context of the caller. |
| [RtlCaptureStackBackTrace function](..\ntifs\nf-ntifs-rtlcapturestackbacktrace.md) | The RtlCaptureStackBackTrace routine captures a stack back trace by walking up the stack and recording the information for each frame. |
| [RtlCompareMemoryUlong function](..\ntifs\nf-ntifs-rtlcomparememoryulong.md) | The RtlCompareMemoryUlong routine returns how many bytes in a block of memory match a specified pattern. |
| [RtlCompressBuffer function](..\ntifs\nf-ntifs-rtlcompressbuffer.md) | The RtlCompressBuffer function compresses a buffer and can be used by a file system driver to facilitate the implementation of file compression. |
| [RtlCompressChunks function](..\ntifs\nf-ntifs-rtlcompresschunks.md) | Reserved for system use. |
| [RtlConvertSidToUnicodeString function](..\ntifs\nf-ntifs-rtlconvertsidtounicodestring.md) | The RtlConvertSidToUnicodeString routine generates a printable Unicode string representation of a security identifier (SID). |
| [RtlCopyLuid function](..\ntifs\nf-ntifs-rtlcopyluid.md) | The RtlCopyLuid routine copies a locally unique identifier (LUID) to a buffer. |
| [RtlCopySid function](..\ntifs\nf-ntifs-rtlcopysid.md) | The RtlCopySid routine copies the value of a security identifier (SID) to a buffer. |
| [RtlCreateAcl function](..\ntifs\nf-ntifs-rtlcreateacl.md) | The RtlCreateAcl routine creates and initializes an access control list (ACL). |
| [RtlCreateHeap function](..\ntifs\nf-ntifs-rtlcreateheap.md) | The RtlCreateHeap routine creates a heap object that can be used by the calling process. This routine reserves space in the virtual address space of the process and allocates physical storage for a specified initial portion of this block. |
| [RtlCreateSecurityDescriptorRelative function](..\ntifs\nf-ntifs-rtlcreatesecuritydescriptorrelative.md) | The RtlCreateSecurityDescriptorRelative routine initializes a new security descriptor in self-relative format. |
| [RtlCreateSystemVolumeInformationFolder function](..\ntifs\nf-ntifs-rtlcreatesystemvolumeinformationfolder.md) | The RtlCreateSystemVolumeInformationFolder routine verifies the existence of the &#0034;System Volume Information&#0034; folder on a file system volume. If the folder is not present, then the folder is created. |
| [RtlCreateUnicodeString function](..\ntifs\nf-ntifs-rtlcreateunicodestring.md) | The RtlCreateUnicodeString routine creates a new counted Unicode string. |
| [RtlCustomCPToUnicodeN function](..\ntifs\nf-ntifs-rtlcustomcptounicoden.md) | Reserved for system use. |
| [RtlDecompressBuffer function](..\ntifs\nf-ntifs-rtldecompressbuffer.md) | The RtlDecompressBuffer function decompresses an entire compressed buffer. |
| [RtlDecompressBufferEx function](..\ntifs\nf-ntifs-rtldecompressbufferex.md) | The RtlDecompressBufferEx function decompresses an entire compressed buffer. |
| [RtlDecompressBufferEx2 function](..\ntifs\nf-ntifs-rtldecompressbufferex2.md) | The RtlDecompressBufferEx2 function decompresses an entire compressed buffer, using multiple processors where possible. Multiple processor support is only implemented for kernel mode callers. |
| [RtlDecompressChunks function](..\ntifs\nf-ntifs-rtldecompresschunks.md) | Reserved for system use. |
| [RtlDecompressFragment function](..\ntifs\nf-ntifs-rtldecompressfragment.md) | The RtlDecompressFragment function is used to decompress part of a compressed buffer (that is, a buffer &#0034;fragment&#0034;). |
| [RtlDecompressFragmentEx function](..\ntifs\nf-ntifs-rtldecompressfragmentex.md) | The RtlDecompressFragmentEx function is used to decompress part of a compressed buffer (that is, a buffer &#0034;fragment&#0034;), using multiple processors where possible. |
| [RtlDeleteAce function](..\ntifs\nf-ntifs-rtldeleteace.md) | The RtlDeleteAce routine deletes an access control entry (ACE) from a specified access control list (ACL). |
| [RtlDescribeChunk function](..\ntifs\nf-ntifs-rtldescribechunk.md) | Reserved for system use. |
| [RtlDestroyHeap function](..\ntifs\nf-ntifs-rtldestroyheap.md) | The RtlDestroyHeap routine destroys the specified heap object. RtlDestroyHeap decommits and releases all the pages of a private heap object, and it invalidates the handle to the heap. |
| [RtlDowncaseUnicodeString function](..\ntifs\nf-ntifs-rtldowncaseunicodestring.md) | The RtlDowncaseUnicodeString routine converts the specified Unicode source string to lowercase. The translation conforms to the current system locale information. |
| [RtlEqualPrefixSid function](..\ntifs\nf-ntifs-rtlequalprefixsid.md) | The RtlEqualPrefixSid routine determines whether two security-identifier (SID) prefixes are equal. An SID prefix is the entire SID except for the last subauthority value. |
| [RtlEqualSid function](..\ntifs\nf-ntifs-rtlequalsid.md) | The RtlEqualSid routine determines whether two security identifier (SID) values are equal. Two SIDs must match exactly to be considered equal. |
| [RtlFillMemoryUlong function](..\ntifs\nf-ntifs-rtlfillmemoryulong.md) | The RtlFillMemoryUlong routine fills the specified range of memory with one or more repetitions of a ULONG value. |
| [RtlFindUnicodePrefix function](..\ntifs\nf-ntifs-rtlfindunicodeprefix.md) | The RtlFindUnicodePrefix routine searches for the best match for a given Unicode file name in a prefix table. |
| [RtlFreeHeap function](..\ntifs\nf-ntifs-rtlfreeheap.md) | The RtlFreeHeap routine frees a memory block that was allocated from a heap by RtlAllocateHeap. |
| [RtlFreeOemString function](..\ntifs\nf-ntifs-rtlfreeoemstring.md) | The RtlFreeOemString routine releases storage that was allocated by any of the Rtl..ToOemString routines. |
| [RtlFreeSid function](..\ntifs\nf-ntifs-rtlfreesid.md) | Reserved for system use. |
| [RtlGenerate8dot3Name function](..\ntifs\nf-ntifs-rtlgenerate8dot3name.md) | The RtlGenerate8dot3Name routine generates a short (8.3) name for the specified long file name. |
| [RtlGetAce function](..\ntifs\nf-ntifs-rtlgetace.md) | The RtlGetAce routine obtains a pointer to an access control entry (ACE) in an access control list (ACL). |
| [RtlGetCompressionWorkSpaceSize function](..\ntifs\nf-ntifs-rtlgetcompressionworkspacesize.md) | The RtlGetCompressionWorkSpaceSize function is used to determine the correct size of the WorkSpace buffer for the RtlCompressBuffer and RtlDecompressFragment functions. |
| [RtlGetDaclSecurityDescriptor function](..\ntifs\nf-ntifs-rtlgetdaclsecuritydescriptor.md) | The RtlGetDaclSecurityDescriptor routine returns a pointer to the discretionary ACL (DACL) for a security descriptor. |
| [RtlGetGroupSecurityDescriptor function](..\ntifs\nf-ntifs-rtlgetgroupsecuritydescriptor.md) | The RtlGetGroupSecurityDescriptor routine returns the primary group information for a given security descriptor. |
| [RtlGetOwnerSecurityDescriptor function](..\ntifs\nf-ntifs-rtlgetownersecuritydescriptor.md) | The RtlGetOwnerSecurityDescriptor routine returns the owner information for a given security descriptor. |
| [RtlGetSaclSecurityDescriptor function](..\ntifs\nf-ntifs-rtlgetsaclsecuritydescriptor.md) | The RtlGetSaclSecurityDescriptor routine returns a pointer to the system ACL (SACL) for a security descriptor. |
| [RtlIdentifierAuthoritySid function](..\ntifs\nf-ntifs-rtlidentifierauthoritysid.md) | Reserved for system use. |
| [RtlInitCodePageTable function](..\ntifs\nf-ntifs-rtlinitcodepagetable.md) | Reserved for system use. |
| [RtlInitializeSid function](..\ntifs\nf-ntifs-rtlinitializesid.md) | The RtlInitializeSid routine initializes a security identifier (SID) structure. |
| [RtlInitializeSidEx function](..\ntifs\nf-ntifs-rtlinitializesidex.md) | The RtlInitializeSidEx routine initializes a pre-allocated security identifier (SID) structure. |
| [RtlInitializeUnicodePrefix function](..\ntifs\nf-ntifs-rtlinitializeunicodeprefix.md) | The RtlInitializeUnicodePrefix routine initializes a prefix table. |
| [RtlInsertUnicodePrefix function](..\ntifs\nf-ntifs-rtlinsertunicodeprefix.md) | The RtlInsertUnicodePrefix routine inserts a new element into a Unicode prefix table. |
| [RtlIsCloudFilesPlaceholder function](..\ntifs\nf-ntifs-rtliscloudfilesplaceholder.md) | The RtlIsCloudFilesPlaceholder routine determines if a file or a directory is a CloudFiles placeholder, based on the FileAttributes and ReparseTag values of the file. |
| [RtlIsNameLegalDOS8Dot3 function](..\ntifs\nf-ntifs-rtlisnamelegaldos8dot3.md) | The RtlIsNameLegalDOS8Dot3 routine determines whether a given name represents a valid short (8.3) file name. |
| [RtlIsPartialPlaceholder function](..\ntifs\nf-ntifs-rtlispartialplaceholder.md) | The RtlIsPartialPlaceholder routine determines if a file or a directory is a CloudFiles placeholder, based on the FileAttributes and ReparseTag values of the file. |
| [RtlIsPartialPlaceholderFileHandle function](..\ntifs\nf-ntifs-rtlispartialplaceholderfilehandle.md) | The RtlIsPartialPlaceholderFileHandle routine determines if a file is a known type of placeholder, based on a file handle. |
| [RtlIsPartialPlaceholderFileInfo function](..\ntifs\nf-ntifs-rtlispartialplaceholderfileinfo.md) | The RtlIsPartialPlaceholderFileInfo routine determines if a file is a known type of placeholder, based on the information returned by NtQueryInformationFile or NtQueryDirectoryFile. |
| [RtlIsValidOemCharacter function](..\ntifs\nf-ntifs-rtlisvalidoemcharacter.md) | The RtlIsValidOemCharacter routine determines if the specified Unicode character can be mapped to a valid OEM character. |
| [RtlLengthRequiredSid function](..\ntifs\nf-ntifs-rtllengthrequiredsid.md) | The RtlLengthRequiredSid routine returns the length, in bytes, of the buffer required to store a security identifier (SID) with a specified number of subauthorities. |
| [RtlLengthSid function](..\ntifs\nf-ntifs-rtllengthsid.md) | The RtlLengthSid routine returns the length, in bytes, of a valid security identifier (SID). |
| [RtlMultiByteToUnicodeN function](..\ntifs\nf-ntifs-rtlmultibytetounicoden.md) | The RtlMultiByteToUnicodeN routine translates the specified source string into a Unicode string, using the current system ANSI code page (ACP). The source string is not necessarily from a multibyte character set. |
| [RtlMultiByteToUnicodeSize function](..\ntifs\nf-ntifs-rtlmultibytetounicodesize.md) | The RtlMultiByteToUnicodeSize routine determines the number of bytes that are required to store the Unicode translation for the specified source string. |
| [RtlNextUnicodePrefix function](..\ntifs\nf-ntifs-rtlnextunicodeprefix.md) | The RtlNextUnicodePrefix routine is used to enumerate the elements in a Unicode prefix table. |
| [RtlNtStatusToDosError function](..\ntifs\nf-ntifs-rtlntstatustodoserror.md) | The RtlNtStatusToDosError routine converts the specified NTSTATUS code to its equivalent system error code. |
| [RtlNtStatusToDosErrorNoTeb function](..\ntifs\nf-ntifs-rtlntstatustodoserrornoteb.md) | Reserved for system use. |
| [RtlOemStringToCountedUnicodeString function](..\ntifs\nf-ntifs-rtloemstringtocountedunicodestring.md) | The RtlOemStringToCountedUnicodeString routine translates the specified source string into a Unicode string using the current system OEM code page. |
| [RtlOemStringToUnicodeString function](..\ntifs\nf-ntifs-rtloemstringtounicodestring.md) | The RtlOemStringToUnicodeString routine translates a given source string into a null-terminated Unicode string using the current system OEM code page. |
| [RtlOemToUnicodeN function](..\ntifs\nf-ntifs-rtloemtounicoden.md) | The RtlOemToUnicodeN routine translates the specified source string into a Unicode string, using the current system OEM code page. |
| [RtlQueryThreadPlaceholderCompatibilityMode function](..\ntifs\nf-ntifs-rtlquerythreadplaceholdercompatibilitymode.md) | RtlQueryThreadPlaceholderCompatibilityMode is a routine which returns the placeholder compatibility mode for the current thread. |
| [RtlRandom function](..\ntifs\nf-ntifs-rtlrandom.md) | The RtlRandom routine returns a random number that was generated from a given seed value. |
| [RtlRandomEx function](..\ntifs\nf-ntifs-rtlrandomex.md) | The RtlRandomEx routine returns a random number that was generated from a given seed value. |
| [RtlRemoveUnicodePrefix function](..\ntifs\nf-ntifs-rtlremoveunicodeprefix.md) | The RtlRemoveUnicodePrefix routine removes an element from a prefix table. |
| [RtlReserveChunk function](..\ntifs\nf-ntifs-rtlreservechunk.md) | Reserved for system use. |
| [RtlSecondsSince1970ToTime function](..\ntifs\nf-ntifs-rtlsecondssince1970totime.md) | The RtlSecondsSince1970ToTime routine converts the elapsed time, in seconds, since the beginning of 1970 to an absolute system time value. |
| [RtlSecondsSince1980ToTime function](..\ntifs\nf-ntifs-rtlsecondssince1980totime.md) | The RtlSecondsSince1980ToTime routine converts the elapsed time, in seconds, since the beginning of 1980 to an absolute system time value. |
| [RtlSelfRelativeToAbsoluteSD function](..\ntifs\nf-ntifs-rtlselfrelativetoabsolutesd.md) | The RtlSelfRelativeToAbsoluteSD routine creates a new security descriptor in absolute format by using a security descriptor in self-relative format as a template. |
| [RtlSetGroupSecurityDescriptor function](..\ntifs\nf-ntifs-rtlsetgroupsecuritydescriptor.md) | The RtlSetGroupSecurityDescriptor routine sets the primary group information of an absolute-format security descriptor. It replaces any primary group information that is already present in the security descriptor. |
| [RtlSetOwnerSecurityDescriptor function](..\ntifs\nf-ntifs-rtlsetownersecuritydescriptor.md) | The RtlSetOwnerSecurityDescriptor routine sets the owner information of an absolute-format security descriptor. It replaces any owner information that is already present in the security descriptor. |
| [RtlSetThreadPlaceholderCompatibilityMode function](..\ntifs\nf-ntifs-rtlsetthreadplaceholdercompatibilitymode.md) | RtlSetThreadPlaceholderCompatibilityMode is a routine which sets the placeholder compatibility mode for the current thread. |
| [RtlSubAuthorityCountSid function](..\ntifs\nf-ntifs-rtlsubauthoritycountsid.md) | Reserved for system use. |
| [RtlSubAuthoritySid function](..\ntifs\nf-ntifs-rtlsubauthoritysid.md) | The RtlSubAuthoritySid routine returns a pointer to a specified subauthority of a security identifier (SID). |
| [RtlTimeToSecondsSince1970 function](..\ntifs\nf-ntifs-rtltimetosecondssince1970.md) | The RtlTimeToSecondsSince1970 routine converts a given absolute system time value to the elapsed time, in seconds, since the beginning of 1970. |
| [RtlTimeToSecondsSince1980 function](..\ntifs\nf-ntifs-rtltimetosecondssince1980.md) | The RtlTimeToSecondsSince1980 routine converts a given absolute system time value to the elapsed time, in seconds, since the beginning of 1980. |
| [RtlUnicodeStringToCountedOemString function](..\ntifs\nf-ntifs-rtlunicodestringtocountedoemstring.md) | The RtlUnicodeStringToCountedOemString routine translates the specified Unicode source string into a counted OEM string using the current system OEM code page. |
| [RtlUnicodeStringToOemString function](..\ntifs\nf-ntifs-rtlunicodestringtooemstring.md) | The RtlUnicodeStringToOemString routine translates a given Unicode source string into an OEM string using the current system OEM code page. |
| [RtlUnicodeToCustomCPN function](..\ntifs\nf-ntifs-rtlunicodetocustomcpn.md) | Reserved for system use. |
| [RtlUnicodeToMultiByteN function](..\ntifs\nf-ntifs-rtlunicodetomultibyten.md) | The RtlUnicodeToMultiByteN routine translates the specified Unicode string into a new character string, using the current system ANSI code page (ACP). The translated string is not necessarily from a multibyte character set. |
| [RtlUnicodeToMultiByteSize function](..\ntifs\nf-ntifs-rtlunicodetomultibytesize.md) | The RtlUnicodeToMultiByteSize routine determines the number of bytes that are required to store the multibyte translation for the specified Unicode string. The translation is assumed to use the current system ANSI code page (ACP). |
| [RtlUnicodeToOemN function](..\ntifs\nf-ntifs-rtlunicodetooemn.md) | The RtlUnicodeToOemN routine translates a given Unicode string to an OEM string, using the current system OEM code page. |
| [RtlUpcaseUnicodeStringToCountedOemString function](..\ntifs\nf-ntifs-rtlupcaseunicodestringtocountedoemstring.md) | The RtlUpcaseUnicodeStringToCountedOemString routine translates a given Unicode source string into an uppercase counted OEM string using the current system OEM code page. |
| [RtlUpcaseUnicodeStringToOemString function](..\ntifs\nf-ntifs-rtlupcaseunicodestringtooemstring.md) | The RtlUpcaseUnicodeStringToOemString routine translates a given Unicode source string into an uppercase OEM string using the current system OEM code page. |
| [RtlUpcaseUnicodeToCustomCPN function](..\ntifs\nf-ntifs-rtlupcaseunicodetocustomcpn.md) | Reserved for system use. |
| [RtlUpcaseUnicodeToMultiByteN function](..\ntifs\nf-ntifs-rtlupcaseunicodetomultibyten.md) | The RtlUpcaseUnicodeToMultiByteN routine translates the specified Unicode string into a new uppercase character string, using the current system ANSI code page (ACP). The translated string is not necessarily from a multibyte character set. |
| [RtlUpcaseUnicodeToOemN function](..\ntifs\nf-ntifs-rtlupcaseunicodetooemn.md) | The RtlUpcaseUnicodeToOemN routine translates a given Unicode string into an uppercase OEM string, using the current system OEM code page. |
| [RtlValidSid function](..\ntifs\nf-ntifs-rtlvalidsid.md) | The RtlValidSid routine validates a security identifier (SID) by verifying that the revision number is within a known range and that the number of subauthorities is less than the maximum. |
| [RtlxOemStringToUnicodeSize function](..\ntifs\nf-ntifs-rtlxoemstringtounicodesize.md) | Reserved for system use. |
| [RtlxUnicodeStringToOemSize function](..\ntifs\nf-ntifs-rtlxunicodestringtooemsize.md) | Reserved for system use. |
| [RxAcquireExclusiveFcbResourceInMRx function](..\mrxfcb\nf-mrxfcb-rxacquireexclusivefcbresourceinmrx.md) | RxAcquireExclusiveFcbResourceInMRx acquires the FCB resource for a network mini-redirector driver in exclusive mode. |
| [RxAcquireSharedFcbResourceInMRx function](..\mrxfcb\nf-mrxfcb-rxacquiresharedfcbresourceinmrx.md) | RxAcquireSharedFcbResourceInMRx acquires the FCB resource for a network mini-redirector driver in shared mode. |
| [RxAcquireSharedFcbResourceInMRxEx function](..\mrxfcb\nf-mrxfcb-rxacquiresharedfcbresourceinmrxex.md) | RxAcquireSharedFcbResourceInMRxEx acquires the FCB resource for a network mini-redirector driver in shared mode. |
| [RxAssociateContextWithMid function](..\midatlax\nf-midatlax-rxassociatecontextwithmid.md) | RxAssociateContextWithMid associates the supplied opaque context with an available multiplex ID (MID) from a MID_ATLAS. |
| [RxCancelTimerRequest function](..\rxtimer\nf-rxtimer-rxcanceltimerrequest.md) | RxCancelTimerRequest cancels a recurrent timer request. The request to be canceled is identified by the worker thread routine and associated context. |
| [RxCeAllocateIrpWithMDL function](..\rxce\nf-rxce-rxceallocateirpwithmdl.md) | RxCeAllocateIrpWithMDL allocates an IRP and associates it with an existing memory descriptor list. |
| [RxCeBuildAddress function](..\rxce\nf-rxce-rxcebuildaddress.md) | RxCeBuildAddress associates a transport address with a transport binding. |
| [RxCeBuildConnection function](..\rxce\nf-rxce-rxcebuildconnection.md) | RxCeBuildConnection establishes a connection between a local RDBSS connection address and a given remote address. |
| [RxCeBuildConnectionOverMultipleTransports function](..\rxce\nf-rxce-rxcebuildconnectionovermultipletransports.md) | RxCeBuildConnectionOverMultipleTransports establishes a connection between a local RDBSS connection address and a given remote address and supports multiple transports. |
| [RxCeBuildTransport function](..\rxce\nf-rxce-rxcebuildtransport.md) | RxCeBuildTransport binds an RDBSS transport object to a specified transport name. |
| [RxCeBuildVC function](..\rxce\nf-rxce-rxcebuildvc.md) | RxCeBuildVC adds a virtual circuit to a specified RDBSS connection.. |
| [RxCeCancelConnectRequest function](..\rxce\nf-rxce-rxcecancelconnectrequest.md) | RxCeCancelConnectRequest cancels a previously issued connection request. Note that this routine is not currently implemented. |
| [RxCeFreeIrp function](..\rxce\nf-rxce-rxcefreeirp.md) | RxCeFreeIrp frees an IRP. |
| [RxCeInitiateVCDisconnect function](..\rxce\nf-rxce-rxceinitiatevcdisconnect.md) | RxCeInitiateVCDisconnect initiates a disconnect on the virtual circuit. |
| [RxCeQueryAdapterStatus function](..\rxce\nf-rxce-rxcequeryadapterstatus.md) | RxCeQueryAdapterStatus returns the ADAPTER_STATUS structure for a given transport in a caller-allocated buffer. |
| [RxCeQueryInformation function](..\rxce\nf-rxce-rxcequeryinformation.md) | RxCeQueryInformation queries information about a connection in a caller-allocated buffer. |
| [RxCeQueryTransportInformation function](..\rxce\nf-rxce-rxcequerytransportinformation.md) | RxCeQueryTransportInformation queries transport information for a given transport. |
| [RxCeSend function](..\rxce\nf-rxce-rxcesend.md) | RxCeSend sends a transport service data unit (TSDU) along the specified connection on a virtual circuit. |
| [RxCeSendDatagram function](..\rxce\nf-rxce-rxcesenddatagram.md) | RxCeSendDatagram sends a transport service data unit (TSDU) along the specified connection on a virtual circuit. |
| [RxCeTearDownAddress function](..\rxce\nf-rxce-rxceteardownaddress.md) | RxCeTearDownAddress deregisters a transport address from a transport binding. |
| [RxCeTearDownConnection function](..\rxce\nf-rxce-rxceteardownconnection.md) | RxCeTearDownConnection tears down a given connection between a local RDBSS connection address and a remote address. |
| [RxCeTearDownTransport function](..\rxce\nf-rxce-rxceteardowntransport.md) | RxCeTearDownTransport unbinds an RDBSS transport object. |
| [RxCeTearDownVC function](..\rxce\nf-rxce-rxceteardownvc.md) | RxCeTearDownVC deregisters a virtual circuit from a specified RDBSS connection. |
| [RxChangeBufferingState function](..\rxprocs\nf-rxprocs-rxchangebufferingstate.md) | RxChangeBufferingState is called to process a buffering state change request. |
| [RxCompleteRequest function](..\rxprocs\nf-rxprocs-rxcompleterequest.md) | RxCompleteRequest completes the IRP request associated with an RX_CONTEXT structure. |
| [RxCompleteRequest_Real function](..\rxprocs\nf-rxprocs-rxcompleterequest_real.md) | RxCompleteRequest_Real completes the IRP request associated with an RX_CONTEXT structure. |
| [RxCreateMidAtlas function](..\midatlax\nf-midatlax-rxcreatemidatlas.md) | RxCreateMidAtlas allocates a new instance of MID_ATLAS data structure and initializes it. |
| [RxCreateNetFcb function](..\fcb\nf-fcb-rxcreatenetfcb.md) | RxCreateNetFCB allocates, initializes, and inserts a new FCB structure into the in-memory data structures for a V_NET_ROOT that this FCB is being opened on. The structure allocated has space for a SRV_OPEN and an FOBX structure. |
| [RxCreateNetFobx function](..\fcb\nf-fcb-rxcreatenetfobx.md) | RxCreateNetFobx allocates, initializes, and inserts a new file object extension (FOBX) structure into the in-memory data structures for a FCB that this FOBX is being opened on. |
| [RxCreateNetRoot function](..\fcb\nf-fcb-rxcreatenetroot.md) | RxCreateNetRoot allocates and initializes a NET_ROOT structure and inserts the name into the net name table on the associated device object. |
| [RxCreateRxContext function](..\rxcontx\nf-rxcontx-rxcreaterxcontext.md) | RxCreateRxContext allocates a new RX_CONTEXT structure and initializes the data structure. |
| [RxCreateSrvCall function](..\fcb\nf-fcb-rxcreatesrvcall.md) | RxCreateSrvCall builds a SRV_CALL structure and inserts the name into the net name table maintained by RDBSS. |
| [RxCreateSrvOpen function](..\fcb\nf-fcb-rxcreatesrvopen.md) | RxCreateSrvOpen allocates, initializes, and inserts a new SRV_OPEN structure into the in-memory data structures used by RDBSS. If a new structure has to be allocated, it has space for an FOBX structure. |
| [RxCreateVNetRoot function](..\fcb\nf-fcb-rxcreatevnetroot.md) | RxCreateVNetRoot allocates and initializes a NET_ROOT structure and inserts the name into the net name table on the associated device object. |
| [RxDereference function](..\rxprocs\nf-rxprocs-rxdereference.md) | RxDereference decrements the NodeReferenceCount member of a structure by one for several reference counted data structures used by RDBSS. |
| [RxDereferenceAndDeleteRxContext_Real function](..\rxcontx\nf-rxcontx-rxdereferenceanddeleterxcontext_real.md) | RxDereferenceAndDeleteRxContext_Real dereferences an RX_CONTEXT data structure and if the ReferenceCount member goes to zero, then it deallocates and removes the specified RX_CONTEXT structure from the RDBSS in-memory data structures. |
| [RxDestroyMidAtlas function](..\midatlax\nf-midatlax-rxdestroymidatlas.md) | RxDestroyMidAtlas destroys an existing instance of a MID_ATLAS data structure and frees the allocated memory. |
| [RxDispatchToWorkerThread function](..\rxworkq\nf-rxworkq-rxdispatchtoworkerthread.md) | RxDispatchToWorkerThread invokes a routine in the context of a worker thread. The memory for the WORK_QUEUE_ITEM is allocated by this routine. |
| [RxDriverEntry function](..\rxprocs\nf-rxprocs-rxdriverentry.md) | RxDriverEntry is called by a monolithic network mini-redirector driver from its DriverEntry routine to initialize the RDBSS static library. |
| [RxFinalizeConnection function](..\rxprocs\nf-rxprocs-rxfinalizeconnection.md) | RxFinalizeConnection deletes a connection to a share. |
| [RxFinalizeNetFcb function](..\rxprocs\nf-rxprocs-rxfinalizenetfcb.md) | RxFinalizeNetFCB finalizes the given FCB structure. The caller must have an exclusive lock on the NET_ROOT associated with FCB. |
| [RxFinalizeNetFobx function](..\fcb\nf-fcb-rxfinalizenetfobx.md) | RxFinalizeNetFOBX finalizes the given FOBX structure. The caller must have an exclusive lock on the FCB associated with FOBX structure. |
| [RxFinalizeNetRoot function](..\fcb\nf-fcb-rxfinalizenetroot.md) | RxFinalizeNetRoot finalizes the given NET_ROOT structure. The caller must have an exclusive lock on the netname table associated with the device object. |
| [RxFinalizeSrvCall function](..\fcb\nf-fcb-rxfinalizesrvcall.md) | RxFinalizeSrvCall finalizes the given SRV_CALL structure. The caller must have an exclusive lock on the netname table associated with the device object. |
| [RxFinalizeSrvOpen function](..\fcb\nf-fcb-rxfinalizesrvopen.md) | RxFinalizeSrvOpen finalizes the given SRV_OPEN structure. The caller must have an exclusive lock on the FCB associated with the SRV_OPEN and either a shared or exclusive lock on the table lock of the NET_ROOT associated with the FCB. |
| [RxFinalizeVNetRoot function](..\fcb\nf-fcb-rxfinalizevnetroot.md) | RxFinalizeVNetRoot finalizes the given V_NET_ROOT structure. The caller must have an exclusive lock on the netname table associated with the device object. |
| [RxFinishFcbInitialization function](..\fcb\nf-fcb-rxfinishfcbinitialization.md) | RxFinishFcbInitialization is used to finish initializing an FCB after the successful completion of a create operation by the network mini-redirector. |
| [RxForceFinalizeAllVNetRoots function](..\rxprocs\nf-rxprocs-rxforcefinalizeallvnetroots.md) | RxForceFinalizeAllVNetRoots force finalizes all the V_NET_ROOT structures associated with a given NET_ROOT structure. The caller must have an exclusive lock on the netname table associated with the device object. |
| [RxFsdDispatch function](..\mrx\nf-mrx-rxfsddispatch.md) | RxFsdDispatch implements the file system driver (FSD) dispatch for RDBSS to process an I/O request packet (IRP). |
| [RxFsdPostRequest function](..\rxprocs\nf-rxprocs-rxfsdpostrequest.md) | RxFsdPostRequest queues the I/O request packet (IRP) specified by an RX_CONTEXT structure to the worker queue for processing by the file system process (FSP). |
| [RxGetFileSizeWithLock function](..\fcb\nf-fcb-rxgetfilesizewithlock.md) | RxGetFileSizeWithLock gets the file size in the FCB structure using a lock to ensure that the 64-bit value is read consistently. |
| [RxGetRDBSSProcess function](..\rxstruc\nf-rxstruc-rxgetrdbssprocess.md) | RxGetRDBSSProcess returns a pointer to the process of the main thread used by the RDBSS kernel process. |
| [RxIndicateChangeOfBufferingState function](..\rxprocs\nf-rxprocs-rxindicatechangeofbufferingstate.md) | RxIndicateChangeOfBufferingState is called to register a change buffering state request (an oplock break indication, for example) for later processing. If necessary, worker thread routines for further processing are activated. |
| [RxIndicateChangeOfBufferingStateForSrvOpen function](..\rxprocs\nf-rxprocs-rxindicatechangeofbufferingstateforsrvopen.md) | RxIndicateChangeOfBufferingStateForSrvOpen is called to register a change buffering state request (an oplock break indication, for example) for later processing. If the necessary preconditions are satisfied, the oplock is processed further. |
| [RxInferFileType function](..\fcb\nf-fcb-rxinferfiletype.md) | RxInferFileType tries to infer the file type (directory or non-directory) from a member in the RX_CONTEXT structure. |
| [RxInitializeContext function](..\rxcontx\nf-rxcontx-rxinitializecontext.md) | RxInitializeContext initializes an existing RX_CONTEXT data structure. |
| [RxIsThisACscAgentOpen function](..\rxprocs\nf-rxprocs-rxisthisacscagentopen.md) | RxIsThisACscAgentOpen determines if a file open was made by a user-mode client-side caching agent. |
| [RxLockEnumerator function](..\rxprocs\nf-rxprocs-rxlockenumerator.md) | RxLockEnumerator is called from a network mini-redirector to enumerate the file locks on an FCB. |
| [RxLogEventDirect function](..\rxprocs\nf-rxprocs-rxlogeventdirect.md) | RxLogEventDirect is called to log an error to the I/O error log. It is recommended that the RXLogEvent macro or the RxLogFailure macro be used instead of calling this routine directly. |
| [RxLogEventWithAnnotation function](..\rxprocs\nf-rxprocs-rxlogeventwithannotation.md) | RxLogEventWithAnnotation allocates an I/O error log structure, fills it in with information, and writes the entry to the I/O error log. |
| [RxLogEventWithBufferDirect function](..\rxprocs\nf-rxprocs-rxlogeventwithbufferdirect.md) | RxLogEventWithBufferDirect allocates an I/O error log structure, fills it in with information, and writes the entry to the I/O error log. |
| [RxLowIoCompletion function](..\lowio\nf-lowio-rxlowiocompletion.md) | RxLowIoCompletion must be called by the network mini-redirector low I/O routines when they complete, if the low I/O routines have initially returned STATUS_PENDING. |
| [RxLowIoGetBufferAddress function](..\lowio\nf-lowio-rxlowiogetbufferaddress.md) | RxLowIoGetBufferAddress returns the buffer corresponding to the MDL from LowIoContext structure of an RX_CONTEXT structure. |
| [RxMakeLateDeviceAvailable function](..\mrx\nf-mrx-rxmakelatedeviceavailable.md) | RxMakeLateDeviceAvailable modifies the device object to make a &#0034;late device&#0034; available. A late device is one that is not created in the driver's load routine. |
| [RxMapAndDissociateMidFromContext function](..\midatlax\nf-midatlax-rxmapanddissociatemidfromcontext.md) | RxMapAndDissociateMidFromContext maps a Multiplex ID (MID) to its associated context in a MID_ATLAS structure and then disassociates the MID from the context. |
| [RxMapMidToContext function](..\midatlax\nf-midatlax-rxmapmidtocontext.md) | RxMapMidToContext maps a Multiplex ID (MID) to its associated context in a MID_ATLAS structure. |
| [RxMapSystemBuffer function](..\rxprocs\nf-rxprocs-rxmapsystembuffer.md) | RxMapSystemBuffer returns the system buffer address from the IRP. |
| [RxNameCacheActivateEntry function](..\namcache\nf-namcache-rxnamecacheactivateentry.md) | RxNameCacheActivateEntry takes a name cache entry and updates the expiration time and the network mini-redirector context. It then puts the name cache entry on the active list. |
| [RxNameCacheCheckEntry function](..\namcache\nf-namcache-rxnamecachecheckentry.md) | RxNameCacheCheckEntry checks a name cache entry for validity. A valid entry means that the lifetime has not expired and the MRxContext parameter passes the equality check. |
| [RxNameCacheCreateEntry function](..\namcache\nf-namcache-rxnamecachecreateentry.md) | RxNameCacheCreateEntry allocates and initializes a NAME_CACHE structure with the given name string. |
| [RxNameCacheExpireEntry function](..\namcache\nf-namcache-rxnamecacheexpireentry.md) | RxNameCacheExpireEntry puts a NAME_CACHE entry on the free list for recycling. |
| [RxNameCacheExpireEntryWithShortName function](..\namcache\nf-namcache-rxnamecacheexpireentrywithshortname.md) | RxNameCacheExpireEntryWithShortName expires all of the name cache entries whose name prefix matches the given short file name. |
| [RxNameCacheFetchEntry function](..\namcache\nf-namcache-rxnamecachefetchentry.md) | RxNameCacheFetchEntry looks for a match with a specified name string for a NAME_CACHE entry. |
| [RxNameCacheFinalize function](..\namcache\nf-namcache-rxnamecachefinalize.md) | RxNameCacheFinalize releases the storage for all of the NAME_CACHE entries associated with a NAME_CACHE_CONTROL structure. |
| [RxNameCacheFreeEntry function](..\namcache\nf-namcache-rxnamecachefreeentry.md) | RxNameCacheFreeEntry releases the storage for a NAME_CACHE entry and decrements the count of the NAME_CACHE cache entries associated with a NAME_CACHE_CONTROL structure. |
| [RxNameCacheInitialize function](..\namcache\nf-namcache-rxnamecacheinitialize.md) | RxNameCacheInitialize initializes a name cache (NAME_CACHE_CONTROL structure). |
| [RxPostOneShotTimerRequest function](..\rxtimer\nf-rxtimer-rxpostoneshottimerrequest.md) | RxPostOneShotTimerRequest initializes a one-shot timer entry. The passed-in pointer to a worker thread routine is called once when the timer expires. |
| [RxPostRecurrentTimerRequest function](..\rxtimer\nf-rxtimer-rxpostrecurrenttimerrequest.md) | RxPostRecurrentTimerRequest initializes a recurrent timer request. The passed in pointer to a worker thread routine is called at regular intervals when the recurrent timer fires based on the input parameters to this routine. |
| [RxPostToWorkerThread function](..\rxworkq\nf-rxworkq-rxposttoworkerthread.md) | RxPostToWorkerThread invokes a routine passed as a parameter in the context of a worker thread. Memory for the WORK_QUEUE_ITEM must be allocated by the caller. |
| [RxPrefixTableLookupName function](..\prefix\nf-prefix-rxprefixtablelookupname.md) | RxPrefixTableLookupName looks up a name in a prefix table used to catalog SRV_CALL, NET_ROOT, and V_NET_ROOT names and converts the underlying pointer to a structure that contains the name. |
| [RxPrepareContextForReuse function](..\rxcontx\nf-rxcontx-rxpreparecontextforreuse.md) | RxPrepareContextForReuse prepares an RX_CONTEXT data structure for reuse by resetting all of the operation-specific allocations and acquisitions that have been made (the ReferenceCount member to the RX_CONTEXT structure is set to zero). |
| [RxPrepareToReparseSymbolicLink function](..\rxprocs\nf-rxprocs-rxpreparetoreparsesymboliclink.md) | RxPrepareToReparseSymbolicLink sets up the file object name to facilitate a reparse. This routine is used by the network mini-redirectors to traverse symbolic links. |
| [RxPurgeAllFobxs function](..\rxprocs\nf-rxprocs-rxpurgeallfobxs.md) | RxPurgeAllFobxs purges all of the FOBX structures associated with a network mini-redirector. |
| [RxPurgeRelatedFobxs function](..\scavengr\nf-scavengr-rxpurgerelatedfobxs.md) | RxPurgeRelatedFobxs purges all of the FOBX structures associated with a NET_ROOT structure. |
| [RxReassociateMid function](..\midatlax\nf-midatlax-rxreassociatemid.md) | RxReassociateMid reassociates a Multiplex ID (MID) with an alternate context. |
| [RxReference function](..\rxprocs\nf-rxprocs-rxreference.md) | RxReference increments the NodeReferenceCount member of a structure by one for several of the reference counted data structures used by RDBSS. |
| [RxRegisterMinirdr function](..\mrx\nf-mrx-rxregisterminirdr.md) | RxRegisterMinirdr is called by a network mini-redirector driver to register the driver with RDBSS, which adds the registration information to an internal registration table. RDBSS also builds a device object for the network mini-redirector. |
| [RxReleaseFcbResourceForThreadInMRx function](..\mrxfcb\nf-mrxfcb-rxreleasefcbresourceforthreadinmrx.md) | RxReleaseFcbResourceForThreadInMRx releases the FCB resource acquired by a network mini-redirector driver with a particular thread ID. |
| [RxReleaseFcbResourceInMRx function](..\mrxfcb\nf-mrxfcb-rxreleasefcbresourceinmrx.md) | RxReleaseFcbResourceInMRx releases the FCB resource acquired by a network mini-redirector driver. |
| [RxResumeBlockedOperations_Serially function](..\rxcontx\nf-rxcontx-rxresumeblockedoperations_serially.md) | RxResumeBlockedOperations_Serially wakes up the next waiting thread, if any, on the serialized blocking I/O queue. |
| [RxScavengeAllFobxs function](..\rxprocs\nf-rxprocs-rxscavengeallfobxs.md) | RxScavengeAllFobxs scavenges all of the FOBX structures associated with a network mini-redirector device object. |
| [RxScavengeFobxsForNetRoot function](..\scavengr\nf-scavengr-rxscavengefobxsfornetroot.md) | RxScavengeFobxsForNetRoot scavenges all of the FOBX structures associated with a given NET_ROOT structure. |
| [RxSetDomainForMailslotBroadcast function](..\mrx\nf-mrx-rxsetdomainformailslotbroadcast.md) | RxSetDomainForMailslotBroadcast is called by a network mini-redirector driver to set the domain used for mailslot broadcasts if mailslots are supported by the driver. |
| [RxSetMinirdrCancelRoutine function](..\rxcontx\nf-rxcontx-rxsetminirdrcancelroutine.md) | RxSetMinirdrCancelRoutine is called by a network mini-redirector driver to set up a network mini-redirector cancel routine for an RX_CONTEXT structure. |
| [RxSetSrvCallDomainName function](..\rxprocs\nf-rxprocs-rxsetsrvcalldomainname.md) | RxSetSrvCallDomainName is called by a network mini-redirector driver to set the domain name associated with any given server (SRV_CALL structure). |
| [RxSpinDownMRxDispatcher function](..\rxworkq\nf-rxworkq-rxspindownmrxdispatcher.md) | RxSpinDownMRxDispatcher tears down the dispatcher context for a network mini-redirector. |
| [RxStartMinirdr function](..\mrx\nf-mrx-rxstartminirdr.md) | RxStartMinirdr is called to start up a network mini-redirector that has previously called to register with RDBSS. |
| [RxStopMinirdr function](..\mrx\nf-mrx-rxstopminirdr.md) | RxStopMinirdr is called to stop a network mini-redirector that has previously been started. |
| [RxUnregisterMinirdr function](..\rxstruc\nf-rxstruc-rxunregisterminirdr.md) | RxUnregisterMinirdr is an inline routine called by a network mini-redirector driver to de-register the driver with RDBSS and remove the registration information from the internal RDBSS registration table. |
| [RxpAcquirePrefixTableLockExclusive function](..\prefix\nf-prefix-rxpacquireprefixtablelockexclusive.md) | RxpAcquirePrefixTableLockExclusive acquires the prefix table lock exclusively. |
| [RxpAcquirePrefixTableLockShared function](..\prefix\nf-prefix-rxpacquireprefixtablelockshared.md) | RxpAcquirePrefixTableLockShared acquires the prefix table lock shared. |
| [RxpDereferenceAndFinalizeNetFcb function](..\fcb\nf-fcb-rxpdereferenceandfinalizenetfcb.md) | RxpDereferenceAndFinalizeNetFcb decrements the reference count and finalizes an FCB structure. |
| [RxpDereferenceNetFcb function](..\fcb\nf-fcb-rxpdereferencenetfcb.md) | RxpDereferenceNetFcb decrements the reference count on an FCB structure. |
| [RxpReferenceNetFcb function](..\fcb\nf-fcb-rxpreferencenetfcb.md) | RxpReferenceNetFcb increments the reference count on an FCB. |
| [RxpReleasePrefixTableLock function](..\prefix\nf-prefix-rxpreleaseprefixtablelock.md) | RxpReleasePrefixTableLock releases a previously acquired shared or exclusive prefix table lock. |
| [RxpTrackDereference function](..\fcb\nf-fcb-rxptrackdereference.md) | RxpTrackDereference is used in checked builds to track requests to dereference SRV_CALL, NET_ROOT, V_NET_ROOT, FOBX, FCB, and SRV_OPEN structures in checked builds. A log of these dereference requests can be accessed by the logging system and WMI. |
| [RxpTrackReference function](..\fcb\nf-fcb-rxptrackreference.md) | RxpTrackReference tracks requests to reference SRV_CALL, NET_ROOT, V_NET_ROOT, FOBX, FCB, and SRV_OPEN structures in checked builds. A log of these reference requests can be accessed by the logging system and WMI. |
| [RxpUnregisterMinirdr function](..\mrx\nf-mrx-rxpunregisterminirdr.md) | RxpUnregisterMinirdr is called by a network mini-redirector driver to de-register the driver with RDBSS and remove the registration information from the internal RDBSS registration table. |
| [SeAppendPrivileges function](..\ntifs\nf-ntifs-seappendprivileges.md) | The SeAppendPrivileges routine appends additional privileges to the privilege set in an access state structure. |
| [SeAuditHardLinkCreation function](..\ntifs\nf-ntifs-seaudithardlinkcreation.md) | Reserved for system use. |
| [SeAuditingFileEvents function](..\ntifs\nf-ntifs-seauditingfileevents.md) | The SeAuditingFileEvents routine determines whether file open events are currently being audited. |
| [SeAuditingFileOrGlobalEvents function](..\ntifs\nf-ntifs-seauditingfileorglobalevents.md) | The SeAuditingFileOrGlobalEvents routine determines whether file or global events are currently being audited. |
| [SeAuditingHardLinkEvents function](..\ntifs\nf-ntifs-seauditinghardlinkevents.md) | Reserved for system use. |
| [SeCaptureSubjectContext function](..\ntifs\nf-ntifs-secapturesubjectcontext.md) | The SeCaptureSubjectContext routine captures the security context of the calling thread for access validation and auditing. |
| [SeCreateClientSecurity function](..\ntifs\nf-ntifs-secreateclientsecurity.md) | The SeCreateClientSecurity routine initializes a security client context structure with the information needed to call SeImpersonateClientEx. |
| [SeCreateClientSecurityFromSubjectContext function](..\ntifs\nf-ntifs-secreateclientsecurityfromsubjectcontext.md) | The SeCreateClientSecurityFromSubjectContext routine retrieves the access token for a security subject context and uses the result to initialize a security client context with the information needed to call SeImpersonateClientEx. |
| [SeDeleteObjectAuditAlarm function](..\ntifs\nf-ntifs-sedeleteobjectauditalarm.md) | The SeDeleteObjectAuditAlarm routine generates audit and alarm messages for an object that is marked for deletion. |
| [SeFilterToken function](..\ntifs\nf-ntifs-sefiltertoken.md) | The SeFilterToken routine creates a new access token that is a restricted version of an existing access token. |
| [SeImpersonateClient function](..\ntifs\nf-ntifs-seimpersonateclient.md) | Obsolete. |
| [SeImpersonateClientEx function](..\ntifs\nf-ntifs-seimpersonateclientex.md) | The SeImpersonateClientEx routine causes a thread to impersonate a user. |
| [SeLockSubjectContext function](..\ntifs\nf-ntifs-selocksubjectcontext.md) | The SeLockSubjectContext routine locks the primary and impersonation tokens of a captured subject context. |
| [SeMarkLogonSessionForTerminationNotification function](..\ntifs\nf-ntifs-semarklogonsessionforterminationnotification.md) | The SeMarkLogonSessionForTerminationNotification routine marks a logon session so that the caller's registered callback routine is called when the logon session terminates. |
| [SeOpenObjectAuditAlarm function](..\ntifs\nf-ntifs-seopenobjectauditalarm.md) | The SeOpenObjectAuditAlarm routine generates audit and alarm messages when an attempt is made to open an object. |
| [SeOpenObjectForDeleteAuditAlarm function](..\ntifs\nf-ntifs-seopenobjectfordeleteauditalarm.md) | The SeOpenObjectForDeleteAuditAlarm routine generates audit and alarm messages when an attempt is made to open an object for deletion. |
| [SePrivilegeCheck function](..\ntifs\nf-ntifs-seprivilegecheck.md) | The SePrivilegeCheck routine determines whether a specified set of privileges is enabled in the subject's access token. |
| [SeQueryAuthenticationIdToken function](..\ntifs\nf-ntifs-sequeryauthenticationidtoken.md) | The SeQueryAuthenticationIdToken routine retrieves the authentication ID of an access token. |
| [SeQueryInformationToken function](..\ntifs\nf-ntifs-sequeryinformationtoken.md) | The SeQueryInformationToken routine retrieves a specified type of information about an access token. The calling process must have appropriate access rights to obtain the information. |
| [SeQuerySecurityDescriptorInfo function](..\ntifs\nf-ntifs-sequerysecuritydescriptorinfo.md) | The SeQuerySecurityDescriptorInfo routine retrieves a copy of an object's security descriptor. |
| [SeQuerySessionIdToken function](..\ntifs\nf-ntifs-sequerysessionidtoken.md) | Reserved for system use. |
| [SeRegisterLogonSessionTerminatedRoutine function](..\ntifs\nf-ntifs-seregisterlogonsessionterminatedroutine.md) | The SeRegisterLogonSessionTerminatedRoutine routine registers a callback routine to be called when a logon session terminates. A logon session terminates when the last token referencing the logon session is deleted. |
| [SeReleaseSubjectContext function](..\ntifs\nf-ntifs-sereleasesubjectcontext.md) | The SeReleaseSubjectContext routine releases a subject security context captured by an earlier call to SeCaptureSubjectContext. |
| [SeSetAccessStateGenericMapping function](..\ntifs\nf-ntifs-sesetaccessstategenericmapping.md) | The SeSetAccessStateGenericMapping routine sets the generic mapping field of an ACCESS_STATE structure. |
| [SeSetSecurityDescriptorInfo function](..\ntifs\nf-ntifs-sesetsecuritydescriptorinfo.md) | The SeSetSecurityDescriptorInfo routine sets an object's security descriptor. |
| [SeSetSecurityDescriptorInfoEx function](..\ntifs\nf-ntifs-sesetsecuritydescriptorinfoex.md) | The SeSetSecurityDescriptorInfoEx routine modifies an object's security descriptor and specifies whether the object supports automatic inheritance of access control entries (ACE). |
| [SeSetSessionIdToken function](..\ntifs\nf-ntifs-sesetsessionidtoken.md) | Reserved for system use. |
| [SeTokenGetNoChildProcessRestricted function](..\ntifs\nf-ntifs-setokengetnochildprocessrestricted.md) | The SeTokenGetNoChildProcessRestricted routine determines the state of the no child process mitigation. It is not possible to be enforced and audit-only at the same time. |
| [SeTokenIsAdmin function](..\ntifs\nf-ntifs-setokenisadmin.md) | The SeTokenIsAdmin routine determines whether a token contains the local administrators group. |
| [SeTokenIsNoChildProcessRestrictionEnforced function](..\ntifs\nf-ntifs-setokenisnochildprocessrestrictionenforced.md) | The SeTokenIsNoChildProcessRestrictionEnforced routine determines if the token carries the no child process restriction. |
| [SeTokenIsRestricted function](..\ntifs\nf-ntifs-setokenisrestricted.md) | The SeTokenIsRestricted routine determines whether a token contains a list of restricting security identifiers (SID). |
| [SeTokenSetNoChildProcessRestricted function](..\ntifs\nf-ntifs-setokensetnochildprocessrestricted.md) | The SeTokenSetNoChildProcessRestricted routine sets the TOKEN_AUDIT_NO_CHILD_PROCESS or TOKEN_AUDIT_NO_CHILD_PROCESS flags in the token. |
| [SeTokenType function](..\ntifs\nf-ntifs-setokentype.md) | Reserved for system use. |
| [SeUnlockSubjectContext function](..\ntifs\nf-ntifs-seunlocksubjectcontext.md) | The SeUnlockSubjectContext routine unlocks the tokens of a captured subject context that were locked by a call to SeLockSubjectContext. |
| [SeUnregisterLogonSessionTerminatedRoutine function](..\ntifs\nf-ntifs-seunregisterlogonsessionterminatedroutine.md) | The SeUnregisterLogonSessionTerminatedRoutine routine unregisters a callback routine that was registered by an earlier call to SeRegisterLogonSessionTerminatedRoutine. |
| [SecLookupAccountName function](..\ntifs\nf-ntifs-seclookupaccountname.md) | SecLookupAccountName accepts an account as input and retrieves a security identifier (SID) for the account and the name of the domain on which the account was found. |
| [SecLookupAccountSid function](..\ntifs\nf-ntifs-seclookupaccountsid.md) | SecLookupAccountSid accepts a security identifier (SID) as input. It retrieves the name of the account for this SID and the name of the first domain on which this SID is found. |
| [SecLookupWellKnownSid function](..\ntifs\nf-ntifs-seclookupwellknownsid.md) | SecLookupWellKnownSid accepts a well-known security identifier (SID) type as input and retrieves the local security identifier (SID) for this well known SID. |
| [SecMakeSPN function](..\ntifs\nf-ntifs-secmakespn.md) | SecMakeSPN creates a service provider name string that can be used when communicating with specific security service providers. |
| [SecMakeSPNEx function](..\ntifs\nf-ntifs-secmakespnex.md) | SecMakeSPNEx creates a service provider name string that can be used when communicating with specific security service providers. |
| [SecMakeSPNEx2 function](..\ntifs\nf-ntifs-secmakespnex2.md) | SecMakeSPNEx2 creates a service provider name string that can be used when it communicates with specific security service providers. |
| [_RxLog function](..\rxlog\nf-rxlog-_rxlog.md) | "_RxLog takes a format string and variable number of parameters and formats an output string for recording as an I/O error log entry if logging is enabled." |
| [__RxFillAndInstallFastIoDispatch function](..\mrx\nf-mrx-__rxfillandinstallfastiodispatch.md) | RxFillAndInstallFastIoDispatch fills out a fast I/O dispatch vector to be identical with the normal dispatch I/O vector and installs it into the driver object associated with the device object passed. |
| [__RxSynchronizeBlockingOperations function](..\rxcontx\nf-rxcontx-__rxsynchronizeblockingoperations.md) | "__RxSynchronizeBlockingOperations synchronizes blocking I/O requests to the same work queue." |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [DRIVER_FS_NOTIFICATION callback](..\ntifs\nc-ntifs-driver_fs_notification.md) | A PDRIVER_FS_NOTIFICATION-typed routine is called by the operating system when a file system registers or unregisters itself by using IoRegisterFileSystem or IoUnregisterFileSystem. |
| [PFLT_COMPLETED_ASYNC_IO_CALLBACK callback](..\fltkernel\nc-fltkernel-pflt_completed_async_io_callback.md) | A minifilter driver that initiates an asynchronous I/O operation can specify a routine of type PFLT_COMPLETED_ASYNC_IO_CALLBACK routine to be called when the operation is completed. |
| [PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE callback](..\fltkernel\nc-fltkernel-pflt_complete_lock_callback_data_routine.md) | A minifilter driver can register a routine of type PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE as the minifilter driver's CompleteLockCallbackDataRoutine callback routine for a FILE_LOCK structure. |
| [PFLT_CONTEXT_ALLOCATE_CALLBACK callback](..\fltkernel\nc-fltkernel-pflt_context_allocate_callback.md) | A minifilter driver can register a routine of type PFLT_CONTEXT_ALLOCATE_CALLBACK as the minifilter driver's ContextAllocateCallback routine. |
| [PFLT_CONTEXT_CLEANUP_CALLBACK callback](..\fltkernel\nc-fltkernel-pflt_context_cleanup_callback.md) | A minifilter driver can register a routine of type PFLT_CONTEXT_CLEANUP_CALLBACK as the minifilter driver's ContextCleanupCallback routine. |
| [PFLT_CONTEXT_FREE_CALLBACK callback](..\fltkernel\nc-fltkernel-pflt_context_free_callback.md) | A minifilter can register a routine of type PFLT_CONTEXT_FREE_CALLBACK as the minifilter driver's ContextFreeCallback routine. |
| [PFLT_FILTER_UNLOAD_CALLBACK callback](..\fltkernel\nc-fltkernel-pflt_filter_unload_callback.md) | A minifilter driver can register a routine of type PFLT_FILTER_UNLOAD_CALLBACK as the minifilter driver's FilterUnloadCallback routine. |
| [PFLT_GENERATE_FILE_NAME callback](..\fltkernel\nc-fltkernel-pflt_generate_file_name.md) | A minifilter driver that provides file names for the filter manager's name cache can register a routine of type PFLT_GENERATE_FILE_NAME as the minifilter driver's GenerateFileNameCallback routine. |
| [PFLT_GET_OPERATION_STATUS_CALLBACK callback](..\fltkernel\nc-fltkernel-pflt_get_operation_status_callback.md) | A minifilter driver can register a routine of type PFLT_GET_OPERATION_STATUS_CALLBACK as the minifilter driver's OperationStatusCallback routine. |
| [PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK callback](..\fltkernel\nc-fltkernel-pflt_instance_query_teardown_callback.md) | A minifilter driver can register a routine of type PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK as the minifilter driver's InstanceQueryTeardownCallback routine. |
| [PFLT_INSTANCE_SETUP_CALLBACK callback](..\fltkernel\nc-fltkernel-pflt_instance_setup_callback.md) | A minifilter driver can register a routine of type PFLT_INSTANCE_SETUP_CALLBACK as the minifilter driver's InstanceSetupCallback routine. |
| [PFLT_INSTANCE_TEARDOWN_CALLBACK callback](..\fltkernel\nc-fltkernel-pflt_instance_teardown_callback.md) | A minifilter driver can register two routines of type PFLT_INSTANCE_TEARDOWN_CALLBACK as the minifilter driver's InstanceTeardownStartCallback and InstanceTeardownCompleteCallback routines. |
| [PFLT_NORMALIZE_CONTEXT_CLEANUP callback](..\fltkernel\nc-fltkernel-pflt_normalize_context_cleanup.md) | A minifilter driver that provides file names for the filter manager's name cache can register a routine of type PFLT_NORMALIZE_CONTEXT_CLEANUP as the minifilter driver's NormalizeContextCleanupCallback routine. |
| [PFLT_NORMALIZE_NAME_COMPONENT callback](..\fltkernel\nc-fltkernel-pflt_normalize_name_component.md) | A minifilter driver that provides file names for the filter manager's name cache can register a routine of type PFLT_NORMALIZE_NAME_COMPONENT as the minifilter driver's NormalizeNameComponentCallback routine. |
| [PFLT_NORMALIZE_NAME_COMPONENT_EX callback](..\fltkernel\nc-fltkernel-pflt_normalize_name_component_ex.md) | A minifilter driver that provides file names for the filter manager's name cache can register a routine of type PFLT_NORMALIZE_NAME_COMPONENT_EX as the minifilter driver's NormalizeNameComponentExCallback callback routine. |
| [PFLT_POST_OPERATION_CALLBACK callback](..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md) | A minifilter driver can register one or more routines of type PFLT_POST_OPERATION_CALLBACK to perform completion processing for I/O operations. |
| [PFLT_PRE_OPERATION_CALLBACK callback](..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md) | A minifilter driver's PFLT_PRE_OPERATION_CALLBACK routine performs pre-operation processing for I/O operations. |
| [PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK callback](..\fltkernel\nc-fltkernel-pflt_section_conflict_notification_callback.md) | A minifilter driver can optionally register a routine of type PFLT_CONTEXT_ALLOCATE_CALLBACK as the minifilter driver's SectionNotificationCallback routine. |
| [PFLT_TRANSACTION_NOTIFICATION_CALLBACK callback](..\fltkernel\nc-fltkernel-pflt_transaction_notification_callback.md) | A minifilter driver can register a routine of type PFLT_TRANSACTION_NOTIFICATION_CALLBACK as its TransactionNotificationCallback routine. |
| [PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK callback](..\ntifs\nc-ntifs-pfsrtl_extra_create_parameter_cleanup_callback.md) | A file system filter driver (legacy filter) or a minifilter driver can register a PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK-typed routine as the filter driver's CleanupCallback callback routine for an extra create parameter (ECP) context structure. |
| [PMRX_CALLDOWN callback](..\mrx\nc-mrx-pmrx_calldown.md) | This callback is called by RDBSS to request that the network mini-redirector perform an action based in the supplied IRP. |
| [PMRX_CALLDOWN_CTX callback](..\mrx\nc-mrx-pmrx_calldown_ctx.md) | TheMRxStart routine is called by RDBSS to start the network mini-redirector. |
| [PMRX_CHANGE_BUFFERING_STATE_CALLDOWN callback](..\mrx\nc-mrx-pmrx_change_buffering_state_calldown.md) | TheMRxCompleteBufferingStateChangeRequest routine is called by RDBSS to notify the network mini-redirector that a buffering state change request has been completed. |
| [PMRX_CHKDIR_CALLDOWN callback](..\mrx\nc-mrx-pmrx_chkdir_calldown.md) | TheMRxIsValidDirectory routine is called by RDBSS to request that a network mini-redirector check for the existence of a remote directory. |
| [PMRX_CHKFCB_CALLDOWN callback](..\mrx\nc-mrx-pmrx_chkfcb_calldown.md) | The MRxAreFilesAliased routine is called by RDBSS to request the network mini-redirector to determine if two FCB structures represent the same file. |
| [PMRX_COMPUTE_NEW_BUFFERING_STATE callback](..\mrx\nc-mrx-pmrx_compute_new_buffering_state.md) | TheMRxComputeNewBufferingState routine is called by RDBSS to request that the network mini-redirector compute a new buffering state change. |
| [PMRX_CREATE_SRVCALL callback](..\mrx\nc-mrx-pmrx_create_srvcall.md) | The MRxCreateSrvCall routine is called by RDBSS to request that the network mini-redirector create an SRV_CALL structure and establish connection with a server. |
| [PMRX_CREATE_V_NET_ROOT callback](..\mrx\nc-mrx-pmrx_create_v_net_root.md) | The MRxCreateVNetRoot routine is called by RDBSS to request that the network mini-redirector create a V_NET_ROOT structure and, in some cases, a NET_ROOT structure. |
| [PMRX_DEALLOCATE_FOR_FCB callback](..\mrx\nc-mrx-pmrx_deallocate_for_fcb.md) | The MRxDeallocateForFcb routine is called by RDBSS to request that the network mini-redirector deallocate an FCB structure. This call is in response to a request to close a file system object. |
| [PMRX_DEALLOCATE_FOR_FOBX callback](..\mrx\nc-mrx-pmrx_deallocate_for_fobx.md) | The MRxDeallocateForFobx routine is called by RDBSS to request that the network mini-redirector deallocate an FOBX structure. This call is in response to a request to close a file system object. |
| [PMRX_EXTENDFILE_CALLDOWN callback](..\mrx\nc-mrx-pmrx_extendfile_calldown.md) | The MRxExtendForCache routine is called by RDBSS to request that a network mini-redirector extend a file when the file is being cached by the cache manager. |
| [PMRX_EXTRACT_NETROOT_NAME callback](..\mrx\nc-mrx-pmrx_extract_netroot_name.md) | The MRxExtractNetRootName routine is called by RDBSS to request that a network mini-redirector extract the name of the NET_ROOT structure from a given pathname. |
| [PMRX_FINALIZE_NET_ROOT_CALLDOWN callback](..\mrx\nc-mrx-pmrx_finalize_net_root_calldown.md) | The MRxFinalizeNetRoot routine is called by RDBSS to request that a network mini-redirector finalize a NET_ROOT structure. |
| [PMRX_FINALIZE_SRVCALL_CALLDOWN callback](..\mrx\nc-mrx-pmrx_finalize_srvcall_calldown.md) | The MRxFinalizeSrvCall routine is called by RDBSS to request that a network mini-redirector finalize an SRV_CALL structure. |
| [PMRX_FINALIZE_V_NET_ROOT_CALLDOWN callback](..\mrx\nc-mrx-pmrx_finalize_v_net_root_calldown.md) | The MRxFinalizeVNetRoot routine is called by RDBSS to request that a network mini-redirector finalize a V_NET_ROOT structure. |
| [PMRX_FORCECLOSED_CALLDOWN callback](..\mrx\nc-mrx-pmrx_forceclosed_calldown.md) | The MRxForceClosed routine is called by RDBSS to request that a network mini-redirector force a close. This routine is called when the condition of the SRV_OPEN structure is not good or the SRV_OPEN structure is marked as closed. |
| [PMRX_GET_CONNECTION_ID callback](..\mrx\nc-mrx-pmrx_get_connection_id.md) | TheMRxGetConnectionId routine is called by RDBSS to request that a network mini-redirector return a connection ID, which can be used for handling multiple sessions. |
| [PMRX_IS_LOCK_REALIZABLE callback](..\mrx\nc-mrx-pmrx_is_lock_realizable.md) | The MRxIsLockRealizable routine is called by RDBSS to request that a network mini-redirector indicate whether a specific byte-range lock is supported on this NET_ROOT structure. |
| [PMRX_PREPARSE_NAME callback](..\mrx\nc-mrx-pmrx_preparse_name.md) | The MRxPreparseName routine is called by RDBSS to give a network mini-redirector the opportunity to preparse a name. |
| [PMRX_SRVCALL_WINNER_NOTIFY callback](..\mrx\nc-mrx-pmrx_srvcall_winner_notify.md) | The MRxSrvCallWinnerNotify routine is called by RDBSS to notify a network mini-redirector that it was chosen when multiple redirectors could fulfill the request. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [MARK_HANDLE_INFO32 structure](..\ntifs\ns-ntifs-mark_handle_info32.md) | Contains information that is used to mark a specified file or directory, and its update sequence number (USN) change journal record with data about changes. |
| [_ACCESS_ALLOWED_ACE structure](..\ntifs\ns-ntifs-_access_allowed_ace.md) | The ACCESS_ALLOWED_ACE structure defines an access-control entry (ACE) for the discretionary access-control list (DACL) that controls access to an object. |
| [_ACCESS_DENIED_ACE structure](..\ntifs\ns-ntifs-_access_denied_ace.md) | The ACCESS_DENIED_ACE structure defines an access-control entry (ACE) for the discretionary access-control list (DACL) controlling access to an object. |
| [_ACE_HEADER structure](..\ntifs\ns-ntifs-_ace_header.md) | The ACE_HEADER structure describes the type and size of an access-control entry (ACE). |
| [_ATOMIC_CREATE_ECP_CONTEXT structure](..\ntifs\ns-ntifs-_atomic_create_ecp_context.md) | This structure allows supplemental operations to be performed on a file atomically during create. |
| [_BOOT_AREA_INFO structure](..\ntifs\ns-ntifs-_boot_area_info.md) | The BOOT_AREA_INFO structure contains the output for the FSCTL_GET_BOOT_AREA_INFO control code. |
| [_ECP_OPEN_PARAMETERS structure](..\ntifs\ns-ntifs-_ecp_open_parameters.md) | The ECP_OPEN_PARAMETERS structure allows a caller to specify the purpose of opening of a file without interfering with existing handles and/or oplocks on the file. |
| [_FILE_ALLOCATION_INFORMATION structure](..\ntifs\ns-ntifs-_file_allocation_information.md) | The FILE_ALLOCATION_INFORMATION structure is used to set the allocation size for a file. |
| [_FILE_BOTH_DIR_INFORMATION structure](..\ntifs\ns-ntifs-_file_both_dir_information.md) | The FILE_BOTH_DIR_INFORMATION structure is used to query detailed information for the files in a directory. |
| [_FILE_COMPLETION_INFORMATION structure](..\ntifs\ns-ntifs-_file_completion_information.md) | The FILE_COMPLETION_INFORMATION structure contains the port handle and key for an I/O completion port created for a file handle. |
| [_FILE_COMPRESSION_INFORMATION structure](..\ntifs\ns-ntifs-_file_compression_information.md) | The FILE_COMPRESSION_INFORMATION structure describes the state of a compressed data buffer. |
| [_FILE_DIRECTORY_INFORMATION structure](..\ntifs\ns-ntifs-_file_directory_information.md) | The FILE_DIRECTORY_INFORMATION structure is used to query detailed information for the files in a directory. |
| [_FILE_FS_ATTRIBUTE_INFORMATION structure](..\ntifs\ns-ntifs-_file_fs_attribute_information.md) | The FILE_FS_ATTRIBUTE_INFORMATION structure is used to query attribute information for a file system. |
| [_FILE_FS_CONTROL_INFORMATION structure](..\ntifs\ns-ntifs-_file_fs_control_information.md) | The FILE_FS_CONTROL_INFORMATION structure is used to query or set control information for the files in a directory. |
| [_FILE_FS_DRIVER_PATH_INFORMATION structure](..\ntifs\ns-ntifs-_file_fs_driver_path_information.md) | The FILE_FS_DRIVER_PATH_INFORMATION structure is used to query whether a given driver is in the I/O path for a file system volume. |
| [_FILE_FS_PERSISTENT_VOLUME_INFORMATION structure](..\ntifs\ns-ntifs-_file_fs_persistent_volume_information.md) | The FILE_FS_PERSISTENT_VOLUME_INFORMATION structure is used to control persistent settings for a file system volume. Persistent settings persist on a file system volume between reboots of the computer. |
| [_FILE_FULL_DIR_INFORMATION structure](..\ntifs\ns-ntifs-_file_full_dir_information.md) | The FILE_FULL_DIR_INFORMATION structure is used to query detailed information for the files in a directory. |
| [_FILE_GET_EA_INFORMATION structure](..\ntifs\ns-ntifs-_file_get_ea_information.md) | The FILE_GET_EA_INFORMATION structure is used to query for extended-attribute (EA) information. |
| [_FILE_GET_QUOTA_INFORMATION structure](..\ntifs\ns-ntifs-_file_get_quota_information.md) | The FILE_GET_QUOTA_INFORMATION structure is used to query for quota information. |
| [_FILE_ID_BOTH_DIR_INFORMATION structure](..\ntifs\ns-ntifs-_file_id_both_dir_information.md) | The FILE_ID_BOTH_DIR_INFORMATION structure is used to query file reference number information for the files in a directory. |
| [_FILE_ID_EXTD_BOTH_DIR_INFORMATION structure](..\ntifs\ns-ntifs-_file_id_extd_both_dir_information.md) | The FILE_ID_EXTD_BOTH_DIR_INFORMATION structure is used to query file reference number information for the files in a directory. |
| [_FILE_ID_FULL_DIR_INFORMATION structure](..\ntifs\ns-ntifs-_file_id_full_dir_information.md) | The FILE_ID_FULL_DIR_INFORMATION structure is used to query detailed information for the files in a directory. |
| [_FILE_ID_GLOBAL_TX_DIR_INFORMATION structure](..\ntifs\ns-ntifs-_file_id_global_tx_dir_information.md) | The FILE_ID_GLOBAL_TX_DIR_INFORMATION structure contains information about transactional visibility for the files in a directory. |
| [_FILE_INTERNAL_INFORMATION structure](..\ntifs\ns-ntifs-_file_internal_information.md) | The FILE_INTERNAL_INFORMATION structure is used to query for the file system's 8-byte file reference number for a file. |
| [_FILE_LEVEL_TRIM structure](..\ntifs\ns-ntifs-_file_level_trim.md) | The FILE_LEVEL_TRIM structure contains an array of byte ranges to trim for a file. |
| [_FILE_LEVEL_TRIM_OUTPUT structure](..\ntifs\ns-ntifs-_file_level_trim_output.md) | The FILE_LEVEL_TRIM_OUTPUT structure contains the results of a trim operation performed by an FSCTL_FILE_LEVEL_TRIM request. |
| [_FILE_LEVEL_TRIM_RANGE structure](..\ntifs\ns-ntifs-_file_level_trim_range.md) | Contains the offset and length of a trim range for a file. |
| [_FILE_LINKS_INFORMATION structure](..\ntifs\ns-ntifs-_file_links_information.md) | The FILE_LINKS_INFORMATION structure is used to query NTFS hard links to an existing file. |
| [_FILE_LINK_ENTRY_INFORMATION structure](..\ntifs\ns-ntifs-_file_link_entry_information.md) | The FILE_LINK_ENTRY_INFORMATION structure describes a single NTFS hard link to an existing file. |
| [_FILE_LINK_INFORMATION structure](..\ntifs\ns-ntifs-_file_link_information.md) | The FILE_LINK_INFORMATION structure is used to create an NTFS hard link to an existing file. |
| [_FILE_MAILSLOT_QUERY_INFORMATION structure](..\ntifs\ns-ntifs-_file_mailslot_query_information.md) | The FILE_MAILSLOT_QUERY_INFORMATION structure contains information about a mailslot. |
| [_FILE_MAILSLOT_SET_INFORMATION structure](..\ntifs\ns-ntifs-_file_mailslot_set_information.md) | The FILE_MAILSLOT_SET_INFORMATION structure is used to set a value on a mailslot. |
| [_FILE_NAMES_INFORMATION structure](..\ntifs\ns-ntifs-_file_names_information.md) | A FILE_NAMES_INFORMATION structure used to query detailed information about the names of files in a directory. |
| [_FILE_NETWORK_PHYSICAL_NAME_INFORMATION structure](..\ntifs\ns-ntifs-_file_network_physical_name_information.md) | Contains the full UNC physical pathname for a file or directory on a remote file share. |
| [_FILE_OBJECTID_INFORMATION structure](..\ntifs\ns-ntifs-_file_objectid_information.md) | The FILE_OBJECTID_INFORMATION structure is used to query for object ID information for the files in a directory on an NTFS volume. |
| [_FILE_PIPE_INFORMATION structure](..\ntifs\ns-ntifs-_file_pipe_information.md) | The FILE_PIPE_INFORMATION structure contains information about a named pipe that is not specific to the local or the remote end of the pipe. |
| [_FILE_PIPE_LOCAL_INFORMATION structure](..\ntifs\ns-ntifs-_file_pipe_local_information.md) | The FILE_PIPE_LOCAL_INFORMATION structure contains information about the local end of a named pipe. |
| [_FILE_PIPE_REMOTE_INFORMATION structure](..\ntifs\ns-ntifs-_file_pipe_remote_information.md) | The FILE_PIPE_REMOTE_INFORMATION structure contains information about the remote end of a named pipe. |
| [_FILE_PROVIDER_EXTERNAL_INFO_V0 structure](..\ntifs\ns-ntifs-_file_provider_external_info_v0.md) | This structure may be altered or unavailable. Instead, use FILE_PROVIDER_EXTERNAL_INFO_V1. |
| [_FILE_PROVIDER_EXTERNAL_INFO_V1 structure](..\ntifs\ns-ntifs-_file_provider_external_info_v1.md) | The FILE_PROVIDER_EXTERNAL_INFO_V1 structure defines metadata specific to files provided by WOF_PROVIDER_FILE. |
| [_FILE_QUOTA_INFORMATION structure](..\ntifs\ns-ntifs-_file_quota_information.md) | The FILE_QUOTA_INFORMATION structure is used to query or set per-user quota information for each of the files in a directory. |
| [_FILE_RENAME_INFORMATION structure](..\ntifs\ns-ntifs-_file_rename_information.md) | The FILE_RENAME_INFORMATION structure is used to rename a file. |
| [_FILE_REPARSE_POINT_INFORMATION structure](..\ntifs\ns-ntifs-_file_reparse_point_information.md) | The FILE_REPARSE_POINT_INFORMATION structure is used to query for information about a reparse point. |
| [_FILE_STREAM_INFORMATION structure](..\ntifs\ns-ntifs-_file_stream_information.md) | The FILE_STREAM_INFORMATION structure is used to enumerate the streams for a file. |
| [_FILE_TIMESTAMPS structure](..\ntifs\ns-ntifs-_file_timestamps.md) | The FILE_TIMESTAMPS structure specifies the last recorded instance of specific actions on a file. |
| [_FILE_ZERO_DATA_INFORMATION structure](..\ntifs\ns-ntifs-_file_zero_data_information.md) | Contains a range of a file to set to zeros. |
| [_FILE_ZERO_DATA_INFORMATION_EX structure](..\ntifs\ns-ntifs-_file_zero_data_information_ex.md) | Contains a range of a file to set to zeros. |
| [_FILTER_AGGREGATE_BASIC_INFORMATION structure](..\fltuserstructures\ns-fltuserstructures-_filter_aggregate_basic_information.md) | The FILTER_AGGREGATE_BASIC_INFORMATION structure contains basic information for a minifilter or legacy filter driver. |
| [_FILTER_AGGREGATE_STANDARD_INFORMATION structure](..\fltuserstructures\ns-fltuserstructures-_filter_aggregate_standard_information.md) | The FILTER_AGGREGATE_STANDARD_INFORMATION structure contains information about a minifilter or legacy filter driver. |
| [_FILTER_FULL_INFORMATION structure](..\fltuserstructures\ns-fltuserstructures-_filter_full_information.md) | The FILTER_FULL_INFORMATION structure contains full information for a minifilter driver. |
| [_FILTER_MESSAGE_HEADER structure](..\fltuserstructures\ns-fltuserstructures-_filter_message_header.md) | The FILTER_MESSAGE_HEADER structure contains message header information. |
| [_FILTER_REPLY_HEADER structure](..\fltuserstructures\ns-fltuserstructures-_filter_reply_header.md) | The FILTER_REPLY_HEADER structure contains message reply header information. |
| [_FILTER_VOLUME_BASIC_INFORMATION structure](..\fltuserstructures\ns-fltuserstructures-_filter_volume_basic_information.md) | The caller-allocated FILTER_VOLUME_BASIC_INFORMATION structure contains basic information for a volume. |
| [_FILTER_VOLUME_STANDARD_INFORMATION structure](..\fltuserstructures\ns-fltuserstructures-_filter_volume_standard_information.md) | The caller-allocated FILTER_VOLUME_STANDARD_INFORMATION structure contains information for a volume. |
| [_FLT_CALLBACK_DATA structure](..\fltkernel\ns-fltkernel-_flt_callback_data.md) | The FLT_CALLBACK_DATA structure represents an I/O operation. The Filter Manager and minifilters use this structure to initiate and process I/O operations. |
| [_FLT_CALLBACK_DATA_QUEUE structure](..\fltkernel\ns-fltkernel-_flt_callback_data_queue.md) | FLT_CALLBACK_DATA_QUEUE is an opaque structure that is used to specify the callback routines for a minifilter's callback data queue. Do not set the members of this structure directly. Use FltCbdqInitialize to initialize this structure. |
| [_FLT_CONTEXT_REGISTRATION structure](..\fltkernel\ns-fltkernel-_flt_context_registration.md) | The FLT_CONTEXT_REGISTRATION structure is used to register context types. |
| [_FLT_CREATEFILE_TARGET_ECP_CONTEXT structure](..\fltkernel\ns-fltkernel-_flt_createfile_target_ecp_context.md) | The FLT_CREATEFILE_TARGET_ECP_CONTEXT structure is an extra create parameter (ECP) used to return reparse target information back to the caller of FltCreateFileEx2. |
| [_FLT_FILE_NAME_INFORMATION structure](..\fltkernel\ns-fltkernel-_flt_file_name_information.md) | The FLT_FILE_NAME_INFORMATION structure contains file name information. |
| [_FLT_IO_PARAMETER_BLOCK structure](..\fltkernel\ns-fltkernel-_flt_io_parameter_block.md) | The FLT_IO_PARAMETER_BLOCK structure contains the parameters for the I/O operation that is represented by a callback data (FLT_CALLBACK_DATA) structure. |
| [_FLT_NAME_CONTROL structure](..\fltkernel\ns-fltkernel-_flt_name_control.md) | A minifilter that provides file names for the Filter Manager's name cache can use the FLT_NAME_CONTROL structure to manage its name buffers. |
| [_FLT_OPERATION_REGISTRATION structure](..\fltkernel\ns-fltkernel-_flt_operation_registration.md) | The FLT_OPERATION_REGISTRATION structure is used to register operation callback routines. |
| [_FLT_PARAMETERS structure](..\fltkernel\ns-fltkernel-_flt_parameters.md) | The FLT_PARAMETERS union defines the request-type-specific parameters associated with an I/O operation. |
| [_FLT_REGISTRATION structure](..\fltkernel\ns-fltkernel-_flt_registration.md) | The FLT_REGISTRATION structure is passed as a parameter to FltRegisterFilter. |
| [_FLT_RELATED_CONTEXTS structure](..\fltkernel\ns-fltkernel-_flt_related_contexts.md) | The FLT_RELATED_CONTEXTS structure contains a minifilter driver's contexts for the objects associated with an I/O operation. |
| [_FLT_RELATED_CONTEXTS_EX structure](..\fltkernel\ns-fltkernel-_flt_related_contexts_ex.md) | The FLT_RELATED_CONTEXTS_EX structure contains a minifilter driver's contexts for the objects associated with an I/O operation. |
| [_FLT_RELATED_OBJECTS structure](..\fltkernel\ns-fltkernel-_flt_related_objects.md) | The FLT_RELATED_OBJECTS structure contains opaque pointers for the objects associated with an operation. |
| [_FLT_TAG_DATA_BUFFER structure](..\fltkernel\ns-fltkernel-_flt_tag_data_buffer.md) | The FLT_TAG_DATA_BUFFER structure contains information about a reparse point tag. |
| [_FLT_VOLUME_PROPERTIES structure](..\fltkernel\ns-fltkernel-_flt_volume_properties.md) | The FLT_VOLUME_PROPERTIES structure is passed as a parameter to FltGetVolumeProperties. |
| [_FSCTL_OFFLOAD_READ_INPUT structure](..\ntifs\ns-ntifs-_fsctl_offload_read_input.md) | The FSCTL_OFFLOAD_READ_INPUT structure contains the input for the FSCTL_OFFLOAD_READ control code request. |
| [_FSCTL_OFFLOAD_READ_OUTPUT structure](..\ntifs\ns-ntifs-_fsctl_offload_read_output.md) | The FSCTL_OFFLOAD_READ_OUTPUT structure contains the output for the FSCTL_OFFLOAD_READ control code request. |
| [_FSCTL_OFFLOAD_WRITE_INPUT structure](..\ntifs\ns-ntifs-_fsctl_offload_write_input.md) | The FSCTL_OFFLOAD_WRITE_INPUT structure contains the input for the FSCTL_OFFLOAD_WRITE control code request. |
| [_FSCTL_OFFLOAD_WRITE_OUTPUT structure](..\ntifs\ns-ntifs-_fsctl_offload_write_output.md) | The FSCTL_OFFLOAD_WRITE_OUTPUT structure contains the output for the FSCTL_OFFLOAD_WRITE control code request. |
| [_FSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT structure](..\ntifs\ns-ntifs-_fsctl_query_volume_numa_info_output.md) | The FSCTL_QUERY_VOLUME_NUMA_INFO_OUTPUT structure specifies the Non-Uniform Memory Architecture (NUMA) node the volume resides on. |
| [_FSRTL_ADVANCED_FCB_HEADER structure](..\ntifs\ns-ntifs-_fsrtl_advanced_fcb_header.md) | The FSRTL_ADVANCED_FCB_HEADER structure contains context information that a file system maintains about a file. |
| [_FSRTL_COMMON_FCB_HEADER structure](..\ntifs\ns-ntifs-_fsrtl_common_fcb_header.md) | Do not use the FSRTL_COMMON_FCB_HEADER structure outside of the FSRTL_ADVANCED_FCB_HEADER structure. |
| [_FSRTL_PER_FILEOBJECT_CONTEXT structure](..\ntifs\ns-ntifs-_fsrtl_per_fileobject_context.md) | The opaque FSRTL_PER_FILEOBJECT_CONTEXT structure is used by the operating system to track file system filter-driver-defined context information structures for a file object. |
| [_FSRTL_PER_FILE_CONTEXT structure](..\ntifs\ns-ntifs-_fsrtl_per_file_context.md) | A legacy file system filter driver can use a FSRTL_PER_FILE_CONTEXT structure to associate driver-specific context information to an open file. |
| [_FSRTL_PER_STREAM_CONTEXT structure](..\ntifs\ns-ntifs-_fsrtl_per_stream_context.md) | The FSRTL_PER_STREAM_CONTEXT structure contains context information that a file system filter driver maintains about a file stream. |
| [_FS_FILTER_SECTION_SYNC_OUTPUT structure](..\ntifs\ns-ntifs-_fs_filter_section_sync_output.md) | The FS_FILTER_SECTION_SYNC_OUTPUT structure contains information describing the attributes of the section that is being created. |
| [_INSTANCE_AGGREGATE_STANDARD_INFORMATION structure](..\fltuserstructures\ns-fltuserstructures-_instance_aggregate_standard_information.md) | The caller-allocated INSTANCE_AGGREGATE_STANDARD_INFORMATION structure contains information for either a minifilter driver instance or a legacy filter driver. |
| [_INSTANCE_BASIC_INFORMATION structure](..\fltuserstructures\ns-fltuserstructures-_instance_basic_information.md) | The INSTANCE_BASIC_INFORMATION structure contains basic information for a minifilter instance. |
| [_INSTANCE_FULL_INFORMATION structure](..\fltuserstructures\ns-fltuserstructures-_instance_full_information.md) | The INSTANCE_FULL_INFORMATION structure contains full information for a minifilter instance. |
| [_INSTANCE_PARTIAL_INFORMATION structure](..\fltuserstructures\ns-fltuserstructures-_instance_partial_information.md) | The INSTANCE_PARTIAL_INFORMATION structure contains partial information for a minifilter instance. |
| [_IO_PRIORITY_INFO structure](..\ntifs\ns-ntifs-_io_priority_info.md) | The IO_PRIORITY_INFO structure is used to hold thread priority information. |
| [_NETWORK_APP_INSTANCE_ECP_CONTEXT structure](..\ntifs\ns-ntifs-_network_app_instance_ecp_context.md) | The NETWORK_APP_INSTANCE_ECP_CONTEXT structure is an Extra Create Parameter (ECP) and contains an application instance identifier to associate with a file. |
| [_NETWORK_OPEN_ECP_CONTEXT structure](..\ntifs\ns-ntifs-_network_open_ecp_context.md) | The NETWORK_OPEN_ECP_CONTEXT structure is used to interpret network ECP contexts on files. |
| [_NETWORK_OPEN_ECP_CONTEXT_V0 structure](..\ntifs\ns-ntifs-_network_open_ecp_context_v0.md) | The NETWORK_OPEN_ECP_CONTEXT_V0 structure is used to interpret network ECP contexts on files. |
| [_NFS_OPEN_ECP_CONTEXT structure](..\ntifs\ns-ntifs-_nfs_open_ecp_context.md) | The NFS_OPEN_ECP_CONTEXT structure is used by the Network File System (NFS) server to open files in response to client requests. |
| [_OPEN_REPARSE_LIST structure](..\ntifs\ns-ntifs-_open_reparse_list.md) | Points to a list of OPEN_REPARSE_LIST_ENTRY structures that specify the tag and possibly GUID that should be opened directly without returning STATUS_REPARSE. |
| [_OPEN_REPARSE_LIST_ENTRY structure](..\ntifs\ns-ntifs-_open_reparse_list_entry.md) | This structure supports callers opening specific reparse points without inhibiting reparse behavior for all classes of reparse points. |
| [_PREFETCH_OPEN_ECP_CONTEXT structure](..\ntifs\ns-ntifs-_prefetch_open_ecp_context.md) | The PREFETCH_OPEN_ECP_CONTEXT structure communicates whether the prefetcher performs a given open request on a file. |
| [_PUBLIC_OBJECT_BASIC_INFORMATION structure](..\ntifs\ns-ntifs-_public_object_basic_information.md) | The PUBLIC_OBJECT_BASIC_INFORMATION structure holds a subset of the full information that is available for an object. |
| [_QUERY_FILE_LAYOUT_INPUT structure](..\ntifs\ns-ntifs-_query_file_layout_input.md) | The QUERY_FILE_LAYOUT_INPUT structure selects which file layout entries are returned from a FSCTL_QUERY_FILE_LAYOUT request. |
| [_QUERY_FILE_LAYOUT_OUTPUT structure](..\ntifs\ns-ntifs-_query_file_layout_output.md) | The QUERY_FILE_LAYOUT_OUTPUT structure serves as a header for the file layout entries that are returned from a FSCTL_QUERY_FILE_LAYOUT request. |
| [_REFS_SMR_VOLUME_GC_PARAMETERS structure](..\ntifs\ns-ntifs-_refs_smr_volume_gc_parameters.md) | The REFS_SMR_VOLUME_GC_PARAMETERS structure. |
| [_REFS_SMR_VOLUME_INFO_OUTPUT structure](..\ntifs\ns-ntifs-_refs_smr_volume_info_output.md) | The REFS_SMR_VOLUME_INFO_OUTPUT structure describes a Shingled Magnetic Recording (SMR) volume's current state on space and garbage collection activities. |
| [_REPARSE_DATA_BUFFER structure](..\ntifs\ns-ntifs-_reparse_data_buffer.md) | The REPARSE_DATA_BUFFER structure contains reparse point data for a Microsoft reparse point. |
| [_REPARSE_GUID_DATA_BUFFER structure](..\ntifs\ns-ntifs-_reparse_guid_data_buffer.md) | The REPARSE_GUID_DATA_BUFFER structure contains reparse point data for a reparse point. |
| [_RX_CONTEXT structure](..\rxcontx\ns-rxcontx-_rx_context.md) | The RX_CONTEXT structure encapsulates an IRP for use by RDBSS, network mini-redirectors, and the file system. |
| [_SECURITY_DESCRIPTOR structure](..\ntifs\ns-ntifs-_security_descriptor.md) | The SECURITY_DESCRIPTOR structure contains the security information associated with an object. Drivers use this structure to set and query an object's security status. |
| [_SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT structure](..\ntifs\ns-ntifs-_set_dax_alloc_alignment_hint_input.md) | This structure is for internal use only and should not be called from your code. |
| [_SE_EXPORTS structure](..\ntifs\ns-ntifs-_se_exports.md) | The SeExports structure is a large external static SE_EXPORTS structure that defines a number of well-known security constants for privilege values and security identifiers. |
| [_SE_SID structure](..\ntifs\ns-ntifs-_se_sid.md) | The SE_SID union holds the maximum-sized valid Security Identifier (SID). The structure occupies 68-bytes and is suitable for stack allocation. |
| [_SE_TOKEN_USER structure](..\ntifs\ns-ntifs-_se_token_user.md) | The SE_TOKEN_USER structure holds the maximum-sized valid user SID that can be returned by SeQueryInformationToken, GetTokenInformation, or ZwQueryInformationToken with the TokenUser information class. This structure is suitable for stack allocation. |
| [_SID structure](..\ntifs\ns-ntifs-_sid.md) | The security identifier (SID) structure is a variable-length structure used to uniquely identify users or groups. |
| [_SID_AND_ATTRIBUTES structure](..\ntifs\ns-ntifs-_sid_and_attributes.md) | The SID_AND_ATTRIBUTES structure represents a security identifier (SID) and its attributes. SIDs are used to uniquely identify users or groups. |
| [_SID_IDENTIFIER_AUTHORITY structure](..\ntifs\ns-ntifs-_sid_identifier_authority.md) | The SID_IDENTIFIER_AUTHORITY structure represents the top-level authority of a security identifier (SID). |
| [_SRV_OPEN_ECP_CONTEXT structure](..\ntifs\ns-ntifs-_srv_open_ecp_context.md) | The SRV_OPEN_ECP_CONTEXT structure is used by a server to conditionally open files in response to client requests. |
| [_SYSTEM_ALARM_ACE structure](..\ntifs\ns-ntifs-_system_alarm_ace.md) | Reserved for future use. |
| [_SYSTEM_AUDIT_ACE structure](..\ntifs\ns-ntifs-_system_audit_ace.md) | The SYSTEM_AUDIT_ACE structure defines an access-control entry (ACE) for the system access-control list (ACL) specifying what types of access cause system-level notifications. |
| [_SYSTEM_PROCESS_TRUST_LABEL_ACE structure](..\ntifs\ns-ntifs-_system_process_trust_label_ace.md) | Reserved. |
| [_SYSTEM_RESOURCE_ATTRIBUTE_ACE structure](..\ntifs\ns-ntifs-_system_resource_attribute_ace.md) | The SYSTEM_RESOURCE_ATTRIBUTE_ACE structure defines an access-control entry (ACE) for the system access-control list (ACL) specifying what rights a particular claim has to a resource. |
| [_SYSTEM_SCOPED_POLICY_ID_ACE structure](..\ntifs\ns-ntifs-_system_scoped_policy_id_ace.md) | The SYSTEM_SCOPED_POLICY_ID_ACE structure defines an access-control entry (ACE) for the system access-control list (ACL) specifying rights for a scoped policy identifer. |
| [_TOKEN_CONTROL structure](..\ntifs\ns-ntifs-_token_control.md) | The TOKEN_CONTROL structure contains information that identifies an access token. |
| [_TOKEN_DEFAULT_DACL structure](..\ntifs\ns-ntifs-_token_default_dacl.md) | The TOKEN_DEFAULT_DACL structure specifies a discretionary access-control list (DACL). |
| [_TOKEN_GROUPS structure](..\ntifs\ns-ntifs-_token_groups.md) | TOKEN_GROUPS contains information about the group security identifiers (SID) in an access token. |
| [_TOKEN_GROUPS_AND_PRIVILEGES structure](..\ntifs\ns-ntifs-_token_groups_and_privileges.md) | TOKEN_GROUPS_AND_PRIVILEGES contains information about the group security identifiers (SIDs) and privileges in an access token. |
| [_TOKEN_ORIGIN structure](..\ntifs\ns-ntifs-_token_origin.md) | The TOKEN_ORIGIN structure contains information about the origin of the logon session. |
| [_TOKEN_OWNER structure](..\ntifs\ns-ntifs-_token_owner.md) | TOKEN_OWNER contains the default owner security identifier (SID) that will be applied to newly created objects. |
| [_TOKEN_PRIMARY_GROUP structure](..\ntifs\ns-ntifs-_token_primary_group.md) | TOKEN_PRIMARY_GROUP specifies a group security identifier (SID) for an access token. |
| [_TOKEN_PRIVILEGES structure](..\ntifs\ns-ntifs-_token_privileges.md) | TOKEN_PRIVILEGES contains information about a set of privileges for an access token. |
| [_TOKEN_SOURCE structure](..\ntifs\ns-ntifs-_token_source.md) | TOKEN_SOURCE identifies the source of an access token. |
| [_TOKEN_STATISTICS structure](..\ntifs\ns-ntifs-_token_statistics.md) | TOKEN_STATISTICS contains information about an access token. A driver can retrieve this information by calling SeQueryInformationToken or ZwQueryInformationToken. |
| [_TOKEN_USER structure](..\ntifs\ns-ntifs-_token_user.md) | TOKEN_USER identifies the user associated with an access token. |
| [_WIM_PROVIDER_ADD_OVERLAY_INPUT structure](..\ntifs\ns-ntifs-_wim_provider_add_overlay_input.md) | A new Windows Image File (WIM) data source is added to the WIM provider with the WIM_PROVIDER_ADD_OVERLAY_INPUT structure. |
| [_WIM_PROVIDER_EXTERNAL_INFO structure](..\ntifs\ns-ntifs-_wim_provider_external_info.md) | The WIM_PROVIDER_EXTERNAL_INFO structure holds the identifier and status information for the Windows Image File (WIM) external backing provider. |
| [_WIM_PROVIDER_OVERLAY_ENTRY structure](..\ntifs\ns-ntifs-_wim_provider_overlay_entry.md) | Contains the a Windows Image Format (WIM) file configuration information for a data source entry. It is used to identify specific WIM file names and indices that supply data to externally backed files on a volume. |
| [_WIM_PROVIDER_REMOVE_OVERLAY_INPUT structure](..\ntifs\ns-ntifs-_wim_provider_remove_overlay_input.md) | A Windows Image File (WIM) data source to remove from the WIM provider is specified in the WIM_PROVIDER_REMOVE_OVERLAY_INPUT structure. |
| [_WIM_PROVIDER_SUSPEND_OVERLAY_INPUT structure](..\ntifs\ns-ntifs-_wim_provider_suspend_overlay_input.md) | A Windows Image File (WIM) data source to suspend from the WIM provider is specified in the WIM_PROVIDER_SUSPEND_OVERLAY_INPUT structure. |
| [_WIM_PROVIDER_UPDATE_OVERLAY_INPUT structure](..\ntifs\ns-ntifs-_wim_provider_update_overlay_input.md) | A current Windows Image File (WIM) data source is updated with a new WIM file using the FSCTL_UPDATE_OVERLAY control request with a WIM_PROVIDER_UPDATE_OVERLAY_INPUT structure. |
| [_WOF_EXTERNAL_FILE_ID structure](..\ntifs\ns-ntifs-_wof_external_file_id.md) | The WOF_EXTERNAL_FILE_ID structure contains a file ID that is used to open a handle to a mini-filter or driver. |
| [_WOF_EXTERNAL_INFO structure](..\ntifs\ns-ntifs-_wof_external_info.md) | The WOF_EXTERNAL_INFO structure identifies a file backing provider and the overlay service version it supports. |
| [_WOF_VERSION_INFO structure](..\ntifs\ns-ntifs-_wof_version_info.md) | The WOF_VERSION_INFO structure contains the version corresponding to the driver supporting a given provider. |
| [__PUBLIC_OBJECT_TYPE_INFORMATION structure](..\ntifs\ns-ntifs-__public_object_type_information.md) | The PUBLIC_OBJECT_TYPE_INFORMATION structure holds the type name of the object. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [NETWORK_OPEN_INTEGRITY_QUALIFIER enumeration](..\ntifs\ne-ntifs-network_open_integrity_qualifier.md) | The NETWORK_OPEN_INTEGRITY_QUALIFIER enumeration type contains values that identify the kind of integrity restriction to attach to a file. |
| [NETWORK_OPEN_LOCATION_QUALIFIER enumeration](..\ntifs\ne-ntifs-network_open_location_qualifier.md) | The NETWORK_OPEN_LOCATION_QUALIFIER enumeration type contains values that identify the kind of location restriction to attach to a file. |
| [_FLT_FILESYSTEM_TYPE enumeration](..\fltuserstructures\ne-fltuserstructures-_flt_filesystem_type.md) | The FLT_FILESYSTEM_TYPE enumeration identifies the type of file system being used on a volume. |
| [_FSRTL_CHANGE_BACKING_TYPE enumeration](..\ntifs\ne-ntifs-_fsrtl_change_backing_type.md) | The FSRTL_CHANGE_BACKING_TYPE enumeration specifies the type of cache or control area that a file object designates. |
| [_OBJECT_INFORMATION_CLASS enumeration](..\ntifs\ne-ntifs-_object_information_class.md) | The OBJECT_INFORMATION_CLASS enumeration type represents the type of information to supply about an object. |
| [_REFS_SMR_VOLUME_GC_ACTION enumeration](..\ntifs\ne-ntifs-_refs_smr_volume_gc_action.md) | The REFS_SMR_VOLUME_GC_ACTION enum contains the available garbage collection commands for FSCTL_SET_REFS_SMR_VOLUME_GC_PARAMETERS. |
| [_REFS_SMR_VOLUME_GC_METHOD enumeration](..\ntifs\ne-ntifs-_refs_smr_volume_gc_method.md) | The REFS_SMR_VOLUME_GC_METHOD enum specifies the garbage collection method or strategy for FSCTL_SET_REFS_SMR_VOLUME_GC_PARAMETERS. |
| [_REFS_SMR_VOLUME_GC_STATE enumeration](..\ntifs\ne-ntifs-_refs_smr_volume_gc_state.md) | The REFS_SMR_VOLUME_GC_STATE enum specifies the garbage collection's current state. |
| [_SID_NAME_USE enumeration](..\ntifs\ne-ntifs-_sid_name_use.md) | The SID_NAME_USE enumeration type contains values that specify the type of a security identifier (SID). |
| [_TOKEN_INFORMATION_CLASS enumeration](..\ntifs\ne-ntifs-_token_information_class.md) | The TOKEN_INFORMATION_CLASS enumeration type contains values that specify the type of information being assigned to or retrieved from an access token. |
| [_TOKEN_TYPE enumeration](..\ntifs\ne-ntifs-_token_type.md) | The TOKEN_TYPE enumeration type contains values that differentiate between a primary token and an impersonation token. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_REDIR_QUERY_PATH IOCTL](..\ntifs\ni-ntifs-ioctl_redir_query_path.md) | The IOCTL_REDIR_QUERY_PATH control code is sent by the multiple UNC provider (MUP) to network redirectors to determine which provider can handle a specific UNC path in a name-based operation, typically an IRP_MJ_CREATE request. |
| [IOCTL_REDIR_QUERY_PATH_EX IOCTL](..\ntifs\ni-ntifs-ioctl_redir_query_path_ex.md) | The IOCTL_REDIR_QUERY_PATH_EX control code is sent by the multiple UNC provider (MUP) on Windows Vista or later to network redirectors to determine which provider can handle a specific UNC path in a name-based operation, typically an IRP_MJ_CREATE request. |
| [IOCTL_VOLSNAP_FLUSH_AND_HOLD_WRITES IOCTL](..\ntifs\ni-ntifs-ioctl_volsnap_flush_and_hold_writes.md) | The IOCTL_VOLSNAP_FLUSH_AND_HOLD_WRITES control code is sent to force a flush of a file system before a volume shadow copy occurs. |

## Macros

| Title   | Description   |
| ---- |:---- |
| [FltAcquirePushLockExclusive macro](..\fltkernel\nf-fltkernel-fltacquirepushlockexclusive.md) | The FltAcquirePushLockExclusive routine acquires the given push lock for exclusive access by the calling thread. |
| [FltAcquirePushLockShared macro](..\fltkernel\nf-fltkernel-fltacquirepushlockshared.md) | The FltAcquirePushLockShared routine acquires the given push lock for shared access by the calling thread. |
| [FltReleasePushLock macro](..\fltkernel\nf-fltkernel-fltreleasepushlock.md) | The FltReleasePushLock routine releases a specified push lock owned by the current thread. |
| [FsRtlAllocatePoolWithQuotaTag macro](..\ntifs\nf-ntifs-fsrtlallocatepoolwithquotatag.md) | The FsRtlAllocatePoolWithQuotaTag routine allocates pool memory, charging quota against the current process. |
| [FsRtlAllocatePoolWithTag macro](..\ntifs\nf-ntifs-fsrtlallocatepoolwithtag.md) | The FsRtlAllocatePoolWithTag routine allocates pool memory. |
| [FsRtlAreThereCurrentFileLocks macro](..\ntifs\nf-ntifs-fsrtlaretherecurrentfilelocks.md) | The FsRtlAreThereCurrentFileLocks macro checks whether any byte range locks exist for the specified file. |
| [FsRtlCheckOplock macro](..\rxprocs\nf-rxprocs-fsrtlcheckoplock.md) | The FsRtlCheckOplock routine synchronizes the IRP for a file I/O operation with the file's current opportunistic lock (oplock) state. |
| [FsRtlCompleteRequest macro](..\ntifs\nf-ntifs-fsrtlcompleterequest.md) | The FsRtlCompleteRequest macro completes an IRP with the specified status. |
| [FsRtlFastLock macro](..\ntifs\nf-ntifs-fsrtlfastlock.md) | The FsRtlFastLock macro is used by file systems and filter drivers to request a byte-range lock for a file stream. |
| [FsRtlGetPerStreamContextPointer macro](..\ntifs\nf-ntifs-fsrtlgetperstreamcontextpointer.md) | The FsRtlGetPerStreamContextPointer macro returns the file system's stream context for a file stream. |
| [FsRtlInitPerStreamContext macro](..\ntifs\nf-ntifs-fsrtlinitperstreamcontext.md) | The FsRtlInitPerStreamContext macro initializes a filter driver context structure. |
| [FsRtlIsAnsiCharacterLegal macro](..\ntifs\nf-ntifs-fsrtlisansicharacterlegal.md) | The FsRtlIsAnsiCharacterLegal macro determines whether a character is a legal ANSI character. |
| [FsRtlIsAnsiCharacterLegalFat macro](..\ntifs\nf-ntifs-fsrtlisansicharacterlegalfat.md) | The FsRtlIsAnsiCharacterLegalFat macro determines whether an ANSI character is legal for FAT file names. |
| [FsRtlIsAnsiCharacterLegalHpfs macro](..\ntifs\nf-ntifs-fsrtlisansicharacterlegalhpfs.md) | The FsRtlIsAnsiCharacterLegalHpfs macro determines whether an ANSI character is legal for HPFS file names. |
| [FsRtlIsAnsiCharacterLegalNtfs macro](..\ntifs\nf-ntifs-fsrtlisansicharacterlegalntfs.md) | The FsRtlIsAnsiCharacterLegalNtfs macro determines whether an ANSI character is legal for NTFS file names. |
| [FsRtlIsAnsiCharacterLegalNtfsStream macro](..\ntifs\nf-ntifs-fsrtlisansicharacterlegalntfsstream.md) | The FsRtlIsAnsiCharacterLegalNtfsStream macro determines whether an ANSI character is legal for NTFS stream names. |
| [FsRtlIsAnsiCharacterWild macro](..\ntifs\nf-ntifs-fsrtlisansicharacterwild.md) | The FsRtlIsAnsiCharacterWild macro determines whether an ANSI character is a wildcard character. |
| [FsRtlIsLeadDbcsCharacter macro](..\ntifs\nf-ntifs-fsrtlisleaddbcscharacter.md) | The FsRtlIsLeadDbcsCharacter macro determines whether a character is a lead byte (the first byte of a character) in a double-byte character set (DBCS). |
| [FsRtlIsUnicodeCharacterWild macro](..\ntifs\nf-ntifs-fsrtlisunicodecharacterwild.md) | The FsRtlIsUnicodeCharacterWild macro determines whether a Unicode character is a wildcard character. |
| [FsRtlLookupPerStreamContext macro](..\ntifs\nf-ntifs-fsrtllookupperstreamcontext.md) | The FsRtlLookupPerStreamContext macro retrieves a per-stream context structure for a file stream. |
| [FsRtlNotifyFullChangeDirectory macro](..\rxprocs\nf-rxprocs-fsrtlnotifyfullchangedirectory.md) | The FsRtlNotifyFullChangeDirectory routine creates a notify structure for a notification request and adds it to the specified notify list. |
| [FsRtlOplockIsFastIoPossible macro](..\rxprocs\nf-rxprocs-fsrtloplockisfastiopossible.md) | FsRtlOplockIsFastIoPossible checks a file's opportunistic lock (oplock) state to determine whether fast I/O can be performed on the file. |
| [FsRtlSetupAdvancedHeaderEx macro](..\ntifs\nf-ntifs-fsrtlsetupadvancedheaderex.md) | The FsRtlSetupAdvancedHeaderEx macro is used by file systems to initialize an FSRTL_ADVANCED_FCB_HEADER structure for use with both stream and file contexts. |
| [FsRtlSupportsPerFileContexts macro](..\ntifs\nf-ntifs-fsrtlsupportsperfilecontexts.md) | The FsRtlSupportsPerFileContexts macro checks if per file context information is supported by the file system that is associated with a specified FILE_OBJECT. |
| [FsRtlTestAnsiCharacter macro](..\ntifs\nf-ntifs-fsrtltestansicharacter.md) | The FsRtlTestAnsiCharacter macro determines whether an ANSI or double-byte character set (DBCS) character meets the specified criteria. |
| [IoIsFileOpenedExclusively macro](..\ntifs\nf-ntifs-ioisfileopenedexclusively.md) | Reserved for system use. |
| [IoSetTopLevelIrp macro](..\rx\nf-rx-iosettoplevelirp.md) | The IoSetTopLevelIrp routine sets the value of the TopLevelIrp field of the current thread. |
| [IsReparseTagMicrosoft macro](..\ntifs\nf-ntifs-isreparsetagmicrosoft.md) | The IsReparseTagMicrosoft macro determines whether a reparse point tag indicates a Microsoft reparse point. |
| [IsReparseTagNameSurrogate macro](..\ntifs\nf-ntifs-isreparsetagnamesurrogate.md) | The IsReparseTagNameSurrogate macro determines whether a tag's associated reparse point is a surrogate for another named entity, such as a volume mount point. |
| [IsReparseTagValid macro](..\ntifs\nf-ntifs-isreparsetagvalid.md) | Reserved for system use. |
| [RtlFillMemoryUlonglong macro](..\ntifs\nf-ntifs-rtlfillmemoryulonglong.md) | The RtlFillMemoryUlonglong routine fills a given range of memory with one or more repetitions of a given ULONGLONG value. |
| [RtlOemStringToCountedUnicodeSize macro](..\ntifs\nf-ntifs-rtloemstringtocountedunicodesize.md) | The RtlOemStringToCountedUnicodeSize routine determines the size, in bytes, that a given OEM string will be after it is translated into a counted Unicode string. |
| [RtlOemStringToUnicodeSize macro](..\ntifs\nf-ntifs-rtloemstringtounicodesize.md) | The RtlOemStringToUnicodeSize routine determines the size, in bytes, that a given OEM string will be after it is translated into a null-terminated Unicode string. |
| [RtlUnicodeStringToOemSize macro](..\ntifs\nf-ntifs-rtlunicodestringtooemsize.md) | The RtlUnicodeStringToOemSize routine determines the size, in bytes, that a given Unicode string will be after it is translated into an OEM string. |
| [SeDeleteClientSecurity macro](..\ntifs\nf-ntifs-sedeleteclientsecurity.md) | The SeDeleteClientSecurity routine deletes a client security context. |
| [SeLengthSid macro](..\ntifs\nf-ntifs-selengthsid.md) | Obsolete. |
| [SeQuerySubjectContextToken macro](..\ntifs\nf-ntifs-sequerysubjectcontexttoken.md) | The SeQuerySubjectContextToken macro retrieves the access token for a security subject context. |
