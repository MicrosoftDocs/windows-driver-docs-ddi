---
UID: NE:61883.CMP_PLUG_LOCATION
title: CMP_PLUG_LOCATION
author: windows-driver-content
description: This enumeration specifies the location of a plug.
old-location: ieee\cmp_plug_location.htm
old-project: IEEE
ms.assetid: C46822B9-2263-4424-853B-32C726D83950
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: 61883/CMP_PlugLocal, 61883/CMP_PLUG_LOCATION, IEEE.cmp_plug_location, CMP_PlugLocal, CMP_PLUG_LOCATION enumeration [Buses], CMP_PlugRemote, 61883/CMP_PlugRemote, CMP_PLUG_LOCATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	CMP_PLUG_LOCATION
product: Windows
targetos: Windows
req.typenames: CMP_PLUG_LOCATION
---

# CMP_PLUG_LOCATION enumeration


## -description


This enumeration specifies the location of a plug.


## -syntax


````
typedef enum  { 
  CMP_PlugLocal   = 0,
  CMP_PlugRemote
} CMP_PLUG_LOCATION;
````


## -enum-fields




### -field CMP_PlugLocal

A local plug.


### -field CMP_PlugRemote

A remote plug.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20CMP_PLUG_LOCATION enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

