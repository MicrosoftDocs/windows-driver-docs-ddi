---
UID: NF:portcls.IPortMidi.RegisterServiceGroup
title: IPortMidi::RegisterServiceGroup method
author: windows-driver-content
description: The RegisterServiceGroup method registers the service group to be used for the IPortMidi::Notify method.
old-location: audio\iportmidi_registerservicegroup.htm
old-project: audio
ms.assetid: 8e6b967f-7114-4231-bcfc-23637cd83268
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPortMidi, RegisterServiceGroup method [Audio Devices], portcls/IPortMidi::RegisterServiceGroup, audio.iportmidi_registerservicegroup, audmp-routines_ff2228bf-489d-4980-a317-e9cb89e4f394.xml, RegisterServiceGroup, IPortMidi::RegisterServiceGroup, IPortMidi interface [Audio Devices], RegisterServiceGroup method, RegisterServiceGroup method [Audio Devices], IPortMidi interface
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
-	IPortMidi.RegisterServiceGroup
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
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




#### - ServiceGroup [in]

Pointer to the miniport driver's <a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a> object that is being registered.


## -returns


<code>RegisterServiceGroup</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.



## -remarks


The <i>ServiceGroup</i> parameter follows the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536893">IPortMidi::Notify</a>

<a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a>

<a href="..\portcls\nn-portcls-iportmidi.md">IPortMidi</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortMidi::RegisterServiceGroup method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

