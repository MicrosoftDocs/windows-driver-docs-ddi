---
UID: NF:hbaapi.HBA_CloseAdapter
title: HBA_CloseAdapter function
author: windows-driver-content
description: The HBA_CloseAdapter routine releases system resources associated with the indicated open HBA handle.
old-location: storage\hba_closeadapter.htm
old-project: storage
ms.assetid: 404c7f82-02dd-4145-91e3-8820f6cbf781
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: HBA_CloseAdapter, HBA_CloseAdapter routine [Storage Devices], fibreHBA_rtns_dcbe3983-fc4d-4a50-886b-6fdb138296a7.xml, hbaapi/HBA_CloseAdapter, storage.hba_closeadapter
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
-	HBA_CloseAdapter
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_CloseAdapter function


## -description


The <b>HBA_CloseAdapter</b> routine releases system resources associated with the indicated open HBA handle.


## -syntax


````
void HBA_API HBA_CloseAdapter(
  _In_ HBA_HANDLE HbaHandle
);
````


## -parameters




### -param handle

TBD




#### - HbaHandle [in]

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA. 


## -returns



None. 




## -see-also

<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>



 

 


