---
UID: NF:irb.AtaPortRequestWorkerRoutine
title: AtaPortRequestWorkerRoutine function
author: windows-driver-content
description: The AtaPortRequestWorkerRoutine routine requests a worker routine.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportrequestworkerroutine.htm
old-project: storage
ms.assetid: 2d9a6886-aeec-4d61-8c9d-056d1409b905
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: AtaPortRequestWorkerRoutine, AtaPortRequestWorkerRoutine routine [Storage Devices], atartns_9edce4ce-1bcf-4e52-81c1-705e645fe5f4.xml, irb/AtaPortRequestWorkerRoutine, storage.ataportrequestworkerroutine
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	irb.h
api_name:
-	AtaPortRequestWorkerRoutine
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortRequestWorkerRoutine function


## -description


The <b>AtaPortRequestWorkerRoutine</b> routine requests a worker routine.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
BOOLEAN __inline AtaPortRequestWorkerRoutine(
  _In_ PVOID      ChannelExtension,
  _In_ IDE_HW_DPC WorkerRoutine
);
````


## -parameters




### -param ChannelExtension [in]

A pointer to the channel extension. 


### -param CallBackRoutine

TBD




#### - WorkerRoutine [in]

A pointer of type IDE_HW_DPC to the worker routine to call. 


## -returns



None 




## -remarks



The miniport driver can request a worker routine to perform tasks that cannot be done in the interrupt service routine. Transferring operations to a worker routine is an effective way to keep the interrupt service routine as small as possible.

The worker routine is not synchronized with the interrupt. 

When the port driver calls the worker routine, the port driver will pass the pointer to the channel extension that is stored in <i>ChannelExtension</i>.

The <i>WorkerRoutine</i> function pointer is declared in <i>Irb.h</i> as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
(*IDE_HW_DPC) (
  IN PVOID ChannelExtension
  );</pre>
</td>
</tr>
</table></span></div>


