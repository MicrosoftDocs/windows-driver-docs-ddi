---
UID: NS:hpmi._HPMI_QUERY_CAPABILITIES
title: "_HPMI_QUERY_CAPABILITIES"
author: windows-driver-content
description: The HPMI_QUERY_CAPABILITIES structure is used to query HPMI capabilities.
old-location: powermeter\hpmi_query_capabilities.htm
old-project: powermeter
ms.assetid: 9DEEB369-8B9E-40AA-9531-6B8138E5668F
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PHPMI_QUERY_CAPABILITIES, HPMI_QUERY_CAPABILITIES, HPMI_QUERY_CAPABILITIES structure [Power Metering and Budgeting Devices], PHPMI_QUERY_CAPABILITIES, PHPMI_QUERY_CAPABILITIES structure pointer [Power Metering and Budgeting Devices], _HPMI_QUERY_CAPABILITIES, hpmi/HPMI_QUERY_CAPABILITIES, hpmi/PHPMI_QUERY_CAPABILITIES, powermeter.hpmi_query_capabilities"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hpmi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10, version 1709 and later versions of the Windows operating systems.
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
-	hpmi.h
api_name:
-	HPMI_QUERY_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: HPMI_QUERY_CAPABILITIES, *PHPMI_QUERY_CAPABILITIES
---

# _HPMI_QUERY_CAPABILITIES structure


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>HPMI_QUERY_CAPABILITIES</b> structure is used to query HPMI capabilities. 


## -syntax


````
typedef struct _HPMI_QUERY_CAPABILITIES {
  ULONG Version;
} HPMI_QUERY_CAPABILITIES, *PHPMI_QUERY_CAPABILITIES;
````


## -struct-fields




### -field Version

Set to HPMI_QUERY_CAPABILITIES_VERSION_1.  


## -see-also

<a href="https://msdn.microsoft.com/35934D6C-3FB4-4AD4-AA50-BD3A7790269F">hpmi.h</a>



<a href="..\hpmi\ns-hpmi-_hpmi_query_capabilities_response.md">HPMI_QUERY_CAPABILITIES_RESPONSE</a>



<a href="..\hpmi\ni-hpmi-ioctl_hpmi_query_capabilities.md">IOCTL_HPMI_QUERY_CAPABILITIES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [powermeter\powermeter]:%20HPMI_QUERY_CAPABILITIES structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

