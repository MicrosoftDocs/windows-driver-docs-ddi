---
UID: NS:iscsiop._SetRADIUSSharedSecret_IN
title: "_SetRADIUSSharedSecret_IN"
author: windows-driver-content
description: The SetRADIUSSharedSecret_IN structure holds the input data for the SetRADIUSSharedSecret method.
old-location: storage\setradiussharedsecret_in.htm
tech.root: storage
ms.assetid: 948475eb-0670-4fab-b831-2fdb3ec86032
ms.date: 3/29/2018
ms.keywords: "*PSetRADIUSSharedSecret_IN, PSetRADIUSSharedSecret_IN, PSetRADIUSSharedSecret_IN structure pointer [Storage Devices], SetRADIUSSharedSecret_IN, SetRADIUSSharedSecret_IN structure [Storage Devices], _SetRADIUSSharedSecret_IN, iscsiop/PSetRADIUSSharedSecret_IN, iscsiop/SetRADIUSSharedSecret_IN, storage.setradiussharedsecret_in, structs-iSCSI_0459fa21-0565-414f-bb05-0a7e553e0aa0.xml"
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
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
-	iscsiop.h
api_name:
-	SetRADIUSSharedSecret_IN
product:
- Windows
targetos: Windows
req.typenames: SetRADIUSSharedSecret_IN, *PSetRADIUSSharedSecret_IN
---

# _SetRADIUSSharedSecret_IN structure


## -description


The SetRADIUSSharedSecret_IN structure holds the input data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565815">SetRADIUSSharedSecret</a> method.


## -struct-fields




### -field SharedSecretSize

The size, in bytes, of the shared secret.


### -field SharedSecret

The shared secret.


## -remarks



You must implement this method.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565815">SetRADIUSSharedSecret</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565837">SetRADIUSSharedSecret_OUT</a>
 

 

