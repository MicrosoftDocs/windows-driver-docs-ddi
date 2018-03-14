---
UID: NF:portcls.IMiniportWaveRT.Init
title: IMiniportWaveRT::Init method
author: windows-driver-content
description: The Init method initializes the WaveRT miniport driver object.
old-location: audio\iminiportwavert_init.htm
old-project: audio
ms.assetid: f25be064-6ad4-42e8-87a5-188978d093fb
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IMiniportWaveRT, IMiniportWaveRT interface [Audio Devices], Init method, IMiniportWaveRT::Init, Init method [Audio Devices], Init method [Audio Devices], IMiniportWaveRT interface, Init,IMiniportWaveRT.Init, audio.iminiportwavert_init, audmp-routines_3304baaf-f3bf-43f1-908b-5cf47b084ee1.xml, portcls/IMiniportWaveRT::Init
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IMiniportWaveRT.Init
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportWaveRT::Init method


## -description


The <code>Init</code> method initializes the <a href="https://msdn.microsoft.com/154dc921-424f-4021-8f17-5482ceef99a8">WaveRT miniport driver</a> object.


## -syntax


````
NTSTATUS Init(
  [in] PUNKNOWN      UnknownAdapter,
  [in] PRESOURCELIST ResourceList,
  [in] PPORTWAVERT   Port
);
````


## -parameters




### -param UnknownAdapter [in]

Pointer to the <b>IUnknown</b> interface of the adapter driver object whose miniport driver object is being initialized.


### -param ResourceList [in]

Pointer to the <a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a> interface of a resource-list object. This object specifies the list of hardware resources that the adapter driver has allocated to the miniport driver. The WaveRT port driver can examine the contents of the resource list, but it does not modify the list.


### -param Port [in]

Pointer to the <a href="..\portcls\nn-portcls-iportwavert.md">IPortWaveRT</a> interface of the WaveRT port driver. The caller specifies a valid, non-NULL pointer value for this parameter.


## -returns



<code>Init</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error status code.




## -remarks



For more information about the <i>ResourceList</i> parameter, see the <a href="https://msdn.microsoft.com/1735a8e8-56d0-4981-aca7-7bb4c2f22c00">IPort::Init </a> topic. The <i>ResourceList</i> and <i>Port</i> parameters follow the reference-counting conventions for COM objects.




## -see-also

<a href="..\portcls\nn-portcls-iminiportwavert.md">IMiniportWaveRT</a>



<a href="..\portcls\nn-portcls-iportwavert.md">IPortWaveRT</a>



 

 


