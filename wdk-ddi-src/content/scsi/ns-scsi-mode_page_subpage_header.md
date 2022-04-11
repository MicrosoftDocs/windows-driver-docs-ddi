---
UID: NS:scsi._MODE_PAGE_SUBPAGE_HEADER
tech.root: storage
title: MODE_PAGE_SUBPAGE_HEADER
ms.date: 05/24/2022
targetos: Windows
description: Learn more about the MODE_PAGE_SUBPAGE_HEADER structure.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: scsi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: WIN11_NEXT
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
 - scsi.h
api_name:
 - _MODE_PAGE_SUBPAGE_HEADER
 - PMODE_PAGE_SUBPAGE_HEADER
 - MODE_PAGE_SUBPAGE_HEADER
f1_keywords:
 - _MODE_PAGE_SUBPAGE_HEADER
 - scsi/_MODE_PAGE_SUBPAGE_HEADER
 - PMODE_PAGE_SUBPAGE_HEADER
 - scsi/PMODE_PAGE_SUBPAGE_HEADER
 - MODE_PAGE_SUBPAGE_HEADER
 - scsi/MODE_PAGE_SUBPAGE_HEADER
dev_langs:
 - c++
helpviewer_keywords:
 - _MODE_PAGE_SUBPAGE_HEADER
---

## -description

The **MODE_PAGE_SUBPAGE_HEADER** structure contains header information for the page_0 or sub_page mode page format, as defined in Section 7.5.8 of the T10 SCSI Primary Commands specification.

## -struct-fields

### -field PageCode

Along with **SubPageCode**, identifies the format and parameters defined for the mode page.

### -field SubPageFormat

A value of zero indicates that the page_0 mode page format is being used. A value of one indicates that the sub_page mode page format is being used.

### -field PageSavable

If the command is MODE SENSE, a value of zero indicates that the device server is not able to save the supported mode parameters. A value of one indicates that the mode page may be saved by the logical unit in a nonvolatile, vendor-specific location. **PageSavable** is reserved when using the MODE SELECT command.

### -field SubPageCode

Along with **PageCode**, identifies the format and parameters defined for the mode page. **SubPageCode** is meaningful only in the context of its associated **PageCode**.

### -field PageLength

The length of the set of mode parameters that follow, in bytes.

## -remarks

Page codes and subpage codes apply to all device types or apply to a specific device type. Page codes and subpage codes that apply to a specific device type are defined in the command standard for that device type.

See Section 7.5.8 of the T10 SCSI Primary Commands specification for additional details.

## -see-also

[**MODE_COMMAND_DURATION_LIMIT_PAGE_T2A_SUBPAGE**](ns-scsi-mode_command_duration_limit_page_t2a_subpage.md)

[**MODE_COMMAND_DURATION_LIMIT_PAGE_T2B_SUBPAGE**](ns-scsi-mode_command_duration_limit_page_t2b_subpage.md)
