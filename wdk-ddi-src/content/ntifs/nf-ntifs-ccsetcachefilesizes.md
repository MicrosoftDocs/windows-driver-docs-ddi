---
UID: NF:ntifs.CcSetCacheFileSizes
tech.root: ifsk
title: CcSetCacheFileSizes
ms.date: 02/05/2024
targetos: Windows
description: Learn more about the CcSetCacheFileSizes function.
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
req.target-min-winverclnt: Windows 11, version 22H2
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
 - CcSetCacheFileSizes
f1_keywords:
 - CcSetCacheFileSizes
 - ntifs/CcSetCacheFileSizes
dev_langs:
 - c++
helpviewer_keywords:
 - CcSetCacheFileSizes
---

## -description

The **CcSetCacheFileSizes** function sets the cache manager file sizes by section object pointers.

## -parameters

### -param SectionObjectPointer [in]

Pointer to a [**SECTION_OBJECT_POINTERS**](../wdm/ns-wdm-_section_object_pointers.md) structure that contains the section object information.

### -param FileSizes [in]

Pointer to a [**CC_FILE_SIZES**](ns-ntifs-cc_file_sizes.md) structure that specifies the file size to set.

## -returns

**CcSetCacheFileSizes** returns STATUS_SUCCESS if the file size was successfully changed, and, if a purge was needed that the purge was successful. Otherwise it returns a non-success NSTATUS code such as STATUS_INSUFFICIENT_RESOURCES, and might raise a status exception.

Regarding raising a status exception on error:

* If the operation causes **CcSetCacheFileSizes** to flush and/or purge the file, **CcSetCacheFileSizes** won't raise on errors; it just returns the appropriate non-success NTSTATUS code of the flush or purge operation.

* If the operation causes **CcSetCacheFileSizes** to extend the section, then **CcSetCacheFileSizes** will raise on any error it hits during this extension.

## -remarks

If the operation causes **CcSetCacheFileSizes** to extend the section and a failure occurs, **CcSetCacheFileSizes** raises a status exception for that particular failure. For example, if a pool allocation failure occurs, **CcSetCacheFileSizes** raises a STATUS_INSUFFICIENT_RESOURCES exception. Therefore, to gain control if a failure occurs, the driver should wrap the call to **CcSetCacheFileSizes** in a *try-except* or *try-finally* statement.

The file system must ensure that the cache map is valid and will remain so for the duration of this call.

To get the size of the cached file, pass **SectionObjectPointer** to [**CcGetCacheFileSize**](nf-ntifs-ccgetcachefilesize.md).

## -see-also

[**CcGetCacheFileSize**](nf-ntifs-ccgetcachefilesize.md)

 [**CcSetFileSizesEx**](nf-ntifs-ccsetfilesizesex.md)
