---
UID: NS:minitape._T2_COMMAND_DURATION_LIMIT_DESCRIPTOR
tech.root: storage
title: T2_COMMAND_DURATION_LIMIT_DESCRIPTOR
ms.date: 05/24/2022
targetos: Windows
description: Learn more about the T2_COMMAND_DURATION_LIMIT_DESCRIPTOR (minitape.h) structure.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: minitape.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: WIN11_NEXT
req.target-min-winversvr: 
req.target-type: 
req.typenames: T2_COMMAND_DURATION_LIMIT_DESCRIPTOR, *PT2_COMMAND_DURATION_LIMIT_DESCRIPTOR
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - minitape.h
api_name:
 - _T2_COMMAND_DURATION_LIMIT_DESCRIPTOR
 - PT2_COMMAND_DURATION_LIMIT_DESCRIPTOR
 - T2_COMMAND_DURATION_LIMIT_DESCRIPTOR
f1_keywords:
 - _T2_COMMAND_DURATION_LIMIT_DESCRIPTOR
 - minitape/_T2_COMMAND_DURATION_LIMIT_DESCRIPTOR
 - PT2_COMMAND_DURATION_LIMIT_DESCRIPTOR
 - minitape/PT2_COMMAND_DURATION_LIMIT_DESCRIPTOR
 - T2_COMMAND_DURATION_LIMIT_DESCRIPTOR
 - minitape/T2_COMMAND_DURATION_LIMIT_DESCRIPTOR
dev_langs:
 - c++
helpviewer_keywords:
 - _T2_COMMAND_DURATION_LIMIT_DESCRIPTOR
---

## -description

The **T2_COMMAND_DURATION_LIMIT_DESCRIPTOR** structure describes the command duration limit (CDL) information that corresponds to one **T2CommandDurationLimitDescriptors** index in a [**MODE_COMMAND_DURATION_LIMIT_PAGE_T2A_SUBPAGE**](ns-minitape-mode_command_duration_limit_page_t2a_subpage.md) and [**MODE_COMMAND_DURATION_LIMIT_PAGE_T2B_SUBPAGE**](ns-minitape-mode_command_duration_limit_page_t2b_subpage.md) structure. See Table 459 (T2 Command Duration Limit Descriptor format) in the [T10 SCSI Primary Commands specification (SPC-6)](https://www.t10.org/members/w_spc6.htm) for details.

## -struct-fields

### -field T2CDLUNITS

Described in the specification.

### -field Reserved

Reserved.

### -field Reserved1

Reserved.

### -field MAX_INACTIVE_TIME

Described in the specification.

### -field MAX_ACTIVE_TIME

Described in the specification.

### -field MAX_ACTIVE_TIME_POLICY

Described in the specification.

### -field MAX_INACTIVE_TIME_POLICY

Described in the specification.

### -field Reserved2

Reserved.

### -field COMMAND_DURATION_GUIDELINE

Described in the specification.

### -field Reserved3

Reserved.

### -field COMMAND_DURATION_GUIDELINE_POLICY

Described in the specification.

### -field Reserved4

Reserved.

### -field BypassSequestration

Described in the specification.

### -field Reserved5

Reserved.

### -field Reserved6

Reserved.

## -remarks

See Table 459 in Section 7.5.11.2 of the [T10 SCSI Primary Commands specification (SPC-6)](https://www.t10.org/members/w_spc6.htm) for details.

## -see-also

[**MODE_COMMAND_DURATION_LIMIT_PAGE_T2A_SUBPAGE**](ns-minitape-mode_command_duration_limit_page_t2a_subpage.md)

[**MODE_COMMAND_DURATION_LIMIT_PAGE_T2B_SUBPAGE**](ns-minitape-mode_command_duration_limit_page_t2b_subpage.md)
