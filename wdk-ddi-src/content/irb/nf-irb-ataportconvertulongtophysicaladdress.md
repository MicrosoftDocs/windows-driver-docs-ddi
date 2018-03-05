---
UID: NF:irb.AtaPortConvertUlongToPhysicalAddress
title: AtaPortConvertUlongToPhysicalAddress function
author: windows-driver-content
description: The AtaPortConvertUlongToPhysicalAddress routine converts a given ULONG address into a value of type IDE_PHYSICAL_ADDRESS.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportconvertulongtophysicaladdress.htm
old-project: storage
ms.assetid: f791f25d-d28e-45d3-b43c-9b87fda82d37
ms.author: windowsdriverdev
ms.date: 2/26/2018
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
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortConvertUlongToPhysicalAddress function


## -description


The <b>AtaPortConvertUlongToPhysicalAddress</b> routine converts a given ULONG address into a value of type IDE_PHYSICAL_ADDRESS.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
IDE_PHYSICAL_ADDRESS AtaPortConvertUlongToPhysicalAddress(
  _In_ ULONG_PTR UlongAddress
);
````


## -parameters




### -param UlongAddress [in]

Specifies a value of type ULONG.


## -returns



<b>AtaPortConvertUlongToPhysicalAddress</b> returns the converted IDE_PHYSICAL_ADDRESS value. 




## -see-also

<a href="..\irb\nf-irb-ataportconvertphysicaladdresstoulong.md">AtaPortConvertPhysicalAddressToUlong</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortConvertUlongToPhysicalAddress routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

