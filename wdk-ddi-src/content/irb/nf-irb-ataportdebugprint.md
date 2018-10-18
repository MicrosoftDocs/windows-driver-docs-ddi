---
UID: NF:irb.AtaPortDebugPrint
title: AtaPortDebugPrint function
author: windows-driver-content
description: The AtaPortDebugPrint routine passes a message string to the kernel debugger for the debugger to print.
old-location: storage\ataportdebugprint.htm
tech.root: storage
ms.assetid: 2a93d30f-4aa0-46b9-b9c7-cc15c62f3053
ms.date: 3/29/2018
ms.keywords: AtaPortDebugPrint, AtaPortDebugPrint routine [Storage Devices], atartns_57e04fb5-19ac-42fc-9bc5-32645ef61320.xml, irb/AtaPortDebugPrint, storage.ataportdebugprint
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ataport.lib
-	ataport.dll
-	pciidex.lib
-	pciidex.dll
api_name:
-	AtaPortDebugPrint
product:
- Windows
targetos: Windows
req.typenames: 
---

# AtaPortDebugPrint function


## -description


The <b>AtaPortDebugPrint</b> routine passes a message string to the kernel debugger for the debugger to print. 
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param DebugPrintLevel

Determines how much debug information to display. 


### -param DebugMessage

A pointer to the debug message to display.


### -param param

TBD




## -returns



None 




## -remarks



The verbosity of debug output is determined by <i>DebugPrintLevel</i> and a port driver-specific mask. Use the <b>nt!kd_idep_mask</b> command to set the desired level of verbosity. For more information about the kernel debugger, see the <a href="https://msdn.microsoft.com/e2490442-9d90-454b-95e0-db8c5d7fa19a">Using a Debugger</a> topic 



