---
UID: NF:portcls.IMiniportWaveRTStreamNotification.FreeBufferWithNotification
title: IMiniportWaveRTStreamNotification::FreeBufferWithNotification (portcls.h)
description: The FreeBufferWithNotification method is used to free an audio buffer previously allocated with a call to IMiniportWaveRTStreamNotification::AllocateBufferWithNotification.
old-location: audio\iminiportwavertstreamnotification_freebufferwithnotification.htm
tech.root: audio
ms.assetid: 2ec9222b-d9e7-4386-ac66-30c5436f549d
ms.date: 05/08/2018
ms.keywords: FreeBufferWithNotification, FreeBufferWithNotification method [Audio Devices], FreeBufferWithNotification method [Audio Devices],IMiniportWaveRTStreamNotification interface, IMiniportWaveRTStreamNotification interface [Audio Devices],FreeBufferWithNotification method, IMiniportWaveRTStreamNotification.FreeBufferWithNotification, IMiniportWaveRTStreamNotification::FreeBufferWithNotification, audio.iminiportwavertstreamnotification_freebufferwithnotification, audmp-routines_7b323e6d-c060-4d8a-beb1-88303e45bc0e.xml, portcls/IMiniportWaveRTStreamNotification::FreeBufferWithNotification
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- portcls.h
api_name:
- IMiniportWaveRTStreamNotification.FreeBufferWithNotification
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportWaveRTStreamNotification::FreeBufferWithNotification


## -description


The <code>FreeBufferWithNotification</code> method is used to free an audio buffer previously allocated with a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff536740">IMiniportWaveRTStreamNotification::AllocateBufferWithNotification</a>.


## -parameters




### -param AudioBufferMdl [in]

Specifies a memory descriptor list (<a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a>) previously allocated with a call to <b>IMiniportWaveRTStreamNotification::AllocateBufferWithNotification</b>.


### -param BufferSize [in]

Output pointer for the number of bytes the method has written to the Attributes buffer. This parameter points to a ULONG variable into which the method writes the byte count.


## -returns



None.




## -remarks



The port driver calls this method to free an audio buffer that was allocated with a previous call to <b>IMiniportWaveRTStreamNotification::AllocateBufferWithNotification</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536739">IMiniportWaveRTStreamNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536740">IMiniportWaveRTStreamNotification::AllocateBufferWithNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a>
 

 

