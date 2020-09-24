---
UID: NF:irb.AtaPortControllerSyncRoutine
title: AtaPortControllerSyncRoutine function (irb.h)
description: The AtaPortControllerSyncRoutine routine provides synchronized access to data structures that are shared across all channels on a controller.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportcontrollersyncroutine.htm
tech.root: storage
ms.assetid: 6b39e89e-21cc-404f-b9fc-6cad0b5c8d22
ms.date: 03/29/2018
keywords: ["AtaPortControllerSyncRoutine function"]
ms.keywords: AtaPortControllerSyncRoutine, AtaPortControllerSyncRoutine routine [Storage Devices], atartns_1fdbc2cb-49db-4121-aaaa-8a50c2a6cbde.xml, irb/AtaPortControllerSyncRoutine, storage.ataportcontrollersyncroutine
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - AtaPortControllerSyncRoutine
 - irb/AtaPortControllerSyncRoutine
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - irb.h
api_name:
 - AtaPortControllerSyncRoutine
---

# AtaPortControllerSyncRoutine function


## -description

The <b>AtaPortControllerSyncRoutine</b> routine provides synchronized access to data structures that are shared across all channels on a controller.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters

### -param ChannelExtension 

[in]
A pointer to the channel extension.

### -param CallBackRoutine

<p>A pointer to the routine to call. </p>

## -returns

None

## -remarks

The miniport driver uses this routine to synchronize access to data structures that are shared across channels on a controller. The miniport driver, however, should use this routine very sparingly.

The <i>ControllerSyncRoutine</i> function pointer is declared in <i>Irb.h</i> as follows:


```
typedef
VOID
(*IDE_HW_DPC) (
  IN PVOID ChannelExtension
  );
```


## -see-also

<a href="/windows-hardware/drivers/ddi/irb/nf-irb-ataportrequestsynchronizedroutine">AtaPortRequestSynchronizedRoutine</a>