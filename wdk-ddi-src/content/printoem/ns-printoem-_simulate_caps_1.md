---
UID: NS:printoem._SIMULATE_CAPS_1
title: SIMULATE_CAPS_1 (printoem.h)
description: The SIMULATE_CAPS_1 structure contains information about the types of simulations a spooler supports.
tech.root: print
ms.date: 08/12/2022
keywords: ["SIMULATE_CAPS_1 structure"]
ms.keywords: "*PSIMULATE_CAPS_1, PSIMULATE_CAPS_1, PSIMULATE_CAPS_1 structure pointer [Print Devices], SIMULATE_CAPS_1, SIMULATE_CAPS_1 structure [Print Devices], _SIMULATE_CAPS_1, print.simulate_caps_1, print_interface-graphics_cb1ba0de-be04-4b11-a746-97fd3f2bc213.xml, printoem/PSIMULATE_CAPS_1, printoem/SIMULATE_CAPS_1"
req.header: printoem.h
req.include-header: Printoem.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
req.typenames: SIMULATE_CAPS_1, *PSIMULATE_CAPS_1
f1_keywords:
 - _SIMULATE_CAPS_1
 - printoem/_SIMULATE_CAPS_1
 - PSIMULATE_CAPS_1
 - printoem/PSIMULATE_CAPS_1
 - SIMULATE_CAPS_1
 - printoem/SIMULATE_CAPS_1
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - _SIMULATE_CAPS_1
 - PSIMULATE_CAPS_1
 - SIMULATE_CAPS_1
---

## -description

The **SIMULATE_CAPS_1** structure contains information about the types of simulations a spooler supports.

## -struct-fields

### -field dwLevel

Specifies the version of this structure. This value must be 1.

### -field dwPageOrderFlags

Specifies the order in which pages will be printed. This member can be set to one of the following values:

| Flag | Definition |
|--|--|
| BOOKLET_PRINT | Pages should be printed in booklet form, with two document pages printed on one side of a physical page. In landscape mode, the two document pages are printed side-by-side on the paper. In portrait mode, the two document pages are printed top-and-bottom. |
| NORMAL_PRINT | Pages should be printed in normal order: page 1, page 2, and so on. |
| REVERSE_PRINT | Pages should be printed in reverse order: last page, next-to-last page, and so on. |

### -field dwNumberOfCopies

Specifies the maximum number of copies the spooler can handle.

### -field dwCollate

Specifies whether the spooler supports collation. A value of 1 indicates that the spooler supports collation, and a value of 0 indicates that it does not.

### -field dwNupOptions

Is a bitmask representing the various numbers of document pages the printer can print on a physical page. The least significant bit represents 1 document page per page, the next bit represents 2 document pages per page, the next bit represents 3 document pages per physical page, and so on. For example, 0x0000810B indicates that the spooler supports 1, 2, 4, 9, and 16 document pages per physical page.

## -remarks

The **IPrintCoreUI2::QuerySimulationSupport** method uses this structure to report the spooler's level of simulation support to a user-interface plug-in.

## -see-also

[IPrintCoreUI2::QuerySimulationSupport](../prcomoem/nf-prcomoem-iprintcoreui2-querysimulationsupport.md)