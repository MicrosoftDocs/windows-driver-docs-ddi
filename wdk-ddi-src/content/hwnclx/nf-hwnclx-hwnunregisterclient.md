---
UID: NF:hwnclx.HwNUnregisterClient
title: HwNUnregisterClient function
author: windows-driver-content
description: Unregisters the hardware notification client driver and its callback functions with the class extension. This function should be invoked when the client driver is unloaded.
old-location: gpiobtn\hwnunregisterclient.htm
old-project: gpiobtn
ms.assetid: 94e5153a-3ce5-400c-b53a-5323b34a6c34
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: HwNUnregisterClient, HwNUnregisterClient function, gpiobtn.hwnunregisterclient, hwnclx/HwNUnregisterClient
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hwnclx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Mshwnclxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Mshwnclxstub.lib
-	Mshwnclxstub.dll
api_name:
-	HwNUnregisterClient
product: Windows
targetos: Windows
req.typenames: HWN_CLX_EXPORT_INDEX, *PHWN_CLX_EXPORT_INDEX
---

# HwNUnregisterClient function


## -description


Unregisters the hardware notification client driver and its callback functions with the class extension. This function should be invoked when the client driver is unloaded.
			
            


## -syntax


````
FORCEINLINE NTSTATUS  HwNUnregisterClient(
  _In_ WDFDRIVER  Driver
);
````


## -parameters




### -param Driver [in]

Handle to the client drivers framework driver object. 


## -returns



Returns STATUS_SUCCESS if function succeeds. Returns STATUS_INVALID_PARAMETER if corresponding client driver can't be found. Otherwise, it returns one of the error status values defined in Ntstatus.h.




## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn789335">Hardware notifications support</a>



<a href="https://msdn.microsoft.com/405ff6db-9bc0-42f3-a740-49dd3967a8b3">Hardware notifications reference</a>



 

 


