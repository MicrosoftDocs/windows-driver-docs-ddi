---
UID: NF:portcls.IMiniportWavePci.Init
title: IMiniportWavePci::Init
description: The Init method initializes the WavePci miniport object. Initialization includes verification of the hardware using the resources specified in the resource list.
old-location: audio\iminiportwavepci_init.htm
tech.root: audio
ms.assetid: 0796a1a2-1aaa-4e07-a8f1-7a3c895643e7
ms.date: 05/08/2018
ms.keywords: IMiniportWavePci interface [Audio Devices],Init method, IMiniportWavePci.Init, IMiniportWavePci::Init, Init, Init method [Audio Devices], Init method [Audio Devices],IMiniportWavePci interface, audio.iminiportwavepci_init, audmp-routines_fd2d7813-ebe8-4cf3-8a6c-4ebfccca5826.xml, portcls/IMiniportWavePci::Init
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
-	IMiniportWavePci.Init
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportWavePci::Init


## -description


The <code>Init</code> method initializes the WavePci miniport object. Initialization includes verification of the hardware using the resources specified in the resource list.


## -parameters




### -param UnknownAdapter [in]

Pointer to the <b>IUnknown</b> interface of the adapter object whose miniport object is being initialized. For more information, see the following Remarks section.


### -param ResourceList [in]

Pointer to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536976">IResourceList</a> interface of resource list object that is to be supplied to the miniport driver during initialization. After passing this reference to the miniport driver, the port driver is free to examine the contents of the resource list but will not modify the contents of this list. For more information, see the following Remarks section.


### -param Port [in]

Pointer to the port driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536905">IPortWavePci</a> interface object. The caller specifies a valid, non-NULL pointer value for this parameter.


### -param ServiceGroup [out]

Output pointer for the service group. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536994">IServiceGroup</a> interface of the miniport driver's service group object. This is the service group that is being registered for interrupt notification. The caller specifies a valid, non-NULL pointer value for this parameter.


## -returns



<code>Init</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



The <i>UnknownAdapter</i> and <i>ResourceList</i> parameters are the same pointer values that the adapter driver earlier passed as parameters to the <b>IPortWavePci</b> object's <b>Init</b> method (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff536943">IPort::Init</a>).

The <i>UnknownAdapter</i>, <i>ResourceList</i>, <i>Port</i>, and <i>ServiceGroup</i> parameters follow the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536724">IMiniportWavePci</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536943">IPort::Init</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536905">IPortWavePci</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536976">IResourceList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536994">IServiceGroup</a>
 

 

