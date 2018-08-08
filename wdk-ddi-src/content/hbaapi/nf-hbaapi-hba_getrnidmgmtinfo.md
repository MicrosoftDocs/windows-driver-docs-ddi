---
UID: NF:hbaapi.HBA_GetRNIDMgmtInfo
title: HBA_GetRNIDMgmtInfo function
author: windows-driver-content
description: The HBA_GetRNIDMgmtInfo routine queries the HBA for request node identification data (RNID) management information.
old-location: storage\hba_getrnidmgmtinfo.htm
tech.root: storage
ms.assetid: 8018d52d-4454-4826-933f-a34a70243547
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HBA_GetRNIDMgmtInfo, HBA_GetRNIDMgmtInfo routine [Storage Devices], fibreHBA_rtns_73ba5195-497c-4105-9b4c-eccd637962b9.xml, hbaapi/HBA_GetRNIDMgmtInfo, storage.hba_getrnidmgmtinfo
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
-	HBA_GetRNIDMgmtInfo
product:
- Windows
targetos: Windows
req.typenames: 
---

# HBA_GetRNIDMgmtInfo function


## -description


The <b>HBA_GetRNIDMgmtInfo</b> routine queries the HBA for request node identification data (RNID) management information. 


## -parameters




### -param Handle

TBD


### -param pInfo

TBD




#### - HbaHandle [in]

Contains a value returned by the routine <a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a> that identifies the HBA to query for RNID. 


#### - HbaMgmtInfo [out]

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557092">HBA_MgmtInfo</a> that holds the RNID management information. 


## -returns



The <b>HBA_GetRNIDMgmtInfo</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_GetRNIDMgmtInfo</b> returns one of the following qualifiers.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>
</td>
<td width="60%">
Returned if the management information was successfully retrieved. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the retrieval of the management information. 

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557092">HBA_MgmtInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557097">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
 

 

