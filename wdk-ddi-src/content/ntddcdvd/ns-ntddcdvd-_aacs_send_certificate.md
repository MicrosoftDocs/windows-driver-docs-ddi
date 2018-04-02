---
UID: NS:ntddcdvd._AACS_SEND_CERTIFICATE
title: "_AACS_SEND_CERTIFICATE"
author: windows-driver-content
description: The AACS_SEND_CERTIFICATE structure is a wrapper for both an Advanced Access Content System (AACS) certificate and an Authentication Grant Identifier (AGID).
old-location: storage\aacs_send_certificate.htm
old-project: storage
ms.assetid: e0071ee1-7675-4029-b457-e7c26e642c31
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PAACS_SEND_CERTIFICATE, AACS_SEND_CERTIFICATE, AACS_SEND_CERTIFICATE structure [Storage Devices], PAACS_SEND_CERTIFICATE, PAACS_SEND_CERTIFICATE structure pointer [Storage Devices], _AACS_SEND_CERTIFICATE, ntddcdvd/AACS_SEND_CERTIFICATE, ntddcdvd/PAACS_SEND_CERTIFICATE, storage.aacs_send_certificate, structs-DVD_0f4e9fce-96a6-4064-bbb2-4c7077dad635.xml"
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
-	AACS_SEND_CERTIFICATE
product: Windows
targetos: Windows
req.typenames: AACS_SEND_CERTIFICATE, *PAACS_SEND_CERTIFICATE
---

# _AACS_SEND_CERTIFICATE structure


## -description


The AACS_SEND_CERTIFICATE structure is a wrapper for both an Advanced Access Content System (AACS) certificate and an Authentication Grant Identifier (AGID).


## -struct-fields




### -field SessionId

A value of type DVD_SESSION_ID that specifies an AGID.


### -field Certificate

A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff550107">AACS_CERTIFICATE</a> that specifies the certificate to retrieve.


## -remarks



Clients send an Advanced Access Content System (AACS) certificate with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff559297">IOCTL_AACS_SEND_CERTIFICATE</a> request. Clients retrieve an AACS certificate with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff559251">IOCTL_AACS_GET_CERTIFICATE</a> request. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550107">AACS_CERTIFICATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553743">DVD_SESSION_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559251">IOCTL_AACS_GET_CERTIFICATE</a>
 

 

