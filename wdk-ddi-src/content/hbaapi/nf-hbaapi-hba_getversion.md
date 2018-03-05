---
UID: NF:hbaapi.HBA_GetVersion
title: HBA_GetVersion function
author: windows-driver-content
description: The HBA_GetVersion routine returns the version of the fibre channel HBA API specification with which the HBA API library is compatible.
old-location: storage\hba_getversion.htm
old-project: storage
ms.assetid: 05fbdc9b-be15-4d1b-96d5-4ea48fb6c543
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: HBA_GetVersion, HBA_GetVersion routine [Storage Devices], fibreHBA_rtns_c4e4bef2-44a6-46e5-8da0-abce57a64f7a.xml, hbaapi/HBA_GetVersion, storage.hba_getversion
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Desktop
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
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hbaapi.dll
api_name:
-	HBA_GetVersion
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_GetVersion function


## -description


The <b>HBA_GetVersion</b> routine returns the version of the fibre channel HBA API specification with which the HBA API library is compatible.


## -syntax


````
HBA_UINT32 HBA_API HBA_GetVersion(void);
````


## -parameters






## -returns



The <b>HBA_GetVersion</b> routine returns a value that indicates the version of the specification with which the library is compliant. A value of 1 indicates version 1 of the specification. A value of 2 indicates version 2 of the specification. All other values are reserved until the future versions of the specification are published.




## -see-also

<a href="..\hbaapi\nf-hbaapi-hba_getvendorlibraryattributes.md">HBA_GetVendorLibraryAttributes</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_GetVersion routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

