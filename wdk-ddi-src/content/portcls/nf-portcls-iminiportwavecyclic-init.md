---
UID: NF:portcls.IMiniportWaveCyclic.Init
title: IMiniportWaveCyclic::Init method
author: windows-driver-content
description: The Init method initializes the WaveCyclic miniport object. Initialization includes verification of the hardware using the resources specified in the resource list.
old-location: audio\iminiportwavecyclic_init.htm
old-project: audio
ms.assetid: 2f0147d0-9c1d-4f3e-890f-941568220605
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: portcls/IMiniportWavweCyclic::Init, Init method [Audio Devices], Init, IMiniportWavweCyclic::Init, audio.iminiportwavecyclic_init, IMiniportWavweCyclic interface [Audio Devices], Init method, Init method [Audio Devices], IMiniportWavweCyclic interface, audmp-routines_d18e9242-160d-4f55-9204-2e425b1f1669.xml, IMiniportWaveCyclic, IMiniportWaveCyclic::Init
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

<a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a>

<a href="..\portcls\nn-portcls-iminiportwavecyclic.md">IMiniportWavweCyclic</a>

<a href="..\portcls\nn-portcls-iportwavecyclic.md">IPortWaveCyclic</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536943">IPort::Init</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportWavweCyclic::Init method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

