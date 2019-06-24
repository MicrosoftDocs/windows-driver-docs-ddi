---
UID: NS:wdm._KBUGCHECK_SECONDARY_DUMP_DATA_EX
title: KBUGCHECK_SECONDARY_DUMP_DATA_EX
author: windows-driver-content
description: 
tech.root:
ms.assetid: dc6b3017-60bd-4681-bb95-3c97b0e604e6
ms.author: windowsdriverdev
ms.date: 
ms.topic: struct
ms.keywords: KBUGCHECK_SECONDARY_DUMP_DATA_EX, KBUGCHECK_SECONDARY_DUMP_DATA_EX, *PKBUGCHECK_SECONDARY_DUMP_DATA_EX, 
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: KBUGCHECK_SECONDARY_DUMP_DATA_EX, *PKBUGCHECK_SECONDARY_DUMP_DATA_EX
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - wdm.h
api_name: 
 - KBUGCHECK_SECONDARY_DUMP_DATA_EX
product: 
 - Windows
targetos: Windows
---

# KBUGCHECK_SECONDARY_DUMP_DATA_EX structure

## -description

The <b>KBUGCHECK_SECONDARY_DUMP_DATA_EX</b> structure describes multipart data to be written by [*KBUGCHECK_REASON_CALLBACK_ROUTINE*](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-kbugcheck_reason_callback_routine) callback routine to the crash dump file.


## -struct-fields

### -field InBuffer

Pointer to a buffer that is allocated by the system.

### -field InBufferLength

Specifies the size of the buffer, in bytes, specified by the <b>InBuffer</b> member.

### -field MaximumAllowed

Specifies the maximum amount of data that the KbCallbackSecondaryDumpData routine can write to the crash dump file.

### -field Guid

Specifies a GUID that identifies the driver's crash dump data. (Drivers must use unique GUIDs to mark their crash dump data. Use the GuidGen.exe tool to generate GUIDs for your driver. This tool is included in the Microsoft Windows SDK.)

### -field OutBuffer

Pointer to the buffer where the driver writes its crash dump data, or <b>NULL</b>.

### -field OutBufferLength

Specifies the size of the buffer, in bytes, that was specified by the <b>OutBuffer</b> member.
 
### -field Context
 
### -field Flags
 
### -field DumpType
 
### -field BugCheckCode
 
### -field BugCheckParameter1
 
### -field BugCheckParameter2
 
### -field BugCheckParameter3
 
### -field BugCheckParameter4
 

## -remarks

## -see-also