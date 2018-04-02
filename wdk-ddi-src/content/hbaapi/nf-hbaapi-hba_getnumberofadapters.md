---
UID: NF:hbaapi.HBA_GetNumberOfAdapters
title: HBA_GetNumberOfAdapters function
author: windows-driver-content
description: The HBA_GetNumberOfAdapters routine returns the number of HBAs supported by the library.
old-location: storage\hba_getnumberofadapters.htm
old-project: storage
ms.assetid: 5864a535-4ff8-4c9a-abf9-f835c7fde305
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HBA_GetNumberOfAdapters, HBA_GetNumberOfAdapters routine [Storage Devices], fibreHBA_rtns_de5ced35-f290-47fb-ada1-df032be61bfd.xml, hbaapi/HBA_GetNumberOfAdapters, storage.hba_getnumberofadapters
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
-	HBA_GetNumberOfAdapters
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_GetNumberOfAdapters function


## -description


The <b>HBA_GetNumberOfAdapters</b> routine returns the number of HBAs supported by the library. 


## -parameters






## -returns



The <b>HBA_GetNumberOfAdapters</b> routine returns the number of adapters supported by this library. If no adapters are supported, <b>HBA_GetNumberOfAdapters</b> returns 0.




## -remarks



The <b>HBA_GetNumberOfAdapters</b> routine allows the caller to dynamically determine the size of the HBA inventory without having to restart the system, the HBA drivers, or the library. 



