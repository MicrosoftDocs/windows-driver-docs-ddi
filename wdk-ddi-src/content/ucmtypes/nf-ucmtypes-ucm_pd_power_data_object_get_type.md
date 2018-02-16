---
UID: NF:ucmtypes.UCM_PD_POWER_DATA_OBJECT_GET_TYPE
title: UCM_PD_POWER_DATA_OBJECT_GET_TYPE function
author: windows-driver-content
description: Retrieves the type of Power Data Object from the UCM_PD_POWER_DATA_OBJECT structure.
old-location: buses\ucm_pd_power_data_object_get_type.htm
old-project: usbref
ms.assetid: ACB0AB92-5EC8-4792-AB40-853FC5AAD125
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: buses.ucm_pd_power_data_object_get_type, UCM_PD_POWER_DATA_OBJECT_GET_TYPE, ucmtypes/UCM_PD_POWER_DATA_OBJECT_GET_TYPE, UCM_PD_POWER_DATA_OBJECT_GET_TYPE function [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucmtypes.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ucmtypes.h
apiname:
-	UCM_PD_POWER_DATA_OBJECT_GET_TYPE
product: Windows
targetos: Windows
req.typenames: UCM_TYPEC_PARTNER
req.product: Windows 10 or later.
---

# UCM_PD_POWER_DATA_OBJECT_GET_TYPE function


## -description


Retrieves the type of Power Data Object from the <a href="..\ucmtypes\ns-ucmtypes-_ucm_pd_power_data_object.md">UCM_PD_POWER_DATA_OBJECT</a> structure. 


## -syntax


````
FORCEINLINE  UCM_PD_POWER_DATA_OBJECT_GET_TYPE(
  _In_ PUCM_PD_POWER_DATA_OBJECT Pdo
);
````


## -parameters




### -param Pdo [in]

A pointer to a <a href="..\ucmtypes\ns-ucmtypes-_ucm_pd_power_data_object.md">UCM_PD_POWER_DATA_OBJECT</a> structure that contains the type of Power Data Object.


## -returns



Returns the <b>Common.Type</b> member of the  <a href="..\ucmtypes\ns-ucmtypes-_ucm_pd_power_data_object.md">UCM_PD_POWER_DATA_OBJECT</a> structure.




## -remarks



For information about the Power Data Object including the types of object, see Power Delivery specification. The Type member of <a href="..\ucmtypes\ns-ucmtypes-_ucm_pd_power_data_object.md">UCM_PD_POWER_DATA_OBJECT</a> indicates the type of Power Data Object.




## -see-also

<a href="..\ucmtypes\ns-ucmtypes-_ucm_pd_power_data_object.md">UCM_PD_POWER_DATA_OBJECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCM_PD_POWER_DATA_OBJECT_GET_TYPE function%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

