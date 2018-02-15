---
UID: NS:ks.KSIDENTIFIER
title: KSIDENTIFIER
author: windows-driver-content
description: The KSIDENTIFIER structure specifies a GUID that uniquely identifies a related set of GUIDs, and an index value to refer to a specific member within that set.
old-location: stream\ksidentifier.htm
old-project: stream
ms.assetid: b89977da-d3ac-4f1f-867e-b3b7912b955d
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/KSIDENTIFIER, *PKSPIN_INTERFACE, *PKSIDENTIFIER, KSIDENTIFIER structure [Streaming Media Devices], *PKSPROPERTY, KSMETHOD, *PKSEVENT, KSIDENTIFIER, PKSIDENTIFIER, PKSIDENTIFIER structure pointer [Streaming Media Devices], KSDEGRADE, KSEVENT, ks-struct_652a0465-0c2b-4e46-ac43-7a6c5bbdaf80.xml, KSPROPERTY, *PKSDEGRADE, ks/PKSIDENTIFIER, *PKSPIN_MEDIUM, KSPIN_MEDIUM, *PKSMETHOD, KSPIN_INTERFACE, stream.ksidentifier
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
-	KSIDENTIFIER
product: Windows
targetos: Windows
req.typenames: "*PKSIDENTIFIER, KSIDENTIFIER"
---

# KSIDENTIFIER structure


## -description


The KSIDENTIFIER structure specifies a GUID that uniquely identifies a related set of GUIDs, and an index value to refer to a specific member within that set.


## -syntax


````
typedef struct {
  union {
    struct {
      GUID  Set;
      ULONG Id;
      ULONG Flags;
    };
    LONGLONG Alignment;
  };
} KSIDENTIFIER, *PKSIDENTIFIER;
````


## -struct-fields




### -field _IDENTIFIER

 


### -field _IDENTIFIER.Set

 


### -field _IDENTIFIER.Id

 


### -field _IDENTIFIER.Flags

 


### -field Set

Specifies the globally unique set identifier.


### -field Id

Specifies the set-specific identifier for an item within the set.


### -field Flags

Specifies values used for various set types, such as properties and methods. Zero when not used.


### -field Alignment

Not used.  A member of an unnamed union used to force proper alignment on the unnamed structure.


## -remarks



The <a href="..\ks\nf-ks-ikscontrol-ksevent.md">KSEVENT</a>, <a href="..\ks\nf-ks-ikscontrol-ksmethod.md">KSMETHOD</a>, and <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structures are aliases for the KSIDENTIFIER structure. As such, their definitions are identical. 

The use of an ID within the set allows one to perform a single large compare for a set identifier, then smaller quick compares (for example, by using a switch statement for identifiers within a set). For example, a <i>property set</i> is referred to by a unique GUID identifier, and properties within that set are referred to by the short ID.

<i>Method</i>, <i>Event</i>, <i>Interface</i>, and <i>medium sets</i> can be thought of as "classes" of sets.




## -see-also

<a href="..\ks\nf-ks-ikscontrol-ksmethod.md">KSMETHOD</a>



<a href="..\ks\nf-ks-ikscontrol-ksevent.md">KSEVENT</a>



<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSIDENTIFIER structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

