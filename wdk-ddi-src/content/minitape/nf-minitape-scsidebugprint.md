---
UID: NF:minitape.ScsiDebugPrint
title: ScsiDebugPrint function (minitape.h)
description: The ScsiDebugPrint function (minitape.h) prints debug information with a specified level of verbosity based on global values.
old-location: storage\scsidebugprint.htm
tech.root: storage
ms.date: 01/03/2022
keywords: ["ScsiDebugPrint function"]
ms.keywords: ScsiDebugPrint, ScsiDebugPrint routine [Storage Devices], scsiprt_ef011e55-85be-4ec8-8ba3-3838417bcd15.xml, srb/ScsiDebugPrint, storage.scsidebugprint
req.header: minitape.h
req.include-header: Miniport.h, Scsi.h, Minitape.h
req.target-type: Desktop
req.target-min-winverclnt: Windows XP
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
req.lib: Scsiport.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - ScsiDebugPrint
 - minitape/ScsiDebugPrint
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Scsiport.lib
 - Scsiport.dll
api_name:
 - ScsiDebugPrint
---

# ScsiDebugPrint function (minitape.h)

## -description

The **ScsiDebugPrint** routine prints debug information with a level of verbosity based on global values set in the kernel debugger or set in the registry and initialized when the system boots.

> [!NOTE]
> The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Use the [Storport driver](/windows-hardware/drivers/storage/storport-driver) and [Storport miniport](/windows-hardware/drivers/storage/storport-miniport-drivers) driver models instead.

## -parameters

### -param DebugPrintLevel

Contains a value between 0 and 3 that specifies the level of verbosity, where a value of 3 signifies the highest level of verbosity and a value of 0 signifies the lowest level. See Remarks.

### -param DebugMessage

Pointer to the debug string to print.

### -param ...

Variadic arguments to be printed with the string that **DebugMessage** points to.

## -returns

None

## -remarks

**ScsiDebugPrint** prints the message pointed to by **DebugMessage**, along with other debugging information depending on the vaue of **DebugPrintLevel** as follows.

| DebugPrintLevel value | Value Passed to DbgPrintEx |
| --------------------- | -------------------------- |
| 0                     | DPFLTR_WARNING_LEVEL       |
| 1                     | DPFLTR_TRACE_LEVEL         |
| 2                     | DPFLTR_TRACE_LEVEL         |
| 3                     | DPFLTR_INFO_LEVEL          |

To view the message pointed to by **DebugMessage** from the kernel debugger, use the component filter mask Kd_ScsiMiniPort_Mask. For more information about debugging masks, see [**DbgPrintEx**](../wdm/nf-wdm-dbgprintex.md).

**ScsiDebugPrint** only functions in checked builds; it compiles to nothing in free builds.

## -see-also

[**DbgPrintEx**](../wdm/nf-wdm-dbgprintex.md)
