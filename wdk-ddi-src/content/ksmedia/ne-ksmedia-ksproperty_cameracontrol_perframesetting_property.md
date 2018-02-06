---
UID: NE:ksmedia.KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_PROPERTY
title: KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_PROPERTY
author: windows-driver-content
description: This enumeration contains the property IDs defined for the per-frame property set.
old-location: stream\ksproperty_cameracontrol_perframesetting_property.htm
old-project: stream
ms.assetid: 59328DD6-3E7B-43C3-A1FF-E02DC24228BA
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_CLEAR, KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_PROPERTY enumeration [Streaming Media Devices], stream.ksproperty_cameracontrol_perframesetting_property, ksmedia/KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_CAPABILITY, KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_SET, KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_PROPERTY, ksmedia/KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_PROPERTY, ksmedia/KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_SET, ksmedia/KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_CLEAR, KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_CAPABILITY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ksmedia.h
req.include-header: 
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
-	Ksmedia.h
apiname:
-	KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_PROPERTY
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_PROPERTY
---

# KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_PROPERTY enumeration


## -description


This enumeration contains the property IDs defined for the per-frame property set.


## -syntax


````
typedef enum  { 
  KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_CAPABILITY  = 0,
  KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_SET,
  KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_CLEAR
} KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_PROPERTY;
````


## -enum-fields




### -field KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_CAPABILITY

This is used to query the driver’s per-frame settings capabilities.


### -field KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_SET

This is used to configure the per-frame settings.


### -field KSPROPERTY_CAMERACONTROL_PERFRAMESETTING_CLEAR

This is used to clear the per-frame settings previously configured.

