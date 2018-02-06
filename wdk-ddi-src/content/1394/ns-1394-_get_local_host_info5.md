---
UID: NS:1394._GET_LOCAL_HOST_INFO5
title: "_GET_LOCAL_HOST_INFO5"
author: windows-driver-content
description: The GET_LOCAL_HOST_INFO5 structure contains the data returned by a REQUEST_GET_LOCAL_HOST_INFO request using u.GetLocalHostInformation.nLevel = GET_HOST_CONFIG_ROM.
old-location: ieee\get_local_host_info5.htm
old-project: IEEE
ms.assetid: a0cdf40e-627e-4d39-9c7b-6defcc2f29c3
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: "_GET_LOCAL_HOST_INFO5, GET_LOCAL_HOST_INFO5 structure [Buses], 1394/PGET_LOCAL_HOST_INFO5, IEEE.get_local_host_info5, PGET_LOCAL_HOST_INFO5, GET_LOCAL_HOST_INFO5, 1394stct_7be8f02e-9734-40ae-9337-91d9026ec65d.xml, 1394/GET_LOCAL_HOST_INFO5, PGET_LOCAL_HOST_INFO5 structure pointer [Buses], *PGET_LOCAL_HOST_INFO5"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	1394.h
apiname:
-	GET_LOCAL_HOST_INFO5
product: Windows
targetos: Windows
req.typenames: GET_LOCAL_HOST_INFO5, *PGET_LOCAL_HOST_INFO5
---

# _GET_LOCAL_HOST_INFO5 structure


## -description


The GET_LOCAL_HOST_INFO5 structure contains the data returned by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a> request using <b>u.GetLocalHostInformation.nLevel</b> = GET_HOST_CONFIG_ROM.


## -syntax


````
typedef struct _GET_LOCAL_HOST_INFO5 {
  PVOID ConfigRom;
  ULONG ConfigRomLength;
} GET_LOCAL_HOST_INFO5, *PGET_LOCAL_HOST_INFO5;
````


## -struct-fields




### -field ConfigRom

Pointer to the beginning of the buffer to be filled with the local host's configuration ROM.


### -field ConfigRomLength

Specifies the length of the buffer pointed to by <b>ConfigRom</b>.


## -remarks


When submitted in a REQUEST_GET_LOCAL_HOST_INFO request, if the <b>ConfigRomLength</b> is smaller than the size of the Configuration ROM, a status code of STATUS_INVALID_BUFFER_SIZE is returned. In this case, the correct buffer size is filled in the <b>ConfigRomLength</b> member.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20GET_LOCAL_HOST_INFO5 structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

