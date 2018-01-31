---
UID: NF:portcls.IInterruptSync.Disconnect
title: IInterruptSync::Disconnect method
author: windows-driver-content
description: The Disconnect method disconnects the synchronization object from the interrupt.
old-location: audio\iinterruptsync_disconnect.htm
old-project: audio
ms.assetid: 799273eb-0ff6-4815-ac32-8fbb01f457e2
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IInterruptSync, audio.iinterruptsync_disconnect, Disconnect method [Audio Devices], IInterruptSync interface, portcls/IInterruptSync::Disconnect, Disconnect, audmp-routines_f25f0c99-96e2-4f1b-9930-e736a6394759.xml, Disconnect method [Audio Devices], IInterruptSync interface [Audio Devices], Disconnect method, IInterruptSync::Disconnect
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
req.lib: portcls.h
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	portcls.h
apiname:
-	IInterruptSync.Disconnect
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# IInterruptSync::Disconnect method


## -description


The <code>Disconnect</code> method disconnects the synchronization object from the interrupt.


## -syntax


````
void Disconnect(
    None
);
````


## -parameters





#### - None



## -returns


None



## -see-also

<a href="..\wdm\nf-wdm-iodisconnectinterrupt.md">IoDisconnectInterrupt</a>

<a href="..\portcls\nn-portcls-iinterruptsync.md">IInterruptSync</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IInterruptSync::Disconnect method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

