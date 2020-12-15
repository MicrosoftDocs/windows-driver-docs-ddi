---
UID: NF:portcls.IMiniportWavePci.Init
title: IMiniportWavePci::Init (portcls.h)
description: The Init method initializes the WavePci miniport object. Initialization includes verification of the hardware using the resources specified in the resource list.
old-location: audio\iminiportwavepci_init.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IMiniportWavePci::Init"]
ms.keywords: IMiniportWavePci interface [Audio Devices],Init method, IMiniportWavePci.Init, IMiniportWavePci::Init, Init, Init method [Audio Devices], Init method [Audio Devices],IMiniportWavePci interface, audio.iminiportwavepci_init, audmp-routines_fd2d7813-ebe8-4cf3-8a6c-4ebfccca5826.xml, portcls/IMiniportWavePci::Init
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
 - IMiniportWavePci::Init
 - portcls/IMiniportWavePci::Init
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IMiniportWavePci.Init
---

# IMiniportWavePci::Init


## -description

The <code>Init</code> method initializes the WavePci miniport object. Initialization includes verification of the hardware using the resources specified in the resource list.

## -parameters

### -param UnknownAdapter 

[in]
Pointer to the <b>IUnknown</b> interface of the adapter object whose miniport object is being initialized. For more information, see the following Remarks section.

### -param ResourceList 

[in]
Pointer to <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iresourcelist">IResourceList</a> interface of resource list object that is to be supplied to the miniport driver during initialization. After passing this reference to the miniport driver, the port driver is free to examine the contents of the resource list but will not modify the contents of this list. For more information, see the following Remarks section.

### -param Port 

[in]
Pointer to the port driver's <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iportwavepci">IPortWavePci</a> interface object. The caller specifies a valid, non-NULL pointer value for this parameter.

### -param ServiceGroup 

[out]
Output pointer for the service group. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicegroup">IServiceGroup</a> interface of the miniport driver's service group object. This is the service group that is being registered for interrupt notification. The caller specifies a valid, non-NULL pointer value for this parameter.

## -returns

<code>Init</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## -remarks

The <i>UnknownAdapter</i> and <i>ResourceList</i> parameters are the same pointer values that the adapter driver earlier passed as parameters to the <b>IPortWavePci</b> object's <b>Init</b> method (see <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iport-init">IPort::Init</a>).

The <i>UnknownAdapter</i>, <i>ResourceList</i>, <i>Port</i>, and <i>ServiceGroup</i> parameters follow the <a href="/windows-hardware/drivers/audio/reference-counting-conventions-for-com-objects">reference-counting conventions for COM objects</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportwavepci">IMiniportWavePci</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iport-init">IPort::Init</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iportwavepci">IPortWavePci</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iresourcelist">IResourceList</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicegroup">IServiceGroup</a>
