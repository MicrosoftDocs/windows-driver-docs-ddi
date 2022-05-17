---
UID: NF:ntddk.WheaErrorRecordBuilderAddSection
tech.root: kernel
title: WheaErrorRecordBuilderAddSection (ntddk.h)
ms.date: 03/25/2022
targetos: Windows
description: The WheaErrorRecordBuilderAddSection function finds the next section, initializes its descriptor, and returns a pointer for the caller to populate with data.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntddk.h
req.idl: 
req.include-header: Ntddk.h
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
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - WheaErrorRecordBuilderAddSection
f1_keywords:
 - WheaErrorRecordBuilderAddSection
 - ntddk/WheaErrorRecordBuilderAddSection
dev_langs:
 - c++
helpviewer_keywords:
 - WheaErrorRecordBuilderAddSection
---

## -description

The **WheaErrorRecordBuilderAddSection** function finds the next section, initializes its descriptor, and returns a pointer for the caller to populate with data.

## -parameters

### -param Record [in, out]

Supplies a buffer that contains the error record data.

### -param MaxSectionCount [in]

Defines the **UINT32** parameter *MaxSectionCount*.

### -param SectionLength [in]

Supplies a length for the new section to be added.

### -param Flags [in]

Supplies the flags for the section.

### -param SectionType [in]

Supplies the GUID to identify the section.

### -param DescriptorOut [in, out, optional]

Supplies an optional buffer to get the section descriptor if additional information needs to be added.

## -returns

A pointer to the next available space for error record information. Returns NULL if the record buffer is full.

## -remarks

## -see-also
