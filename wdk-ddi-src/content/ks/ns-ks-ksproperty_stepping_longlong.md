---
UID: NS:ks.KSPROPERTY_STEPPING_LONGLONG
title: KSPROPERTY_STEPPING_LONGLONG
author: windows-driver-content
description: The KSPROPERTY_STEPPING_LONGLONG structure defines the valid range of values for a 64-bit property.
old-location: stream\ksproperty_stepping_longlong.htm
tech.root: stream
ms.assetid: 14ec504e-baf6-441a-b908-2d8c051dd45a
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PKSPROPERTY_STEPPING_LONGLONG, KSPROPERTY_STEPPING_LONGLONG, KSPROPERTY_STEPPING_LONGLONG structure [Streaming Media Devices], PKSPROPERTY_STEPPING_LONGLONG, PKSPROPERTY_STEPPING_LONGLONG structure pointer [Streaming Media Devices], ks-struct_f7cc7036-e7b5-4765-bf2e-abd24f5f06a6.xml, ks/KSPROPERTY_STEPPING_LONGLONG, ks/PKSPROPERTY_STEPPING_LONGLONG, stream.ksproperty_stepping_longlong"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
-	ks.h
api_name:
-	KSPROPERTY_STEPPING_LONGLONG
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_STEPPING_LONGLONG, *PKSPROPERTY_STEPPING_LONGLONG
---

# KSPROPERTY_STEPPING_LONGLONG structure


## -description


The KSPROPERTY_STEPPING_LONGLONG structure defines the valid range of values for a 64-bit property.


## -struct-fields




### -field SteppingDelta

Specifies the step value that should be used to create legal values within the range defined in <b>Bounds</b>.


### -field Bounds

Specifies a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff564395">KSPROPERTY_BOUNDS_LONGLONG</a> that specifies the range of values over which the <b>SteppingDelta</b> is valid.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff565190">KSPROPERTY_MEMBERSLIST</a> structure may contain structures of this type in its <b>Members</b> array.

See the Testcap sample in the Windows Driver Kit (WDK) for examples of usage.

For more information, see <a href="https://msdn.microsoft.com/a385929e-1934-4d88-aaf9-ff1ddbfd30f7">KS Properties</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564395">KSPROPERTY_BOUNDS_LONGLONG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565190">KSPROPERTY_MEMBERSLIST</a>
 

 

