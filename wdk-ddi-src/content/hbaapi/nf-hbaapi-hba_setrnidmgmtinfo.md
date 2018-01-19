---
UID: NF:hbaapi.HBA_SetRNIDMgmtInfo
title: HBA_SetRNIDMgmtInfo function
author: windows-driver-content
description: The HBA_SetRNIDMgmtInfo routine programs the HBA to return the indicated request node identification information data (RNID).
old-location: storage\hba_setrnidmgmtinfo.htm
old-project: storage
ms.assetid: 0c4fbe80-03f2-4ee0-b766-c1ccaa8e83c2
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: HBA_SetRNIDMgmtInfo
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
req.alt-api: HBA_SetRNIDMgmtInfo
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

# HBA_SetRNIDMgmtInfo function



## -description
The <b>HBA_SetRNIDMgmtInfo</b> routine programs the HBA to return the indicated request node identification information data (RNID). 



## -syntax

````
HBA_STATUS HBA_API HBA_SetRNIDMgmtInfo(
  _In_ HBA_HANDLE   HbaHandle,
  _In_ HBA_MGMTINFO *HbaMgmtInfo
);
````


## -parameters

### -param HbaHandle [in]

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the HBA whose RNID is set.  


### -param HbaMgmtInfo [in]

Contains a structure of type <a href="..\hbaapi\ns-hbaapi-hba_mgmtinfo.md">HBA_MgmtInfo</a> that specifies the RNID to associate with the HBA referenced by <i>HbaHandle. </i>


## -returns
The <b>HBA_SetRNIDMgmtInfo</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_SetRNIDMgmtInfo</b> returns one of the following values.
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>Returned if the HBA was successfully programmed to return the specified RNID. 
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>Returned if an unspecified error occurred that prevented the routine from programming the HBA to return the specified RNID. 

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_SetRNIDMgmtInfo routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

