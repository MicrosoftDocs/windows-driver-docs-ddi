---
UID: NF:portcls.IInterruptSync.Connect
title: IInterruptSync::Connect method
author: windows-driver-content
description: The Connect method connects the synchronization object to the interrupt.
old-location: audio\iinterruptsync_connect.htm
old-project: audio
ms.assetid: 62cb451d-1170-4462-94ac-0477adc5946b
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: Connect method [Audio Devices], Connect method [Audio Devices], IInterruptSync interface, Connect,IInterruptSync.Connect, IInterruptSync, IInterruptSync interface [Audio Devices], Connect method, IInterruptSync::Connect, audio.iinterruptsync_connect, audmp-routines_10f66201-af8d-42ff-a854-04f5cb90f2cc.xml, portcls/IInterruptSync::Connect
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IInterruptSync.Connect
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IInterruptSync::Connect method


## -description


The <code>Connect</code> method connects the synchronization object to the interrupt.


## -parameters






#### - None


## -returns



<code>Connect</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



This method connects the synchronization object to the interrupt that was specified in the call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff537713">PcNewInterruptSync</a> that created the synchronization object. The interrupt is specified in the <b>PcNewInterruptSync</b> function's <i>ResourceList</i> and <i>ResourceIndex</i> parameters.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536590">IInterruptSync</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548371">IoConnectInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537713">PcNewInterruptSync</a>
 

 

