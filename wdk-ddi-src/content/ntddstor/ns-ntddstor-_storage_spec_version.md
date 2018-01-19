---
UID: NS:ntddstor._STORAGE_SPEC_VERSION
title: _STORAGE_SPEC_VERSION
author: windows-driver-content
description: Indicates the specification of the storage device.
old-location: storage\storage_spec_version.htm
old-project: storage
ms.assetid: E7E80C4E-C002-4F00-AF7E-6B8DDA337323
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _STORAGE_SPEC_VERSION, *PSTORAGE_SPEC_VERSION, STORAGE_SPEC_VERSION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_SPEC_VERSION
req.alt-loc: Ntddstor.h
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
req.typenames: *PSTORAGE_SPEC_VERSION, STORAGE_SPEC_VERSION
---

# _STORAGE_SPEC_VERSION structure



## -description
Indicates the specification of the storage device.



## -syntax

````
typedef union _STORAGE_SPEC_VERSION {
  struct {
    union {
      struct {
        BYTE SubMinor;
        BYTE Minor;
      } DUMMYSTRUCTNAME;
      WORD   AsUshort;
    } MinorVersion;
    WORD  MajorVersion;
  } DUMMYSTRUCTNAME;
  DWORD  AsUlong;
} STORAGE_SPEC_VERSION, *PSTORAGE_SPEC_VERSION;
````


## -struct-fields

### -field DUMMYSTRUCTNAME

The major and minor version of the storage specification.


### -field MinorVersion

The minor version of the storage specification.


### -field DUMMYSTRUCTNAME

The minor and sub-minor version of the storage specification.


### -field SubMinor

The sub-minor version of the storage specification.


### -field Minor

The minor version of the storage specification.

</dd>
</dl>

### -field AsUshort

The combination of the <b>Minor</b> and <b>SubMinor</b> versions of the storage specification.

</dd>
</dl>

### -field MajorVersion

The major version of the storage specification.

</dd>
</dl>

### -field AsUlong

The combination of the <b>MajorVersion</b> and <b>MinorVersion</b> versions of the storage specification.


## -remarks
This union allows for specifying the storage specification version, such as SBC 3, SATA 3.2, and NVMe 1.2.</p>