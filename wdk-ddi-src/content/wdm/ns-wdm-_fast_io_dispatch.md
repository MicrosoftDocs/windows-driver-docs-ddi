---
UID: NS:wdm._FAST_IO_DISPATCH
title: _FAST_IO_DISPATCH (wdm.h)
description: Contains a set of callback routines that a file system driver or file system filter driver (legacy) provides for fast I/O processing.
old-location: ifsk\fast_io_dispatch.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FAST_IO_DISPATCH structure"]
ms.keywords: "*PFAST_IO_DISPATCH, FAST_IO_DISPATCH, FAST_IO_DISPATCH structure [Installable File System Drivers], PFAST_IO_DISPATCH, PFAST_IO_DISPATCH structure pointer [Installable File System Drivers], _FAST_IO_DISPATCH, ifsk.fast_io_dispatch, wdm/FAST_IO_DISPATCH, wdm/PFAST_IO_DISPATCH"
req.header: wdm.h
req.include-header: 
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
req.typenames: FAST_IO_DISPATCH, *PFAST_IO_DISPATCH
f1_keywords:
 - _FAST_IO_DISPATCH
 - wdm/_FAST_IO_DISPATCH
 - PFAST_IO_DISPATCH
 - wdm/PFAST_IO_DISPATCH
 - FAST_IO_DISPATCH
 - wdm/FAST_IO_DISPATCH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _FAST_IO_DISPATCH
 - PFAST_IO_DISPATCH
 - FAST_IO_DISPATCH
---

# _FAST_IO_DISPATCH structure


## -description

Contains a set of callback routines that a file system driver or file system filter driver (legacy) provides for fast I/O processing.

## -struct-fields

### -field SizeOfFastIoDispatch

Set to <b>sizeof</b>(FAST_IO_DISPATCH).

### -field FastIoCheckIfPossible

A pointer to a callback routine that checks if fast I/O is possible for a either a read or a write operation.

### -field FastIoRead

A pointer to a callback routine that does a fast cached read, bypassing the IRP read path.  It is used to perform a copy read
    for a cached file object.

### -field FastIoWrite

A pointer to a callback routine that does a fast cached write, bypassing the IRP write path.  It is used to perform a copy write
    for a cached file object.

### -field FastIoQueryBasicInfo

A pointer to a callback routine for fast query of basic file information.

### -field FastIoQueryStandardInfo

A pointer to a callback routine for fast query of standard file information.

### -field FastIoLock

A pointer to a callback routine for doing a fast lock on a file object.

### -field FastIoUnlockSingle

A pointer to a callback routine for doing a fast release of a single lock on a file object.

### -field FastIoUnlockAll

A pointer to a callback routine for doing a fast release of a all locks held on a file object.

### -field FastIoUnlockAllByKey

A pointer to a callback routine for doing a fast release of a all locks grouped by a key.

### -field FastIoDeviceControl

A pointer to a callback routine for fast device control processing.

### -field AcquireFileForNtCreateSection

A pointer to a callback routine used by the memory manager to acquire a file exclusively.

### -field ReleaseFileForNtCreateSection

A pointer to a callback routine used by the memory manager to release a previously acquired file.

### -field FastIoDetachDevice

A pointer to a callback routine that is invoked to detach the current device object from a device object that
    is being deleted.

### -field FastIoQueryNetworkOpenInfo

A pointer to a callback routine for fast query of network file information.

### -field AcquireForModWrite

A pointer to a callback routine that decides which file system resource the modified page
    writer should acquire and acquires it if possible.

### -field MdlRead

A pointer to a callback routine that does a fast cached MDL read, bypassing the IRP read path.  It is used to perform a copy read
    for a cached file object.

### -field MdlReadComplete

A pointer to a callback routine that performs a fast completion of an MDL read.

### -field PrepareMdlWrite

A pointer to a callback routine that does a fast cached MDL write, bypassing the IRP write path.  It is used to perform a copy write
    for a cached file object.

### -field MdlWriteComplete

A pointer to a callback routine that performs a fast completion of an MDL write.

### -field FastIoReadCompressed

A pointer to a callback routine that performs a fast  compressed read of data from a file.

### -field FastIoWriteCompressed

A pointer to a callback routine that performs a fast  compressed write of data to  a file.

### -field MdlReadCompleteCompressed

A pointer to a callback routine that completes  a fast  MDL compressed read of data from  a file.

### -field MdlWriteCompleteCompressed

A pointer to a callback routine that completes  a fast  MDL compressed write of data to  a file.

### -field FastIoQueryOpen

A pointer to a callback routine that implements  a fast  open for path based queries.

### -field ReleaseForModWrite

This routine releases a file system resource previously acquired for
    the modified page write.

### -field AcquireForCcFlush

A pointer to a callback routine that acquires a file system resource prior to a cache flush.

### -field ReleaseForCcFlush

A pointer to a callback routine that releases a file system resource previously acquired for a cache flush.

