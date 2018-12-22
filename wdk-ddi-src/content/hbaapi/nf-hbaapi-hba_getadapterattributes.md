---
UID: NF:hbaapi.HBA_GetAdapterAttributes
title: HBA_GetAdapterAttributes function
description: The HBA_GetAdapterAttributes routine retrieves the attributes for an HBA.
old-location: storage\hba_getadapterattributes.htm
tech.root: storage
ms.assetid: a172f53c-9993-4d52-ae3f-35a8ab5745f6
ms.date: 03/29/2018
ms.keywords: HBA_GetAdapterAttributes, HBA_GetAdapterAttributes routine [Storage Devices], fibreHBA_rtns_f7675f0c-2f71-428e-871b-90c51a1b5bc4.xml, hbaapi/HBA_GetAdapterAttributes, storage.hba_getadapterattributes
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
-	HBA_GetAdapterAttributes
product:
- Windows
targetos: Windows
req.typenames: 
---

# HBA_GetAdapterAttributes function


## -description


The <b>HBA_GetAdapterAttributes</b> routine retrieves the attributes for an HBA. 


## -parameters




### -param Handle

<p>Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/Ff557097(v=VS.85).aspx"><b>HBA_OpenAdapter</b></a> that identifies the HBA on which the port is located.  </p>


### -param HbaAttributes

<p>Contains, on return, a structure of type <a href="https://msdn.microsoft.com/library/Ff556044(v=VS.85).aspx"><b>HBA_AdapterAttributes</b></a> that holds the HBA attributes. </p>




## -returns



The <b>HBA_GetAdapterAttributes</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556044">HBA_AdapterAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
 

 

