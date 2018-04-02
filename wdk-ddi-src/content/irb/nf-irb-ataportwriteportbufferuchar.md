---
UID: NF:irb.AtaPortWritePortBufferUchar
title: AtaPortWritePortBufferUchar function
author: windows-driver-content
description: The AtaPortWritePortBufferUchar routine transfers the indicated number of unsigned bytes from a buffer to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportwriteportbufferuchar.htm
old-project: storage
ms.assetid: 43c12b35-380c-46bc-9ea0-9745f047c81a
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AtaPortWritePortBufferUchar, AtaPortWritePortBufferUchar routine [Storage Devices], atartns_a1c82429-9d44-4a9b-8285-e632172a6be4.xml, irb/AtaPortWritePortBufferUchar, storage.ataportwriteportbufferuchar
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
-	AtaPortWritePortBufferUchar
product:
- Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortWritePortBufferUchar function


## -description


The <b>AtaPortWritePortBufferUchar</b> routine transfers the indicated number of unsigned bytes from a buffer to the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Port [in]

Pointer to the I/O port. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550160">AtaPortGetDeviceBase</a>.


### -param Buffer [in]

A pointer to the source buffer.


### -param Count [in]

Specifies the number of UCHAR values to write to the HBA.


## -returns



None 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550160">AtaPortGetDeviceBase</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550241">AtaPortWritePortBufferUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550249">AtaPortWritePortBufferUshort</a>
 

 

