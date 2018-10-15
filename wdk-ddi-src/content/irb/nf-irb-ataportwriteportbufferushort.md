---
UID: NF:irb.AtaPortWritePortBufferUshort
title: AtaPortWritePortBufferUshort function
author: windows-driver-content
description: The AtaPortWritePortBufferUshort routine transfers the indicated number of USHORT values from a buffer to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportwriteportbufferushort.htm
tech.root: storage
ms.assetid: b2b5b126-8cb3-494f-a67e-f8d4f37ec639
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AtaPortWritePortBufferUshort, AtaPortWritePortBufferUshort routine [Storage Devices], atartns_78cda4b1-7995-40c3-a784-ed66d8a8d520.xml, irb/AtaPortWritePortBufferUshort, storage.ataportwriteportbufferushort
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
-	AtaPortWritePortBufferUshort
product:
- Windows
targetos: Windows
req.typenames: 
---

# AtaPortWritePortBufferUshort function


## -description


The <b>AtaPortWritePortBufferUshort</b> routine transfers the indicated number of USHORT values from a buffer to the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Port [in]

The pointer to the I/O port. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550160">AtaPortGetDeviceBase</a>.


### -param Buffer [in]

A pointer to the source buffer. 


### -param Count [in]

Specifies the number of USHORT values to write to the HBA.


## -returns



None 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550160">AtaPortGetDeviceBase</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550239">AtaPortWritePortBufferUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550241">AtaPortWritePortBufferUlong</a>
 

 

