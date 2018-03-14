---
UID: NF:portcls.IMiniportWaveCyclic.Init
title: IMiniportWaveCyclic::Init method
author: windows-driver-content
description: The Init method initializes the WaveCyclic miniport object. Initialization includes verification of the hardware using the resources specified in the resource list.
old-location: audio\iminiportwavecyclic_init.htm
old-project: audio
ms.assetid: 2f0147d0-9c1d-4f3e-890f-941568220605
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IMiniportWaveCyclic, IMiniportWaveCyclic::Init, IMiniportWavweCyclic interface [Audio Devices], Init method, IMiniportWavweCyclic::Init, Init method [Audio Devices], Init method [Audio Devices], IMiniportWavweCyclic interface, Init,IMiniportWaveCyclic.Init, audio.iminiportwavecyclic_init, audmp-routines_d18e9242-160d-4f55-9204-2e425b1f1669.xml, portcls/IMiniportWavweCyclic::Init
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
-	IMiniportWavweCyclic.Init
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportWaveCyclic::Init method


## -description


The <code>Init</code> method initializes the WaveCyclic miniport object. Initialization includes verification of the hardware using the resources specified in the resource list.


## -syntax


````
NTSTATUS Init(
  [in] PUNKNOWN        UnknownAdapter,
  [in] PRESOURCELIST   ResourceList,
  [in] PPORTWAVECYCLIC Port
);
````


## -parameters




### -param UnknownAdapter [in]

Pointer to the <b>IUnknown</b> interface of the adapter object whose miniport object is being initialized. For more information, see the following Remarks section.


### -param ResourceList [in]

Pointer to <a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a> interface of the resource list object that is to be supplied to the miniport driver during initialization. After passing this reference to the miniport driver, the port driver is free to examine the contents of the resource list but will not modify the contents of this list. For more information, see the following Remarks section.


### -param Port [in]

Pointer to the <a href="..\portcls\nn-portcls-iportwavecyclic.md">IPortWaveCyclic</a> object that is bound to this miniport driver. The caller specifies a valid, non-NULL pointer for this parameter.


## -returns



<code>Init</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



The <i>UnknownAdapter</i> and <i>ResourceList</i> parameters are the same pointer values that the adapter driver earlier passed as parameters to the <b>IPortWaveCyclic</b> object's <code>Init</code> method (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff536943">IPort::Init</a>).

The <i>UnknownAdapter</i>, <i>ResourceList</i>, and <i>Port</i> parameters follow the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536943">IPort::Init</a>



<a href="..\portcls\nn-portcls-iportwavecyclic.md">IPortWaveCyclic</a>



<a href="..\portcls\nn-portcls-iminiportwavecyclic.md">IMiniportWavweCyclic</a>



<a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a>



 

 


