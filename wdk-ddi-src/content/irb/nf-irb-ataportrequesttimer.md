---
UID: NF:irb.AtaPortRequestTimer
title: AtaPortRequestTimer function
author: windows-driver-content
description: The AtaPortRequestTimer routine requests a timer callback.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportrequesttimer.htm
old-project: storage
ms.assetid: b057ae2e-53ae-4da9-8668-1ebca3c80998
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: AtaPortRequestTimer
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
req.alt-api: AtaPortRequestTimer
req.alt-loc: irb.h
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
req.typenames: IDE_POWER_STATE
---

# AtaPortRequestTimer function



## -description
The <b>AtaPortRequestTimer</b> routine requests a timer callback.



## -syntax

````
BOOLEAN __inline AtaPortRequestTimer(
  _In_ PVOID      ChannelExtension,
  _In_ IDE_HW_DPC TimerRoutine,
  _In_ ULONG      TimerValue
);
````


## -parameters

### -param ChannelExtension [in]

A pointer to the channel extension. 


### -param TimerRoutine [in]

A pointer to the timer routine. 


### -param TimerValue [in]

Time interval in units of microseconds.


## -returns
None 


## -remarks
The <b>AtaPortRequestTimer</b> routine informs the ATA port driver that it must call the timer routine that is pointed to by <i>TimerRoutine</i> in the number of microseconds indicated by <i>TimerValue</i>. 

The ATA port driver passes a pointer to the channel extension to the timer routine.


## -see-also
<dl>
<dt>
<a href="..\irb\nf-irb-ataportstallexecution.md">AtaPortStallExecution</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortRequestTimer routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

