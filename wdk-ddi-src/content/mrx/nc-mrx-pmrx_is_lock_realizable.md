---
UID: NC:mrx.PMRX_IS_LOCK_REALIZABLE
title: PMRX_IS_LOCK_REALIZABLE (mrx.h)
description: Learn more about the PMRX_IS_LOCK_REALIZABLE callback function.
tech.root: ifsk
ms.date: 10/11/2023
keywords: ["PMRX_IS_LOCK_REALIZABLE callback function"]
ms.keywords: MRxIsLockRealizable, MRxIsLockRealizable routine [Installable File System Drivers], PMRX_IS_LOCK_REALIZABLE, ifsk.mrxislockrealizable, mrx/MRxIsLockRealizable, mrxref_52518201-df6f-40ab-803d-14d8fc0993f6.xml
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
 - PMRX_IS_LOCK_REALIZABLE
 - mrx/PMRX_IS_LOCK_REALIZABLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - mrx.h
api_name:
 - PMRX_IS_LOCK_REALIZABLE
---

# PMRX_IS_LOCK_REALIZABLE callback function

## -description

The **MRxIsLockRealizable** routine is called by [RDBSS](/windows-hardware/drivers/ifs/the-rdbss-driver-and-library) to request that a network mini-redirector indicate whether a specific byte-range lock is supported on this NET_ROOT structure.

## -parameters

### -param Fcb

[in, out] A pointer to the FCB structure.

### -param ByteOffset

[in] A value indicating the byte offset for the byte range lock.

### -param Length

[in] A value indicating the length for the byte range lock.

### -param LowIoLockFlags

[in] A value with a bitmask indicating the I/O lock flags.

## -returns

**MRxIsLockRealizable** returns STATUS_SUCCESS on success or an appropriate NTSTATUS value, such as the following:

| Return code | Description |
| ------------- | ------------- |
| STATUS_NOT_SUPPORTED | The byte range lock that is requested is not supported. A network mini-redirector would return this value for a lock request that is not supported even if other types of byte range locks are supported. Unsupported locks might include 64-bit locks (the **ByteOffset->HighPart** member is nonzero), zero-length locks (the **Length** parameter is zero), or shared locks (the LOWIO_LOCKSFLAG_EXCLUSIVELOCK bit of the **LowIoLockFlags** parameter is not set).

## -remarks

**MRxIsLockRealizable** determines whether the specific byte-range lock requested is supported on this NET_ROOT structure. A network mini-redirector might support certain byte range locks and not support others. For example, a network mini-redirector might only support 32-bit byte range locks or exclusive locks.

**MRxIsLockRealizable** is called in response to receiving an IRP with the IRP_MN_LOCK minor function.

## -see-also

[**MRxAreFilesAliased**](nc-mrx-pmrx_chkfcb_calldown.md)

[**MRxCleanupFobx**](/previous-versions/windows/hardware/drivers/ff549841(v=vs.85))

[**MRxCloseSrvOpen**](nc-mrx-pmrx_calldown.md)

[**MRxCollapseOpen**](/windows-hardware/drivers/ifs/mrxcollapseopen)

[**MRxCreate**](/windows-hardware/drivers/ifs/mrxcreate)

[**MRxDeallocateForFcb**](nc-mrx-pmrx_deallocate_for_fcb.md)

[**MRxDeallocateForFobx**](nc-mrx-pmrx_deallocate_for_fobx.md)

[**MRxExtendForCache**](nc-mrx-pmrx_extendfile_calldown.md)

[**MRxExtendForNonCache**](/windows-hardware/drivers/ifs/mrxextendfornoncache)

[**MRxFlush**](/windows-hardware/drivers/ifs/mrxflush)

[**MRxForceClosed**](nc-mrx-pmrx_forceclosed_calldown.md)

[**MRxShouldTryToCollapseThisOpen**](/windows-hardware/drivers/ifs/mrxshouldtrytocollapsethisopen)

[**MRxTruncate**](/windows-hardware/drivers/ifs/mrxtruncate)

[**MRxZeroExtend**](/windows-hardware/drivers/ifs/mrxzeroextend)
