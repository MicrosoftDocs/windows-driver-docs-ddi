---
UID: NF:dbgeng.IDebugDataSpaces3.ReadDebuggerData
title: IDebugDataSpaces3::ReadDebuggerData
author: windows-driver-content
description: The ReadDebuggerData method returns information about the target that the debugger engine has queried or determined during the current session.
old-location: debugger\readdebuggerdata.htm
tech.root: debugger
ms.assetid: 54e4d3b9-db9d-4844-938f-c8ca8819d182
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: IDebugDataSpaces interface [Windows Debugging],ReadDebuggerData method, IDebugDataSpaces2 interface [Windows Debugging],ReadDebuggerData method, IDebugDataSpaces2::ReadDebuggerData, IDebugDataSpaces3 interface [Windows Debugging],ReadDebuggerData method, IDebugDataSpaces3.ReadDebuggerData, IDebugDataSpaces3::ReadDebuggerData, IDebugDataSpaces4 interface [Windows Debugging],ReadDebuggerData method, IDebugDataSpaces4::ReadDebuggerData, IDebugDataSpaces::ReadDebuggerData, IDebugDataSpaces_618b8518-3e32-4518-8e4b-38f66484d554.xml, ReadDebuggerData, ReadDebuggerData method [Windows Debugging], ReadDebuggerData method [Windows Debugging],IDebugDataSpaces interface, ReadDebuggerData method [Windows Debugging],IDebugDataSpaces2 interface, ReadDebuggerData method [Windows Debugging],IDebugDataSpaces3 interface, ReadDebuggerData method [Windows Debugging],IDebugDataSpaces4 interface, dbgeng/IDebugDataSpaces2::ReadDebuggerData, dbgeng/IDebugDataSpaces3::ReadDebuggerData, dbgeng/IDebugDataSpaces4::ReadDebuggerData, dbgeng/IDebugDataSpaces::ReadDebuggerData, debugger.readdebuggerdata
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugDataSpaces.ReadDebuggerData
-	IDebugDataSpaces2.ReadDebuggerData
-	IDebugDataSpaces3.ReadDebuggerData
-	IDebugDataSpaces4.ReadDebuggerData
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugDataSpaces3::ReadDebuggerData


## -description


The <b>ReadDebuggerData</b> method returns information about the target that the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> has queried or determined during the current session.  The available information includes the locations of certain key target kernel locations, specific status values, and a number of other things.


## -parameters




### -param Index [in]

Specifies the index of the data to retrieve.  The following values are valid:

<table>
<tr>
<th>Value</th>
<th>Return Type</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_DATA_KernBase

</td>
<td>
ULONG64

</td>
<td>
Returns the base address of the kernel image.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_BreakpointWithStatusAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel function <b>BreakpointWithStatusInstruction</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_SavedContextAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of saved context record during a bugcheck.  It is only valid after a bugcheck.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_KiCallUserModeAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel function <b>KiCallUserMode</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_KeUserCallbackDispatcherAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the kernel variable <b>KeUserCallbackDispatcher</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_PsLoadedModuleListAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>PsLoadedModuleList</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_PsActiveProcessHeadAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>PsActiveProcessHead</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_PspCidTableAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>PspCidTable</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_ExpSystemResourcesListAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>ExpSystemResourcesList</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_ExpPagedPoolDescriptorAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>ExpPagedPoolDescriptor</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_ExpNumberOfPagedPoolsAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>ExpNumberOfPagedPools</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_KeTimeIncrementAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>KeTimeIncrement</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_KeBugCheckCallbackListHeadAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>KeBugCheckCallbackListHead</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_KiBugcheckDataAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the kernel variable <b>KiBugCheckData</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_IopErrorLogListHeadAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>IopErrorLogListHead</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_ObpRootDirectoryObjectAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>ObpRootDirectoryObject</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_ObpTypeObjectTypeAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>ObpTypeObjectType</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmSystemCacheStartAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmSystemCacheStart</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmSystemCacheEndAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmSystemCacheEnd</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmSystemCacheWsAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmSystemCacheWs</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmPfnDatabaseAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmPfnDatabase</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmSystemPtesStartAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the kernel variable <b>MmSystemPtesStart</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmSystemPtesEndAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the kernel variable <b>MmSystemPtesEnd</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmSubsectionBaseAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmSubsectionBase</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmNumberOfPagingFilesAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmNumberOfPagingFiles</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmLowestPhysicalPageAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmLowestPhysicalPage</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmHighestPhysicalPageAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmHighestPhysicalPage</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmNumberOfPhysicalPagesAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmNumberOfPhysicalPages</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmMaximumNonPagedPoolInBytesAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmMaximumNonPagedPoolInBytes</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmNonPagedSystemStartAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmNonPagedSystemStart</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmNonPagedPoolStartAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmNonPagedPoolStart</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmNonPagedPoolEndAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmNonPagedPoolEnd</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmPagedPoolStartAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmPagedPoolStart</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmPagedPoolEndAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmPagedPoolEnd</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmPagedPoolInformationAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmPagedPoolInfo</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmPageSize

</td>
<td>
ULONG64

</td>
<td>
Returns the page size.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmSizeOfPagedPoolInBytesAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmSizeOfPagedPoolInBytes</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmTotalCommitLimitAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmTotalCommitLimit</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmTotalCommittedPagesAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmTotalCommittedPages</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmSharedCommitAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmSharedCommit</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmDriverCommitAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmDriverCommit</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmProcessCommitAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmProcessCommit</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmPagedPoolCommitAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmPagedPoolCommit</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmExtendedCommitAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmExtendedCommit</b>..

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmZeroedPageListHeadAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmZeroedPageListHead</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmFreePageListHeadAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmFreePageListHead</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmStandbyPageListHeadAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmStandbyPageListHead</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmModifiedPageListHeadAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmModifiedPageListHead</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmModifiedNoWritePageListHeadAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmModifiedNoWritePageListHead</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmAvailablePagesAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmAvailablePages</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmResidentAvailablePagesAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmResidentAvailablePages</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_PoolTrackTableAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>PoolTrackTable</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_NonPagedPoolDescriptorAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>NonPagedPoolDescriptor</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmHighestUserAddressAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmHighestUserAddress</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmSystemRangeStartAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmSystemRangeStart</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmUserProbeAddressAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmUserProbeAddress</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_KdPrintCircularBufferAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the kernel variable <b>KdPrintDefaultCircularBuffer</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_KdPrintCircularBufferEndAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the end of the array KdPrintDefaultCircularBuffer

</td>
</tr>
<tr>
<td>
DEBUG_DATA_KdPrintWritePointerAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>KdPrintWritePointer</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_KdPrintRolloverCountAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable 
<b>KdPrintRolloverCount</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmLoadedUserImageListAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmLoadedUserImageList</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_PaeEnabled

</td>
<td>
BOOLEAN

</td>
<td>
Returns <b>TRUE</b> when the target system has PAE enabled.

Returns <b>FALSE</b> otherwise.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_SharedUserData

</td>
<td>
ULONG64

</td>
<td>
Returns the address in the target of the shared user-mode structure, KUSER_SHARED_DATA.  The KUSER_SHARED_DATA structure is defined in ntddk.h (in the Windows Driver Kit) and ntexapi.h (in the Windows SDK).

Some of the information contained in this structure is displayed by the debugger extension <b>!kuser</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_ProductType

</td>
<td>
ULONG

</td>
<td>
Returns the value of the <b>NtProductType</b> field in the shared user-mode page.

This value should be interpreted the same way as the <b>wProductType</b> field of the structure OSVERSIONINFOEX, which is documented in the Windows SDK.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_SuiteMask

</td>
<td>
ULONG

</td>
<td>
Returns the value of the <b>SuiteMask</b> field in the shared user-mode page.

This value should be interpreted the same way as the <b>wSuiteMask</b> field of the structure OSVERSIONINFOEX, which is documented in the Windows SDK.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_DumpWriterStatus

</td>
<td>
ULONG

</td>
<td>
Returns the status of the writer of the dump file.  This value is operating system and dump file type specific.

</td>
</tr>
</table>
 

The following values are valid for Windows XP and later versions of Windows:

<table>
<tr>
<th>Value</th>
<th>Return Type</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_DATA_NtBuildLabAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>NtBuildLab</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_KiNormalSystemCall

</td>
<td>
ULONG64

</td>
<td>
(Itanium only) Returns the address of the kernel function <b>KiNormalSystemCall</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_KiProcessorBlockAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the kernel variable <b>KiProcessorBlock</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmUnloadedDriversAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmUnloadedDrivers</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmLastUnloadedDriverAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmLastUnloadedDriver</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmTriageActionTakenAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>VerifierTriageActionTaken</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmSpecialPoolTagAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmSpecialPoolTag</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_KernelVerifierAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>KernelVerifier</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmVerifierDataAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmVerifierData</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmAllocatedNonPagedPoolAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmAllocatedNonPagedPool</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmPeakCommitmentAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmPeakCommitment</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmTotalCommitLimitMaximumAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmTotalCommitLimitMaximum</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_CmNtCSDVersionAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>CmNtCSDVersion</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmPhysicalMemoryBlockAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmPhysicalMemoryBlock</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmSessionBase

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmSessionBase</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmSessionSize

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmSessionSize</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_MmSystemParentTablePage

</td>
<td>
ULONG64

</td>
<td>
(Itanium only) Returns the address of the kernel variable <b>MmSystemParentTablePage</b>.

</td>
</tr>
</table>
 

The following values are valid for Windows Server 2003 and later versions of Windows:

<table>
<tr>
<th>Value</th>
<th>Return Type</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_DATA_MmVirtualTranslationBase

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>MmVirtualTranslationBase</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_OffsetKThreadNextProcessor

</td>
<td>
USHORT

</td>
<td>
Returns the offset of the <b>NextProcessor</b> field in the KTHREAD structure.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_OffsetKThreadTeb

</td>
<td>
USHORT

</td>
<td>
Returns the offset of the <b>Teb</b> field in the KTHREAD structure.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_OffsetKThreadKernelStack

</td>
<td>
USHORT

</td>
<td>
Returns the offset of the <b>KernelStack</b> field in the KTHREAD structure.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_OffsetKThreadInitialStack

</td>
<td>
USHORT

</td>
<td>
Returns the offset of the <b>InitialStack</b> field in the KTHREAD structure.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_OffsetKThreadApcProcess

</td>
<td>
USHORT

</td>
<td>
Returns the offset of the ApcState.Process field in the KTHREAD structure.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_OffsetKThreadState

</td>
<td>
USHORT

</td>
<td>
Returns the offset of the <b>State</b> field in the KTHREAD structure.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_OffsetKThreadBStore

</td>
<td>
USHORT

</td>
<td>
(Itanium only) Returns the offset of the <b>InitialBStore</b> field in the KTHREAD structure.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_OffsetKThreadBStoreLimit

</td>
<td>
USHORT

</td>
<td>
(Itanium only) Returns the offset of the <b>BStoreLimit</b> field in the KTHREAD structure.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_SizeEProcess

</td>
<td>
USHORT

</td>
<td>
Returns the size of the EPROCESS structure.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_OffsetEprocessPeb

</td>
<td>
USHORT

</td>
<td>
Returns the offset of the <b>Peb</b> field in the EPROCESS structure.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_OffsetEprocessParentCID

</td>
<td>
USHORT

</td>
<td>
Returns the offset of the <b>InheritedFromUniqueProcessId</b> field in the EPROCESS structure.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_OffsetEprocessDirectoryTableBase

</td>
<td>
USHORT

</td>
<td>
Returns the offset of the <b>DirectoryTableBase</b> field in the EPROCESS structure.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_SizePrcb

</td>
<td>
USHORT

</td>
<td>
Returns the size of the KPRCB structure.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_OffsetPrcbDpcRoutine

</td>
<td>
USHORT

</td>
<td>
Returns the offset of the <b>DpcRoutineActive</b> field in the KPRCB structure.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_OffsetPrcbCurrentThread

</td>
<td>
USHORT

</td>
<td>
Returns the offset of the <b>CurrentThread</b> field in the KPRCB structure.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_OffsetPrcbMhz

</td>
<td>
USHORT

</td>
<td>
Returns the offset of the <b>MHz</b> field in the KPRCB structure.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_OffsetPrcbCpuType

</td>
<td>
USHORT

</td>
<td>
<b>For Itanium processors:</b>  Returns the offset of the <b>ProcessorModel</b> field in the KPRCB structure.

<b>For all other processors:</b>  Returns the offset of the <b>CpuType</b> field in the KPRCB structure.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_OffsetPrcbVendorString

</td>
<td>
USHORT

</td>
<td>
<b>For Itanium processors:</b>  Returns the offset of the <b>ProcessorVendorString</b> field in the KPRCB structure.

<b>For all other processors:</b>  Returns the offset of the <b>VendorString</b> field in the KPRCB structure.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_OffsetPrcbProcessorState

</td>
<td>
USHORT

</td>
<td>
Returns the offset of the ProcessorState.ContextFrame field in the KPRCB structure.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_OffsetPrcbNumber

</td>
<td>
USHORT

</td>
<td>
Returns the offset of the <b>Number</b> field in the KPRCB structure.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_SizeEThread

</td>
<td>
USHORT

</td>
<td>
Returns the size of the ETHREAD structure.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_KdPrintCircularBufferPtrAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>KdPrintCircularBuffer</b>.

</td>
</tr>
<tr>
<td>
DEBUG_DATA_KdPrintBufferSizeAddr

</td>
<td>
ULONG64

</td>
<td>
Returns the address of the kernel variable <b>KdPrintBufferSize</b>.

</td>
</tr>
</table>
 


### -param Buffer [out]

Receives the value of the specified debugger data.  The "Return Type" column in the above table specifies the data type that is returned.  The data can be accessed by casting <i>Buffer</i> to a pointer to that type.


### -param BufferSize [in]

Specifies the size in bytes of the buffer <i>Buffer</i>.


### -param DataSize [out, optional]

Receives the number of bytes used in the buffer <i>Buffer</i>.  If <i>DataSize</i> is <b>NULL</b>, this information is not returned.


## -returns



<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>
 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



Some or all of the values may be unavailable in certain debugging sessions.  For example, some of the values are only available for particular versions of the operating system.

For details on the different values returned by <b>ReadDebuggerData</b>, see <i>Microsoft Windows Internals</i> by David Solomon and Mark Russinovich, the Microsoft Windows SDK, and the Windows Driver Kit (WDK).



