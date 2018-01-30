---
UID: NS:ks.KSPROPERTY_BOUNDS_LONG
title: KSPROPERTY_BOUNDS_LONG
author: windows-driver-content
description: The KSPROPERTY_BOUNDS_LONG structure defines the bounds for a 32-bit property.
old-location: stream\ksproperty_bounds_long.htm
old-project: stream
ms.assetid: 16804ff1-8531-48aa-baf6-b89ccfe25d07
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PKSPROPERTY_BOUNDS_LONG union pointer [Streaming Media Devices], stream.ksproperty_bounds_long, KSPROPERTY_BOUNDS_LONG, ks/PKSPROPERTY_BOUNDS_LONG, PKSPROPERTY_BOUNDS_LONG, *PKSPROPERTY_BOUNDS_LONG, ks-struct_805e1a44-91bb-45be-a99d-174e98639d9e.xml, ks/KSPROPERTY_BOUNDS_LONG, KSPROPERTY_BOUNDS_LONG union [Streaming Media Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KSPROPERTY_BOUNDS_LONG
product: Windows
targetos: Windows
req.typenames: "*PKSPROPERTY_BOUNDS_LONG, KSPROPERTY_BOUNDS_LONG"
---

# KSPROPERTY_BOUNDS_LONG structure


## -description


The KSPROPERTY_BOUNDS_LONG structure defines the bounds for a 32-bit property.


## -syntax


````
typedef union {
  struct {
    LONG SignedMinimum;
    LONG SignedMaximum;
  };
  struct {
    ULONG UnsignedMinimum;
    ULONG UnsignedMaximum;
  };
} KSPROPERTY_BOUNDS_LONG, *PKSPROPERTY_BOUNDS_LONG;
````


## -struct-fields




### -field _SIGNED

 


### -field _SIGNED.SignedMinimum

 


### -field _SIGNED.SignedMaximum

 


### -field SignedMinimum

Specifies a minimum bound as a signed 32-bit value.


### -field SignedMaximum

Specifies a maximum bound as a signed 32-bit value.


### -field _UNSIGNED

 


### -field _UNSIGNED.UnsignedMinimum

 


### -field _UNSIGNED.UnsignedMaximum

 


### -field UnsignedMinimum

Specifies a minimum bound as an unsigned 32-bit value.


### -field UnsignedMaximum

Specifies a maximum bound as an unsigned 32-bit value.


## -remarks


This structure specifies a range of 32-bit values for a property. Use only when the <b>MembersFlags</b> member of the relevant <a href="..\ks\ns-ks-ksproperty_membersheader.md">KSPROPERTY_MEMBERSHEADER</a> is set to KSPROPERTY_MEMBER_RANGES. Use this structure in the <b>Members</b> array in the relevant <a href="..\ks\ns-ks-ksproperty_memberslist.md">KSPROPERTY_MEMBERSLIST</a> structure.

See the Testcap sample in the Windows Driver Kit (WDK) for examples of usage.

Also see related information in <a href="https://msdn.microsoft.com/a385929e-1934-4d88-aaf9-ff1ddbfd30f7">KS Properties</a>.



## -see-also

<a href="..\ks\ns-ks-ksproperty_memberslist.md">KSPROPERTY_MEMBERSLIST</a>

<a href="..\ks\ns-ks-ksproperty_membersheader.md">KSPROPERTY_MEMBERSHEADER</a>

<a href="..\ks\ns-ks-ksproperty_values.md">KSPROPERTY_VALUES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_BOUNDS_LONG union%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

