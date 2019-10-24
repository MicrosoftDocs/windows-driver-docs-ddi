---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_HEADER
title: tagKSCAMERA_EXTENDEDPROP_HEADER (ksmedia.h)
description: The KSCAMERA_EXTENDEDPROP_HEADER structure is the payload header for an extend control property.
old-location: stream\kscamera_extendedprop_header.htm
tech.root: stream
ms.assetid: 2CE89C1E-8FE8-4304-BD3F-5A926CAC74B4
ms.date: 04/23/2018
ms.keywords: "*PKSCAMERA_EXTENDEDPROP_HEADER, KSCAMERA_EXTENDEDPROP_CAPS_ASYNCCONTROL, KSCAMERA_EXTENDEDPROP_CAPS_CANCELLABLE, KSCAMERA_EXTENDEDPROP_HEADER, KSCAMERA_EXTENDEDPROP_HEADER structure [Streaming Media Devices], PKSCAMERA_EXTENDEDPROP_HEADER, PKSCAMERA_EXTENDEDPROP_HEADER structure pointer [Streaming Media Devices], ksmedia/KSCAMERA_EXTENDEDPROP_HEADER, ksmedia/PKSCAMERA_EXTENDEDPROP_HEADER, stream.kscamera_extendedprop_header, tagKSCAMERA_EXTENDEDPROP_HEADER"
ms.topic: struct
f1_keywords:
 - "ksmedia/KSCAMERA_EXTENDEDPROP_HEADER"
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ksmedia.h
api_name:
- KSCAMERA_EXTENDEDPROP_HEADER
product:
- Windows
targetos: Windows
req.typenames: KSCAMERA_EXTENDEDPROP_HEADER, *PKSCAMERA_EXTENDEDPROP_HEADER
---

# tagKSCAMERA_EXTENDEDPROP_HEADER structure


## -description


The <b>KSCAMERA_EXTENDEDPROP_HEADER</b> structure is the payload header for an extend control property.


## -struct-fields




### -field Version

The extended property version number. This is set to 1.


### -field PinId

The pin ID that corresponds with the property.  If <b>PinId</b> is set to (ULONG)-1, the control applies to the filter.  Otherwise, the camera driver must route this control to the corresponding pin when that pin is created (or if already available).


### -field Size

The total size, in bytes of the entire payload. This includes the <b>KSCAMERA_EXTENDEDPROP_HEADER</b> structure and the following control specific payload data.


### -field Result

For a set operation, this is 0.  For queries, <b>Result</b> contains any failure code the driver provides for the most recent control operation.


### -field Flags

The settings in <b>Flags</b> may vary depending on the control.

The high order bit of the <b>Flags</b> value is reserved.  This bit serves as the cancel flag and is defined as <b>KSCAMERA_EXTENDEDPROP_FLAG_CANCELOPERATION</b>.  This flag is only meaningful for asynchronous controls.


### -field Capability

This member is read only and indicates the standard capabilities of the control. The following capabilities are defined.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="KSCAMERA_EXTENDEDPROP_CAPS_ASYNCCONTROL"></a><a id="kscamera_extendedprop_caps_asynccontrol"></a><dl>
<dt><b>KSCAMERA_EXTENDEDPROP_CAPS_ASYNCCONTROL</b></dt>
</dl>
</td>
<td width="60%">
The control supports asynchronous operation.

</td>
</tr>
<tr>
<td width="40%"><a id="KSCAMERA_EXTENDEDPROP_CAPS_CANCELLABLE"></a><a id="kscamera_extendedprop_caps_cancellable"></a><dl>
<dt><b>KSCAMERA_EXTENDEDPROP_CAPS_CANCELLABLE</b></dt>
</dl>
</td>
<td width="60%">
Applies only to asynchronous controls. This flag marks the control operation as cancellable. If a synchronous control sets this flag, it is be marked as being invalid and is not exposed to higher level applications.

</td>
</tr>
</table>
 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-tagkscamera_extendedprop_value">KSCAMERA_EXTENDEDPROP_VALUE</a>
 

 

