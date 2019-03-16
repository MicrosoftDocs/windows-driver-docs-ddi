---
UID: NS:ks.__unnamed_struct_71
title: KSMETHOD_SET (ks.h)
description: The KSMETHOD_SET structure describes the methods that comprise a kernel streaming method set.
old-location: stream\ksmethod_set.htm
tech.root: stream
ms.assetid: e06bbf6f-f636-4fb1-8195-b74512d4cd13
ms.date: 04/23/2018
ms.keywords: "*PKSMETHOD_SET, KSMETHOD_SET, KSMETHOD_SET structure [Streaming Media Devices], PKSMETHOD_SET, PKSMETHOD_SET structure pointer [Streaming Media Devices], ks-struct_c3d1123f-8d2a-491b-a748-df8d88c7d9bc.xml, ks/KSMETHOD_SET, ks/PKSMETHOD_SET, stream.ksmethod_set"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KSMETHOD_SET
product:
- Windows
targetos: Windows
req.typenames: KSMETHOD_SET, *PKSMETHOD_SET
---

# KSMETHOD_SET structure


## -description


The KSMETHOD_SET structure describes the methods that comprise a kernel streaming method set.


## -struct-fields




### -field Set

Specifies a GUID the identifies the kernel streaming method set. For more information about method set GUIDs, see <b>Remarks</b>.


### -field MethodsCount

Specifies the number of methods in this method set.


### -field MethodItem

Points to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff563420">KSMETHOD_ITEM</a> structures. Each structure describes one method of the method set.


### -field FastIoCount

Reserved for system use. Do not use.


### -field FastIoTable

Reserved for system use. Do not use.


## -remarks



Microsoft provides several system-defined kernel streaming method set GUIDs. Minidrivers specify one of these GUIDs in the <b>Set</b> member. Kernel streaming method sets typically begin with a <i>KSMETHODSETID</i> prefix. Method set GUIDs are defined in <i>ks.h</i>, <i>ksmedia.h</i>, <i>bdamedia.h</i>, and possibly other header files.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563420">KSMETHOD_ITEM</a>
 

 

