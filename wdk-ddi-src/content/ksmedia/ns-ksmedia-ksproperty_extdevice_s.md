---
UID: NS:ksmedia.KSPROPERTY_EXTDEVICE_S
title: KSPROPERTY_EXTDEVICE_S
author: windows-driver-content
description: The KSPROPERTY_EXTDEVICE_S structure describes an external device and its capabilities.
old-location: stream\ksproperty_extdevice_s.htm
old-project: stream
ms.assetid: da866f7e-f2c6-4926-bbde-db0629571c57
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSPROPERTY_EXTDEVICE_S, *PKSPROPERTY_EXTDEVICE_S, KSPROPERTY_EXTDEVICE_S
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSPROPERTY_EXTDEVICE_S
req.alt-loc: ksmedia.h
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
req.typenames: *PKSPROPERTY_EXTDEVICE_S, KSPROPERTY_EXTDEVICE_S
---

# KSPROPERTY_EXTDEVICE_S structure



## -description
The KSPROPERTY_EXTDEVICE_S structure describes an external device and its capabilities.



## -syntax

````
typedef struct {
  KSPROPERTY Property;
  union {
    DEVCAPS Capabilities;
    ULONG   DevPort;
    ULONG   PowerState;
    WCHAR   pawchString[MAX_PATH];
    DWORD   NodeUniqueID[2];
  } u;
} KSPROPERTY_EXTDEVICE_S, *PKSPROPERTY_EXTDEVICE_S;
````


## -struct-fields

### -field Property

Specifies an initialized <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field u


### -field Capabilities

Describes the external device's capabilities.


### -field DevPort

Specifies the external device's port. For example:

DEV_PORT_1394

DEV_PORT_USB


### -field PowerState

Specifies the external device's power state:

ED_POWER_ON

ED_POWER_STANDBY

ED_POWER_OFF


### -field pawchString

Specifies the external device's ID and version.


### -field NodeUniqueID

Specifies the external device's unique node Id.

</dd>
</dl>

## -remarks
Any ED_Xxx or DEV_PORT_Xxx tokens are defined in <i>xprtdefs.h</i> in the Microsoft DirectX SDK.


## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia-tagdevcaps.md">DEVCAPS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_EXTDEVICE_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

