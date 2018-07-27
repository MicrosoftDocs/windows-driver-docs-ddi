---
UID: NF:irb.AtaPortWriteRegisterBufferUchar
title: AtaPortWriteRegisterBufferUchar function
author: windows-driver-content
description: The AtaPortWriteRegisterBufferUchar routine transfers the indicated number of unsigned bytes from a buffer to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportwriteregisterbufferuchar.htm
tech.root: storage
ms.assetid: 0b617fa4-da0b-4a98-a0e5-ad9fea67d980
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AtaPortWriteRegisterBufferUchar, AtaPortWriteRegisterBufferUchar routine [Storage Devices], atartns_6722ff8e-9f8c-4b6a-88d1-305f892250bd.xml, irb/AtaPortWriteRegisterBufferUchar, storage.ataportwriteregisterbufferuchar
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
-	AtaPortWriteRegisterBufferUchar
product:
- Windows
targetos: Windows
req.typenames: 
---

# AtaPortWriteRegisterBufferUchar function


## -description


The <b>AtaPortWriteRegisterBufferUchar</b> routine transfers the indicated number of unsigned bytes from a buffer to the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Register [in]

Contains the destination register address where the transfer should begin. This address value must be within the range of mapped I/O space addresses that are obtained by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550160">AtaPortGetDeviceBase</a>.


### -param Buffer [in]

A pointer to the source buffer.


### -param Count [in]

Specifies the number of unsigned bytes to write to the HBA.


## -returns



None 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550160">AtaPortGetDeviceBase</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550270">AtaPortWriteRegisterBufferUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550273">AtaPortWriteRegisterBufferUshort</a>
 

 

