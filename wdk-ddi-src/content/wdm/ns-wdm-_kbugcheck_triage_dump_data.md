---
UID: NS:wdm._KBUGCHECK_TRIAGE_DUMP_DATA
title: KBUGCHECK_TRIAGE_DUMP_DATA
author: windows-driver-content
description: 
tech.root:
ms.assetid: a6151c1e-1553-4f49-b502-93d63cad0844
ms.author: windowsdriverdev
ms.date: 
ms.topic: struct
ms.keywords: KBUGCHECK_TRIAGE_DUMP_DATA, KBUGCHECK_TRIAGE_DUMP_DATA, *PKBUGCHECK_TRIAGE_DUMP_DATA, 
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
req.typenames: KBUGCHECK_TRIAGE_DUMP_DATA, *PKBUGCHECK_TRIAGE_DUMP_DATA
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - wdm.h
api_name: 
 - KBUGCHECK_TRIAGE_DUMP_DATA
product: 
 - Windows
targetos: Windows
---

# KBUGCHECK_TRIAGE_DUMP_DATA structure

## -description

The <b>KBUGCHECK_TRIAGE_DUMP_DATA</b> structure describes dump data used in conjunction with the [*KBUGCHECK_REASON_CALLBACK_ROUTINE*](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-kbugcheck_reason_callback_routine) callback routine.


## -struct-fields

### -field DataArray

A pointer to a structure of type KTRIAGE_DUMP_DATA_ARRAY that is an out

### -field Flags

Contains flags that describe the remove pages request. The callback routine must set the value of this member. Set this member to the bitwise OR of one or more of the following flag bits: 

#### KB_TRIAGE_DUMP_DATA_FLAG_BUGCHECK_ACTIVE


### -field MaxVirtMemSize
 
### -field BugCheckCode

Contains a bug check code, which specifies the reason for the bug check. For a full list of bug check codes, see the Bugcodes.h header file included in the WDK.

### -field BugCheckParameter1
 
### -field BugCheckParameter2
 
### -field BugCheckParameter3
 
### -field BugCheckParameter4
 

## -remarks


The driver receives a structure of this type as a parameter to its [*KBUGCHECK_REASON_CALLBACK_ROUTINE*](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-kbugcheck_reason_callback_routine) callback routine.

From the callback routine, the driver calls the [**KeAddTriageDumpDataBlock**](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keaddtriagedumpdatablock) function to modify a dump data array.

The maximum size of a dump data array is 32 MB.

## -see-also