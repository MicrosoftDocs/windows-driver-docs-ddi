---
UID: NF:irb.AtaPortWriteRegisterUshort
title: AtaPortWriteRegisterUshort function
author: windows-driver-content
description: The AtaPortWriteRegisterUshort routine transfers a USHORT value to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportwriteregisterushort.htm
tech.root: storage
ms.assetid: 26acd4ce-b5e8-405a-bc9f-b08627f4830f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AtaPortWriteRegisterUshort, AtaPortWriteRegisterUshort routine [Storage Devices], atartns_09e1e2b6-ad88-4af7-9623-f9e441e491cb.xml, irb/AtaPortWriteRegisterUshort, storage.ataportwriteregisterushort
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
-	AtaPortWriteRegisterUshort
product:
- Windows
targetos: Windows
req.typenames: 
---

# AtaPortWriteRegisterUshort function


## -description


The <b>AtaPortWriteRegisterUshort</b> routine transfers a USHORT value to the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Register [in]

A pointer to the destination register. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550160">AtaPortGetDeviceBase</a>.


### -param Value [in]

Specifies the value to write to the register for the HBA.


## -returns



None 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550160">AtaPortGetDeviceBase</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550277">AtaPortWriteRegisterUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550280">AtaPortWriteRegisterUlong</a>
 

 

