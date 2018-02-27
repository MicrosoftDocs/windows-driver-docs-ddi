---
UID: NS:1394._GET_LOCAL_HOST_INFO1
title: "_GET_LOCAL_HOST_INFO1"
author: windows-driver-content
description: The GET_LOCAL_HOST_INFO1 structure contains the data returned by a REQUEST_GET_LOCAL_HOST_INFO request using u.GetLocalHostInformation.nLevel GET_HOST_UNIQUE_ID.
old-location: ieee\get_local_host_info1.htm
old-project: IEEE
ms.assetid: 49ec5322-2caa-4e95-85d0-74b9137d9bcd
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PGET_LOCAL_HOST_INFO1, 1394/GET_LOCAL_HOST_INFO1, 1394/PGET_LOCAL_HOST_INFO1, 1394stct_17301961-cba0-4966-851a-bd92fec75bc7.xml, GET_LOCAL_HOST_INFO1, GET_LOCAL_HOST_INFO1 structure [Buses], IEEE.get_local_host_info1, PGET_LOCAL_HOST_INFO1, PGET_LOCAL_HOST_INFO1 structure pointer [Buses], _GET_LOCAL_HOST_INFO1"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 1394.h
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
-	1394.h
api_name:
-	GET_LOCAL_HOST_INFO1
product: Windows
targetos: Windows
req.typenames: GET_LOCAL_HOST_INFO1, *PGET_LOCAL_HOST_INFO1
---

# _GET_LOCAL_HOST_INFO1 structure


## -description


The GET_LOCAL_HOST_INFO1 structure contains the data returned by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a> request using <b>u.GetLocalHostInformation.nLevel</b> GET_HOST_UNIQUE_ID.


## -syntax


````
typedef struct _GET_LOCAL_HOST_INFO1 {
  LARGE_INTEGER UniqueId;
} GET_LOCAL_HOST_INFO1, *PGET_LOCAL_HOST_INFO1;
````


## -struct-fields




### -field UniqueId

The bus driver fills in this member with the IEEE 1394 globally unique device ID for the host controller.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20GET_LOCAL_HOST_INFO1 structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

