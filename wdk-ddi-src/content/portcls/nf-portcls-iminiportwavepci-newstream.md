---
UID: NF:portcls.IMiniportWavePci.NewStream
title: IMiniportWavePci::NewStream method
author: windows-driver-content
description: The NewStream method creates a new instance of a logical stream associated with a specified physical channel.
old-location: audio\iminiportwavepci_newstream.htm
old-project: audio
ms.assetid: cad3eeb5-2106-4648-97e5-cf3bb8601599
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IMiniportWavePci, IMiniportWavePci interface [Audio Devices], NewStream method, IMiniportWavePci::NewStream, NewStream method [Audio Devices], NewStream method [Audio Devices], IMiniportWavePci interface, NewStream,IMiniportWavePci.NewStream, audio.iminiportwavepci_newstream, audmp-routines_cf0b0f93-033d-47f1-8e07-c0407e0a89f3.xml, portcls/IMiniportWavePci::NewStream
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IMiniportWavePci.NewStream
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportWavePci::NewStream method


## -description


The <code>NewStream</code> method creates a new instance of a logical stream associated with a specified physical channel.


## -syntax


````
NTSTATUS NewStream(
  [out]          PMINIPORTWAVEPCISTREAM *Stream,
  [in, optional] PUNKNOWN               OuterUnknown,
  [in]           POOL_TYPE              PoolType,
  [in]           PPORTWAVEPCISTREAM     PortStream,
  [in]           ULONG                  Pin,
  [in]           BOOLEAN                Capture,
  [in]           PKSDATAFORMAT          DataFormat,
  [out]          PDMACHANNEL            *DmaChannel,
  [out]          PSERVICEGROUP          *ServiceGroup
);
````


## -parameters




### -param Stream [out]

Output pointer for the new stream. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the stream object's <a href="..\portcls\nn-portcls-iminiportwavepcistream.md">IMiniportWavePciStream</a> interface. The caller specifies a valid, non-<b>NULL</b> pointer for this parameter.


### -param OuterUnknown [in, optional]

Pointer to the <b>IUnknown</b> interface of an object that needs to aggregate the stream object. This parameter is optional. If aggregation is not required, the caller specifies this parameter as <b>NULL</b>.


### -param PoolType [in]

Specifies the type of memory pool from which the storage for the DMA-channel object should be allocated. This parameter will be one of the nonpaged pool types defined in the <a href="..\wudfwdm\ne-wudfwdm-_pool_type.md">POOL_TYPE</a> enumeration.


### -param PortStream [in]

Pointer to the <a href="..\portcls\nn-portcls-iportwavepcistream.md">IPortWavePciStream</a> interface of the port driver's stream object.


### -param Pin [in]

Specifies a pin ID identifying the pin that is to be opened. If the WavePci miniport driver's filter descriptor specifies a total of <i>n</i> pin factories on the filter, then valid values for parameter <i>Pin</i> are in the range 0 to <i>n</i>-1.


### -param Capture [in]

Specifies whether to create a capture stream or a render stream. This parameter is <b>TRUE</b> for an capture (input) channel, and <b>FALSE</b> for an playback (output) channel.


### -param DataFormat [in]

Pointer to a <a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a> structure that specifies the stream's data format.


### -param DmaChannel [out]

Output pointer for the DMA channel. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the stream's <a href="..\portcls\nn-portcls-idmachannel.md">IDmaChannel</a> object. The caller specifies a valid, non-<b>NULL</b> pointer for this parameter.


### -param ServiceGroup [out]

Output pointer for the service group. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the <a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a> interface of the stream's service group object. This is the service group that is being registered for interrupt notification. The caller specifies a valid, non-<b>NULL</b> pointer for this parameter.


## -returns



<code>NewStream</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



The <code>NewStream</code> method sets the initial state of the stream to KSSTATE_STOP and its initial position to zero. (See <a href="https://msdn.microsoft.com/library/windows/hardware/ff536733">IMiniportWavePciStream::SetState</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff536727">IMiniportWavePciStream::GetPosition</a>.)

The <i>DataFormat</i> parameter, which specifies the data format of the stream, points to one of the following audio-specific, extended versions of the <a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a> structure:


<a href="..\ksmedia\ns-ksmedia-ksdataformat_waveformatex.md">KSDATAFORMAT_WAVEFORMATEX</a>



<a href="..\ksmedia\ns-ksmedia-ksdataformat_dsound.md">KSDATAFORMAT_DSOUND</a>


If the miniport driver does not provide a service group pointer (that is, if the <code>NewStream</code> call outputs <b>NULL</b> through the <i>ServiceGroup</i> pointer), the port driver sets up its own periodic timer instead for processing stream position and clock events. The period for this timer is currently 20 milliseconds, but the period might change in future implementations.

The <i>Stream</i>, <i>OuterUnknown</i>, <i>PortStream</i>, and <i>ServiceGroup</i> parameters follow the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.

Note that <code>NewStream</code> does not follow the usual reference-counting conventions in its handling of the pointer that it outputs through the <i>DmaChannel</i> OUT parameter. When the port driver finishes using the references that it receives through the <code>NewStream</code> method's other OUT parameters, <i>Stream</i> and <i>ServiceGroup</i>, it releases them, as expected. In contrast, the port driver never uses the <i>DmaChannel</i> pointer that it receives from the <code>NewStream</code> call and it never calls <b>Release</b> on the <i>DmaChannel</i> object.

The ac97 sample audio driver in the Microsoft Windows Driver Kit (WDK) reflects this behavior. This sample's implementation of the <code>IMiniportWavePci::NewStream</code> method calls <b>AddRef</b> on the <i>Stream</i> and <i>ServiceGroup</i> references that it outputs but not the <i>DmaChannel</i> reference. This behavior is preserved for the sake of backward compatibility.

Note that the <code>NewStream</code> methods for the other port types (WaveCyclic, in particular) follow the usual reference-counting conventions for all their OUT parameters. 




## -see-also

<a href="..\portcls\nn-portcls-iminiportwavepci.md">IMiniportWavePci</a>



<a href="..\portcls\nn-portcls-idmachannel.md">IDmaChannel</a>



<a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a>



<a href="..\portcls\nn-portcls-iminiportwavepcistream.md">IMiniportWavePciStream</a>



<a href="..\ks\ns-ks-ksdataformat.md">KSDATAFORMAT</a>



<a href="..\portcls\nn-portcls-iportwavepcistream.md">IPortWavePciStream</a>



<a href="..\ksmedia\ns-ksmedia-ksdataformat_dsound.md">KSDATAFORMAT_DSOUND</a>



<a href="..\wudfwdm\ne-wudfwdm-_pool_type.md">POOL_TYPE</a>



<a href="..\ksmedia\ns-ksmedia-ksdataformat_waveformatex.md">KSDATAFORMAT_WAVEFORMATEX</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportWavePci::NewStream method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

