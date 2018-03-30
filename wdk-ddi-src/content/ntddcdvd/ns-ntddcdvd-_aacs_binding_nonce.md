---
UID: NS:ntddcdvd._AACS_BINDING_NONCE
title: "_AACS_BINDING_NONCE"
author: windows-driver-content
description: The AACS_BINDING_NONCE structure contains the binding nonce.
old-location: storage\aacs_binding_nonce.htm
old-project: storage
ms.assetid: 8bbefe34-9653-4868-894f-a77c1fc9939f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PAACS_BINDING_NONCE, AACS_BINDING_NONCE, AACS_BINDING_NONCE structure [Storage Devices], PAACS_BINDING_NONCE, PAACS_BINDING_NONCE structure pointer [Storage Devices], _AACS_BINDING_NONCE, ntddcdvd/AACS_BINDING_NONCE, ntddcdvd/PAACS_BINDING_NONCE, storage.aacs_binding_nonce, structs-DVD_4420e26a-681e-4942-9f90-699bcd80b37f.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddcdvd.h
api_name:
-	AACS_BINDING_NONCE
product: Windows
targetos: Windows
req.typenames: AACS_BINDING_NONCE, *PAACS_BINDING_NONCE
---

# _AACS_BINDING_NONCE structure


## -description


The AACS_BINDING_NONCE structure contains the binding nonce.


## -struct-fields




### -field BindingNonce

The binding nonce for the requested logical block address(es) (LBAs).


### -field MAC

A message authentication code (MAC) that clients can use to verify that the binding nonce is for the current Advanced Access Content System (AACS) Authentication sequence.


## -remarks



Clients retrieve the binding nonce with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff559262">IOCTL_AACS_READ_BINDING_NONCE</a> request or an <a href="https://msdn.microsoft.com/library/windows/hardware/ff559248">IOCTL_AACS_GENERATE_BINDING_NONCE</a> request.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559248">IOCTL_AACS_GENERATE_BINDING_NONCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559262">IOCTL_AACS_READ_BINDING_NONCE</a>
 

 

