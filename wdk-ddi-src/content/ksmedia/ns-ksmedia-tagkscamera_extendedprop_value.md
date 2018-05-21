---
UID: NS:ksmedia.tagKSCAMERA_EXTENDEDPROP_VALUE
title: tagKSCAMERA_EXTENDEDPROP_VALUE
author: windows-driver-content
description: The KSCAMERA_EXTENDEDPROP_VALUE structure is a data type union used to express an extended property value.
old-location: stream\kscamera_extendedprop_value.htm
old-project: stream
ms.assetid: E595C2BF-C3C8-4FE8-90B0-CD53524F4852
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PKSCAMERA_EXTENDEDPROP_VALUE, KSCAMERA_EXTENDEDPROP_VALUE, KSCAMERA_EXTENDEDPROP_VALUE structure [Streaming Media Devices], PKSCAMERA_EXTENDEDPROP_VALUE, PKSCAMERA_EXTENDEDPROP_VALUE structure pointer [Streaming Media Devices], ksmedia/KSCAMERA_EXTENDEDPROP_VALUE, ksmedia/PKSCAMERA_EXTENDEDPROP_VALUE, stream.kscamera_extendedprop_value, tagKSCAMERA_EXTENDEDPROP_VALUE"
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
-	Ksmedia.h
api_name:
-	KSCAMERA_EXTENDEDPROP_VALUE
product:
- Windows
targetos: Windows
req.typenames: KSCAMERA_EXTENDEDPROP_VALUE, *PKSCAMERA_EXTENDEDPROP_VALUE
---

# tagKSCAMERA_EXTENDEDPROP_VALUE structure


## -description


The <b>KSCAMERA_EXTENDEDPROP_VALUE</b> structure is a data type union used to express an extended property value.


## -struct-fields




### -field Value

The extended property value. 


### -field Value.dbl

The extended property expressed as a <b>double</b> value.


### -field Value.ull

The extended property expressed as a <b>ULONGLONG</b> value.


### -field Value.ul

The extended property expressed as a <b>ULONG</b> value.


### -field Value.ratio

The extended property value expressed as a ratio.


### -field Value.l

The extended property expressed as a <b>LONG</b> value.


### -field Value.ll

The extended property expressed as a <b>LONGLONG</b> value.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn567563">KSCAMERA_EXTENDEDPROP_HEADER</a>
 

 

