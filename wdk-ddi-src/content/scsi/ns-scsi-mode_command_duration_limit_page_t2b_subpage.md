---
UID: NS:scsi._MODE_COMMAND_DURATION_LIMIT_PAGE_T2B_SUBPAGE
tech.root: storage
title: MODE_COMMAND_DURATION_LIMIT_PAGE_T2B_SUBPAGE (scsi.h)
ms.date: 05/24/2022
targetos: Windows
description: Learn more about the MODE_COMMAND_DURATION_LIMIT_PAGE_T2B_SUBPAGE (scsi.h) structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: scsi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: MODE_COMMAND_DURATION_LIMIT_PAGE_T2B_SUBPAGE, *PMODE_COMMAND_DURATION_LIMIT_PAGE_T2B_SUBPAGE
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - scsi.h
api_name:
 - _MODE_COMMAND_DURATION_LIMIT_PAGE_T2B_SUBPAGE
 - PMODE_COMMAND_DURATION_LIMIT_PAGE_T2B_SUBPAGE
 - MODE_COMMAND_DURATION_LIMIT_PAGE_T2B_SUBPAGE
f1_keywords:
 - _MODE_COMMAND_DURATION_LIMIT_PAGE_T2B_SUBPAGE
 - scsi/_MODE_COMMAND_DURATION_LIMIT_PAGE_T2B_SUBPAGE
 - PMODE_COMMAND_DURATION_LIMIT_PAGE_T2B_SUBPAGE
 - scsi/PMODE_COMMAND_DURATION_LIMIT_PAGE_T2B_SUBPAGE
 - MODE_COMMAND_DURATION_LIMIT_PAGE_T2B_SUBPAGE
 - scsi/MODE_COMMAND_DURATION_LIMIT_PAGE_T2B_SUBPAGE
dev_langs:
 - c++
helpviewer_keywords:
 - _MODE_COMMAND_DURATION_LIMIT_PAGE_T2B_SUBPAGE
---

## -description

The **MODE_COMMAND_DURATION_LIMIT_PAGE_T2B_SUBPAGE** structure describes the Command Duration Limit T2B mode page, described in Section 7.5.12 of the [T10 SCSI Primary Commands specification (SPC-6)](https://www.t10.org/members/w_spc6.htm).

## -struct-fields

### -field PageCode

Described in the specification.

### -field SubPageFormat

Described in the specification.

### -field PageSavable

Described in the specification.

### -field SubPageCode

Described in the specification.

### -field PageLength

Described in the specification.

### -field Reserved

Reserved.

### -field Reserved1

Reserved.

### -field PerfvsLatencyControls

Described in the specification.

### -field T2CommandDurationLimitDescriptors

An array of **DURATION_LIMIT_T2_DESCRIPTOR_COUNT** [**T2_COMMAND_DURATION_LIMIT_DESCRIPTOR**](ns-scsi-t2_command_duration_limit_descriptor.md) structures, where each structure contains a T2 command duration limit descriptor.

## -remarks

See Section 7.5.12 of the [T10 SCSI Primary Commands specification (SPC-6)](https://www.t10.org/members/w_spc6.htm) for details.

## -see-also

[**MODE_COMMAND_DURATION_LIMIT_PAGE_T2A_SUBPAGE**](ns-scsi-mode_command_duration_limit_page_t2a_subpage.md)

[**MODE_PAGE_SUBPAGE_HEADER**](ns-scsi-mode_page_subpage_header.md)
