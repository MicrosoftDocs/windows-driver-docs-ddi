---
UID: NS:ntddcdvd._AACS_BINDING_NONCE
title: "_AACS_BINDING_NONCE"
author: windows-driver-content
description: The AACS_BINDING_NONCE structure contains the binding nonce.
old-location: storage\aacs_binding_nonce.htm
old-project: storage
ms.assetid: 8bbefe34-9653-4868-894f-a77c1fc9939f
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PAACS_BINDING_NONCE structure pointer [Storage Devices], ntddcdvd/PAACS_BINDING_NONCE, structs-DVD_4420e26a-681e-4942-9f90-699bcd80b37f.xml, ntddcdvd/AACS_BINDING_NONCE, AACS_BINDING_NONCE structure [Storage Devices], PAACS_BINDING_NONCE, *PAACS_BINDING_NONCE, _AACS_BINDING_NONCE, storage.aacs_binding_nonce, AACS_BINDING_NONCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
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
-	ntddcdvd.h
apiname:
-	AACS_BINDING_NONCE
product: Windows
targetos: Windows
req.typenames: "*PAACS_BINDING_NONCE, AACS_BINDING_NONCE"
---

# _AACS_BINDING_NONCE structure


## -description


The AACS_BINDING_NONCE structure contains the binding nonce.


## -syntax


````
typedef struct _AACS_BINDING_NONCE {
  UCHAR BindingNonce[16];
  UCHAR MAC[16];
} AACS_BINDING_NONCE, *PAACS_BINDING_NONCE;
````


## -struct-fields




### -field BindingNonce

The binding nonce for the requested logical block address(es) (LBAs).


### -field MAC

A message authentication code (MAC) that clients can use to verify that the binding nonce is for the current Advanced Access Content System (AACS) Authentication sequence.


## -remarks



Clients retrieve the binding nonce with an <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_read_binding_nonce.md">IOCTL_AACS_READ_BINDING_NONCE</a> request or an <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_generate_binding_nonce.md">IOCTL_AACS_GENERATE_BINDING_NONCE</a> request.




## -see-also

<a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_read_binding_nonce.md">IOCTL_AACS_READ_BINDING_NONCE</a>



<a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_generate_binding_nonce.md">IOCTL_AACS_GENERATE_BINDING_NONCE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AACS_BINDING_NONCE structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

