---
UID: NF:hbaapi.HBA_OpenAdapter
title: HBA_OpenAdapter function
author: windows-driver-content
description: The HBA_OpenAdapter routine opens an HBA and returns a handle.
old-location: storage\hba_openadapter.htm
old-project: storage
ms.assetid: 78c37e2c-171b-483c-967d-1b80bde24338
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: HBA_OpenAdapter routine [Storage Devices], storage.hba_openadapter, fibreHBA_rtns_2c583fd9-a3b4-4e35-aa22-31f5f9bb2002.xml, hbaapi/HBA_OpenAdapter, HBA_OpenAdapter
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Hbaapi.dll
apiname:
-	HBA_OpenAdapter
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---

# HBA_OpenAdapter function


## -description


The <b>HBA_OpenAdapter</b> routine opens an HBA and returns a handle.


## -syntax


````
HBA_HANDLE HBA_API HBA_OpenAdapter(
  _In_ PSTR SniaAdapterName
);
````


## -parameters




### -param AdapterName

TBD




#### - SniaAdapterName [in]

Indicates the name of the HBA to open. 


## -returns



The <b>HBA_OpenAdapter</b> routine returns a handle to the open HBA. 



