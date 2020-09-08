---
UID: NS:wdfmemory._WDFMEMORY_OFFSET
title: _WDFMEMORY_OFFSET (wdfmemory.h)
description: The WDFMEMORY_OFFSET structure identifies a subsection of a memory object's buffer.
old-location: wdf\wdfmemory_offset.htm
tech.root: wdf
ms.assetid: ca891a21-e7ab-4230-bfc4-adfdb413838b
ms.date: 02/26/2018
keywords: ["WDFMEMORY_OFFSET structure"]
ms.keywords: "*PWDFMEMORY_OFFSET, DFMemoryObjectRef_d6ea5bd1-f672-4624-9663-f1e5f70eb8b2.xml, PWDFMEMORY_OFFSET, PWDFMEMORY_OFFSET structure pointer, WDFMEMORY_OFFSET, WDFMEMORY_OFFSET structure, _WDFMEMORY_OFFSET, kmdf.wdfmemory_offset, wdf.wdfmemory_offset, wdfmemory/PWDFMEMORY_OFFSET, wdfmemory/WDFMEMORY_OFFSET"
req.header: wdfmemory.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
req.typenames: WDFMEMORY_OFFSET, *PWDFMEMORY_OFFSET
f1_keywords:
 - _WDFMEMORY_OFFSET
 - wdfmemory/_WDFMEMORY_OFFSET
 - PWDFMEMORY_OFFSET
 - wdfmemory/PWDFMEMORY_OFFSET
 - WDFMEMORY_OFFSET
 - wdfmemory/WDFMEMORY_OFFSET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfmemory.h
api_name:
 - WDFMEMORY_OFFSET
---

# _WDFMEMORY_OFFSET structure (wdfmemory.h)


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDFMEMORY_OFFSET</b> structure identifies a subsection of a memory object's buffer.

## -struct-fields

### -field BufferOffset

A byte offset from the beginning of the memory object's buffer. This offset identifies the location of the buffer's subsection. A value of zero represents the beginning of the buffer.

### -field BufferLength

The length, in bytes, of the buffer's subsection. A value of zero represents the entire buffer.

## -remarks

The <b>WDFMEMORY_OFFSET</b> structure is used as a member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/ns-wdfmemory-_wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a> structure and as an input parameter to various I/O target object methods.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/ns-wdfmemory-_wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a>

