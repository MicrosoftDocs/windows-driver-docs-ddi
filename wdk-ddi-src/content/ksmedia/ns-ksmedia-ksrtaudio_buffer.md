---
UID: NS:ksmedia.KSRTAUDIO_BUFFER
title: KSRTAUDIO_BUFFER
author: windows-driver-content
description: The KSRTAUDIO_BUFFER structure specifies the buffer address, size, and a call memory barrier flag for a cyclic audio data buffer.
old-location: audio\ksrtaudio_buffer.htm
old-project: audio
ms.assetid: b80efaf0-ecee-40cd-befb-2139a20840a5
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PKSRTAUDIO_BUFFER, KSRTAUDIO_BUFFER, KSRTAUDIO_BUFFER structure [Audio Devices], PKSRTAUDIO_BUFFER, PKSRTAUDIO_BUFFER structure pointer [Audio Devices], aud-prop_50b4ab60-2e9a-444b-98d3-984d9084ab0b.xml, audio.ksrtaudio_buffer, ksmedia/KSRTAUDIO_BUFFER, ksmedia/PKSRTAUDIO_BUFFER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KSRTAUDIO_BUFFER
product: Windows
targetos: Windows
req.typenames: KSRTAUDIO_BUFFER, *PKSRTAUDIO_BUFFER
---

# KSRTAUDIO_BUFFER structure


## -description


The KSRTAUDIO_BUFFER structure specifies the buffer address, size, and a call memory barrier flag for a cyclic audio data buffer.


## -syntax


````
typedef struct {
  PVOID BufferAddress;
  ULONG ActualBufferSize;
  BOOL  CallMemoryBarrier;
} KSRTAUDIO_BUFFER, *PKSRTAUDIO_BUFFER;
````


## -struct-fields




### -field BufferAddress

Specifies the base address of the cyclic buffer. This is a virtual memory address through which the user-mode client can directly access the buffer. The driver writes the actual base address of the allocated buffer into this member.


### -field ActualBufferSize

Specifies the buffer size, in bytes. The driver sets this member to the actual size of the allocated buffer.


### -field CallMemoryBarrier

Specifies a flag based on cache type of the allocated buffer. The driver sets this flag to <b>TRUE</b> if the cache type is <b>MmWriteCombined</b>; otherwise, the flag should be set to <b>FALSE</b>. For more information about <b>MmWriteCombined</b>, see <a href="..\wudfwdm\ne-wudfwdm-_memory_caching_type.md">MEMORY_CACHING_TYPE </a>,


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff537370">KSPROPERTY_RTAUDIO_BUFFER</a> request uses the KSRTAUDIO_BUFFER structure to describe the actual cyclic buffer that the driver allocates. This client fills in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537494">KSRTAUDIO_BUFFER_PROPERTY</a> structure to request the audio buffer, and the driver fills in a KSRTAUDIO_BUFFER structure with the results from the buffer allocation.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537494">KSRTAUDIO_BUFFER_PROPERTY</a>



<a href="..\wudfwdm\ne-wudfwdm-_memory_caching_type.md">MEMORY_CACHING_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537370">KSPROPERTY_RTAUDIO_BUFFER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSRTAUDIO_BUFFER structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

