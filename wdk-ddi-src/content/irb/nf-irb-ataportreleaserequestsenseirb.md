---
UID: NF:irb.AtaPortReleaseRequestSenseIrb
title: AtaPortReleaseRequestSenseIrb function (irb.h)
description: The AtaPortReleaseRequestSenseIrb routine frees the request sense IRB tha is allocated by using AtaPortBuildRequestSenseIrb.
old-location: storage\ataportreleaserequestsenseirb.htm
tech.root: storage
ms.assetid: 53e5e234-c256-4581-b109-307f2f17522f
ms.date: 03/29/2018
ms.keywords: AtaPortReleaseRequestSenseIrb, AtaPortReleaseRequestSenseIrb routine [Storage Devices], atartns_b46ae59d-b5b8-49fb-9458-742eefacd197.xml, irb/AtaPortReleaseRequestSenseIrb, storage.ataportreleaserequestsenseirb
ms.topic: function
f1_keywords:
 - "irb/AtaPortReleaseRequestSenseIrb"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ataport.lib
- ataport.dll
- pciidex.lib
- pciidex.dll
api_name:
- AtaPortReleaseRequestSenseIrb
product:
- Windows
targetos: Windows
req.typenames: 
---

# AtaPortReleaseRequestSenseIrb function


## -description


The <b>AtaPortReleaseRequestSenseIrb</b> routine frees the request sense IRB tha is allocated by using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportbuildrequestsenseirb">AtaPortBuildRequestSenseIrb</a>. 
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param ChannelExtension [in]

A pointer to the channel extension. 


### -param Irb [in]

A pointer to a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/ns-irb-_ide_request_block">IDE_REQUEST_BLOCK</a> that defines the request sense IRB.


## -returns



None




## -remarks



The <b>AtaPortReleaseRequestSenseIrb</b> routine releases the IRB to the port driver and copies the sense data to the buffer that is pointed to by the <b>SenseInfoBuffer</b> member of the original (failed) request's IRB. The miniport driver can then complete the original request by using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportcompleterequest">AtaPortCompleteRequest</a>. The miniport driver must not touch the request sense IRB after it has been released to the port driver.

The miniport driver must call <b>AtaPortReleaseRequestSenseIrb</b> for every allocated IRB that is allocated by using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportbuildrequestsenseirb">AtaPortBuildRequestSenseIrb</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportbuildrequestsenseirb">AtaPortBuildRequestSenseIrb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nf-irb-ataportcompleterequest">AtaPortCompleteRequest</a>
 

 

