---
UID: NF:portcls.IPortMidi.RegisterServiceGroup
title: IPortMidi::RegisterServiceGroup method
author: windows-driver-content
description: The RegisterServiceGroup method registers the service group to be used for the IPortMidi::Notify method.
old-location: audio\iportmidi_registerservicegroup.htm
old-project: audio
ms.assetid: 8e6b967f-7114-4231-bcfc-23637cd83268
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IPortMidi, IPortMidi interface [Audio Devices], RegisterServiceGroup method, IPortMidi::RegisterServiceGroup, RegisterServiceGroup method [Audio Devices], RegisterServiceGroup method [Audio Devices], IPortMidi interface, RegisterServiceGroup,IPortMidi.RegisterServiceGroup, audio.iportmidi_registerservicegroup, audmp-routines_ff2228bf-489d-4980-a317-e9cb89e4f394.xml, portcls/IPortMidi::RegisterServiceGroup
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
-	IPortMidi.RegisterServiceGroup
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortMidi::RegisterServiceGroup method


## -description


The <code>RegisterServiceGroup</code> method registers the service group to be used for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536893">IPortMidi::Notify</a> method.


## -syntax


````
void RegisterServiceGroup(
  [in] PSERVICEGROUP ServiceGroup
);
````


## -parameters




### -param ServiceGroup [in]

Pointer to the miniport driver's <a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a> object that is being registered.


## -returns



<code>RegisterServiceGroup</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



The <i>ServiceGroup</i> parameter follows the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536893">IPortMidi::Notify</a>



<a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a>



<a href="..\portcls\nn-portcls-iportmidi.md">IPortMidi</a>



 

 


