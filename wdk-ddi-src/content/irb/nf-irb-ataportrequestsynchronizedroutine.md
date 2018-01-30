---
UID: NF:irb.AtaPortRequestSynchronizedRoutine
title: AtaPortRequestSynchronizedRoutine function
author: windows-driver-content
description: The AtaPortRequestSynchronizedRoutine routine is used by the miniport driver to request synchronization with the interrupt service routine (ISR).Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportrequestsynchronizedroutine.htm
old-project: storage
ms.assetid: fc4faca4-4d44-4b3e-bace-718fc8774f54
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: AtaPortRequestSynchronizedRoutine, storage.ataportrequestsynchronizedroutine, AtaPortRequestSynchronizedRoutine routine [Storage Devices], atartns_612d4956-589d-4404-b3d3-f72eb6119e65.xml, irb/AtaPortRequestSynchronizedRoutine
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	irb.h
apiname:
-	AtaPortRequestSynchronizedRoutine
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# AtaPortRequestSynchronizedRoutine function


## -description


The <b>AtaPortRequestSynchronizedRoutine</b> routine is used by the miniport driver to request synchronization with the interrupt service routine (ISR).
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
BOOLEAN __inline AtaPortRequestSynchronizedRoutine(
  _In_ PVOID      ChannelExtension,
  _In_ IDE_HW_DPC SynchronizedRoutine
);
````


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


This routine is typically used by miniport drivers that set the <b>SyncWithIsr</b> member of the <a href="..\irb\ns-irb-_ide_channel_configuration.md">IDE_CHANNEL_CONFIGURATION</a> structure to <b>FALSE</b>. When <b>SyncWithIsr</b> is set to <b>FALSE</b>, the miniport driver should use the <b>AtaPortRequestSynchronizedRoutine </b>routine to ensure synchronized access to data structures that are modified in the ISR. 

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

<a href="..\irb\nf-irb-ataportcontrollersyncroutine.md">AtaPortControllerSyncRoutine</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortRequestSynchronizedRoutine routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

