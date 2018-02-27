---
UID: NF:ucmtypes.UCM_PD_POWER_DATA_OBJECT_INIT_FIXED
title: UCM_PD_POWER_DATA_OBJECT_INIT_FIXED function
author: windows-driver-content
description: Initializes a to the UCM_PD_POWER_DATA_OBJECT for a Fixed Supply type Power Data Object.
old-location: buses\ucm_pd_power_data_object_init_fixed.htm
old-project: usbref
ms.assetid: AC51EA77-7F5B-42DE-B366-7BCE46AA5097
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UCM_PD_POWER_DATA_OBJECT_INIT_FIXED, UCM_PD_POWER_DATA_OBJECT_INIT_FIXED function [Buses], buses.ucm_pd_power_data_object_init_fixed, ucmtypes/UCM_PD_POWER_DATA_OBJECT_INIT_FIXED
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ucmtypes.h
api_name:
-	UCM_PD_POWER_DATA_OBJECT_INIT_FIXED
product: Windows
targetos: Windows
req.typenames: UCM_TYPEC_PARTNER
req.product: Windows 10 or later.
---

# UCM_PD_POWER_DATA_OBJECT_INIT_FIXED function


## -description


Initializes a to the <a href="..\ucmtypes\ns-ucmtypes-_ucm_pd_power_data_object.md">UCM_PD_POWER_DATA_OBJECT</a> for a Fixed Supply type Power Data Object.


## -syntax


````
FORCEINLINE void UCM_PD_POWER_DATA_OBJECT_INIT_FIXED(
  _Out_ PUCM_PD_POWER_DATA_OBJECT Pdo
);
````


## -parameters




### -param Pdo [out]

A pointer to a <a href="..\ucmtypes\ns-ucmtypes-_ucm_pd_power_data_object.md">UCM_PD_POWER_DATA_OBJECT</a> structure in which the <b>FixedSupplyPdo.FixedSupply</b> member is set to <b>UcmPdPdoTypeFixedSupply</b>.


## -returns



This function does not return a value.




## -remarks



For different types of Power Data Objects, see the power delivery specification. 

This function initializes the structure and sets Power Data Object as a Fixed Supply type. The client driver must set the remaining members with values relevant to the specific object type.




## -see-also

<a href="..\ucmtypes\ns-ucmtypes-_ucm_pd_power_data_object.md">UCM_PD_POWER_DATA_OBJECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCM_PD_POWER_DATA_OBJECT_INIT_FIXED function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

