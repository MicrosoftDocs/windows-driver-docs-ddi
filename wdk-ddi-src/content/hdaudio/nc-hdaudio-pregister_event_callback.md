---
UID: NC:hdaudio.PREGISTER_EVENT_CALLBACK
title: PREGISTER_EVENT_CALLBACK (hdaudio.h)
description: The RegisterEventCallback routine registers a callback routine for an unsolicited response from a codec or codecs.The function pointer type for a RegisterEventCallback routine is defined as follows.
old-location: audio\registereventcallback.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["PREGISTER_EVENT_CALLBACK callback function"]
ms.keywords: PREGISTER_EVENT_CALLBACK, PREGISTER_EVENT_CALLBACK callback, RegisterEventCallback, RegisterEventCallback callback function [Audio Devices], aud-prop2_4ef71e0f-0887-4d20-8198-cb5b9c161647.xml, audio.registereventcallback, hdaudio/RegisterEventCallback
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL (See Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - PREGISTER_EVENT_CALLBACK
 - hdaudio/PREGISTER_EVENT_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - hdaudio.h
api_name:
 - PREGISTER_EVENT_CALLBACK
---

# PREGISTER_EVENT_CALLBACK callback function


## -description

The <i>RegisterEventCallback</i> routine registers a callback routine for an unsolicited response from a codec or codecs.

The function pointer type for a <i>RegisterEventCallback</i> routine is defined as follows.

## -parameters

### -param _context 

[in]
Specifies the context value from the <b>Context</b> member of the <a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a><u>, </u><a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a>, or <a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_bdl">HDAUDIO_BUS_INTERFACE_BDL</a> structure.

### -param Routine 

[in]
Function pointer to a callback routine. This parameter must be a valid, non-NULL function pointer of type PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK. For more information, see the following Remarks section.

### -param Context 

[in]
Specifies a context value for the callback routine. The caller casts the context value to type PVOID. When a codec generates an unsolicited response that contains the specified tag, the HD Audio bus driver passes the context value to the callback routine as a call parameter.

### -param Tag 

[out]
Retrieves a tag value that identifies the unsolicited response. This parameter points to a caller-allocated UCHAR variable into which the routine writes the tag value. The caller should specify this tag value when programming the codec or codecs to generate the unsolicited response. For more information, see the following Remarks section.

## -returns

<i>RegisterEventCallback</i> returns STATUS_SUCCESS if the call succeeds in registering the event. Otherwise, the routine returns an appropriate error code. The following table shows a possible return status code.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Indicates that not enough resources are available to complete the operation.

</td>
</tr>
</table>

## -remarks

This routine registers a callback routine for an unsolicited response from a codec. The routine outputs a tag to identify the unsolicited response. When the HD Audio bus driver encounters an unsolicited response from any codec with a matching tag value, the routine calls the specified callback routine at IRQL DISPATCH_LEVEL and passes the specified context value to the routine as a call parameter.

Following the call to <i>RegisterEventCallback</i>, the function driver is responsible for programming the codec or codecs to generate unsolicited responses with the specified tag.

The routine assigns a unique tag to each registered callback routine. The unique association between tag and callback routine persists as long as the callback routine remains registered. The function driver can delete the registration of a callback routine by calling <a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-punregister_event_callback">UnregisterEventCallback</a>.

Currently, the bus driver can supply up to 64 unique tags per codec.

The callback parameter is a function pointer to a callback routine in the function driver. The function pointer type for the callback routine is defined as:


```
typedef VOID
  (*PHDAUDIO_UNSOLICITED_RESPONSE_CALLBACK)
    (HDAUDIO_CODEC_RESPONSE, PVOID);
```

The first call parameter is a structure of type <a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_codec_response">HDAUDIO_CODEC_RESPONSE</a> that specifies the codec's response to the command. This structure is passed by value. The second call parameter is the <i>callbackContext</i> value that was passed previously to <i>RegisterEventCallback</i>. The HD Audio bus driver calls the callback routine at IRQL DISPATCH_LEVEL.

## -see-also

<a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a>



<a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_bdl">HDAUDIO_BUS_INTERFACE_BDL</a>



<a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a>



<a href="/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_codec_response">HDAUDIO_CODEC_RESPONSE</a>



<a href="/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-punregister_event_callback">UnregisterEventCallback</a>
 

[hdaudio.h](../hdaudio/index.md)

