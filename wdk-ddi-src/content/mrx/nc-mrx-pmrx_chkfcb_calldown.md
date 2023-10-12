---
UID: NC:mrx.PMRX_CHKFCB_CALLDOWN
title: PMRX_CHKFCB_CALLDOWN (mrx.h)
description: Learn more about the PMRX_CHKFCB_CALLDOWN callback function.
tech.root: ifsk
ms.date: 10/11/2023
keywords: ["PMRX_CHKFCB_CALLDOWN callback function"]
ms.keywords: MRxAreFilesAliased, MRxAreFilesAliased routine [Installable File System Drivers], PMRX_CHKFCB_CALLDOWN, ifsk.mrxarefilesaliased, mrx/MRxAreFilesAliased, mrxref_5d6e6988-84d7-43ac-860e-4f184686a9e6.xml
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
 - PMRX_CHKFCB_CALLDOWN
 - mrx/PMRX_CHKFCB_CALLDOWN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - mrx.h
api_name:
 - PMRX_CHKFCB_CALLDOWN
---

# PMRX_CHKFCB_CALLDOWN callback function

## -description

The **MRxAreFilesAliased** routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request the network mini-redirector to determine if two FCB structures represent the same file.

## -parameters

### -param Fcb1 [in]

A pointer to the first FCB structure.

### -param Fcb2 [in]

A pointer to the second FCB structure.

## -returns

**MRxAreFilesAliased** returns STATUS_SUCCESS indicating that the files are not aliased, or an appropriate NTSTATUS value, such as the following:

| Return code | Description |
| ------------- | ------------- |
| STATUS_MORE_PROCESSING_REQUIRED | The **IndexNumber.QuadPart** members of the two FCB structures are identical. This value indicates that the two files that are being compared are aliases. |

## -remarks

RDBSS calls this routine when processing two files that appear to be the same but have different names (for example, an MS-DOS short name and a long name).

**MRxAreFilesAliased** is called by the [**RxPurgeRelatedFobxs**](../scavengr/nf-scavengr-rxpurgerelatedfobxs.md) routine when purging all the structures of an FOBX structure associated with a NET_ROOT structure. As part of this process, an attempt is made to purge all the FOBX structures that had a close pending before the purge request was received. RDBSS needs to scavenge any temporary FOBX structures in the following cases:

* The **PurgingFcb** parameter that is passed to the [**RxPurgeRelatedFobxs**](../scavengr/nf-scavengr-rxpurgerelatedfobxs.md) routine is the FCB structure for which the scavenging should occur. When this parameter is a directory, RDBSS needs to ensure that files that can potentially be in that directory are closed.

* The FCB structure that is associated with the FOBX structure on the **FobxsToBeFinalized** member of the RDBSS_SCAVENGER structure doesn't point to the same FCB structure as the **PurgingFCB** parameter passed to [**RxPurgeRelatedFobxs**](../scavengr/nf-scavengr-rxpurgerelatedfobxs.md). This is complicated by the fact that they might not be the same FCB structures, but are actually the same file because of aliasing. In this case, the **MRxAreFilesAliased** routine is called to determine if the FCB structure is aliased.

**MRxAreFilesAliased** is also called by the [**RxScavengeFobxsForNetRoot**](../scavengr/nf-scavengr-rxscavengefobxsfornetroot.md) routine when purging all the file objects associated with a NET_ROOT structure. This is complicated by the fact that the **PurgingFCB** parameter passed to **RxScavengeFobxsForNetRoot** and the FCB structure that is associated with the NET_ROOT structure might actually be the same file because of aliasing. In this case, the **MRxAreFilesAliased** routine is called to determine if the FCB structure is aliased.

## -see-also

[**MRxCleanupFobx**](/previous-versions/windows/hardware/drivers/ff549841(v=vs.85))

[**MRxCloseSrvOpen**](nc-mrx-pmrx_calldown.md)

[**MRxCollapseOpen**](/windows-hardware/drivers/ifs/mrxcollapseopen)

[**MRxCreate**](/windows-hardware/drivers/ifs/mrxcreate)

[**MRxDeallocateForFbc**](nc-mrx-pmrx_deallocate_for_fbcb.md)

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

[**RxPurgeRelatedFobxs**](../scavengr/nf-scavengr-rxpurgerelatedfobxs.md)

[**RxScavengeFobxsForNetRoot**](../scavengr/nf-scavengr-rxscavengefobxsfornetroot.md)
