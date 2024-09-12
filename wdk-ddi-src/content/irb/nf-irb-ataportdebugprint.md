---
UID: NF:irb.AtaPortDebugPrint
title: AtaPortDebugPrint function (irb.h)
description: The AtaPortDebugPrint routine passes a message string to the kernel debugger for the debugger to print.
old-location: storage\ataportdebugprint.htm
tech.root: storage
ms.date: 01/03/2022
keywords: ["AtaPortDebugPrint function"]
ms.keywords: AtaPortDebugPrint, AtaPortDebugPrint routine [Storage Devices], atartns_57e04fb5-19ac-42fc-9bc5-32645ef61320.xml, irb/AtaPortDebugPrint, storage.ataportdebugprint
req.header: irb.h
req.include-header: Ata.h, Irb.h
req.target-type: Desktop
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
req.lib: Ataport.lib; Pciidex.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - AtaPortDebugPrint
 - irb/AtaPortDebugPrint
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ataport.lib
 - ataport.dll
 - pciidex.lib
 - pciidex.dll
api_name:
 - AtaPortDebugPrint
---

# AtaPortDebugPrint function

## -description

The **AtaPortDebugPrint** routine passes a message string to the kernel debugger for the debugger to print.

> [!NOTE]
>
> The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Use the [Storport driver](/windows-hardware/drivers/storage/storport-driver) and [Storport miniport](/windows-hardware/drivers/storage/storport-miniport-drivers) driver models instead.

## -parameters

### -param DebugPrintLevel

Contains a value between 0 and 3 that specifies the level of verbosity, where a value of 3 signifies the highest level of verbosity and a value of 0 signifies the lowest level. See Remarks.

### -param DebugMessage

Pointer to the debug string to print.

### -param ...

Variadic arguments to be used with the string that **DebugMessage** points to.

## -remarks

**ScsiDebugPrint** will print the message pointed to by **DebugMessage**, along with other debugging information depending on the value of **DebugPrintLevel** and a port driver-specific mask. Use the **nt!kd_idep_mask** command to set the desired level of verbosity. For more information about the kernel debugger, see [Getting Started with WinDbg - Kernel Mode](/windows-hardware/drivers/debugger/getting-started-with-windbg--kernel-mode-).

## -see-also

[**DbgPrintEx**](../wdm/nf-wdm-dbgprintex.md)
