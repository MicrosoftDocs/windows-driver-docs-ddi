---
UID: NF:irb.AtaPortCompleteAllActiveRequests
title: AtaPortCompleteAllActiveRequests function (irb.h)
description: The AtaPortCompleteAllActiveRequests routine completes all active IRBs for the indicated device.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportcompleteallactiverequests.htm
tech.root: storage
ms.assetid: e17b1a76-ab1e-4263-9e4a-42c6f2066de1
ms.date: 03/29/2018
keywords: ["AtaPortCompleteAllActiveRequests function"]
ms.keywords: AtaPortCompleteAllActiveRequests, AtaPortCompleteAllActiveRequests routine [Storage Devices], atartns_b9f2bdc5-ede8-4a7f-9d9e-df16a9d83634.xml, irb/AtaPortCompleteAllActiveRequests, storage.ataportcompleteallactiverequests
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
targetos: Windows
req.typenames: 
f1_keywords:
 - AtaPortCompleteAllActiveRequests
 - irb/AtaPortCompleteAllActiveRequests
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
 - AtaPortCompleteAllActiveRequests
---

# AtaPortCompleteAllActiveRequests function


## -description

The <b>AtaPortCompleteAllActiveRequests</b> routine completes all active IRBs for the indicated device.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param ChannelExtension 

[in]
A pointer to the channel extension.

### -param Target 

[in]
Specifies the target identifier of the device.

### -param Lun 

[in]
Specifies the logical unit number of the device.

### -param IrbStatus 

[in]
Specifies the status with which the requests will be completed.

## -remarks

The <b>AtaPortCompleteAllActiveRequests</b> routine completes all active IRBs on the device as indicated by the <i>Target </i>and <i>Lun</i> parameters. Miniport drivers use this routine to complete all active IRPs if there is a reset. Miniport drivers can complete IRBs on all devices concurrently by assigning a value of IDE_UNTAGGED to the <i>Target </i>and <i>Lun </i>parameters, instead of specifying a specific device.

The miniport driver must not call this routine from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nc-irb-ide_hw_interrupt">IdeHwInterrupt</a> routine.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/nc-irb-ide_hw_interrupt">IdeHwInterrupt</a>

