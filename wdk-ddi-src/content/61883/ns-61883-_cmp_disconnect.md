---
UID: NS:61883._CMP_DISCONNECT
title: "_CMP_DISCONNECT"
author: windows-driver-content
description: This structure is used to break a connection.
old-location: ieee\cmp_disconnect.htm
old-project: IEEE
ms.assetid: 7EAE617D-EFF9-4F77-9B9C-5985B864B310
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PCMP_DISCONNECT, 61883/CMP_DISCONNECT, 61883/PCMP_DISCONNECT, CMP_DISCONNECT, CMP_DISCONNECT structure [Buses], IEEE.cmp_disconnect, PCMP_DISCONNECT, PCMP_DISCONNECT structure pointer [Buses], _CMP_DISCONNECT"
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
-	61883.h
api_name:
-	CMP_DISCONNECT
product: Windows
targetos: Windows
req.typenames: CMP_DISCONNECT, *PCMP_DISCONNECT
---

# _CMP_DISCONNECT structure


## -description


This structure is used to break a connection. 


## -syntax


````
typedef struct _CMP_DISCONNECT {
  HANDLE hConnect;
} CMP_DISCONNECT, *PCMP_DISCONNECT;
````


## -struct-fields




### -field hConnect

On input, a handle to the connection to break.


## -remarks



If successful, the IEC-61883 protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_SUCCESS. 

If an incorrect parameter is passed in, the protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_INVALID_PARAMETER.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>



 

 


