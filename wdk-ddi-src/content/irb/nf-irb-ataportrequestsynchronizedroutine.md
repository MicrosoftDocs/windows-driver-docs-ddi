---
UID: NF:irb.AtaPortRequestSynchronizedRoutine
title: AtaPortRequestSynchronizedRoutine function
author: windows-driver-content
description: The AtaPortRequestSynchronizedRoutine routine is used by the miniport driver to request synchronization with the interrupt service routine (ISR).Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportrequestsynchronizedroutine.htm
old-project: storage
ms.assetid: fc4faca4-4d44-4b3e-bace-718fc8774f54
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AtaPortRequestSynchronizedRoutine, AtaPortRequestSynchronizedRoutine routine [Storage Devices], atartns_612d4956-589d-4404-b3d3-f72eb6119e65.xml, irb/AtaPortRequestSynchronizedRoutine, storage.ataportrequestsynchronizedroutine
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
req.lib: 
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
-	AtaPortRequestSynchronizedRoutine
product:
- Windows
targetos: Windows
req.typenames: 
---

# AtaPortRequestSynchronizedRoutine function


## -description


The <b>AtaPortRequestSynchronizedRoutine</b> routine is used by the miniport driver to request synchronization with the interrupt service routine (ISR).
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param ChannelExtension [in]

A pointer to the channel extension.


### -param CallBackRoutine

TBD




#### - SynchronizedRoutine [in]

A pointer to the routine to call. 


## -returns



None 




## -remarks



This routine is typically used by miniport drivers that set the <b>SyncWithIsr</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559029">IDE_CHANNEL_CONFIGURATION</a> structure to <b>FALSE</b>. When <b>SyncWithIsr</b> is set to <b>FALSE</b>, the miniport driver should use the <b>AtaPortRequestSynchronizedRoutine </b>routine to ensure synchronized access to data structures that are modified in the ISR. 

The pointer to the channel extension that is stored in <i>ChannelExtension</i> will be passed to the worker routine when it is called.

When the port driver calls the routine that is pointed to by <i>SynchronizedRoutine</i>, it passes the pointer to the channel extension that is stored in <i>ChannelExtension</i>.

The <i>SynchronizedRoutine</i> function pointer is declared in <i>Irb.h</i> as follows:

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



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550148">AtaPortControllerSyncRoutine</a>
 

 

