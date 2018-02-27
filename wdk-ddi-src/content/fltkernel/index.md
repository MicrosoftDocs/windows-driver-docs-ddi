---
UID: NA:fltkernel
ms.assetid: 4bae9dcd-2c48-3a14-9947-7e0831da3b42
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Fltkernel.h header



This header is used by Installable file system. For more information, see
- [Installable file system](../_ifsk/index.md)

Fltkernel.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [FltAcknowledgeEcp function](nf-fltkernel-fltacknowledgeecp.md) | The FltAcknowledgeEcp routine is used to mark an extra create parameter context structure (ECP) as acknowledged. |
| [FltAddOpenReparseEntry function](nf-fltkernel-fltaddopenreparseentry.md) | This routine adds a caller allocated open reparse structure, OPEN_REPARSE_LIST_ENTRY, into a create operation. |
| [FltAdjustDeviceStackSizeForIoRedirection function](nf-fltkernel-fltadjustdevicestacksizeforioredirection.md) | The FltAdjustDeviceStackSizeForIoRedirection routine increases the size of the source device stack to allow a minifilter to redirect I/O from a specified source instance to a specified target instance when the target stack is deeper than the source stack. |
| [FltAllocateCallbackData function](nf-fltkernel-fltallocatecallbackdata.md) | FltAllocateCallbackData allocates a callback data structure that a minifilter driver can use to initiate an I/O request. |
| [FltAllocateCallbackDataEx function](nf-fltkernel-fltallocatecallbackdataex.md) | The FltAllocateCallbackDataEx routine allocates a callback data structure and can preallocate memory for additional structures that a minifilter driver can use to initiate an I/O request. |
| [FltAllocateContext function](nf-fltkernel-fltallocatecontext.md) | The FltAllocateContext routine allocates a context structure for a specified context type. |
| [FltAllocateDeferredIoWorkItem function](nf-fltkernel-fltallocatedeferredioworkitem.md) | FltAllocateDeferredIoWorkItem allocates a deferred-I/O work item. |
| [FltAllocateExtraCreateParameter function](nf-fltkernel-fltallocateextracreateparameter.md) | The FltAllocateExtraCreateParameter routine allocates paged memory pool for a user-defined extra create parameter (ECP) context structure and generates a pointer to that structure. |
| [FltAllocateExtraCreateParameterFromLookasideList function](nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md) | The FltAllocateExtraCreateParameterFromLookasideList routine allocates memory pool from a given lookaside list for an extra create parameter (ECP) context structure and generates a pointer to that structure. |
| [FltAllocateExtraCreateParameterList function](nf-fltkernel-fltallocateextracreateparameterlist.md) | The FltAllocateExtraCreateParameterList routine allocates paged pool memory for an extra create parameter (ECP) list structure and generates a pointer to that structure. |
| [FltAllocateFileLock function](nf-fltkernel-fltallocatefilelock.md) | The FltAllocateFileLock routine allocates and initializes a new FILE_LOCK structure. |
| [FltAllocateGenericWorkItem function](nf-fltkernel-fltallocategenericworkitem.md) | FltAllocateGenericWorkItem allocates a generic work item. |
| [FltAllocatePoolAlignedWithTag function](nf-fltkernel-fltallocatepoolalignedwithtag.md) | FltAllocatePoolAlignedWithTag allocates a device-aligned buffer for use in a noncached I/O operation. |
| [FltApplyPriorityInfoThread function](nf-fltkernel-fltapplypriorityinfothread.md) | The FltApplyPriorityInfoThread routine is used by a minifilter driver to apply priority information to a thread. |
| [FltAttachVolume function](nf-fltkernel-fltattachvolume.md) | FltAttachVolume creates a new minifilter driver instance and attaches it to the given volume. |
| [FltAttachVolumeAtAltitude function](nf-fltkernel-fltattachvolumeataltitude.md) | FltAttachVolumeAtAltitude is a debugging support routine that attaches a minifilter driver instance to a volume at a specified altitude, overriding any settings in the minifilter driver's INF file. |
| [FltBuildDefaultSecurityDescriptor function](nf-fltkernel-fltbuilddefaultsecuritydescriptor.md) | FltBuildDefaultSecurityDescriptor builds a default security descriptor for use with FltCreateCommunicationPort. |
| [FltCancelFileOpen function](nf-fltkernel-fltcancelfileopen.md) | A minifilter driver can use the FltCancelFileOpen routine to close a newly opened or created file. |
| [FltCancelIo function](nf-fltkernel-fltcancelio.md) | The FltCancelIo routine cancels an I/O operation. |
| [FltCancellableWaitForMultipleObjects function](nf-fltkernel-fltcancellablewaitformultipleobjects.md) | The FltCancellableWaitForMultipleObjects executes a cancelable wait operation (a wait that can be terminated) on one or more dispatcher objects. |
| [FltCancellableWaitForSingleObject function](nf-fltkernel-fltcancellablewaitforsingleobject.md) | The FltCancellableWaitForSingleObject routine executes a cancelable wait operation (a wait that can be terminated) on a dispatcher object. |
| [FltCbdqDisable function](nf-fltkernel-fltcbdqdisable.md) | FltCbdqDisable disables a minifilter driver's callback data queue. |
| [FltCbdqEnable function](nf-fltkernel-fltcbdqenable.md) | FltCbdqEnable enables a callback data queue that was disabled by a previous call to FltCbdqDisable. |
| [FltCbdqInitialize function](nf-fltkernel-fltcbdqinitialize.md) | FltCbdqInitialize initializes a minifilter driver's callback data queue dispatch table. |
| [FltCbdqInsertIo function](nf-fltkernel-fltcbdqinsertio.md) | FltCbdqInsertIo inserts the callback data structure for an I/O operation into a minifilter driver's callback data queue. |
| [FltCbdqRemoveIo function](nf-fltkernel-fltcbdqremoveio.md) | FltCbdqRemoveIo removes a particular item from a minifilter driver's callback data queue. |
| [FltCbdqRemoveNextIo function](nf-fltkernel-fltcbdqremovenextio.md) | FltCbdqRemoveNextIo removes the next matching item in a minifilter driver's callback data queue. |
| [FltCheckAndGrowNameControl function](nf-fltkernel-fltcheckandgrownamecontrol.md) | The FltCheckAndGrowNameControl routine checks whether the buffer in a FLT_NAME_CONTROL structure is large enough to hold the specified number of bytes. If not, FltCheckAndGrowNameControl replaces it with a larger system-allocated buffer. |
| [FltCheckLockForReadAccess function](nf-fltkernel-fltchecklockforreadaccess.md) | The FltCheckLockForReadAccess routine determines whether the caller has read access to a locked byte range of a file. |
| [FltCheckLockForWriteAccess function](nf-fltkernel-fltchecklockforwriteaccess.md) | The FltCheckLockForWriteAccess routine determines whether the caller has write access to a locked byte range of a file. |
| [FltCheckOplock function](nf-fltkernel-fltcheckoplock.md) | A minifilter driver calls FltCheckOplock to synchronize the callback data structure for an IRP-based file I/O operation with the file's current opportunistic lock (oplock) state. |
| [FltCheckOplockEx function](nf-fltkernel-fltcheckoplockex.md) | A minifilter driver calls the FltCheckOplockEx routine to synchronize the callback data structure for an IRP-based file I/O operation that has the current opportunistic lock (oplock) state of the file. |
| [FltClearCallbackDataDirty function](nf-fltkernel-fltclearcallbackdatadirty.md) | The FltClearCallbackDataDirty routine clears the callback dirty flag in a callback data structure. |
| [FltClearCancelCompletion function](nf-fltkernel-fltclearcancelcompletion.md) | FltClearCancelCompletion clears a cancel routine that was specified for an I/O operation. |
| [FltClose function](nf-fltkernel-fltclose.md) | FltClose closes a file handle that was opened by FltCreateFile or FltCreateFileEx. |
| [FltCloseClientPort function](nf-fltkernel-fltcloseclientport.md) | FltCloseClientPort closes a communication client port. |
| [FltCloseCommunicationPort function](nf-fltkernel-fltclosecommunicationport.md) | FltCloseCommunicationPort closes a minifilter driver's communication server port. |
| [FltCloseSectionForDataScan function](nf-fltkernel-fltclosesectionfordatascan.md) | The FltCloseSectionForDataScan routine closes a section object associated with a file stream. |
| [FltCommitComplete function](nf-fltkernel-fltcommitcomplete.md) | The FltCommitComplete routine acknowledges a TRANSACTION_NOTIFY_COMMIT notification. |
| [FltCommitFinalizeComplete function](nf-fltkernel-fltcommitfinalizecomplete.md) | The FltCommitFinalizeComplete routine acknowledges a TRANSACTION_NOTIFY_COMMIT_FINALIZE notification. |
| [FltCompareInstanceAltitudes function](nf-fltkernel-fltcompareinstancealtitudes.md) | FltCompareInstanceAltitudes compares the altitudes of two minifilter driver instances. |
| [FltCompletePendedPostOperation function](nf-fltkernel-fltcompletependedpostoperation.md) | FltCompletePendedPostOperation resumes completion processing for an I/O operation that was pended in a minifilter driver's postoperation callback routine. |
| [FltCompletePendedPreOperation function](nf-fltkernel-fltcompletependedpreoperation.md) | FltCompletePendedPreOperation resumes processing for an I/O operation that was pended in a minifilter driver's preoperation callback (PFLT_PRE_OPERATION_CALLBACK) routine. |
| [FltCopyOpenReparseList function](nf-fltkernel-fltcopyopenreparselist.md) | This routine copies any open reparse information from a previous create into a new ECP list that can be used to issue a second create. |
| [FltCreateCommunicationPort function](nf-fltkernel-fltcreatecommunicationport.md) | FltCreateCommunicationPort creates a communication server port on which a minifilter driver can receive connection requests from user-mode applications. |
| [FltCreateFile function](nf-fltkernel-fltcreatefile.md) | Minifilter drivers call FltCreateFile to create a new file or open an existing file. |
| [FltCreateFileEx function](nf-fltkernel-fltcreatefileex.md) | Minifilter drivers call FltCreateFileEx to create a new file or open an existing file. |
| [FltCreateFileEx2 function](nf-fltkernel-fltcreatefileex2.md) | Minifilter drivers call FltCreateFileEx2 to create a new file or open an existing file. This routine also includes an optional create context parameter. |
| [FltCreateMailslotFile function](nf-fltkernel-fltcreatemailslotfile.md) | Minifilter drivers call FltCreateMailslotFile to create a new pipe or open an existing mailslot. |
| [FltCreateNamedPipeFile function](nf-fltkernel-fltcreatenamedpipefile.md) | Minifilter drivers call FltCreateNamedPipeFile to create a new pipe or open an existing pipe. |
| [FltCreateSectionForDataScan function](nf-fltkernel-fltcreatesectionfordatascan.md) | The FltCreateSectionForDataScan routine creates a section object for a file. The filter manager can optionally synchronize I/O with the section created. |
| [FltCreateSystemVolumeInformationFolder function](nf-fltkernel-fltcreatesystemvolumeinformationfolder.md) | FltCreateSystemVolumeInformationFolder verifies the existence of the &#0034;System Volume Information&#0034; folder on a file system volume. If the folder is not present, then the folder is created. |
| [FltCurrentBatchOplock function](nf-fltkernel-fltcurrentbatchoplock.md) | A minifilter driver calls FltCurrentBatchOplock to determine whether there are any batch or filter opportunistic locks (oplocks) on a file. |
| [FltCurrentOplock function](nf-fltkernel-fltcurrentoplock.md) | A minifilter driver calls the FltCurrentOplock routine to determine whether there are any opportunistic locks (oplocks) on a file. |
| [FltCurrentOplockH function](nf-fltkernel-fltcurrentoplockh.md) | A minifilter driver calls the FltCurrentOplockH routine to determine whether there are any CACHE_HANDLE_LEVEL opportunistic locks (oplocks) on a file. |
| [FltDecodeParameters function](nf-fltkernel-fltdecodeparameters.md) | FltDecodeParameters returns pointers to the memory descriptor list (MDL) address, buffer pointer, buffer length, and desired access parameters for an I/O operation. |
| [FltDeleteContext function](nf-fltkernel-fltdeletecontext.md) | FltDeleteContext marks a specified context for deletion. |
| [FltDeleteExtraCreateParameterLookasideList function](nf-fltkernel-fltdeleteextracreateparameterlookasidelist.md) | The FltDeleteExtraCreateParameterLookasideList routine frees an extra create parameter (ECP) lookaside list. |
| [FltDeleteFileContext function](nf-fltkernel-fltdeletefilecontext.md) | The FltDeleteFileContext routine retrieves and deletes a file context that a given minifilter driver has set for a given file. |
| [FltDeleteInstanceContext function](nf-fltkernel-fltdeleteinstancecontext.md) | FltDeleteInstanceContext removes a context from a given instance and marks the context for deletion. |
| [FltDeletePushLock function](nf-fltkernel-fltdeletepushlock.md) | The FltDeletePushLock routine deletes a given push lock. |
| [FltDeleteStreamContext function](nf-fltkernel-fltdeletestreamcontext.md) | FltDeleteStreamContext removes a context that a given minifilter driver instance has set for a given stream and marks the context for deletion. |
| [FltDeleteStreamHandleContext function](nf-fltkernel-fltdeletestreamhandlecontext.md) | FltDeleteStreamHandleContext removes a context that a given minifilter driver instance has set for a given stream handle and marks the context for deletion. |
| [FltDeleteTransactionContext function](nf-fltkernel-fltdeletetransactioncontext.md) | The FltDeleteTransactionContext routine removes a context from a given transaction and marks the context for deletion. |
| [FltDeleteVolumeContext function](nf-fltkernel-fltdeletevolumecontext.md) | FltDeleteVolumeContext removes a context that a given minifilter driver has set for a given volume and marks the context for deletion. |
| [FltDetachVolume function](nf-fltkernel-fltdetachvolume.md) | FltDetachVolume detaches a minifilter driver instance from a volume. |
| [FltDeviceIoControlFile function](nf-fltkernel-fltdeviceiocontrolfile.md) | FltDeviceIoControlFile sends a control code directly to a specified device driver, causing the corresponding driver to perform the specified action. |
| [FltDoCompletionProcessingWhenSafe function](nf-fltkernel-fltdocompletionprocessingwhensafe.md) | If it is safe to do so, the FltDoCompletionProcessingWhenSafe function executes a minifilter driver postoperation callback routine. |
| [FltEnlistInTransaction function](nf-fltkernel-fltenlistintransaction.md) | The FltEnlistInTransaction routine enlists a minifilter driver in a given transaction. |
| [FltEnumerateFilterInformation function](nf-fltkernel-fltenumeratefilterinformation.md) | The FltEnumerateFilterInformation routine provides information about all the registered filter drivers (including minifilter and legacy filter drivers) in the system. |
| [FltEnumerateFilters function](nf-fltkernel-fltenumeratefilters.md) | The FltEnumerateFilters routine enumerates all registered minifilter drivers in the system. |
| [FltEnumerateInstanceInformationByDeviceObject function](nf-fltkernel-fltenumerateinstanceinformationbydeviceobject.md) | The FltEnumerateInstanceInformationByDeviceObject routine provides information about minifilter driver instances and legacy filter drivers that are attached to the volume related to a specified device object. |
| [FltEnumerateInstanceInformationByFilter function](nf-fltkernel-fltenumerateinstanceinformationbyfilter.md) | The FltEnumerateInstanceInformationByFilter routine provides information about instances of a given minifilter driver. |
| [FltEnumerateInstanceInformationByVolume function](nf-fltkernel-fltenumerateinstanceinformationbyvolume.md) | The FltEnumerateInstanceInformationByVolume routine provides information about minifilter driver instances and legacy filter drivers (Windows Vista only) that are attached to a given volume. |
| [FltEnumerateInstanceInformationByVolumeName function](nf-fltkernel-fltenumerateinstanceinformationbyvolumename.md) | The FltEnumerateInstanceInformationByVolumeName routine provides information about minifilter driver instances and legacy filter drivers that are attached to the volume with the specified name. |
| [FltEnumerateInstances function](nf-fltkernel-fltenumerateinstances.md) | The FltEnumerateInstances routine enumerates minifilter driver instances for a given minifilter driver or volume. |
| [FltEnumerateVolumeInformation function](nf-fltkernel-fltenumeratevolumeinformation.md) | The FltEnumerateVolumeInformation routine provides information about volumes that are known to the filter manager. |
| [FltEnumerateVolumes function](nf-fltkernel-fltenumeratevolumes.md) | The FltEnumerateVolumes routine enumerates all volumes in the system. |
| [FltFastIoMdlRead function](nf-fltkernel-fltfastiomdlread.md) | The FltFastIoMdlRead routine returns a memory descriptor list (MDL) that points directly to the specified byte range in the file cache. |
| [FltFastIoMdlReadComplete function](nf-fltkernel-fltfastiomdlreadcomplete.md) | The FltFastIoMdlReadComplete routine completes the read operation that the FltFastIoMdlRead routine initiated. |
| [FltFastIoMdlWriteComplete function](nf-fltkernel-fltfastiomdlwritecomplete.md) | The FltFastIoMdlWriteComplete routine frees the resources that FltFastIoPrepareMdlWrite allocated. |
| [FltFastIoPrepareMdlWrite function](nf-fltkernel-fltfastiopreparemdlwrite.md) | The FltFastIoPrepareMdlWrite routine returns a linked list of memory descriptor lists (MDLs) that point to the specified range of cached file data to write data directly to the cache. |
| [FltFindExtraCreateParameter function](nf-fltkernel-fltfindextracreateparameter.md) | The FltFindExtraCreateParameter routine searches a given ECP list for an ECP context structure of a given type and returns a pointer to this structure if it is found. |
| [FltFlushBuffers function](nf-fltkernel-fltflushbuffers.md) | The FltFlushBuffers routine is used by the minifilter driver to send a flush request for a given file to the file system. |
| [FltFreeCallbackData function](nf-fltkernel-fltfreecallbackdata.md) | The FltFreeCallbackData routine frees a callback data structure allocated by the FltAllocateCallbackData routine. |
| [FltFreeDeferredIoWorkItem function](nf-fltkernel-fltfreedeferredioworkitem.md) | The FltFreeDeferredIoWorkItem routine frees a work item allocated by the FltAllocateDeferredIoWorkItem routine. |
| [FltFreeExtraCreateParameter function](nf-fltkernel-fltfreeextracreateparameter.md) | The FltFreeExtraCreateParameter routine frees the memory for an ECP context structure. |
| [FltFreeExtraCreateParameterList function](nf-fltkernel-fltfreeextracreateparameterlist.md) | The FltFreeExtraCreateParameterList routine frees an extra create parameter (ECP) list structure. |
| [FltFreeFileLock function](nf-fltkernel-fltfreefilelock.md) | The FltFreeFileLock routine uninitializes and frees an initialized FILE_LOCK structure. |
| [FltFreeGenericWorkItem function](nf-fltkernel-fltfreegenericworkitem.md) | The FltFreeGenericWorkItem routine frees a work item allocated by the FltAllocateGenericWorkItem routine. |
| [FltFreeOpenReparseList function](nf-fltkernel-fltfreeopenreparselist.md) | This routine deallocates any information copied into a create operation by a previous call to FltCopyOpenReparseList. |
| [FltFreePoolAlignedWithTag function](nf-fltkernel-fltfreepoolalignedwithtag.md) | The FltFreePoolAlignedWithTag routine frees a cache-aligned buffer that was allocated by a previous call to FltAllocatePoolAlignedWithTag. |
| [FltFreeSecurityDescriptor function](nf-fltkernel-fltfreesecuritydescriptor.md) | FltFreeSecurityDescriptor frees a security descriptor allocated by the FltBuildDefaultSecurityDescriptor routine. |
| [FltFsControlFile function](nf-fltkernel-fltfscontrolfile.md) | The FltFsControlFile routine sends a control code directly to a specified file system or file system filter driver, causing the corresponding driver to perform the specified action. |
| [FltGetActivityIdCallbackData function](nf-fltkernel-fltgetactivityidcallbackdata.md) | The FltGetActivityIdCallbackData routine retrieves the current activity ID associated with a request in a minifilter's callback data. |
| [FltGetBottomInstance function](nf-fltkernel-fltgetbottominstance.md) | FltGetBottomInstance returns an opaque instance pointer for the minifilter driver instance, if there is one, that is attached at the bottom of the instance stack for a given volume. |
| [FltGetContexts function](nf-fltkernel-fltgetcontexts.md) | The FltGetContexts routine retrieves a minifilter driver's contexts for the objects related to the current operation. |
| [FltGetContextsEx function](nf-fltkernel-fltgetcontextsex.md) | The FltGetContextsEx routine retrieves a minifilter driver's contexts for the objects related to the current operation. |
| [FltGetDestinationFileNameInformation function](nf-fltkernel-fltgetdestinationfilenameinformation.md) | The FltGetDestinationFileNameInformation routine constructs a full destination path name for a file or directory that is being renamed or for which an NTFS hard link is being created. |
| [FltGetDeviceObject function](nf-fltkernel-fltgetdeviceobject.md) | The FltGetDeviceObject routine returns a pointer to the Filter Manager's volume device object (VDO) for a given volume. |
| [FltGetDiskDeviceObject function](nf-fltkernel-fltgetdiskdeviceobject.md) | The FltGetDiskDeviceObject routine returns a pointer to the disk device object associated with a given volume. |
| [FltGetEcpListFromCallbackData function](nf-fltkernel-fltgetecplistfromcallbackdata.md) | The FltGetEcpListFromCallbackData routine returns a pointer to an extra create parameter context structure (ECP) list that is associated with a given create operation callback-data object. |
| [FltGetFileContext function](nf-fltkernel-fltgetfilecontext.md) | The FltGetFileContext routine retrieves a context that was set for a file by a given minifilter driver instance. |
| [FltGetFileNameInformation function](nf-fltkernel-fltgetfilenameinformation.md) | The FltGetFileNameInformation routine returns name information for a file or directory. |
| [FltGetFileNameInformationUnsafe function](nf-fltkernel-fltgetfilenameinformationunsafe.md) | The FltGetFileNameInformationUnsafe routine returns name information for an open file or directory. |
| [FltGetFileSystemType function](nf-fltkernel-fltgetfilesystemtype.md) | The FltGetFileSystemType function takes a volume or instance object and provides the file system type of the volume. |
| [FltGetFilterFromInstance function](nf-fltkernel-fltgetfilterfrominstance.md) | The FltGetFilterFromInstance routine returns an opaque filter pointer for the minifilter driver that created the given instance. |
| [FltGetFilterFromName function](nf-fltkernel-fltgetfilterfromname.md) | The FltGetFilterFromName routine returns an opaque filter pointer for a registered minifilter driver whose name matches the value in the FilterName parameter. |
| [FltGetFilterInformation function](nf-fltkernel-fltgetfilterinformation.md) | The FltGetFilterInformation routine provides information about a minifilter driver. |
| [FltGetInstanceContext function](nf-fltkernel-fltgetinstancecontext.md) | The FltGetInstanceContext routine retrieves a context that was set for an instance by a given minifilter driver. |
| [FltGetInstanceInformation function](nf-fltkernel-fltgetinstanceinformation.md) | The FltGetInstanceInformation routine returns information about a minifilter driver instance. |
| [FltGetIoPriorityHint function](nf-fltkernel-fltgetiopriorityhint.md) | The FltGetIoPriorityHint routine is used by a minifilter driver to get IO priority information from Callback Data. |
| [FltGetIoPriorityHintFromCallbackData function](nf-fltkernel-fltgetiopriorityhintfromcallbackdata.md) | The FltGetIoPriorityHintFromCallbackData routine is used by a minifilter driver to get IO priority information from callback data. |
| [FltGetIoPriorityHintFromFileObject function](nf-fltkernel-fltgetiopriorityhintfromfileobject.md) | The FltGetIoPriorityHintFromFileObject routine is used by a minifilter driver to get IO priority information from a file object. |
| [FltGetIoPriorityHintFromThread function](nf-fltkernel-fltgetiopriorityhintfromthread.md) | The FltGetIoPriorityHintFromThread routine is used by a minifilter driver to get IO priority information from a thread. |
| [FltGetIrpName function](nf-fltkernel-fltgetirpname.md) | The FltGetIrpName routine returns the name for a major function code as a printable string. |
| [FltGetLowerInstance function](nf-fltkernel-fltgetlowerinstance.md) | The FltGetLowerInstance routine returns an opaque instance pointer for the next lower minifilter driver instance, if there is one, that is attached below a given minifilter driver instance on the same volume. |
| [FltGetNewSystemBufferAddress function](nf-fltkernel-fltgetnewsystembufferaddress.md) | The FltGetNewSystemBufferAddress function retrieves the AssociatedIrp.SystemBuffer buffer, which the file system has allocated. A minifilter driver's post-callback routine calls this function. |
| [FltGetNextExtraCreateParameter function](nf-fltkernel-fltgetnextextracreateparameter.md) | The FltGetNextExtraCreateParameter routine returns a pointer to the next (or first) extra create parameter context structure (ECP) in a given ECP list. |
| [FltGetRequestorProcess function](nf-fltkernel-fltgetrequestorprocess.md) | The FltGetRequestorProcess routine returns a process pointer for the thread that requested a given I/O operation. |
| [FltGetRequestorProcessId function](nf-fltkernel-fltgetrequestorprocessid.md) | The FltGetRequestorProcessId routine returns the unique 32-bit process ID for the process associated with the thread that requested a given I/O operation. |
| [FltGetRequestorProcessIdEx function](nf-fltkernel-fltgetrequestorprocessidex.md) | The FltGetRequestorProcessIdEx routine returns the kernel-mode handle for the process that is associated with the thread that requested a given I/O operation. |
| [FltGetRequestorSessionId function](nf-fltkernel-fltgetrequestorsessionid.md) | The FltGetRequestorSessionId routine returns the session ID of the process that originally requested the specified I/O operation. |
| [FltGetRoutineAddress function](nf-fltkernel-fltgetroutineaddress.md) | The FltGetRoutineAddress routine returns a pointer to a routine specified by the FltMgrRoutineName parameter. |
| [FltGetSectionContext function](nf-fltkernel-fltgetsectioncontext.md) | The FltGetSectionContext routine retrieves a section context that was created for a file stream by a specified minifilter driver instance. |
| [FltGetStreamContext function](nf-fltkernel-fltgetstreamcontext.md) | The FltGetStreamContext routine retrieves a context that was set for a file stream by a given minifilter driver instance. |
| [FltGetStreamHandleContext function](nf-fltkernel-fltgetstreamhandlecontext.md) | The FltGetStreamHandleContext routine retrieves a context that was set for a stream handle by a given minifilter driver instance. |
| [FltGetSwappedBufferMdlAddress function](nf-fltkernel-fltgetswappedbuffermdladdress.md) | The FltGetSwappedBufferMdlAddress routine returns the memory descriptor list (MDL) address for a buffer that was swapped in by a minifilter driver. |
| [FltGetTopInstance function](nf-fltkernel-fltgettopinstance.md) | The FltGetTopInstance routine returns an opaque instance pointer for the minifilter driver instance that is attached at the top of the instance stack for a given volume. |
| [FltGetTransactionContext function](nf-fltkernel-fltgettransactioncontext.md) | The FltGetTransactionContext routine retrieves a context that was set for a transaction by a given minifilter driver. |
| [FltGetTunneledName function](nf-fltkernel-fltgettunneledname.md) | The FltGetTunneledName routine retrieves the tunneled name for a file, given the normalized name returned for the file by a previous call to FltGetFileNameInformation, FltGetFileNameInformationUnsafe, or FltGetDestinationFileNameInformation. |
| [FltGetUpperInstance function](nf-fltkernel-fltgetupperinstance.md) | The FltGetUpperInstance routine returns an opaque instance pointer for the next higher minifilter driver instance, if there is one, that is attached above a given minifilter driver instance on the same volume. |
| [FltGetVolumeContext function](nf-fltkernel-fltgetvolumecontext.md) | The FltGetVolumeContext routine retrieves a context that was set for a volume by a given minifilter driver. |
| [FltGetVolumeFromDeviceObject function](nf-fltkernel-fltgetvolumefromdeviceobject.md) | The FltGetVolumeFromDeviceObject routine returns an opaque pointer for the volume represented by a volume device object (VDO). |
| [FltGetVolumeFromFileObject function](nf-fltkernel-fltgetvolumefromfileobject.md) | The FltGetVolumeFromFileObject routine returns an opaque pointer for the volume that a given file stream resides on. |
| [FltGetVolumeFromInstance function](nf-fltkernel-fltgetvolumefrominstance.md) | The FltGetVolumeFromInstance routine returns an opaque pointer for the volume that a given minifilter driver instance is attached to. |
| [FltGetVolumeFromName function](nf-fltkernel-fltgetvolumefromname.md) | The FltGetVolumeFromName routine returns an opaque pointer for the volume whose name matches the value of the VolumeName parameter. |
| [FltGetVolumeGuidName function](nf-fltkernel-fltgetvolumeguidname.md) | The FltGetVolumeGuidName routine returns the volume name for a given volume, in volume globally unique identifier (GUID) format. |
| [FltGetVolumeInformation function](nf-fltkernel-fltgetvolumeinformation.md) | The FltGetVolumeInformation routine provides information about a given volume. |
| [FltGetVolumeInstanceFromName function](nf-fltkernel-fltgetvolumeinstancefromname.md) | The FltGetVolumeInstanceFromName routine returns an opaque instance pointer for the given minifilter driver instance on the given volume. |
| [FltGetVolumeName function](nf-fltkernel-fltgetvolumename.md) | The FltGetVolumeName routine gets the volume name for a given volume. |
| [FltGetVolumeProperties function](nf-fltkernel-fltgetvolumeproperties.md) | The FltGetVolumeProperties routine returns volume property information for the given volume. |
| [FltInitExtraCreateParameterLookasideList function](nf-fltkernel-fltinitextracreateparameterlookasidelist.md) | The FltInitExtraCreateParameterLookasideList routine initializes a paged or non-paged pool lookaside list used for the allocation of one or more extra create parameter context structures (ECPs) of fixed size. |
| [FltInitializeFileLock function](nf-fltkernel-fltinitializefilelock.md) | The FltInitializeFileLock routine initializes an opaque FILE_LOCK structure that the caller has allocated from paged pool. |
| [FltInitializeOplock function](nf-fltkernel-fltinitializeoplock.md) | The FltInitializeOplock routine initializes an opportunistic lock (oplock) pointer. |
| [FltInitializePushLock function](nf-fltkernel-fltinitializepushlock.md) | The FltInitializePushLock routine initializes a push lock variable. |
| [FltInsertExtraCreateParameter function](nf-fltkernel-fltinsertextracreateparameter.md) | The FltInsertExtraCreateParameter routine inserts an extra create parameter (ECP) context structure into an ECP list. |
| [FltIs32bitProcess function](nf-fltkernel-fltis32bitprocess.md) | The FltIs32bitProcess routine checks whether the originator of the current I/O operation is a 32-bit user-mode application. |
| [FltIsCallbackDataDirty function](nf-fltkernel-fltiscallbackdatadirty.md) | The FltIsCallbackDataDirty routine tests the FLTFL_CALLBACK_DATA_DIRTY flag in a callback data structure. |
| [FltIsDirectory function](nf-fltkernel-fltisdirectory.md) | A minifilter driver calls the FltIsDirectory routine to determine whether a given file object represents a directory. |
| [FltIsEcpAcknowledged function](nf-fltkernel-fltisecpacknowledged.md) | The FltIsEcpAcknowledged routine is used to determine if a given extra create parameter context structure (ECP) has been marked as acknowledged. |
| [FltIsEcpFromUserMode function](nf-fltkernel-fltisecpfromusermode.md) | The FltIsEcpFromUserMode routine is used to determine if an extra create parameter context structure (ECP) originated from user mode. |
| [FltIsFltMgrVolumeDeviceObject function](nf-fltkernel-fltisfltmgrvolumedeviceobject.md) | The FltIsFltMgrVolumeDeviceObject routine determines whether the given device object belongs to filter manager and if the device object is a volume device object. |
| [FltIsIoCanceled function](nf-fltkernel-fltisiocanceled.md) | The FltIsIoCanceled routine checks if an IRP-based operation has been canceled. |
| [FltIsIoRedirectionAllowed function](nf-fltkernel-fltisioredirectionallowed.md) | The FltIsIoRedirectionAllowed routine determines whether I/O can be redirected from the specified source filter instance to another specified filter instance. |
| [FltIsIoRedirectionAllowedForOperation function](nf-fltkernel-fltisioredirectionallowedforoperation.md) | The FltIsIoRedirectionAllowedForOperation routine determines whether I/O can be redirected from the filter instance associated with the specified FLT_CALLBACK_DATA structure to the specified filter instance. |
| [FltIsOperationSynchronous function](nf-fltkernel-fltisoperationsynchronous.md) | The FltIsOperationSynchronous routine determines whether a given callback data structure (FLT_CALLBACK_DATA) represents a synchronous or asynchronous I/O operation. |
| [FltIsVolumeSnapshot function](nf-fltkernel-fltisvolumesnapshot.md) | The FltIsVolumeSnapshot routine determines whether a volume or minifilter driver instance is attached to a snapshot volume. |
| [FltIsVolumeWritable function](nf-fltkernel-fltisvolumewritable.md) | The FltIsVolumeWritable routine determines whether the disk device that corresponds to a volume or minifilter driver instance is writable. |
| [FltLoadFilter function](nf-fltkernel-fltloadfilter.md) | The FltLoadFilter routine dynamically loads a minifilter driver into the currently running system. |
| [FltLockUserBuffer function](nf-fltkernel-fltlockuserbuffer.md) | The FltLockUserBuffer routine locks the user buffer for a given I/O operation. |
| [FltNotifyFilterChangeDirectory function](nf-fltkernel-fltnotifyfilterchangedirectory.md) | The FltNotifyFilterChangeDirectory routine creates a notify structure for an IRP_MN_NOTIFY_CHANGE_DIRECTORY operation and adds it to the specified notify list. |
| [FltObjectDereference function](nf-fltkernel-fltobjectdereference.md) | The FltObjectDereference routine removes a rundown reference from an opaque filter, instance, or volume pointer. |
| [FltObjectReference function](nf-fltkernel-fltobjectreference.md) | The FltObjectReference routine adds a rundown reference to an opaque filter, instance, or volume pointer. |
| [FltOpenVolume function](nf-fltkernel-fltopenvolume.md) | The FltOpenVolume routine returns a handle and a file object pointer for the file system volume that a given minifilter driver instance is attached to. |
| [FltOplockBreakH function](nf-fltkernel-fltoplockbreakh.md) | The FltOplockBreakH routine breaks CACHE_HANDLE_LEVEL opportunistic locks (oplocks). |
| [FltOplockBreakToNone function](nf-fltkernel-fltoplockbreaktonone.md) | The FltOplockBreakToNone routine breaks all opportunistic locks (oplocks) immediately without regard for any oplock key. |
| [FltOplockBreakToNoneEx function](nf-fltkernel-fltoplockbreaktononeex.md) | The FltOplockBreakToNoneEx routine breaks all opportunistic locks (oplocks) immediately without regard for any oplock key. |
| [FltOplockFsctrl function](nf-fltkernel-fltoplockfsctrl.md) | The FltOplockFsctrl routine performs various opportunistic lock (oplock) operations on behalf of a minifilter driver. |
| [FltOplockFsctrlEx function](nf-fltkernel-fltoplockfsctrlex.md) | The FltOplockFsctrlEx routine performs various opportunistic lock (oplock) operations on behalf of a minifilter driver. |
| [FltOplockIsFastIoPossible function](nf-fltkernel-fltoplockisfastiopossible.md) | The FltOplockIsFastIoPossible routine checks a file's opportunistic lock (oplock) state to determine whether fast I/O can be performed on the file. |
| [FltOplockIsSharedRequest function](nf-fltkernel-fltoplockissharedrequest.md) | The FltOplockIsSharedRequest routine determines if a request for an opportunistic lock (oplock) wants a shared oplock. |
| [FltOplockKeysEqual function](nf-fltkernel-fltoplockkeysequal.md) | The FltOplockKeysEqual routine compares the opportunistic lock (oplock) keys that are stored in the file object extensions of two file objects. |
| [FltParseFileName function](nf-fltkernel-fltparsefilename.md) | FltParseFileName parses the extension, stream, and final component from a file name string. |
| [FltParseFileNameInformation function](nf-fltkernel-fltparsefilenameinformation.md) | FltParseFileNameInformation parses the contents of a FLT_FILE_NAME_INFORMATION structure. |
| [FltPerformAsynchronousIo function](nf-fltkernel-fltperformasynchronousio.md) | A minifilter driver calls FltPerformAsynchronousIo to initiate an asynchronous I/O operation. |
| [FltPerformSynchronousIo function](nf-fltkernel-fltperformsynchronousio.md) | A minifilter driver calls FltPerformSynchronousIo to initiate a synchronous I/O operation after calling FltAllocateCallbackData to allocate a callback data structure for the operation. |
| [FltPrePrepareComplete function](nf-fltkernel-fltprepreparecomplete.md) | The FltPrePrepareComplete routine acknowledges a TRANSACTION_NOTIFY_PREPREPARE notification. |
| [FltPrepareComplete function](nf-fltkernel-fltpreparecomplete.md) | The FltPrepareComplete routine acknowledges a TRANSACTION_NOTIFY_PREPARE notification. |
| [FltPrepareToReuseEcp function](nf-fltkernel-fltpreparetoreuseecp.md) | The FltPrepareToReuseEcp routine resets an extra create parameter (ECP) context structure, which prepares it for reuse. |
| [FltProcessFileLock function](nf-fltkernel-fltprocessfilelock.md) | The FltProcessFileLock routine processes and completes a file lock operation. |
| [FltPropagateActivityIdToThread function](nf-fltkernel-fltpropagateactivityidtothread.md) | The FltPropagateActivityIdToThread routine associates the activity ID from the IRP in the minifilter's callback data with the current thread. |
| [FltPurgeFileNameInformationCache function](nf-fltkernel-fltpurgefilenameinformationcache.md) | FltPurgeFileNameInformationCache purges from the Filter Manager's name cache all file name information structures that were generated from names provided by the given minifilter driver instance. |
| [FltQueryDirectoryFile function](nf-fltkernel-fltquerydirectoryfile.md) | The FltQueryDirectoryFile routine returns various kinds of information about files in the directory specified by a given file object. |
| [FltQueryEaFile function](nf-fltkernel-fltqueryeafile.md) | FltQueryEaFile returns information about extended-attribute (EA) values for a file. |
| [FltQueryInformationFile function](nf-fltkernel-fltqueryinformationfile.md) | FltQueryInformationFile retrieves information for a given file. |
| [FltQueryQuotaInformationFile function](nf-fltkernel-fltqueryquotainformationfile.md) | The FltQueryQuotaInformationFile routine retrieves quota entries associated with a file object. |
| [FltQuerySecurityObject function](nf-fltkernel-fltquerysecurityobject.md) | FltQuerySecurityObject retrieves a copy of an object's security descriptor. |
| [FltQueryVolumeInformation function](nf-fltkernel-fltqueryvolumeinformation.md) | The FltQueryVolumeInformation routine retrieves information about the volume that the given instance is attached to. |
| [FltQueryVolumeInformationFile function](nf-fltkernel-fltqueryvolumeinformationfile.md) | FltQueryVolumeInformationFile retrieves volume information for a given file, directory, storage device, or volume. |
| [FltQueueDeferredIoWorkItem function](nf-fltkernel-fltqueuedeferredioworkitem.md) | The FltQueueDeferredIoWorkItem routine posts an IRP-based I/O operation to a work queue. |
| [FltQueueGenericWorkItem function](nf-fltkernel-fltqueuegenericworkitem.md) | FltQueueGenericWorkItem posts a work item that is not associated with a specific I/O operation to a work queue. |
| [FltReadFile function](nf-fltkernel-fltreadfile.md) | FltReadFile reads data from an open file, stream, or device. |
| [FltReadFileEx function](nf-fltkernel-fltreadfileex.md) | FltReadFileEx reads data from an open file, stream, or device. This function extends FltReadFile to allow the optional use of an MDL for read data instead of a mapped buffer address. |
| [FltReferenceContext function](nf-fltkernel-fltreferencecontext.md) | FltReferenceContext increments the reference count on a context structure. |
| [FltReferenceFileNameInformation function](nf-fltkernel-fltreferencefilenameinformation.md) | FltReferenceFileNameInformation increments the reference count on a file name information structure. |
| [FltRegisterFilter function](nf-fltkernel-fltregisterfilter.md) | FltRegisterFilter registers a minifilter driver. |
| [FltRegisterForDataScan function](nf-fltkernel-fltregisterfordatascan.md) | The FltRegisterForDataScan routine enables data scanning for the volume attached to the minifilter instance. |
| [FltReissueSynchronousIo function](nf-fltkernel-fltreissuesynchronousio.md) | FltReissueSynchronousIo initiates a new synchronous I/O operation that uses the parameters from a previously synchronized I/O operation. |
| [FltReleaseContext function](nf-fltkernel-fltreleasecontext.md) | FltReleaseContext decrements the reference count on a context. |
| [FltReleaseContexts function](nf-fltkernel-fltreleasecontexts.md) | FltReleaseContexts releases each context in a given FLT_RELATED_CONTEXTS structure. |
| [FltReleaseContextsEx function](nf-fltkernel-fltreleasecontextsex.md) | FltReleaseContextsEx releases each context in a given FLT_RELATED_CONTEXTS_EX structure. |
| [FltReleaseFileNameInformation function](nf-fltkernel-fltreleasefilenameinformation.md) | FltReleaseFileNameInformation releases a file name information structure. |
| [FltRemoveExtraCreateParameter function](nf-fltkernel-fltremoveextracreateparameter.md) | The FltRemoveExtraCreateParameter routine searches an ECP list for an ECP context structure and, if found, detaches it from the ECP list. |
| [FltRemoveOpenReparseEntry function](nf-fltkernel-fltremoveopenreparseentry.md) | This routine removes an OPEN_REPARSE_LIST_ENTRY structure (added by FltAddOpenReparseEntry) from a create operation. |
| [FltRequestOperationStatusCallback function](nf-fltkernel-fltrequestoperationstatuscallback.md) | FltRequestOperationStatusCallback returns status information for the given I/O operation. |
| [FltRetainSwappedBufferMdlAddress function](nf-fltkernel-fltretainswappedbuffermdladdress.md) | FltRetainSwappedBufferMdlAddress prevents the Filter Manager from freeing the memory descriptor list (MDL) for a buffer that was swapped in by a minifilter driver. |
| [FltRetrieveIoPriorityInfo function](nf-fltkernel-fltretrieveiopriorityinfo.md) | The FltRetrieveIoPriorityInfo routine is used by a minifilter driver to retrieve priority information from a thread. |
| [FltReuseCallbackData function](nf-fltkernel-fltreusecallbackdata.md) | The FltReuseCallbackData routine reinitializes a callback data structure so that it can be reused. |
| [FltRollbackComplete function](nf-fltkernel-fltrollbackcomplete.md) | The FltRollbackComplete routine acknowledges a TRANSACTION_NOTIFY_ROLLBACK notification. |
| [FltRollbackEnlistment function](nf-fltkernel-fltrollbackenlistment.md) | The FltRollbackEnlistment routine rolls back or aborts a transaction on behalf of a minifilter driver. |
| [FltSendMessage function](nf-fltkernel-fltsendmessage.md) | FltSendMessage sends a message to a waiting user-mode application on behalf of a minifilter driver or a minifilter driver instance. |
| [FltSetActivityIdCallbackData function](nf-fltkernel-fltsetactivityidcallbackdata.md) | The FltSetActivityIdCallbackData routine sets the a activity ID for an IRP in a minifilter's callback data. |
| [FltSetCallbackDataDirty function](nf-fltkernel-fltsetcallbackdatadirty.md) | A minifilter driver's preoperation or postoperation callback routine calls FltSetCallbackDataDirty to indicate that it has modified the contents of the callback data structure. |
| [FltSetCancelCompletion function](nf-fltkernel-fltsetcancelcompletion.md) | A minifilter driver calls FltSetCancelCompletion to specify a cancel routine to be called if a given I/O operation is canceled. |
| [FltSetEaFile function](nf-fltkernel-fltseteafile.md) | FltSetEaFile sets extended-attribute (EA) values for a file. |
| [FltSetEcpListIntoCallbackData function](nf-fltkernel-fltsetecplistintocallbackdata.md) | The FltSetEcpListIntoCallbackData routine attaches an extra create parameter context structure (ECP) list to a create operation callback-data object. |
| [FltSetFileContext function](nf-fltkernel-fltsetfilecontext.md) | The FltSetFileContext routine sets a context for a file. |
| [FltSetInformationFile function](nf-fltkernel-fltsetinformationfile.md) | FltSetInformationFile sets information for a given file. |
| [FltSetInstanceContext function](nf-fltkernel-fltsetinstancecontext.md) | FltSetInstanceContext sets a context for a minifilter driver instance. |
| [FltSetIoPriorityHintIntoCallbackData function](nf-fltkernel-fltsetiopriorityhintintocallbackdata.md) | The FltSetIoPriorityHintIntoCallbackData routine is used by a minifilter driver to set the I/O priority information in callback data. |
| [FltSetIoPriorityHintIntoFileObject function](nf-fltkernel-fltsetiopriorityhintintofileobject.md) | The FltSetIoPriorityHintIntoFileObject routine is used by a minifilter driver to set the I/O priority information in a file object. |
| [FltSetIoPriorityHintIntoThread function](nf-fltkernel-fltsetiopriorityhintintothread.md) | The FltSetIoPriorityHintIntoThread routine is used by a minifilter driver to set the IO priority information in a thread. |
| [FltSetQuotaInformationFile function](nf-fltkernel-fltsetquotainformationfile.md) | The FltSetQuotaInformationFile routine modifies quota entries for a file object. |
| [FltSetSecurityObject function](nf-fltkernel-fltsetsecurityobject.md) | FltSetSecurityObject sets an object's security state. |
| [FltSetStreamContext function](nf-fltkernel-fltsetstreamcontext.md) | The FltSetStreamContext routine sets a context for a file stream. |
| [FltSetStreamHandleContext function](nf-fltkernel-fltsetstreamhandlecontext.md) | The FltSetStreamHandleContext routine sets a context for a stream handle. |
| [FltSetTransactionContext function](nf-fltkernel-fltsettransactioncontext.md) | The FltSetTransactionContext routine sets a context on a transaction. |
| [FltSetVolumeContext function](nf-fltkernel-fltsetvolumecontext.md) | FltSetVolumeContext sets a context for a volume. |
| [FltSetVolumeInformation function](nf-fltkernel-fltsetvolumeinformation.md) | FltSetVolumeInformation changes various kinds of information about the volume that the given instance is attached to. |
| [FltStartFiltering function](nf-fltkernel-fltstartfiltering.md) | FltStartFiltering starts filtering for a registered minifilter driver. |
| [FltSupportsFileContexts function](nf-fltkernel-fltsupportsfilecontexts.md) | The FltSupportsFileContexts routine determines whether the file system supports file contexts for a given file. |
| [FltSupportsFileContextsEx function](nf-fltkernel-fltsupportsfilecontextsex.md) | The FltSupportsFileContextsEx routine determines whether the file system or the filter manager support file contexts for a given file. |
| [FltSupportsStreamContexts function](nf-fltkernel-fltsupportsstreamcontexts.md) | FltSupportsStreamContexts determines whether stream contexts are supported on a given file object. |
| [FltSupportsStreamHandleContexts function](nf-fltkernel-fltsupportsstreamhandlecontexts.md) | FltSupportsStreamHandleContexts determines whether stream handle contexts are supported on a given file object. |
| [FltTagFile function](nf-fltkernel-flttagfile.md) | FltTagFile sets a reparse tag on a file or directory. |
| [FltUninitializeFileLock function](nf-fltkernel-fltuninitializefilelock.md) | The FltUninitializeFileLock routine uninitializes a FILE_LOCK structure. |
| [FltUninitializeOplock function](nf-fltkernel-fltuninitializeoplock.md) | FltUninitializeOplock uninitializes an opportunistic lock (oplock) pointer. |
| [FltUnloadFilter function](nf-fltkernel-fltunloadfilter.md) | A minifilter driver that has loaded a supporting minifilter driver by calling FltLoadFilter can unload the minifilter driver by calling FltUnloadFilter. |
| [FltUnregisterFilter function](nf-fltkernel-fltunregisterfilter.md) | A registered minifilter driver calls FltUnregisterFilter to unregister itself so that the Filter Manager no longer calls it to process I/O operations. |
| [FltUntagFile function](nf-fltkernel-fltuntagfile.md) | FltUntagFile removes a reparse point from a file or directory. |
| [FltWriteFile function](nf-fltkernel-fltwritefile.md) | FltWriteFile is used to write data to an open file, stream, or device. |
| [FltWriteFileEx function](nf-fltkernel-fltwritefileex.md) | FltWriteFileEx is used to write data to an open file, stream, or device. This function extends FltWriteFile to allow the optional use of an MDL for write data instead of a mapped buffer address. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PFLT_COMPLETED_ASYNC_IO_CALLBACK callback](nc-fltkernel-pflt_completed_async_io_callback.md) | A minifilter driver that initiates an asynchronous I/O operation can specify a routine of type PFLT_COMPLETED_ASYNC_IO_CALLBACK routine to be called when the operation is completed. |
| [PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE callback](nc-fltkernel-pflt_complete_lock_callback_data_routine.md) | A minifilter driver can register a routine of type PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE as the minifilter driver's CompleteLockCallbackDataRoutine callback routine for a FILE_LOCK structure. |
| [PFLT_CONTEXT_ALLOCATE_CALLBACK callback](nc-fltkernel-pflt_context_allocate_callback.md) | A minifilter driver can register a routine of type PFLT_CONTEXT_ALLOCATE_CALLBACK as the minifilter driver's ContextAllocateCallback routine. |
| [PFLT_CONTEXT_CLEANUP_CALLBACK callback](nc-fltkernel-pflt_context_cleanup_callback.md) | A minifilter driver can register a routine of type PFLT_CONTEXT_CLEANUP_CALLBACK as the minifilter driver's ContextCleanupCallback routine. |
| [PFLT_CONTEXT_FREE_CALLBACK callback](nc-fltkernel-pflt_context_free_callback.md) | A minifilter can register a routine of type PFLT_CONTEXT_FREE_CALLBACK as the minifilter driver's ContextFreeCallback routine. |
| [PFLT_FILTER_UNLOAD_CALLBACK callback](nc-fltkernel-pflt_filter_unload_callback.md) | A minifilter driver can register a routine of type PFLT_FILTER_UNLOAD_CALLBACK as the minifilter driver's FilterUnloadCallback routine. |
| [PFLT_GENERATE_FILE_NAME callback](nc-fltkernel-pflt_generate_file_name.md) | A minifilter driver that provides file names for the filter manager's name cache can register a routine of type PFLT_GENERATE_FILE_NAME as the minifilter driver's GenerateFileNameCallback routine. |
| [PFLT_GET_OPERATION_STATUS_CALLBACK callback](nc-fltkernel-pflt_get_operation_status_callback.md) | A minifilter driver can register a routine of type PFLT_GET_OPERATION_STATUS_CALLBACK as the minifilter driver's OperationStatusCallback routine. |
| [PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK callback](nc-fltkernel-pflt_instance_query_teardown_callback.md) | A minifilter driver can register a routine of type PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK as the minifilter driver's InstanceQueryTeardownCallback routine. |
| [PFLT_INSTANCE_SETUP_CALLBACK callback](nc-fltkernel-pflt_instance_setup_callback.md) | A minifilter driver can register a routine of type PFLT_INSTANCE_SETUP_CALLBACK as the minifilter driver's InstanceSetupCallback routine. |
| [PFLT_INSTANCE_TEARDOWN_CALLBACK callback](nc-fltkernel-pflt_instance_teardown_callback.md) | A minifilter driver can register two routines of type PFLT_INSTANCE_TEARDOWN_CALLBACK as the minifilter driver's InstanceTeardownStartCallback and InstanceTeardownCompleteCallback routines. |
| [PFLT_NORMALIZE_CONTEXT_CLEANUP callback](nc-fltkernel-pflt_normalize_context_cleanup.md) | A minifilter driver that provides file names for the filter manager's name cache can register a routine of type PFLT_NORMALIZE_CONTEXT_CLEANUP as the minifilter driver's NormalizeContextCleanupCallback routine. |
| [PFLT_NORMALIZE_NAME_COMPONENT callback](nc-fltkernel-pflt_normalize_name_component.md) | A minifilter driver that provides file names for the filter manager's name cache can register a routine of type PFLT_NORMALIZE_NAME_COMPONENT as the minifilter driver's NormalizeNameComponentCallback routine. |
| [PFLT_NORMALIZE_NAME_COMPONENT_EX callback](nc-fltkernel-pflt_normalize_name_component_ex.md) | A minifilter driver that provides file names for the filter manager's name cache can register a routine of type PFLT_NORMALIZE_NAME_COMPONENT_EX as the minifilter driver's NormalizeNameComponentExCallback callback routine. |
| [PFLT_POST_OPERATION_CALLBACK callback](nc-fltkernel-pflt_post_operation_callback.md) | A minifilter driver can register one or more routines of type PFLT_POST_OPERATION_CALLBACK to perform completion processing for I/O operations. |
| [PFLT_PRE_OPERATION_CALLBACK callback](nc-fltkernel-pflt_pre_operation_callback.md) | A minifilter driver's PFLT_PRE_OPERATION_CALLBACK routine performs pre-operation processing for I/O operations. |
| [PFLT_SECTION_CONFLICT_NOTIFICATION_CALLBACK callback](nc-fltkernel-pflt_section_conflict_notification_callback.md) | A minifilter driver can optionally register a routine of type PFLT_CONTEXT_ALLOCATE_CALLBACK as the minifilter driver's SectionNotificationCallback routine. |
| [PFLT_TRANSACTION_NOTIFICATION_CALLBACK callback](nc-fltkernel-pflt_transaction_notification_callback.md) | A minifilter driver can register a routine of type PFLT_TRANSACTION_NOTIFICATION_CALLBACK as its TransactionNotificationCallback routine. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_FLT_CALLBACK_DATA structure](ns-fltkernel-_flt_callback_data.md) | The FLT_CALLBACK_DATA structure represents an I/O operation. The Filter Manager and minifilters use this structure to initiate and process I/O operations. |
| [_FLT_CALLBACK_DATA_QUEUE structure](ns-fltkernel-_flt_callback_data_queue.md) | FLT_CALLBACK_DATA_QUEUE is an opaque structure that is used to specify the callback routines for a minifilter's callback data queue. Do not set the members of this structure directly. Use FltCbdqInitialize to initialize this structure. |
| [_FLT_CONTEXT_REGISTRATION structure](ns-fltkernel-_flt_context_registration.md) | The FLT_CONTEXT_REGISTRATION structure is used to register context types. |
| [_FLT_CREATEFILE_TARGET_ECP_CONTEXT structure](ns-fltkernel-_flt_createfile_target_ecp_context.md) | The FLT_CREATEFILE_TARGET_ECP_CONTEXT structure is an extra create parameter (ECP) used to return reparse target information back to the caller of FltCreateFileEx2. |
| [_FLT_FILE_NAME_INFORMATION structure](ns-fltkernel-_flt_file_name_information.md) | The FLT_FILE_NAME_INFORMATION structure contains file name information. |
| [_FLT_IO_PARAMETER_BLOCK structure](ns-fltkernel-_flt_io_parameter_block.md) | The FLT_IO_PARAMETER_BLOCK structure contains the parameters for the I/O operation that is represented by a callback data (FLT_CALLBACK_DATA) structure. |
| [_FLT_NAME_CONTROL structure](ns-fltkernel-_flt_name_control.md) | A minifilter that provides file names for the Filter Manager's name cache can use the FLT_NAME_CONTROL structure to manage its name buffers. |
| [_FLT_OPERATION_REGISTRATION structure](ns-fltkernel-_flt_operation_registration.md) | The FLT_OPERATION_REGISTRATION structure is used to register operation callback routines. |
| [_FLT_PARAMETERS structure](ns-fltkernel-_flt_parameters.md) | The FLT_PARAMETERS union defines the request-type-specific parameters associated with an I/O operation. |
| [_FLT_REGISTRATION structure](ns-fltkernel-_flt_registration.md) | The FLT_REGISTRATION structure is passed as a parameter to FltRegisterFilter. |
| [_FLT_RELATED_CONTEXTS structure](ns-fltkernel-_flt_related_contexts.md) | The FLT_RELATED_CONTEXTS structure contains a minifilter driver's contexts for the objects associated with an I/O operation. |
| [_FLT_RELATED_CONTEXTS_EX structure](ns-fltkernel-_flt_related_contexts_ex.md) | The FLT_RELATED_CONTEXTS_EX structure contains a minifilter driver's contexts for the objects associated with an I/O operation. |
| [_FLT_RELATED_OBJECTS structure](ns-fltkernel-_flt_related_objects.md) | The FLT_RELATED_OBJECTS structure contains opaque pointers for the objects associated with an operation. |
| [_FLT_TAG_DATA_BUFFER structure](ns-fltkernel-_flt_tag_data_buffer.md) | The FLT_TAG_DATA_BUFFER structure contains information about a reparse point tag. |
| [_FLT_VOLUME_PROPERTIES structure](ns-fltkernel-_flt_volume_properties.md) | The FLT_VOLUME_PROPERTIES structure is passed as a parameter to FltGetVolumeProperties. |

## Macros

| Title   | Description   |
| ---- |:---- |
| [FltAcquirePushLockExclusive macro](nf-fltkernel-fltacquirepushlockexclusive.md) | The FltAcquirePushLockExclusive routine acquires the given push lock for exclusive access by the calling thread. |
| [FltAcquirePushLockShared macro](nf-fltkernel-fltacquirepushlockshared.md) | The FltAcquirePushLockShared routine acquires the given push lock for shared access by the calling thread. |
| [FltReleasePushLock macro](nf-fltkernel-fltreleasepushlock.md) | The FltReleasePushLock routine releases a specified push lock owned by the current thread. |
