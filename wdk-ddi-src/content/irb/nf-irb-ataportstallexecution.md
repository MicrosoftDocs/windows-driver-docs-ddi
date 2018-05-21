---
UID: NF:irb.AtaPortStallExecution
title: AtaPortStallExecution function
author: windows-driver-content
description: The AtaPortStallExecution stalls in the miniport driver.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportstallexecution.htm
old-project: storage
ms.assetid: 5dae484f-fb79-4291-bae5-dba0be7f9b97
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AtaPortStallExecution, AtaPortStallExecution function [Storage Devices], atartns_3a78519d-4ee5-4a4a-9564-1d2bbd256300.xml, irb/AtaPortStallExecution, storage.ataportstallexecution
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	AtaPortStallExecution
product:
- Windows
targetos: Windows
req.typenames: 
---

# AtaPortStallExecution function


## -description


The <b>AtaPortStallExecution</b> stalls in the miniport driver.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Delay [in]

Specifies the delay interval, in microseconds.


## -returns



None 




## -remarks



Miniport drivers should rarely call the <b>AtaPortStallExecution</b> routine. The total stall time in any miniport driver routine must always be less than one millisecond. Because this call ties up a processor, the processor does no useful work while it stalls in the driver.

Typically, a miniport driver should call <b>AtaPortStallExecution</b> only if the driver must wait for some sort of state change on the HBA that is unable to cause an interrupt, or if the driver must delay for a very short interval between accesses to the HBA.

Miniport drivers should use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550227">AtaPortRequestTimer</a> routine for delays longer than 1 millisecond.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550227">AtaPortRequestTimer</a>
 

 

