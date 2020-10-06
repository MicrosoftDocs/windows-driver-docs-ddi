---
UID: NC:irb.IDE_HW_STARTIO
title: IDE_HW_STARTIO (irb.h)
description: The IdeHwStartIo miniport driver routine processes the synchronized aspects of an I/O request.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\idehwstartio.htm
tech.root: storage
ms.assetid: 9172e62e-263c-471c-bcc2-9be4e1d6b1a2
ms.date: 03/29/2018
keywords: ["IDE_HW_STARTIO callback function"]
ms.keywords: IDE_HW_STARTIO, IdeHwStartIo, IdeHwStartIo routine [Storage Devices], atartns_5be92425-7e5b-4a9b-9673-baea4aace64a.xml, irb/IdeHwStartIo, storage.idehwstartio
req.header: irb.h
req.include-header: Irb.h
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IDE_HW_STARTIO
 - irb/IDE_HW_STARTIO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - irb.h
api_name:
 - IdeHwStartIo
---

# IDE_HW_STARTIO callback function


## -description

The <b><i>IdeHwStartIo</i></b> miniport driver routine processes the synchronized aspects of an I/O request.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param ChannelExtension 

[in]
A pointer to the miniport driver per channel device extension.

### -param Irb 

[in]
A pointer to a structure of type <a href="/windows-hardware/drivers/ddi/irb/ns-irb-_ide_request_block">IDE_REQUEST_BLOCK</a> that defines the IDE request block (IRB) to process.

## -returns

<b><i>IdeHwStartIo</i></b> returns <b>TRUE</b> to acknowledge the receipt of an IRB. The port driver ignores a return value of <b>FALSE</b>.

## -remarks

Miniport drivers must provide an <b><i>IdeHwStartIo</i></b> routine to process the aspects of an I/O request that must be handled synchronously. For information about how the miniport driver processes the unsynchronized aspects of an I/O request, see <a href="/windows-hardware/drivers/ddi/irb/nc-irb-ide_hw_buildio">IdeHwBuildIo</a>. 

After the miniport driver receives the <b><i>IdeHwStartIo</i></b> call, it owns the request and must complete it.

After this routine returns, the miniport driver should be prepared to receive the next request from the port driver immediately.

## -see-also

<a href="/windows-hardware/drivers/ddi/irb/ns-irb-_ide_request_block">IDE_REQUEST_BLOCK</a>



<a href="/windows-hardware/drivers/ddi/irb/nc-irb-ide_hw_buildio">IdeHwBuildIo</a>