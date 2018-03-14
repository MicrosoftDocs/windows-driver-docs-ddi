---
UID: NF:hbaapi.HBA_RefreshInformation
title: HBA_RefreshInformation function
author: windows-driver-content
description: The HBA_RefreshInformation routine refreshes the library's internally cached data for the indicated HBA.
old-location: storage\hba_refreshinformation.htm
old-project: storage
ms.assetid: 7fd03702-154b-47d4-96cb-6ad9683124ca
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: HBA_RefreshInformation, HBA_RefreshInformation routine [Storage Devices], fibreHBA_rtns_3c486993-5307-42c2-924c-743f635447e8.xml, hbaapi/HBA_RefreshInformation, storage.hba_refreshinformation
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
-	HBA_RefreshInformation
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_RefreshInformation function


## -description


The <b>HBA_RefreshInformation</b> routine refreshes the library's internally cached data for the indicated HBA.


## -syntax


````
void HBA_API HBA_RefreshInformation(
  _In_ HBA_HANDLE HbaHandle
);
````


## -parameters




### -param Handle

TBD




#### - HbaHandle [in]

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA whose cached data the library will refresh.


## -returns



None




## -see-also

<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>



<a href="..\hbaapi\nf-hbaapi-hba_refreshadapterconfiguration.md">HBA_RefreshAdapterConfiguration</a>



 

 


