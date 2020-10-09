---
UID: NF:portcls.IMiniportWaveRT.Init
title: IMiniportWaveRT::Init (portcls.h)
description: The Init method initializes the WaveRT miniport driver object.
old-location: audio\iminiportwavert_init.htm
tech.root: audio
ms.assetid: f25be064-6ad4-42e8-87a5-188978d093fb
ms.date: 05/08/2018
keywords: ["IMiniportWaveRT::Init"]
ms.keywords: IMiniportWaveRT interface [Audio Devices],Init method, IMiniportWaveRT.Init, IMiniportWaveRT::Init, Init, Init method [Audio Devices], Init method [Audio Devices],IMiniportWaveRT interface, audio.iminiportwavert_init, audmp-routines_3304baaf-f3bf-43f1-908b-5cf47b084ee1.xml, portcls/IMiniportWaveRT::Init
req.header: portcls.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later Windows operating systems.
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
req.irql: Passive level.
targetos: Windows
req.typenames: 
f1_keywords:
 - IMiniportWaveRT::Init
 - portcls/IMiniportWaveRT::Init
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IMiniportWaveRT.Init
---

# IMiniportWaveRT::Init


## -description

The <code>Init</code> method initializes the <a href="/windows-hardware/drivers/audio/wavert-miniport-driver">WaveRT miniport driver</a> object.

## -parameters

### -param UnknownAdapter 

[in]
Pointer to the <b>IUnknown</b> interface of the adapter driver object whose miniport driver object is being initialized.

### -param ResourceList 

[in]
Pointer to the <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iresourcelist">IResourceList</a> interface of a resource-list object. This object specifies the list of hardware resources that the adapter driver has allocated to the miniport driver. The WaveRT port driver can examine the contents of the resource list, but it does not modify the list.

### -param Port 

[in]
Pointer to the <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iportwavert">IPortWaveRT</a> interface of the WaveRT port driver. The caller specifies a valid, non-NULL pointer value for this parameter.

## -returns

<code>Init</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error status code.

## -remarks

For more information about the <i>ResourceList</i> parameter, see the <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iport-init">IPort::Init </a> topic. The <i>ResourceList</i> and <i>Port</i> parameters follow the reference-counting conventions for COM objects.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportwavert">IMiniportWaveRT</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iportwavert">IPortWaveRT</a>