---
UID: NF:irb.AtaPortGetScatterGatherList
title: AtaPortGetScatterGatherList function
author: windows-driver-content
description: The AtaPortGetScatterGatherList routine retrieves the scatter/gather list that is associated with this request.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportgetscattergatherlist.htm
tech.root: storage
ms.assetid: 11181574-b329-4182-8d17-93d44cb3b839
ms.date: 3/29/2018
ms.keywords: AtaPortGetScatterGatherList, AtaPortGetScatterGatherList routine [Storage Devices], atartns_ef8ff0f5-2d1c-47e1-bf1a-2b554de3969d.xml, irb/AtaPortGetScatterGatherList, storage.ataportgetscattergatherlist
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
-	AtaPortGetScatterGatherList
product:
- Windows
targetos: Windows
req.typenames: 
---

# AtaPortGetScatterGatherList function


## -description


The <b>AtaPortGetScatterGatherList</b> routine retrieves the scatter/gather list that is associated with this request.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param ChannelExtension [in]

A pointer to the channel extension. 


### -param Irb [in]

A pointer to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff559140">IDE_REQUEST_BLOCK</a> that defines the IDE request block (IRB) for which a scatter/gather list is constructed.


## -returns



If the IRB_FLAGS_USE_DMA flag is set in the <b>IrbFlags</b> member of IRB, the <b>AtaPortGetScatterGatherList</b> routine returns a pointer to the scatter/gather list that is associated with the IRB. Otherwise, <b>AtaPortGetScatterGatherList</b> returns <b>NULL</b>.




## -remarks



Every IRB with IRB_FLAGS_USE_DMA set in the <b>IrbFlags</b> member has a scatter/gather list associated with it. 

The miniport driver must not modify the scatter/gather list.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559140">IDE_REQUEST_BLOCK</a>
 

 

