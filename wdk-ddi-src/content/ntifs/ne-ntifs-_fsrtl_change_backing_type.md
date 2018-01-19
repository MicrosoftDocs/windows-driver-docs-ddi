---
UID: NE:ntifs._FSRTL_CHANGE_BACKING_TYPE
title: _FSRTL_CHANGE_BACKING_TYPE
author: windows-driver-content
description: The FSRTL_CHANGE_BACKING_TYPE enumeration specifies the type of cache or control area that a file object designates.
old-location: ifsk\fsrtl_change_backing_type.htm
old-project: ifsk
ms.assetid: 952812f4-5d29-4d1d-ab81-dd3a76a5f04c
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _FSRTL_CHANGE_BACKING_TYPE, *PFSRTL_CHANGE_BACKING_TYPE, FSRTL_CHANGE_BACKING_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FSRTL_CHANGE_BACKING_TYPE
req.alt-loc: ntifs.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PFSRTL_CHANGE_BACKING_TYPE, FSRTL_CHANGE_BACKING_TYPE
---

# _FSRTL_CHANGE_BACKING_TYPE enumeration



## -description
The FSRTL_CHANGE_BACKING_TYPE enumeration specifies the type of cache or control area that a file object designates.



## -syntax

````
typedef enum _FSRTL_CHANGE_BACKING_TYPE { 
  ChangeDataControlArea   = 0,
  ChangeImageControlArea  = 1,
  ChangeSharedCacheMap    = 2
} FSRTL_CHANGE_BACKING_TYPE, *PFSRTL_CHANGE_BACKING_TYPE;
````


## -enum-fields

### -field ChangeDataControlArea

The data control area of the memory manager.


### -field ChangeImageControlArea

An image control area that belongs to the memory manager.


### -field ChangeSharedCacheMap

The shared cache map of the cache manager.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtlchangebackingfileobject.md">FsRtlChangeBackingFileObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FSRTL_CHANGE_BACKING_TYPE enumeration%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

