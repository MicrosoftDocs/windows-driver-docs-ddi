---
UID: NS:usbcamdi._pipe_config_descriptor
title: _pipe_config_descriptor (usbcamdi.h)
description: The USBCAMD_Pipe_Config_Descriptor structure describes the association between pipes and streams.
old-location: stream\usbcamd_pipe_config_descriptor.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["pipe_config_descriptor structure"]
ms.keywords: "*PUSBCAMD_Pipe_Config_Descriptor, PUSBCAMD_Pipe_Config_Descriptor, PUSBCAMD_Pipe_Config_Descriptor structure pointer [Streaming Media Devices], USBCAMD_Pipe_Config_Descriptor, USBCAMD_Pipe_Config_Descriptor structure [Streaming Media Devices], _pipe_config_descriptor, stream.usbcamd_pipe_config_descriptor, usbcamdi/PUSBCAMD_Pipe_Config_Descriptor, usbcamdi/USBCAMD_Pipe_Config_Descriptor, usbcmdpr_41ff7b81-10f6-469c-ad6f-d444acf15c07.xml"
req.header: usbcamdi.h
req.include-header: Usbcamdi.h
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
targetos: Windows
req.typenames: USBCAMD_Pipe_Config_Descriptor, *PUSBCAMD_Pipe_Config_Descriptor
f1_keywords:
 - _pipe_config_descriptor
 - usbcamdi/_pipe_config_descriptor
 - PUSBCAMD_Pipe_Config_Descriptor
 - usbcamdi/PUSBCAMD_Pipe_Config_Descriptor
 - USBCAMD_Pipe_Config_Descriptor
 - usbcamdi/USBCAMD_Pipe_Config_Descriptor
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbcamdi.h
api_name:
 - USBCAMD_Pipe_Config_Descriptor
---

# _pipe_config_descriptor structure


## -description

The <b>USBCAMD_Pipe_Config_Descriptor</b> structure describes the association between pipes and streams.

## -struct-fields

### -field StreamAssociation

Specifies the type of stream. This should be set to one of the following values:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
USBCAMD_VIDEO_STREAM

</td>
<td>
Indicates that the stream contains video data.

</td>
</tr>
<tr>
<td>
USBCAMD_STILL_STREAM

</td>
<td>
Indicates that the stream contains still data.

</td>
</tr>
<tr>
<td>
USBCAMD_VIDEO_STILL_STREAM

</td>
<td>
Indicates that the stream contains both video and still data.

</td>
</tr>
</table>

### -field PipeConfigFlags

Specifies the pipe characteristics. This should be set to one of the following values:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
USBCAMD_DATA_PIPE

</td>
<td>
Indicates a video or still data pipe.

</td>
</tr>
<tr>
<td>
USBCAMD_MULTIPLEX_PIPE

</td>
<td>
Indicates a video and still data pipe.

</td>
</tr>
<tr>
<td>
USBCAMD_SYNC_PIPE

</td>
<td>
Indicates an out-of-band signaling pipe.

</td>
</tr>
<tr>
<td>
USBCAMD_DONT_CARE_PIPE

</td>
<td>
Indicates a pipe that is not to be used for video or still streaming.

</td>
</tr>
</table>

## -remarks

The camera minidriver indicates pipe stream associations by identifying all streams associated with a particular pipe. If there is more than one stream association, USBCAMD creates a virtual still pin. The still stream pin always follows the video stream pin (that is, the video stream pin is the first stream pin). 

The <a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_configure_routine_ex">CamConfigureEx</a> routine uses the <b>USBCAMD_Pipe_Config_Descriptor</b> structure to establish a connection between pipes and streams. An array of USBCAMD_Pipe_Config_Descriptor structures is passed into <b>CamConfigureEx</b>, along with the array size, which is equal to the number of pipes found.

The camera minidriver must set the <b>PipeConfigFlags</b> member to the value USBCAMD_DONT_CARE_PIPE if a particular pipe should not be used by USBCAMD. For example, when using an audio and video isochronous pipe, and a camera device that supports stills and video, the <b>PipeConfigFlags</b> member in the first structure should be set to USBCAMD_DONT_CARE_PIPE. The second <b>USBCAMD_Pipe_Config_Descriptor</b> structure should have its <b>StreamAssociation</b> member value set to USBCAMD_VIDEO_STILL_STREAM and its <b>PipeConfigFlags</b> member value set to USBCAMD_MULTIPLEX_PIPE.

The USBCAMD library requires that the camera must have a single configuration description, and all alternate settings within the USB video streaming interface must have the same number and type of pipes.

<b>USBCAMD_Pipe_Config_Descriptor</b> is not supported in the original USBCAMD.

## -see-also

<a href="/windows-hardware/drivers/ddi/usbcamdi/nc-usbcamdi-pcam_configure_routine_ex">CamConfigureEx</a>
