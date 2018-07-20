---
UID: NF:irb.AtaPortConvertUlongToPhysicalAddress
title: AtaPortConvertUlongToPhysicalAddress function
author: windows-driver-content
description: The AtaPortConvertUlongToPhysicalAddress routine converts a given ULONG address into a value of type IDE_PHYSICAL_ADDRESS.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportconvertulongtophysicaladdress.htm
tech.root: storage
ms.assetid: f791f25d-d28e-45d3-b43c-9b87fda82d37
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AtaPortConvertUlongToPhysicalAddress, AtaPortConvertUlongToPhysicalAddress routine [Storage Devices], atartns_29b4ce0d-5dda-4203-a10b-66ccd7859d5d.xml, irb/AtaPortConvertUlongToPhysicalAddress, storage.ataportconvertulongtophysicaladdress
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
-	AtaPortConvertUlongToPhysicalAddress
product:
- Windows
targetos: Windows
req.typenames: 
---

# AtaPortConvertUlongToPhysicalAddress function


## -description


The <b>AtaPortConvertUlongToPhysicalAddress</b> routine converts a given ULONG address into a value of type IDE_PHYSICAL_ADDRESS.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param UlongAddress [in]

Specifies a value of type ULONG.


## -returns



<b>AtaPortConvertUlongToPhysicalAddress</b> returns the converted IDE_PHYSICAL_ADDRESS value. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550149">AtaPortConvertPhysicalAddressToUlong</a>
 

 

