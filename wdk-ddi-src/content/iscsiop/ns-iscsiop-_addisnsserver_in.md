---
UID: NS:iscsiop._AddiSNSServer_IN
title: "_AddiSNSServer_IN"
author: windows-driver-content
description: The AddiSNSServer_IN structure holds the input data for the user-mode AddISNSServer method, which is used to add a new iSNS server entry to the list of iSNS server names that the initiator maintains.
old-location: storage\addisnsserver_in.htm
old-project: storage
ms.assetid: 5d05eeeb-ab68-4770-88c1-483c56dbc116
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PAddiSNSServer_IN, AddiSNSServer_IN, AddiSNSServer_IN structure [Storage Devices], PAddiSNSServer_IN, PAddiSNSServer_IN structure pointer [Storage Devices], _AddiSNSServer_IN, iscsiop/AddiSNSServer_IN, iscsiop/PAddiSNSServer_IN, storage.addisnsserver_in, structs-iSCSI_2c317c93-3fea-4749-98ef-fba28c0cc93f.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
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
-	iscsiop.h
api_name:
-	AddiSNSServer_IN
product: Windows
targetos: Windows
req.typenames: AddiSNSServer_IN, *PAddiSNSServer_IN
---

# _AddiSNSServer_IN structure


## -description


The AddiSNSServer_IN structure holds the input data for the user-mode <b>AddISNSServer</b> method, which is used to add a new iSNS server entry to the list of iSNS server names that the initiator maintains.


## -syntax


````
typedef struct _AddiSNSServer_IN {
  WCHAR iSNSServerName[223 + 1];
} AddiSNSServer_IN, *PAddiSNSServer_IN;
````


## -struct-fields




### -field iSNSServerName

The iSNS server name to add to the list of iSNS servers that the iSCSI initiator maintains.


## -remarks



It is optional that you implement this method.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563091">MSiSCSI_Operations WMI Class</a>



<a href="..\iscsiop\ns-iscsiop-_addisnsserver_out.md">AddiSNSServer_OUT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AddiSNSServer_IN structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

