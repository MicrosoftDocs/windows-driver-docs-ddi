---
UID: NF:irb.AtaPortReadPortUlong
title: AtaPortReadPortUlong function
author: windows-driver-content
description: The AtaPortReadPortUlong routine reads a ULONG value from the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportreadportulong.htm
tech.root: storage
ms.assetid: f9e5fb0a-7add-462c-9b2a-2b543f7c7649
ms.date: 03/29/2018
ms.keywords: AtaPortReadPortUlong, AtaPortReadPortUlong routine [Storage Devices], atartns_e2d91111-cf48-4987-82ff-055469d67dc8.xml, irb/AtaPortReadPortUlong, storage.ataportreadportulong
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
-	AtaPortReadPortUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# AtaPortReadPortUlong function


## -description


The <b>AtaPortReadPortUlong</b> routine reads a ULONG value from the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Port [in]

A pointer to the I/O port. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550160">AtaPortGetDeviceBase</a>.


## -returns



<b>AtaPortReadPortUlong</b> returns a ULONG value from the HBA's I/O port. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550160">AtaPortGetDeviceBase</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550182">AtaPortReadPortUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550185">AtaPortReadPortUshort</a>
 

 

