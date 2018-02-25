---
UID: NS:ks.KSSTREAMALLOCATOR_STATUS
title: KSSTREAMALLOCATOR_STATUS
author: windows-driver-content
description: The KSSTREAMALLOCATOR_STATUS structure describes framing requirements and current number of allocated frames for a specific allocator.
old-location: stream\ksstreamallocator_status.htm
old-project: stream
ms.assetid: 95ef6c1e-c2b7-49ca-9aaf-caeb2dca7c3a
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PKSSTREAMALLOCATOR_STATUS, ,, A, C, E, K, KSSTREAMALLOCATOR_STATUS, KSSTREAMALLOCATOR_STATUS structure [Streaming Media Devices], L, M, O, P, PKSSTREAMALLOCATOR_STATUS, PKSSTREAMALLOCATOR_STATUS structure pointer [Streaming Media Devices], R, S, T, U, _, ks-struct_e9071d70-ee9c-4ef9-828e-81d9abf6cc68.xml, ks/KSSTREAMALLOCATOR_STATUS, ks/PKSSTREAMALLOCATOR_STATUS, stream.ksstreamallocator_status"
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
-	KSSTREAMALLOCATOR_STATUS
product: Windows
targetos: Windows
req.typenames: KSSTREAMALLOCATOR_STATUS, *PKSSTREAMALLOCATOR_STATUS
---

# KSSTREAMALLOCATOR_STATUS structure


## -description


The KSSTREAMALLOCATOR_STATUS structure describes framing requirements and current number of allocated frames for a specific allocator.


## -syntax


````
typedef struct {
  KSALLOCATOR_FRAMING Framing;
  ULONG               AllocatedFrames;
  ULONG               Reserved;
} KSSTREAMALLOCATOR_STATUS, *PKSSTREAMALLOCATOR_STATUS;
````


## -struct-fields




### -field Framing

A <a href="..\ks\ns-ks-ksallocator_framing.md">KSALLOCATOR_FRAMING</a> structure that contains the framing specified when the allocator was created.


### -field AllocatedFrames

Contains the current number of allocated frames. This value changes on an extremely frequent basis.


### -field Reserved

Reserved and set to zero.


## -remarks



Clients can query allocator status by providing a KSSTREAMALLOCATOR_STATUS structure in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565670">KSPROPERTY_STREAMALLOCATOR_STATUS</a> property request.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565670">KSPROPERTY_STREAMALLOCATOR_STATUS</a>



<a href="..\ks\ns-ks-ksallocator_framing.md">KSALLOCATOR_FRAMING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSSTREAMALLOCATOR_STATUS structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

