---
UID: NC:storport.HW_DPC_ROUTINE
title: HW_DPC_ROUTINE
author: windows-driver-content
description: The HwStorDpcRoutine routine is a routine that is deferred for execution at DISPATCH IRQL by means of the deferred procedure call (DPC) mechanism.
old-location: storage\hwstordpcroutine.htm
old-project: storage
ms.assetid: bc646191-e405-49e2-8793-0c0b81e52f50
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.hwstordpcroutine, HwStorDpcRoutine routine [Storage Devices], HwStorDpcRoutine, HW_DPC_ROUTINE, HW_DPC_ROUTINE, storport/HwStorDpcRoutine, stormini_593e93b3-e078-48a4-b192-75cc161686bb.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.irql: DISPATCH_LEVEL (See Remarks section.)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Storport.h
apiname:
-	HwStorDpcRoutine
product: Windows
targetos: Windows
req.typenames: "*PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER"
req.product: Windows 10 or later.
---

# HW_DPC_ROUTINE callback


## -description


The <b>HwStorDpcRoutine</b> routine is a routine that is deferred for execution at DISPATCH IRQL by means of the deferred procedure call (DPC) mechanism. 


## -prototype


````
HW_DPC_ROUTINE HwStorDpcRoutine;

VOID HwStorDpcRoutine(
   IN PSTOR_DPC Dpc,
   IN PVOID     HwDeviceExtension,
   IN PVOID     SystemArgument1,
   IN PVOID     SystemArgument2
)
{ ... }
````


## -parameters




### -param Dpc

A pointer to a Storport DPC  context. 


### -param HwDeviceExtension

A pointer to the per-adapter device extension. 


### -param SystemArgument1

A pointer to caller-supplied information.


### -param SystemArgument2

A pointer to caller-supplied information.


## -returns


None. 



## -remarks


When a miniport driver calls <a href="..\storport\nf-storport-storportinitializedpc.md">StorPortInitializeDpc</a> to initialize a DPC it must load the <i>HwDpcRoutine</i>  parameter of the <b>StorPortInitializeDpc</b> routine with a pointer to the <b>HwStorDpcRoutine</b> routine. 

Any particular instance of a DPC routine is guaranteed to be synchronized with other instances of the DPC routine. A DPC routine can synchronize itself with the <a href="..\storport\nc-storport-hw_startio.md">HwStorStartIo</a> routine or with the <a href="..\storport\nc-storport-hw_interrupt.md">HwStorInterrupt</a> routine by acquiring the appropriate spin lock with a call to <a href="..\storport\nf-storport-storportacquirespinlock.md">StorPortAcquireSpinLock</a>. For more information about the management of spin locks within DPC routines, see <a href="..\storport\nf-storport-storportissuedpc.md">StorPortIssueDpc</a>. 

The name <b>HwStorDpcRoutine</b> is just a placeholder. The actual prototype of this routine is defined in <i>storport.h</i> as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
BOOLEAN
HW_DPC_ROUTINE (
  _In_  PSTOR_DPC Dpc,
  _In_  PVOID HwDeviceExtension,
  _In_opt_  PVOID SystemArgument1,
  _In_opt_  PVOID SystemArgument2
  );</pre>
</td>
</tr>
</table></span></div>The port driver calls the <b>HwStorDpcRoutine</b> routine at DISPATCH IRQL.



## -see-also

<a href="..\storport\nf-storport-storportacquirespinlock.md">StorPortAcquireSpinLock</a>

<a href="..\storport\nc-storport-hw_interrupt.md">HwStorInterrupt</a>

<a href="..\storport\nf-storport-storportissuedpc.md">StorPortIssueDpc</a>

<a href="..\storport\nf-storport-storportinitializedpc.md">StorPortInitializeDpc</a>

<a href="..\storport\nc-storport-hw_startio.md">HwStorStartIo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HW_DPC_ROUTINE routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

