---
UID: NS:1394._GET_LOCAL_HOST_INFO3
title: "_GET_LOCAL_HOST_INFO3"
author: windows-driver-content
description: The GET_LOCAL_HOST_INFO3 structure contains the data returned by a REQUEST_GET_LOCAL_HOST_INFO request using u.GetLocalHostInformation.nLevel = GET_POWER_SUPPLIED.
old-location: ieee\get_local_host_info3.htm
old-project: IEEE
ms.assetid: 49c24328-dfd9-4d4d-a40f-a375f1384a5c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: "*PGET_LOCAL_HOST_INFO3, IEEE.get_local_host_info3, 1394stct_327b0f83-9367-41ef-8b04-a07338f8725b.xml, GET_LOCAL_HOST_INFO3, _GET_LOCAL_HOST_INFO3, PGET_LOCAL_HOST_INFO3 structure pointer [Buses], PGET_LOCAL_HOST_INFO3, 1394/PGET_LOCAL_HOST_INFO3, 1394/GET_LOCAL_HOST_INFO3, GET_LOCAL_HOST_INFO3 structure [Buses]"
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
-	GET_LOCAL_HOST_INFO3
product: Windows
targetos: Windows
req.typenames: "*PGET_LOCAL_HOST_INFO3, GET_LOCAL_HOST_INFO3"
---

# _GET_LOCAL_HOST_INFO3 structure


## -description


The GET_LOCAL_HOST_INFO3 structure contains the data returned by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a> request using <b>u.GetLocalHostInformation.nLevel</b> = GET_POWER_SUPPLIED.


## -syntax


````
typedef struct _GET_LOCAL_HOST_INFO3 {
  ULONG deciWattsSupplied;
  ULONG Voltage;
} GET_LOCAL_HOST_INFO3, *PGET_LOCAL_HOST_INFO3;
````


## -struct-fields




### -field deciWattsSupplied

Specifies the wattage supplied, in tenths of a watt.


### -field Voltage

Specifies the voltage, in tenths of a volt.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20GET_LOCAL_HOST_INFO3 structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

