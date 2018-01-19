---
UID: NS:61883._CIP_LISTEN
title: _CIP_LISTEN
author: windows-driver-content
description: This structure is used for a listen request. The request begins isochronous reception on the specified connection.
old-location: ieee\cip_listen.htm
old-project: IEEE
ms.assetid: 362ABECF-66D3-4B0B-913B-59F7196D6BFD
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _CIP_LISTEN, CIP_LISTEN, *PCIP_LISTEN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 61883.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CIP_LISTEN
req.alt-loc: 61883.h
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
req.typenames: CIP_LISTEN, *PCIP_LISTEN
---

# _CIP_LISTEN structure



## -description
This structure is used for a listen request. The request begins isochronous reception on the specified connection. This request will start capturing CIP packets, whether the packets have frames attached. 



## -syntax

````
typedef struct _CIP_LISTEN {
  HANDLE hConnect;
} CIP_LISTEN, *PCIP_LISTEN;
````


## -struct-fields

### -field hConnect

On input, the handle of the connection to begin isochronous reception.


## -remarks
If successful, the IEC-61883 protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_SUCCESS. 

If an incorrect parameter is passed in, the protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INVALID_PARAMETER.

If the protocol driver is unable to allocate resources, it sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INSUFFICIENT_RESOURCES.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20CIP_LISTEN structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

