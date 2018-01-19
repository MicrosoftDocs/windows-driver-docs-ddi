---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_HEADER
title: tagKSCAMERA_EXTENDEDPROP_HEADER
author: windows-driver-content
description: The KSCAMERA_EXTENDEDPROP_HEADER structure is the payload header for an extend control property.
old-location: stream\kscamera_extendedprop_header.htm
old-project: stream
ms.assetid: 2CE89C1E-8FE8-4304-BD3F-5A926CAC74B4
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: tagKSCAMERA_EXTENDEDPROP_HEADER, *PKSCAMERA_EXTENDEDPROP_HEADER, KSCAMERA_EXTENDEDPROP_HEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSCAMERA_EXTENDEDPROP_HEADER
req.alt-loc: Ksmedia.h
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
req.typenames: *PKSCAMERA_EXTENDEDPROP_HEADER, KSCAMERA_EXTENDEDPROP_HEADER
---

# tagKSCAMERA_EXTENDEDPROP_HEADER structure



## -description
The <b>KSCAMERA_EXTENDEDPROP_HEADER</b> structure is the payload header for an extend control property.



## -syntax

````
typedef struct _KSCAMERA_EXTENDEDPROP_HEADER {
  ULONG     Version;
  ULONG     PinId;
  ULONG     Size;
  ULONG     Result;
  ULONGLONG Flags;
  ULONGLONG Capability;
} KSCAMERA_EXTENDEDPROP_HEADER, *PKSCAMERA_EXTENDEDPROP_HEADER;
````


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

### -field KSCAMERA_EXTENDEDPROP_CAPS_ASYNCCONTROL

</td>
<td width="60%">
The control supports asynchronous operation.

</td>
</tr>
<tr>

### -field KSCAMERA_EXTENDEDPROP_CAPS_CANCELLABLE

</td>
<td width="60%">
Applies only to asynchronous controls. This flag marks the control operation as cancellable. If a synchronous control sets this flag, it is be marked as being invalid and is not exposed to higher level applications.

</td>
</tr>
</table>
 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ksmedia\ns-ksmedia-tagkscamera_extendedprop_value.md">KSCAMERA_EXTENDEDPROP_VALUE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSCAMERA_EXTENDEDPROP_HEADER structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

