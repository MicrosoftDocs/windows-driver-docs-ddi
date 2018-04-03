---
UID: NS:61883._CIP_FRAME
title: "_CIP_FRAME"
author: windows-driver-content
description: The CIP_FRAME structure describes a frame to be attached to an input or output plug.
old-location: ieee\cip_frame.htm
old-project: IEEE
ms.assetid: ac9efa58-fd38-43f2-85e6-577d58735847
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PCIP_FRAME, 61883/CIP_FRAME, 61883/PCIP_FRAME, 61883_structures_1fd796fa-88d2-4dc4-a440-89bf50b81ae8.xml, CIP_FRAME, CIP_FRAME structure [Buses], IEEE.cip_frame, PCIP_FRAME, PCIP_FRAME structure pointer [Buses], _CIP_FRAME"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 61883.h
req.include-header: 61883.h
req.target-type: Windows
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	61883.h
api_name:
-	CIP_FRAME
product:
- Windows
targetos: Windows
req.typenames: CIP_FRAME, *PCIP_FRAME
---

# _CIP_FRAME structure


## -description


The CIP_FRAME structure describes a frame to be attached to an input or output plug.  


## -struct-fields




### -field Flags

Specifies options associated with this frame. 

For packets to be received, <b>Flags</b> can be one of the following:





#### CIP_VALIDATE_FIRST_SOURCE

Instructs the IEC-61883 protocol driver to call the client-driver-supplied function at <b>pfnValidate</b> to validate only the first source packet.



#### CIP_VALIDATE_ALL_SOURCE

Instructs the IEC-61883 protocol driver to call the client-driver-supplied function at <b>pfnValidate</b> to validate all source packets.

For packets to be received, CIP_VALIDATE_XXX can be combined with either or both of the following:





#### CIP_STRIP_SOURCE_HEADER

Instructs the protocol driver to strip the source header packet within a source packet.



#### CIP_USE_SOURCE_HEADER_TIMESTAMP

Instructs the protocol driver to timestamp the frame with the timestamp found within the source header packet.

For packets to be transmitted, <b>Flags</b> can be one of the following:





#### CIP_DV_STYLE_SYT

The value at <b>TimeStamp</b> is formatted for data transmission to digital video devices (SD-DVCR, HD-DVCR, or SDL-DVCR).



#### CIP_AUDIO_STYLE_SYT

The value at <b>TimeStamp</b> is formatted for audio and music data transmission to audio devices.

For packets to be transmitted or received, <b>Flags</b> can also be set with the following:





#### CIP_RESET_FRAME_ON_DISCONTINUITY

Instructs the protocol driver to resume a stopped stream at the beginning of the frame instead of the next source packet. 


### -field pfnValidate

Points to a caller-supplied function to validate a source packet. This function uses the following prototype: The parameter <b>ValidateInfo</b> must point to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537048">CIP_VALIDATE_INFO</a> structure that contains information about the frame. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>ULONG 
  (*PCIP_VALIDATE_ROUTINE) ( 
    IN PCIP_VALIDATE_INFO ValidateInfo
   );</pre>
</td>
</tr>
</table></span></div>

### -field ValidateContext

Points to an optional caller-defined context for the function at <b>pfnValidate</b>. If the function does not require a context, <b>ValidateContext</b> can be <b>NULL</b>.


### -field pfnNotify

Points to a caller-supplied function to be called by the protocol driver when the requested frame is completed. The protocol driver calls this function at IRQL = DISPATCH_LEVEL.

This function uses the following prototype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>ULONG 
  (*PCIP_NOTIFY_ROUTINE) ( 
     IN PCIP_NOTIFY_INFO NotifyInfo 
 );</pre>
</td>
</tr>
</table></span></div>




##### 


### -field NotifyContext

Points to an optional caller-defined context for the caller-supplied function at <b>pfnNotify</b>. If the function does not require a context, <b>NotifyContext</b> can be <b>NULL</b>.


### -field Timestamp

The time associated with completion of the frame. 

For packets to be received, the protocol driver sets this member to the time when transmission of the frame was completed, unless CIP_USE_SOURCE_HEADER_TIMESTAMP is set in <b>Flags</b>. 

For packets to be transmitted, CIP-DV_STYLE_SYT or CIP_AUDIO_STYLE_SYT in <b>Flags</b> indicates the format of the timestamp.


### -field Status

The status of the frame. Can be one of the following:

CIP_STATUS_SUCCESS

CIP_STATUS_CORRUPT_FRAME

CIP_STATUS_FIRST_FRAME


### -field Packet

Points to the beginning of a caller-allocated data buffer to be transmitted or received with this frame. The frame length specified in the associated <a href="https://msdn.microsoft.com/library/windows/hardware/ff536950">Av61883_AttachFrame</a> request indicates the size of the buffer.


### -field CompletedBytes


#### - Reserved


#### - pNext

Reserved for internal use.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536950">Av61883_AttachFrame</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536956">Av61883_CancelFrame</a>
 

 

