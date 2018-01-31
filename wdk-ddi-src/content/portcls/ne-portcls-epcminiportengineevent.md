---
UID: NE:portcls.EPcMiniportEngineEvent
title: EPcMiniportEngineEvent
author: windows-driver-content
description: This topic introduces the EPcMiniportEngineEvent enum, and describes the parameters that provide additional information when the miniport driver reports a glitching error.
old-location: audio\epcminiportengineevent.htm
old-project: audio
ms.assetid: 6B282CA4-2EE8-48BB-99E2-1A16A92E57A5
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: portcls/eMINIPORT_GLITCH_REPORT, eMINIPORT_BUFFER_COMPLETE, eMINIPORT_MaxValue, portcls/eMINIPORT_GET_PRESENTATION_POS, eMINIPORT_PROCESSING_MODE, eMINIPORT_PROGRAM_DMA, eMINIPORT_PIN_STATE, portcls/eMINIPORT_LAST_BUFFER_RENDERED, EPcMiniportEngineEvent enumeration [Audio Devices], eMINIPORT_GLITCH_REPORT, eMINIPORT_GET_STREAM_POS, eMINIPORT_GET_PRESENTATION_POS, portcls/eMINIPORT_BUFFER_COMPLETE, portcls/eMINIPORT_PROGRAM_DMA, eMINIPORT_LAST_BUFFER_RENDERED, portcls/eMINIPORT_PROCESSING_MODE, portcls/eMINIPORT_SET_WAVERT_BUFFER_WRITE_POS, portcls/eMINIPORT_IHV_DEFINED, portcls/eMINIPORT_PIN_STATE, portcls/eMINIPORT_GET_STREAM_POS, EPcMiniportEngineEvent, portcls/eMINIPORT_FX_CLSID, audio.epcminiportengineevent, eMINIPORT_FX_CLSID, portcls/eMINIPORT_MaxValue, portcls/EPcMiniportEngineEvent, eMINIPORT_IHV_DEFINED, eMINIPORT_SET_WAVERT_BUFFER_WRITE_POS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Portcls.h
apiname:
-	EPcMiniportEngineEvent
product: Windows
targetos: Windows
req.typenames: EPcMiniportEngineEvent
---

# EPcMiniportEngineEvent enumeration


## -description


This topic introduces the EPcMiniportEngineEvent enum, and describes the parameters that provide additional information when the miniport driver reports a  glitching error.

The event IDs in the following enum represent events that the miniport driver can report, by using callbacks via the port class driver (PortCls).


## -syntax


````
typedef enum _EPcMiniportEngineEvent { 
  eMINIPORT_IHV_DEFINED                  = 0,
  eMINIPORT_BUFFER_COMPLETE,
  eMINIPORT_PIN_STATE,
  eMINIPORT_GET_STREAM_POS,
  eMINIPORT_SET_WAVERT_BUFFER_WRITE_POS,
  eMINIPORT_GET_PRESENTATION_POS,
  eMINIPORT_PROGRAM_DMA,
  eMINIPORT_GLITCH_REPORT,
  eMINIPORT_LAST_BUFFER_RENDERED,
  eMINIPORT_PROCESSING_MODE,
  eMINIPORT_FX_CLSID,
  eMINIPORT_MaxValue
} EPcMiniportEngineEvent;
````


## -enum-fields




#### - eMINIPORT_IHV_DEFINED

Specifies the ID for an IHV-defined event.


#### - eMINIPORT_BUFFER_COMPLETE

Specifies the ID for the buffer complete event.


#### - eMINIPORT_PIN_STATE

Specifies the ID for the event related to a change in pin state.


### -field eMINIPORT_GET_STREAM_POSITION



### -field eMINIPORT_SET_WAVERT_BUFFER_WRITE_POSITION



### -field eMINIPORT_GET_PRESENTATION_POSITION



#### - eMINIPORT_PROGRAM_DMA

Specifies the ID for a "program DMA" event.


#### - eMINIPORT_GLITCH_REPORT

Specifies the ID for a "glitch report" event.


#### - eMINIPORT_LAST_BUFFER_RENDERED

Specifies the ID for the last buffer that was rendered.


#### - eMINIPORT_PROCESSING_MODE

Specifies the ID for the processing mode that was in effect when the glitch happened.


#### - eMINIPORT_FX_CLSID

Specifies the class ID for the audio processing effect (FX) that was in effect when the glitch happened.


#### - eMINIPORT_MaxValue

Specifies the ID for the highest enumerated value that was used to report the glitch.


#### - eMINIPORT_GET_STREAM_POS

Specifies the ID for a "get stream position" event.


#### - eMINIPORT_SET_WAVERT_BUFFER_WRITE_POS

Specifies the ID for a "wave  buffer write position" event.


#### - eMINIPORT_GET_PRESENTATION_POS

Specifies the ID for a "get presentation position" event.


## -remarks


The following table shows the members of the  EPcMiniportEngineEvent enum that were introduced with Windows 8. The table shows the events associated with the enum's members, and the meanings of their parameters.


<table>
<tr>
<th>Event type</th>
<th>Parameter 1</th>
<th>Parameter  2</th>
<th>Parameter  3</th>
<th>Parameter  4</th>
</tr>
<tr>
<td>IHV-specific event type.</td>
<td>Defined and used by IHVs.</td>
<td>Defined and used by IHVs.</td>
<td>Defined and used by IHVs.</td>
<td>Defined and used by IHVs.</td>
</tr>
<tr>
<td>Buffer complete. </td>
<td>Current linear buffer position.</td>
<td>Current WaveRTBuffer write position.</td>
<td>Data length completed.</td>
<td>0</td>
</tr>
<tr>
<td>Pin state.</td>
<td>Current linear buffer position.</td>
<td>Current WaveRTBuffer write position.</td>
<td>
<dl>
<dd>0 - KS_STOP</dd>
<dd>1 - KS_ACQUIRE</dd>
<dd>2 - KS_PAUSE</dd>
<dd>3 - KS_RUN</dd>
</dl>
</td>
<td>0</td>
</tr>
<tr>
<td>Get stream position.</td>
<td>Current linear buffer position.</td>
<td>Current WaveRTBuffer write position.</td>
<td>0</td>
<td>0</td>
</tr>
<tr>
<td>Set WaveRT buffer write position.</td>
<td>Current linear buffer position.</td>
<td>Current WaveRTBuffer write position that was received from PortCls.</td>
<td>Target WaveRTBuffer write position that was received from PortCls.</td>
<td>0</td>
</tr>
<tr>
<td>Get presentation position.</td>
<td>Current linear buffer position.</td>
<td>Current WaveRTBuffer write position.</td>
<td>Presentation position.</td>
<td>0</td>
</tr>
<tr>
<td>Program DMA.</td>
<td>Current linear buffer position.</td>
<td>Current WaveRTBuffer write position.</td>
<td>Starting WaveRtBuffer offset</td>
<td>Data length.</td>
</tr>
<tr>
<td>Glitch detection.</td>
<td>Current linear buffer position.</td>
<td>Current WaveRTBuffer write position.</td>
<td>
<dl>
<dd>1 - WaveRT buffer under run</dd>
<dd>2 - Decoder errors</dd>
<dd>3 - Receive the same WaveRT buffer write position twice in a row.</dd>
</dl>
</td>
<td>When Parameter 3 = '3' then Parameter 4 is the offending write position.</td>
</tr>
</table>
 



The following table shows the members of the  EPcMiniportEngineEvent enum that were introduced with Windows 8.1. The table shows the events associated with the enum's members, and the meanings of their parameters.


<table>
<tr>
<th>Event type</th>
<th>Parameter 1</th>
<th>Parameter  2</th>
<th>Parameter  3</th>
<th>Parameter  4</th>
</tr>
<tr>
<td>Last buffer rendered.</td>
<td>Current linear buffer position.</td>
<td>The very last WaveRtBuffer write position that the driver received.</td>
<td>0</td>
<td>0</td>
</tr>
<tr>
<td>Processing mode.</td>
<td>Current linear buffer position.</td>
<td>Current WaveRTBuffer write position.</td>
<td>First 8 bytes of GUID.</td>
<td>Second 8 bytes of GUID.</td>
</tr>
<tr>
<td>FX class ID.</td>
<td>Current linear buffer position.</td>
<td>Current WaveRTBuffer write position.</td>
<td>First 8 bytes of FX CLSID.            </td>
<td>Second 8 bytes of FX CLSID.            </td>
</tr>
<tr>
<td>Max value.</td>
<td>ID for enumerated value.</td>
<td>0</td>
<td>0</td>
<td>0</td>
</tr>
</table>
 





## -see-also

<a href="https://msdn.microsoft.com/9FF2A5D6-9382-4EE6-AA21-DCF47210F73B">Glitch Reporting for Offloaded Audio</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265124">MiniportWriteEtwEvent</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20EPcMiniportEngineEvent enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

