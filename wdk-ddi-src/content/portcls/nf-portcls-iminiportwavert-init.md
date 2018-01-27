---
UID: NF:portcls.IMiniportWaveRT.Init
title: IMiniportWaveRT::Init method
author: windows-driver-content
description: The Init method initializes the WaveRT miniport driver object.
old-location: audio\iminiportwavert_init.htm
old-project: audio
ms.assetid: f25be064-6ad4-42e8-87a5-188978d093fb
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.iminiportwavert_init, IMiniportWaveRT::Init, Init method [Audio Devices], IMiniportWaveRT interface, audmp-routines_3304baaf-f3bf-43f1-908b-5cf47b084ee1.xml, IMiniportWaveRT, portcls/IMiniportWaveRT::Init, Init method [Audio Devices], IMiniportWaveRT interface [Audio Devices], Init method, Init
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
req.lib: portcls.h
req.dll: 
req.irql: Passive level.
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	COM
apilocation: 
-	portcls.h
apiname: 
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

<a href="..\portcls\nn-portcls-iportwavert.md">IPortWaveRT</a>

<a href="..\portcls\nn-portcls-iminiportwavert.md">IMiniportWaveRT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportWaveRT::Init method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

