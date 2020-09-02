---
UID: NF:portcls.IPortMidi.RegisterServiceGroup
title: IPortMidi::RegisterServiceGroup (portcls.h)
description: The RegisterServiceGroup method registers the service group to be used for the IPortMidi::Notify method.
old-location: audio\iportmidi_registerservicegroup.htm
tech.root: audio
ms.assetid: 8e6b967f-7114-4231-bcfc-23637cd83268
ms.date: 05/08/2018
keywords: ["IPortMidi::RegisterServiceGroup"]
ms.keywords: IPortMidi interface [Audio Devices],RegisterServiceGroup method, IPortMidi.RegisterServiceGroup, IPortMidi::RegisterServiceGroup, RegisterServiceGroup, RegisterServiceGroup method [Audio Devices], RegisterServiceGroup method [Audio Devices],IPortMidi interface, audio.iportmidi_registerservicegroup, audmp-routines_ff2228bf-489d-4980-a317-e9cb89e4f394.xml, portcls/IPortMidi::RegisterServiceGroup
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPortMidi::RegisterServiceGroup
 - portcls/IPortMidi::RegisterServiceGroup
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IPortMidi.RegisterServiceGroup
---

# IPortMidi::RegisterServiceGroup


## -description

The <code>RegisterServiceGroup</code> method registers the service group to be used for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportmidi-notify">IPortMidi::Notify</a> method.

## -parameters

### -param ServiceGroup 

[in]
Pointer to the miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicegroup">IServiceGroup</a> object that is being registered.

## -returns

<code>RegisterServiceGroup</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## -remarks

The <i>ServiceGroup</i> parameter follows the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/reference-counting-conventions-for-com-objects">reference-counting conventions for COM objects</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iportmidi">IPortMidi</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportmidi-notify">IPortMidi::Notify</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicegroup">IServiceGroup</a>

