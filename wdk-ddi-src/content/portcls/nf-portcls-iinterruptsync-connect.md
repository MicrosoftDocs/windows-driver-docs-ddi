---
UID: NF:portcls.IInterruptSync.Connect
title: IInterruptSync::Connect (portcls.h)
description: The Connect method connects the synchronization object to the interrupt.
old-location: audio\iinterruptsync_connect.htm
tech.root: audio
ms.assetid: 62cb451d-1170-4462-94ac-0477adc5946b
ms.date: 05/08/2018
ms.keywords: Connect, Connect method [Audio Devices], Connect method [Audio Devices],IInterruptSync interface, IInterruptSync interface [Audio Devices],Connect method, IInterruptSync.Connect, IInterruptSync::Connect, audio.iinterruptsync_connect, audmp-routines_10f66201-af8d-42ff-a854-04f5cb90f2cc.xml, portcls/IInterruptSync::Connect
f1_keywords:
 - "portcls/IInterruptSync.Connect"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- portcls.h
api_name:
- IInterruptSync.Connect
product:
- Windows
targetos: Windows
req.typenames: 
---

# IInterruptSync::Connect


## -description


The <code>Connect</code> method connects the synchronization object to the interrupt.


## -returns



<code>Connect</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks


This method connects the synchronization object to the interrupt that was specified in the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcnewinterruptsync">PcNewInterruptSync</a> that created the synchronization object. The interrupt is specified in the <b>PcNewInterruptSync</b> function's <i>ResourceList</i> and <i>ResourceIndex</i> parameters.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iinterruptsync">IInterruptSync</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioconnectinterrupt">IoConnectInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcnewinterruptsync">PcNewInterruptSync</a>
 

 

