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


## -parameters






## -returns



The <b>HBA_GetVersion</b> routine returns a value that indicates the version of the specification with which the library is compliant. A value of 1 indicates version 1 of the specification. A value of 2 indicates version 2 of the specification. All other values are reserved until the future versions of the specification are published.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556112">HBA_GetVendorLibraryAttributes</a>
 

 

