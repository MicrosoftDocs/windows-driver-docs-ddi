---
UID: NS:iscsiop._SetCHAPSharedSecret_IN
title: "_SetCHAPSharedSecret_IN"
author: windows-driver-content
description: The SetCHAPSharedSecret_IN structure holds the input data for the SetCHAPSharedSecret method.
old-location: storage\setchapsharedsecret_in.htm
old-project: storage
ms.assetid: d352785b-982f-4469-bee8-6274c0ce1cd6
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: structs-iSCSI_e0aefea0-989e-4834-b812-ae02da2e6f34.xml, iscsiop/PSetCHAPSharedSecret_IN, _SetCHAPSharedSecret_IN, iscsiop/SetCHAPSharedSecret_IN, PSetCHAPSharedSecret_IN structure pointer [Storage Devices], storage.setchapsharedsecret_in, *PSetCHAPSharedSecret_IN, PSetCHAPSharedSecret_IN, SetCHAPSharedSecret_IN structure [Storage Devices], SetCHAPSharedSecret_IN
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iscsiop.h
apiname:
-	SetCHAPSharedSecret_IN
product: Windows
targetos: Windows
req.typenames: "*PSetCHAPSharedSecret_IN, SetCHAPSharedSecret_IN"
---

# _SetCHAPSharedSecret_IN structure


## -description


The SetCHAPSharedSecret_IN structure holds the input data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565585">SetCHAPSharedSecret</a> method.


## -syntax


````
typedef struct _SetCHAPSharedSecret_IN {
  ULONG SharedSecretSize;
  UCHAR SharedSecret[1];
} SetCHAPSharedSecret_IN, *PSetCHAPSharedSecret_IN;
````


## -struct-fields




#### - SharedSecretSize

The size, in bytes, of the shared secret.


#### - SharedSecret

A variable-length array that contains the shared secret.


## -remarks


You must implement this method.



## -see-also

<a href="..\iscsiop\ns-iscsiop-_setchapsharedsecret_out.md">SetCHAPSharedSecret_OUT</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565585">SetCHAPSharedSecret</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SetCHAPSharedSecret_IN structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

