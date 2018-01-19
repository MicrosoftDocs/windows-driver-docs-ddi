---
UID: NF:hbaapi.HBA_GetRNIDMgmtInfo
title: HBA_GetRNIDMgmtInfo function
author: windows-driver-content
description: The HBA_GetRNIDMgmtInfo routine queries the HBA for request node identification data (RNID) management information.
old-location: storage\hba_getrnidmgmtinfo.htm
old-project: storage
ms.assetid: 8018d52d-4454-4826-933f-a34a70243547
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: HBA_GetRNIDMgmtInfo
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
req.alt-api: HBA_GetRNIDMgmtInfo
req.alt-loc: Hbaapi.dll
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
req.typenames: HBA_WWNTYPE
---

# HBA_GetRNIDMgmtInfo function



## -description
The <b>HBA_GetRNIDMgmtInfo</b> routine queries the HBA for request node identification data (RNID) management information. 



## -syntax

````
HBA_STATUS HBA_API HBA_GetRNIDMgmtInfo(
  _In_  HBA_HANDLE   HbaHandle,
  _Out_ HBA_MGMTINFO *HbaMgmtInfo
);
````


## -parameters

### -param HbaHandle [in]

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA to query for RNID. 


### -param HbaMgmtInfo [out]

Contains a structure of type <a href="..\hbaapi\ns-hbaapi-hba_mgmtinfo.md">HBA_MgmtInfo</a> that holds the RNID management information. 


## -returns
The <b>HBA_GetRNIDMgmtInfo</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_GetRNIDMgmtInfo</b> returns one of the following qualifiers.
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>Returned if the management information was successfully retrieved. 
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>Returned if an unspecified error occurred that prevented the retrieval of the management information. 

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\hbaapi\ns-hbaapi-hba_mgmtinfo.md">HBA_MgmtInfo</a>
</dt>
<dt>
<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_GetRNIDMgmtInfo routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

