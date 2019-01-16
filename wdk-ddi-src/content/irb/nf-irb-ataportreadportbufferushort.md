---
UID: NF:irb.AtaPortReadPortBufferUshort
title: AtaPortReadPortBufferUshort function
description: The AtaPortReadPortBufferUshort routine transfers a given number of USHORT values from the HBA to a buffer.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportreadportbufferushort.htm
tech.root: storage
ms.assetid: f118af3b-5a9a-486b-9550-9b48bdfb48cd
ms.date: 03/29/2018
ms.keywords: AtaPortReadPortBufferUshort, AtaPortReadPortBufferUshort routine [Storage Devices], atartns_9cf8ae36-e364-4fb8-9fda-c8a78cd022b4.xml, irb/AtaPortReadPortBufferUshort, storage.ataportreadportbufferushort
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
-	AtaPortReadPortBufferUshort
product:
- Windows
targetos: Windows
req.typenames: 
---

# AtaPortReadPortBufferUshort function


## -description


The <b>AtaPortReadPortBufferUshort</b> routine transfers a given number of USHORT values from the HBA to a buffer.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Port [in]

A pointer to the I/O port. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550160">AtaPortGetDeviceBase</a>.


### -param Buffer [in]

A pointer to the destination buffer. 


### -param Count [in]

Specifies the number of USHORT values to read from the HBA.


## -returns



None 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550160">AtaPortGetDeviceBase</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550175">AtaPortReadPortBufferUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550177">AtaPortReadPortBufferUlong</a>
 

 

