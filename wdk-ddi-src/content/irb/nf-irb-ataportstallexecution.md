---
UID: NF:irb.AtaPortStallExecution
title: AtaPortStallExecution function
author: windows-driver-content
description: The AtaPortStallExecution stalls in the miniport driver.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportstallexecution.htm
old-project: storage
ms.assetid: 5dae484f-fb79-4291-bae5-dba0be7f9b97
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , A, AtaPortStallExecution, AtaPortStallExecution function [Storage Devices], E, P, S, a, atartns_3a78519d-4ee5-4a4a-9564-1d2bbd256300.xml, c, e, i, irb/AtaPortStallExecution, l, n, o, r, storage.ataportstallexecution, t, u, x"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ataport.lib
-	ataport.dll
-	pciidex.lib
-	pciidex.dll
apiname:
-	AtaPortStallExecution
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortStallExecution function


## -description


The <b>AtaPortStallExecution</b> stalls in the miniport driver.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
VOID AtaPortStallExecution(
  _In_ ULONG Delay
);
````


## -parameters




### -param Delay [in]

Specifies the delay interval, in microseconds.


## -returns



None 




## -remarks



Miniport drivers should rarely call the <b>AtaPortStallExecution</b> routine. The total stall time in any miniport driver routine must always be less than one millisecond. Because this call ties up a processor, the processor does no useful work while it stalls in the driver.

Typically, a miniport driver should call <b>AtaPortStallExecution</b> only if the driver must wait for some sort of state change on the HBA that is unable to cause an interrupt, or if the driver must delay for a very short interval between accesses to the HBA.

Miniport drivers should use the <a href="..\irb\nf-irb-ataportrequesttimer.md">AtaPortRequestTimer</a> routine for delays longer than 1 millisecond.




## -see-also

<a href="..\irb\nf-irb-ataportrequesttimer.md">AtaPortRequestTimer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortStallExecution function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

