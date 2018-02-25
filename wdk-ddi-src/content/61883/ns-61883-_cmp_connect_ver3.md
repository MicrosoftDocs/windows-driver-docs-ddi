---
UID: NS:61883._CMP_CONNECT_VER3
title: "_CMP_CONNECT_VER3"
author: windows-driver-content
description: This structure contains information for a connection request.
old-location: ieee\cmp_connect_ver3.htm
old-project: IEEE
ms.assetid: 1F2C2B8E-6535-40F1-A5D3-46DAD43E923E
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , *, *PCMP_CONNECT, *PCMP_CONNECT_VER3, ,, 3, 61883/CMP_CONNECT_VER3, 61883/PCMP_CONNECT_VER3, C, CMP_CONNECT, CMP_CONNECT_VER3, CMP_CONNECT_VER3 structure [Buses], E, IEEE.cmp_connect_ver3, M, N, O, P, PCMP_CONNECT_VER3, PCMP_CONNECT_VER3 structure pointer [Buses], R, T, V, _, _CMP_CONNECT_VER3"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	61883.h
apiname:
-	CMP_CONNECT_VER3
product: Windows
targetos: Windows
req.typenames: CMP_CONNECT_VER3, *PCMP_CONNECT_VER3
---

# _CMP_CONNECT_VER3 structure


## -description


This structure contains information for a connection request.


## -syntax


````
typedef struct _CMP_CONNECT_VER3 {
  HANDLE               hOutputPlug;
  HANDLE               hInputPlug;
  CMP_CONNECT_TYPE     Type;
  CIP_DATA_FORMAT_VER3 Format;
  HANDLE               hConnect;
} CMP_CONNECT_VER3, *PCMP_CONNECT_VER3;
````


## -struct-fields




### -field hOutputPlug

The handle of an output plug.


### -field hInputPlug

The handle of an input plug.


### -field Type

The type of the requested connection.


### -field Format

The requested data format.


### -field hConnect

The handle for the created connection.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20CMP_CONNECT_VER3 structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

