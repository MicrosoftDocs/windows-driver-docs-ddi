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
ms.keywords: vidcapstruct_7c8b60d9-303e-489a-8c93-39d91cda2819.xml, *PKSPROPERTY_EXTDEVICE_S, KSPROPERTY_EXTDEVICE_S structure [Streaming Media Devices], ksmedia/PKSPROPERTY_EXTDEVICE_S, PKSPROPERTY_EXTDEVICE_S structure pointer [Streaming Media Devices], stream.ksproperty_extdevice_s, KSPROPERTY_EXTDEVICE_S, ksmedia/KSPROPERTY_EXTDEVICE_S, PKSPROPERTY_EXTDEVICE_S
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
-	ksmedia.h
apiname:
-	KSPROPERTY_EXTDEVICE_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_EXTDEVICE_S, *PKSPROPERTY_EXTDEVICE_S
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




### -field u



### -field u.Capabilities

Describes the external device's capabilities.


### -field u.DevPort

Specifies the external device's port. For example:

DEV_PORT_1394

DEV_PORT_USB


### -field u.PowerState

Specifies the external device's power state:

ED_POWER_ON

ED_POWER_STANDBY

ED_POWER_OFF


### -field u.pawchString

Specifies the external device's ID and version.


### -field u.NodeUniqueID

Specifies the external device's unique node Id.


### -field Property

Specifies an initialized <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


## -remarks


Any ED_Xxx or DEV_PORT_Xxx tokens are defined in <i>xprtdefs.h</i> in the Microsoft DirectX SDK.



## -see-also

<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>

<a href="..\ksmedia\ns-ksmedia-tagdevcaps.md">DEVCAPS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_EXTDEVICE_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

