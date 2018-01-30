---
UID: NF:hwnclx.HwNUnregisterClient
title: HwNUnregisterClient function
author: windows-driver-content
description: Unregisters the hardware notification client driver and its callback functions with the class extension. This function should be invoked when the client driver is unloaded.
old-location: gpiobtn\hwnunregisterclient.htm
old-project: gpiobtn
ms.assetid: 94e5153a-3ce5-400c-b53a-5323b34a6c34
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: gpiobtn.hwnunregisterclient, HwNUnregisterClient, hwnclx/HwNUnregisterClient, HwNUnregisterClient function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Mshwnclxstub.lib
-	Mshwnclxstub.dll
apiname:
-	HwNUnregisterClient
product: Windows
targetos: Windows
req.typenames: "*PHWN_CLX_EXPORT_INDEX, HWN_CLX_EXPORT_INDEX"
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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [gpiobtn\gpiobtn]:%20HwNUnregisterClient function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

