---
UID: NF:irb.AtaPortConvertPhysicalAddressToUlong
title: AtaPortConvertPhysicalAddressToUlong function
author: windows-driver-content
description: The AtaPortConvertPhysicalAddressToUlong routine truncates an address of type IDE_PHYSICAL_ADDRESS to a ULONG.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportconvertphysicaladdresstoulong.htm
old-project: storage
ms.assetid: cd63cb65-701e-46e2-ba32-971f91f9eb29
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AtaPortConvertPhysicalAddressToUlong, AtaPortConvertPhysicalAddressToUlong routine [Storage Devices], atartns_b9df7c2c-3309-4d5a-88d9-bc1eee37fae0.xml, irb/AtaPortConvertPhysicalAddressToUlong, storage.ataportconvertphysicaladdresstoulong
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
-	AtaPortConvertPhysicalAddressToUlong
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortConvertPhysicalAddressToUlong function


## -description


The <b>AtaPortConvertPhysicalAddressToUlong</b> routine truncates an address of type IDE_PHYSICAL_ADDRESS to a ULONG.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param Address [in]

Specifies a value of type IDE_PHYSICAL_ADDRESS.


## -returns



<b>AtaPortConvertPhysicalAddressToUlong</b> returns the lower order part of the given IDE_PHYSICAL_ADDRESS value. 




## -remarks



A miniport driver must not use this routine to truncate a 64-bit physical address. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550151">AtaPortConvertUlongToPhysicalAddress</a>
 

 

