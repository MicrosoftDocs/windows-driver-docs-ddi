---
UID: NS:minitape._MODE_PAGE_SUBPAGE_HEADER
tech.root: storage
title: MODE_PAGE_SUBPAGE_HEADER (minitape.h)
ms.date: 05/24/2022
targetos: Windows
description: Learn more about the MODE_PAGE_SUBPAGE_HEADER (minitape.h) structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: minitape.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: MODE_PAGE_SUBPAGE_HEADER, *PMODE_PAGE_SUBPAGE_HEADER
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - minitape.h
api_name:
 - _MODE_PAGE_SUBPAGE_HEADER
 - PMODE_PAGE_SUBPAGE_HEADER
 - MODE_PAGE_SUBPAGE_HEADER
f1_keywords:
 - _MODE_PAGE_SUBPAGE_HEADER
 - minitape/_MODE_PAGE_SUBPAGE_HEADER
 - PMODE_PAGE_SUBPAGE_HEADER
 - minitape/PMODE_PAGE_SUBPAGE_HEADER
 - MODE_PAGE_SUBPAGE_HEADER
 - minitape/MODE_PAGE_SUBPAGE_HEADER
dev_langs:
 - c++
helpviewer_keywords:
 - _MODE_PAGE_SUBPAGE_HEADER
---

## -description

The **MODE_PAGE_SUBPAGE_HEADER** structure contains header information for the page_0 or sub_page mode page format, as defined in Section 7.5.8 of the [T10 SCSI Primary Commands specification (SPC-6)](https://www.t10.org/members/w_spc6.htm).

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

## -remarks

See Section 7.5.8 of the [T10 SCSI Primary Commands specification (SPC-6)](https://www.t10.org/members/w_spc6.htm) for details.

## -see-also

[**MODE_COMMAND_DURATION_LIMIT_PAGE_T2A_SUBPAGE**](ns-minitape-mode_command_duration_limit_page_t2a_subpage.md)

[**MODE_COMMAND_DURATION_LIMIT_PAGE_T2B_SUBPAGE**](ns-minitape-mode_command_duration_limit_page_t2b_subpage.md)
