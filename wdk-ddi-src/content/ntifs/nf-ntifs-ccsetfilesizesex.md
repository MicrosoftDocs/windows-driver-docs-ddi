---
UID: NF:ntifs.CcSetFileSizesEx
tech.root: ifsk
title: CcSetFileSizesEx
ms.date: 02/02/2024
targetos: Windows
description: Learn more about the CcSetFileSizesEx function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - ntifs.h
api_name:
 - CcSetFileSizesEx
f1_keywords:
 - CcSetFileSizesEx
 - ntifs/CcSetFileSizesEx
dev_langs:
 - c++
helpviewer_keywords:
 - CcSetFileSizesEx
---

## -description

The **CcSetFileSizesEx** routine updates the cache maps and section object for a cached file whose size has changed.

## -parameters

### -param FileObject

[in] Pointer to a file object for the cached file.

### -param FileSizes

[in] Pointer to a [**CC_FILE_SIZES**](ns-ntifs-cc_file_sizes.md) structure containing the new file size information.

## -returns

**CcSetFileSizesEx** returns STATUS_SUCCESS if the file size was successfully changed, and, if a purge was needed that the purge was successful. Otherwise it returns a non-success NSTATUS code such as STATUS_INSUFFICIENT_RESOURCES, and might raise a status exception.

Regarding raising a status exception on error:

* If the operation causes **CcSetFileSizesEx** to flush and/or purge the file, **CcSetFileSizesEx** won't raise on errors; it just returns the appropriate non-success NTSTATUS code of the flush or purge operation.

* If the operation causes **CcSetFileSizesEx** to extend the section, then **CcSetFileSizesEx** will raise on any error it hits during this extension.

## -remarks

File systems must call **CcSetFileSizesEx** to update the cache manager data structures whenever one of the following changes is made to a cached file:

* Its allocation size is increased.

* Its valid data length is decreased.

* Its valid data length is increased by a non-cached I/O operation.

* Its file size is increased or decreased.

If the operation causes **CcSetFileSizesEx** to extend the section and a failure occurs, **CcSetFileSizesEx** raises a status exception for that particular failure. For example, if a pool allocation failure occurs, **CcSetFileSizesEx** raises a STATUS_INSUFFICIENT_RESOURCES exception. Therefore, to gain control if a failure occurs, the driver should wrap the call to **CcSetFileSizesEx** in a *try-except* or *try-finally* statement.

The file system must ensure that the cache map is valid and will remain so for the duration of this call.

To cache a file, use [**CcInitializeCacheMap**](nf-ntifs-ccinitializecachemap.md).

To get the size of the cached file, pass **FileObject** to [**CcGetFileSizePointer**](nf-ntifs-ccgetfilesizepointer.md).

## -see-also

[**CcInitializeCacheMap**](nf-ntifs-ccinitializecachemap.md)

[**CcSetCacheFileSizes**](nf-ntifs-ccsetcachefilesizes.md)
